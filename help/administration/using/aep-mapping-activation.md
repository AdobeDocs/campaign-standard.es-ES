---
title: Activación de la asignación
description: Obtenga información sobre cómo activar la asignación de datos
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 57b87896281efa7dd1e6a612926f59061a0fdcb8

---


# Activación de la asignación {#mapping-activation}

>[!IMPORTANT]
>
>El conector de datos de la plataforma de Adobe Experience está actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

Una vez completada la definición de la asignación, puede publicarla. Después del paso de implementación, la replicación de datos entre Campaign Standard y Adobe Experience Platform se inicia automáticamente. En cualquier momento, puede detener la replicación haciendo clic en el **[!UICONTROL Stop]** botón.

Según las modificaciones de asignación, puede optar por reenviar todos los registros a Adobe Experience Platform.

![](assets/aep_publishmapping.png)

Desde el mosaico de implementación, puede acceder al registro de publicación y a los registros de exportación.

![](assets/aep_publog.png)

En la **[!UICONTROL Export jobs]** ficha, puede supervisar el trabajo de exportación de la asignación publicada.

![](assets/aep_jobstatus.png)

Si desea controlar todos los trabajos de exportación de datos, vaya al menú **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** > **[!UICONTROL Status of data export to platform]** .

![](assets/aep_statusmapping.png)

Estados de trabajo de inserción de datos:

* **[!UICONTROL Created]**:: Se crea un trabajo de inserción de datos y la ingestión de datos está en curso.
* **[!UICONTROL Failed]**:: Error en un trabajo de inserción de datos. El campo de motivo describe el motivo del error. El fallo puede ser transitorio o permanente. En caso de errores transitorios, se crea un nuevo trabajo de inserción después de un intervalo configurado. Como primer paso para solucionar problemas, el usuario puede comprobar el campo de motivo del error. Si el motivo redirige a un usuario a la interfaz de usuario de Adobe Experience Platform, el usuario puede iniciar sesión en Adobe Experience Platform y comprobar el estado del lote en el conjunto de datos para determinar el motivo exacto del error.
* **[!UICONTROL Uploaded]**:: Primero se crea un lote en la plataforma de Adobe Experience y, a continuación, los datos se transfieren al lote. El campo ID de lote muestra la identificación de lote del lote en Adobe Experience Platform. Adobe Experience Platform también realiza una validación posterior del lote. El lote se marca primero como cargado hasta que Adobe Experience Platform completa el paso de validación posterior. Un trabajo sigue sondeando Adobe Experience Platform para ver el estado del lote tras la carga. Un lote puede ir en Error o en Estado de éxito después de la validación en Adobe Experience Platform.
* **[!UICONTROL Success]**:: Después de cargar un lote en Adobe Experience Platform, el estado del trabajo (validación posterior en la plataforma) se comprueba tras un intervalo configurado. El estado &quot;Éxito&quot; identificó una correcta ingestión de datos en Adobe Experience Platform.
