---
title: Acerca de la mensajería transaccional
seo-title: Acerca de la mensajería transaccional
description: Acerca de la mensajería transaccional
seo-description: Descubra los distintos tipos de mensajes transaccionales que puede enviar y cómo se utilizan en Adobe Campaign.
page-status-flag: nunca activado
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: transaccional-mensajería
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: fad149d30d06f285a89f13e4c8bff20932297695

---


# Acerca de la mensajería transaccional{#about-transactional-messaging}

Puede crear y administrar mensajes transaccionales personalizados en Adobe Campaign.

Un mensaje transaccional es una comunicación individual y única enviada a un usuario por un proveedor como un sitio web.

* Este tipo de mensaje es especialmente esperado, ya que contiene información que el destinatario desea comprobar o confirmar. Podría ser un mensaje de bienvenida después de crear una cuenta, por ejemplo, o una confirmación de envío de un pedido, una factura o un mensaje que confirme un cambio de contraseña.
* Es un mensaje importante que define la relación con el cliente: el usuario espera que se envíe en tiempo real. Por lo tanto, el retraso entre el evento que se está activando y el mensaje que llega tiene que ser muy corto.
* Los mensajes transaccionales generalmente tienen altas tasas abiertas.

Adobe Campaign le permite integrar esta funcionalidad con un sistema de información que le envía eventos que se van a transformar en mensajes transaccionales personalizados.

>[!NOTE]
>
>Los mensajes transaccionales se pueden enviar por correo electrónico, SMS o notificación push, según las opciones que tenga. Compruebe el acuerdo de licencia.

Adobe Campaign ofrece dos tipos de mensajes transaccionales:

* [Mensajes](../../channels/using/event-transactional-messages.md) transaccionales de eventos dirigidos a un evento. Los datos contenidos en el propio evento se utilizan para definir el objetivo de entrega.
* [Perfil de perfiles de segmentación de mensajes](../../channels/using/profile-transactional-messages.md) transaccionales desde la base de datos de marketing de Adobe Campaign. Puede utilizar la información de la base de datos de Adobe Campaign para enviar un mensaje transaccional basado en perfiles de marketing del cliente.

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje transaccional. Consulte Configuración [de mensajería transaccional](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign prioriza el procesamiento de los mensajes transaccionales sobre cualquier otra entrega.

La mensajería transaccional también está disponible en la API de Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#about-transactional-messaging).

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

Veamos el ejemplo de una empresa que tiene un sitio web y en este sitio web sus usuarios pueden comprar productos.

Adobe Campaign permite enviar un correo electrónico de notificación a los usuarios del sitio que han agregado productos al carro de compras: cuando uno de ellos abandona el sitio sin pasar por sus compras, se les envía automáticamente un correo electrónico de abandono del carro de compras.

Los pasos para ponerlo en práctica son:

1. Configure un evento con el nombre "Abandono del carro de compras" y publique esta configuración de evento, que crea automáticamente un mensaje transaccional. La creación y publicación de un evento se presenta en la sección [Configuración de un evento para enviar un mensaje](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) transaccional de evento.
1. El mensaje transaccional debe personalizarse, probarse y publicarse. Consulte Mensajes [transaccionales](../../channels/using/event-transactional-messages.md)de eventos.
1. Además, para que el evento se active cuando un cliente abandone el carro de compras, este evento debe enviarse desde el sitio web de la empresa mediante la API REST de Adobe Campaign Standard. Consulte Integración [del](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)sitio.

Una vez que se han realizado todos estos pasos, tan pronto como un usuario abandona el sitio sin ordenar los productos en su carro, automáticamente recibe un mensaje de correo electrónico de notificación.

## Limitaciones de mensajería transaccional {#transactional-messaging-limitations}

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe tener derechos de administración.

### Diseño y publicación {#design-and-publication}

Al diseñar y publicar mensajes transaccionales, algunos de los pasos que necesita realizar no se pueden revertir. Debe tener en cuenta las siguientes limitaciones:

* Solo se puede utilizar un canal para cada configuración de evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Una vez creado el evento, no se puede cambiar el canal. Por lo tanto, si un mensaje no se envía correctamente, debe diseñar el mecanismo que permita enviarlo desde otro canal mediante un flujo de trabajo. Consulte Procesos [y datos](../../automating/using/workflow-data-and-processes.md)de flujo de trabajo.
* No puede cambiar la dimensión de objetivo ( **[!UICONTROL Real-time event]** o **[!UICONTROL Profile]** ) después de crear el evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* No es posible revertir una publicación, pero puede cancelar la publicación de un evento: esta operación hace que el evento y el mensaje transaccional asociado no sean accesibles. Consulte [Cancelación de la publicación de un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* El único mensaje transaccional que se puede asociar con un evento es el mensaje que se crea automáticamente al publicar ese evento. Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalización {#personalization}

La manera de personalizar el contenido de un mensaje depende del tipo de mensaje transaccional. A continuación se enumeran las características específicas:

**Mensajes** transaccionales basados en eventos:

* La información de personalización proviene de los datos contenidos en el propio evento. Consulte Mensajes [transaccionales](../../channels/using/event-transactional-messages.md)de eventos.
* No puede utilizar los bloques de contenido de vínculos **de** cancelación de suscripciones en un mensaje transaccional de eventos.
* Se supone que la mensajería transaccional basada en eventos utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido del mensaje transaccional con información de la base de datos de Adobe Campaign. Consulte [Enriquecimiento del contenido](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)de mensajes transaccionales.
* Como los mensajes transaccionales de eventos no contienen información de perfil, no son compatibles con las reglas de fatiga, incluso en el caso de un enriquecimiento con perfiles. Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md).

**Mensajes** transaccionales basados en perfiles:

* La información de personalización puede proceder de los datos contenidos en el evento o del registro de perfil conciliado. Consulte [Perfil de mensajes](../../channels/using/profile-transactional-messages.md)transaccionales.
* Puede utilizar los bloques de contenido de vínculos **de** cancelación de suscripciones en un mensaje transaccional de perfil. Consulte [Adición de un bloque](../../designing/using/personalization.md#adding-a-content-block)de contenido.
* Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md).

Tenga en cuenta que las listas de productos solo están disponibles en los mensajes de correo electrónico transaccionales. Consulte [Uso de listados de productos en un mensaje](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message)transaccional.

### Permisos y marca {#permissions-and-branding}

En cuanto a la administración de [marca](../../administration/using/branding.md) , la mensajería transaccional permite menos flexibilidad que la mensajería estándar. Adobe recomienda vincular todas las marcas utilizadas en los mensajes transaccionales a la unidad **[!UICONTROL All]** [](../../administration/using/organizational-units.md)organizativa. Para más información sobre esto, lea la explicación detallada a continuación.

Al editar un mensaje transaccional, puede vincularlo a una marca para aplicar automáticamente algunos parámetros como el nombre de la marca o el logotipo de la marca. La opción **[!UICONTROL Default brand]** se selecciona de forma predeterminada en las propiedades del mensaje transaccional.

![](assets/message-center_branding.png)

Todos los objetos (incluida la marca) utilizados en un mensaje transaccional deben ser visibles desde la unidad organizativa, lo que significa que estos objetos deben estar en las unidades organizativas **[!UICONTROL Message Center]** o **[!UICONTROL Message Center]** **[!UICONTROL All]** .

Sin embargo, si la marca seleccionada en las propiedades del mensaje está vinculada a una unidad organizativa distinta de **[!UICONTROL Message Center]** o **[!UICONTROL All]**, se producirá un error y no podrá enviar el mensaje transaccional.

Por lo tanto, si desea utilizar la marca múltiple en el contexto de los mensajes transaccionales, debe vincular todas las marcas a la unidad organizativa o a la unidad organizativa **[!UICONTROL Message Center]** o a la **[!UICONTROL All]** .

### Exportación e importación de mensajes transaccionales {#exporting-and-importing-transactional-messages}

* Para exportar un mensaje transaccional, debe incluir la configuración del evento correspondiente al [crear la exportación](../../automating/using/managing-packages.md#creating-a-package)del paquete.
* Una vez que el mensaje transaccional se [importa a través de un paquete](../../automating/using/managing-packages.md#importing-a-package), no se muestra en la lista de mensajes transaccionales. Debe [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configuración del evento para que el mensaje transaccional asociado esté disponible.

