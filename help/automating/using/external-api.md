---
title: API externa
seo-title: API externa
description: API externa
seo-description: null
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
context-tags: Externalapi, flujo de trabajo, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb908d4e0ff23319025d3193bb9b22d006b5901e

---


# External API {#external-api}

## Description {#description}

![](assets/wf_externalAPI.png)

**[!UICONTROL External API]** La actividad incorpora datos en el flujo de trabajo desde un sistema **externo** a través de **una llamada de API** REST.

The REST endpoints can be a customer management system, an [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html) instance or an Experience Cloud REST endpoints (Data Platform, Target, Analytics, Campaign, etc).

>[!CAUTION]
>
>Esta capacidad está actualmente en versión beta pública. Debe aceptar el acuerdo de uso antes de comenzar con la actividad de API externa. Tenga en cuenta que, debido a que Adobe todavía no ha lanzado esta función beta pública, Adobe Client Care no lo admite, puede que contenga errores y que no funcione así como otras funciones publicadas.

Las características principales de esta actividad son:

* Capacidad para pasar datos en formato JSON a un extremo de API de REST de terceros
* Capacidad para recibir una respuesta JSON, asignarla a tablas de salida y pasar hacia abajo a otras actividades de flujo de trabajo.
* Administración de errores con una transición específica saliente

Se han implementado las siguientes garantías para esta actividad:

* Límite de tamaño de datos de respuesta http 5 MB
* El tiempo de espera de la solicitud es de 60 segundos
* No se permiten redirecciones HTTP
* Se rechazan las direcciones URL no HTTPS
* " Aceptar: application/json "request header and" Content-Type: Se permite el encabezado de respuesta application/json

>[!CAUTION]
>
>Tenga en cuenta que la actividad está pensada para recuperar datos de toda la campaña (conjunto más reciente de ofertas, puntuaciones más recientes, etc.) no para recuperar información específica para cada perfil, ya que esto puede dar como resultado una gran cantidad de datos que se transfieren. If the use case requires this, the recommendation is to use the [Transfer File](../../automating/using/transfer-file.md) activity.

## Configuration {#configuration}

Drag and drop an **[!UICONTROL External API]** activity into your workflow and open the activity to start the configuration.

### Asignación de entrada

La asignación de entrada es una tabla temporal generada por una actividad de entrada anterior que se mostrará y enviará como JSON en la interfaz de usuario.
En función de esta tabla temporal, el usuario puede modificar los datos de entrada.

![](assets/externalAPI-inbound.png)

The **Inbound resource** dropdown lets you select the query activity that will create the temporary table.

The **Add count parameter** checkbox will a count value for each row coming from the temporary table. Tenga en cuenta que esta casilla solo está disponible si la actividad de entrada está generando una tabla temporal.

The **Inbound Columns** section allow the user to add any fields from the inbound transition table. Las columnas seleccionadas serán las claves del objeto de datos. El objeto de datos del JSON será una lista de matriz que contiene datos de columnas seleccionadas de cada fila de la tabla de transición entrante.

The **customize parameter** text box lets you add a valid JSON with additional data needed by the external API. Estos datos adicionales se agregarán al objeto params del JSON generado.

### Asignación saliente

This tab lets you define the sample **JSON structure** returned by the API Call.

![](assets/externalAPI-outbound.png)

The JSON structure pattern is: `{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

The sample JSON definition must have the **following characteristics**:

* **es** un nombre de propiedad obligatorio en JSON, el contenido de "data" es una matriz JSON.
* **Los elementos** de la matriz deben contener propiedades de primer nivel (no se admiten niveles más profundos).
   **Los nombres** de propiedad terminaban convirtiéndose en nombres de columna para el esquema de salida de la tabla temporal de salida.
* **La definición del nombre** de columna se basa en el primer elemento de la matriz "data".
Columns definition (add/remove) and the type value of the property can be edited in the **Column definition** tab.

If the **parsing is validated** a message appears and invite you to customize the data mapping in the "Column definition" tab. En otros casos, se muestra un mensaje de error.

### Ejecución

This tab lets you define the **HTTPS Endpoint** that will send data to ACS. If needed, you can enter authentication information in the fields below.
![](assets/externalAPI-execution.png)

### Propiedades

This tab lets you control **general properties** on the external API activity like the displayed label in the UI. El ID interno no se puede personalizar.

![](assets/externalAPI-properties.png)

### Definición de columna

>[!NOTE]
>
>This tab appears when the **response data format** is completed and validated in Outbound Mapping tab.

The **Column definition** tab allows you to precisely specify the data structure of each column in order to import data that does not contain any errors and make it match the types that are already present in the Adobe Campaign database for future operations.

![](assets/externalAPI-column.png)

Por ejemplo, puede cambiar la etiqueta de una columna, seleccionar su tipo (cadena, entero, fecha, etc.)o incluso especificar el procesamiento de errores.

For more information, refer to the [Load File](../../automating/using/load-file.md) section.

### Transición

This tab lets you activate the **outbound transition** and its label. This specific transition is useful in case of **timeout** or if the payload exceed the **data size limit**.

![](assets/externalAPI-transition.png)

### Opciones de ejecución

Esta ficha está disponible en la mayoría de las actividades de flujo de trabajo. For more information, consult the [Activity properties](../../automating/using/executing-a-workflow.md#activity-properties) section.

![](assets/externalAPI-options.png)

## Solución de problemas

Se agregaron dos tipos de mensajes de registro a esta nueva actividad de flujo de trabajo: información y errores. Pueden ayudarle a solucionar problemas potenciales.

### Información

Estos mensajes de registro se utilizan para registrar información sobre puntos de comprobación útiles durante la ejecución de la actividad del flujo de trabajo. Concretamente, los siguientes mensajes de registro se utilizan para registrar el primer intento y un intento de reintento (y motivo para el primer intento) de acceder a la API.

<table> 
 <thead> 
  <tr> 
   <th> Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Invocar URL de API ' % s '.</td> 
   <td> <p>Invocando URL de API ' https://example.com/api/v1/web-coupon?count=2'.</p></td> 
  </tr> 
  <tr> 
   <td> Reintentar URL de API ' % s ', falló el intento previo (' % s ').</td> 
   <td> <p>Reintentar URL de API ' https://example.com/api/v1/web-coupon?count=2', falló el intento previo (' HTTP - 401 ').</p></td>
  </tr> 
  <tr> 
   <td> Transfiriendo contenido de ' % s ' (% s/% s).</td> 
   <td> <p>Transfiriendo contenido desde ' https://example.com/api/v1/web-coupon?count=2' (1234/1234).</p></td> 
  </tr>
 </tbody> 
</table>

### Errores

Estos mensajes de registro se utilizan para registrar información sobre condiciones de error inesperadas, lo que finalmente puede provocar errores en la actividad del flujo de trabajo.

<table> 
 <thead> 
  <tr> 
   <th> Code - Message format<br /> </th> 
   <th> Example<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF -560250 - Cuerpo de solicitud de API excedido (límite: ' % d ').</td> 
   <td> <p>Se excedió el límite del cuerpo de la solicitud de API (límite: ' 5242880 ').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560239 - La respuesta de la API excedió el límite (límite: ' % d ').</td> 
   <td> <p>Se excedió el límite de respuesta de API (límite: 5242880 ').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560245 - La URL de API no pudo analizarse (error: ' % d ').</td> 
   <td> <p>No se pudo analizar la URL de API (error: ' -2010 ').</p>
   <p> Nota: Este error se registra cuando la URL de API falla en las reglas de validación.</p></td>
  </tr> 
  <tr>
   <td> WKF -560244 - El host de URL de API no debe ser'localhost ', o literal de dirección IP (host de URL: ' % s ').</td> 
   <td> <p>El host de la URL de API no debe ser'localhost ', o literal de dirección IP (host de URL: ' localhost ').</p>
    <p>El host de la URL de API no debe ser'localhost ', o literal de dirección IP (host de URL: ' 192.168.0.5 ').</p>
    <p>El host de la URL de API no debe ser'localhost ', o literal de dirección IP (host de URL: ' [2001]').</p></td>
  </tr> 
  <tr> 
   <td> WKF -560238 - La URL de API debe ser una URL segura (https) (URL solicitada: ' % s ').</td> 
   <td> <p>La URL de API debe ser una URL segura (https) (URL solicitada: ' https://example.com/api/v1/web-coupon?count=2').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560249 - Error al crear el cuerpo de solicitud JSON. Error al agregar ' % s '.</td> 
   <td> <p>No se pudo crear el cuerpo de solicitud JSON. Error al agregar'params '.</p>
    <p>No se pudo crear el cuerpo de solicitud JSON. Error al agregar'datos '.</p></td>
  </tr> 
  <tr> 
   <td> WKF -560246 - La clave del encabezado HTTP es mala (clave de encabezado: ' % s ').</td> 
   <td> <p>La clave del encabezado HTTP es mala (clave de encabezado: ' % s ').</p>
   <p> Nota: Este error se registra cuando la clave de encabezado personalizada falla en la validación según [RFC] (https://tools.ietf.org/html/rfc7230#section-3.2.html)</p></td> 
  </tr>
 <tr> 
   <td> WKF -560248 - No se permite la clave de encabezado HTTP (clave del encabezado: ' % s ').</td> 
   <td> <p>No se permite la clave del encabezado HTTP (clave del encabezado: ' Accept ').</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560247 - El valor del encabezado AHTTP es negativo (valor de encabezado: ' % s ').</td> 
   <td> <p>El valor del encabezado HTTP es negativo (valor del encabezado: ' % s '). </p>
    <p>Nota: Este error se registra cuando el valor del encabezado personalizado falla en la validación según [RFC] (https://tools.ietf.org/html/rfc7230#section-3.2.html)</p></td> 
  </tr> 
  <tr> 
   <td> WKF -560240 - JSON Payload tiene una propiedad ' % s'errónea.</td> 
   <td> <p>La carga útil JSON tiene una propiedad'blah'errónea.</p></td>
  </tr> 
  <tr>
   <td> WKF -560241: JSON incorrecto o formato incorrecto.</td> 
   <td> <p>JSON incorrecto o formato incorrecto.</p>
   <p>Nota: Este mensaje solo se aplica al análisis del cuerpo de respuesta de la API externa y se registra al intentar validar si el cuerpo de respuesta sigue el formato JSON solicitado por esta actividad.</p></td>
  </tr>
  <tr> 
   <td> WKF -560246 - Activity failed (reason: ' % s ').</td> 
   <td> <p>Cuando la actividad falla debido a la respuesta de error HTTP 401 - Error de actividad (motivo: ' HTTP - 401 ')</p>
        <p>Cuando la actividad falla debido a una llamada interna fallida - La actividad falló (motivo: ' Irc - -nn ').</p>
        <p>Cuando falla la actividad debido a un encabezado de tipo de contenido no válido. - Error de actividad (motivo: ' Content-Type - application/html ').</p></td> 
  </tr>
 </tbody> 
</table>

<!--
## Example: Managing coupons with External API Activity

This example illustrates how to **add coupon value** retrieving by a REST call to profiles and then sending an email containing these coupon values.

The workflow is presented as follows:

![](assets/externalAPI_activity_example1.png)

1. Drag and drop an **External API** activity
    1. Parse the JSON sample responsa as {"data":[{"code":"value"}]}.
    1. Add the **Rest endpoint URL** and define authentication setting if needed
    ![](assets/externalAPI_activity_example2.png)
    1. In the **column definition** tab, add a new column called **code** that will store the code value.
        ![](assets/externalAPI_activity_example3.png)
    1. Enabled an **outbound transition** to manage request failures.
1. Drag and drop a **Query** activity
    1. Configure the **Target** tab to query all the **@adobe.com** email. For different Query samples, refer to the [Query](../../automating/using/query.md) section.
    1. In the **additional data** tab, add a new column based on **rowId()** function. This additional column allows you to reconciliate coupon code with the profile ID..
        ![](assets/externalAPI_activity_example4.png)

        >[!NOTE]
        >
        >This reconciliation approach means that the profile query number is equal to the number of coupon values returned by the REST call.
1. Once this two activities are configured, drag and drop an **Enrichment** activity to associate coupon values with profiles.
    1. Select the previous Query activity in the **primarySet** field.
        ![](assets/externalAPI_activity_example5.png)
    1. Create a new relation in the **Advanced relations** tab, and add the following reconciliation criteria:
    1. **@expr1** coming grom the Query activity in the source expression field.
    1. **@lineNum** as an expression that returns the line number for each coupon value in the destination field.
        ![](assets/externalAPI_activity_example6.png)
        More information on the enrichment activity are available [here](../../automating/using/enrichment.md)

    1. The transition **Data Structure** will contain:
        ![](assets/externalAPI_activity_example7.png)
1. Finally drag and drop a **Send via Email** activity.
    You can modify your email template by adding the **code** personnalized field.

-->
