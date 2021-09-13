---
title: Configuración del acceso a la API
description: Obtenga información sobre cómo configurar el acceso a las API de Campaign Standard.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: efbbd0cd-9c56-4ad0-8bcb-efba4b63c28b
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---

# Configuración del acceso a API {#setting-up-api-access}

El acceso a la API de Adobe Campaign Standard se configura siguiendo los pasos que se indican a continuación. Cada uno de estos pasos se detalla en la [documentación de IO de Adobe](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!IMPORTANT]
>
>Para administrar certificados en Adobe IO, asegúrese de que tiene <b>derechos de administrador del sistema</b> en la organización o una [cuenta de desarrollador](https://helpx.adobe.com/enterprise/using/manage-developers.html)</a> en Admin Console.

1. **Compruebe que tiene un certificado** digital o cree uno si es necesario. Las claves pública y privada proporcionadas con el certificado son necesarias en los siguientes pasos.
1. **Cree una nueva integración a Adobe Campaign** Service en Adobe IO y configúrela. A continuación, se generarán sus credenciales (clave de API, secreto de cliente...).
1. **Cree un token web JSON (JWT)**  a partir de las credenciales generadas anteriormente y firme con su clave privada. El JWT codifica toda la información de identidad y seguridad que necesita el Adobe para comprobar su identidad y permitirle acceder a la API.
1. **Intercambie su JWT por un token de acceso** a través de una solicitud de POST. Este token de acceso debe utilizarse en cada encabezado de sus solicitudes de API.

Para establecer una sesión de API de Adobe I/O de servicio a servicio segura, cada solicitud a un servicio de Adobe debe incluir en el encabezado Autorización la siguiente información.

```
-X GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServices/profile \
-H 'Content-Type: application/json' \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>'
```

* **&lt;organization>**: Este es su ID de organización personal, el Adobe proporciona un ID de organización para cada una de sus instancias:

   * &lt;organization> : la instancia de producción,
   * &lt;organization-mkt-stage>: la instancia de stage.

   Para obtener el valor de ID de organización, consulte con el administrador o con el contacto técnico de Adobe. También puede recuperarla en Adobe I/O al crear una nueva integración, en la lista de licencias (consulte la <a href="https://www.adobe.io/authentication.html">documentación de IO de Adobe</a>).

* **&lt;access_token>**: Su token de acceso personal, que se recuperó al intercambiar su token web JSON mediante una solicitud del POST.

* **&lt;api_key>**: su clave de API personal. Se proporciona en Adobe I/O después de crear una nueva integración en Adobe Campaign Service.

   ![texto alternativo](assets/tenant.png)

## Resolución de problemas

Durante la integración con AdobeIO, si aparece el siguiente error:

```
{ 
"code": 502, 
"message": "Oops. Something went wrong. Check your URI and try again." 
}
```


Consulte a su administrador o al contacto técnico de su Adobe para comprobar si el parámetro CNAME se ha creado correctamente.
