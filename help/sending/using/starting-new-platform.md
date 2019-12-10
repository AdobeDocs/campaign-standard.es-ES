---
title: Inicio de una nueva plataforma con Adobe Campaign Standard
description: Obtenga información sobre cómo configurar una nueva plataforma a la vez que mantiene la reputación de su dominio y dirección IP con Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 89965d859986b9176de6b6bf96df1fbbb89b5b8f

---


# Inicio de una nueva plataforma{#starting-new-platform}

Es esencial mantener la reputación de su dominio y dirección IP. Aquí hay algunos consejos para configurar una nueva plataforma.

Comenzar a enviar correos electrónicos en una nueva plataforma es un paso importante porque la plataforma no tiene historial de uso ni reputación (cuando las direcciones IP de envío nunca se han utilizado para este fin). Los ISP sospechan naturalmente de las direcciones IP que nunca se han utilizado para enviar correos electrónicos y que de repente comienzan a enviar grandes volúmenes de tráfico de correo electrónico. De hecho, los remitentes de spam generalmente utilizan direcciones IP "desconocidas" (es decir, direcciones que nunca se han bloqueado) para enviar el mayor número posible de mensajes antes de la detección.

No se puede esperar alcanzar la velocidad operativa en términos de salida al inicio de la fase de producción. Además, no debería intentar enviar mensajes a este ritmo, ya que podría llevar a los ISP a bloquear las direcciones de envío y comprometer seriamente el resto de la fase de inicio.

El inicio de una plataforma suele ocurrir cuando se utiliza una lista de direcciones por primera vez y puede que no esté completamente cualificada. Si envía a direcciones no válidas o a direcciones de Honeypot, esto contribuirá a disminuir la reputación de la plataforma. Si dispone de una lista de direcciones no válidas, le conviene importarla en la tabla de cuarentena (**[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** &gt; **[!UICONTROL Addresses]**) antes de enviarla por primera vez. Si, al mismo tiempo, desea recalificar las direcciones no válidas, es preferible hacerlo una vez que se establezca la reputación de la plataforma y poco a poco para "diluir" el uso de direcciones incorrectas con el tiempo.

Resumir los principios que deben seguirse al iniciar:
* **Delegar un subdominio** dedicado a Adobe específico para campañas de correo electrónico enviadas desde Adobe
* **Importar direcciones no válidas o inactivas en la tabla** de cuarentena (si tiene esta información)
* **Limitar la velocidad de rendimiento** de entrega (configuración técnica: limitar el número de equipos)
* **Aumente progresivamente los volúmenes enviados**: no dirija la base de datos entera desde el principio, sino que añada una fracción adicional de la lista cada vez que la envíe; esto debería permitirle aumentar el volumen en cada paso y reducir al mismo tiempo la tasa global de direcciones no válidas
* **Enviar mensajes regularmente**: En cierta medida, es mejor enviar pequeñas tomas con regularidad en lugar de campañas grandes de forma esporádica
* **Monitoree de cerca los informes** de envío: los indicadores de error altos pueden significar que una configuración técnica está mal configurada.
