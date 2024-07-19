---
title: Limitaciones de mensajería transaccional
description: Conozca las principales recomendaciones y limitaciones con respecto a los mensajes transaccionales en Adobe Campaign Standard.
audience: channels
content-type: reference
topic-tags: transactional-messaging
context-tags: null
feature: Transactional Messaging
role: User
level: Intermediate
exl-id: d6aaec6e-c718-46a2-88e8-7402970def1a
source-git-commit: 2d3ef53d5ea5603d90da169366be6ea516d96823
workflow-type: tm+mt
source-wordcount: '756'
ht-degree: 61%

---

# Prácticas recomendadas y limitaciones de la mensajería transaccional {#transactional-messaging-limitations}

<img src="assets/do-not-localize/icon_concepts.svg" width="60px">

En esta sección se enumeran las prácticas recomendadas y las limitaciones que debe tener en cuenta antes de empezar a crear mensajes transaccionales.

<!--For more on transactional messages, including on how to configure and create them, see [Getting started with transactional messaging](../../channels/using/getting-started-with-transactional-msg.md).-->

## Permisos {#permissions}

Solo los usuarios con el rol [Administration](../../administration/using/users-management.md#functional-administrators) pueden configurar eventos transaccionales y acceder a mensajes transaccionales.

## Configuración y publicación de eventos {#design-and-publication}

Al configurar y publicar eventos transaccionales, algunos de los pasos que necesita realizar no se pueden revertir. Debe tener en cuenta las siguientes limitaciones:

* Los canales disponibles para la mensajería transaccional son: **[!UICONTROL Email]**, **[!UICONTROL Mobile (SMS)]** y **[!UICONTROL Push notification]**.
* Solo se puede utilizar un canal para cada configuración de evento. Consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).
* Una vez creado el evento, no se puede cambiar el canal. Por lo tanto, si un mensaje no se envía correctamente, debe diseñar el mecanismo que permita enviarlo desde otro canal mediante un flujo de trabajo. Consulte [Procesos y datos de flujo de trabajo](../../automating/using/get-started-workflows.md).
* No se puede cambiar la dimensión de segmentación ( **[!UICONTROL Real-time event]** o **[!UICONTROL Profile]** ) después de crear el evento. Consulte [Creación de un evento](../../channels/using/configuring-transactional-event.md#creating-an-event).
* No es posible revertir una publicación, pero puede cancelar la publicación de un evento: esta operación hace que el evento y el mensaje transaccional asociado no sean accesibles. Consulte [Cancelación de la publicación de un evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event).
* El único mensaje transaccional que se puede asociar con un evento es el mensaje que se crea automáticamente al publicar ese evento. Consulte [Vista previa y publicación del evento](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event).

## Número de mensajes transaccionales {#transactional-message-number}

El número de mensajes transaccionales publicados puede tener un impacto significativo en su plataforma. Para obtener un rendimiento óptimo, el número de mensajes transaccionales publicados debe permanecer por debajo de 100; de lo contrario, se puede encontrar una degradación del rendimiento. Para garantizar esto, cancele la publicación o elimine cualquier mensaje transaccional que no se utilice a fin de cumplir con la protección mencionada. Ver [Cancelar la publicación de un mensaje transaccional](../../channels/using/publishing-transactional-message.md#unpublishing-a-transactional-message) y [Eliminar un mensaje transaccional](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message).

Para garantizar el mejor rendimiento, también puede cancelar la publicación de eventos que no se utilicen o eliminarlos. De hecho, cancelar la publicación o la eliminación de un evento también cancelará la publicación o la eliminación de los mensajes transaccionales correspondientes, y de sus registros de envío y seguimiento, si los hay. Ver [Cancelar la publicación de un evento](../../channels/using/publishing-transactional-event.md#unpublishing-an-event) y [Eliminar un evento](../../channels/using/publishing-transactional-event.md#deleting-an-event).

## Personalización {#personalization}

La forma de personalizar el contenido de un mensaje depende del tipo de mensaje transaccional. Las particularidades se enumeran a continuación.

### Mensajes transaccionales basados en eventos

* La información de personalización proviene de los datos contenidos en el propio evento. Consulte [Configuración de mensaje transaccional basado en eventos](../../channels/using/configuring-transactional-event.md#event-based-transactional-messages).
* Usted **no puede** usar bloques de contenido de **[!UICONTROL Unsubscription link]** en un mensaje transaccional de evento.
* Se supone que la mensajería transaccional basada en eventos utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido de su mensaje transaccional con información de la base de datos de Adobe Campaign. Ver [Enriquecimiento de un evento](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content) y [Personalización de un mensaje transaccional](../../channels/using/editing-transactional-message.md#personalizing-a-transactional-message).
* Como los mensajes transaccionales de eventos no contienen información sobre perfiles, no son compatibles con las normas de fatiga, incluso en el caso de un enriquecimiento con perfiles.

### Mensajes transaccionales basados en perfiles

* La información de personalización puede proceder de los datos contenidos en el evento o del registro de perfiles reconciliado. Consulte [Configuración de mensaje transaccional basada en perfiles](../../channels/using/configuring-transactional-event.md#profile-based-transactional-messages) y [Características específicas de mensaje transaccional basado en perfiles](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities).
* Usted **puede** utilizar **[!UICONTROL Unsubscription link]** bloques de contenido en un mensaje transaccional de perfil. Consulte [Adición de un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block).
* Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

### Listados de productos

Tenga en cuenta que las listas de productos solo están disponibles en **mensajes de correo electrónico** transaccionales. Consulte [Uso de listas de productos en un mensaje transaccional](../../designing/using/using-product-listings.md).

## Promoción de la marca {#permissions-and-branding}

En cuanto a la gestión de la [promoción de la marca](../../administration/using/branding.md), la mensajería transaccional permite menos flexibilidad que la mensajería estándar. Adobe recomienda vincular todas las marcas utilizadas en los mensajes transaccionales a la [unidad organizativa](../../administration/using/organizational-units.md) **[!UICONTROL All]**. Para más información al respecto, lea la explicación detallada a continuación.

Al editar un mensaje transaccional, puede vincularlo a una marca para aplicar automáticamente algunos parámetros como el nombre de la marca o el logotipo de la marca. La opción **[!UICONTROL Default brand]** se selecciona de forma predeterminada en las propiedades del mensaje transaccional.

![](assets/message-center_branding.png)

Todos los objetos (incluida la promoción de la marca) utilizados en un mensaje transaccional deben ser visibles desde la unidad organizativa **[!UICONTROL Message Center]**, lo que significa que estos objetos deben estar en las unidades organizativas **[!UICONTROL Message Center]** o **[!UICONTROL All]**.

Sin embargo, si la marca seleccionada en las propiedades del mensaje está vinculada a una unidad organizativa distinta de **[!UICONTROL Message Center]** o **[!UICONTROL All]**, esto provocará un error y no podrá enviar el mensaje transaccional.

Por lo tanto, si desea utilizar promoción de la marca múltiple en el contexto de los mensajes transaccionales, debe vincular todas las marcas a la unidad organizativa o a la unidad organizativa **[!UICONTROL Message Center]** o **[!UICONTROL All]** .

## Exportación e importación de mensajes transaccionales {#exporting-and-importing-transactional-messages}

* Para exportar un mensaje transaccional, debe incluir la configuración de evento correspondiente al [crear la exportación del paquete](../../automating/using/managing-packages.md#creating-a-package).
* Una vez que el mensaje transaccional se [importa mediante un paquete](../../automating/using/managing-packages.md#importing-a-package), no se muestra en la lista de mensaje transaccional. Debe [publicar](../../channels/using/publishing-transactional-event.md) la configuración del evento para que el mensaje transaccional asociado esté disponible.
