---
title: API externa
description: La actividad de API externa introduce datos en el flujo de trabajo del Campaign Standard desde un sistema externo a través de una llamada de API HTTP.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: externalAPI,workflow,main
feature: Workflows
role: Data Architect
level: Experienced
exl-id: 44ad654e-bde9-4189-8765-0479d81dc0f7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '2200'
ht-degree: 94%

---

# API externa {#external-api}

## Descripción {#description}

![](assets/wf_externalAPI.png)

La actividad de **[!UICONTROL External API]** introduce datos en el flujo de trabajo desde un **sistema externo** a través de una llamada de **API HTTP**.

Los extremos externos del sistema pueden ser extremos de API públicos, sistemas de administración de clientes o instancias de aplicaciones sin servidor (por ejemplo, [Adobe I/O Runtime](https://www.adobe.io/apis/experienceplatform/runtime.html)), por mencionar algunas categorías.

>[!NOTE]
>
>Por motivos de seguridad, el uso de JSSP no es compatible con Campaign Standard. Si necesita ejecutar código, puede llamar a una instancia de Adobe I/O Runtime a través de la actividad de API externa.

Las principales características de esta actividad son:

* Capacidad para pasar datos en formato JSON a un extremo de API de REST de terceros.
* Capacidad para recibir una respuesta JSON, asignarla a tablas de salida y pasar a otras actividades de flujo de trabajo.
* Administración de errores con una transición específica de salida.

### Avisos de compatibilidad con versiones anteriores {#from-beta-to-ga}

Con la versión Campaign Standard 20.4, se han reducido los márgenes de límite de tamaño de datos de respuesta http y de tiempo de espera de respuesta para ajustarse a las prácticas recomendadas; consulte [Limitaciones y protecciones](#guardrails). Estas modificaciones de la limitación no tendrán efecto en las actividades de API externas existentes; por lo tanto, se recomienda reemplazar las actividades de API externas existentes con nuevas versiones en todos los flujos de trabajo.

Al reemplazar actividades de API externas, añada la nueva actividad de API externa al flujo de trabajo, copie manualmente los detalles de configuración y, a continuación, elimine la actividad antigua.

>[!NOTE]
>
>No podrá copiar sobre los valores del encabezado específicos de la actividad, ya que están enmascarados dentro de la actividad.

### Limitaciones y barreras {#guardrails}

Esta actividad se rige por las siguientes limitaciones:

* Límite de tamaño de datos de respuesta http de 5 MB (Nota: Esto supone un cambio con respecto al límite de 50 MB de la versión anterior).
* El tiempo de espera de la solicitud es de 1 minuto (Nota: Esto supone un cambio con respecto al tiempo de espera de 10 minutos de la versión anterior).
* No se permiten redirecciones HTTP.
* Se rechazan las direcciones URL que no son HTTPS.
* Están permitidos el encabezado de solicitud “Accept: application/json” y el encabezado de respuesta “Content-Type: application/json”.

Se han establecido limitaciones específicas:

* **Profundidad máxima de JSON**: limitar la profundidad máxima de un archivo JSON personalizado anidado que se puede procesar a 10 niveles.
* **Longitud máxima de clave JSON**: limitar la longitud máxima de la clave interna generada a 255. Esta clave está asociada al ID de columna.
* **Se permiten las claves de duplicado máximas de JSON**: limitar el número total máximo de nombres de propiedades JSON de duplicado, que se utilizan como ID de columna, a 150.

>[!CAUTION]
>
>La actividad de la API externa está diseñada para obtener datos de toda la campaña (último conjunto de ofertas, puntuaciones más recientes, etc.), no para recuperar información específica para cada perfil, ya que esto puede conllevar transferir grandes cantidades de datos. Si fuera necesario, se recomienda utilizar la actividad [Transferir archivo](../../automating/using/transfer-file.md).

## Configuración {#configuration}

Arrastre y suelte una actividad de **[!UICONTROL External API]** en el flujo de trabajo y ábrala para comenzar con la configuración.

### Asignación de entrada

La asignación de entrada es una tabla temporal generada por una actividad de entrada anterior que se muestra y envía como JSON en la interfaz de usuario.
En función de esta tabla temporal, el usuario puede realizar modificaciones en los datos de entrada.

![](assets/externalAPI-inbound.png)

La lista desplegable **Recurso de entrada** permite seleccionar la actividad de consulta que crea la tabla temporal.

La casilla de verificación **Añadir parámetro de recuento** añade un valor de recuento para cada fila proveniente de la tabla temporal. Tenga en cuenta que esta casilla de verificación solo está disponible si la actividad de entrada genera una tabla temporal.

La sección **Columnas de entrada** permite al usuario añadir cualquier campo de la tabla de transición de entrada. Las columnas seleccionadas son las claves del objeto de datos. El objeto de datos en el archivo JSON es una lista de matriz que contiene datos para las columnas seleccionadas de cada fila de la tabla de transición de entrada.

El cuadro de texto **Personalizar parámetro** le permite añadir un archivo JSON válido con los datos adicionales que necesita la API externa. Estos datos adicionales se añaden al objeto parámetros en el archivo JSON generado.

### Asignación de salida

Esta pestaña le permite definir la **estructura JSON** de muestra devuelta por la llamada de API.

![](assets/externalAPI-outbound.png)

El analizador JSON está diseñado para admitir tipos de patrones de estructura JSON estándar, con algunas excepciones. Un ejemplo de patrón estándar es:`{“data”:[{“key”:“value”}, {“key”:“value”},...]}`

La definición JSON de muestra debe tener las **siguientes características**:

* **Los elementos de matriz** deben contener propiedades de primer nivel (no se admiten niveles más profundos).
   **Los nombres de propiedades** terminan convirtiéndose en nombres de columna para el esquema de salida de la tabla temporal.
* **Los elementos JSON** que se van a recopilar deben tener 10 niveles o menos de anidación dentro de la respuesta JSON.
* **La definición del nombre de columna** se basa en el primer elemento de la matriz de “datos”.
La definición de columnas (añadir/quitar) y el valor de tipo de la propiedad se pueden editar en la pestaña **Definición de columna**.

El comportamiento de la **casilla Acoplar**:

La casilla Acoplar (sin marcar por defecto) sirve para indicar si desea acoplar el archivo JSON a un mapa de clave/valor o no.

* Cuando la **casilla de verificación está desactivada** (sin marcar), el archivo JSON de muestra se analiza para buscar un objeto de matriz. El usuario debe proporcionar una versión recortada como muestra de la respuesta de API en formato JSON para que Adobe Campaign pueda determinar exactamente qué matriz le interesa utilizar. En el momento de la creación del flujo de trabajo, se determina y registra la ruta al objeto de matriz anidado, de modo que se pueda utilizar en el momento de la ejecución para acceder a ese objeto de matriz desde el cuerpo de respuesta JSON recibido de la llamada de API.

* Cuando la **casilla de verificación está activada** (marcada), el archivo JSON de muestra se acopla y todas las propiedades especificadas en el archivo de muestra proporcionado se utilizan para crear columnas de la tabla temporal de salida y se muestran en la pestaña Definiciones de columna. Tenga en cuenta que si hay algún objeto de matriz en el archivo JSON de muestra, también se acoplan todos los elementos de esos objetos de matriz.


Si se **valida el análisis**, aparece un mensaje que le invita a personalizar la asignación de datos en la pestaña “Definición de columna”. En otros casos, se muestra un mensaje de error.

### Ejecución

Esta pestaña permite definir el extremo de la conexión. El campo **[!UICONTROL URL]** permite definir el **extremo HTTPS** con el que se comunicará el Campaign Standard.

Si lo necesita el extremo, hay dos tipos de método de autenticación disponibles.

* Autenticación básica: introduzca la información de nombre de usuario y contraseña en la sección **[!UICONTROL Request Header(s)]**.

* Autenticación de OAuth: Al hacer clic en **[!UICONTROL Use connection parameters defined in an external account]** en una cuenta externa, puede seleccionar una cuenta externa donde se define la autenticación OAuth. Para obtener más información, consulte la sección [Cuentas externas](../../administration/using/external-accounts.md) .

![](assets/externalAPI-execution.png)

### Propiedades

Esta pestaña le permite controlar las **propiedades generales** de la actividad de API externa, como las que se muestran en la interfaz de usuario. El ID interno no se puede personalizar.

![](assets/externalAPI-properties.png)

### Definición de columna

>[!NOTE]
>
>Esta pestaña aparece cuando se completa y valida el **formato de datos de respuesta** en la pestaña Asignación de salida.

La pestaña **Definición de columna** le permite especificar con precisión la estructura de datos de cada columna para importar datos que no contengan errores y hacer que coincidan con los tipos que ya están presentes en la base de datos de Adobe Campaign para futuras operaciones.

![](assets/externalAPI-column.png)

Por ejemplo, puede cambiar la etiqueta de una columna y seleccionar su tipo (cadena, entero, fecha, etc.) o incluso especificar el procesamiento de errores.

Para obtener más información, consulte la sección [Cargar archivo](../../automating/using/load-file.md).

### Transición

Esta pestaña le permite activar la **transición de salida** y su etiqueta. Esta transición específica resulta útil en caso de **tiempo de espera** o si la carga supera el **límite de tamaño de datos**.

![](assets/externalAPI-transition.png)

### Opciones de ejecución

Esta pestaña está disponible en la mayoría de las actividades de flujo de trabajo. Para obtener más información, consulte la sección [Propiedades de actividad](../../automating/using/activity-properties.md).

![](assets/externalAPI-options.png)

## Pruebas

Para probar la funcionalidad de la API externa con un punto final de prueba sencillo, puede utilizar Postman Echo: https://docs.postman-echo.com.

## Resolución de problemas

Se han añadido dos tipos de mensajes de registro a esta nueva actividad de flujo de trabajo: información y errores. Pueden ayudarle a solucionar problemas potenciales.

### Información

Estos mensajes de registro se utilizan para registrar información sobre puntos de comprobación útiles durante la ejecución de la actividad del flujo de trabajo.
<table> 
 <thead> 
  <tr> 
   <th> Formato del mensaje<br /> </th> 
   <th> Ejemplo<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Invoking API URL '%s'.</td> 
   <td> <p>Invocando la dirección URL de la API “https://example.com/api/v1/web-coupon?count=2”.</p></td> 
  </tr> 
  <tr> 
   <td> Retrying API URL '%s' due to %s in %d ms, attempt %d.</td> 
   <td> <p>Reintentando la URL de la API “https://example.com/api/v1/web-coupon?count=0” due to HTTP - 401 in 2364 ms, intento 2.</p></td>
  </tr> 
  <tr> 
   <td> Transferring content from '%s' (%s / %s).</td> 
   <td> <p>Transferencia de contenido desde “https://example.com/api/v1/web-coupon?count=2” (1234 / 1234).</p></td> 
  </tr>
  <tr> 
   <td> Using cached access token for provider ID '%s'.</td> 
   <td> <p>Usando token de acceso en caché para el identificador de proveedor “EXT25”. Nota: EXT25 es la ID (o nombre) de la cuenta externa. </p></td> 
  </tr>
  <tr> 
   <td> Fetched access token from server for provider ID '%s'.</td> 
   <td> <p>Se obtuvo el token de acceso del servidor para el identificador de proveedor “EXT25”. Nota: EXT25 es la ID (o nombre) de la cuenta externa.</p></td> 
  </tr>
  <tr> 
   <td> Refreshing OAuth access token due to error (HTTP: '%d').</td> 
   <td> <p>Actualización del token de acceso de OAuth debido a un error (HTTP: “401”).</p></td> 
  </tr>
  <tr> 
   <td> Error refreshing OAuth access token (error: '%d'). </td> 
   <td> <p>Error al actualizar el token de acceso de OAuth (error: “404”).</p></td> 
  </tr>
  <tr> 
   <td> Failed to fetch the OAuth access token using the specified external account on attempt %d, retrying in %d ms.</td> 
   <td> <p>No se pudo recuperar el token de acceso de OAuth usando la cuenta externa especificada en el intento 1, reintentando en 1387 ms.</p></td> 
  </tr>
 </tbody> 
</table>

### Errores

Estos mensajes de registro se utilizan para registrar información sobre las condiciones de error inesperadas, lo que puede provocar que la actividad del flujo de trabajo falle.

<table> 
 <thead> 
  <tr> 
   <th> Código: formato del mensaje<br /> </th> 
   <th> Ejemplo<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> WKF-560250 - API request body exceeded limit (limit: '%d').</td> 
   <td> <p>Se ha superado el límite del cuerpo de la solicitud de API (límite: “5242880”).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560239 -  API response exceeded limit (limit: '%d').</td> 
   <td> <p>Se ha superado el límite de respuesta de API (límite: “5242880”).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560245 - API URL could not be parsed (error: '%d').</td> 
   <td> <p>No se ha podido analizar la dirección URL de la API (error: “-2010”).</p>
   <p> Nota: Este error se registra cuando la dirección URL de la API falla en las reglas de validación.</p></td>
  </tr> 
  <tr>
   <td> WKF-560244 - API URL host must not be 'localhost', or IP address literal (URL host: '%s').</td> 
   <td> <p>El host de URL de API no debe ser “localhost” ni literal de dirección IP (host de URL: “localhost”).</p>
    <p>El host de URL de API no debe ser “localhost” ni literal de dirección IP (host de URL: “192.168.0.5”).</p>
    <p>El host de URL de API no debe ser “localhost” ni literal de dirección IP (host de URL: “[2001]”).</p></td>
  </tr> 
  <tr> 
   <td> WKF-560238 - API URL must be a secure URL (https) (requested URL: '%s').</td> 
   <td> <p>La dirección URL de API debe ser una dirección URL segura (https) (dirección URL solicitada: “https://example.com/api/v1/web-coupon?count=2”).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560249: error al crear el cuerpo de la solicitud JSON. Error when adding '%s'.</td> 
   <td> <p>No se ha podido crear el cuerpo de la solicitud JSON. Error al añadir “parámetros”.</p>
    <p>No se ha podido crear el cuerpo de la solicitud JSON. Error al añadir “datos”.</p></td>
  </tr> 
  <tr> 
   <td> WKF-560246 - HTTP header key is bad (header key: '%s').</td> 
   <td> <p>HTTP header key is bad (header key: '%s').</p>
   <p> Nota: Este error se registra cuando la clave de encabezado personalizada falla en la validación según <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a>.</p></td> 
  </tr>
 <tr> 
   <td> WKF-560248 - HTTP header key is not allowed (header key: '%s').</td> 
   <td> <p>No se permite la clave de encabezado HTTP (clave de encabezado: “Accept”).</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560247 - Un valor de encabezado HTTP no es correcto (valor de encabezado: '%s').</td> 
   <td> <p>El valor del encabezado HTTP es incorrecto (valor del encabezado: '%s'). </p>
    <p>Nota: Este error se registra cuando el valor del encabezado personalizado falla en la validación según <a href="https://tools.ietf.org/html/rfc7230#section-3.2.html">RFC</a>.</p></td> 
  </tr> 
  <tr> 
   <td> WKF-560240 - JSON payload has bad property '%s'.</td> 
   <td> <p>La carga de JSON tiene una propiedad “blah” incorrecta.</p></td>
  </tr> 
  <tr>
   <td> WKF-560241 - Malformed JSON or unacceptable format.</td> 
   <td> <p>Formato JSON no correcto o no compatible.</p>
   <p>Nota: Este mensaje solo se aplica al análisis del cuerpo de respuesta desde la API externa y se registra al intentar validar si el cuerpo de respuesta se ajusta al formato JSON establecido por esta actividad.</p></td>
  </tr>
  <tr> 
   <td> WKF-560246 - Activity failed (reason: '%s').</td> 
   <td> <p>Cuando falla la actividad debido a la respuesta de error HTTP 401: error de actividad (motivo: “HTTP - 401”)</p>
        <p>Cuando falla la actividad debido a una llamada interna fallida: error de actividad (motivo: “iRc - -Nn”).</p>
        <p>Cuando falla la actividad debido a un encabezado de Content-Type no válido: error de actividad (motivo: “Content-Type - application/html”).</p></td> 
  </tr>
  <tr> 
   <td> WKF-560278 - "Error initializing OAuth helper (error: '%d')" .</td> 
   <td> <p>Este error indica que la actividad no pudo inicializar la función de ayuda OAuth2.0 interna debido a un error al usar los atributos configurados en la cuenta externa para inicializar el asistente.</p></td>
  </tr>
  <tr> 
   <td> WKF-560279 - "HTTP header key is not allowed (header key: '%s')."</td> 
   <td> <p>Este mensaje de advertencia (no de error) indica que la cuenta externa OAuth 2.0 se ha configurado para agregar una credencial como un encabezado HTTP, pero la clave del encabezado utilizada no está permitida porque es una clave de encabezado reservada.</p></td>
  </tr>
  <tr> 
   <td> WKF-560280 - External account of '%s' ID cannot be found.</td> 
   <td> <p>No se encuentra la cuenta externa del identificador “EXT25”.  Nota: Este error indica que la actividad está configurada para utilizar una cuenta externa, que ya no se puede encontrar. Es muy probable que esto ocurra cuando la cuenta se elimina de la base de datos y, como tal, no es probable que ocurra en circunstancias normales de funcionamiento.</p></td>
  </tr>
  <tr> 
   <td> WKF-560281 - External account of '%s' ID is disabled.</td> 
   <td> <p>La cuenta externa del identificador “EXT25” está deshabilitada. Nota: Este error indica que la actividad está configurada para usar una cuenta externa, pero que esa cuenta se ha deshabilitado (o marcado como inactiva).</p></td>
  </tr>
  <tr> 
   <td> WKF-560282 - Protocol not supported.</td> 
   <td> <p>Este error indica que la cuenta externa asociada con la actividad no es una cuenta externa OAuth2.0. Como tal, es improbable que este error ocurra a menos que haya algún daño o cambios manuales en la configuración de la actividad.</p></td>
  </tr>
  <tr> 
   <td> WKF-560283 - Failed to fetch the OAuth access token.</td> 
   <td> <p>La causa más común de este error es la configuración incorrecta de la cuenta externa (por ejemplo, uso de la cuenta externa sin comprobar que la conexión se haya realizado correctamente). Es posible que se cambien las direcciones URL/credenciales de la cuenta externa.</p></td>
  </tr>
  <tr> 
   <td> CRL-290199 - Cannot reach page at: %s.</td> 
   <td> <p>Este mensaje de error se muestra en la pantalla de la interfaz de usuario de cuentas externas al configurarlo para OAuth. Significa que la dirección URL del servidor de autorización externo es incorrecta, está modificada o la respuesta del servidor es Página no encontrada.</p></td>
  </tr>
  <tr> 
   <td> CRL-290200 - Incomplete/Incorrect credentials.</td> 
   <td> <p>Este mensaje de error se muestra en la pantalla de la interfaz de usuario de cuentas externas al configurarlo para OAuth. Esto significa que las credenciales son incorrectas o que faltan otras credenciales necesarias para conectarse al servidor de autenticación.
</p></td>
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
