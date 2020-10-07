---
title: Prueba
description: La actividad Prueba permite una transición basada en un resultado de prueba.
page-status-flag: never-activated
uuid: 1562ec7a-253a-4f4f-b66a-c2948b57775a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 2650bf1f-0bce-4049-a226-2369f6666b95
context-tags: jstest,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 91%

---


# Prueba{#test}

## Descripción {#description}

![](assets/test.png)

La actividad **[!UICONTROL Test]** permite una transición basada en un resultado de prueba.

## Contexto de uso {#context-of-use}

Una actividad **Prueba** activa la primera transición que cumple la condición asociada a esta.

Si no se cumple ninguna condición y si la opción **Use default transition** está activada, se activa la transición predeterminada.

![](assets/wkf_test_activity_example.png)

Las condiciones se pueden basar en **funciones** o en **variables** como, por ejemplo, variables de eventos que se han declarado en la actividad **[!UICONTROL External signal]** del flujo de trabajo.

**Temas relacionados:**

* [Lista de funciones](../../automating/using/list-of-functions.md)
* [Invocación de un flujo de trabajo con parámetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuración {#configuration}

1. Arrastre y suelte una actividad **[!UICONTROL Test]** en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el botón ![](assets/edit_darkgrey-24px.png), en las acciones rápidas que aparecerán.
1. Defina los atributos de cada condición:

   Al editar el campo **[!UICONTROL Condition]**, dos botones proporcionan ayuda para llamar a variables de eventos y editar expresiones que combinan variables y funciones:

   * ![](assets/extsignal_picker.png):: seleccione la variable de eventos entre todas las variables disponibles en el flujo de trabajo (consulte [](../../automating/using/customizing-workflow-external-parameters.md))

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): edite expresiones que combinan variables y funciones. Para obtener más información sobre el editor de expresiones, consulte [esta sección](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)
