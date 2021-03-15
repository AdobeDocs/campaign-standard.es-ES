---
solution: Campaign Standard
product: campaign
title: Prueba
description: La actividad Prueba permite una transición basada en un resultado de prueba.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: jstest,main
feature: Flujos de trabajo
role: Arquitecto de datos
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '194'
ht-degree: 80%

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

   * ![](assets/extsignal_picker.png): seleccione la variable events entre todas las variables disponibles en el flujo de trabajo (consulte  [esta página](../../automating/using/customizing-workflow-external-parameters.md)).

      Por ejemplo, puede comprobar el número de archivos descargados después de una actividad [File transfer](../../automating/using/transfer-file.md) mediante la variable **[!UICONTROL filesCount]**.

      ![](assets/wkf_test_activity_variables.png)

   * ![](assets/extsignal_expression_editor.png): edite expresiones que combinan variables y funciones. Para obtener más información sobre el editor de expresiones, consulte [esta sección](../../automating/using/advanced-expression-editing.md).

      ![](assets/wkf_test_activity_variables_expression.png)
