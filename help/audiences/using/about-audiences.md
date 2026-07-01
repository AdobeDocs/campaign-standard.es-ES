---
title: Acerca de los públicos
description: Aprenda a crear públicos a partir de una consulta, una lista o un archivo, y a importarlas desde Adobe Experience Cloud.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: f99987d8-b1bf-4ec7-885c-fb511f4168ac
TQID: https://experienceleague.adobe.com/NPcDi1kh8Ye1Y14CAwVxBLW-0qwHnpFRUQ2WYj7BJbI
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
source-git-commit: 1e34b244937569402d8fe873f6dd67f20b9a9a29
workflow-type: tm+mt
source-wordcount: 249
ht-degree: 85%

---

# Acerca de los públicos{#about-audiences}

Un público es una lista de perfiles basada en reglas y atributos.

Adobe Campaign le permite crear públicos manualmente con consultas o automáticamente con flujos de trabajo específicos. También puede usar públicos compartidos desde Adobe Experience Cloud. Todos los públicos se reagrupan en una lista a la que se puede acceder mediante la tarjeta **[!UICONTROL Audiences]** de la página de inicio de Adobe Campaign o desde el vínculo **[!UICONTROL Audiences]**.

![](assets/audience_1.png)

Puede manipular diferentes tipos de públicos en Adobe Campaign. El tipo de público corresponde a la forma en que se creó:

* **[!UICONTROL Query]**: indica que la audiencia se creó con una [consulta](../../automating/using/editing-queries.md#about-query-editor) en los datos de la base de datos de Adobe Campaign a través de la lista de audiencias. Los públicos definidos por una consulta se recomiendan para cada uso posterior.
* **[!UICONTROL List]**: indica que el público es una lista fija de perfiles. Estas listas se crean en un [flujo de trabajo](../../automating/using/get-started-workflows.md) donde la dimensión de datos al guardar el público se conoce. Por ejemplo, después de dirigir actividades (especialmente **[!UICONTROL Query]**) o después de la reconciliación de datos importados de un archivo.
* **[!UICONTROL File]**: indica que el público se creó directamente a partir de un flujo de trabajo de [importación de archivos](../../automating/using/load-file.md) y que la dimensión de datos era desconocida al guardar el público.
* **[!UICONTROL Experience Cloud]**: indica que el público se importó desde Adobe Experience Cloud. Esta opción solo está disponible si se ha configurado la funcionalidad de uso compartido de públicos. Para obtener más información, consulte [Importación de un público desde Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)
