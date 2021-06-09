---
solution: Campaign Standard
product: campaign
title: Ingesta de audiencias de Adobe Experience Platform en Campaign
description: Aprenda a incorporar audiencias de Adobe Experience Platform en Campaign Standard.
audience: integrating
content-type: reference
feature: Sources and Destinations
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 894d691f1df3a613bacc74e149e5fdf7f4531d92
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 3%

---


# Ingesta de audiencias de Adobe Experience Platform en Campaign {#destinations}

Para ingerir audiencias de Adobe Experience Platform en Campaign y utilizarlas en sus flujos de trabajo, primero debe conectar Adobe Campaign as a Adobe Experience Platform **Destination** y configurarlo con el segmento a exportar.

Una vez configurado el destino, los datos se exportan a su ubicación de almacenamiento y deberá crear un flujo de trabajo dedicado en Campaign Standard para ingerirlos.

## Conectar Adobe Campaign como destino

En Adobe Experience Platform, para configurar una conexión con Adobe Campaign, seleccione una ubicación de almacenamiento para los segmentos exportados. Estos pasos también le permiten seleccionar los segmentos que desea exportar y especificar campos XDM adicionales que incluir.

Para obtener más información, consulte la [Documentación de destinos](https://experienceleague.adobe.com/docs/experience-platform/destinations/catalog/email-marketing/adobe-campaign.html).

Una vez configurado el destino, Adobe Experience Platform crea un archivo .txt o .csv delimitado por tabuladores en la ubicación de almacenamiento proporcionada. Esta operación se programa y realiza una vez cada 24 horas.

Ahora puede configurar un flujo de trabajo de Campaign Standard para introducir el segmento en Campaign.

## Creación de un flujo de trabajo de importación en Campaign Standard

Una vez configurado el Campaign Standard como destino, debe crear un flujo de trabajo dedicado para importar el archivo que ha exportado Adobe Experience Platform.

Para ello, debe añadir y configurar una actividad **[!UICONTROL Transfer file]** . Para obtener más información sobre cómo configurar esta actividad, consulte [esta sección](../../automating/using/transfer-file.md).

![](assets/rtcdp-transfer-file.png)

A continuación, puede crear el flujo de trabajo según sus necesidades (actualice la base de datos con los datos del segmento, envíe envíos multicanal al segmento, etc.)

Por ejemplo, el flujo de trabajo siguiente descarga diariamente el archivo desde su ubicación de almacenamiento y, a continuación, actualiza la base de datos de Campaign con los datos del segmento.

![](assets/rtcdp-workflow.png)

En la sección [workflows use cases](../../automating/using/about-workflow-use-cases.md#management) encontrará ejemplos de flujos de trabajo de administración de datos.

Temas relacionados:

* [Actividades de gestión de datos](../../automating/using/about-data-management-activities.md)
* [Acerca de la importación y exportación de datos](../../automating/using/about-data-import-and-export.md)