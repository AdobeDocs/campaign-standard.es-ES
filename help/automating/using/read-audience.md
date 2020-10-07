---
title: Leer audiencia
description: La actividad Leer audiencia permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---


# Leer audiencia{#read-audience}

## Descripción {#description}

![](assets/prefill.png)

La actividad **[!UICONTROL Read audience]** le permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Read audience]** es una versión más sencilla de la actividad **[!UICONTROL Query]** diseñada para casos en los que solo necesita seleccionar una audiencia existente.

**Temas relacionados**

* [Caso de uso: Unión en dos audiencias refinadas](../../automating/using/union-on-two-refined-audiences.md)
* [Caso de uso: Reconciliación de una audiencia de archivo con la base de datos](../../automating/using/reconcile-file-audience-with-database.md)

## Configuración {#configuration}

1. Coloque una actividad **[!UICONTROL Read audience]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Seleccione la audiencia que desee recuperar desde la pestaña **[!UICONTROL Properties]**.

   Puede recuperar audiencias de los siguientes tipos: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** y **[!UICONTROL Experience Cloud]**. Para obtener más información sobre los tipos de audiencia, consulte la documentación de [Audiencias](../../audiences/using/about-audiences.md).

   La opción **[!UICONTROL Use a dynamic audience]** permite definir el nombre de la audiencia a quien se dirige en función de las variables de eventos del flujo de trabajo. For more on this, refer to this section: [](../../automating/using/customizing-workflow-external-parameters.md) section.

   ![](assets/readaudience_activity1.png)

1. Si desea aplicar filtros adicionales a la audiencia seleccionada, añada condiciones en la pestaña **[!UICONTROL Source filtering]** de la actividad.

   Para obtener más información sobre la creación de condiciones de filtrado, consulte la documentación sobre la [Creación de consultas](../../automating/using/editing-queries.md#creating-queries).

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.
