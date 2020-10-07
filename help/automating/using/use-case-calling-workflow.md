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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '977'
ht-degree: 1%

---


# Ejemplo de uso {#use-case}

El caso de uso siguiente muestra cómo llamar al flujo de trabajo con parámetros dentro de sus flujos de trabajo.

El objetivo es activar un flujo de trabajo desde una llamada de API con parámetros externos. Este flujo de trabajo cargará datos en la base de datos desde un archivo y creará una audiencia asociada. Una vez creada la audiencia, se activará un segundo flujo de trabajo para enviar un mensaje personalizado con los parámetros externos definidos en la llamada de API.

Para realizar este caso de uso, debe realizar las acciones siguientes:

1. **Realice una llamada** de API para activar Workflow 1 con parámetros externos. Consulte [el paso 1: Configuración de la llamada](../../automating/using/use-case-calling-workflow.md#step-1--configuring-the-api-call)de API.
1. **Generar flujo de trabajo 1**: el flujo de trabajo transferirá un archivo y lo cargará en la base de datos. Luego comprobará si los datos están vacíos o no y, finalmente, guardará los perfiles en una audiencia. Finalmente, activará Workflow 2. Consulte [el paso 2: Configuración del flujo de trabajo 1](../../automating/using/use-case-calling-workflow.md#step-2--configuring-workflow-1).
1. **Generar flujo de trabajo 2**: el flujo de trabajo leerá la audiencia creada en Workflow 1 y, a continuación, enviará un mensaje personalizado a los perfiles, con un código de segmento personalizado con los parámetros. Consulte [el paso 3: Configuración del flujo de trabajo 2](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

![](assets/extsignal_uc_process.png)

## Requisitos previos {#prerequisites}

Antes de configurar los flujos de trabajo, debe crear Workflow 1 y 2 con una **[!UICONTROL External signal]** actividad en cada uno de ellos. De este modo, podrá realizar el destinatario de estas actividades de señal al llamar a los flujos de trabajo.

## Paso 1: Configuración de la llamada de API {#step-1--configuring-the-api-call}

Realice una llamada de API para activar Workflow 1 con parámetros. Para obtener más información sobre la sintaxis de llamada de API, consulte la documentación [de las API de REST de](../../api/using/triggering-a-signal-activity.md)Campaign Standard.

En nuestro caso, queremos llamar al flujo de trabajo con los parámetros siguientes:

* **fileToTarget**: el nombre del archivo que desea importar a la base de datos.
* **descuentosDesc**: la descripción que queremos mostrar en el envío para el descuento.

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

1. Declare los parámetros que se han definido en la llamada de API. Para ello, abra la **[!UICONTROL External signal]** actividad y agregue los nombres y tipos de los parámetros.

   ![](assets/extsignal_uc1.png)

1. Añada una **[!UICONTROL Transfer file]** actividad para importar datos en la base de datos.Para ello, arrastre y suelte la actividad, ábrala y, a continuación, seleccione la **[!UICONTROL Protocol]** ficha.
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

1. Si se recuperan datos, guárdelos en una audiencia. Para ello, agregue una **[!UICONTROL Save audience]** actividad al **Destinatario que no esté vacía** y, a continuación, ábrala.
1. Seleccione la **[!UICONTROL Use a dynamic label]** opción y, a continuación, utilice el parámetro **fileToTarget** como etiqueta de la audiencia:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc6.png)

1. Arrastre y suelte una **[!UICONTROL End]** actividad que llamará a Workflow 2 con parámetros y, a continuación, ábrala.
1. Seleccione la **[!UICONTROL External signal]** ficha y, a continuación, especifique el flujo de trabajo que se va a activar y su actividad de señal asociada.
1. Defina los parámetros que desee utilizar en Workflow 2 y sus valores asociados.

   En nuestro caso, queremos pasar los parámetros definidos originalmente en la llamada de API (**fileToTarget** y **descuentosDesc**), y un parámetro **segmentCode** adicional con un valor constante (&quot;20% de descuento&quot;).

   ![](assets/extsignal_uc7.png)

El flujo de trabajo 1 está configurado, ahora puede crear el flujo de trabajo 2. Para obtener más información, consulte [esta sección](../../automating/using/use-case-calling-workflow.md#step-3--configuring-workflow-2).

## Paso 3: Configuración del flujo de trabajo 2 {#step-3--configuring-workflow-2}

El flujo de trabajo 2 se generará de la siguiente manera:

* **[!UICONTROL External signal]** actividad: donde los parámetros deben declararse para poder utilizarse dentro del flujo de trabajo.
* **[!UICONTROL Read audience]** actividad: lee la audiencia guardada en Workflow 1.
* **[!UICONTROL Email delivery]** actividad: envía un mensaje recurrente a la audiencia de destino, personalizado con parámetros.

![](assets/extsignal_uc_wkf2.png)

Siga los pasos a continuación para configurar el flujo de trabajo:

1. Declare los parámetros definidos en Workflow 1.

   Para ello, abra la **[!UICONTROL External signal]** actividad y agregue el nombre y el tipo de cada parámetro definido en la **[!UICONTROL End]** actividad de Workflow 1.

   ![](assets/extsignal_uc8.png)

1. Utilice la audiencia que se ha guardado en el flujo de trabajo 1. Para ello, arrastre y suelte una **[!UICONTROL Read audience]** actividad en el flujo de trabajo y, a continuación, ábrala.
1. Seleccione la **[!UICONTROL Use a dynamic audience]** opción y, a continuación, utilice el parámetro **fileToTarget** como nombre de la audiencia que desea leer:

   ```
   $(vars/@fileToTarget)
   ```

   ![](assets/extsignal_uc9.png)

1. Asigne un nombre a la transición de salida según el parámetro **segmentCode** .

   To do this, select the **[!UICONTROL Transition]** tab, then the **[!UICONTROL Use a dynamic segment code]** option.

1. Utilice el parámetro **segmentCode** como nombre de la transición saliente:

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
1. Utilice el parámetro **descuentosDesc** como campo de personalización. Para ello, selecciónelo en la lista campos de personalización.

   ![](assets/extsignal_uc13.png)

1. Ahora puede terminar de configurar el mensaje y enviarlo como de costumbre.

   ![](assets/extsignal_uc14.png)

## Ejecución de los flujos de trabajo {#executing-the-workflows}

Una vez construidos los flujos de trabajo, puede ejecutarlos. Asegúrese de que los dos flujos de trabajo se inician antes de realizar la llamada de API.
