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
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 14%

---

# Pasos clave para enviar un mensaje{#key-steps-to-send-a-message}

En esta sección, aprenderá a crear y enviar mensajes personalizados a una audiencia de destino mediante Adobe Campaign Standard.

En estas secciones se encuentra disponible información específica sobre cómo crear y configurar cada canal de comunicación:

* [Creación de un correo electrónico](../../channels/using/creating-an-email.md)
* [Creación de un SMS](../../channels/using/creating-an-sms-message.md)
* [Creación de una entrega de correo postal](../../channels/using/creating-the-direct-mail.md)
* [Creación de una notificación push](../../channels/using/preparing-and-sending-a-push-notification.md).
* [Preparación y envío de un mensaje en la aplicación](../../channels/using/preparing-and-sending-an-in-app-message.md)

Para conocer las prácticas recomendadas de envío, consulte la sección [Prácticas recomendadas de envío](../../sending/using/delivery-best-practices.md).

## Crear el mensaje

Aproveche las [actividades de marketing](../../start/using/marketing-activities.md) del Campaign Standard para crear un mensaje de correo electrónico, SMS, correo postal, notificación push o mensaje en la aplicación.

![](assets/marketing-activities.png)

Los mensajes se pueden crear desde la lista de actividades de marketing o desde un flujo de trabajo mediante [actividades dedicadas](../../automating/using/about-channel-activities.md).

![](assets/steps-channel.png)

## Definición de la audiencia

Defina los destinatarios del mensaje. Para ello, utilice el [editor de consultas](../../automating/using/editing-queries.md) del panel izquierdo para filtrar los datos contenidos en la base de datos y crear reglas para dirigirse a la audiencia.

Hay varios tipos de audiencias disponibles:

* **[!UICONTROL Target]** es el destinatario principal del correo electrónico,
* **[!UICONTROL Test profiles]** son los perfiles utilizados para probar y validar el correo electrónico (consulte  [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md)).

![](assets/steps-audience.png)

## Diseño y personalización del contenido

En el bloque **[!UICONTROL Content]** , diseñe y personalice el contenido del mensaje utilizando campos de la base de datos. Para obtener más información sobre cómo diseñar contenido para un canal específico, consulte las secciones que aparecen en la parte superior de esta página.

![](assets/steps-content.png)

## Preparación y prueba

[](../../sending/using/preparing-the-send.md) Prepare el mensaje. Este proceso calcula la población objetivo y prepara el mensaje personalizado.

![](assets/steps-prepare.png)

**Compruebe y pruebe el** mensaje antes de enviarlo con las funciones del Campaign Standard: vista previa, procesamiento de correo electrónico, pruebas, etc. Para obtener más información, consulte [esta sección](../../sending/using/previewing-messages.md).

Utilice el bloque **[!UICONTROL Schedule]** para definir cuándo se enviarán los mensajes (consulte [Scheduling messages](../../sending/using/about-scheduling-messages.md)).

![](assets/steps-schedule.png)

## Envío y seguimiento

Una vez que el mensaje esté listo, puede confirmar el envío. El bloque **[!UICONTROL Deployment]** muestra el progreso del envío y el resultado.

![](assets/steps-send.png)

Hay varios registros disponibles para ayudarle a supervisar el envío de sus mensajes (consulte [supervisión de un envío](../../sending/using/monitoring-a-delivery.md)). También puede realizar un seguimiento del comportamiento de sus destinatarios de envío gracias a las [funcionalidades de seguimiento](../../sending/using/tracking-messages.md) del Campaign Standard.

![](../../sending/using/assets/tracking_logs.png)

Mida la eficacia de sus mensajes y la evolución de sus envíos y campañas a través de varios indicadores y gráficos (consulte [Acceso a informes](../../reporting/using/about-dynamic-reports.md)).

![](assets/steps-reports.png)
