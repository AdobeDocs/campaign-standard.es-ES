---
title: Introducción a la mensajería transaccional
description: Descubra qué es la mensajería transaccional y aprenda los pasos principales para configurar un mensaje transaccional en Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Beginner
exl-id: 49fba1af-3c99-45b7-bcbb-b9b9678eedcd
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '963'
ht-degree: 31%

---

# Introducción a la mensajería transaccional {#getting-started-with-transactional-messaging}

## Información general {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Un mensaje transaccional es una comunicación individual y única que un proveedor, como un sitio web, envía en tiempo real. Se espera especialmente, ya que contiene información importante que el destinatario desea comprobar o confirmar.

* **¿Cuándo se espera?** Dado que este mensaje contiene información importante, el usuario espera que se envíe en tiempo real. Por lo tanto, el retraso entre el evento que se está activando y el mensaje que llega tiene que ser muy corto.

* **¿Por qué es importante?** Generalmente, un mensaje transaccional tiene altas tasas de apertura. Por lo tanto, debe diseñarse cuidadosamente, ya que puede tener un fuerte impacto en el comportamiento de los clientes, ya que define la relación con ellos.

* **¿Por ejemplo?** Podría ser un mensaje de bienvenida después de crear una cuenta, una confirmación de envío de un pedido, una factura, un mensaje que confirme un cambio de contraseña, o una notificación después de que un cliente navegue por su sitio web, etc.

Adobe Campaign le permite integrar esta funcionalidad con un sistema de información que envía eventos que se van a transformar en mensajes transaccionales personalizados.

Los mensajes transaccionales se pueden enviar por correo electrónico, SMS o [push notification](../../channels/using/transactional-push-notifications.md), según las opciones que tenga. Compruebe el acuerdo de licencia.

>[!NOTE]
>
>Adobe Campaign prioriza el procesamiento de los mensajes transaccionales sobre cualquier otra entrega.

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

Antes de empezar con la mensajería transaccional, asegúrese de leer las [prácticas recomendadas y limitaciones](../../channels/using/transactional-messaging-limitations.md) correspondientes.

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

El proceso general de mensajería transaccional se puede describir de la siguiente manera:

![](assets/message-center-process.png)

Por ejemplo, imaginemos que es una compañía con un sitio web en el que los clientes pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los clientes que han añadido productos al carro de compras. Cuando uno de ellos abandona el sitio web sin finalizar sus compras (evento externo que activa un evento de Campaign), se les envía automáticamente un correo electrónico de abandono del carro de compras (entrega de mensaje transaccional).

Los pasos principales para ponerlo en práctica se detallan a continuación en [esta sección](#key-steps).

## Tipos de mensajes transaccionales {#transactional-message-types}

En Adobe Campaign, hay disponibles dos tipos de mensajes transaccionales.

**El** mensaje transaccional del evento está dirigido a los datos contenidos en el propio evento. Estos mensajes:
* No contenga información de perfil y, por lo tanto, no pueda incluir vínculos de baja.
* no son compatibles con las reglas de fatiga (incluso en el caso de un enriquecimiento con perfiles).
* Haga que el objetivo de su envío esté definido por los datos contenidos en el propio evento.

Puede que desee enviar un mensaje transaccional de evento a un cliente que necesite recuperar una contraseña olvidada, por ejemplo, o confirmar un pedido. De hecho, no desea que su destinatario cancele la suscripción a este tipo de comunicaciones y esta notificación no debe añadirse al contador de mensajes de marketing como parte de una regla de fatiga.

**Perfil,** mensajes transaccionales, perfiles de destino de la base de datos de marketing de Campaign. Con este tipo de mensajes, puede:
* Aproveche los datos contenidos en la base de datos de Adobe Campaign.
* Personalice el mensaje con información de perfil agregando un [enriquecimiento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) a la configuración de evento.
* Aplicar [reglas de tipología de marketing](../../sending/using/managing-typology-rules.md) o [reglas de fatiga](../../sending/using/fatigue-rules.md).
* Incluir vínculos de baja en los mensajes.
* Añadir mensajes transaccionales al sistema de informes de envío global.
* Aprovechar mensajes transaccionales en el recorrido del cliente.

Por ejemplo, puede utilizar este tipo de mensajes al ponerse en contacto con los clientes después de que abandonen el carro de compras en el sitio web, para animarlos a continuar con la compra. De este modo, puede personalizar más fácilmente su mensaje con acceso directo a toda la información de su base de datos de perfiles, aplicar reglas de marketing e incluir este mensaje en el recorrido de clientes global y en los informes para obtener una mejor vista del comportamiento de sus clientes.

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje transaccional. Consulte las secciones de configuración [Mensajes transaccionales basados en eventos](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) y [Mensajes transaccionales basados en perfiles](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

## Pasos clave {#key-steps}

Los pasos principales para crear y administrar mensajes transaccionales personalizados en Adobe Campaign se resumen en el esquema siguiente.

![](assets/message-center-overview.png)

Cada uno de estos pasos se detalla a continuación.

>[!IMPORTANT]
>
>Solo los usuarios con la función [Administration](../../administration/using/users-management.md#functional-administrators) pueden configurar eventos transaccionales y acceder a mensajes transaccionales.

### Paso 1: Creación y publicación de la configuración de evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Usuario | Acción | Resultado |
|--- |--- |--- |
| Este paso debe realizarlo un administrador que mantenga [derechos de administración](../../administration/using/users-management.md#functional-administrators). | Configure un evento con el nombre &quot;Abandono del carro de compras&quot; y publique esta configuración de evento. | El desarrollador del sitio web implementa la API que utilizará y se crea automáticamente un mensaje transaccional. |

La creación y publicación de un evento se presenta en las secciones [Configuración de un evento transaccional](../../channels/using/configuring-transactional-event.md) y [Publicación de un evento transaccional](../../channels/using/publishing-transactional-event.md).

### Paso 2: Editar y publicar el mensaje transaccional {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Usuario | Acción | Resultado |
|--- |--- |--- |
| Este paso lo puede llevar a cabo un usuario de marketing que mantenga [derechos de administración](../../administration/using/users-management.md#functional-administrators). | Edite y personalice el mensaje transaccional, pruébelo y, a continuación, publíquelo. | El mensaje transaccional está listo para enviarse. |

Para obtener más información sobre la edición y publicación de un mensaje transaccional, consulte [Edición de mensajes transaccionales](../../channels/using/editing-transactional-message.md) y [Ciclo de vida de mensajes transaccionales](../../channels/using/publishing-transactional-message.md).

### Paso 3: Integración del activador de eventos {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| Usuario | Acción | Resultado |
|--- |--- |--- |
| Este paso lo realiza el desarrollador del sitio web. | Utilice la API de mensajes transaccionales de REST para integrar el evento en su sitio web. | El evento se activará cuando un cliente abandone el carro de compras. |

Una vez creado un evento, debe integrar el activador de este evento en el sitio web.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> Para ello, el desarrollador web del sitio web debe utilizar la API de REST de  **Adobe Campaign Standard**.

Para obtener más información sobre el uso de la API de REST de Campaign para administrar mensajes transaccionales, consulte la [documentación de la API de REST](../../api/using/managing-transactional-messages.md).

### Paso 4: Envío de mensajes {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Una vez realizados todos estos pasos, se puede enviar el mensaje.

Tan pronto como un usuario abandona el sitio sin ordenar los productos en el carro de compras, se activa el evento de Campaign correspondiente. El usuario recibe automáticamente un correo electrónico de notificación.

## Temas relacionados

* [Pasos clave para enviar un mensaje](../../channels/using/key-steps-to-send-a-message.md)
* [Introducción a los canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Notificaciones push transaccionales](../../channels/using/transactional-push-notifications.md)
* [Mensajes de seguimiento](../../channels/using/follow-up-messages.md)
