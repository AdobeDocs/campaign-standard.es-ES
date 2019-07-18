---
title: Acerca de las audiencias
seo-title: Acerca de las audiencias
description: Acerca de las audiencias
seo-description: Obtenga información sobre cómo crear audiencias desde una consulta, una lista o un archivo, y cómo importarlos desde Adobe Experience Cloud.
page-status-flag: no activado nunca
uuid: b 3996642-96 ec -489 e-b 146-c 8 c 2 cb 52 aa 32
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: audiencias
content-type: reference
topic-tags: administración de audiencias
discoiquuid: 750 ecd 8 d -67 a 5-4180-bfy -2 a 8 e 3098 c 812
context-tags: audiencia, asistente; audiencia, información general; entrega, audiencia, atrás
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# About audiences{#about-audiences}

Una audiencia es una lista de perfiles basados en reglas y atributos.

Adobe Campaign permite crear audiencias manualmente mediante consultas o utilizando automáticamente flujos de trabajo dedicados. También puede utilizar audiencias compartidas de Adobe Experience Cloud. All of the audiences are regrouped into a list that can be accessed via the **[!UICONTROL Audiences]** card on the Adobe Campaign home page or from the **[!UICONTROL Audiences]** link.

![](assets/audience_1.png)

Puede manipular distintos tipos de audiencia en Adobe Campaign. El tipo de audiencia corresponde al modo en que se creó:

* **[!UICONTROL Query]**: indica que la audiencia se creó a partir de [una consulta](../../automating/using/editing-queries.md#about-query-editor) sobre datos de la base de datos de Adobe Campaign desde la lista de audiencias. Las audiencias definidas por una consulta se vuelven a calcular en cada uso.
* **[!UICONTROL List]**: indica que la audiencia es una lista fija de perfiles. These lists are created in a [workflow](../../automating/using/discovering-workflows.md), where the data dimension is known when saving the audience. For example, after targeting activities (especially **[!UICONTROL Query]** ) or after the reconciliation of data imported from a file.
* **[!UICONTROL File]**: indica que la audiencia se ha creado directamente desde un [flujo de trabajo de importación](../../automating/using/load-file.md) de archivos y que la dimensión de datos era desconocida al guardar la audiencia.
* **[!UICONTROL Experience Cloud]**: indica que la audiencia se ha importado desde Adobe Experience Cloud. Esta opción solo está disponible si se ha configurado la funcionalidad de uso compartido de audiencias. For more information, see [Importing an audience from the Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)

