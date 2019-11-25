---
title: Configuración del acceso a la API
description: Obtenga información sobre cómo configurar el acceso a las API de Campaign Standard.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Configuración del acceso a API {#setting-up-api-access}

El acceso a la API de Adobe Campaign Standard se configura a través de los pasos a continuación. Cada uno de estos pasos se detalla en la documentación [de E/S de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe.

>[!CAUTION]
>
>Para administrar certificados en la E/S de Adobe, asegúrese de que tiene derechos de administrador <b></b> del sistema en la organización o una cuenta <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">de</a> desarrollador en la consola de administración.

1. **Compruebe que dispone de un certificado** digital o cree uno si es necesario. Las claves pública y privada que se proporcionan con el certificado son necesarias en los pasos siguientes.
1. **Cree una nueva integración en el servicio** de Adobe Campaign en la E/S de Adobe y configúrela. Se generarán las credenciales (clave de API, secreto de cliente...).
1. **Cree un token web JSON (JWT)** a partir de las credenciales generadas anteriormente y fírmelo con su clave privada. JWT codifica toda la información de identidad y seguridad que Adobe necesita para verificar su identidad y permitirle acceder a la API.
1. **Intercambie el JWT por un autentificador** de acceso a través de una solicitud POST. Este autentificador de acceso deberá utilizarse en cada encabezado de las solicitudes de API.

Para establecer una sesión segura de la API de Adobe I/O servicio a servicio, cada solicitud a un servicio de Adobe debe incluir en el encabezado Autorización la información siguiente.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZACIÓN&gt;**: Este es su ID de organización personal; Adobe proporciona un ID de organización para cada una de sus instancias:

   * &lt;ORGANIZACIÓN&gt; : la instancia de producción,
   * &lt;ORGANIZATION-mkt-stage&gt;: la instancia de escenario.
   Para obtener el valor de ID de organización, consulte a su administrador o al contacto técnico de Adobe. También puede recuperarla en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la documentación <a href="https://www.adobe.io/authentication.html">de E/S de</a>Adobe).

* **&lt;ACCESS_TOKEN&gt;**: Su autentificador de acceso personal, que se recuperó al intercambiar el autentificador web JSON a través de una solicitud POST.

* **&lt;API_KEY&gt;**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración en el servicio Adobe Campaign.

   ![texto alt](assets/tenant.png)
