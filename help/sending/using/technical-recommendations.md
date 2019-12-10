---
title: Recomendaciones técnicas de entrega para Adobe Campaign Standard
description: Obtenga información sobre algunas recomendaciones técnicas para mejorar la capacidad de entrega con Adobe Campaign Standard.
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
source-git-commit: 44049443f8028ed26089ee0d49944ebac6a62111

---


# Recomendaciones técnicas{#technical-recommendations}

Además, a continuación se enumeran varias técnicas, configuraciones y herramientas que puede utilizar para mejorar la tasa de entrega.

A continuación se presentan algunas definiciones de los principales términos técnicos.

**DNS** Adobe Campaign inverso comprueba si se proporciona un DNS inverso para una dirección IP y si esto apunta correctamente a la dirección IP.

**Las reglas** MX se utilizan para controlar la velocidad a la que el MTA de campaña (Agente de transferencia de mensajes) envía correos electrónicos a cada dominio de correo electrónico o ISP individual (por ejemplo, hotmail.com, comcast.net). Estas reglas generalmente se basan en los límites publicados por los ISP (por ejemplo, no incluir más de 20 mensajes por cada conexión SMTP).

**TLS** TLS (Transport Layer Security) es un protocolo de codificación que se puede utilizar para asegurar la conexión entre dos servidores de correo electrónico y proteger el contenido de un correo electrónico de que no lo lean los destinatarios previstos.

**SPF** SPF (Sender Policy Framework) es un estándar de autenticación de correo electrónico que permite al propietario de un dominio especificar qué servidores de correo electrónico pueden enviar correos electrónicos en nombre de ese dominio. Este estándar utiliza el dominio en el encabezado "Return-Path" del correo electrónico (también denominado la dirección "Envelope From").

**La autenticación DKIM** DKIM (Domain Keys Identified Mail) es un sucesor de SPF y utiliza criptografía de clave pública que permite al servidor de correo electrónico receptor verificar que un mensaje fue enviado por la persona o entidad por la que afirma que fue enviado, y si el contenido del mensaje se alteró entre el momento en que se envió originalmente (y DKIM "firmado") y el momento en que se recibió. Este estándar suele utilizar el dominio en el encabezado "De" o "Remitente".

**DMARC** DMARC (Autenticación de mensajes, informes y conformidad basados en dominio) es la forma más reciente de autenticación por correo electrónico y se basa en la autenticación SPF y DKIM para determinar si un correo electrónico pasa o falla. DMARC es única y poderosa de dos maneras muy importantes:
* Conformidad: permite al remitente indicar a los ISP qué hacer con cualquier mensaje que no se autentique (p. ej., no aceptarlo).
* Informes: proporciona al remitente un informe detallado que muestra todos los mensajes en los que se ha producido un error en la autenticación DMARC, junto con el dominio "De" y la dirección IP utilizadas para cada uno. Esto permite que una empresa identifique el correo electrónico legítimo que falla en la autenticación y necesita algún tipo de "corrección" (por ejemplo, agregar direcciones IP a su registro SPF), así como las fuentes y la prevalencia de intentos de phishing en sus dominios de correo electrónico.

DMARC puede aprovechar los informes generados por 250ok.

**SMTP**(Protocolo simple de transferencia de correo) es un estándar de Internet para la transmisión de correo electrónico.

**IP dedicadas** Adobe proporciona una estrategia IP dedicada para cada cliente con una IP de aumento para crear una reputación y optimizar el rendimiento de la entrega.
