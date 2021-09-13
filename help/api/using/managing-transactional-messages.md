---
title: Administración de mensajes transaccionales
description: Obtenga información sobre cómo administrar mensajes transaccionales con API.
audience: developing
content-type: reference
topic-tags: campaign-standard-apis
feature: API
role: Data Engineer
level: Experienced
exl-id: 00d39438-a232-49f1-ae5e-1e98c73397e3
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 3%

---

# Administración de mensajes transaccionales {#managing-transactional-messages}

## Acerca de la mensajería transaccional

Una vez creado y publicado un evento transaccional, debe integrar el activador de este evento en el sitio web.

>[!NOTE]
>
>La configuración de un evento se presenta en [esta sección](../../channels/using/configuring-transactional-event.md).

Por ejemplo, desea que se active un evento de &quot;Abandono del carro de compras&quot; cada vez que uno de los clientes abandone el sitio web antes de comprar los productos del carro de compras. Para ello, el desarrollador web debe utilizar la API de mensajes transaccionales de REST.

1. El desarrollador envía una solicitud según el método del POST, que déclencheur el [envío del evento transaccional](#sending-a-transactional-event).
1. La respuesta a la solicitud del POST contiene una clave principal, que permite al desarrollador enviar una o varias solicitudes a través de una solicitud de GET. De esta forma, puede obtener el estado del evento [](#transactional-event-status).

## Envío de un evento transaccional {#sending-a-transactional-event}

El evento transaccional se envía mediante una solicitud de POST con la siguiente estructura de URL:

```
POST https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>
```

* **&lt;organization>**: su ID de organización personal. Consulte [esta sección](../../api/using/must-read.md).

* **&lt;transactionalapi>**: los extremos de la API de mensajes transaccionales.

   El nombre del extremo de la API de mensajes transaccionales depende de la configuración de la instancia. Corresponde al valor &quot;mc&quot; seguido de su ID de organización personal. Veamos el ejemplo de la empresa de Geometrixx, con &quot;geometrixx&quot; como ID de organización. En ese caso, la solicitud del POST sería la siguiente:

   `POST https://mc.adobe.io/geometrixx/campaign/mcgeometrixx/<eventID>`

   (Tenga en cuenta que el extremo de la API de mensajes transaccionales también está visible durante la vista previa de la API)

* **&lt;eventid>**: el tipo de evento que desea enviar. Este ID se genera al crear la configuración de evento (consulte [esta sección](../../channels/using/configuring-transactional-event.md#creating-an-event)).

### encabezado de solicitud del POST

La solicitud debe contener un &quot;Content-Type: application/json&quot; .

Debe agregar un conjunto de caracteres, por ejemplo **utf-8**. Tenga en cuenta que este valor depende de la aplicación REST que utilice.

```
-X POST \
-H 'Authorization: Bearer <ACCESS_TOKEN>' \
-H 'Cache-Control: no-cache' \
-H 'X-Api-Key: <API_KEY>' \
-H 'Content-Type: application/json;charset=utf-8' \
-H 'Content-Length:79' \
```

### cuerpo de solicitud del POST

Los datos del evento están contenidos dentro del cuerpo del POST JSON. La estructura del evento depende de su definición. El botón Vista previa de API de la pantalla de definición del recurso proporciona una muestra de solicitud. Consulte [esta sección](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

Se pueden añadir los siguientes parámetros opcionales al contenido del evento para administrar el envío de mensajes transaccionales vinculados al evento:

* **caducidad**  (opcional): después de esta fecha, se cancela el envío del evento transaccional.
* **scheduled**  (opcional): a partir de esta fecha, el evento transaccional se procesa y se envía el mensaje transaccional.

>[!NOTE]
>
>Los valores de los parámetros &quot;expiration&quot; y &quot;scheduled&quot; siguen el formato ISO 8601. ISO 8601 especifica el uso de la letra en mayúsculas &quot;T&quot; para separar la fecha y la hora. Sin embargo, se puede eliminar de la entrada o salida para mejorar la legibilidad.

### Respuesta a la solicitud del POST

La respuesta del POST devuelve el estado del evento transaccional en el momento en que se creó. Para recuperar su estado actual (datos de evento, estado de evento...), utilice la clave principal devuelta por la respuesta del POST en una solicitud de GET:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/<transactionalAPI>/<eventID>/`

<br/>

***Solicitud de ejemplo***

solicitud del POST para enviar el evento.

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

### Estado del evento transaccional {#transactional-event-status}

En la respuesta, el campo &quot;status&quot; permite saber si el evento se ha procesado o no:

* **pendiente**: el evento está pendiente : el evento toma este estado cuando acaba de activarse.
* **procesamiento**: el evento está pendiente de envío: se está transformando en un mensaje y este se está enviando.
* **en pausa**: el proceso de eventos se está pausando. Ya no se procesa, pero se mantiene en cola en la base de datos de Adobe Campaign. Para obtener más información, consulte [esta sección](../../channels/using/publishing-transactional-message.md#suspending-a-transactional-message-publication).
* **procesado**: el evento se procesó y el mensaje se envió correctamente.
* **ignorado**: el envío ignoró el evento, normalmente cuando una dirección está en cuarentena.
* **deliveryFailed**: se produjo un error de entrega mientras se procesaba el evento.
* **routingFailed**: error en la fase de enrutamiento: esto puede ocurrir, por ejemplo, cuando no se encuentra el tipo de evento especificado.
* **tooOld**: el evento caducó antes de poder procesarse; esto puede ocurrir por varios motivos, por ejemplo, cuando una entrega falla varias veces (lo que provoca que el evento ya no esté actualizado) o cuando el servidor ya no puede procesar eventos después de sobrecargarse.
* **targetingFailed**: Campaign Standard no pudo enriquecer un vínculo que se está utilizando para la segmentación de mensajes.
