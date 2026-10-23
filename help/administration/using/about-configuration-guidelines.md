---
title: Directrices de configuración
description: Obtenga información acerca de las directrices de configuración de Campaign Standard
audience: administration
feature: Access Management
role: Admin
level: Experienced
exl-id: 88684ed6-6d8d-4691-987f-812e7e1d834c
TQID: 'https://experienceleague.adobe.com/A54xeRieGeoElw38gcHeHrky80og-fNVPkf9qi2bu40'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: c5474392-5419-4296-9e41-f6f4ce4f6e9b
    internal-label: Administration
subfeature_v2:
  - id: efa38731-2723-4334-8d8b-a778af834835
    internal-label: Access management
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '119'
ht-degree: 7%
---
# Directrices de configuración {#about-configuration-guidelines}

## Exploradores compatibles{#compatible-browsers}

Adobe Campaign Standard es compatible con la mayoría de los navegadores para ordenadores, así como con los principales sistemas operativos para tabletas.

Adobe Campaign Standard solo admite el modo de visualización horizontal en tabletas.

Esta es la lista de exploradores compatibles con Adobe Campaign Standard:

**Equipo:**

* Chrome (versión más reciente)
* Firefox (versión más reciente)
* Safari (versión más reciente)
* Microsoft Edge (versión más reciente)

**Tableta:**

* iOS (versión 7 y posterior)
* Android (versión 4.4 y posterior)

## extremos de red de Campaign Standard {#campaign-standard-network-endpoints}

Estos son los diferentes extremos utilizados en Campaign Standard.

| Contexto | Dirección URL |
|--- |--- |
| Instancias de Campaign | `https://*.experiencecloud.adobe.com` (ID de inquilino * + dominio de cliente)<br>`https://*.campaign.adobe.com` (inquilino de instancia de Campaign) |
| IMS | `https://adobeid-na1.services.adobe.com`<br>`https://*.adobelogin.com` |
| Experience Cloud | `https://experiencecloud.adobe.com` |
| Seguimiento | `https://*.adobedtm.com`<br>`https://*.demdex.net`<br>`https://*.omtrdc.net` |
| Integración de Assets | `https://*.marketing-assets.adobe.com` |
| Servicios internos de Adobe | `https://*.adobe.io` |
| Encuestas | `https://adobe.allegiancetech.com` |
| URL de marca predeterminada (antes de la configuración del cliente) | `https://*.adobe-campaign.com` |
