---
title: Limitaciones de mensajería transaccional
description: Obtenga información sobre las principales limitaciones y recomendaciones relacionadas con los mensajes transaccionales en Adobe Campaign Standard.
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
source-git-commit: 0b6607afe05e762c87a95fd88bda0196baa57f1e
workflow-type: tm+mt
source-wordcount: '640'
ht-degree: 88%

---


# Limitaciones de mensajería transaccional {#transactional-messaging-limitations}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_concepts.svg" width="60px"></td>
<td><p>La sección siguiente lista las limitaciones que debe tener en cuenta antes de empezar a crear mensajes transaccionales.</p></td>
</tr>
</table>

Para obtener más información sobre mensajes transaccionales, incluso sobre cómo configurarlos y crearlos, consulte [Introducción a los mensajes](../../channels/using/getting-started-with-transactional-msg.md)transaccionales.

>[!NOTE]
>
>Para acceder a los mensajes transaccionales, debe tener derechos de administración.

## Diseño y publicación {#design-and-publication}

Al diseñar y publicar mensajes transaccionales, algunos de los pasos que necesita realizar no se pueden revertir. Debe tener en cuenta las siguientes limitaciones:

* Solo se puede utilizar un canal para cada configuración de evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* Una vez creado el evento, no se puede cambiar el canal. Por lo tanto, si un mensaje no se envía correctamente, debe diseñar el mecanismo que permita enviarlo desde otro canal mediante un flujo de trabajo. Consulte [Procesos y datos de flujo de trabajo](../../automating/using/get-started-workflows.md).
* No se puede cambiar la dimensión de segmentación ( **[!UICONTROL Real-time event]** o **[!UICONTROL Profile]** ) después de crear el evento. Consulte [Creación de un evento](../../administration/using/configuring-transactional-messaging.md#creating-an-event).
* No es posible revertir una publicación, pero puede cancelar la publicación de un evento: esta operación hace que el evento y el mensaje transaccional asociado no sean accesibles. Consulte [Cancelación de la publicación de un evento](../../administration/using/configuring-transactional-messaging.md#unpublishing-an-event).
* El único mensaje transaccional que se puede asociar con un evento es el mensaje que se crea automáticamente al publicar ese evento. Consulte [Vista previa y publicación del evento](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event).

## Personalización {#personalization}

La forma de personalizar el contenido de un mensaje depende del tipo de mensaje transaccional. A continuación, se enumeran las características específicas.

### Mensajes transaccionales basados en eventos

* La información de personalización proviene de los datos contenidos en el propio evento. Consulte [Mensajes transaccionales de eventos](../../channels/using/event-transactional-messages.md).
* You **cannot** use **[!UICONTROL Unsubscription link]** content blocks in an event transactional message.
* Se supone que la mensajería transaccional basada en eventos utiliza solamente los datos que se encuentran en el evento enviado para definir el destinatario y la personalización del contenido del mensaje. Sin embargo, puede enriquecer el contenido de su mensaje transaccional con información de la base de datos de Adobe Campaign. Consulte [Enriquecimiento del contenido de mensajes transaccionales](../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content).
* Como los mensajes transaccionales de eventos no contienen información sobre perfiles, no son compatibles con las normas de fatiga, incluso en el caso de un enriquecimiento con perfiles. Consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

### Mensajes transaccionales basados en perfil

* La información de personalización puede proceder de los datos contenidos en el evento o del registro de perfiles conciliado. Consulte [Mensajes transaccionales de perfil ](../../channels/using/profile-transactional-messages.md).
* You **can** use **[!UICONTROL Unsubscription link]** content blocks in a profile transactional message. Consulte [Adición de un bloque de contenido](../../designing/using/personalization.md#adding-a-content-block).
* Las reglas de fatiga son compatibles con los mensajes transaccionales de perfil. Consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

Tenga en cuenta que las listas de productos solo están disponibles en los mensajes de correos electrónicos transaccionales. Consulte [Uso de listas de productos en un mensaje transaccional](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Permisos y promoción de la marca {#permissions-and-branding}

En cuanto a la gestión de la [promoción de la marca](../../administration/using/branding.md), la mensajería transaccional permite menos flexibilidad que la mensajería estándar. Adobe recomienda vincular todas las marcas utilizadas en los mensajes transaccionales a la [unidad organizativa](../../administration/using/organizational-units.md) **[!UICONTROL All]**. Para más información al respecto, lea la explicación detallada a continuación.

Al editar un mensaje transaccional, puede vincularlo a una marca para aplicar automáticamente algunos parámetros como el nombre de la marca o el logotipo de la marca. La opción **[!UICONTROL Default brand]** se selecciona de forma predeterminada en las propiedades del mensaje transaccional.

![](assets/message-center_branding.png)

Todos los objetos (incluida la promoción de la marca) utilizados en un mensaje transaccional deben ser visibles desde la unidad organizativa **[!UICONTROL Message Center]**, lo que significa que estos objetos deben estar en las unidades organizativas **[!UICONTROL Message Center]** o **[!UICONTROL All]**.

Sin embargo, si la marca seleccionada en las propiedades del mensaje está vinculada a una unidad organizativa distinta de **[!UICONTROL Message Center]** o **[!UICONTROL All]**, esto provocará un error y no podrá enviar el mensaje transaccional.

Por lo tanto, si desea utilizar promoción de la marca múltiple en el contexto de los mensajes transaccionales, debe vincular todas las marcas a la unidad organizativa o a la unidad organizativa **[!UICONTROL Message Center]** o **[!UICONTROL All]** .

## Exportación e importación de mensajes transaccionales {#exporting-and-importing-transactional-messages}

* Para exportar un mensaje transaccional, debe incluir la configuración de evento correspondiente al [crear la exportación del paquete](../../automating/using/managing-packages.md#creating-a-package).
* Una vez que el mensaje transaccional se [importa mediante un paquete](../../automating/using/managing-packages.md#importing-a-package), no se muestra en la lista de mensaje transaccional. Debe [publicar](../../administration/using/configuring-transactional-messaging.md#previewing-and-publishing-the-event) la configuración del evento para que el mensaje transaccional asociado esté disponible.
