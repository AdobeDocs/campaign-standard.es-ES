---
solution: Campaign Standard
product: campaign
title: Introducción a las pruebas y envíos
description: Prepare, pruebe, programe, envíe y supervise sus mensajes.
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '573'
ht-degree: 14%

---


# Introducción a las pruebas y envíos {#about-sending-messages-with-campaign}

<table>
<tr>
<td><img src="assets/do-not-localize/icon_prepare.svg" width="60px"><p><a href="#prepare-test-send">Preparación y prueba</a></p></td>
<td><img src="assets/do-not-localize/icon_send.svg" width="60px"><p><a href="#send-track-messages">Envío, supervisión y seguimiento</a></p></td>
<td><img src="assets/do-not-localize/icon_deliverability.svg" width="60px"><p><a href="#improve-deliverability">Directrices de capacidad de entrega</a></p></td></tr>
</table>

Una vez definido el destinatario y creado el contenido de un mensaje, deberá preparar y probar el contenido, la personalización, el procesamiento y la configuración de sus envíos. Esto le permite asegurarse de que todo es correcto antes de enviar el mensaje al destinatario principal. Para ello, hay disponibles varias funcionalidades, como previsualización, pruebas, pruebas de línea de asunto de correo electrónico o representación por correo electrónico.

Una vez que se hayan ejecutado las campañas de mercadotecnia y se hayan enviado los distintos mensajes, monitoréelos mediante registros para comprobar el éxito de la campaña y recuperar la información de seguimiento de los destinatarios.

Por último, aproveche las directrices y herramientas de entrega disponibles en Campaign Standard para mejorar el número de mensajes entregados y garantizar campañas de marketing exitosas.

## Preparación y prueba {#prepare-test-send}

<img src="assets/do-not-localize/icon_prepare.svg" width="60px">

La preparación **de** mensajes de Campaign Standard analiza el destinatario, la personalización y la validez del mensaje. Los errores detectados durante este paso deben corregirse antes de poder continuar.

**Realice previsualizaciones y pruebas** de los mensajes con diversas funciones: enviar pruebas para probar perfiles o perfiles con objetivos, probar la línea de asunto de los mensajes de correo electrónico y comprobar la presentación de los mensajes para asegurarse de que se muestre de manera óptima en una variedad de clientes web, correos electrónicos y dispositivos.

Aproveche las capacidades de programación de Campañas para definir cuándo se enviarán los mensajes. Por ejemplo, puede adaptar el envío en la zona horaria del destinatario, optimizar la hora de envío o calcular la fecha de envío.

Use **tipologías** para comprobar durante la preparación si su mensaje es válido y cumple con sus criterios de calidad mediante reglas de fatiga, control y segmentación. Por ejemplo, para comprobar que los correos electrónicos siempre contienen una línea de asunto o para excluir a los suscriptores de los destinatarios de mensaje.

Más información:

* [Preparación del envío](../../sending/using/preparing-the-send.md)
* [Vista previa de mensajes](../../sending/using/previewing-messages.md)
* [Envío de pruebas](../../sending/using/sending-proofs.md)
* [Procesamiento de correo electrónico](../../sending/using/email-rendering.md)
* [Programación de mensajes](../../sending/using/about-scheduling-messages.md)
* [Información sobre las tipologías y reglas de tipología](../../sending/using/about-typology-rules.md)

## Envío, supervisión y seguimiento {#send-track-messages}

<img src="assets/do-not-localize/icon_send.svg"  width="60px">

Una vez que el mensaje esté listo, puede confirmar los registros y los informes de envío y acceso para **monitorear el envío** y medir el éxito de la campaña. Adobe Campaign también ofrece un sistema de alertas por correo electrónico para realizar un seguimiento de los éxitos o errores de los envíos, así como de las funciones de administración de cuarentenas.

**Rastree el comportamiento** de los destinatarios de mensajes utilizando cookies permanentes y de sesión para recuperar información de seguimiento (direcciones URL en las que se hizo clic, páginas espejo, mensajes abiertos...).

Finalmente, puede configurar Adobe Campaign para **guardar una copia de los correos electrónicos** enviados desde su plataforma a través de Email BCC. En particular, si su organización necesita archivar todos los mensajes de correo electrónico salientes para cumplir con la normativa, puede habilitar esta capacidad.

Más información:

* [Confirmación del envío](../../sending/using/confirming-the-send.md)
* [Seguimiento de mensajes](../../sending/using/tracking-messages.md)
* [Archivado con Email BCC](../../sending/using/archiving.md)
* [Seguimiento de una entrega](../../sending/using/monitoring-a-delivery.md)
* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Comprensión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)

## Directrices de capacidad de entrega {#improve-deliverability}

<img src="assets/do-not-localize/icon_deliverability.svg"  width="60px">

La posibilidad de entrega permite medir el éxito de sus campañas alcanzando la bandeja de entrada de sus destinatarios sin rebotar, o bien se marca como correo no deseado.

Campaign Standard proporciona varias herramientas **de** entrega para ayudarle a mejorar el número de mensajes enviados correctamente: informes de perspectiva de envío, envío de optimización de tiempo, previsualización de mensajes, procesamiento de correo electrónico, administración de cuarentenas, etc.

Más información:

* [Acerca de la capacidad de la entrega](../../sending/using/about-deliverability.md)
* [Supervisión de la capacidad de entrega](../../sending/using/monitor-deliverability.md)
* [Mejora de la reputación](../../sending/using/improving-reputation.md)
* [Recomendaciones técnicas](../../sending/using/technical-recommendations.md)
* [Control del rendimiento del Envío](../../reporting/using/delivery-throughput.md)

## Recursos adicionales

* [Diseño de correos electrónicos de prueba A/B](../../channels/using/designing-an-a-b-test-email.md)
* [Envío de una prueba, preparación y envío de un correo electrónico (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/sending-test-preparing-sending-email.html)
* [Revisar un envío de correo electrónico e informes (vídeo)](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/reviewing-personalized-email-delivery-and-reports.html)
* [Introducción a los correos electrónicos](https://helpx.adobe.com/es/campaign/kb/acs-get-started-with-emails.html)
* [Prácticas recomendadas relacionadas con las entregas](../../sending/using/delivery-best-practices.md)
* [Adición de un grupo de control](../../sending/using/control-group.md)
