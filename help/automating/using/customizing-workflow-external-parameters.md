---
title: Personalización de un flujo de trabajo con parámetros externos
description: Esta sección detalla cómo invocar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 8c1a47ed-3467-4fcd-8747-86f0e8f15cec
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 1%

---

# Personalización de un flujo de trabajo con parámetros externos {#customizing-a-workflow-with-external-parameters}

Una vez activado el flujo de trabajo, los parámetros se incorporan a las variables de eventos y se pueden utilizar para personalizar las actividades del flujo de trabajo.

Por ejemplo, se pueden utilizar para definir qué audiencia leer en la **[!UICONTROL Read audience]** actividad, el nombre del archivo que se va a transferir en la **[!UICONTROL Transfer file]** actividad, etc. (consulte [esta página](../../automating/using/customizing-workflow-external-parameters.md)).

## Uso de variables de eventos {#using-events-variables}

Las variables de eventos se utilizan dentro de una expresión que debe respetar el [Sintaxis estándar](../../automating/using/advanced-expression-editing.md#standard-syntax).

La sintaxis para utilizar variables de eventos debe seguir el formato siguiente y utilizar el nombre del parámetro que se ha definido en **[!UICONTROL External signal]** actividad (consulte [Declaración de los parámetros en la actividad Señal externa](../../automating/using/declaring-parameters-external-signal.md)):

```
$(vars/@parameterName)
```

En esta sintaxis, la variable **$** función devuelve **cadena** tipo de datos. Si desea especificar otro tipo de datos, utilice las funciones siguientes:

* **$long**: número entero.
* **$float**: número decimal.
* **$booleano**: true/false.
* **$datetime**: marca de tiempo.

Cuando se utiliza una variable en una actividad, la interfaz proporciona ayuda para llamarla.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png): seleccione la variable de eventos de entre todas las variables disponibles en el flujo de trabajo.

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): edite expresiones que combinan variables y funciones (consulte [esta página](../../automating/using/advanced-expression-editing.md)).

   ![](assets/wkf_test_activity_variables_expression.png)

   Esta lista proporciona funciones que le permiten realizar filtros complejos. Estas funciones se detallan en [esta sección](../../automating/using/list-of-functions.md).

   Además, puede utilizar las funciones siguientes, que están disponibles en todas las actividades que permiten utilizar variables de eventos después de llamar a un flujo de trabajo con parámetros externos (consulte [esta sección](../../automating/using/customizing-workflow-external-parameters.md#customizing-activities-with-events-variables)):

   | Nombre | Descripción | Sintaxis |
   | ---------|----------|---------|
   | EndWith | Indica si una cadena (primer parámetro) termina con una cadena específica (segundo parámetro). | EndWith()&lt;string>,&lt;string>) |
   | startWith | Indica si una cadena (primer parámetro) comienza con una cadena específica (segundo parámetro). | startWith()&lt;string>,&lt;string>) |
   | Extract | Devuelve los primeros caracteres de una cadena utilizando un separador. | Extract()&lt;string>,&lt;separator>) |
   | ExtractRight | Devuelve los últimos caracteres de una cadena utilizando un separador. | ExtractRight()&lt;string>,&lt;separator>) |
   | DateFormat | Da formato a una fecha utilizando el formato especificado en el segundo parámetro (ejemplo: &#39;%4Y%2M%2D&#39;) | DateFormat()&lt;date>,&lt;format>) |
   | FileName | Devuelve el nombre de una ruta de archivo. | FileName()&lt;string>) |
   | FileExt | Devuelve la extensión de una ruta de archivo. | FileExt()&lt;string>) |
   | GetOption | Devuelve el valor de la función especificada. | GetOption()&lt;optionname>) |
   | IsNull | Indica si una cadena o una fecha es nula. | IsNull(&lt;string date=&quot;&quot;>) |
   | UrlUtf8Encode | Codifica una dirección URL en UTF8. | UrlUtf8Encode()&lt;string>) |

## Personalización de actividades con variables de eventos {#customizing-activities-with-events-variables}

Las variables de eventos se pueden utilizar para personalizar varias actividades, que se enumeran en la sección siguiente. Para obtener más información sobre cómo llamar a una variable desde una actividad, consulte [esta sección](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** actividad: definir la audiencia a quien se dirige en función de las variables de eventos. Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** actividad: generar condiciones basadas en variables de eventos. Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** actividad: personalice el archivo para transferirlo en función de variables de eventos. Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** actividad: se puede hacer referencia a los parámetros en una consulta mediante expresiones que combinan variables de eventos y funciones. Para ello, añada una regla y haga clic en **[!UICONTROL Advanced mode]** para acceder a la ventana de edición de expresiones (consulte [Edición avanzada de expresiones](../../automating/using/advanced-expression-editing.md)).

Para obtener más información sobre cómo utilizar la actividad, consulte [esta sección](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** actividades: personalice las entregas en función de variables de eventos.

>[!NOTE]
>
>Los valores de los parámetros de envío se recuperan cada vez que se prepara el envío.
>
>La preparación de los envíos recurrentes se basa en el envío **período de acumulación**. Por ejemplo, si el periodo de acumulación es &quot;por día&quot;, la entrega se vuelve a preparar solo una vez al día. Si el valor de un parámetro de envío se modifica durante el día, no se actualiza en el envío, ya que ya se ha preparado una vez.
>
>Si planea llamar al flujo de trabajo varias veces al día, utilice el [!UICONTROL No aggregation] , de modo que los parámetros de envío se actualicen cada vez. Para obtener más información sobre la configuración de envíos recurrentes, consulte [esta sección](/help/automating/using/email-delivery.md#configuration).

Para personalizar una entrega en función de variables de eventos, primero debe declarar en la actividad de entrega las variables que desea utilizar:

1. Seleccione la actividad y haga clic en ![](assets/dlv_activity_params-24px.png) para acceder a la configuración.
1. Seleccione el **[!UICONTROL General]** y, a continuación, añada las variables de eventos que estarán disponibles como campos personalizados en la entrega.

   ![](assets/extsignal_activities_delivery.png)

1. Haga clic en el botón **[!UICONTROL Confirm]**.

Las variables de eventos declarados ya están disponibles en la lista de campos personalizados. Puede utilizarlos en la entrega para realizar las siguientes acciones:

* Defina el nombre de la plantilla que desea utilizar para la entrega.

   >[!NOTE]
   >
   >Esta acción está disponible para **recurrente** solo envíos.

   ![](assets/extsignal_activities_template.png)

* Personalice la entrega: al seleccionar un campo de personalización para configurar una entrega, las variables de eventos están disponibles en la variable **[!UICONTROL Workflow parameters]** Elemento. Puede utilizarlos como cualquier campo personalizado, por ejemplo para definir el asunto de la entrega, el remitente, etc.

   La personalización de la entrega se detalla en [esta sección](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Códigos de segmento**: defina el código de segmento en función de las variables de eventos.

>[!NOTE]
>
>Esta acción se puede realizar desde cualquier actividad que le permita definir un código de segmento como, por ejemplo, **[!UICONTROL Query]** o **[!UICONTROL Segmentation]** actividades.

![](assets/extsignal_activities_segment.png)

**Etiqueta de envío**: defina la etiqueta de entrega en función de las variables de eventos.

![](assets/extsignal_activities_label.png)
