---
title: Actualización de datos en función de una descarga automática de archivos
description: 'El siguiente ejemplo muestra el resultado de una actividad de archivos de carga descargada automáticamente mediante una actividad de archivos de transferencia, seguida de una actividad de datos de actualización. '
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---


# Actualización de datos en función de una descarga automática de archivos {#updating-data-automatic-file-download}

La actividad del archivo de carga estructura principalmente los datos de una actividad de archivo de transferencia para integrarlos en los datos existentes.

El siguiente ejemplo muestra el resultado de una actividad de archivos de carga descargada automáticamente mediante una actividad de archivos de transferencia, seguida de una actividad de datos de actualización. Este flujo de trabajo pretende enriquecer la base de datos de Adobe Campaign con nuevos perfiles o actualizar los perfiles existentes utilizando los datos recuperados del archivo importado.

![](assets/load_file_workflow_ex1.png)

Para generar el flujo de trabajo, siga estos pasos:

1. Arrastre y suelte una actividad de archivo [](../../automating/using/transfer-file.md) Transfer en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Configure la actividad de forma que recupere el archivo que desee. In the **[!UICONTROL Protocol]** tab, select **SFTP**.
1. Seleccione la opción **Usar parámetros de conexión definidos en una cuenta externa** .
1. Introduzca el nombre de la cuenta externa.
1. Introduzca la ruta **de archivo en el servidor** remoto.

   ![](assets/wkf_file_transfer_07.png)

1. Confirme su actividad.
1. Arrastre y suelte una actividad [Cargar archivo](../../automating/using/load-file.md) en el flujo de trabajo y colóquela después de la **[!UICONTROL Transfer file]** actividad.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. En la **[!UICONTROL File to load]** sección de la **[!UICONTROL Execution]** ficha, marque la **[!UICONTROL Use the file specified in the inbound transition]** opción.

   ![](assets/wkf_file_loading8.png)

1. Configure la actividad como se especificó anteriormente.
1. Arrastre y suelte una actividad de datos [de](../../automating/using/update-data.md) actualización en el flujo de trabajo y colóquela después de la **[!UICONTROL Load file]** actividad y, a continuación, configúrela.

Una vez iniciado el flujo de trabajo, los datos del archivo cargado se extraen y se utilizan para enriquecer la base de datos de Adobe Campaign.
