---
solution: Campaign Standard
product: campaign
title: Exportación de perfiles en un archivo externo
description: Este caso de uso muestra cómo exportar una lista de perfiles en forma de archivo externo para que los datos se puedan utilizar fuera de Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Flujos de trabajo
role: Arquitecto de datos
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 67%

---


# Exportación de perfiles en un archivo externo {#exporting-profiles-external-file}

El siguiente ejemplo ilustra cómo configurar una actividad **[!UICONTROL Extract file]** después de una actividad **[!UICONTROL Query]**.

El objetivo de este flujo de trabajo es exportar una lista de perfiles en forma de archivo externo para que los datos puedan utilizarse fuera de Adobe Campaign.

1. Arrastre y suelte una actividad [Extract file](../../automating/using/extract-file.md) en el flujo de trabajo y colóquela después de la actividad [Query](../../automating/using/query.md).

   En este ejemplo, la consulta se realiza en todos los perfiles de 18 a 30 años.

1. Abra la actividad **[!UICONTROL Extract file]** para editarla.
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
1. Arrastre y suelte una actividad [Transfer file](../../automating/using/transfer-file.md) después de la actividad **[!UICONTROL Extract file]** para recuperar el archivo de extracción en una cuenta externa.
1. Abra la actividad y elija la acción **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Seleccione la cuenta externa e introduzca la ruta de la carpeta en el servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo.

   Cuando el flujo de trabajo se haya ejecutado correctamente, el archivo extraído estará disponible en la cuenta externa.
