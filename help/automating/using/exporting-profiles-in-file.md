---
title: Exportación de perfiles en un archivo externo
description: Este caso de uso muestra cómo exportar una lista de perfiles en forma de archivo externo para que los datos se puedan utilizar fuera del Adobe Campaign.
page-status-flag: never-activated
uuid: 631f0fbd-9e8d-4f77-a338-fcb7f4fc1774
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: a06509f9-4731-4187-b43d-3bfa361284d3
context-tags: fileExport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 2%

---


# Exportación de perfiles en un archivo externo {#exporting-profiles-external-file}

El siguiente ejemplo ilustra cómo configurar una **[!UICONTROL Extract file]** actividad después de una **[!UICONTROL Query]** actividad.

El objetivo de este flujo de trabajo es exportar una lista de perfiles en forma de archivo externo para que los datos puedan utilizarse fuera del Adobe Campaign.

1. Arrastre y suelte una actividad de archivo [](../../automating/using/extract-file.md) Extract en el flujo de trabajo y colóquela después de la actividad de [Consulta](../../automating/using/query.md) .

   En este ejemplo, la consulta se realiza en todos los perfiles de 18 a 30 años.

1. Abra la **[!UICONTROL Extract file]** actividad para editarla.
1. Asigne un nombre al archivo de salida.
1. Añadir columnas de salida.

   En este ejemplo, el correo electrónico, la edad, la fecha de nacimiento, el nombre y los apellidos de los perfiles se agregan como columnas de salida.

   ![](assets/wkf_data_export6.png)

1. Haga clic en la **[!UICONTROL File structure]** ficha para definir:

   * Formato de salida CSV

      ![](assets/wkf_data_export7.png)

   * Formato de fecha

      ![](assets/wkf_data_export9.png)

1. Confirme su actividad.
1. Arrastre y suelte una actividad de archivo [](../../automating/using/transfer-file.md) Transfer después de la **[!UICONTROL Extract file]** actividad para recuperar el archivo de extracción en una cuenta externa.
1. Abra la actividad y elija la **[!UICONTROL File upload]** acción.

   ![](assets/wkf_data_export11.png)

1. Seleccione la cuenta externa e introduzca la ruta de la carpeta en el servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo.

   Cuando el flujo de trabajo se haya ejecutado correctamente, el archivo extraído estará disponible en la cuenta externa.
