---
title: Exportación de perfiles en un archivo externo
description: Este caso de uso muestra cómo exportar una lista de perfiles en forma de archivo externo para que los datos puedan utilizarse fuera de Adobe Campaign.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileExport,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 3fc286a9-bba4-4e3d-95cd-600eed4943e7
TQID: 'https://experienceleague.adobe.com/wVo-oDNJNFmaNcb7p6fACNIfrPG-2Y-VbXxXG0P8XTQ'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 68%
---
# Exportación de perfiles en un archivo externo {#exporting-profiles-external-file}

El siguiente ejemplo ilustra cómo configurar una actividad **[!UICONTROL Extract file]** después de una actividad **[!UICONTROL Query]**.

El objetivo de este flujo de trabajo es exportar una lista de perfiles en forma de archivo externo para que los datos puedan utilizarse fuera de Adobe Campaign.

1. Arrastre y suelte una actividad [Extraer archivo](../../automating/using/extract-file.md) en el flujo de trabajo y colóquela después de la actividad [Consulta](../../automating/using/query.md).

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
1. Arrastre y suelte una actividad [Transferir archivo](../../automating/using/transfer-file.md) después de la actividad **[!UICONTROL Extract file]** para recuperar el archivo de extracción en una cuenta externa.
1. Abra la actividad y elija la acción **[!UICONTROL File upload]**.

   ![](assets/wkf_data_export11.png)

1. Seleccione la cuenta externa e introduzca la ruta de la carpeta en el servidor.

   ![](assets/wkf_data_export12.png)

1. Confirme la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo.

   Cuando el flujo de trabajo se haya ejecutado correctamente, el archivo extraído estará disponible en la cuenta externa.
