---
title: Ingesta de públicos de Adobe Experience Platform en Campaign
description: Obtenga información sobre cómo introducir audiencias de Adobe Experience Platform en Campaign Standard.
audience: integrating
content-type: reference
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5c266c44-535b-4954-862d-74c83a6f6406
TQID: 'https://experienceleague.adobe.com/LdVWEXa90p4yOKgPGG5LUOGRk3xWE8kJ8SkKM7ODBXk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: b70f632b-2cfd-43d0-9266-284281100d70
    internal-label: Data import and export
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
    internal-label: Data management
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 69%
---
# Ingesta de públicos de Adobe Experience Platform en Campaign {#destinations}

Para introducir público de Adobe Experience Platform en Campaign y utilizarlo en sus flujos de trabajo, primero debe conectar Adobe Campaign como **destino** de Adobe Experience Platform y configurarlo con el segmento a exportar.

Una vez configurado el destino, los datos se exportan a su ubicación de almacenamiento y deberá crear un flujo de trabajo dedicado en Campaign Standard para introducirlo.

## Conexión de Adobe Campaign como destino

En Adobe Experience Platform, para configurar una conexión con Adobe Campaign, seleccione una ubicación de almacenamiento para los segmentos exportados. Estos pasos también le permiten seleccionar los segmentos que desea exportar y especificar los campos XDM adicionales que incluir.

Para obtener más información, consulte la [documentación de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html?lang=es#catalog).

Una vez configurado el destino, Adobe Experience Platform crea un archivo .txt o .csv delimitado por tabuladores en la ubicación de almacenamiento proporcionada. Esta operación se programa y realiza una vez cada 24 horas.

Ahora puede configurar un flujo de trabajo de Campaign Standard para introducir el segmento en Campaign.

## Creación de un flujo de trabajo de importación en Campaign Standard

Una vez configurado Campaign Standard como destino, debe crear un flujo de trabajo dedicado para importar el archivo que ha exportado Adobe Experience Platform.

Para ello, debe añadir y configurar una actividad **[!UICONTROL Transfer file]**. Para obtener más información sobre cómo configurar esta actividad, consulte [esta sección](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

A continuación, puede crear un flujo de trabajo según sus necesidades (actualizar la base de datos con los datos del segmento, realizar envíos en canales múltiples al segmento, etc.).

Por ejemplo, el flujo de trabajo siguiente descarga diariamente el archivo desde su ubicación de almacenamiento y, a continuación, actualiza la base de datos de Campaign con los datos del segmento.

![](assets/rtcdp-workflow.png)

Hay ejemplos de flujos de trabajo de administración de datos disponibles en la sección [casos de uso de flujos de trabajo](../../automating/using/about-workflow-use-cases.md#management).

Temas relacionados:

* [Actividades de administración de datos](../../automating/using/about-data-management-activities.md)
* [Acerca de la importación y exportación de datos](../../automating/using/about-data-import-and-export.md)
