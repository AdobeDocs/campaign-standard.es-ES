---
title: Pasos clave para enviar un mensaje
description: Siga estos pasos para crear y enviar mensajes con Adobe Campaign.
audience: channels
content-type: reference
topic-tags: about-communication-channels
feature: Overview
role: User
level: Beginner
exl-id: a903d7e2-7654-46b3-bc61-4653a065faad
TQID: https://experienceleague.adobe.com/jEwlV4sdPtwlYNW-3uSWMBJOOCiffDv1GbCFMN1wNF4
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: a075b2c1-7748-4328-b7f6-343aa314616a
  - id: a4671286-a59f-47e3-b97b-90627a1977d5
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 370
ht-degree: 12%

---

# Pasos clave para enviar un mensaje{#key-steps-to-send-a-message}

En esta sección, aprenderá a crear y enviar mensajes personalizados a una audiencia segmentada mediante Adobe Campaign Standard.

Encontrará información específica sobre cómo crear y configurar cada canal de comunicación en estas secciones:

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Creación de un SMS](../../channels/using/creating-an-sms-message.md)
* [Creación de una entrega de correo directo](../../channels/using/creating-the-direct-mail.md)
* [Creando una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md).
* [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md)

Para conocer las prácticas recomendadas de entrega, consulte la sección [Prácticas recomendadas de entrega](../../sending/using/delivery-best-practices.md).

## Cree su mensaje

Aproveche las [actividades de marketing](../../start/using/marketing-activities.md) de Campaign Standard para crear un mensaje de correo electrónico, SMS, correo directo, notificación push o en la aplicación.

![](assets/marketing-activities.png)

Los mensajes se pueden crear desde la lista de actividades de marketing o desde un flujo de trabajo mediante [actividades dedicadas](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Definición del público

Defina los destinatarios del mensaje. Para ello, use el [editor de consultas](../../automating/using/editing-queries.md) del panel izquierdo para filtrar los datos contenidos en la base de datos y generar reglas para segmentar la audiencia.

Hay varios tipos de audiencias disponibles:

* **[!UICONTROL Target]** es el destinatario principal del correo electrónico,
* **[!UICONTROL Test profiles]** son los perfiles utilizados para probar y validar el correo electrónico (consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)).

![](assets/steps-audience.png)

## Diseño y personalización del contenido

En el bloque **[!UICONTROL Content]**, diseñe y personalice el contenido del mensaje con campos de la base de datos. Para obtener más información sobre cómo diseñar contenido para un canal específico, consulte las secciones que aparecen en la parte superior de esta página.

![](assets/steps-content.png)

## Preparar y probar

[Preparar](../../sending/using/preparing-the-send.md) el mensaje. Este proceso calcula la población objetivo y prepara el mensaje personalizado.

![](assets/steps-prepare.png)

**Compruebe y pruebe su mensaje** antes de enviarlo mediante las funciones de Campaign Standard: vista previa, procesamiento de correo electrónico, revisión, etc. Para obtener más información, consulte [esta sección](../../sending/using/previewing-messages.md).

Use el bloque **[!UICONTROL Schedule]** para definir cuándo se enviarán los mensajes (consulte [Programación de mensajes](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Envío y seguimiento

Una vez que el mensaje esté listo, puede confirmar el envío. El bloque **[!UICONTROL Deployment]** muestra el progreso de envío y el resultado.

![](assets/steps-send.png)

Hay varios registros disponibles para ayudarle a supervisar el envío de sus mensajes (consulte [supervisar un envío](../../sending/using/monitoring-a-delivery.md)). También puede rastrear el comportamiento de los destinatarios de la entrega gracias a las [funcionalidades de seguimiento](../../sending/using/tracking-messages.md) de Campaign Standard.

![](../../sending/using/assets/tracking_logs.png)

Mida la eficacia de sus mensajes y la evolución de sus envíos y campañas mediante diversos indicadores y gráficos (consulte [Acceso a informes](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
