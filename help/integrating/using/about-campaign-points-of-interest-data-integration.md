---
solution: Campaign Standard
product: campaign
title: Acerca de la integración de Campaign con datos de Puntos de interés
description: Recopilando los datos de puntos de interés de los suscriptores de su aplicación móvil, envíe mensajes de marketing basados en la ubicación a sus suscriptores a través de la integración en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%

---


# Acerca de la integración de Campaign con datos de Puntos de interés{#about-campaign-points-of-interest-data-integration}

Además de rastrear la presencia en línea de los clientes, también puede aprovechar su ubicación física. Mediante la integración con Adobe Analytics para móviles, puede utilizar Adobe Campaign para enviar mensajes de marketing basados en la ubicación a los suscriptores de la aplicación móvil.

Los puntos de interés constan de una latitud, una longitud y un radio asociados a una etiqueta. Se definen en la interfaz [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html).

Cuando un suscriptor abre la aplicación móvil, si la ubicación coincide con un punto de interés, Adobe Campaign captura los datos a través del SDK móvil del Experience Cloud. Puede utilizar esta información para enviar mensajes personalizados en función de la ubicación del usuario (como correos electrónicos, notificaciones push o mensajes SMS).

Por ejemplo, puede enviar una oferta de 10% de descuento a los clientes que usen su aplicación y que hayan visitado una de sus tiendas en Boston en las últimas dos semanas.

Se presenta un caso de uso en la sección [Personalización de mensajes de campaña con datos del punto de interés](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md).
