---
title: Acerca de la integración de Campaign con datos de Puntos de interés
description: Al recopilar los datos de puntos de interés de los suscriptores de la aplicación móvil, envíe mensajes de marketing basados en la ubicación a sus suscriptores a través de la integración en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-analytics-for-mobile
feature: Audiences
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 358194f9-34ce-4dd5-b9b2-1a7d541879ab
TQID: 'https://experienceleague.adobe.com/NMHm-sHLhsjMqprniSnxca27zpoxGEhRGKlt1IJXfVg'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: d6330382-c886-4f7a-a4f7-74e3f36c0d9c
    internal-label: Audiences
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
    internal-label: Data integration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 6%
---
# Acerca de la integración de Campaign con datos de Puntos de interés{#about-campaign-points-of-interest-data-integration}

Además de rastrear la presencia en línea de los clientes, también puede aprovechar sus ubicaciones físicas. Mediante la integración con Adobe Analytics para dispositivos móviles, puede utilizar Adobe Campaign para enviar mensajes de marketing basados en la ubicación a los suscriptores de la aplicación móvil.

Los puntos de interés constan de una latitud, una longitud y un radio asociados a una etiqueta. Se definen en la interfaz [Adobe Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html).

Cuando un suscriptor abre la aplicación móvil, si la ubicación coincide con un punto de interés, Adobe Campaign captura los datos mediante Experience Cloud Mobile SDK. Puede utilizar esta información para enviar mensajes personalizados según la ubicación del usuario (como correos electrónicos, notificaciones push o mensajes SMS).

Por ejemplo, puede enviar una oferta de descuento del 10 % a los clientes que usen su aplicación y hayan visitado una de sus tiendas en Boston en las últimas dos semanas.

Se presenta un caso de uso en la sección [Personalización de mensajes de Campaign con datos del punto de interés](../../integrating/using/personalizing-campaign-messages-with-point-of-interest-data.md).
