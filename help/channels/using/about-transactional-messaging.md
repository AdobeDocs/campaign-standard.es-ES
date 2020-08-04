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
translation-type: ht
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb
workflow-type: ht
source-wordcount: '1147'
ht-degree: 100%

---


# Acerca de la mensajería transaccional{#about-transactional-messaging}

Puede crear y administrar mensajes transaccionales personalizados en Adobe Campaign.

Un mensaje transaccional es una comunicación individual y única que un proveedor, como un sitio web, envía a un usuario.

* Este tipo de mensaje es especialmente esperado, ya que contiene información que el destinatario puede comprobar o confirmar. Podría ser un mensaje de bienvenida después de crear una cuenta, por ejemplo, o una confirmación de envío de un pedido, una factura o un mensaje que confirme un cambio de contraseña.
* Es un mensaje importante que define la relación con el cliente: el usuario espera que se envíe en tiempo real. Por lo tanto, el retraso entre el evento que se está activando y el mensaje que llega tiene que ser muy corto.
* Por lo general, los mensajes transaccionales tienen tasas abiertas elevadas.

Adobe Campaign le permite integrar esta funcionalidad con un sistema de información que le envía eventos que se van a transformar en mensajes transaccionales personalizados.

>[!NOTE]
>
>Los mensajes transaccionales se pueden enviar por correo electrónico, por SMS o por notificaciones push, según las opciones que tenga. Compruebe el acuerdo de licencia.

En Adobe Campaign, hay disponibles dos tipos de mensajes transaccionales:

* Los [mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md) están dirigidos a un evento. Los datos contenidos en el propio evento se utilizan para definir el destinatario del envío.
* Los [mensajes transaccionales de perfil](../../channels/using/profile-transactional-messages.md) están dirigidos a perfiles de la base de datos de marketing de Adobe Campaign. Puede utilizar la información de la base de datos de Adobe Campaign para enviar un mensaje transaccional basado en perfiles de marketing de clientes.

El tipo de mensaje se define al configurar el evento que se transformará en un mensaje transaccional. Consulte [Configuración de mensajería transaccional](../../administration/using/configuring-transactional-messaging.md).

>[!NOTE]
>
>Adobe Campaign prioriza el procesamiento de los mensajes transaccionales sobre cualquier otro envío.

La mensajería transaccional también está disponible en la API de Adobe Campaign Standard. Para obtener más información, consulte [la documentación dedicada](../../api/using/managing-transactional-messages.md) .

>[!NOTE]
>
>Todos los mensajes transaccionales ahora se envían con el MTA mejorado de Adobe Campaign para mejorar la capacidad de entrega, el rendimiento y la gestión de devoluciones. Todos los impactos son los mismos que con los mensajes de marketing estándar. Para obtener más información, consulte esta [sección](../../administration/using/configuring-email-channel.md).

## Principio operativo de mensajería transaccional {#transactional-messaging-operating-principle}

Veamos el ejemplo de una compañía que tiene un sitio web y en este sitio web sus usuarios pueden comprar productos.

Adobe Campaign le permite enviar un correo electrónico de notificación a los usuarios del sitio que han agregado productos al carro de compras: cuando uno de ellos abandona el sitio sin comprar, se les envía automáticamente un correo electrónico de abandono del carro de compras.

Los pasos para ponerlo en práctica son estos:

1. Configure un evento con el nombre Abandono del carro de compras y publique esta configuración de evento, que crea automáticamente un mensaje transaccional. La creación y publicación de un evento se presenta en la sección [Configuración de un evento para enviar un mensaje transaccional de evento](../../administration/using/configuring-transactional-messaging.md#use-case--configuring-an-event-to-send-a-transactional-message).
1. El mensaje transaccional debe personalizarse, probarse y, luego, publicarse. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).
1. Además, para que el evento se active cuando un cliente abandone el carro, este evento debe enviarse desde el sitio web de la compañía utilizando la API REST de Adobe Campaign Standard. Consulte [Integración del sitio](../../administration/using/configuring-transactional-messaging.md#integrating-the-triggering-of-the-event-in-a-website).

Una vez que se han realizado todos estos pasos, tan pronto como un usuario abandona el sitio sin comprar los productos que tiene en el carro, automáticamente recibe un mensaje de correo electrónico de notificación.

## Proceso de publicación de mensajes transaccionales {#transactional-messaging-pub-process}

El gráfico siguiente ilustra el proceso de publicación de mensajes transaccionales.

![](assets/message-center_pub-process.png)

Para obtener más información sobre los pasos de configuración de evento, consulte [Configuración de mensajería transaccional](../../administration/using/configuring-transactional-messaging.md).

## Limitaciones de mensajería transaccional {#transactional-messaging-limitations}

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe tener derechos de administración.

### Diseño y publicación {#design-and-publication}

Al diseñar y publicar mensajes transaccionales, algunos de los pasos que necesita realizar no se pueden revertir. Debe tener en cuenta las siguientes limitaciones:

* Solo se puede utilizar un canal para cada configuración de evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Una vez creado el evento, no se puede cambiar el canal. Por lo tanto, si un mensaje no se envía correctamente, debe diseñar el mecanismo que permita enviarlo desde otro canal mediante un flujo de trabajo. Consulte [Procesos y datos de flujo de trabajo](../../automating/using/get-started-workflows.md).
* No se puede cambiar la dimensión de segmentación ( **[!UICONTROL Real-time event]** o **[!UICONTROL Profile]** ) después de crear el evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* No es posible revertir una publicación, pero puede cancelar la publicación de un evento: esta operación hace que el evento y el mensaje transaccional asociado no sean accesibles. Consulte [Cancelación de la publicación de un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* El único mensaje transaccional que se puede asociar con un evento es el mensaje que se crea automáticamente al publicar ese evento. Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

### Personalización {#personalization}

La forma de personalizar el contenido de un mensaje depende del tipo de mensaje transaccional. A continuación, se enumeran las características específicas:

**Mensajes transaccionales basados en eventos**.

* La información de personalización proviene de los datos contenidos en el propio evento. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).
* No puede utilizar bloques de contenido de **Vínculo de baja** en un mensaje transaccional de eventos.
* Se supone que la mensajería transaccional basada en eventos utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido de su mensaje transaccional con información de la base de datos de Adobe Campaign. Consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Como los mensajes transaccionales de eventos no contienen información sobre perfiles, no son compatibles con las normas de fatiga, incluso en el caso de un enriquecimiento con perfiles. Consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

**Mensajes transaccionales basados en perfil**:

* La información de personalización puede proceder de los datos contenidos en el evento o del registro de perfiles conciliado. Consulte [Mensajes transaccionales de perfil ](../../channels/using/profile-transactional-messages.md).
* Puede utilizar bloques de contenido de **Vínculo de baja** en un mensaje transaccional de perfil. Consulte [Adición de un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block).
* Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

Tenga en cuenta que las listas de productos solo están disponibles en los mensajes de correos electrónicos transaccionales. Consulte [Uso de listas de productos en un mensaje transaccional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

### Permisos y promoción de la marca {#permissions-and-branding}

En cuanto a la gestión de la [promoción de la marca](../../administration/using/branding.md), la mensajería transaccional permite menos flexibilidad que la mensajería estándar. Adobe recomienda vincular todas las marcas utilizadas en los mensajes transaccionales a la [unidad organizativa](../../administration/using/organizational-units.md) **[!UICONTROL All]**. Para más información al respecto, lea la explicación detallada a continuación.

Al editar un mensaje transaccional, puede vincularlo a una marca para aplicar automáticamente algunos parámetros como el nombre de la marca o el logotipo de la marca. La opción **[!UICONTROL Default brand]** se selecciona de forma predeterminada en las propiedades del mensaje transaccional.

![](assets/message-center_branding.png)

Todos los objetos (incluida la promoción de la marca) utilizados en un mensaje transaccional deben ser visibles desde la unidad organizativa **[!UICONTROL Message Center]**, lo que significa que estos objetos deben estar en las unidades organizativas **[!UICONTROL Message Center]** o **[!UICONTROL All]**.

Sin embargo, si la marca seleccionada en las propiedades del mensaje está vinculada a una unidad organizativa distinta de **[!UICONTROL Message Center]** o **[!UICONTROL All]**, esto provocará un error y no podrá enviar el mensaje transaccional.

Por lo tanto, si desea utilizar promoción de la marca múltiple en el contexto de los mensajes transaccionales, debe vincular todas las marcas a la unidad organizativa o a la unidad organizativa **[!UICONTROL Message Center]** o **[!UICONTROL All]** .

### Exportación e importación de mensajes transaccionales {#exporting-and-importing-transactional-messages}

* Para exportar un mensaje transaccional, debe incluir la configuración de evento correspondiente al [crear la exportación del paquete](../../automating/using/managing-packages.md#creating-a-package).
* Una vez que el mensaje transaccional se [importa mediante un paquete](../../automating/using/managing-packages.md#importing-a-package), no se muestra en la lista de mensaje transaccional. Debe [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configuración del evento para que el mensaje transaccional asociado esté disponible.

