---
title: Llamada a un flujo de trabajo con parámetros externos
seo-title: Llamada a un flujo de trabajo con parámetros externos
description: Llamada a un flujo de trabajo con parámetros externos
seo-description: Esta sección detalla los elementos que se usan para llamar a un flujo de trabajo con parámetros externos.
page-status-flag: no activado nunca
uuid: beccd 1 b 6-8 e 6 d -4504-9152-9 ff 537459 c 4 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: flujo de trabajo general operation
discoiquuid: 1676 da 91-55 e 3-414 f-bcd 3-bb 0804 b 682 bd
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 267e30c603baf67020aadefad578f91b40dc042d

---


# Calling a workflow with external parameters{#calling-a-workflow-with-external-parameters}

Campaign Standard permite llamar a un flujo de trabajo con parámetros (un nombre de audiencia objetivo, un nombre de archivo que importar, una parte del contenido del mensaje, etc.). De esta forma, puede integrar fácilmente las automatizaciones de Campañas con el sistema externo.

Veamos el siguiente ejemplo, donde queremos enviar correos electrónicos directamente desde un CMS. En ese caso, puede configurar el sistema para que seleccione la audiencia y el contenido de correo electrónico en el CMS. Al hacer clic en Enviar, se llamará a un flujo de trabajo de Campaña con estos parámetros, permitiéndole usarlos en el flujo de trabajo para definir la audiencia y el contenido URL que se usarán en la entrega.

El proceso para llamar a un flujo de trabajo con parámetros es el siguiente:

1. Declare the parameters in the **[!UICONTROL External signal]** activity. See [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).
1. Configure the **[!UICONTROL End]** activity or the API call to define the parameters and trigger the workflow **[!UICONTROL External signal]** activity.

Una vez que se activa el flujo de trabajo, los parámetros se ingestan en las variables de eventos del flujo de trabajo y se pueden utilizar dentro del flujo de trabajo. See [Customizing a workflow with external parameters](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-a-workflow-with-external-parameters).

![](assets/extsignal_process.png)

## Declaring the parameters in the External signal activity {#declaring-the-parameters-in-the-external-signal-activity}

The first step to call a workflow with parameters is to declare them in an **[!UICONTROL External signal]** activity.

1. Open the **[!UICONTROL External signal]** activity, then select the **[!UICONTROL Parameters]** tab.
1. Click the **[!UICONTROL Create element]** button, then specify the name and type of each parameter.

   >[!CAUTION]
   >
   >Make sure that the name and number of parameters are identical to what is defined when calling the workflow (see [Defining the parameters when calling the workflow](../../automating/using/calling-a-workflow-with-external-parameters.md#defining-the-parameters-when-calling-the-workflow)). Además, los tipos de parámetros deben ser coherentes con los valores esperados.

   ![](assets/extsignal_declaringparameters_1.png)

1. Una vez que los parámetros declarados, finalice la configuración del flujo de trabajo y ejecútela.

## Defining the parameters when calling the workflow {#defining-the-parameters-when-calling-the-workflow}

Esta sección detalla cómo definir parámetros al llamar a un flujo de trabajo. For more on how to perform this operation from an API call, refer to the [REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

Antes de definir los parámetros, asegúrese de que:

* The parameters have been declared in the **[!UICONTROL External Signal]** activity. See [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity).
* Se está ejecutando el flujo de trabajo que contiene la actividad de señal.

To configure the **[!UICONTROL End]** activity, follow the steps below:

1. Open the **[!UICONTROL End]** activity, then select the **[!UICONTROL External signal]** tab.
1. Seleccione el flujo de trabajo y la actividad de señal externa que desea llamar.
1. Click the **[!UICONTROL Create element]** button to add a parameter, then fill in its name and value.

   * **[!UICONTROL Name]**: el nombre que se ha declarado en **[!UICONTROL External signal]** la actividad (consulte [Declaración de los parámetros en la actividad de señal externa](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)).
   * **[!UICONTROL Value]**: el valor que desea asignar al parámetro. The value should follow the **Standard syntax**, described in [this section](../../automating/using/advanced-expression-editing.md#standard-syntax).
   ![](assets/extsignal_definingparameters_2.png)

   >[!CAUTION]
   >
   >Make sure that all the parameters have been declared in the **[!UICONTROL External signal]** activity. De lo contrario, se producirá un error al ejecutar la actividad.

1. Una vez definidos los parámetros, confirme la actividad y, a continuación, guarde el flujo de trabajo.

## Monitoring the events variables {#monitoring-the-events-variables}

Es posible supervisar las variables de eventos que están disponibles en el flujo de trabajo, incluidos los parámetros externos declarados. Para ello, siga los pasos a continuación:

1. Select the activity that follows the **[!UICONTROL External signal]** activity, then click the **[!UICONTROL Log and tasks]** button.
1. In the **[!UICONTROL Tasks]** tab, click ![](assets/edit_darkgrey-24px.png) button.

   ![](assets/extsignal_monitoring_2.png)

1. Se muestra el contexto de ejecución de la tarea (ID, estado, duración, etc.), incluidas todas las variables de eventos que ahora están disponibles para su uso en el flujo de trabajo.

   ![](assets/extsignal_monitoring_3.png)

## Customizing a workflow with external parameters {#customizing-a-workflow-with-external-parameters}

Una vez que se activa el flujo de trabajo, los parámetros se ingestan en las variables de eventos y se pueden utilizar para personalizar las actividades del flujo de trabajo.

They can, for example, be used to define which audience to read in the **[!UICONTROL Read audience]** activity, the name of the file to transfer in the **[!UICONTROL Transfer file]** activity, etc.

Activities that can be customized with events variables are detailed in [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables).

### Using events variables {#using-events-variables}

Events variables are used within an expression that must respect the **[Standard syntax](../../automating/using/advanced-expression-editing.md#standard-syntax)**.

The syntax to use events variables must follow the format below, and use the parameter's name that has been defined in the **[!UICONTROL External signal]** activity (see [Declaring the parameters in the External signal activity](../../automating/using/calling-a-workflow-with-external-parameters.md#declaring-the-parameters-in-the-external-signal-activity)):

```
$(vars/@parameterName)
```

In this syntax, the **$** function returns **string** data type. Si desea especificar otro tipo de datos, utilice las siguientes funciones:

* **$ long**: número entero.
* **$ float**: decimal.
* **$ boolean**: true/false.
* **$ datetime**: timestamp.

Al utilizar una variable en una actividad, la interfaz proporciona ayuda para llamarla.

![](assets/extsignal_callparameter.png)

* ![](assets/extsignal_picker.png): seleccione la variable events entre todas las variables disponibles en el flujo de trabajo (véase).

   ![](assets/wkf_test_activity_variables.png)

* ![](assets/extsignal_expression_editor.png): editar expresiones combinando variables y funciones. For more on the Expression editor, refer to [this section](../../automating/using/advanced-expression-editing.md).

   ![](assets/wkf_test_activity_variables_expression.png)

**Temas relacionados:**

* [Editar una expresión](../../automating/using/advanced-expression-editing.md#edit-an-expression)
* [Sintaxis estándar](../../automating/using/advanced-expression-editing.md#standard-syntax)
* [Lista de funciones](../../automating/using/list-of-functions.md)

### Customizing activities with events variables {#customizing-activities-with-events-variables}

Las variables de eventos pueden utilizarse para personalizar varias actividades, enumeradas en la sección siguiente. For more on how to call a variable from an activity, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#using-events-variables).

**[!UICONTROL Read audience]** actividad: definir la audiencia objetivo según las variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/read-audience.md).

![](assets/extsignal_activities_audience.png)

**[!UICONTROL Test]** actividad: condiciones de compilación basadas en variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/test.md).

![](assets/extsignal_activities_test.png)

**[!UICONTROL Transfer file]** actividad: personalice el archivo que se va a transferir según las variables de eventos.

For more on how to use the activity, refer to the [dedicated section](../../automating/using/transfer-file.md).

![](assets/extsignal_activities_transfer.png)

**[!UICONTROL Query]** actividad: se puede hacer referencia a parámetros en una consulta mediante expresiones que combinan variables y variables de eventos. To do this, add a rule then click the **[!UICONTROL Advanced mode]** link to access the expression editing window (see [Advanced expression editing](../../automating/using/advanced-expression-editing.md)).

For more on how to use the activity, refer to the [dedicated section](../../automating/using/query.md).

![](assets/extsignal_activities_query.png)

**[!UICONTROL Channels]** actividades: personalizar entregas basadas en variables de eventos.

>[!NOTE]
>
>Los valores de los parámetros de entrega se recuperan cada vez que se prepara la entrega.
>
>Recurring deliveries preparation is based on the delivery **aggregation period**. Por ejemplo, si el período de agregación es "por día", el envío se vuelve a preparar una vez al día. Si se modifica el valor de un parámetro de entrega durante el día, no se actualizará en la entrega, ya que ya se preparó una vez.
>
>If you plan on calling the workflow multiple times a day, use the [!UICONTROL No aggregation] option, so that the delivery parameters are updated each time. For more on recurring deliveries configuration, refer to [this section](/help/automating/using/email-delivery.md#configuration).

Para personalizar una entrega basada en variables de eventos, primero debe declarar en la actividad de entrega las variables que desee utilizar:

1. Select the activity, then click the ![](assets/dlv_activity_params-24px.png) button to access the settings.
1. Select the **[!UICONTROL General]** tab, then add the events variables that will be available as personalization fields in the delivery.

   ![](assets/extsignal_activities_delivery.png)

1. Click the **[!UICONTROL Confirm]** button.

Las variables declaradas de eventos ahora están disponibles en la lista de campos de personalización. Puede utilizarlos en la entrega para realizar las acciones siguientes:

* Defina el nombre de la plantilla que se utilizará para la entrega.

   >[!NOTE]
   >
   >This action is available for **recurring** deliveries only.

   ![](assets/extsignal_activities_template.png)

* Personalize the delivery: when selecting a personalization field to configure a delivery, events variables are available in the **[!UICONTROL Workflow parameters]** element. Puede utilizarlos como cualquier campo de personalización, por ejemplo para definir el asunto, el remitente, etc.

   Delivery personalization is detailed in [this section](../../designing/using/about-personalization.md).

   ![](assets/extsignal_activities_perso.png)

**Códigos de segmentos**: definir el código de segmento basado en variables de eventos.

>[!NOTE]
>
>This action can be performed from any activity that lets you define a segment code like, for example, **[!UICONTROL Query]** or **[!UICONTROL Segmentation]** activities.

![](assets/extsignal_activities_segment.png)

**Etiqueta de envío**: defina la etiqueta de entrega en función de las variables de eventos.

![](assets/extsignal_activities_label.png)

## Use case {#use-case}

El caso de uso siguiente muestra cómo llamar a workflow con parámetros dentro de los flujos de trabajo.

El objetivo es activar un flujo de trabajo desde una llamada de API con parámetros externos. Este flujo de trabajo cargará los datos en la base de datos desde un archivo y creará una audiencia asociada. Una vez creada la audiencia, se activará un segundo flujo de trabajo para enviar un mensaje personalizado con los parámetros externos definidos en la llamada de API.

Para realizar este caso de uso, debe realizar las acciones siguientes:

1. **Realice una llamada** de API para activar Workflow 1 con parámetros externos. See [Step 1: Configuring the API call](../../automating/using/calling-a-workflow-with-external-parameters.md#step-1--configuring-the-api-call).
1. **Flujo de trabajo de creación 1**: el flujo de trabajo transferirá un archivo y lo cargará en la base de datos. A continuación, comprobará si los datos están vacíos o no y, finalmente, guarde los perfiles en una audiencia. Finalmente, activará Workflow 2. See [Step 2: Configuring Workflow 1](../../automating/using/calling-a-workflow-with-external-parameters.md#step-2--configuring-workflow-1).
1. **Flujo de trabajo de creación 2**: El flujo de trabajo leerá la audiencia que se ha creado en Flujo de trabajo 1 y, a continuación, envía un mensaje personalizado a los perfiles, con un código de segmento personalizado con los parámetros. See [Step 3: Configuring Workflow 2](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

### Prerequisites {#prerequisites}

Before configuring the workflows, you need to create Workflow 1 and 2 with an **[!UICONTROL External signal]** activity in each of them. De esta forma, podrá dirigir estas actividades de señal al llamar a los flujos de trabajo.

### Step 1: Configuring the API call {#step-1--configuring-the-api-call}

Realice una llamada de API para activar Workflow 1 con parámetros. For more on the API call syntax, refer to the [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

En nuestro caso, queremos llamar al flujo de trabajo con los parámetros siguientes:

* **Filetotarget**: el nombre del archivo que se desea importar en la base de datos.
* **Discountdesc**: la descripción que queremos mostrar en la entrega del descuento.

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

### Step 2: Configuring Workflow 1 {#step-2--configuring-workflow-1}

El flujo de trabajo 1 se creará de la siguiente manera:

* **[!UICONTROL External signal]** actividad: donde deben declararse los parámetros externos para usarlos dentro del flujo de trabajo.
* **[!UICONTROL Transfer file]** actividad: importa el archivo con el nombre definido en los parámetros.
* **[!UICONTROL Load file]** actividad: carga datos del archivo importado en la base de datos.
* **[!UICONTROL Update data]** actividad: inserta o actualice la base de datos con datos del archivo importado.
* **[!UICONTROL Test]** actividad: comprueba si hay datos importados.
* **[!UICONTROL Save audience]** actividad: Si el archivo contiene datos, guarda los perfiles en una audiencia.
* **[!UICONTROL End activity]** actividad: llama al flujo de trabajo 2 con los parámetros que desea utilizar dentro de él.

![](assets/extsignal_uc_wkf1.png)

Siga los pasos a continuación para configurar el flujo de trabajo:

1. Declare los parámetros que se han definido en la llamada de API. To do this, open the **[!UICONTROL External signal]** activity, then add the parameters' names and types.

   ![](assets/extsignal_uc1.png)

1. Add a **[!UICONTROL Transfer file]** activity to import data into the database.To do this, drag and drop the activity, open it, then select the **[!UICONTROL Protocol]** tab.
1. Select the **[!UICONTROL Use a dynamic file path]** option, then use the **fileToTarget** parameter as the file to transfer:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Cargue los datos del archivo en la base de datos.

   To do this, drag and drop a **[!UICONTROL Load file]** activity into the workflow, then configure it according to your needs.

1. Inserte y actualice la base de datos con datos del archivo importado.

   To do this, drag and drop an **[!UICONTROL Update data]** activity, then select the **[!UICONTROL Identification]** tab to add a reconciliation criteria (in our case the **email** field).

   ![](assets/extsignal_uc3.png)

1. Select the **[!UICONTROL Fields to update]** tab, then specify the fields to update in the database (in our case the **firstname** and **email** fields).

   ![](assets/extsignal_uc4.png)

1. Compruebe si los datos se recuperan del archivo. To do this, drag and drop a **[!UICONTROL Test]** activity into the workflow, then click the **[!UICONTROL Add an element]** button to add a condition.
1. Asigne un nombre a la condición y defina la misma. En nuestro caso, queremos probar si la transición saliente contiene datos con la sintaxis siguiente:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Si se recuperan los datos, guárdelos en una audiencia. To do this, add a **[!UICONTROL Save audience]** activity to the **Target not empty** transition, then open it.
1. Select the **[!UICONTROL Use a dynamic label]** option, then use the **fileToTarget** parameter as the label of the audience:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Drag and drop an **[!UICONTROL End]** activity that will call Workflow 2 with parameters, then open it.
1. Select the **[!UICONTROL External signal]** tab, then specify the workflow to trigger and its associated signal activity.
1. Defina los parámetros que desee utilizar en el flujo de trabajo 2 y sus valores asociados.

   In our case, we want to pass the parameters originally defined in the API call (**fileToTarget** and **discountDesc**), and an additional **segmentCode** parameter with a constant value ("20% discount").

   ![](assets/extsignal_uc7.png)

El flujo de trabajo 1 está configurado, ahora puede crear el flujo de trabajo 2. For more on this, refer to [this section](../../automating/using/calling-a-workflow-with-external-parameters.md#step-3--configuring-workflow-2).

### Step 3: Configuring Workflow 2 {#step-3--configuring-workflow-2}

El flujo de trabajo 2 se generará de la siguiente manera:

* **[!UICONTROL External signal]** actividad: donde deben declararse los parámetros para usarlos dentro del flujo de trabajo.
* **[!UICONTROL Read audience]** actividad: lee la audiencia guardada en Flujo de trabajo 1.
* **[!UICONTROL Email delivery]** actividad: envía un mensaje recurrente a la audiencia de destino, personalizado con parámetros.

![](assets/extsignal_uc_wkf2.png)

Siga los pasos a continuación para configurar el flujo de trabajo:

1. Declare los parámetros definidos en Flujo de trabajo 1.

   To do this, open the **[!UICONTROL External signal]** activity, then add the name and type of each parameter defined in the **[!UICONTROL End]** activity of Workflow 1.

   ![](assets/extsignal_uc8.png)

1. Utilice la audiencia que se ha guardado en Flujo de trabajo 1. To do this, drag and drop a **[!UICONTROL Read audience]** activity into the workflow, then open it.
1. Select the **[!UICONTROL Use a dynamic audience]** option, then use the **fileToTarget** parameter as the name of the audience to read:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Name the outbound transition according to the **segmentCode** parameter.

   To do this, select the **[!UICONTROL Transition]** tab, then the **[!UICONTROL Use a dynamic segment code]** option.

1. Use the **segmentCode** parameter as the name of the outbound transition:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Drag and drop an **[!UICONTROL Email delivery]** activity to send a message to the audience.
1. Identify the parameters to use in the message to personalize it with the **discountDesc** parameter. Para ello, abra las opciones avanzadas de la actividad y, a continuación, agregue el nombre y el valor del parámetro.

   ![](assets/extsignal_uc10b.png)

1. Ahora puede configurar el mensaje. Open the activity, then select **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Seleccione la plantilla que desee utilizar y defina las propiedades de correo electrónico según sus necesidades.
1. Use the **discountDesc** parameter as a personalization field. Para ello, selecciónelo en la lista de campos de personalización.

   ![](assets/extsignal_uc13.png)

1. Ahora puede finalizar la configuración del mensaje y enviarlo como de costumbre.

   ![](assets/extsignal_uc14.png)

### Executing the workflows {#executing-the-workflows}

Una vez creados los flujos de trabajo, puede ejecutarlos. Asegúrese de que los dos flujos de trabajo se inician antes de realizar la llamada de API.
