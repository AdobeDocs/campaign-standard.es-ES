---
title: Acerca de las audiencias
description: Aprenda a crear audiencias a partir de una consulta, una lista o un archivo, y a importarlas desde Adobe Experience Cloud.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Audiences
role: User
level: Beginner
exl-id: f99987d8-b1bf-4ec7-885c-fb511f4168ac
source-git-commit: 8412c728edabf72680ddfdb1fd7547442890150f
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 91%

---

# Acerca de las audiencias{#about-audiences}

Una audiencia es una lista de perfiles basada en reglas y atributos.

Adobe Campaign le permite crear audiencias manualmente con consultas o automáticamente con flujos de trabajo específicos. También puede usar audiencias compartidas desde Adobe Experience Cloud. Todas las audiencias se reagrupan en una lista a la que se puede acceder mediante la tarjeta **[!UICONTROL Audiences]** de la página de inicio de Adobe Campaign o desde el vínculo **[!UICONTROL Audiences]**.

![](assets/audience_1.png)

Puede manipular diferentes tipos de audiencias en Adobe Campaign. El tipo de audiencia corresponde a la forma en que se creó:

* **[!UICONTROL Query]**: indica que la audiencia se creó con una [consulta](../../automating/using/editing-queries.md#about-query-editor) en los datos de la base de datos de Adobe Campaign a través de la lista de audiencias. Las audiencias definidas por una consulta se recomiendan para cada uso posterior.
* **[!UICONTROL List]**: indica que la audiencia es una lista fija de perfiles. Estas listas se crean en un [flujo de trabajo](../../automating/using/get-started-workflows.md) donde la dimensión de datos al guardar la audiencia se conoce. Por ejemplo, después de dirigir actividades (especialmente **[!UICONTROL Query]**) o después de la reconciliación de datos importados de un archivo.
* **[!UICONTROL File]**: indica que la audiencia se creó directamente a partir de un flujo de trabajo de [importación de archivos](../../automating/using/load-file.md) y que la dimensión de datos era desconocida al guardar la audiencia.
* **[!UICONTROL Experience Cloud]**: indica que la audiencia se importó desde Adobe Experience Cloud. Esta opción solo está disponible si se ha configurado la funcionalidad de uso compartido de audiencias. Para obtener más información, consulte [Importación de una audiencia desde Adobe Experience Cloud](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md#importing-an-audience).

![](assets/audience_type_selection.png)
