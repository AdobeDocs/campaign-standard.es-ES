---
solution: Campaign Standard
product: campaign
title: Actualización de datos en función de una descarga automática de archivos
description: 'El siguiente ejemplo muestra el resultado de una actividad de carga de archivo descargada automáticamente mediante una actividad de transferencia de archivos, seguida de una actividad de actualización de datos. '
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 78%

---


# Actualización de datos en función de una descarga automática de archivos {#updating-data-automatic-file-download}

La actividad de carga de archivo estructura principalmente los datos de una actividad de transferencia de archivos para integrarlos en los datos existentes.

El siguiente ejemplo muestra el resultado de una actividad de carga de archivo descargada automáticamente mediante una actividad de transferencia de archivos, seguida de una actividad de actualización de datos. Este flujo de trabajo pretende enriquecer la base de datos de Adobe Campaign con nuevos perfiles o actualizar los perfiles existentes utilizando los datos recuperados del archivo importado.

![](assets/load_file_workflow_ex1.png)

Para crear el flujo de trabajo, siga estos pasos:

1. Arrastre y suelte una actividad [Transferir archivo](../../automating/using/transfer-file.md) en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Configure la actividad de forma que recupere el archivo que desee. En la pestaña **[!UICONTROL Protocol]**, seleccione **SFTP**.
1. Seleccione la opción **Usar parámetros de conexión definidos en una cuenta externa**.
1. Introduzca el nombre de la cuenta externa.
1. Introduzca la **ruta de archivo en el servidor remoto**.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme su actividad.
1. Arrastre y suelte una actividad [Load file](../../automating/using/load-file.md) en el flujo de trabajo y colóquela después de la actividad **[!UICONTROL Transfer file]** .
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. En la sección **[!UICONTROL File to load]** de la pestaña **[!UICONTROL Execution]**, marque la opción **[!UICONTROL Use the file specified in the inbound transition]**.

   ![](assets/wkf_file_loading8.png)

1. Configure la actividad como se ha especificado anteriormente.
1. Arrastre y suelte una actividad [Update data](../../automating/using/update-data.md) en el flujo de trabajo y colóquela después de la actividad **[!UICONTROL Load file]** y, a continuación, configúrela.

Una vez iniciado el flujo de trabajo, los datos del archivo cargado se extraen y se utilizan para enriquecer la base de datos de Adobe Campaign.
