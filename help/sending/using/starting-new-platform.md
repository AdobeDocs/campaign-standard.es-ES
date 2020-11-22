---
solution: Campaign Standard
product: campaign
title: Inicio de una nueva plataforma con Adobe Campaign Standard
description: Obtenga información sobre cómo configurar una nueva plataforma mientras mantiene la reputación de su dominio y dirección IP con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 55%

---


# Inicio de una nueva plataforma{#starting-new-platform}

Es esencial mantener la reputación de su dominio y dirección IP. Aquí hay algunos consejos para configurar una nueva plataforma.

Comenzar a enviar correos electrónicos en una nueva plataforma es un paso importante porque la plataforma no tiene historial de uso ni reputación (cuando las direcciones IP de envío nunca se han utilizado para este fin). Los ISP sospechan naturalmente de las direcciones IP que nunca se han utilizado para enviar correos electrónicos y que de repente comienzan a enviar grandes volúmenes de tráfico de correo electrónico. De hecho, los remitentes de spam generalmente utilizan direcciones IP &quot;desconocidas&quot; (direcciones que nunca se han agregado a la  de lista de bloqueados) para enviar el mayor número posible de mensajes antes de la detección.

No se puede esperar alcanzar la velocidad operativa en términos de salida al inicio de la fase de producción. Además, no debería intentar enviar mensajes a este ritmo, ya que podría llevar a los ISP a bloquear las direcciones de envío y comprometer seriamente el resto de la fase de inicio.

El inicio de una plataforma suele ocurrir cuando se utiliza una lista de direcciones por primera vez y puede que no esté completamente cualificada. Si envía a direcciones no válidas o a direcciones de honeypot, esto contribuye a disminuir la reputación de la plataforma.
* If you have a list of invalid addresses, it is in your best interests to import it into the quarantine table (**[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** > **[!UICONTROL Addresses]**) before sending for the first times. Para obtener más información, consulte esta [sección](../../sending/using/understanding-quarantine-management.md#identifying-quarantined-addresses-for-the-entire-platform).
* Si, al mismo tiempo, desea recalificar las direcciones no válidas, es preferible hacerlo una vez que se establezca la reputación de la plataforma y poco a poco para &quot;diluir&quot; el uso de direcciones incorrectas con el tiempo.

Resumir los principios que deben seguirse al iniciar:
* **Configure un subdominio** dedicado para que funcione con una Campaña específica para las campañas de correo electrónico enviadas desde Adobe.
* **Importe direcciones no válidas o inactivas en la tabla** de cuarentena (si tiene esta información).
* **Limitar la velocidad de rendimiento** del envío (configuración técnica: limitar el número de equipos).
* **Aumente progresivamente los volúmenes enviados**: no destinatario toda la base de datos desde el mismo inicio, sino que agrega una fracción adicional de la lista cada vez que envía. Esto debería permitirle aumentar el volumen en cada paso y reducir al mismo tiempo la tasa global de direcciones no válidas.
* **Enviar mensajes regularmente**: hasta cierto punto es mejor enviar pequeñas tomas con regularidad en lugar de grandes campañas esporádicamente.
* **Monitorear de cerca los informes de envío**: los indicadores de error altos pueden significar que una configuración técnica está mal configurada.
