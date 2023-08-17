---
title: Configuración de la aplicación de integración de Campaign-Dynamics
description: Obtenga información sobre cómo configurar la aplicación de integración de Campaign y Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 184bc656-2107-4380-9b35-148cb4380547
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 4%

---

# Conexión de sistemas con la aplicación de integración

## Añadir credenciales a la aplicación de integración

El **[!UICONTROL Settings]** le permite especificar las credenciales de la API de Adobe y Microsoft Dynamics 365. También puede definir las opciones relacionadas con la instancia SFTP de Adobe Campaign.

### Credenciales de Microsoft Dynamics 365

Las credenciales de Microsoft Dynamics 365 otorgan permiso a la aplicación de integración para extraer los datos de Microsoft Dynamics 365.  Primero debe seguir los pasos de la pantalla [Configuración de Microsoft Dynamics 365 para integración con Campaign](../../integrating/using/d365-acs-configure-d365.md) para generar los valores que se pegarán en esta pantalla. Las entradas que se describen a continuación harán referencia a esta pantalla.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**: Obtenga información sobre cómo hacer referencia a su ID de cliente en [esta sección](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**: Obtenga información sobre cómo generar el Secreto del cliente en [esta sección](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**: Obtenga información sobre cómo encontrar su ID de inquilino en [esta sección](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**: la dirección URL tendrá el formato `https://&lt;servername&gt;.api.crm.dynamics.com/`

### Credenciales de API de Adobe

Las credenciales de Adobe Campaign se generan mediante [Adobe I/O](https://www.adobe.io/). Tendrá que visitar la pantalla [Configuración del Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) y siga las instrucciones antes de poder completar las entradas de esta sección.

La siguiente imagen explica en detalle la asignación entre el Adobe I/O y las entradas de la pantalla de configuración.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Clave privada*: el proceso a para definir esto comienza haciendo clic en el botón &quot;Generar par de claves pública/privada&quot;. Esto creará un archivo zip que debe descargar. Una vez descargado, descomprima el archivo, que generará dos archivos llamados certificate_pub.crt y private.key. Asegúrese de colocar la clave private.key en un lugar seguro y no la comparta. Abra el archivo private.key en un editor de texto. Copie todo el valor en el editor de texto (ctrl-A y después ctrl-C en un equipo o cmd-A y luego cmd-C en un Mac). Esto debe incluir las líneas con &quot;BEGIN PRIVATE KEY&quot; y &quot;END PRIVATE KEY&quot; en su totalidad. Pegue todo este texto multilínea en la entrada &quot;Private Key&quot; de la pantalla Settings.

* *URL*: Este valor se ajustará al patrón https\://mc.adobe.io/&lt;campaign-instance-name>. El encabezado de la aplicación de integración incluye &quot;Org&quot; e &quot;Instance&quot;. La parte &quot;campaign-instance-name&quot; de la dirección URL sería simplemente el nombre encontrado en este valor de instancia.

## Configuración de SFTP de Adobe Campaign {#ac-smtp-settings}

Esta configuración es opcional. Debe definirlos si planea utilizar la instancia SFTP de Adobe Campaign para generar registros de salida desde el conector. Esto resulta útil si experimenta problemas cuando la integración se está ejecutando y necesita depurar por qué el resultado no cumple sus expectativas.

El otro motivo para configurar el servidor SFTP sería si planea ejecutar el flujo de trabajo de inclusión/exclusión y hay un flujo de datos de Adobe Campaign a Microsoft Dynamics 365, ya sea **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Usted es responsable de la información a la que accede y descarga desde las carpetas SFTP. Si la información contiene datos personales, usted es responsable de cumplir con las leyes y regulaciones de privacidad aplicables. [Más información](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).
>

Para definir la configuración SFTP de Campaign para la integración con Microsoft Dynamics 365, acceda a la siguiente sección:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-settings-sftp.png)

Debe especificar lo siguiente:

* **Host SFTP**: este campo contiene &lt;campaign-instance-name>.campaign.adobe.com. El encabezado de la aplicación de integración incluye **Org** y **Instancia**. La parte &quot;campaign-instance-name&quot; de la dirección URL sería simplemente el nombre encontrado en este valor de instancia.

* **Usuario de SFTP**: Si tiene el usuario de SFTP, agréguelo aquí. De lo contrario, consulte [esta sección](#ac-control-panel-settings). Como parte del proceso, se le mostrará el nombre de usuario.

* **Clave SFTP**: Si tiene una clave SSH, añádala aquí. De lo contrario, consulte [esta sección](#ac-control-panel-settings).

* El **Intervalos de IP** será necesario que se incluya en la configuración del SFTP de Adobe Campaign. Deberán estar incluidos en la lista de permitidos para que la integración pueda utilizar el punto final SFTP.

* El **¿Desea exportar los registros al SFTP de Adobe Campaign?** permite determinar si la integración generará información de registro en el extremo SFTP. Se puede usar para depurar si Adobe Campaign o Microsoft Dynamics 365 no muestran la información que espera.

## Configuración de SFTP en Adobe Campaign {#ac-control-panel-settings}

Descubra la administración de SFTP con [Panel de control de Campaign de campaña](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es) en estas secciones:

* [Acerca de la administración SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=es#sftp-management)

* [Administración de almacenamiento SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#installing-ssh-key)

* [Agregar intervalos de IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html#sftp-management)

* [Administrar claves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html#sftp-management)

* [Inicio de sesión en el servidor SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html#sftp-management)

Una vez completada la configuración, inicie sesión en el servidor SFTP con la clave privada y cree el directorio &quot;d365_loads/exports&quot;.

[Visite esta página](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=es#sftp-management) para obtener información sobre el servidor SFTP de Adobe Campaign Standard.
