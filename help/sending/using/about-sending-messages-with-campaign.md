---
title: Acerca del envío de mensajes con Campaign
description: Descubrir los diferentes pasos para probar y enviar un mensaje.
page-status-flag: never-activated
uuid: 58666444-6e7c-4049-b2d2-8b26eabf5a82
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: about-sending-messages-with-campaign
discoiquuid: ae2eba1c-24ad-4839-afa9-5a2975570d9b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c49fcd793cbb13d26ccf3a47af145de7acd697e7

---


# Acerca del envío de mensajes con Campaign{#about-sending-messages-with-campaign}

Una vez definido el destinatario y creado el contenido de un mensaje, debe probar y aprobar el contenido, la personalización, la representación y la configuración, y asegurarse de que todo es correcto antes de enviar el mensaje al destinatario principal.

Para ello, las prácticas recomendadas son:

* Preparar el envío: este paso le permite pasar al análisis y la preparación de mensajes para enviarlos. La preparación del mensaje analiza el destinatario, la personalización y la validez del mensaje. Los errores detectados durante este paso deben corregirse antes de poder continuar. Puede iniciar la preparación del mensaje tantas veces como sea necesario. For more on message preparation, refer to [this section](../../sending/using/preparing-the-send.md).

   >[!NOTE]
   >
   >Puede establecer reglas globales de fatiga entre canales que excluyan automáticamente los perfiles superpuestos de las campañas. Consulte Reglas [de fatiga](../../sending/using/fatigue-rules.md).

* Previsualización de mensajes mediante un perfil de prueba. For more on previewing messages, refer to [this section](../../sending/using/previewing-messages.md).
* Enviar pruebas a los mensajes de prueba. For more on proofs, refer to [this  section](../../sending/using/sending-proofs.md).
* Compruebe la representación del mensaje: asegúrese de que el mensaje se muestre de forma óptima en una variedad de clientes web, correos electrónicos web y dispositivos. Obtenga más información sobre el procesamiento por correo electrónico en [esta sección](../../sending/using/email-rendering.md).

A continuación, puede:

* Programar el envío: puede definir cuándo se enviarán los mensajes. Por ejemplo, puede adaptar el envío en la zona horaria del destinatario, optimizar la hora de envío o calcular la fecha de envío. Obtenga más información en [esta sección](../../sending/using/about-scheduling-messages.md).
* Enviar el mensaje: una vez que el mensaje esté listo, puede enviar el inicio. Los registros de acceso y los informes están disponibles para supervisar el envío del mensaje y medir el éxito de la campaña. Adobe Campaign también proporciona un sistema de alertas por correo electrónico para realizar un seguimiento de los éxitos o errores de los envíos. Learn more in [this page](../../sending/using/confirming-the-send.md).

## Temas relacionados

| Páginas útiles | Recursos adicionales |
|---|---|
| [Optimización de la capacidad de entrega](../../sending/using/about-deliverability.md) | [Gestión de la fatiga](../../sending/using/fatigue-rules.md) |
| [Control del rendimiento del Envío](../../reporting/using/delivery-throughput.md) | [Diseño de correos electrónicos de prueba A/B](../../channels/using/designing-an-a-b-test-email.md) |
| [Recibir una notificación cuando se produce un error](../../sending/using/receiving-alerts-when-failures-happen.md) | [Seguimiento de una entrega](../../sending/using/monitoring-a-delivery.md) |
| [Creación de un grupo de control](../../automating/using/workflow-control-group.md) | [Envío de mensajes de seguimiento](../../channels/using/follow-up-messages.md) |