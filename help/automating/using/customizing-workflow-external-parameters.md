---
solution: Campaign Standard
product: campaign
title: Invocación de un flujo de trabajo con parámetros externos
description: Esta sección detalla cómo llamar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '803'
ht-degree: 1%

---


# Personalización de un flujo de trabajo con parámetros externos {#customizing-a-workflow-with-external-parameters}

Una vez activado el flujo de trabajo, los parámetros se ingieren en las variables de eventos y se pueden utilizar para personalizar las actividades del flujo de trabajo.

Pueden, por ejemplo, utilizarse para definir qué audiencia leer en la actividad **[!UICONTROL Read audience]**, el nombre del archivo que se va a transferir en la actividad **[!UICONTROL Transfer file]**, etc. (consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md)).

## Uso de variables de evento {#using-events-variables}

Las variables eventos se utilizan dentro de una expresión que debe respetar la sintaxis [Estándar](../../automating/using/advanced-expression-editing.md#standard-syntax).

La sintaxis para utilizar variables eventos debe seguir el formato siguiente y utilizar el nombre del parámetro que se ha definido en la actividad **[!UICONTROL External signal]** (consulte [Declaración de los parámetros en la actividad de señal externa](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

En esta sintaxis, la función **$** devuelve el tipo de datos **string**. Si desea especificar otro tipo de datos, utilice las siguientes funciones:

* **$long**: número entero.
* **$float**: número decimal.
* **$boolean**: true/false.
* **$datetime**: timestamp.

Cuando se utiliza una variable en una actividad, la interfaz proporciona ayuda para llamarla.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):: seleccione la variable de eventos entre todas las variables disponibles en el flujo de trabajo.

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):: edite expresiones combinando variables y funciones (consulte  [esta página](../../automating/using/advanced-expression-editing.md)).

   ![](assets/wkf_test_activity_variables_expression.png)

   Esta lista proporciona funciones que le permiten realizar filtros complejos. Estas funciones se detallan en [esta sección](../../automating/using/list-of-functions.md).

   Además, puede utilizar las funciones siguientes, que están disponibles en todas las actividades que le permiten utilizar variables de eventos después de llamar a un flujo de trabajo con parámetros externos (consulte [esta sección](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)):

   | Name | Descripción | Syntax |
   ---------|----------|---------
   | EndWith | Indica si una cadena (primer parámetro) termina con una cadena específica (segundo parámetro). | EndWith(&lt;String>,&lt;String>) |
   | startWith | Indica si una cadena (primer parámetro) inicio con una cadena específica (segundo parámetro). | startWith(&lt;String>,&lt;String>) |
   | Extraer | Devuelve los primeros caracteres de una cadena que utiliza un separador. | Extract(&lt;String>,&lt;Separator>) |
   | ExtractRight | Devuelve los últimos caracteres de una cadena que utiliza un separador. | ExtractRight(&lt;String>,&lt;Separator>) |
   | DateFormat | Da formato a una fecha con el formato especificado en el segundo parámetro (ejemplo:  &#39;%4Y%2M%2D&#39;) | DateFormat(&lt;Fecha>,&lt;Formato>) |
   | NombreDeArchivo | Devuelve el nombre de una ruta de archivo. | FileName(&lt;String>) |
   | FileExt | Devuelve la extensión de una ruta de archivo. | FileExt(&lt;String>) |
   | IsNull | Indica si una cadena o una fecha es nula. | IsNull(&lt;String/date>) |
   | UrlUtf8Encode | Codifica una URL en UTF8. | UrlUtf8Encode(&lt;String>) |

## Personalización de actividades con variables de eventos {#customizing-activities-with-events-variables}

Las variables de eventos se pueden utilizar para personalizar varias actividades, enumeradas en la sección siguiente. Para obtener más información sobre cómo llamar a una variable desde una actividad, consulte [esta sección](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** actividad: definir la audiencia a destinatario en función de las variables de eventos. Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** actividad: crear condiciones basadas en variables de eventos. Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** actividad: personalice el archivo que se va a transferir en función de las variables de evento. Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** actividad: se puede hacer referencia a los parámetros en una consulta, mediante expresiones que combinan variables y funciones de eventos. Para ello, agregue una regla y haga clic en el vínculo **[!UICONTROL Advanced mode]** para acceder a la ventana de edición de expresiones (consulte [Edición avanzada de expresiones](../../automating/using/advanced-expression-editing.md)).

Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** actividades: personalizar envíos en función de las variables de evento.

>[!NOTE]
>
>Los valores de los parámetros de envío se recuperan cada vez que se prepara el envío.
>
>La preparación de envíos recurrentes se basa en el envío **período de agregación**. Por ejemplo, si el período de agregación es &quot;por día&quot;, el envío se volverá a preparar sólo una vez al día. Si el valor de un parámetro de envío se modifica durante el día, no se actualizará en el envío, ya que ya se ha preparado una vez.
>
>Si planea llamar al flujo de trabajo varias veces al día, utilice la opción [!UICONTROL No aggregation] para que los parámetros de envío se actualicen cada vez. Para obtener más información sobre la configuración de envíos recurrentes, consulte [esta sección](/help/automating/using/email-delivery.md#configuration).

Para personalizar un envío basado en variables de eventos, primero debe declarar en la actividad de envío las variables que desee utilizar:

1. Seleccione la actividad y haga clic en el botón ![](assets/dlv_activity_params-24px.png) para acceder a la configuración.
1. Seleccione la ficha **[!UICONTROL General]** y, a continuación, agregue las variables de eventos que estarán disponibles como campos de personalización en el envío.

   ![](assets/extsignal_activities_delivery.png)

1. Haga clic en el botón **[!UICONTROL Confirm]**.

Las variables de eventos declarados ahora están disponibles desde la lista de campos de personalización. Puede utilizarlos en el envío para realizar las siguientes acciones:

* Defina el nombre de la plantilla que se va a utilizar para el envío.

   >[!NOTE]
   >
   >Esta acción solo está disponible para envíos **recurrentes**.

   ![](assets/extsignal_activities_template.png)

* Personalice el envío: al seleccionar un campo de personalización para configurar un envío, las variables de eventos están disponibles en el elemento **[!UICONTROL Workflow parameters]**. Puede utilizarlos como cualquier campo de personalización, por ejemplo para definir el asunto del envío, el remitente, etc.

   La personalización de envío se detalla en [esta sección](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Códigos de segmento**: defina el código de segmento en función de las variables de evento.

>[!NOTE]
>
>Esta acción se puede realizar desde cualquier actividad que le permita definir un código de segmento como, por ejemplo, actividades **[!UICONTROL Query]** o **[!UICONTROL Segmentation]**.

![](assets/extsignal_activities_segment.png)

**Etiqueta** de envío: defina la etiqueta de envío en función de las variables de evento.

![](assets/extsignal_activities_label.png)
