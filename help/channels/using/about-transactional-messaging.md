---
title: Acerca de la mensajería transaccional
description: Descubra los diferentes tipos de mensajes transaccionales que puede enviar y cómo se utilizan en el Adobe Campaign.
page-status-flag: never-activated
uuid: 8470e9e2-ee17-456f-9e4c-460e69c78a2c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: transactional-messaging
discoiquuid: 71a4d5d5-fe2a-4ce5-b22b-a4736f7add83
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 155ed7e50e207e4c4dc0569e5e96b24e712e4be8

---


# Acerca de la mensajería transaccional{#about-transactional-messaging}

Puede crear y administrar mensajes transaccionales personalizados en Adobe Campaign.

Un mensaje transaccional es una comunicación individual y única que un proveedor, como un sitio web, envía a un usuario.

* Este tipo de mensaje es especialmente esperado, ya que contiene información que el destinatario desea comprobar o confirmar. Podría ser un mensaje de bienvenida después de crear una cuenta, por ejemplo, o una confirmación de envío de un pedido, una factura o un mensaje que confirme un cambio de contraseña.
* Es un mensaje importante que define la relación con el cliente: el usuario espera que se envíe en tiempo real. Por lo tanto, el retraso entre el evento que se está activando y el mensaje que llega tiene que ser muy corto.
* Por lo general, los Mensajes transaccionales tienen tasas abiertas elevadas.

Adobe Campaign le permite integrar esta funcionalidad con un sistema de información que le envía eventos que se van a transformar en mensajes transaccionales personalizados.

>[!NOTE]
>
>Los Mensajes transaccionales se pueden enviar por correo electrónico, por SMS o por notificaciones push, según las opciones que tenga. Compruebe el acuerdo de licencia.

Hay dos tipos de mensajes transaccionales disponibles en Adobe Campaign:

* [mensajes transaccionales](../../channels/using/event-transactional-messages.md) de Evento dirigidos a un evento. Los datos contenidos en el propio evento se utilizan para definir el destinatario del envío.
* [perfiles de objetivo de mensajes transaccionales](../../channels/using/profile-transactional-messages.md) de Perfil de la base de datos de marketing de Adobe Campaign. Puede utilizar la información de la base de datos de Adobe Campaign para enviar un mensaje transaccional basado en perfiles de marketing de clientes.

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje transaccional. Consulte Configuración [de mensajería transaccional](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign prioriza el procesamiento de los mensajes transaccionales sobre cualquier otro envío.

La mensajería transaccional también está disponible en la API de Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](../../api/using/managing-transactional-messages.md).

>[!IMPORTANT]
>
>Una vez actualizado al MTA [](https://helpx.adobe.com/es/campaign/kb/campaign-enhanced-mta.html)mejorado, todos los mensajes transaccionales se envían con el MTA mejorado de Adobe Campaign para mejorar la entrega, el rendimiento y la gestión de devoluciones. Todos los impactos son los mismos que para los mensajes de marketing estándar y se detallan en el documento [MTA mejorado de Adobe Campaign](https://helpx.adobe.com/es/campaign/kb/campaign-enhanced-mta.html).

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

Veamos el ejemplo de una compañía que tiene un sitio web y en este sitio web sus usuarios pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los usuarios del sitio que han agregado productos al carro de compras: cuando uno de ellos abandona el sitio sin pasar por sus compras, se les envía automáticamente un correo electrónico de abandono del carro de compras.

Los pasos para ponerlo en práctica son:

1. Configure un evento con el nombre &quot;Abandono del carro de compras&quot; y publique esta configuración de evento, que crea automáticamente un mensaje transaccional. La creación y publicación de un evento se presenta en la sección [Configuración de un evento para enviar un mensaje transaccional](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message) de evento.
1. El mensaje transaccional debe personalizarse, probarse y luego publicarse. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
1. Además, para que el evento se active cuando un cliente abandone el carro, este evento debe enviarse desde el sitio web de la compañía utilizando la API REST de Adobe Campaign Standard. Consulte Integración [del](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website)sitio.

Una vez que se han realizado todos estos pasos, tan pronto como un usuario abandona el sitio sin ordenar los productos en su carro, automáticamente recibe un mensaje de correo electrónico de notificación.

## Proceso de publicación de mensajes transaccionales {#transactional-messaging-pub-process}

El gráfico siguiente ilustra el proceso de publicación de mensajes transaccionales.

![](assets/message-center_pub-process.png)

Para obtener más información sobre los pasos de configuración de evento, consulte Configuración [de mensajería transaccional](../../administration/using/configuring-transactional-messaging.md).

## Limitaciones de mensajería transaccional {#transactional-messaging-limitations}

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe tener derechos de administración.

### Diseño y publicación {#design-and-publication}

Al diseñar y publicar mensajes transaccionales, algunos de los pasos que necesita realizar no se pueden revertir. Debe tener en cuenta las siguientes limitaciones:

* Sólo se puede utilizar un canal para cada configuración de evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Una vez creado el evento, no se puede cambiar el canal. Por lo tanto, si un mensaje no se envía correctamente, debe diseñar el mecanismo que permita enviarlo desde otro canal mediante un flujo de trabajo. See [Workflow data and processes](../../automating/using/workflow-data-and-processes.md).
* No se puede cambiar la dimensión de segmentación ( **[!UICONTROL Real-time event]** o **[!UICONTROL Profile]** ) después de crear el evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* No es posible revertir una publicación, pero puede cancelar la publicación de un evento: esta operación hace que el evento y el mensaje transaccional asociado no sean accesibles. Consulte [Cancelación de la publicación de un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* El único mensaje transaccional que se puede asociar con un evento es el mensaje que se crea automáticamente al publicar ese evento. Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalización {#personalization}

La forma de personalizar el contenido de un mensaje depende del tipo de mensaje transaccional. A continuación se enumeran las características específicas:

**mensajes transaccionales** basados en Eventos:

* La información de personalización proviene de los datos contenidos en el propio evento. See [Event transactional messages](../../channels/using/event-transactional-messages.md).
* No puede utilizar bloques de contenido de vínculos **** Bajas en un mensaje transaccional de evento.
* Se supone que la mensajería transaccional basada en Evento utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido de su mensaje transaccional con información de la base de datos de Adobe Campaign. Consulte [Enriquecimiento del contenido](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content)de mensaje transaccional.
* Como los mensajes transaccionales de evento no contienen información sobre perfiles, no son compatibles con las normas de fatiga, incluso en el caso de un enriquecimiento con perfiles. Consulte Reglas [de fatiga](../../sending/using/fatigue-rules.md).

**mensajes transaccionales** basados en Perfiles:

* La información de personalización puede proceder de los datos contenidos en el evento o del registro de perfiles conciliado. See [Profile transactional messages](../../channels/using/profile-transactional-messages.md).
* Puede utilizar bloques de contenido de vínculos **** Bajas en un mensaje transaccional de perfil. Consulte [Añadir un bloque](../../designing/using/personalization.md#adding-a-content-block)de contenido.
* Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte Reglas [de fatiga](../../sending/using/fatigue-rules.md).

Tenga en cuenta que las listas de productos solo están disponibles en los mensajes de correo electrónico transaccionales. Consulte [Uso de listas de productos en un mensaje transaccional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permisos y marca {#permissions-and-branding}

En cuanto a la administración de [marca](../../administration/using/branding.md) , la mensajería transaccional permite menos flexibilidad que la mensajería estándar. Adobe recomienda vincular todas las marcas utilizadas en los mensajes transaccionales a la unidad **[!UICONTROL All]** [](../../administration/using/organizational-units.md)organizativa. Para más información sobre esto, lea la explicación detallada a continuación.

Al editar un mensaje transaccional, puede vincularlo a una marca para aplicar automáticamente algunos parámetros como el nombre de la marca o el logotipo de la marca. La opción **[!UICONTROL Default brand]** se selecciona de forma predeterminada en las propiedades de mensaje transaccional.

![](assets/message-center_branding.png)

Todos los objetos (incluida la marca) utilizados en un mensaje transaccional deben ser visibles desde la unidad organizativa, lo que significa que estos objetos deben estar en las unidades **[!UICONTROL Message Center]** o **[!UICONTROL Message Center]** **[!UICONTROL All]** organizativas.

Sin embargo, si la marca seleccionada en las propiedades del mensaje está vinculada a una unidad organizativa distinta de **[!UICONTROL Message Center]** o **[!UICONTROL All]**, esto provocará un error y no podrá enviar el mensaje transaccional.

Por lo tanto, si desea utilizar la marca múltiple en el contexto de los mensajes transaccionales, debe vincular todas las marcas a la unidad organizativa o a la unidad organizativa **[!UICONTROL Message Center]** o a la **[!UICONTROL All]** .

### Exportación e importación de mensajes transaccionales {#exporting-and-importing-transactional-messages}

* Para exportar un mensaje transaccional, debe incluir la configuración de evento correspondiente al [crear la exportación](../../automating/using/managing-packages.md#creating-a-package)del paquete.
* Una vez que el mensaje transaccional se [importa mediante un paquete](../../automating/using/managing-packages.md#importing-a-package), no se muestra en la lista de mensaje transaccional. Debe [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configuración de evento para que el mensaje transaccional asociado esté disponible.

