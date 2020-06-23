---
title: Acerca de la integración de Campaign con datos de Puntos de interés
description: Al recopilar los datos de puntos de interés de los suscriptores de la aplicación móvil, envíe mensajes de marketing basados en la ubicación a sus suscriptores mediante la integración en Adobe Campaign.
page-status-flag: never-activated
uuid: 1e6840c8-0472-4da2-85ed-f9a65147555a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
discoiquuid: bc10c650-80cd-4146-ae82-c5981fc62bec
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '198'
ht-degree: 6%

---


# Acerca de la integración de Campaign con datos de Puntos de interés{#about-campaign-points-of-interest-data-integration}

Además de rastrear la presencia en línea de los clientes, también puede aprovechar sus ubicaciones físicas. Mediante la integración con Adobe Analytics para móviles, puede utilizar Adobe Campaign para enviar mensajes de marketing basados en la ubicación a los suscriptores de la aplicación móvil.

Los puntos de interés consisten en una latitud, una longitud y un radio asociados a una etiqueta. Se definen en la interfaz de [Adobe Mobile Services](https://docs.adobe.com/content/help/en/mobile-services/using/home.html) .

Cuando un suscriptor abre la aplicación móvil, si la ubicación coincide con un punto de interés, Adobe Campaign captura los datos mediante el SDK de Experience Cloud Mobile. Puede utilizar esta información para enviar mensajes personalizados en función de la ubicación del usuario (como correos electrónicos, notificaciones push o mensajes SMS).

Por ejemplo, puede enviar una oferta de descuento del 10 % a los clientes que utilicen su aplicación y hayan visitado una de sus tiendas en Boston en las dos últimas semanas.

Un caso de uso se presenta en la sección [Personalización de mensajes de Campaña con datos](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md) de puntos de interés.
