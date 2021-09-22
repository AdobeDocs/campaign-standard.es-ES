---
title: Introducción a las pruebas y envíos
description: Prepare, pruebe, programe, envíe y supervise sus mensajes.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 17%

---

# Introducción a las pruebas y envíos {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparación y prueba</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Envío, monitorización y seguimiento de</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Directrices de capacidad de entrega</a></p></td></tr>
</table>

Una vez definido el destinatario y creado el contenido de un mensaje, debe preparar y probar el contenido, la personalización, la renderización y la configuración de los envíos. Esto le permite asegurarse de que todo es correcto antes de enviar el mensaje al destinatario principal. Para ello, hay disponibles varias funcionalidades, como vista previa, pruebas, pruebas de línea de asunto de correo electrónico o procesamiento de correo electrónico.

Una vez que se hayan ejecutado las campañas de marketing y enviado los distintos mensajes, monitoréelos mediante registros para comprobar el éxito de la campaña y recuperar la información de seguimiento de los destinatarios.

Por último, aproveche las herramientas y directrices de capacidad de envío disponibles en Campaign Standard para mejorar el número de mensajes enviados y garantizar que las campañas de marketing tengan éxito.

![](assets/do-not-localize/how-to-video.png) [Descubra cómo enviar un correo electrónico de prueba, preparar y enviar una entrega por correo electrónico en vídeo](#video)

## Preparación y prueba {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

El Campaign Standard **message preparation** analiza el destinatario, la personalización y la validez del mensaje. Los errores detectados durante este paso deben corregirse antes de poder continuar.

**Previsualice y** pruebe los mensajes con diversas funciones: envíe pruebas a perfiles de prueba o perfiles objetivo, pruebe la línea de asunto de sus correos electrónicos y compruebe la renderización de sus mensajes para asegurarse de que se muestre de forma óptima en una variedad de clientes, correos web y dispositivos web.

Aproveche las capacidades de programación de Campaign para definir cuándo se enviarán los mensajes. Por ejemplo, se puede adaptar el envío en el huso horario del destinatario, optimizar la hora de envío o calcular la fecha de envío.

Utilice **tipologías** para comprobar durante la preparación si su mensaje es válido y cumple con los criterios de calidad mediante reglas de fatiga, control y segmentación. Por ejemplo, para comprobar que los correos electrónicos siempre contienen una línea de asunto o para excluir a los suscriptores de los destinatarios de mensajes.

Más información:

* [Preparación del envío](../../sending/using/preparing-the-send.md)
* [Vista previa de mensajes](../../sending/using/previewing-messages.md)
* [Envío de pruebas](../../sending/using/sending-proofs.md)
* [Procesamiento de correo electrónico](../../sending/using/email-rendering.md)
* [Programación de mensajes](../../sending/using/about-scheduling-messages.md)
* [Acerca de las tipologías y reglas de tipología](../../sending/using/about-typology-rules.md)

## Envío, monitorización y seguimiento de {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Una vez que el mensaje esté listo, puede confirmar el envío y acceder a los registros e informes para **monitorizar el envío** y medir el éxito de la campaña. Adobe Campaign también proporciona un sistema de alertas por correo electrónico para realizar un seguimiento de los envíos erróneos o correctos, así como funciones de administración de cuarentena.

**Rastree el** comportamiento de los destinatarios de mensajes mediante el uso de cookies permanentes y de sesión para recuperar información de seguimiento (direcciones URL en las que se hizo clic, páginas espejo, mensajes abiertos...).

Por último, puede configurar Adobe Campaign para **conservar una copia de los correos electrónicos** enviados desde su plataforma a través del correo electrónico CCO. En concreto, si su organización necesita archivar todos los mensajes de correo electrónico salientes para que sean compatibles, puede habilitar esta capacidad.

Más información:

* [Confirmación del envío](../../sending/using/confirming-the-send.md)
* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Archivado con CCO de correo electrónico](../../sending/using/archiving.md)
* [Seguimiento de una entrega](../../sending/using/monitoring-a-delivery.md)
* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)

## Directrices de capacidad de entrega {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

La capacidad de entrega permite medir el éxito de las campañas que llegan a la bandeja de entrada de los destinatarios sin rebotar o marcadas como correo no deseado.

Campaign Standard proporciona varias **herramientas de envío** para ayudarle a mejorar el número de mensajes enviados correctamente: informes de rendimiento de entrega, optimización del tiempo de envío, previsualización de mensajes, procesamiento de correo electrónico, administración de cuarentena, etc.

Más información:

* [Acerca de la capacidad de entrega](../../sending/using/about-deliverability.md)
* [Supervisión de la capacidad de entrega](../../sending/using/monitor-deliverability.md)
* [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es)
* [Control del rendimiento de entrega](../../reporting/using/delivery-throughput.md)

## Recursos adicionales

* [Diseño de correos electrónicos de prueba A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Introducción a los correos electrónicos](https://helpx.adobe.com/es/campaign/kb/acs-get-started-with-emails.html)
* [Prácticas recomendadas de entregas](../../sending/using/delivery-best-practices.md)
* [Adición de un grupo de control](../../sending/using/control-group.md)

## Tutorial en vídeo {#video}

Este vídeo muestra cómo enviar un correo electrónico de prueba, preparar y después enviar una entrega por correo electrónico en Campaign Standard.

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

Hay disponibles más vídeos prácticos del Campaign Standard [aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
