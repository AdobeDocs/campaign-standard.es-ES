---
title: Activación de la asignación
description: Obtenga información sobre cómo activar la asignación de datos
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: d7ca0de6-7f7b-4e31-877c-909d962c5f53
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '476'
ht-degree: 0%

---

# Activación de la asignación {#mapping-activation}

>[!IMPORTANT]
>
>Adobe Experience Platform Data Connectors se encuentra actualmente en fase beta, por lo que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Es necesario que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea acceder, póngase en contacto con el Servicio de atención al cliente de Adobe.

Cuando finalice la definición de la asignación, puede publicarla. Después del paso de implementación, la duplicación de datos entre Campaign Standard y Adobe Experience Platform se inicia automáticamente. En cualquier momento, puede detener la replicación haciendo clic en el botón **[!UICONTROL Stop]** botón.

Según las modificaciones de asignación, puede elegir reenviar todos los registros a Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Desde el mosaico de implementación, puede acceder al registro de publicación y a los registros de exportación.

![](assets/aep_publog.png)

En el **[!UICONTROL Export jobs]** , puede controlar el trabajo de exportación para la asignación publicada.

![](assets/aep_jobstatus.png)

Si desea controlar todos los trabajos de exportación de datos, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** para abrir el Navegador.

![](assets/aep_statusmapping.png)

Los estados de trabajo de ingesta de datos son:

* **[!UICONTROL Created]**: Se crea un trabajo de inserción de datos y el consumo de datos está en curso.
* **[!UICONTROL Failed]**: Error en un trabajo de ingesta de datos. El campo reason describe el motivo del error. El error puede ser transitorio o permanente. En caso de errores transitorios, se crea un nuevo trabajo de ingesta después de un intervalo configurado. Como primer paso para la resolución de problemas, el usuario puede comprobar el campo de motivo del error. Si el motivo redirige a un usuario a la interfaz de usuario de Adobe Experience Platform, el usuario puede iniciar sesión en Adobe Experience Platform y comprobar el estado del lote en el conjunto de datos para determinar el motivo exacto del error.
* **[!UICONTROL Uploaded]**: Primero se crea un lote en Adobe Experience Platform y luego se introducen datos en el lote. El campo ID de lote muestra el identificador del lote en Adobe Experience Platform. Adobe Experience Platform también realiza una validación posterior del lote. El lote se marca primero como cargado hasta que Adobe Experience Platform complete el paso de validación posterior. Un trabajo sigue sondeando en Adobe Experience Platform el estado del lote tras la carga. Un lote puede ir en Estado fallido o en Estado de éxito después de la validación en Adobe Experience Platform.
* **[!UICONTROL Success]**: Una vez cargado un lote en Adobe Experience Platform, el estado del trabajo (después de la validación en la plataforma) se comprueba después de un intervalo configurado. El estado &quot;Éxito&quot; identificaba una ingesta correcta de datos en Adobe Experience Platform.

En algunos casos, es posible que obtenga el siguiente error de validación al publicar la asignación.

![](assets/aep_datamapping_ccpa.png)

Esto ocurre cuando el esquema XDM que está utilizando no se ha actualizado con el último campo XDM relacionado con la administración de privacidad y aún contiene el campo XDM &quot;cpa&quot; obsoleto.

Para actualizar el esquema XDM, siga estos pasos:

1. Vaya al conjunto de datos en Adobe Experience Platform mediante el vínculo presente en la página de asignación de XDM.

1. Vaya al esquema XDM.

1. Agregue la variable **[!UICONTROL Profile Privacy]** mezcla en el esquema.

   ![](assets/aep_datamapping_privacyfield.png)

1. Guarde el esquema y vuelva a publicar la asignación. La publicación debería pasar ahora.

   ![](assets/aep_save_mapping.png)
