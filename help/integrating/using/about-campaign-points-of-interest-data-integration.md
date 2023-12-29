---
title: Acerca de la integración de Campaign con datos de Puntos de interés
description: Al recopilar los datos de puntos de interés de los suscriptores de la aplicación móvil, envíe mensajes de marketing basados en la ubicación a sus suscriptores a través de la integración en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 6%

---

# Acerca de la integración de Campaign con datos de Puntos de interés{#about-campaign-points-of-interest-data-integration}

Además de rastrear la presencia en línea de los clientes, también puede aprovechar sus ubicaciones físicas. Mediante la integración con Adobe Analytics para dispositivos móviles, puede utilizar Adobe Campaign para enviar mensajes de marketing basados en la ubicación a los suscriptores de la aplicación móvil.

Los puntos de interés constan de una latitud, una longitud y un radio asociados a una etiqueta. Se definen en la variable [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html) interfaz.

Cuando un suscriptor abre la aplicación móvil, si la ubicación coincide con un punto de interés, Adobe Campaign captura los datos mediante el SDK para móviles de Experience Cloud. Puede utilizar esta información para enviar mensajes personalizados según la ubicación del usuario (como correos electrónicos, notificaciones push o mensajes SMS).

Por ejemplo, puede enviar una oferta de descuento del 10 % a los clientes que usen su aplicación y hayan visitado una de sus tiendas en Boston en las últimas dos semanas.

Se presenta un caso de uso en la variable [Personalización de mensajes de Campaign con datos de Puntos de interés](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) sección.
