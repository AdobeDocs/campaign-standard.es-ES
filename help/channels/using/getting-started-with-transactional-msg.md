---
solution: Campaign Standard
product: campaign
title: Pasos principales para configurar un mensaje transaccional
description: Descubrir qué es la mensajería transaccional y conocer los pasos principales para configurar un mensaje transaccional en Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
translation-type: tm+mt
source-git-commit: c276c468627208b584a0342414cdbe382e349f50
workflow-type: tm+mt
source-wordcount: '966'
ht-degree: 9%

---


# Introducción a la mensajería transaccional {#getting-started-with-transactional-messaging}

## Información general {#overview}

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Un mensaje transaccional es una comunicación individual y única, enviada en tiempo real por un proveedor como un sitio web. Se espera especialmente, porque contiene información importante que el destinatario desea comprobar o confirmar.

* **¿Cuándo es debido?** Dado que este mensaje contiene información importante, el usuario espera que se envíe en tiempo real. En consecuencia, el retraso entre el evento que se está activando y el mensaje que llega tiene que ser muy corto.

* **¿Por qué es importante?** Generalmente, un mensaje transaccional tiene altas tasas abiertas. Por lo tanto, debe diseñarse cuidadosamente, ya que puede tener un fuerte impacto en el comportamiento de los clientes, ya que define la relación con los clientes.

* **Por ejemplo?** Podría ser un mensaje de bienvenida después de crear una cuenta, una confirmación de envío de un pedido, una factura, un mensaje que confirme un cambio de contraseña, o una notificación después de que un cliente haya navegado por su sitio web, etc.

Adobe Campaign le permite integrar esta funcionalidad con un sistema de información que envía eventos que se van a transformar en mensajes transaccionales personalizados.

Las mensajes transaccionales se pueden enviar por correo electrónico, SMS o [notificación push](../../channels/using/transactional-push-notifications.md), según las opciones. Compruebe el acuerdo de licencia.

>[!NOTE]
>
>Adobe Campaign prioriza los mensajes transaccionales de procesamiento sobre cualquier otro envío.

<!--Guidelines to implement transactional messaging capabilities in your website are detailed in [this section](../../api/using/managing-transactional-messages.md).-->

<!--All transactional messages are now sent with the Adobe Campaign Enhanced MTA for improved deliverability, throughput, and bounce handling. All impacts are the same as for standard marketing messages. For more on this, see [this section](../../administration/using/configuring-email-channel.md).-->

Antes de comenzar con los mensajes transaccionales, asegúrese de leer las [prácticas recomendadas y limitaciones](../../channels/using/transactional-messaging-limitations.md) correspondientes.

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

El proceso general de mensajería transaccional se puede describir de la siguiente manera:

![](assets/message-center-process.png)

Por ejemplo, imagine que es una compañía con un sitio web en el que sus clientes pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los clientes que han agregado productos al carro de compras. Cuando uno de ellos abandona el sitio web sin pasar por sus compras (eventos externos que activan un evento de Campaña), se les envía automáticamente un correo electrónico de abandono del carro de compras (envío de mensaje transaccional).

Los principales pasos para ponerlo en marcha se detallan a continuación en [esta sección](#key-steps).

## Tipos de mensaje transaccional {#transactional-message-types}

En Adobe Campaign, hay disponibles dos tipos de mensajes transaccionales.

**Evento transactional** messagesttarget datos contenidos en el propio evento. Estos mensajes:
* No contenga información de perfil y, por lo tanto, no pueda incluir vínculos bajas.
* No son compatibles con las reglas de fatiga (incluso en el caso de un enriquecimiento con perfiles).
* Tener su destinatario de envío definido por los datos contenidos en el propio evento.

Puede que desee enviar un mensaje transaccional de evento a un cliente que necesite recuperar una contraseña olvidada, por ejemplo, o para confirmar un pedido. De hecho, no desea que su destinatario cancele la suscripción a este tipo de comunicaciones, y esta notificación no debe agregarse al contador de mensajes de marketing como parte de una regla de fatiga.

**Perfiles de** destino de transacciones de perfil de la base de datos de marketing de Campaña. Con este tipo de mensajes, puede:
* Aproveche los datos contenidos en la base de datos de Adobe Campaign.
* Personalice su mensaje con información de perfil agregando un [enriquecimiento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) a la configuración de evento.
* Aplicar [reglas de tipología de marketing](../../sending/using/managing-typology-rules.md) o [reglas de fatiga](../../sending/using/fatigue-rules.md).
* Incluir vínculos de baja en los mensajes.
* Añadir mensajes transaccionales al sistema de informes de envío global.
* Aprovechar mensajes transaccionales en el recorrido del cliente.

Por ejemplo, puede utilizar este tipo de mensajes cuando se ponga en contacto con sus clientes después de que abandonen el carro en su sitio web, para alentarlos a continuar con la compra. Al hacer esto, puede personalizar su mensaje con mayor facilidad gracias al acceso directo a toda la información de la base de datos de perfil, aplicar reglas de marketing e incluir este mensaje en el sistema de informes y el viaje del cliente global para obtener una mejor vista del comportamiento del cliente.

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje transaccional. Consulte las secciones de configuración [mensajes transaccionales basados en Evento](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages) y [mensajes transaccionales basados en Perfil](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages).

## Pasos clave {#key-steps}

Los pasos principales para crear y administrar mensajes transaccionales personalizados en Adobe Campaign se resumen en el esquema siguiente.

![](assets/message-center-overview.png)

A continuación se detalla cada una de estas medidas.

>[!IMPORTANT]
>
>Solo los usuarios con la función [Administración](../../administration/using/users-management.md#functional-administrators) pueden configurar eventos transaccionales y mensajes transaccionales de acceso.

### Paso 1: Crear y publicar la configuración de evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

| Usuario | Acción | Resultado |
|--- |--- |--- |
| Este paso debe realizarlo un administrador que tenga [derechos de administración](../../administration/using/users-management.md#functional-administrators). | Configure un evento con el nombre &quot;Abandono del carro de compras&quot; y publique esta configuración de evento. | Se implementa la API que utilizará el desarrollador de su sitio web y se crea automáticamente un mensaje transaccional. |

La creación y publicación de un evento se presenta en las secciones [Configuración de un evento transaccional](../../channels/using/configuring-transactional-event.md) y [Publicación de un evento transaccional](../../channels/using/publishing-transactional-event.md).

### Paso 2: Editar y publicar el mensaje transaccional {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

| Usuario | Acción | Resultado |
|--- |--- |--- |
| Este paso lo puede llevar a cabo un usuario de mercadotecnia que tenga [derechos de administración](../../administration/using/users-management.md#functional-administrators). | Edite y personalice el mensaje transaccional, pruébelo y, a continuación, publíquelo. | El mensaje transaccional está listo para ser enviado. |

Para obtener más información sobre la edición y publicación de un mensaje transaccional, consulte [Edición de mensajes transaccionales](../../channels/using/editing-transactional-message.md) y [Ciclo de vida de Mensaje transaccional](../../channels/using/publishing-transactional-message.md).

### Paso 3: Integración del activador de eventos {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

<!--**Event triggering integration**-->

| Usuario | Acción | Resultado |
|--- |--- |--- |
| Este paso lo realiza el desarrollador del sitio web. | Utilice la API de Mensajes transaccionales REST para integrar el evento en su sitio web. | El evento se activará cuando un cliente abandone el carro de compras. |

Una vez creado un evento, debe integrar el activador de este evento en el sitio web.<!--In this example, you want a "Cart abandonment" event to be triggered whenever one of your clients leaves your website before purchasing the products in their cart.--> Para ello, el desarrollador web de su sitio web debe utilizar la API **REST de** Adobe Campaign Standard.

Para obtener más información sobre el uso de la API de Campaña REST para administrar mensajes transaccionales, consulte la [documentación de la API de REST](../../api/using/managing-transactional-messages.md).

### Paso 4 - envío de mensajes {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

Una vez que se hayan realizado todos estos pasos, el mensaje se podrá entregar.

Tan pronto como un usuario abandona el sitio sin ordenar los productos en su carro, se activa el evento de Campaña correspondiente. El usuario recibe automáticamente un correo electrónico de notificación.

## Temas relacionados

* [Pasos clave para enviar un mensaje](../../channels/using/key-steps-to-send-a-message.md)
* [Introducción a los canales de comunicación](../../channels/using/get-started-communication-channels.md)
* [Notificaciones push transaccionales](../../channels/using/transactional-push-notifications.md)
* [Mensajes de seguimiento](../../channels/using/follow-up-messages.md)
