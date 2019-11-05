---
title: Acerca de las audiencias
description: Descubra cómo crear audiencias a partir de una consulta, una lista o un archivo, y cómo importarlas desde Adobe Experience Cloud.
page-status-flag: nunca activado
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: administrar-audiencias
discoiquuid: 750ecd8d-67a5-4180-bect-2a8e3098c812
context-tags: audiencia,asistente;audiencia,información general;entrega,audiencia,vuelta
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de las audiencias{#about-audiences}

Una audiencia es una lista de perfiles basados en reglas y atributos.

Adobe Campaign permite crear las audiencias manualmente mediante consultas o automáticamente mediante flujos de trabajo dedicados. También puede usar audiencias compartidas desde Adobe Experience Cloud. Todas las audiencias se reagrupan en una lista a la que se puede acceder mediante la tarjeta en la página de inicio de Adobe Campaign o desde el **[!UICONTROL Audiences]** **[!UICONTROL Audiences]** vínculo.

![](assets/audience_1.png)

Puede manipular diferentes tipos de audiencia en Adobe Campaign. El tipo de audiencia corresponde a la forma en que se creó:

* **[!UICONTROL Query]**:: indica que la audiencia se creó a partir de una [consulta](../../automating/using/editing-queries.md#about-query-editor) de datos de la base de datos de Adobe Campaign de la lista de audiencias. Las audiencias definidas por una consulta se vuelven a calcular en cada uso posterior.
* **[!UICONTROL List]**:: indica que la audiencia es una lista fija de perfiles. Estas listas se crean en un [flujo de trabajo](../../automating/using/discovering-workflows.md)en el que se conoce la dimensión de datos al guardar la audiencia. Por ejemplo, después de actividades de segmentación (especialmente **[!UICONTROL Query]** ) o después de la reconciliación de datos importados de un archivo.
* **[!UICONTROL File]**:: indica que la audiencia se ha creado directamente a partir de un flujo de trabajo de importación [de](../../automating/using/load-file.md) archivos y que la dimensión de datos era desconocida al guardar la audiencia.
* **[!UICONTROL Experience Cloud]**:: indica que la audiencia se importó desde Adobe Experience Cloud. Esta opción solo está disponible si se ha configurado la funcionalidad de uso compartido de público. Para obtener más información, consulte [Importación de una audiencia desde Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

