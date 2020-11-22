---
solution: Campaign Standard
product: campaign
title: Recomendaciones técnicas de entrega para Adobe Campaign Standard
description: Obtenga más información sobre algunas recomendaciones técnicas para mejorar la capacidad de entrega con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 43%

---


# Recomendaciones técnicas{#technical-recommendations}

A continuación se enumeran varias técnicas, configuraciones y herramientas que puede utilizar para mejorar la tasa de entrega. A continuación se presentan algunas definiciones de los principales términos técnicos.

**Reverse DNS**: Adobe Campaign comprueba si se ha proporcionado un DNS inverso para una dirección IP y que este señale correctamente a la dirección IP.

**Las reglas** MX se utilizan para controlar la velocidad a la que el MTA de Campaña (Agente de transferencia de mensajes) envía correos electrónicos a cada dominio de correo electrónico o ISP individual (por ejemplo, hotmail.com, comcast.net). Estas reglas generalmente se basan en los límites que publican los ISP (por ejemplo, no incluir más de 20 mensajes por cada conexión SMTP).

**TLS** (Transport Layer Security) es un protocolo de codificación que se puede utilizar para asegurar la conexión entre dos servidores de correo electrónico y proteger el contenido de un correo electrónico de que no lo lean los destinatarios previstos.

**SPF** (Marco de directivas de remitentes) es un estándar de autenticación de correo electrónico que permite al propietario de un dominio especificar qué servidores de correo electrónico pueden enviar correos electrónicos en nombre de ese dominio. Este estándar utiliza el dominio en el encabezado “Return-Path” del correo electrónico (también denominado la dirección “Envelope From”).

**La autenticación DKIM** (correo identificado con claves de dominio) es un sucesor de SPF y utiliza criptografía de clave pública que permite al servidor de correo electrónico receptor verificar que un mensaje fue enviado por la persona o entidad por la que afirma que fue enviado, y si el contenido del mensaje se alteró entre el momento en que se envió originalmente (y DKIM &quot;firmado&quot;) y la hora en que fue recibido. Este estándar suele utilizar el dominio en el encabezado “De” o “Remitente”. 

**DMARC** (Autenticación de mensajes basada en dominio, Sistema de informes y conformidad) es la forma más reciente de autenticación por correo electrónico y se basa en la autenticación SPF y DKIM para determinar si un correo electrónico pasa o falla. DMARC es única y útil de dos maneras muy importantes:
* Conformidad: permite al remitente indicar a los ISP qué hacer con cualquier mensaje que no se autentique (por ejemplo: no aceptarlo).
* Creación de informes: proporciona al remitente un informe detallado que muestra todos los mensajes en los que se ha producido un error en la autenticación DMARC, junto con el dominio “De” y la dirección IP utilizadas para cada uno. Esto permite que una empresa identifique el correo electrónico legítimo que falla en la autenticación y necesita algún tipo de “corrección” (por ejemplo: añadir direcciones IP a su registro SPF), así como las fuentes y la prevalencia de intentos de phishing en sus dominios de correo electrónico.

DMARC puede aprovechar los informes generados por 250ok.

**SMTP** (Protocolo simple de transferencia de correo) es un estándar de Internet para la transmisión de correo electrónico.

**IPs** dedicadas: Adobe proporciona una estrategia IP específica para cada cliente con una IP de aumento para crear una reputación y optimizar el rendimiento del envío.
