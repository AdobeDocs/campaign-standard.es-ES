---
title: Leer audiencia
description: La actividad Leer audiencia permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 9a77a2c7-cc1c-416f-8103-bb7d5c84a373
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 87%

---

# Lectura de audiencia{#read-audience}

## Descripción {#description}

![](assets/prefill.png)

La actividad **[!UICONTROL Read audience]** le permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.

## Contexto de uso {#context-of-use}

La actividad **[!UICONTROL Read audience]** es una versión más sencilla de la actividad **[!UICONTROL Query]** diseñada para casos en los que solo necesita seleccionar una audiencia existente.

**Temas relacionados**

* [Caso de uso: Unión de dos audiencias refinadas](../../automating/using/union-on-two-refined-audiences.md)
* [Caso de uso: Reconciliación de una audiencia de archivo con la base de datos](../../automating/using/reconcile-file-audience-with-database.md)

## Configuración {#configuration}

1. Coloque una actividad **[!UICONTROL Read audience]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Seleccione la audiencia que desee recuperar desde la pestaña **[!UICONTROL Properties]**.

   Puede recuperar audiencias de los siguientes tipos: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** y **[!UICONTROL Experience Cloud]**. Para obtener más información sobre los tipos de audiencia, consulte la documentación de [Audiencias](../../audiences/using/about-audiences.md).

   La opción **[!UICONTROL Use a dynamic audience]** permite definir el nombre de la audiencia a quien se dirige en función de las variables de eventos del flujo de trabajo. Para obtener más información, consulte la sección [esta página](../../automating/using/customizing-workflow-external-parameters.md) .

   ![](assets/readaudience_activity1.png)

1. Si desea aplicar filtros adicionales a la audiencia seleccionada, añada condiciones en la pestaña **[!UICONTROL Source filtering]** de la actividad.

   Para obtener más información sobre la creación de condiciones de filtrado, consulte la documentación sobre la [Creación de consultas](../../automating/using/editing-queries.md#creating-queries).

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.
