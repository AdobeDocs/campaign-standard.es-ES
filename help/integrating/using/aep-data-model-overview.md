---
title: Información general del modelo de datos de Experience
description: Modelo de datos de experiencia (XDM) es un conjunto estándar de esquemas de datos en los que se pueden ingerir datos para utilizarlos con soluciones y productos de Adobe Experience Platform.
audience: administration
content-type: reference
topic-tags: configuring-channels
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: cc1aa669-30cd-4ea4-9fab-4d1b6c373744
hide: true
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 0%
---
# Información general del modelo de datos de Experience {#experience-data-model-overview}

>[!IMPORTANT]
>
>El conector de datos de Adobe Experience Platform se encuentra en la versión beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Los clientes deben estar alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas funciones. Si desea acceder, póngase en contacto con el Servicio de atención al cliente de Adobe.

Modelo de datos de experiencia (XDM) es un conjunto estándar de esquemas de datos en los que se pueden ingerir datos para utilizarlos con soluciones y productos de Adobe Experience Platform.

La creación y administración de esquemas XDM está disponible con una API dedicada o con la interfaz de usuario de XDM.

## Espacio de trabajo XDM {#xdm-workspace}

XDM Workspace permite ver, crear y ampliar esquemas de datos.

Para acceder a la interfaz de usuario de XDM, abra Adobe Experience Platform. Acceda a la ventana Modelo de Datos para crear o ampliar un esquema XDM.

Consulte la [documentación completa de XDM Workspace](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=es).

![](assets/aep_xdmworkspace.png)

## API de XDM {#xdm-api}

Puede realizar las siguientes acciones a través de la API de esquema XDM:

* Ver una lista de esquemas existentes
* Ver un esquema específico Ampliar un esquema existente
* Añadir campos a una extensión
* Creación y actualización de un nuevo esquema
* Ver descriptores de esquema
* Crear, actualizar y eliminar descriptores de esquema

Todos los detalles para manipular las llamadas API están disponibles en [Guía para desarrolladores](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html?lang=es).
