---
solution: Campaign Standard
product: campaign
title: Activación de la asignación
description: Obtenga información sobre cómo activar la asignación de datos
audience: administration
content-type: reference
topic-tags: configuring-channels
translation-type: tm+mt
source-git-commit: 3a4e8628b916291244d142d9cc4a6a84b799502b
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---


# Activación de la asignación {#mapping-activation}

>[!IMPORTANT]
>
>El conector de datos de Adobe Experience Platform se encuentra actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea obtener acceso, póngase en contacto con el Servicio de atención al cliente de Adobe.

Una vez completada la definición de la asignación, puede publicarla. Después del paso de implementación, la replicación de datos entre Campaign Standard y Adobe Experience Platform se inicia automáticamente. En cualquier momento, puede detener la replicación haciendo clic en el **[!UICONTROL Stop]** botón.

Según las modificaciones de asignación, puede elegir reenviar todos los registros a Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Desde el mosaico de implementación, puede acceder al registro de publicación y a los registros de exportación.

![](assets/aep_publog.png)

En la **[!UICONTROL Export jobs]** ficha, puede supervisar el trabajo de exportación de la asignación publicada.

![](assets/aep_jobstatus.png)

Si desea controlar todos los trabajos de exportación de datos, vaya al menú **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

![](assets/aep_statusmapping.png)

Los estados de trabajo de inserción de datos son:

* **[!UICONTROL Created]**:: Se crea un trabajo de inserción de datos y la ingestión de datos está en curso.
* **[!UICONTROL Failed]**:: Error en un trabajo de inserción de datos. El campo de motivo describe el motivo del error. El fallo puede ser transitorio o permanente. En caso de errores transitorios, se crea un nuevo trabajo de inserción después de un intervalo configurado. Como primer paso para solucionar problemas, el usuario puede comprobar el campo de motivo del error. Si el motivo redirige a un usuario a la interfaz de usuario de Adobe Experience Platform, el usuario puede iniciar sesión en Adobe Experience Platform y comprobar el estado del lote en el conjunto de datos para determinar el motivo exacto del error.
* **[!UICONTROL Uploaded]**:: Primero se crea un lote en Adobe Experience Platform y luego se ingieren datos en el lote. El campo Id. de lote muestra el id. de lote del lote en Adobe Experience Platform. Adobe Experience Platform también realiza una validación posterior del lote. El lote se marca primero como cargado hasta que Adobe Experience Platform completa el paso de validación de la publicación. Un trabajo sigue sondeando en Adobe Experience Platform el estado del lote tras la carga. Un lote puede ir en Error o en Estado de éxito después de la validación en Adobe Experience Platform.
* **[!UICONTROL Success]**:: Después de cargar un lote en Adobe Experience Platform, el estado del trabajo (validación posterior en la plataforma) se comprueba tras un intervalo configurado. El estado &quot;Éxito&quot; identificó una correcta ingestión de datos en Adobe Experience Platform.

En algunos casos, puede que reciba el error de validación siguiente al publicar la asignación.

![](assets/aep_datamapping_ccpa.png)

Esto ocurre cuando el esquema XDM que está utilizando no se ha actualizado con el último campo XDM relacionado con la administración de privacidad y aún contiene el campo XDM &quot;ccpa&quot; desaprobado.

Para actualizar el esquema XDM, siga estos pasos:

1. Vaya al conjunto de datos de Adobe Experience Platform mediante el vínculo presente en la página de asignación XDM.

1. Vaya al esquema XDM.

1. Añada la mezcla &quot;Proporle privacidad&quot; al esquema.

   ![](assets/aep_datamapping_privacyfield.png)

1. Guarde el esquema y vuelva a intentar publicar la asignación. La publicación debería pasar ahora.

   ![](assets/aep_save_mapping.png)
