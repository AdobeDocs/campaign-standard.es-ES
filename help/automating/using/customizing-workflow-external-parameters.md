---
title: Invocación de un flujo de trabajo con parámetros externos
description: Esta sección detalla cómo llamar a un flujo de trabajo con parámetros externos.
page-status-flag: never-activated
uuid: beccd1b6-8e6d-4504-9152-9ff537459c4a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 1676da91-55e3-414f-bcd3-bb0804b682bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 51e98bb6212ad96d9c11b848df9dcad25b3f1b61
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 5%

---


# Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

Una vez activado el flujo de trabajo, los parámetros se ingieren en las variables de eventos y se pueden utilizar para personalizar las actividades del flujo de trabajo.

Pueden, por ejemplo, utilizarse para definir qué audiencia leer en la **[!UICONTROL Read audience]** actividad, el nombre del archivo que se va a transferir en la **[!UICONTROL Transfer file]** actividad, etc. (see [](../../automating/using/customizing-workflow-external-parameters.md)).

## Uso de variables de eventos {#using-events-variables}

Las variables eventos se utilizan dentro de una expresión que debe respetar la sintaxis [](../../automating/using/advanced-expression-editing.md#standard-syntax)estándar.

La sintaxis para utilizar variables eventos debe seguir el formato siguiente y utilizar el nombre del parámetro que se ha definido en la **[!UICONTROL External signal]** actividad (consulte [Declaración de los parámetros en la actividad](../../automating/using/declaring-parameters-external-signal.md)de señal externa):

```
$(vars/@parameterName)
```

En esta sintaxis, la función **$** devuelve el tipo de datos de **cadena** . Si desea especificar otro tipo de datos, utilice las siguientes funciones:

* **$long**: número entero.
* **$float**: número decimal.
* **$boolean**: true/false.
* **$datetime**: timestamp.

Cuando se utiliza una variable en una actividad, la interfaz proporciona ayuda para llamarla.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png):: seleccione la variable de eventos entre todas las variables disponibles en el flujo de trabajo.

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): edite expresiones que combinan variables y funciones. Para obtener más información sobre el editor de expresiones, consulte [esta sección](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**Temas relacionados:**

* [Edición de una expresión](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [Sintaxis estándar](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [Lista de funciones](../../automating/using/list-of-functions.md)

## Personalización de actividades con variables de eventos {#customizing-activities-with-events-variables}

Las variables de eventos se pueden utilizar para personalizar varias actividades, enumeradas en la sección siguiente. Para obtener más información sobre cómo llamar a una variable desde una actividad, consulte [esta sección](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** actividad: definir la audiencia a destinatario en función de las variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** actividad: crear condiciones basadas en variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** actividad: personalice el archivo que se va a transferir en función de las variables de evento.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** actividad: se puede hacer referencia a los parámetros en una consulta, mediante expresiones que combinan variables y funciones de eventos. Para ello, agregue una regla y haga clic en el **[!UICONTROL Advanced mode]** vínculo para acceder a la ventana de edición de expresiones (consulte Edición [de expresiones](../../automating/using/advanced-expression-editing.md)avanzada).

For more on how to use the activity, refer to the [dedicated section](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** actividades: personalizar envíos en función de las variables de evento.

>[!NOTE]
>
>Los valores de los parámetros de envío se recuperan cada vez que se prepara el envío.
>
>La preparación de envíos recurrentes se basa en el período **de** agregación de envíos. Por ejemplo, si el período de agregación es &quot;por día&quot;, el envío se volverá a preparar sólo una vez al día. Si el valor de un parámetro de envío se modifica durante el día, no se actualizará en el envío, ya que ya se ha preparado una vez.
>
>Si planea llamar al flujo de trabajo varias veces al día, utilice la [!UICONTROL No aggregation] opción para que los parámetros de envío se actualicen cada vez. Para obtener más información sobre la configuración de envíos recurrentes, consulte [esta sección](/help/automating/using/email-delivery.md#configuration).

Para personalizar un envío basado en variables de eventos, primero debe declarar en la actividad de envío las variables que desee utilizar:

1. Seleccione la actividad y, a continuación, haga clic en el ![](assets/dlv_activity_params-24px.png) botón para acceder a la configuración.
1. Seleccione la **[!UICONTROL General]** ficha y, a continuación, agregue las variables de eventos que estarán disponibles como campos de personalización en el envío.

   ![](assets/extsignal_activities_delivery.png)

1. Haga clic en el botón **[!UICONTROL Confirm]**.

Las variables de eventos declarados ahora están disponibles desde la lista de campos de personalización. Puede utilizarlos en el envío para realizar las siguientes acciones:

* Defina el nombre de la plantilla que se va a utilizar para el envío.

   >[!NOTE]
   >
   >Esta acción solo está disponible para envíos **recurrentes** .

   ![](assets/extsignal_activities_template.png)

* Personalice el envío: al seleccionar un campo de personalización para configurar un envío, las variables de eventos están disponibles en el **[!UICONTROL Workflow parameters]** elemento . Puede utilizarlos como cualquier campo de personalización, por ejemplo para definir el asunto del envío, el remitente, etc.

   Delivery personalization is detailed in [this section](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Códigos de segmento**: defina el código de segmento en función de las variables de evento.

>[!NOTE]
>
>Esta acción se puede realizar desde cualquier actividad que le permita definir un código de segmento como, por ejemplo, **[!UICONTROL Query]** o **[!UICONTROL Segmentation]** actividades.

![](assets/extsignal_activities_segment.png)

**Etiqueta** de envío: defina la etiqueta de envío en función de las variables de evento.

![](assets/extsignal_activities_label.png)
