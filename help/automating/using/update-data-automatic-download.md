---
title: Actualización de datos en función de una descarga automática de archivos
description: 'El siguiente ejemplo muestra el resultado de una actividad de carga de archivo descargada automáticamente mediante una actividad de transferencia de archivos, seguida de una actividad de actualización de datos. '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 79%

---


# Actualización de datos en función de una descarga automática de archivos {#updating-data-automatic-file-download}

La actividad de carga de archivo estructura principalmente los datos de una actividad de transferencia de archivos para integrarlos en los datos existentes.

El siguiente ejemplo muestra el resultado de una actividad de carga de archivo descargada automáticamente mediante una actividad de transferencia de archivos, seguida de una actividad de actualización de datos. Este flujo de trabajo pretende enriquecer la base de datos de Adobe Campaign con nuevos perfiles o actualizar los perfiles existentes utilizando los datos recuperados del archivo importado.

![](assets/load_file_workflow_ex1.png)

Para generar el flujo de trabajo, siga estos pasos:

1. Arrastre y suelte una actividad [Transferir archivo](../../automating/using/transfer-file.md) en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Configure la actividad de forma que recupere el archivo que desee. En la pestaña **[!UICONTROL Protocol]**, seleccione **SFTP**.
1. Seleccione la opción **Usar parámetros de conexión definidos en una cuenta externa**.
1. Introduzca el nombre de la cuenta externa.
1. Introduzca la **ruta de archivo en el servidor remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme su actividad.
1. Drag and drop a [Load file](../../automating/using/load-file.md) activity into your workflow and place it after the **[!UICONTROL Transfer file]** activity.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. En la sección **[!UICONTROL File to load]** de la pestaña **[!UICONTROL Execution]**, marque la opción **[!UICONTROL Use the file specified in the inbound transition]**.

   ![](assets/wkf_file_loading8.png)

1. Configure la actividad como se ha especificado anteriormente.
1. Drag and drop an [Update data](../../automating/using/update-data.md) activity into your workflow and place it after the **[!UICONTROL Load file]** activity, then configure it.

Una vez iniciado el flujo de trabajo, los datos del archivo cargado se extraen y se utilizan para enriquecer la base de datos de Adobe Campaign.
