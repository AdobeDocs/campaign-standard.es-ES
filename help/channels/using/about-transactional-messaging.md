---
title: Acerca de los mensajes transaccionales
seo-title: Acerca de los mensajes transaccionales
description: Acerca de los mensajes transaccionales
seo-description: Descubra los distintos tipos de mensajes transaccionales que puede enviar y cómo se utilizan en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 8470 e 9 e 2-ee 17-456 f -9 e 4 c -460 e 69 c 78 a 2 c
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajes transaccionales
discoiquuid: 71 a 4 d 5 d 5-fe 2 a -4 ce 5-b 22 b-a 4736 f 7 add 83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d93c2600299a8d2ec3672b3d82222f423878034c

---


# About transactional messaging{#about-transactional-messaging}

Puede crear y gestionar mensajes transaccionales personalizados en Adobe Campaign.

Un mensaje transaccional es una comunicación individual y única enviada a un usuario por un proveedor como un sitio web.

* Este tipo de mensaje es especialmente esperado, ya que contiene información que el destinatario desea comprobar o confirmar. Puede ser un mensaje de bienvenida después de crear una cuenta, o una confirmación que haya enviado un pedido, una factura o un mensaje que confirma un cambio de contraseña.
* Constituye un mensaje importante que define la relación del cliente: el usuario espera que se envíe en tiempo real. El retraso entre el evento que se está activando y el que llega, tiene que ser muy corto.
* Los mensajes transaccionales generalmente tienen altos índices abiertos.

Adobe Campaign permite integrar esta funcionalidad con un sistema de información que le envía eventos que se van a transformar en mensajes transaccionales personalizados.

>[!NOTE]
>
>Los mensajes transaccionales se pueden enviar por correo electrónico, SMS o notificaciones push, según las opciones. Verifique su contrato de licencia.

En Adobe Campaign hay dos tipos de mensajes transaccionales disponibles:

* [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md) dirigidos a un evento. Los datos contenidos en el mismo evento se utilizan para definir el objetivo de entrega.
* [Perfil de mensajes](../../channels/using/profile-transactional-messages.md) transaccionales de perfil de la base de datos de marketing de Adobe Campaign. Puede utilizar la información de la base de datos de Adobe Campaign para enviar un mensaje de transacción basado en perfiles de marketing del cliente.

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje de transacción. See [Transactional messaging configuration](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign prioriza el procesamiento de mensajes transaccionales sobre cualquier otra entrega.

Los mensajes transaccionales también están disponibles en la API de Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Transactional messaging operating principle {#transactional-messaging-operating-principle}

Veamos el ejemplo de una empresa que tiene un sitio web y en este sitio web los usuarios pueden comprar productos.

Adobe Campaign permite enviar un correo electrónico de notificación a los usuarios del sitio que han agregado productos al carro de compras: Cuando uno de ellos abandona el sitio sin continuar con sus compras, se envía automáticamente un mensaje de correo electrónico de abandono del carro de compras.

Los pasos para colocar esto son:

1. Configure un evento que se llamará "Abandono del carro" y publique esta configuración del evento, lo cual crea automáticamente un mensaje de transacción. Creating and publishing an event are presented in the [Configuring an event to send an event transactional message](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) section.
1. El mensaje transaccional debe personalizarse, comprobarse y publicarse. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. Además, para que el evento se active cuando un cliente abandona el carro de compras, este evento debe enviarse desde el sitio Web de la empresa utilizando la API de REST de Adobe Campaign Standard. See [Site integration](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Una vez completados todos estos pasos, tan pronto como un usuario abandona el sitio sin ordenar los productos del carro de compras, recibirá automáticamente un correo electrónico de notificación.

## Transactional messaging limitations {#transactional-messaging-limitations}

### Design and publication {#design-and-publication}

Al diseñar y publicar mensajes transaccionales, algunos de los pasos que debe realizar no se pueden revertir. Debe tener en cuenta las siguientes limitaciones:

* Solo se puede usar un canal para cada configuración de evento. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Una vez creado el evento, no podrá cambiar el canal. Por lo tanto, si no se envía correctamente un mensaje, es necesario diseñar el mecanismo que permita enviarlo desde otro canal mediante un flujo de trabajo. See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* You cannot change the targeting dimension ( **[!UICONTROL Real-time event]** or **[!UICONTROL Profile]** ) after the event is created. See [Creating an event](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* No es posible revertir una publicación, pero puede cancelar la publicación de un evento: esta operación hace que el evento y el mensaje transaccional asociado sean inaccesibles. See [Unpublishing an event](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* El único mensaje transaccional que se puede asociar con un evento es el mensaje que se crea automáticamente al publicar el evento. See [Previewing and publishing the event](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalization {#personalization}

La manera de personalizar un contenido de mensaje depende del tipo de mensaje transaccional. A continuación se enumeran las opciones específicas:

**Mensajes transaccionales basados en eventos**:

* La información de personalización proviene de los datos contenidos en el mismo evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* You cannot use **Unsubscription link** content blocks in an event transactional message.
* Los mensajes transaccionales basados en eventos deben utilizar solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización de contenido del mensaje. Sin embargo, puede enriquecer el contenido del mensaje de transacción mediante la información de la base de datos de Adobe Campaign. See [Enriching the transactional message content](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Dado que los mensajes transaccionales de eventos no contienen información de perfil, no son compatibles con las reglas de fatiga, incluso en el caso de un enriquecimiento con perfiles. See [Fatigue rules](../../administration/using/fatigue-rules.md).

**Mensajes transaccionales basados en perfiles**:

* La información de personalización puede proceder de los datos contenidos en el evento o del registro de perfiles conciliados. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* You can use **Unsubscription link** content blocks in a profile transactional message. See [Adding a content block](../../designing/using/adding-a-content-block.md).
* Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. See [Fatigue rules](../../administration/using/fatigue-rules.md).

Tenga en cuenta que las listas de productos solo están disponibles en mensajes de correo electrónico transaccionales. See [Using product listings in a transactional message](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permissions and branding {#permissions-and-branding}

When it comes to [branding](../../administration/using/branding.md) management, transactional messaging enables less flexibility than standard messaging. Adobe recommends linking all brands used in transactional messages to the **[!UICONTROL All]** organizational unit. Para obtener más información, lea la explicación detallada a continuación.

Al editar un mensaje de transacción, puede vincularlo a una marca para aplicar automáticamente algunos parámetros como el nombre de la marca o el logotipo de marca. The **[!UICONTROL Default brand]** is selected by default in the transactional message properties.

![](assets/message-center_branding.png)

To access the transactional messages, you must be part of the **[!UICONTROL Message Center agents]** (mcExec) security group, which is linked to the **[!UICONTROL Message Center]** [organizational unit](../../administration/using/organizational-units.md). Therefore, all objects (including branding) used in a transactional message must be visible from the **[!UICONTROL Message Center]** organizational unit, meaning that these objects must be in the **[!UICONTROL Message Center]** or **[!UICONTROL All]** organizational units.

However, if the brand selected in the message properties is linked to an organizational unit which is different from **[!UICONTROL Message Center]** or **[!UICONTROL All]**, this will cause an error and you will not be able to send the transactional message.

Therefore, if you want to use multi-branding in the context of transactional messaging, you should link all brands either to the **[!UICONTROL Message Center]** organizational unit or to the **[!UICONTROL All]** organizational unit.

### Exporting and importing transactional messages {#exporting-and-importing-transactional-messages}

* To export a transactional message, you need to include the corresponding event configuration when [creating the package export](../../automating/using/managing-packages.md#creating-a-package).
* Once the transactional message is [imported through a package](../../automating/using/managing-packages.md#importing-a-package), it is not displayed in the transactional message list. You need to [publish](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) the event configuration in order to make the associated transactional message available.

