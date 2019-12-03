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
source-git-commit: aee0e0437cbfe578cb2f715a2433099c79dd1748

---


# Invocación de un flujo de trabajo con parámetros externos{#calling-a-workflow-with-external-parameters}

Campaign Standard le permite llamar a un flujo de trabajo con parámetros (un nombre de audiencia para el objetivo, un nombre de archivo para importar, una parte del contenido del mensaje, etc.). De este modo, puede integrar fácilmente las automatizaciones de su campaña con su sistema externo.

Veamos el siguiente ejemplo, donde queremos enviar correos electrónicos directamente desde un CMS. En ese caso, puede configurar el sistema para que seleccione la audiencia y el contenido del correo electrónico en el CMS. Al hacer clic en Enviar, se llamará a un flujo de trabajo de campaña con estos parámetros, lo que le permitirá utilizarlos en el flujo de trabajo para definir la audiencia y el contenido URL que se utilizarán en la entrega.

El proceso para llamar a un flujo de trabajo con parámetros es el siguiente:

1. Declare los parámetros de la **[!UICONTROL External signal]** actividad. Consulte [Declaración de los parámetros en la actividad](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)de señal externa.
1. Configure la actividad **[!UICONTROL End]** o la llamada de API para definir los parámetros y activar la **[!UICONTROL External signal]** actividad de flujo de trabajo.

Una vez activado el flujo de trabajo, los parámetros se ingieren en las variables de eventos del flujo de trabajo y se pueden utilizar dentro del mismo. Consulte [Personalización de un flujo de trabajo con parámetros](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters)externos.

![](assets/extsignal_process.png)

## Declaración de los parámetros en la actividad de señal externa {#declaring-the-parameters-in-the-external-signal-activity}

El primer paso para llamar a un flujo de trabajo con parámetros es declararlos en una **[!UICONTROL External signal]** actividad.

1. Abra la **[!UICONTROL External signal]** actividad y seleccione la **[!UICONTROL Parameters]** ficha.
1. Haga clic en el **[!UICONTROL Create element]** botón y luego especifique el nombre y el tipo de cada parámetro.

   >[!CAUTION]
   >
   >Asegúrese de que el nombre y el número de parámetros son idénticos a los definidos al llamar al flujo de trabajo (consulte [Definición de parámetros al llamar al flujo de trabajo](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Además, los tipos de parámetros deben ser coherentes con los valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una vez declarados los parámetros, finalice la configuración del flujo de trabajo y, a continuación, ejecútela.

## Definición de los parámetros al llamar al flujo de trabajo {#defining-the-parameters-when-calling-the-workflow}

En esta sección se explica cómo definir parámetros al llamar a un flujo de trabajo. Para obtener más información sobre cómo realizar esta operación desde una llamada de API, consulte la documentación [de las API de](../../api/using/triggering-a-signal-activity.md)REST.

Antes de definir los parámetros, asegúrese de que:

* Los parámetros se han declarado en la **[!UICONTROL External Signal]** actividad. Consulte [Declaración de los parámetros en la actividad](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)de señal externa.
* Se está ejecutando el flujo de trabajo que contiene la actividad de señal.

Para configurar la **[!UICONTROL End]** actividad, siga los pasos a continuación:

1. Abra la **[!UICONTROL End]** actividad y seleccione la **[!UICONTROL External signal]** ficha.
1. Seleccione el flujo de trabajo y la actividad de señal externa que desea llamar.
1. Haga clic en el **[!UICONTROL Create element]** botón para agregar un parámetro y luego complete su nombre y valor.

   * **[!UICONTROL Name]**:: el nombre que se ha declarado en la **[!UICONTROL External signal]** actividad (consulte [Declaración de los parámetros en la actividad](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)de señal externa).
   * **[!UICONTROL Value]**:: el valor que desea asignar al parámetro. El valor debe seguir la sintaxis **** estándar descrita en [esta sección](../../automating/using/advanced-expression-editing.md#standard-syntax).
   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Asegúrese de que todos los parámetros se han declarado en la **[!UICONTROL External signal]** actividad. De lo contrario, se producirá un error al ejecutar la actividad.

1. Una vez definidos los parámetros, confirme la actividad y guarde el flujo de trabajo.

## Monitoreo de las variables de eventos {#monitoring-the-events-variables}

Es posible supervisar las variables de eventos disponibles en el flujo de trabajo, incluidos los parámetros externos declarados. Para realizar esto, siga los pasos a continuación:

1. Seleccione la actividad que sigue a la **[!UICONTROL External signal]** actividad y haga clic en el **[!UICONTROL Log and tasks]** botón.
1. En la **[!UICONTROL Tasks]** ficha, haga clic en ![](assets/edit_darkgrey-24px.png) .

   ![](assets/extsignal_monitoring_2.png)

1. Se muestra el contexto de ejecución de la tarea (ID, estado, duración, etc.), incluidas todas las variables de eventos que ahora están disponibles para su uso en el flujo de trabajo.

   ![](assets/extsignal_monitoring_3.png)

## Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

Una vez activado el flujo de trabajo, los parámetros se ingieren en las variables de eventos y se pueden utilizar para personalizar las actividades del flujo de trabajo.

Pueden, por ejemplo, utilizarse para definir qué audiencia leer en la **[!UICONTROL Read audience]** actividad, el nombre del archivo que se va a transferir en la **[!UICONTROL Transfer file]** actividad, etc.

Las actividades que se pueden personalizar con variables de eventos se detallan en [esta sección](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

### Uso de variables de eventos {#using-events-variables}

Las variables events se utilizan dentro de una expresión que debe respetar la sintaxis **[](../../automating/using/advanced-expression-editing.md#standard-syntax)** estándar.

La sintaxis para utilizar variables de eventos debe seguir el formato siguiente y utilizar el nombre del parámetro que se ha definido en la **[!UICONTROL External signal]** actividad (consulte [Declaración de parámetros en la actividad](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)de señal externa):

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

* ![](assets/extsignal_picker.png):: seleccione la variable events entre todas las variables disponibles en el flujo de trabajo (consulte ).

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png):: editar expresiones combinando variables y funciones. For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**Temas relacionados:**

* [Editar una expresión](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [Sintaxis estándar](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [Lista de funciones](../../automating/using/list-of-functions.md)

### Personalización de actividades con variables de eventos {#customizing-activities-with-events-variables}

Las variables de eventos se pueden utilizar para personalizar varias actividades, enumeradas en la sección siguiente. Para obtener más información sobre cómo llamar a una variable desde una actividad, consulte [esta sección](../../automating/using/calling-a-workflow-with-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** actividad: defina la audiencia a la que se dirigirá en función de las variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** actividad: generar condiciones basadas en variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** actividad: personalice el archivo que se va a transferir en función de las variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** actividad: se puede hacer referencia a los parámetros en una consulta, mediante expresiones que combinan variables y funciones de eventos. Para ello, agregue una regla y haga clic en el **[!UICONTROL Advanced mode]** vínculo para acceder a la ventana de edición de expresiones (consulte Edición [de expresiones](../../automating/using/advanced-expression-editing.md)avanzadas).

For more on how to use the activity, refer to the [dedicated section](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** actividades: personalice los envíos en función de las variables de eventos.

>[!NOTE]
>
>Los valores de los parámetros de entrega se recuperan cada vez que se prepara la entrega.
>
>La preparación de entregas recurrentes se basa en el período **de** agregación de envíos. Por ejemplo, si el período de agregación es "por día", la entrega se volverá a preparar sólo una vez al día. Si el valor de un parámetro de entrega se modifica durante el día, no se actualizará en la entrega, ya que ya se ha preparado una vez.
>
>Si planea llamar al flujo de trabajo varias veces al día, utilice la [!UICONTROL No aggregation] opción para que los parámetros de envío se actualicen cada vez. Para obtener más información sobre la configuración de envíos recurrentes, consulte [esta sección](/help/automating/using/email-delivery.md#configuration).

Para personalizar una entrega según las variables de eventos, primero debe declarar en la actividad de entrega las variables que desee utilizar:

1. Seleccione la actividad y, a continuación, haga clic en el ![](assets/dlv_activity_params-24px.png) botón para acceder a la configuración.
1. Seleccione la **[!UICONTROL General]** ficha y, a continuación, agregue las variables de eventos que estarán disponibles como campos de personalización en la entrega.

   ![](assets/extsignal_activities_delivery.png)

1. Haga clic en el botón **.[!UICONTROL Confirm]**

Las variables de eventos declarados ya están disponibles en la lista de campos de personalización. Puede utilizarlos en la entrega para realizar las acciones siguientes:

* Defina el nombre de la plantilla que se va a utilizar para la entrega.

   >[!NOTE]
   >
   >Esta acción solo está disponible para entregas **recurrentes** .

   ![](assets/extsignal_activities_template.png)

* Personalice la entrega: al seleccionar un campo de personalización para configurar una entrega, las variables events están disponibles en el **[!UICONTROL Workflow parameters]** elemento . Puede utilizarlos como cualquier campo de personalización, por ejemplo para definir el asunto de entrega, el remitente, etc.

   La personalización de la entrega se detalla en [esta sección](../../designing/using/personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Códigos** de segmento: defina el código de segmento en función de las variables de eventos.

>[!NOTE]
>
>Esta acción se puede realizar desde cualquier actividad que le permita definir un código de segmento como, por ejemplo, **[!UICONTROL Query]** o **[!UICONTROL Segmentation]** actividades.

![](assets/extsignal_activities_segment.png)

**Etiqueta** de envío: defina la etiqueta de entrega en función de las variables events.

![](assets/extsignal_activities_label.png)

## Ejemplo de uso {#use-case}

El siguiente caso de uso muestra cómo llamar al flujo de trabajo con parámetros dentro de los flujos de trabajo.

El objetivo es activar un flujo de trabajo desde una llamada de API con parámetros externos. Este flujo de trabajo cargará datos en la base de datos desde un archivo y creará una audiencia asociada. Una vez creada la audiencia, se activará un segundo flujo de trabajo para enviar un mensaje personalizado con los parámetros externos definidos en la llamada de API.

Para realizar este caso de uso, debe realizar las acciones siguientes:

1. **Realice una llamada** de API para activar Workflow 1 con parámetros externos. Consulte [el paso 1: Configuración de la llamada](../../automating/using/calling-a-workflow-with-external-parameters.md#step-1--configuring-the-api-call)de API.
1. **Generar flujo de trabajo 1**: el flujo de trabajo transferirá un archivo y lo cargará en la base de datos. Luego comprobará si los datos están vacíos o no y, finalmente, guardará los perfiles en una audiencia. Finalmente, activará Workflow 2. Consulte [el paso 2: Configuración del flujo de trabajo 1](../../automating/using/calling-a-workflow-with-external-parameters.md#step-2--configuring-workflow-1).
1. **Generar flujo de trabajo 2**: el flujo de trabajo leerá la audiencia que se ha creado en Workflow 1 y, a continuación, enviará un mensaje personalizado a los perfiles, con un código de segmento personalizado con los parámetros. Consulte [el paso 3: Configuración del flujo de trabajo 2](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

### Requisitos previos {#prerequisites}

Antes de configurar los flujos de trabajo, debe crear los flujos de trabajo 1 y 2 con una **[!UICONTROL External signal]** actividad en cada uno de ellos. De este modo, podrá dirigir estas actividades de señal al llamar a los flujos de trabajo.

### Paso 1: Configuración de la llamada de API {#step-1--configuring-the-api-call}

Realice una llamada de API para activar Workflow 1 con parámetros. Para obtener más información sobre la sintaxis de llamada de API, consulte la documentación [de las API de REST de](../../api/using/triggering-a-signal-activity.md)Campaign Standard.

En nuestro caso, queremos llamar al flujo de trabajo con los parámetros siguientes:

* **fileToTarget**: el nombre del archivo que desea importar a la base de datos.
* **descuentosDesc**: la descripción que queremos mostrar en la entrega para el descuento.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/<TRIGGER_URL>
-H 'Authorization: Bearer <ACCESS_TOKEN>' 
-H 'Cache-Control: no-cache' 
-H 'X-Api-Key: <API_KEY>' 
-H 'Content-Type: application/json;charset=utf-8' 
-H 'Content-Length:79' 
-i
-d {
-d "source:":"API",
-d "parameters":{
-d "fileToTarget":"profile.txt",
-d "discountDesc":"Running shoes"
-d } 
```

### Paso 2: Configuración del flujo de trabajo 1 {#step-2--configuring-workflow-1}

El flujo de trabajo 1 se generará de la siguiente manera:

* **[!UICONTROL External signal]** actividad: donde los parámetros externos deben declararse para poder utilizarse dentro del flujo de trabajo.
* **[!UICONTROL Transfer file]** actividad: importa el archivo con el nombre definido en los parámetros.
* **[!UICONTROL Load file]** actividad: carga datos del archivo importado en la base de datos.
* **[!UICONTROL Update data]** actividad: insertar o actualizar la base de datos con datos del archivo importado.
* **[!UICONTROL Test]** actividad: comprueba si hay datos importados.
* **[!UICONTROL Save audience]** actividad: si el archivo contiene datos, guarda los perfiles en una audiencia.
* **[!UICONTROL End activity]** actividad: llama al flujo de trabajo 2 con los parámetros que desea usar dentro de él.

![](assets/extsignal_uc_wkf1.png)

Siga los pasos a continuación para configurar el flujo de trabajo:

1. Declare los parámetros que se han definido en la llamada de API. Para ello, abra la **[!UICONTROL External signal]** actividad y, a continuación, agregue los nombres y tipos de los parámetros.

   ![](assets/extsignal_uc1.png)

1. Agregue una **[!UICONTROL Transfer file]** actividad para importar datos en la base de datos.Para ello, arrastre y suelte la actividad, ábrala y seleccione la **[!UICONTROL Protocol]** ficha.
1. Seleccione la **[!UICONTROL Use a dynamic file path]** opción y, a continuación, utilice el parámetro **fileToTarget** como archivo para transferir:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Cargue los datos del archivo en la base de datos.

   Para ello, arrastre y suelte una **[!UICONTROL Load file]** actividad en el flujo de trabajo y configúrela según sus necesidades.

1. Inserte y actualice la base de datos con datos del archivo importado.

   Para ello, arrastre y suelte una **[!UICONTROL Update data]** actividad y, a continuación, seleccione la **[!UICONTROL Identification]** ficha para agregar un criterio de reconciliación (en nuestro caso, el campo de **correo electrónico** ).

   ![](assets/extsignal_uc3.png)

1. Seleccione la **[!UICONTROL Fields to update]** ficha y, a continuación, especifique los campos que desea actualizar en la base de datos (en nuestro caso, los campos **first name** y **email** ).

   ![](assets/extsignal_uc4.png)

1. Compruebe si los datos se recuperan del archivo. Para ello, arrastre y suelte una **[!UICONTROL Test]** actividad en el flujo de trabajo y, a continuación, haga clic en el **[!UICONTROL Add an element]** botón para agregar una condición.
1. Asigne un nombre y defina la condición. En nuestro caso, queremos probar si la transición saliente contiene datos con la sintaxis siguiente:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Si se recuperan datos, guárdelos en una audiencia. Para ello, agregue una **[!UICONTROL Save audience]** actividad a **Target que no esté vacía** y, a continuación, ábrala.
1. Seleccione la **[!UICONTROL Use a dynamic label]** opción y, a continuación, utilice el parámetro **fileToTarget** como etiqueta de la audiencia:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Arrastre y suelte una **[!UICONTROL End]** actividad que llamará a Workflow 2 con parámetros y, a continuación, ábrala.
1. Seleccione la **[!UICONTROL External signal]** ficha y, a continuación, especifique el flujo de trabajo que se activará y su actividad de señal asociada.
1. Defina los parámetros que desee utilizar en Workflow 2 y sus valores asociados.

   En nuestro caso, queremos pasar los parámetros definidos originalmente en la llamada de API (**fileToTarget** y **descuentosDesc**), y un parámetro **segmentCode** adicional con un valor constante ("20% de descuento").

   ![](assets/extsignal_uc7.png)

El flujo de trabajo 1 está configurado, ahora puede crear el flujo de trabajo 2. Para obtener más información, consulte [esta sección](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2).

### Paso 3: Configuración del flujo de trabajo 2 {#step-3--configuring-workflow-2}

El flujo de trabajo 2 se generará de la siguiente manera:

* **[!UICONTROL External signal]** actividad: donde los parámetros deben declararse para poder utilizarse dentro del flujo de trabajo.
* **[!UICONTROL Read audience]** actividad: lee la audiencia guardada en Workflow 1.
* **[!UICONTROL Email delivery]** actividad: envía un mensaje recurrente a la audiencia de destino, personalizado con parámetros.

![](assets/extsignal_uc_wkf2.png)

Siga los pasos a continuación para configurar el flujo de trabajo:

1. Declare los parámetros definidos en Workflow 1.

   Para ello, abra la **[!UICONTROL External signal]** actividad y, a continuación, agregue el nombre y el tipo de cada parámetro definido en la **[!UICONTROL End]** actividad de Workflow 1.

   ![](assets/extsignal_uc8.png)

1. Utilice la audiencia que se ha guardado en el flujo de trabajo 1. Para ello, arrastre y suelte una **[!UICONTROL Read audience]** actividad en el flujo de trabajo y, a continuación, ábrala.
1. Seleccione la **[!UICONTROL Use a dynamic audience]** opción y, a continuación, utilice el parámetro **fileToTarget** como nombre de la audiencia para leer:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Asigne un nombre a la transición de salida según el parámetro **segmentCode** .

   Para ello, seleccione la **[!UICONTROL Transition]** ficha y, a continuación, la **[!UICONTROL Use a dynamic segment code]** opción.

1. Utilice el parámetro **segmentCode** como nombre de la transición de salida:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad para enviar un mensaje a la audiencia.
1. Identifique los parámetros que se utilizarán en el mensaje para personalizarlo con el parámetro **descuentosDesc** . Para ello, abra las opciones avanzadas de la actividad y, a continuación, agregue el nombre y el valor del parámetro.

   ![](assets/extsignal_uc10b.png)

1. Ahora puede configurar el mensaje. Abra la actividad y seleccione **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Seleccione la plantilla que desee utilizar y defina las propiedades de correo electrónico según sus necesidades.
1. Utilice el parámetro **descuentosDesc** como campo de personalización. Para ello, selecciónelo en la lista de campos de personalización.

   ![](assets/extsignal_uc13.png)

1. Ahora puede terminar de configurar el mensaje y enviarlo como de costumbre.

   ![](assets/extsignal_uc14.png)

### Ejecución de los flujos de trabajo {#executing-the-workflows}

Una vez creados los flujos de trabajo, puede ejecutarlos. Asegúrese de que los dos flujos de trabajo se inician antes de realizar la llamada de API.
