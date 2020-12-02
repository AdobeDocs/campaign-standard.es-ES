---
solution: Campaign Standard
product: campaign
title: Administración de mensajes transaccionales
description: Obtenga información sobre cómo administrar mensajes transaccionales con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 1%

---


# Administración de mensajes transaccionales {#managing-transactional-messages}

## Acerca de la mensajería transaccional

Una vez que haya creado un evento, deberá integrar el activador de este evento en su sitio web.

>[!NOTE]
>
>La creación y publicación de un evento se presenta en [la documentación de la Campaña](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Por ejemplo: desea que se active un evento de &quot;abandono del carro de compras&quot; cada vez que uno de sus clientes abandone el sitio web antes de comprar los productos en el carro de compras. Para ello, el desarrollador web debe utilizar la API de Mensajes transaccionales REST.

1. El programador envía una solicitud según el método POST, que activa el [envío del evento transaccional](#sending-a-transactional-event).
1. La respuesta a la solicitud del POST contiene una clave principal, que permite al programador enviar una o varias solicitudes a través de una solicitud de GET. De este modo, puede obtener el [estado de evento](#transactional-event-status).

## Envío de un evento transaccional {#sending-a-transactional-event}

El evento transaccional se envía a través de una solicitud de POST con la siguiente estructura URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**:: su ID de organización personal. Consulte [esta sección](../../api/using/must-read.md).

* **&lt;transactionalapi>**:: endPoints de la API de Mensajes transaccionales.

   El nombre del extremo de la API de Mensajes transaccionales depende de la configuración de la instancia. Corresponde al valor &quot;mc&quot; seguido de su ID de organización personal. Veamos el ejemplo de la compañía de Geometrixx, con &quot;geometrixx&quot; como ID de organización. En ese caso, la solicitud del POST sería la siguiente:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Tenga en cuenta que el extremo de la API de mensajes transaccionales también está visible durante la previsualización de la API)

* **&lt;eventid>**:: el tipo de evento que desea enviar. Este ID se genera al crear la definición de evento. Consulte la [documentación de Campaña](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

### Encabezado de solicitud de POST

La solicitud debe contener un &quot;Content-Type: application/json&quot;.

Debe agregar un charset, por ejemplo **utf-8**. Tenga en cuenta que este valor depende de la aplicación REST que utilice.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### Cuerpo de solicitud de POST

Los datos de evento están contenidos dentro del cuerpo del POST JSON. La estructura del evento depende de su definición. El botón previsualización de API de la pantalla de definición de recursos proporciona un ejemplo de solicitud. Consulte la [documentación de Campaña](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html).

Se pueden añadir los siguientes parámetros opcionales al contenido de evento para gestionar el envío de mensajes transaccionales vinculados al evento:

* **expiration** (opcional): después de esta fecha, se cancelará el envío del evento de transacción.
* **programado**  (opcional): a partir de esta fecha, se procesará el evento de transacción y se enviará el mensaje transaccional.

>[!NOTE]
>
>Los valores de los parámetros &quot;expiration&quot; y &quot;schedule&quot; siguen el formato ISO 8601. ISO 8601 especifica el uso de la letra mayúscula &quot;T&quot; para separar la fecha y la hora. Sin embargo, se puede eliminar de la entrada o salida para mejorar la legibilidad.

### Respuesta a la solicitud del POST

La respuesta del POST devuelve el estado del evento de transacción en el momento en que se creó. Para recuperar su estado actual (datos de evento, estado de evento...), utilice la clave principal devuelta por la respuesta del POST en una solicitud de GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Solicitud de muestra***

Solicitud del POST para enviar el evento.

```
-X POST https://mc.adobe.io/<ORGANIZATION>/campaign/mcAdobe/EVTcartAbandonment \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79'

{
  "email":"test@example.com",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "ctx":
  {
    "cartAmount": "$ 125",
    "lastProduct": "Leather motorbike jacket",
    "firstName": "Jack"
  }
}
```

Respuesta a la solicitud del POST.

```
{
  "PKey":"<PKEY>",
  "ctx":
  {
    "cartAmount": "",
    "lastProduct": "",
    "firstName": ""
  }
  "email":"",
  "scheduled":"2017-12-01 08:00:00.768Z",
  "expiration":"2017-12-31 08:00:00.768Z",
  "href": "mcAdobe/EVTcartAbandonment/<PKEY>",
  "serverUrl":" https://myserver.com ",
  "status":"pending",
  "type":""
}
```

### Estado de evento transaccional {#transactional-event-status}

En la respuesta, el campo &quot;estado&quot; permite saber si el evento se ha procesado o no:

* **pendiente**: el evento está pendiente - el evento toma este estado cuando se acaba de activar.
* **procesando**: el evento está pendiente de envío - se está transformando en un mensaje y el mensaje se está enviando.
* **pausado**: el proceso de evento se está pausando. Ya no se procesa, sino que se mantiene en cola en la base de datos de Adobe Campaign. Para obtener más información sobre esto, consulte la [documentación de Campaña](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **procesado**: el evento se procesó y el mensaje se envió correctamente.
* **ignorado**: el envío ignoró el evento, normalmente cuando una dirección está en cuarentena.
* **deliveryFailed**: se produjo un error de envío mientras se procesaba el evento.
* **RoutingFailed**: error en la fase de enrutamiento: esto puede ocurrir, por ejemplo, cuando no se encuentra el tipo de evento especificado.
* **tooOld**: el evento caducó antes de que se pudiera procesar; esto puede suceder por varios motivos, por ejemplo, cuando un envío falla varias veces (lo que hace que el evento ya no esté actualizado) o cuando el servidor ya no puede procesar eventos después de sobrecargarse.
* **targetingFailed**: Campaign Standard no pudo enriquecer un vínculo que se está utilizando para la segmentación de mensajes.
