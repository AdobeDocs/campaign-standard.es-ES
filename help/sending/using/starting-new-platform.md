---
solution: Campaign Standard
product: campaign
title: Inicio de una nueva plataforma con Adobe Campaign Standard
description: Obtenga información sobre cómo configurar una nueva plataforma a la vez que mantiene la reputación de su dominio y dirección IP con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Capacidad de entrega
role: Profesional empresarial
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 55%

---


# Inicio de una nueva plataforma{#starting-new-platform}

Es esencial mantener la reputación de su dominio y dirección IP. Aquí hay algunos consejos para configurar una nueva plataforma.

Comenzar a enviar correos electrónicos en una nueva plataforma es un paso importante porque la plataforma no tiene historial de uso ni reputación (cuando las direcciones IP de envío nunca se han utilizado para este fin). Los ISP sospechan naturalmente de las direcciones IP que nunca se han utilizado para enviar correos electrónicos y que de repente comienzan a enviar grandes volúmenes de tráfico de correo electrónico. De hecho, los remitentes de correo no deseado generalmente utilizan direcciones IP &quot;desconocidas&quot; (direcciones que nunca se han agregado a la  de lista de bloqueados) para enviar el mayor número posible de mensajes antes de la detección.

No se puede esperar alcanzar la velocidad operativa en términos de salida al inicio de la fase de producción. Además, no debería intentar enviar mensajes a este ritmo, ya que podría llevar a los ISP a bloquear las direcciones de envío y comprometer seriamente el resto de la fase de inicio.

El inicio de una plataforma suele ocurrir cuando se utiliza una lista de direcciones por primera vez y puede que no esté completamente cualificada. Si envía a direcciones no válidas o a direcciones de honeypot, esto contribuye a disminuir la reputación de la plataforma.
* Si tiene una lista de direcciones no válidas, lo mejor es importarla a la tabla de cuarentena (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) antes de enviarla por primera vez. Para obtener más información, consulte esta [sección](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Si, al mismo tiempo, desea recalificar las direcciones no válidas, es preferible hacerlo una vez que se establezca la reputación de la plataforma y poco a poco para &quot;diluir&quot; el uso de direcciones incorrectas con el tiempo.

Resumir los principios que deben seguirse al iniciar:
* **Configure un** subdominio dedicado para que funcione con Campaign que sea específico de las campañas de correo electrónico enviadas desde el Adobe.
* **Importe direcciones no válidas/inactivas en la tabla de cuarentena**  (si tiene esta información).
* **Limite la** velocidad de entrega (configuración técnica: limitar el número de equipos).
* **Aumente progresivamente los volúmenes enviados**: no dirija toda la base de datos desde el principio, sino que añada una fracción adicional de la lista cada vez que envíe. Esto debería permitirle aumentar el volumen en cada paso y reducir al mismo tiempo la tasa global de direcciones no válidas.
* **Envíe mensajes regularmente**: en cierta medida, es mejor enviar pequeñas tomas con regularidad que grandes campañas esporádicamente.
* **Monitorice de cerca los informes** de envío: los indicadores de error altos pueden significar que una configuración técnica está mal configurada.
