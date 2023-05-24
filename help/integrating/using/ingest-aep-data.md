---
title: Ingesta de audiencias de Adobe Experience Platform en Campaign
description: Aprenda a introducir audiencias de Adobe Experience Platform en Campaign Standard.
audience: integrating
content-type: reference
role: Data Architect
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 68%

---

# Ingesta de audiencias de Adobe Experience Platform en Campaign {#destinations}

Para introducir público de Adobe Experience Platform en Campaign y utilizarlo en sus flujos de trabajo, primero debe conectar Adobe Campaign como **destino** de Adobe Experience Platform y configurarlo con el segmento a exportar.

Una vez configurado el destino, los datos se exportan a su ubicación de almacenamiento y deberá crear un flujo de trabajo específico en Campaign Standard para introducirlo.

## Conexión de Adobe Campaign como destino

En Adobe Experience Platform, para configurar una conexión con Adobe Campaign, seleccione una ubicación de almacenamiento para los segmentos exportados. Estos pasos también le permiten seleccionar los segmentos que desea exportar y especificar los campos XDM adicionales que incluir.

Para obtener más información, consulte la [documentación de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=es).

Una vez configurado el destino, Adobe Experience Platform crea un archivo .txt o .csv delimitado por tabuladores en la ubicación de almacenamiento proporcionada. Esta operación se programa y realiza una vez cada 24 horas.

Ahora puede configurar un flujo de trabajo de Campaign Standard para introducir el segmento en Campaign.

## Creación de un flujo de trabajo de importación en Campaign Standard

Una vez configurado el Campaign Standard como destino, debe crear un flujo de trabajo dedicado para importar el archivo que ha exportado Adobe Experience Platform.

Para ello, debe añadir y configurar una actividad **[!UICONTROL Transfer file]**. Para obtener más información sobre cómo configurar esta actividad, consulte [esta sección](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

A continuación, puede crear un flujo de trabajo según sus necesidades (actualizar la base de datos con los datos del segmento, realizar envíos en canales múltiples al segmento, etc.).

Por ejemplo, el flujo de trabajo siguiente descarga diariamente el archivo desde su ubicación de almacenamiento y, a continuación, actualiza la base de datos de Campaign con los datos del segmento.

![](assets/rtcdp-workflow.png)

Hay ejemplos de flujos de trabajo de gestión de datos disponibles en la [casos de uso de flujos de trabajo](../../automating/using/about-workflow-use-cases.md#management) sección.

Temas relacionados:

* [Actividades de administración de datos](../../automating/using/about-data-management-activities.md)
* [Acerca de la importación y exportación de datos](../../automating/using/about-data-import-and-export.md)
