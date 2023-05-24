---
title: Caso de uso para invocar al flujo de trabajo
description: Esta sección detalla cómo invocar a un flujo de trabajo con parámetros externos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 7a21f4f6-316f-4f3d-9d53-37d406a46aae
source-git-commit: a6471d2970a55373574301fb5d49ee73103fa870
workflow-type: tm+mt
source-wordcount: '976'
ht-degree: 1%

---

# Caso de uso {#use-case}

El siguiente caso de uso muestra cómo invocar al flujo de trabajo con parámetros dentro de sus flujos de trabajo.

El objetivo es almacenar en déclencheur un flujo de trabajo desde una llamada de API con parámetros externos. Este flujo de trabajo carga datos en la base de datos desde un archivo y crea una audiencia asociada. Una vez creada la audiencia, se activa un segundo flujo de trabajo para enviar un mensaje personalizado con los parámetros externos definidos en la llamada de API.

Para realizar este caso de uso, debe realizar las siguientes acciones:

1. **Realizar una llamada de API** para almacenar en déclencheur el flujo de trabajo 1 con parámetros externos. Consulte [Paso 1: Configuración de la llamada de API](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call).
1. **Flujo de trabajo de compilación 1**: el flujo de trabajo transfiere un archivo y lo carga en la base de datos. A continuación, se comprueba si los datos están vacíos o no y, finalmente, se guardan los perfiles en una audiencia. Por último, se utilizará el déclencheur Workflow 2. Consulte [Paso 2: Configuración del flujo de trabajo 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **Flujo de trabajo de compilación 2**: el flujo de trabajo leerá la audiencia que se ha creado en el flujo de trabajo 1 y, a continuación, enviará un mensaje personalizado a los perfiles con un código de segmento personalizado con los parámetros. Consulte [Paso 3: Configuración del flujo de trabajo 2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## Requisitos previos {#prerequisites}

Antes de configurar los flujos de trabajo, debe crear los flujos de trabajo 1 y 2 con una **[!UICONTROL External signal]** actividad en cada uno de ellos. De este modo, podrá segmentar estas actividades de señal al invocar a los flujos de trabajo.

## Paso 1: Configuración de la llamada de API {#step-1--configuring-the-api-call}

Realice una llamada de API al flujo de trabajo 1 de déclencheur con parámetros. Para obtener más información sobre la sintaxis de la llamada de API, consulte la [Documentación de las API de REST de Campaign Standard](../../api/using/triggering-a-signal-activity.md).

En nuestro caso, queremos llamar al flujo de trabajo con los parámetros siguientes:

* **fileToTarget**: nombre del archivo que queremos importar en la base de datos.
* **discountDesc**: la descripción que queremos mostrar en la entrega del descuento.

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

## Paso 2: Configuración del flujo de trabajo 1 {#step-2--configuring-workflow-1}

El flujo de trabajo 1 se creará de la siguiente manera:

* **[!UICONTROL External signal]** actividad: donde se deben declarar los parámetros externos para utilizarlos en el flujo de trabajo.
* **[!UICONTROL Transfer file]** actividad: importa el archivo con el nombre definido en los parámetros.
* **[!UICONTROL Load file]** actividad: carga datos del archivo importado en la base de datos.
* **[!UICONTROL Update data]** actividad: insertar o actualizar la base de datos con datos del archivo importado.
* **[!UICONTROL Test]** actividad: comprueba si hay datos importados.
* **[!UICONTROL Save audience]** actividad: si el archivo contiene datos, guarda los perfiles en una audiencia.
* **[!UICONTROL End activity]** actividad: llama al flujo de trabajo 2 con los parámetros que desea utilizar en él.

![](assets/extsignal_uc_wkf1.png)

Siga los pasos a continuación para configurar el flujo de trabajo:

1. Declare los parámetros que se han definido en la llamada de API. Para ello, abra el **[!UICONTROL External signal]** actividad y, a continuación, añada los nombres y tipos de los parámetros.

   ![](assets/extsignal_uc1.png)

1. Añadir un **[!UICONTROL Transfer file]** actividad para importar datos en la base de datos. Para ello, arrastre y suelte la actividad, ábrala y seleccione. **[!UICONTROL Protocol]** pestaña.
1. Seleccione el **[!UICONTROL Use a dynamic file path]** y, a continuación, utilice la **fileToTarget** como el archivo que se va a transferir:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc2.png)

1. Cargue los datos del archivo en la base de datos.

   Para ello, arrastre y suelte un **[!UICONTROL Load file]** en el flujo de trabajo y, a continuación, configúrelo según sus necesidades.

1. Inserte y actualice la base de datos con los datos del archivo importado.

   Para ello, arrastre y suelte una **[!UICONTROL Update data]** actividad, luego seleccione la **[!UICONTROL Identification]** para añadir un criterio de reconciliación (en nuestro caso, la variable **email** field).

   ![](assets/extsignal_uc3.png)

1. Seleccione el **[!UICONTROL Fields to update]** , luego especifique los campos que se actualizarán en la base de datos (en nuestro caso, la variable **firstname** y **email** campos).

   ![](assets/extsignal_uc4.png)

1. Compruebe si se recuperan datos del archivo. Para ello, arrastre y suelte un **[!UICONTROL Test]** en el flujo de trabajo y, a continuación, haga clic en **[!UICONTROL Add an element]** para añadir una condición.
1. Nombre y defina la condición. En nuestro caso, queremos probar si la transición saliente contiene datos con la sintaxis siguiente:

   ```
   $long(vars/@recCount)>0
   ```

   ![](assets/extsignal_uc5.png)

1. Si se recuperan datos, guárdelos en una audiencia. Para ello, añada un **[!UICONTROL Save audience]** actividad a la **Destino no vacío** transición y, a continuación, ábrala.
1. Seleccione el **[!UICONTROL Use a dynamic label]** y, a continuación, utilice la **fileToTarget** como etiqueta de la audiencia:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Arrastre y suelte un **[!UICONTROL End]** actividad que llamará al flujo de trabajo 2 con parámetros y, a continuación, ábrala.
1. Seleccione el **[!UICONTROL External signal]** y, a continuación, especifique el flujo de trabajo de déclencheur y su actividad de señal asociada.
1. Defina los parámetros que desea utilizar en el flujo de trabajo 2 y sus valores asociados.

   En nuestro caso, queremos pasar los parámetros definidos originalmente en la llamada de API (**fileToTarget** y **discountDesc**) y un adicional **segmentCode** parámetro con un valor constante (&quot;20% de descuento&quot;).

   ![](assets/extsignal_uc7.png)

El flujo de trabajo 1 está configurado y ahora puede crear el flujo de trabajo 2. Para obtener más información, consulte [esta sección](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

## Paso 3: Configuración del flujo de trabajo 2 {#step-3--configuring-workflow-2}

El flujo de trabajo 2 se creará de la siguiente manera:

* **[!UICONTROL External signal]** actividad: donde se deben declarar los parámetros para utilizarlos en el flujo de trabajo.
* **[!UICONTROL Read audience]** actividad: lee la audiencia guardada en el flujo de trabajo 1.
* **[!UICONTROL Email delivery]** actividad: envía un mensaje recurrente a la audiencia de destino, personalizado con parámetros.

![](assets/extsignal_uc_wkf2.png)

Siga los pasos a continuación para configurar el flujo de trabajo:

1. Declare los parámetros que se han definido en el flujo de trabajo 1.

   Para ello, abra el **[!UICONTROL External signal]** actividad y, a continuación, añada el nombre y el tipo de cada parámetro definido en la **[!UICONTROL End]** actividad del flujo de trabajo 1.

   ![](assets/extsignal_uc8.png)

1. Utilice la audiencia que se ha guardado en el flujo de trabajo 1. Para ello, arrastre y suelte un **[!UICONTROL Read audience]** en el flujo de trabajo y, a continuación, ábralo.
1. Seleccione el **[!UICONTROL Use a dynamic audience]** y, a continuación, utilice la **fileToTarget** parámetro como nombre de la audiencia que se va a leer:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Asigne un nombre a la transición saliente según el parámetro **segmentCode** parámetro.

   Para ello, seleccione la **[!UICONTROL Transition]** y, a continuación, **[!UICONTROL Use a dynamic segment code]** opción.

1. Utilice el **segmentCode** parámetro como nombre de la transición saliente:

   ```
   $(vars/@segmentCode)
   ```

   ![](assets/extsignal_uc10.png)

1. Arrastre y suelte un **[!UICONTROL Email delivery]** actividad para enviar un mensaje a la audiencia.
1. Identifique los parámetros que se utilizarán en el mensaje para personalizarlo con **discountDesc** parámetro. Para ello, abra las opciones avanzadas de la actividad y añada el nombre y el valor del parámetro.

   ![](assets/extsignal_uc10b.png)

1. Ahora puede configurar el mensaje. Abra la actividad y seleccione **[!UICONTROL Recurring email]**.

   ![](assets/extsignal_uc11.png)

1. Seleccione la plantilla que desea utilizar y defina las propiedades de correo electrónico según sus necesidades.
1. Utilice el **discountDesc** como campo de personalización. Para ello, selecciónelo en la lista de campos personalizados.

   ![](assets/extsignal_uc13.png)

1. Ahora puede finalizar la configuración del mensaje y, a continuación, enviarlo como de costumbre.

   ![](assets/extsignal_uc14.png)

## Ejecución de flujos de trabajo {#executing-the-workflows}

Una vez creados los flujos de trabajo, puede ejecutarlos. Asegúrese de que los dos flujos de trabajo se inicien antes de realizar la llamada de API.
