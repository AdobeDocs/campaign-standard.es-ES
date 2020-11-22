---
solution: Campaign Standard
product: campaign
title: Pasos principales para configurar un mensaje transaccional
description: Descubrir qué es la mensajería transaccional y conocer los pasos principales para configurar un mensaje transaccional en Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 28%

---


# Introducción a la mensajería transaccional {#getting-started-with-transactional-messaging}

## Información general

<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Introducción del concepto de mensajería **transaccional**

La mensajería transaccional le permite enviar mensajes individuales y únicos a sus clientes en tiempo real.

Pueden ser mensajes de bienvenida, confirmaciones de envío de pedidos, actualizaciones de contraseñas, etc.
Adobe Campaign le permite integrar esta funcionalidad con un sistema de información que envía eventos que se van a transformar en mensajes transaccionales personalizados.

Los mensajes transaccionales se pueden enviar por correo electrónico, por SMS o por notificaciones push, según las opciones que tenga. Compruebe el acuerdo de licencia.

Adobe Campaign prioriza los mensajes transaccionales de procesamiento sobre cualquier otro envío.

La mensajería transaccional también está disponible en la API de Adobe Campaign Standard. Para obtener más información, consulte [la documentación dedicada](../../api/using/managing-transactional-messages.md) .

>[!NOTE]
>
>Todos los mensajes transaccionales ahora se envían con el MTA mejorado de Adobe Campaign para mejorar la capacidad de entrega, el rendimiento y la gestión de devoluciones. Todos los impactos son los mismos que con los mensajes de marketing estándar. Para obtener más información, consulte esta [sección](../../administration/using/configuring-email-channel.md).

## Definición de mensajería transaccional {#transactional-messaging-definition}

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_concepts.svg" width="60px"><br><p><b>¿Qué es un mensaje transaccional?</b></p></td>
<td><p>Es una comunicación individual y única, enviada por un proveedor como un sitio web.</p></td>
<td><p>Se espera especialmente, porque contiene información importante que el destinatario desea comprobar o confirmar.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_channels.svg" width="60px"><br><p><b>¿Cuándo es debido?</b></p></td>
<td><p> Dado que este mensaje contiene información importante, el usuario espera que se envíe en tiempo real.</p></td>
<td><p>En consecuencia, el retraso entre el evento que se está activando y el mensaje que llega tiene que ser muy corto.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_important.svg" width="60px"><br><p><b>¿Por qué es importante?</b></p></td>
<td><p>Generalmente, un mensaje transaccional tiene altas tasas abiertas. Por lo tanto, debe diseñarse cuidadosamente.</p></td>
<td><p>De hecho, puede tener un fuerte impacto en el comportamiento de los clientes, ya que define la relación con ellos.</p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_example.svg" width="60px"><br><p><b>Por ejemplo?</b></p></td>
<td><p>Podría ser un mensaje de bienvenida después de crear una cuenta, una confirmación de envío de un pedido, una factura...</p></td>
<td><p>También puede ser un mensaje que confirme un cambio de contraseña o una notificación después de que un cliente haya explorado su sitio web...</p></td>
</tr>
</table>

## Tipos de mensaje transaccional

En Adobe Campaign, hay disponibles dos tipos de mensajes transaccionales:

<img src="assets/do-not-localize/icon_event.svg" width="60px">

Los [mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md) están dirigidos a un evento.

* Los mensajes transaccionales de evento no contienen información de perfil.

* No son compatibles con las reglas [de](../../sending/using/fatigue-rules.md) fatiga (incluso en el caso de un enriquecimiento con perfiles).

* El destinatario de envío se define por los datos contenidos en el propio evento.


<img src="assets/do-not-localize/icon_profile.svg" width="60px">

Los [mensajes transaccionales de perfil](../../channels/using/profile-transactional-messages.md) están dirigidos a perfiles de la base de datos de marketing de Campaign.

Con mensajes transaccionales de perfiles, puede:

* Apply [marketing typology rules](../../sending/using/managing-typology-rules.md) or [fatigue rules](../../sending/using/fatigue-rules.md)

* Incluir vínculos de baja en los mensajes.

* Añadir mensajes transaccionales al sistema de informes de envío global.

* Aprovechar mensajes transaccionales en el recorrido del cliente.

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje transaccional. Consulte [Configuración de mensajería transaccional](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

Veamos el ejemplo de una compañía que tiene un sitio web y en este sitio web sus clientes pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los usuarios del sitio que han agregado productos al carro de compras: cuando uno de ellos abandona el sitio sin comprar, se les envía automáticamente un correo electrónico de abandono del carro de compras.

Los pasos para poner esto en práctica son los siguientes.

### Paso 1: Creación y publicación de la configuración de evento {#create-event-configuration}

<img src="assets/do-not-localize/icon_config.svg" width="60px">

**Configuración** de evento transaccional:

* Configure un evento con el nombre &quot;Abandono del carro de compras&quot; y publique esta configuración de evento.

* Se implementa la API que utilizará el desarrollador de su sitio web y se crea automáticamente un mensaje transaccional.

* Tenga en cuenta que este paso debe realizarlo un usuario con derechos [de](../../administration/using/users-management.md#functional-administrators)administración.

La creación y publicación de un evento se presenta en la sección [Configuración de un evento para enviar un mensaje transaccional de evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Paso 2: Editar y publicar el mensaje transaccional {#create-transactional-message}

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

**Edición de mensaje transaccional**

* Edite y personalice el mensaje transaccional, pruébelo y, a continuación, publíquelo.

* El mensaje transaccional estará listo para ser enviado.

* Este paso lo puede llevar a cabo cualquier usuario de marketing con derechos [de acceso de usuario](../../administration/using/users-management.md#basic-users)estándar.

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Paso 3: Integración del activador de eventos {#integrate-event-trigger}

<img src="assets/do-not-localize/icon_api.svg" width="55px">

**Integración de activación de eventos**

* Utilice la API de Mensajes transaccionales REST para integrar el evento en su sitio web.&lt;

* El evento se activará cuando un cliente abandone el carro de compras.

* Este paso lo realiza el desarrollador del sitio web.

Para obtener más información sobre la integración del evento en el sitio web, consulte Integración [del sitio](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Paso 4 - envío de mensajes {#message-delivery}

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

**Evento externo procedente del sitio web**

* Una vez que se hayan realizado todos estos pasos, el mensaje se podrá entregar.

* Tan pronto como un usuario abandona el sitio sin ordenar los productos en su carro, se activa el evento de Campaña correspondiente.

* El usuario recibe automáticamente un correo electrónico de notificación.

## Pasos clave {#key-steps}

Los pasos principales para crear y administrar mensajes transaccionales personalizados en Adobe Campaign se resumen en el gráfico siguiente.

![](assets/message-center-overview.png)

## Temas relacionados

* [Pasos clave para enviar un mensaje](../../channels/using/key-steps-to-send-a-message.md)
* [Introducción a los canales de comunicación](../../channels/using/get-started-communication-channels.md)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->