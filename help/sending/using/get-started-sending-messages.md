---
title: Introducción a las pruebas y envíos
description: Prepare, pruebe, programe, envíe y supervise sus mensajes.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
role: User
level: Intermediate
exl-id: bcb28ef5-5cad-43c1-b11b-080abc791a72
TQID: https://experienceleague.adobe.com/0dYFLX0zAqDIz27Y-ekkp9a9rHE9zdjOjioh5gBwaAA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 595
ht-degree: 15%

---

# Introducción a las pruebas y envíos {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparar y probar</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Envío, monitorización y seguimiento</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Directrices de entrega</a></p></td></tr>
</table>

Una vez definido el objetivo y creado el contenido de un mensaje, se debe preparar y probar el contenido, la personalización, el procesamiento y la configuración de las entregas. Esto le permite asegurarse de que todo es correcto antes de enviar el mensaje al destinatario principal. Para ello, hay varias funcionalidades disponibles, como vista previa, pruebas, prueba de línea de asunto de correo electrónico o procesamiento de correo electrónico.

Una vez que se hayan ejecutado las campañas de marketing y enviado los diferentes mensajes, monitorícelos con registros para comprobar el éxito de la campaña y recuperar la información de seguimiento de los destinatarios.

Por último, aproveche las directrices y herramientas de capacidad de entrega disponibles en Campaign Standard para mejorar el número de mensajes enviados y garantizar el éxito de las campañas de marketing.

![](assets/do-not-localize/how-to-video.png) [Descubra cómo enviar un correo electrónico de prueba, preparar y enviar un envío de correo electrónico en vídeo](#video)

## Preparar y probar {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

Campaign Standard **message preparation** analiza el objetivo, la personalización y la validez del mensaje. Los errores detectados durante este paso deben corregirse antes de poder continuar.

**Previsualice y pruebe** sus mensajes con varias funciones: envíe pruebas para probar perfiles o perfiles objetivo, pruebe la línea de asunto de sus correos electrónicos y compruebe el procesamiento de sus mensajes para asegurarse de que se mostrarán de una manera óptima en una variedad de clientes, correos web y dispositivos web.

Aproveche las funcionalidades de programación de Campaign para definir cuándo se enviarán los mensajes. Por ejemplo, puede adaptar la entrega en el huso horario del destinatario, optimizar la hora de envío o calcular la fecha de envío.

Use **tipologías** para comprobar durante la preparación si su mensaje es válido y cumple con sus criterios de calidad mediante reglas de fatiga, control y segmentación. Por ejemplo, para comprobar que los correos electrónicos siempre contienen una línea de asunto o para excluir a los suscriptores que cancelaron la suscripción de los destinatarios del mensaje.

Más información:

* [Preparación del envío](../../sending/using/preparing-the-send.md)
* [Previsualización de mensajes](../../sending/using/previewing-messages.md)
* [Envío de pruebas](../../sending/using/sending-proofs.md)
* [Representación de correo electrónico](../../sending/using/email-rendering.md)
* [Programación de mensajes](../../sending/using/about-scheduling-messages.md)
* [Acerca de las tipologías y reglas de tipología](../../sending/using/about-typology-rules.md)

## Envío, monitorización y seguimiento {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Una vez que el mensaje esté listo, puede confirmar el envío y los registros de acceso y los informes para **supervisar la entrega** y medir el éxito de la campaña. Adobe Campaign también proporciona un sistema de alertas por correo electrónico para realizar un seguimiento de los éxitos o errores de entrega, así como funciones de administración de cuarentena.

**Rastree el comportamiento** de los destinatarios del mensaje usando cookies permanentes y de sesión para recuperar la información de seguimiento (direcciones URL en las que se hizo clic, páginas espejo, mensajes abiertos...).

Por último, puede configurar Adobe Campaign para que **conserve una copia de los mensajes de correo electrónico** enviados desde su plataforma a través del correo electrónico CCO. En concreto, si su organización necesita archivar todos los mensajes de correo electrónico salientes para fines de conformidad, puede activar esta capacidad.

Más información:

* [Confirmación del envío](../../sending/using/confirming-the-send.md)
* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Archivado con CCO de correo electrónico](../../sending/using/archiving.md)
* [Seguimiento de una entrega](../../sending/using/monitoring-a-delivery.md)
* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)

## Directrices de entrega {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

La capacidad de entrega permite medir el éxito de las campañas que llegan a la bandeja de entrada de los destinatarios sin rechazarse ni marcarse como correo no deseado.

Campaign Standard proporciona **herramientas de envío** para ayudarle a mejorar el número de mensajes enviados correctamente: informes de rendimiento de envío, optimización del tiempo de envío, vista previa de mensajes, procesamiento de correo electrónico, administración de cuarentena, etc.

Más información:

* [Acerca de la capacidad de entrega](../../sending/using/about-deliverability.md)
* [Supervisión de la entregabilidad](../../sending/using/monitor-deliverability.md)
* [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es)
* [Control del rendimiento del envío](../../reporting/using/delivery-throughput.md)

## Recursos adicionales

* [Diseño de correos electrónicos de prueba A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Introducción a los mensajes](../../channels/using/key-steps-to-send-a-message.md)
* [Prácticas recomendadas para envíos](../../sending/using/delivery-best-practices.md)
* [Adición de un grupo de control](../../sending/using/control-group.md)

## Tutorial en vídeo {#video}

Este vídeo muestra cómo enviar un correo electrónico de prueba, prepararse y, a continuación, enviar un envío de correo electrónico en Campaign Standard.

>[!VIDEO](https://video.tv.adobe.com/v/24013/)

Hay disponibles [más vídeos de procedimientos para Campaign Standard aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
