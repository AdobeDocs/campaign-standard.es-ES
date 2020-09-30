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
source-git-commit: b0e69280912ee70e6f53efd24782474395c57f74
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# Configuración del acceso a API {#setting-up-api-access}

El acceso a la API de Adobe Campaign Standard se configura a través de los pasos a continuación. Cada uno de estos pasos se detalla en la documentación [de E/S de](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe.

>[!IMPORTANT]
>
>Para administrar certificados en E/S de Adobe, asegúrese de que tiene derechos de administrador <b></b> del sistema en la organización o una cuenta [de](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> desarrollador en la consola de administración.

1. **Compruebe que dispone de un certificado** digital o cree uno si es necesario. Las claves pública y privada que se proporcionan con el certificado son necesarias en los pasos siguientes.
1. **Cree una nueva integración con el servicio** Adobe Campaign en E/S de Adobe y configúrela. Se generarán las credenciales (clave de API, secreto de cliente...).
1. **Cree un token web JSON (JWT)** a partir de las credenciales generadas anteriormente y fírmelo con su clave privada. JWT codifica toda la información de identidad y seguridad que Adobe necesita para comprobar su identidad y permitirle acceder a la API.
1. **Intercambiar el JWT por un Token de acceso** a través de una solicitud de POST. Este Token de acceso deberá utilizarse en cada encabezado de las solicitudes de API.

Para establecer una sesión segura de API de E/S de Adobe de servicio a servicio, cada solicitud a un servicio de Adobe debe incluir en el encabezado de Autorización la información siguiente.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;ORGANIZACIÓN>**: Este es su ID de organización personal, el Adobe proporciona un ID de organización para cada una de sus instancias:

   * &lt;ORGANIZACIÓN> : la instancia de producción,
   * &lt;ORGANIZATION-mkt-stage>: la instancia de escenario.

   Para obtener el valor de ID de la organización, consulte con el administrador o con el contacto técnico de Adobe. También puede recuperarla en la E/S de Adobe al crear una nueva integración, en la lista de licencias (consulte la documentación <a href="https://www.adobe.io/authentication.html">de E/S de</a>Adobe).

* **&lt;ACCESS_TOKEN>**: Su token de acceso personal, que se recuperó al intercambiar el autentificador web JSON mediante una solicitud de POST.

* **&lt;API_KEY>**: su clave de API personal. Se proporciona en E/S de Adobe después de crear una nueva integración en Adobe Campaign Service.

   ![texto alt](assets/tenant.png)

## Resolución de problemas

Durante la integración de AdobeIO, si aparece el siguiente error:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Consulte al administrador o al contacto técnico de Adobe para comprobar si el parámetro CNAME se ha creado correctamente.