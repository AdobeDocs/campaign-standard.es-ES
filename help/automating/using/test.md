---
title: Prueba
description: La actividad de prueba activa una transición basada en un resultado de prueba.
page-status-flag: nunca activado
uuid: 1562ec7a-253a-4f4f-b66a-c2948b57775a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: execute-activity
discoiquuid: 2650bf1f-0bce-4049-a226-2369f666b95
context-tags: jstest,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Prueba{#test}

## Descripción {#description}

![](assets/test.png)

The **[!UICONTROL Test]** activity enables a transition based on a test result.

## Contexto de uso {#context-of-use}

A **Test** activity activates the first transition that satisfies the condition associated to it.

If no condition is satisfied and if the **Use default transition** option is activated, a default transition will be activated.

![](assets/wkf_test_activity_example.png)

Las condiciones se pueden basar en **funciones** o en **variables**, por ejemplo variables de eventos que se han declarado en la **[!UICONTROL External signal]** actividad del flujo de trabajo.

**Temas relacionados:**

* [Lista de funciones](../../automating/using/list-of-functions.md)
* [Invocación de un flujo de trabajo con parámetros externos](../../automating/using/calling-a-workflow-with-external-parameters.md)

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Test]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Defina los atributos de cada condición:

   Al editar el **[!UICONTROL Condition]** campo, dos botones proporcionan ayuda para llamar a variables de eventos y editar expresiones que combinan variables y funciones:

   * ![](assets/extsignal_picker.png):: seleccione la variable events entre todas las variables disponibles en el flujo de trabajo (consulte [Personalización de un flujo de trabajo con parámetros](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)externos)

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png):: editar expresiones combinando variables y funciones. For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)

