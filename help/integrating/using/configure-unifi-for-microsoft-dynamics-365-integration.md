---
title: Configurar la integración de Unifi para Microsoft Dynamics 365
description: Obtenga información sobre cómo configurar la integración de Unifi para Microsoft Dynamics 365
page-status-flag: never-activated
uuid: effa1028-66b2-4bef-b5e4-7319dbb23d5d
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics
discoiquuid: eb3639f5-7246-46c4-8ddb-da9413b40c32
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---



# Configurar la integración de Unifi para Microsoft Dynamics 365

Configure Unifi para configurar y activar la integración de Microsoft Dynamics 365 - Adobe Campaign.

## Requisitos previos

Antes de realizar los pasos posteriores al aprovisionamiento en este artículo, se da por hecho que ya ha completado correctamente los pasos [posteriores al aprovisionamiento para la Campaña](../../integrating/using/configure-adobe-io-for-ms-dynamic.md) y [para Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).  Si esto no ha sucedido, deberá seguir estos pasos para completar el Campaign Standard y el postaprovisionamiento de Dynamics 365.

También se da por hecho que se ha puesto en contacto con Unifi, que se le ha creado una cuenta de Unifi y que ha podido iniciar sesión con éxito.  Si esto no ha sucedido, siga los pasos descritos en [este artículo](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md).

>[!CAUTION]
>
>Se recomienda encarecidamente que trabaje con la asesoría de Unifi y/o Adobe (póngase en contacto con su CSM de Adobe) al configurar Unifi.

## Configurar la integración de Campañas

En la primera conexión, haga clic en **[!UICONTROL Adobe Campaign Standard]** para introducir las credenciales de Campaña.

La mayoría de estas credenciales provienen de la integración creada en la consola de Adobe I/O durante los pasos [de configuración del](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)Campaign Standard.

>[!NOTE]
>
>Para garantizar la seguridad y la privacidad, los campos de credenciales confidenciales aparecen en blanco al volver a visitar estas pantallas de configuración.

1. Para la URL de autenticación de Adobe, introduzca `https://ims-na1.adobelogin.com/ims/exchange/jwt`

1. Escribe tu **[!UICONTROL Adobe IO Organization ID]** y tu **[!UICONTROL Adobe IO Integration ID]**.

Para obtener los ID de integración y organización de E/S de Adobe, vaya a la pantalla Integración de la consola de Adobe I/O en pantalla y anote la URL web.

Debería tener este aspecto: `https://console.adobe.io/integrations/<Org ID>/<Int ID>/overview`, donde ID de organización e ID de entrada son números.

1. Especifique la **[!UICONTROL Tenant ID]**

Para obtener su ID de inquilino, siga los pasos a continuación:

1. Vaya a la Consola [de administración de](https://adminconsole.adobe.com/) Adobe y seleccione su organización de IMS en el menú desplegable superior derecho.
1. Seleccione el producto Adobe Campaign Standard y, a continuación, seleccione la instancia de Campaign Standard (si tiene más de uno).  Esto mostrará una lista de perfiles de productos.

   Las descripciones de los perfiles de productos suelen aparecer en uno de los siguientes formatos, donde `<tenantID>` es el ID de inquilino de la instancia.

`Campaign Standard – https://<tenantID> - <ROLE>`

`Campaign Standard – <tenantID> - <ROLE>`

>[!NOTE]
>
>Si tiene problemas para identificar su ID de inquilino, póngase en contacto con usted > contacto técnico de Adobe o con el servicio de atención al cliente de Adobe.
>
>Los ID de inquilinos de instancias de simulación de pruebas de socio suelen seguir el patrón `https://<tenantId>`, donde `tenantId` está `tbd.campaign-sandbox.adobe.com`.

1. Escriba su **[!UICONTROL Campaign Instance ID]**.

Para obtener su ID de instancia, siga los pasos a continuación:

    1. Escriba &quot;https://&lt;acs-instance-url>/r/test&quot; en un navegador web, reemplazando &quot;&lt;acs-instance-url>&quot; por la dirección URL de la instancia de Campaign Standard.
    1. La respuesta contendrá &quot;instance=&quot;, seguido del ID de instancia.

1. Seleccione la región de la instancia de Campaña.

1. Puede dejar **[!UICONTROL Base Directory]** en blanco.

1. Seleccione la **[!UICONTROL Allow as Output Destination]** opción.

Una vez configurados los parámetros, haga clic en **[!UICONTROL CONNECT]** y compruebe que la conexión es correcta.

Si no es así, haga clic en **[!UICONTROL CLOSE]** y marque los parámetros.

>[!NOTE]
>
>Si no puede completar este paso, póngase en contacto con el servicio [de atención al cliente de](mailto:support@unifisoftware.atlassian.net)Unifi.

## Configuración de la integración de Dynamics 365

Haga clic en Microsoft Dynamics CRM para configurar las credenciales de Dynamics 365. La mayoría de estas credenciales provienen de la integración creada en Microsoft Dynamics 365 durante los pasos de configuración de Microsoft Dynamics 365.

>[!NOTE]
>
>Para garantizar la seguridad y la privacidad, los campos de credenciales confidenciales aparecen en blanco al volver a visitar estas pantallas de configuración.

1. Por **[!UICONTROL URL]**, escriba la dirección URL de la instancia de Dynamics 365, teniendo cuidado de insertar &quot;.api&quot; antes de &quot;.crm&quot; (por ejemplo, `https://mydynamicsinstance.api.crm.dynamics.com`)

1. Por **[!UICONTROL clientid]**, utilizará el ID de aplicación que se generó cuando creó el registro de la aplicación al [configurar Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Por **[!UICONTROL clientsecret]**, utilizará el secreto de cliente que se generó al agregar un secreto de cliente al registro de la aplicación al [configurar Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Por **[!UICONTROL callbackurl]**, agregue `http://localhost:33333`.

1. Por **[!UICONTROL refresh token]**, deje en blanco.

1. Para el ID **[!UICONTROLde]** inquilino, utilice el ID de inquilino que obtuvo de portal.azure.com para [configurar Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

1. Por último, marque la casilla de verificación para **[!UICONTROL Allow as Output Destination]**.

Una vez introducidos los parámetros, haga clic en **[!UICONTROL CONNECT]** y compruebe que la conexión es correcta.

Si no es así, haga clic en **[!UICONTROL CLOSE]** y marque los parámetros.

>[!NOTE]
>
>Si no puede completar este paso, póngase en contacto con el servicio [de atención al cliente de](mailto:support@unifisoftware.atlassian.net)Unifi.

## Finalización de configuración de Unifi

Una vez configuradas las credenciales, debe notificar a Unifi que es necesario realizar algunos pasos adicionales para poder finalizar la configuración de integración.  Póngase en contacto con la información de contacto de Unifi que le ha proporcionado para indicarle que ha configurado sus credenciales.

Debe seleccionar una opción de exclusión y notificar a Unifi cuando se complete (indicando a Unifi qué opción de exclusión se está seleccionando).  Encontrará una explicación de las opciones de exclusión en la Guía del usuario [Unifi](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn).

Una vez que Unifi complete su trabajo, le notificarán y le proporcionarán más información para ayudarle a configurar su instancia de Unifi, a ejecutar el ingreso de datos una vez y, una vez que la finalización sea exitosa, podrá habilitar los programas.

Se recomienda la siguiente frecuencia para diversos casos de uso:

* Ingreso: Cada 15 minutos
* Huevo: Cada 15 minutos
* Elimina: Cada día
* Opciones de exclusión: Cada día

>[!NOTE]
>
>De forma predeterminada, los eventos de marketing ENVIAR se filtran fuera del trabajo de salida.  Si desea ver eventos de marketing SEND en Dynamics 365, debe modificar el filtro (paso 5) del trabajo de salida en Unifi.

Hay dos funciones distintas en Unifi, un usuario propietario y un usuario analista de sólo lectura. Un usuario propietario tiene la capacidad de modificar trabajos y programaciones, mientras que el analista de solo lectura no.  Sólo puede haber un usuario propietario para una instancia de cliente determinada.  Si el cliente necesita cambiar la persona asignada como usuario propietario, puede enviar un correo electrónico a [adobe-support@unifisoftware.com](mailto: adobe-support@unifisoftware.com) con el cambio solicitado.

La configuración, los detalles del trabajo, la configuración y el monitoreo de Unifi se presentan en los siguientes videos.

## Trabajos Unifi

### Visión general de los trabajos Unifi

>[!VIDEO](https://video.tv.adobe.com/v/27392)

En este vídeo se explican los diferentes trabajos Unifi necesarios para la integración de Adobe Campaign Standard con Microsoft Dynamics 365 (02:10 min)

### Detalles del trabajo Unifi: Ingreso y salida

>[!VIDEO](https://video.tv.adobe.com/v/27396)

Este vídeo explica los trabajos de ingreso y salida en Unifi (04:27 min)

### Operacionalización y supervisión

>[!VIDEO](https://video.tv.adobe.com/v/27391)

Este vídeo explica los flujos de trabajo y programaciones (03:03 min)

Más parecido a esto
* [Uso de Adobe Campaign Standard - Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* [Configuración de Microsoft Dynamics 365 para la integración de Campañas](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md)
* [Configuración de la integración de Adobe IO para Microsoft Dynamics 365 - Campaign Standard](../../integrating/using/configure-adobe-io-for-ms-dynamic.md)
* [Página de características de integración de Microsoft Dynamics 365](https://helpx.adobe.com/campaign/kt/acs/using/acs-ms-dynamics-crm-connector-tutorial.html)