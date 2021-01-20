---
title: Configurar la aplicación de integración de Campaña-Dynamics
description: Obtenga información sobre cómo configurar la aplicación de integración Campaña-Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '795'
ht-degree: 2%

---


# Conectar sistemas con la aplicación de integración

## Añadir credenciales a la aplicación de integración

La pantalla **[!UICONTROL Settings]** permite especificar las credenciales de Microsoft Dynamics 365 y la API de Adobe. También puede configurar opciones relacionadas con la instancia de Adobe Campaign SFTP.

### Credenciales de Microsoft Dynamics 365

Las credenciales de Microsoft Dynamics 365 otorgan a la aplicación de integración permiso para extraer los datos de Microsoft Dynamics 365.  Primero debe seguir los pasos que se muestran en la pantalla [Configurar Microsoft Dynamics 365 para la integración de Campañas](../../integrating/using/d365-acs-configure-d365.md) a fin de generar los valores que se pegarán en esta pantalla. Las entradas que se describen a continuación harán referencia a esta pantalla.

![](assets/d365-to-acs-ui-page-workflows-settings-d365.png)

* **[!UICONTROL Client ID]**:: Obtenga información sobre cómo hacer referencia a su ID de cliente en  [esta sección](../../integrating/using/d365-acs-configure-d365.md#register-a-new-app)

* **[!UICONTROL Client Secret]**:: Obtenga información sobre cómo generar el secreto del cliente en  [esta sección](../../integrating/using/d365-acs-configure-d365.md#generate-a-client-secret)

* **[!UICONTROL Tenant]**:: Descubra cómo encontrar su ID de inquilino en  [esta sección](../../integrating/using/d365-acs-configure-d365.md#get-the-tenant-id)

* **[!UICONTROL URL]**:: La dirección URL tendrá el formato `https://&lt;servername>.api.crm.ddynamic.com/

### Credenciales de API de Adobe

Las credenciales de Adobe Campaign se generan mediante [Adobe I/O](https://www.adobe.io/). Tendrá que visitar la pantalla [Configurar Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md) y seguir las instrucciones allí antes de poder completar las entradas de esta sección.

La siguiente imagen explicará en detalle la asignación entre Adobe I/O y las entradas de pantalla de configuración.

![](assets/d365-to-acs-ui-page-workflows-settings-adobeio.png)

* *Clave* privada: el proceso para definir estos inicios haciendo clic en el botón &quot;Generar par de claves público/privado&quot;. Esto creará un archivo zip que debe descargar. Una vez descargado, descomprima el archivo, lo que resultará en dos archivos denominados certificate_pub.crt y private.key. Asegúrese de colocar el archivo private.key en un lugar seguro y no lo comparta. Abra el archivo private.key en un editor de texto. Copie todo el valor en el editor de texto (ctrl-A y luego ctrl-C en un PC, o cmd-A y luego cmd-C en un Mac). Esto debería incluir las líneas &quot;INICIAR CLAVE PRIVADA&quot; y &quot;FINALIZAR CLAVE PRIVADA&quot; en su totalidad. Pegue todo este texto multilínea en la entrada &quot;Clave privada&quot; de la pantalla Configuración.

* *Dirección URL*: Este valor se ajustará al patrón https\://mc.adobe.io/&lt;campaign-instance-name>. El encabezado de la aplicación de integración incluye tanto la &quot;organización&quot; como la &quot;instancia&quot;. La parte &quot;campaña-instance-name&quot; de la dirección URL sería simplemente el nombre que se encuentra en este valor de instancia.

## Configuración de Adobe Campaign SFTP {#ac-smtp-settings}

Esta configuración es opcional. Debe definirlos si tiene pensado utilizar la instancia de Adobe Campaign SFTP para generar registros desde el conector. Esto le resultará útil si experimenta problemas al ejecutar la integración y necesita depurar por qué la salida no cumple con sus expectativas.

El otro motivo para configurar el servidor SFTP sería si planea ejecutar el flujo de trabajo de inclusión/exclusión y hay un flujo de datos de Adobe Campaign a Microsoft Dynamics 365, ya sea **[!UICONTROL Unidirectional (Campaign to Microsoft Dynamics 365)]** o **[!UICONTROL Bidirectional]**.

>[!IMPORTANT]
>
>Usted es responsable de la información a la que accede y descarga desde las carpetas SFTP. Si la información contiene datos personales, usted es responsable de cumplir con las leyes y regulaciones de privacidad aplicables. [Más información](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).


Para definir la configuración de SFTP de Campaña para la integración de Microsoft Dynamics 365, acceda a la siguiente sección:

![](assets/d365-to-acs-ui-page-workflows-settings-sftp.png)

Debe especificar:

* **Host** SFTP: este campo contendrá  &lt;campaign-instance-name>.campaña.adobe.com. El encabezado de la aplicación de integración incluye tanto la **organización** como la **instancia**. La parte &quot;campaña-instance-name&quot; de la dirección URL sería simplemente el nombre que se encuentra en este valor de instancia.

* **Usuario** SFTP: Si tiene el usuario de SFTP, agréguelo aquí. De lo contrario, consulte [esta sección](#ac-control-panel-settings). Como parte del proceso, se le mostrará el nombre de usuario.

* **Clave** SFTP: Si tiene una clave SSH, agréguela aquí. De lo contrario, consulte [esta sección](#ac-control-panel-settings).

* Los **intervalos de IP** serán necesarios para incluirse en la configuración de SFTP de Adobe Campaign. Estos deberán estar incluidos en la lista de permitidos para que la integración pueda utilizar el extremo SFTP.

* **¿Desea exportar los registros a su SFTP de Adobe Campaign?** le permite determinar si la integración generará información de registro en el extremo SFTP. Esto se puede usar para ayudar con la depuración si Adobe Campaign o Microsoft Dynamics 365 no muestran la información que espera.

## Configuración de SFTP en Adobe Campaign {#ac-control-panel-settings}

Descubra la administración de SFTP con [Panel de control de Campaign de Campaña](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es) en estas secciones:

* [Acerca de la administración SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/about-sftp-management.html?lang=en#sftp-management)

* [Administración de almacenamiento SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#installing-ssh-key)

* [Añadir intervalos IP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/ip-range-allow-listing.html?lang=en#sftp-management)

* [Administrar claves](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/key-management.html?lang=en#sftp-management)

* [Inicie sesión en el servidor SFTP](https://experienceleague.adobe.com/docs/control-panel/using/sftp-management/logging-into-sftp-server.html?lang=en#sftp-management)

Una vez finalizada la configuración, inicie sesión en el servidor SFTP con la clave privada y cree el directorio &quot;d365_loads/export&quot;.

[Visite esta ](https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/sftp-management/monitoring-server-capacity.html?lang=en#sftp-management) página para obtener información sobre el servidor SFTP de Adobe Campaign Standard.
