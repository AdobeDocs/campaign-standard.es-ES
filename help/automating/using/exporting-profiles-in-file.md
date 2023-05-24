---
title: Exportación de perfiles en un archivo externo
description: Este caso de uso muestra cómo exportar una lista de perfiles en forma de archivo externo para que los datos puedan utilizarse fuera de Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 68%

---

# Exportación de perfiles en un archivo externo {#exporting-profiles-external-file}

El siguiente ejemplo ilustra cómo configurar una actividad **[!UICONTROL Extract file]** después de una actividad **[!UICONTROL Query]**.

El objetivo de este flujo de trabajo es exportar una lista de perfiles en forma de archivo externo para que los datos puedan utilizarse fuera de Adobe Campaign.

1. Arrastre y suelte un [Extraer archivo](../../automating/using/extract-file.md) en el flujo de trabajo y colóquelo después de la actividad de [Consulta](../../automating/using/query.md) actividad.

   En este ejemplo, la consulta se realiza en todos los perfiles de 18 a 30 años.

1. Abra el **[!UICONTROL Extract file]** actividad para editarla.
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
1. Arrastrar y soltar una [Transferir archivo](../../automating/using/transfer-file.md) actividad después de **[!UICONTROL Extract file]** actividad para recuperar el archivo de extracción en una cuenta externa.
1. Abra la actividad y elija la acción **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Seleccione la cuenta externa e introduzca la ruta de la carpeta en el servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo.

   Cuando el flujo de trabajo se haya ejecutado correctamente, el archivo extraído estará disponible en la cuenta externa.
