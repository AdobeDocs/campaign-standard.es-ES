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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# Leer audiencia{#read-audience}

## Descripción {#description}

![](assets/prefill.png)

La **[!UICONTROL Read audience]** actividad le permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Read audience]** actividad es una versión más sencilla de la **[!UICONTROL Query]** actividad diseñada para casos en los que solo necesita seleccionar una audiencia existente.

**Temas relacionados**

* [Caso de uso: Unión en dos audiencias refinadas](../../automating/using/union-on-two-refined-audiences.md)
* [Caso de uso: Reconciliación de una audiencia de archivo con la base de datos](../../automating/using/reconcile-file-audience-with-database.md)

## Configuración {#configuration}

1. Coloque una **[!UICONTROL Read audience]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione la audiencia que desee recuperar desde la **[!UICONTROL Properties]** ficha.

   Puede recuperar audiencias de los siguientes tipos: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** y **[!UICONTROL Experience Cloud]**. Para obtener más información sobre los tipos de audiencia, consulte la documentación de [Audiencias](../../audiences/using/about-audiences.md) .

   La **[!UICONTROL Use a dynamic audience]** opción permite definir el nombre de la audiencia al destinatario en función de las variables de eventos del flujo de trabajo. Para obtener más información sobre esto, consulte la sección [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

   ![](assets/readaudience_activity1.png)

1. Si desea aplicar filtros adicionales a la audiencia seleccionada, agregue condiciones a través de la **[!UICONTROL Source filtering]** ficha de la actividad.

   Para obtener más información sobre la creación de condiciones de filtrado, consulte la documentación sobre la [creación de consultas](../../automating/using/editing-queries.md#creating-queries) .

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.
