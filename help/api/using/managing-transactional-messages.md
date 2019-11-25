---
title: Administración de mensajes transaccionales
description: Obtenga información sobre cómo administrar mensajes transaccionales con API.
page-status-flag: never-activated
uuid: c7b9c171-0409-4707-9d45-3fa72aee8008
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
discoiquuid: 304e7779-42d2-430a-9704-8c599a4eb1da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c0c0be79613f99a15676343d8ce10d335baf968a

---


# Administración de mensajes transaccionales {#managing-transactional-messages}

## Acerca de la mensajería transaccional

Una vez creado un evento, deberá integrar la activación de este evento en su sitio Web.

>[!NOTE]
>
>La creación y publicación de un evento se presenta en <a href="https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html">la documentación</a>de la campaña.

Por ejemplo: desea que se active un evento de "abandono del carro de compras" cada vez que uno de sus clientes abandone el sitio Web antes de comprar los productos en el carro de compras. Para ello, el desarrollador web debe utilizar la API de mensajes transaccionales REST.

1. El programador envía una solicitud según el método POST, que activa el [envío del evento](#sending-a-transactional-event)transaccional.
1. La respuesta a la solicitud POST contiene una clave principal, que permite al programador enviar una o varias solicitudes a través de una solicitud GET. De esta manera, puede obtener el estado [del](#transactional-event-status)evento.

## Envío de un evento transaccional {#sending-a-transactional-event}

El evento transaccional se envía a través de una solicitud POST con la siguiente estructura URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;ORGANIZACIÓN&gt;**: su ID de organización personal. Consulte [esta sección](../../api/using/must-read.md).

* **&lt;transactionAPI&gt;**: los extremos de la API de Mensajes transaccionales.

   El nombre del extremo de la API de mensajes transaccionales depende de la configuración de la instancia. Corresponde al valor "mc" seguido de su ID de organización personal. Veamos el ejemplo de la empresa Geometrixx, con "geometrixx" como ID de organización. En ese caso, la solicitud POST sería la siguiente:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Tenga en cuenta que el extremo de la API de mensajes transaccionales también está visible durante la vista previa de la API)

* **&lt;eventID&gt;**: el tipo de evento que desea enviar. Este ID se genera al crear la definición del evento. Consulte la documentación [de](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)Campaña.

### Encabezado de solicitud POST

La solicitud debe contener un "Content-Type: application/json".

Debe agregar un charset, por ejemplo **utf-8**. Tenga en cuenta que este valor depende de la aplicación REST que utilice.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### Cuerpo de solicitud POST

Los datos del evento están contenidos dentro del cuerpo de JSON POST. La estructura del evento depende de su definición. El botón de vista previa de la API en la pantalla de definición de recursos proporciona un ejemplo de solicitud. Consulte la documentación [de](https://helpx.adobe.com/campaign/standard/administration/using/configuring-transactional-messaging.html)Campaña.

Se pueden agregar los siguientes parámetros opcionales al contenido del evento para administrar el envío de mensajes transaccionales vinculados al evento:

* **caducidad** (opcional): después de esta fecha, se cancelará el envío del evento transaccional.
* **programado** (opcional): a partir de esta fecha, se procesará el evento transaccional y se enviará el mensaje transaccional.

>[!NOTE]
>
>Los valores de los parámetros "expiration" y "schedule" siguen el formato ISO 8601. ISO 8601 especifica el uso de la letra mayúscula "T" para separar la fecha y la hora. Sin embargo, se puede eliminar de la entrada o salida para mejorar la legibilidad.

### Respuesta a la solicitud POST

La respuesta POST devuelve el estado del evento transaccional en el momento en que se creó. Para recuperar el estado actual (datos del evento, estado del evento...), utilice la clave principal devuelta por la respuesta POST en una solicitud GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Solicitud de muestra***

Solicitud POST para enviar el evento.

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

Respuesta a la solicitud POST.

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

### Estado del evento transaccional {#transactional-event-status}

En la respuesta, el campo "status" le permite saber si el evento se ha procesado o no:

* **pendiente**: el evento está pendiente; el evento toma este estado cuando se acaba de activar.
* **procesando**: el evento está pendiente de entrega; se está transformando en un mensaje y se está enviando el mensaje.
* **pausado**: el proceso del evento se está pausando. Ya no se procesa, sino que se mantiene en cola en la base de datos de Adobe Campaign. For more on this, refer to the [Campaign documentation](https://helpx.adobe.com/campaign/standard/channels/using/event-transactional-messages.html#unpublishing-a-transactional-message).
* **procesado**: el evento se procesó y el mensaje se envió correctamente.
* **ignorado**: la entrega ignoró el evento, normalmente cuando una dirección está en cuarentena.
* **deliveryFailed**: se produjo un error de entrega mientras se procesaba el evento.
* **RoutingFailed**: error en la fase de enrutamiento: esto puede ocurrir, por ejemplo, cuando no se encuentra el tipo de evento especificado.
* **tooOld**: el evento caducó antes de que se pudiera procesar; esto puede suceder por varios motivos, por ejemplo, cuando un envío falla varias veces (esto resulta en que el evento ya no se actualiza) o cuando el servidor ya no puede procesar eventos después de sobrecargarse.
* **targetingFailed**: Campaign Standard no pudo enriquecer un vínculo que se está utilizando para la segmentación de mensajes.
