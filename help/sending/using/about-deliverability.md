---
title: Acerca de la capacidad de entrega en Adobe Campaign Standard
description: Obtenga información sobre los conceptos y las prácticas recomendadas relacionados con la capacidad de entrega, así como sobre las herramientas ofrecidas por Adobe Campaign Standard para optimizar el envío de los envíos.
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
source-git-commit: 02b8d847d4506eca96abfa27db1e2efadc2a68d2

---


# Acerca de la capacidad del envío{#about-deliverability}

La capacidad de entrega permite medir el éxito de las campañas que llegan a la bandeja de entrada de los destinatarios sin rebotar o marcadas como correo no deseado.

La tasa de entregabilidad depende de numerosos factores, en particular:

* Configuración correcta de las instancias
* Su reputación de dirección IP
* Calidad de las direcciones objetivo
* Baja cantidad de quejas y tasas de devolución
* Contenido del mensaje
* Autenticación de mensajes (SPF, DKIM, DMARC)
* Conocimiento del remitente

## Puntos clave que comprobar {#deliverability-key-points}

Para optimizar la entrega de los correos electrónicos de Adobe Campaign, recomendamos que utilice las optimizaciones que se enumeran a continuación. Los problemas de entrega generalmente están vinculados a medidas de protección contra spam implementadas por proveedores de servicios de Internet y administradores de servidores de correo.

La capacidad de envío de correo electrónico hace referencia al conjunto de características que determinan la capacidad de un mensaje para llegar a su destino a través de una dirección de correo electrónico personal, en poco tiempo y con la calidad esperada en términos de contenido y formato. Estas características se dividen en cuatro categorías principales: calidad de datos, mensaje y contenido, infraestructura de envío y reputación. Juntas forman la base del éxito de un programa de envío de correo electrónico.

La tasa de entrega es el número de correos electrónicos enviados correctamente a sus destinatarios.
A continuación se muestra una lista de los puntos clave que se deben comprobar para garantizar una buena entrega.

## Herramientas de distribución {#deliverability-tools}

En primer lugar, comience consultando la documentación sobre las herramientas de entregabilidad proporcionadas con Campaign Standard:
* [Prácticas recomendadas relacionadas con los envíos](https://helpx.adobe.com/campaign/kb/delivery-best-practices.html)
* [Personalización del nombre del remitente](../../designing/using/personalization.md#personalizing-the-sender)
* [Prueba de la línea de asunto de un correo electrónico](../../sending/using/testing-subject-line-email.md)
* [Optimización del tiempo de envío](../../sending/using/optimizing-the-sending-time.md)
* [Vista previa de mensajes](../../sending/using/previewing-messages.md)
* [Procesamiento de correo electrónico](../../sending/using/email-rendering.md)
* [Seguimiento de un envío](../../sending/using/monitoring-a-delivery.md)
* [Recibir alertas cuando se produzcan errores](../../sending/using/receiving-alerts-when-failures-happen.md)
* [Comprensión de los errores de envío](../../sending/using/understanding-delivery-failures.md)
* [Compresión de la gestión de la cuarentena](../../sending/using/understanding-quarantine-management.md)
* [Cuarentena o lista negra](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting)
* [Informes dinámicos](../../reporting/using/about-dynamic-reports.md)

## Comprobación de la configuración de red {#network-configuration}

Los remitentes de spam intentan ocultar su identidad real y, como consecuencia, dificultan la identificación de sus servidores. Una configuración de red legítima que no intente ocultar la identidad del servidor es esencial para enviar correos electrónicos en grandes volúmenes.

## Envío a direcciones válidas {#valid-addresses}

Los remitentes de spam suelen utilizar generadores de direcciones basados en listas de nombres y apellidos frecuentes; además, rara vez procesan las notificaciones técnicas enviadas por los servidores de correo. Una tasa alta de direcciones no válidas se interpreta a menudo como un signo de spam. Los mecanismos de doble inclusión y el manejo eficaz de los mensajes de devolución técnicos permiten evitar esto.

## Reducción de la tasa de quejas {#reduce-complaint-rate}

Los proveedores de servicios de Internet generalmente tienen un medio prominente para informar un mensaje recibido como correo no deseado. Esto permite identificar fuentes no fiables. Al cumplir con rapidez las solicitudes de exclusión, utilizar con regularidad una lista determinada, verificar el consentimiento a través de un sistema de doble inclusión e implementar círculos de retroalimentación, puede reducir las tasas de quejas.

## Envío a direcciones de honeypot {#honeypot-addresses}

Los ISP y otras organizaciones (consulte https://www.projecthoneypot.org/) utilizan buzones de correo que no corresponden a personas físicas pero que se crean simplemente para engañar a los remitentes de spam. Estas llamadas &quot;ollas de miel&quot; se publican en la web para ser recogidas por los spambots y así atrapar a remitentes ilegítimos. El uso de un mecanismo de doble inclusión impide que este tipo de dirección se agregue a una lista. Al utilizar una lista de terceros, debe estar seguro de los métodos empleados por su mantenedor.

## Adaptación del contenido de los mensajes {#adapt-message-content}

En menor medida, el contenido de ciertos mensajes puede llevar a ciertos filtros a detectarlo como correo no deseado. El uso de ciertas palabras, el uso de exclamaciones en la línea del asunto y dentro de los mensajes se interpretan como signos reveladores de spam. También se sabe que los remitentes de spam reemplazan el texto con imágenes para evitar que el texto ofensivo se analice automáticamente mediante filtros antispam. En respuesta a esto, un mensaje (en formato HTML) con una alta proporción de imágenes, o imágenes como archivos adjuntos, puede terminar siendo bloqueado.

## Envío regular {#regular-deliveries}

Los remitentes de spam realizan entregas programadas para mantener su reputación con el tiempo. A veces necesitan adaptar su plan de mercadotecnia para cumplir con las mejores prácticas impuestas por los ISP y así, después de un pico de reputación (aumento), configuran entregas regulares.
