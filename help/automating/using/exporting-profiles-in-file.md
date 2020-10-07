---
title: Exportación de perfiles en un archivo externo
description: Este caso de uso muestra cómo exportar una lista de perfiles en forma de archivo externo para que los datos se puedan utilizar fuera de Adobe Campaign.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---


# Exportación de perfiles en un archivo externo {#exporting-profiles-external-file}

El siguiente ejemplo ilustra cómo configurar una actividad **[!UICONTROL Extract file]** después de una actividad **[!UICONTROL Query]**.

El objetivo de este flujo de trabajo es exportar una lista de perfiles en forma de archivo externo para que los datos puedan utilizarse fuera de Adobe Campaign.

1. Drag and drop an [Extract file](../../automating/using/extract-file.md) activity into your workflow and place it after the [Query](../../automating/using/query.md) activity.

   En este ejemplo, la consulta se realiza en todos los perfiles de 18 a 30 años.

1. Open the **[!UICONTROL Extract file]** activity to edit it.
1. Asigne un nombre al archivo de salida.
1. Añada columnas de salida.

   En este ejemplo, el correo electrónico, la edad, la fecha de nacimiento, el nombre y los apellidos de los perfiles se agregan como columnas de salida.

   ![](assets/wkf_data_export6.png)

1. Haga clic en la pestaña **[!UICONTROL File structure]** para definir lo siguiente:

   * Formato de salida CSV

      ![](assets/wkf_data_export7.png)

   * Formato de fecha

      ![](assets/wkf_data_export9.png)

1. Confirme su actividad.
1. Drag and drop a [Transfer file](../../automating/using/transfer-file.md) activity after the **[!UICONTROL Extract file]** activity to recover the extract file on an external account.
1. Abra la actividad y elija la acción **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Seleccione la cuenta externa e introduzca la ruta de la carpeta en el servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo.

   Cuando el flujo de trabajo se haya ejecutado correctamente, el archivo extraído estará disponible en la cuenta externa.
