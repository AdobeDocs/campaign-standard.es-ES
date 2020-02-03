---
title: Creación de contenido de correo electrónico en Adobe Experience Manager.
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5c1a540475b7d93c18c957243ee2a403b8154aa3

---


# Creación de contenido de correo electrónico en Adobe Experience Manager {#creating-email-aem}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Este caso de uso le mostrará cómo crear contenido de correo electrónico en Adobe Experience Manager.

## Requisitos previos {#prerequisites}

Asegúrese de que tiene los siguientes elementos de antemano:

* Una instancia **creación** de Adobe Experience Manager
* Una instancia **publicación** de Adobe Experience Manager
* Una instancia de Adobe Campaign

## Configuración {#configuration}

Para utilizar estas dos soluciones juntas, debe configurarlas para que se conecten entre sí.

1. Configuración de Adobe Campaign. Para ello:

   * Configure una cuenta externa de tipo Adobe Experience Manager.
   * Configure la **[!UICONTROL AEMResourceTypeFilter]**opción, que reconoce los tipos de contenido creados en Adobe Experience Manager para Adobe Campaign.
   * Cree una plantilla de correo electrónico que especifique que es contenido de Adobe Experience Manager y vincule la cuenta externa creada anteriormente a esta plantilla.

1. Configure Adobe Experience Manager. Para ello:

   * Configure la replicación entre las instancias de creación y publicación de Adobe Experience Manager.
   * Para conectar Adobe Experience Manager a Adobe Campaign, configure un **[!UICONTROL Cloud Service]**específico.

## Creación de contenido de correo electrónico en Adobe Experience Manager {#use-case}

Para crear contenido de correo electrónico en Adobe Experience Manager:

1. Cree contenido de correo electrónico con una plantilla creada específicamente para Adobe Campaign.
1. En las propiedades de contenido, seleccione la **[!UICONTROL Cloud Service]**correspondiente a la instancia de Adobe Campaign.
1. Edite el contenido insertando texto, imágenes, personalización, etc.
1. Valide el contenido.

Para obtener más información, consulte la [documentación detallada](https://docs.adobe.com/content/help/en/experience-manager-65/authoring/aem-adobe-campaign/campaign.html).

![](assets/aem_content.png)

Para recuperar el contenido en Adobe Campaign:

1. Cree un correo electrónico basado en una plantilla de contenido de tipo Adobe Experience Manager.
1. Vincule un contenido creado con Adobe Experience Manager mediante la pantalla de definición de contenido de correo electrónico de Adobe Campaign.

![](assets/aem_linked_content.png)

