---
title: Pasos principales para configurar un mensaje transaccional
description: Descubrir qué es la mensajería transaccional y conocer los pasos principales para configurar un mensaje transaccional en Adobe Campaign Standard.
page-status-flag: never-activated
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 07adae5bac947df794520e48361fd3c20eba5ff8
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 30%

---


# Introducción a la mensajería transaccional {#getting-started-with-transactional-messaging}

## Información general


<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

<table>
<tr>
<td ><br><p>La mensajería transaccional le permite <b>enviar mensajes</b> individuales y únicos a sus clientes en tiempo real.</p></td>
<td>Pueden ser mensajes de bienvenida, confirmaciones de envío de pedidos, modificación de contraseña, etc.</td>
</tr>
</table>

Adobe Campaign le permite integrar esta funcionalidad con un sistema de información que envía eventos que se van a transformar en mensajes transaccionales personalizados.

>[!NOTE]
>
>Los mensajes transaccionales se pueden enviar por correo electrónico, por SMS o por notificaciones push, según las opciones que tenga. Compruebe el acuerdo de licencia.

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

<!--[Event transactional messages](../../channels/using/event-transactional-messages.md) targeting an **event**. The data contained in the event itself is used to define the delivery target.-->

<table>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_event.svg" width="60px"><br><p>Los <a href="../../channels/using/event-transactional-messages.md">mensajes transaccionales de eventos</a><br><b> están dirigidos a un evento</b></p></td>
<td><p><ul><li>No contienen información de perfil.</li><li>No son compatibles con las reglas <a href="../../sending/using/fatigue-rules.md">de</a> fatiga (incluso en el caso de un enriquecimiento con perfiles).</li><li>El destinatario de envío se define por los datos contenidos en el propio evento.</li></ul></p></td>
</tr>
<tr>
<td align="center"><img src="assets/do-not-localize/icon_profile.svg" width="60px"><br><p>Los <a href="../../channels/using/profile-transactional-messages.md">mensajes transaccionales de perfil</a><br><b> están dirigidos a perfiles de la base de datos de marketing de Adobe Campaign</b></p></td>
<td><p>Los mensajes transaccionales de perfil permiten:<ul><li>Aplicar reglas de tipología de marketing como <b>Dirección en las reglas de lista de bloqueados</b> o <a href="../../sending/using/fatigue-rules.md">fatiga</a>.</li><li>Incluir vínculos de baja en los mensajes.</li><li>Añadir mensajes transaccionales al sistema de informes de envío global.</li><li>Aprovechar mensajes transaccionales en el recorrido del cliente.</li></ul></p></td>
</tr>
</table>

<!--[Profile transactional messages](../../channels/using/profile-transactional-messages.md) targeting **profiles from the Adobe Campaign marketing database**. You can use information from the Adobe Campaign database to send a transactional message based on customer marketing profiles.-->

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje transaccional. Consulte [Configuración de mensajería transaccional](../../administration/using/configuring-transactional-messaging.md).

>[!IMPORTANT]
>
>To access all transactional messages, you must be part of the **[!UICONTROL Administrators (all units)]** security group.

<!--Event transactional messages do not contain profile information, therefore they are not compatible with fatigue rules (even in the case of an enrichment with profiles). However, profile transactional messages are compatible. For more on fatigue rules, see [this section](../../sending/using/fatigue-rules.md#choosing-the-channel).-->

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

Veamos el ejemplo de una compañía que tiene un sitio web y en este sitio web sus clientes pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los usuarios del sitio que han agregado productos al carro de compras: cuando uno de ellos abandona el sitio sin comprar, se les envía automáticamente un correo electrónico de abandono del carro de compras.

Los pasos para poner esto en práctica son los siguientes.

### Paso 1: Creación y publicación de la configuración de evento {#create-event-configuration}

<!--<img src="assets/do-not-localize/icon_config.svg" width="60px">

Configure an event that will be named "Cart abandonment" and publish this event configuration.

The API that will be used by your website developer is deployed and a transactional message is automatically created.-->

<img src="assets/do-not-localize/icon_config.svg" width="60px">

<table>
<tr>
<td><br><p>Configure un evento con el nombre "Abandono del carro de compras" y publique esta configuración de evento.</p></td>
<td>Se implementa la API que utilizará el desarrollador de su sitio web y se crea automáticamente un mensaje transaccional.</td>
</tr>
</table>

La creación y publicación de un evento se presenta en la sección [Configuración de un evento para enviar un mensaje transaccional de evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).

### Paso 2: Editar y publicar el mensaje transaccional {#create-transactional-message}

<!--<img src="assets/do-not-localize/icon_transactional.svg" width="60px">

Edit and personalize the transactional message, test it, and then publish it.-->

<img src="assets/do-not-localize/icon_notification.svg" width="45px">

<table>
<tr>
<td><br><p>Edite y personalice el mensaje transaccional, pruébelo y, a continuación, publíquelo.</p></td>
<td>El mensaje transaccional estará listo para ser enviado.</td>
</tr>
</table>

For more on editing and publishing a transactional message, see [Event transactional messages](../../channels/using/event-transactional-messages.md).

### Paso 3: Integración del activador de eventos {#integrate-event-trigger}

<!--<img src="assets/do-not-localize/icon_api.svg" width="60px">

Use the REST Transactional Messages API to integrate the event into your website.

The event will be triggered when a client abandons their cart.-->

<img src="assets/do-not-localize/icon_api.svg" width="60px">

<table>
<tr>
<td><br><p>Utilice la API de Mensajes transaccionales REST para integrar el evento en su sitio web.</p></td>
<td>El evento se activará cuando un cliente abandone el carro de compras.</td>
</tr>
</table>

Para obtener más información sobre la integración del evento en el sitio web, consulte Integración [del sitio](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

### Paso 4 - envío de mensajes {#message-delivery}

<!--Once all of these steps have been carried out, the message can be delivered:

<img src="assets/do-not-localize/icon_notification.svg" width="40px">

As soon as a user leaves the site without ordering the products in their cart, they automatically receive a notification email.-->

<img src="assets/do-not-localize/icon_channels.svg" width="60px">

<table>
<tr>
<td><br><p>Una vez que se hayan realizado todos estos pasos, el mensaje se podrá entregar.</p></td>
<td>Tan pronto como un usuario abandona el sitio sin ordenar los productos en el carro, automáticamente recibe un mensaje de correo electrónico de notificación.</td>
</tr>
</table>

## Pasos clave {#key-steps}

Los pasos principales para crear y administrar mensajes transaccionales personalizados en Adobe Campaign se resumen en el gráfico siguiente.

![](assets/message-center-overview.png)

<!--## Transactional messaging publication process {#transactional-messaging-pub-process}

The chart below illustrates the whole transactional messaging publication process.

![](assets/message-center_pub-process.png)

For more on the event configuration steps, see [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

Read more:

* [About transactional messaging](../../channels/using/about-transactional-messaging.md)
* [Event transactional messages](../../channels/using/event-transactional-messages.md)
* [Profile transactional messages](../../channels/using/profile-transactional-messages.md)
* [Transactional push notifications](../../channels/using/transactional-push-notifications.md)
* [Follow-up messages](../../channels/using/follow-up-messages.md)-->

**Temas relacionados:**

* [Pasos clave para enviar un mensaje](../../channels/using/key-steps-to-send-a-message.md)
* [Introducción a los canales de comunicación](../../channels/using/get-started-communication-channels.md)