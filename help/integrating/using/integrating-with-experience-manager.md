---
title: Integración con Experience Manager
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
page-status-flag: nunca activado
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Integración con Experience Manager{#integrating-with-experience-manager}

Esta integración entre Adobe Campaign Standard y Adobe Experience Manager le permite utilizar contenido creado en Adobe Experience Manager en los correos electrónicos de Adobe Campaign.

Por lo tanto, puede aprovechar al máximo las funciones de edición de contenido de Adobe Experience Manager, así como las funciones de administración de datos y entrega de Adobe Campaign.

>[!NOTE]
>
>No puede realizar pruebas A/B para el contenido importado de Adobe Experience Manager.

Adobe Campaign Standard es compatible con Adobe Experience Manager 6.1, 6.2, 6.3 y 6.4. Las siguientes secciones presentan una descripción general de las acciones que puede ejecutar. Para obtener más información, consulte las secciones dedicadas a la [configuración](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html) y el [uso](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/campaign.html) de la integración.

## Requisitos previos {#prerequisites}

Asegúrese de que tiene los siguientes elementos de antemano:

* Una instancia **creación** de Adobe Experience Manager
* Una instancia **publicación** de Adobe Experience Manager
* Una instancia de Adobe Campaign

## Ejemplo de uso {#use-case}

Para crear contenido de correo electrónico en Adobe Experience Manager:

1. Cree contenido de correo electrónico con una plantilla creada específicamente para Adobe Campaign.
1. En las propiedades de contenido, seleccione la **[!UICONTROL Cloud Service]** correspondiente a la instancia de Adobe Campaign.
1. Edite el contenido insertando texto, imágenes, personalización, etc.
1. Valide el contenido.

Para obtener más información, consulte la [documentación detallada](https://docs.adobe.com/docs/en/aem/6-2/author/personalization/adobe-campaign/campaign.html).

![](assets/aem_content.png)

Para recuperar el contenido en Adobe Campaign:

1. Cree un correo electrónico basado en una plantilla de contenido de tipo Adobe Experience Manager.
1. Vincule un contenido creado con Adobe Experience Manager mediante la pantalla de definición de contenido de correo electrónico de Adobe Campaign.

![](assets/aem_linked_content.png)

## Configuración {#configuration}

Para utilizar estas dos soluciones juntas, debe configurarlas para que se conecten entre sí.

1. Configuración de Adobe Campaign. Para ello:

   * Configure una cuenta externa de tipo Adobe Experience Manager.
   * Configure la opción **AEMResourceTypeFilter** , que reconoce los tipos de contenido creados en Adobe Experience Manager para Adobe Campaign.
   * Cree una plantilla de correo electrónico que especifique que es contenido de Adobe Experience Manager y vincule la cuenta externa creada anteriormente a esta plantilla.

1. Configure Adobe Experience Manager. Para ello:

   * Configure la replicación entre las instancias de creación y publicación de Adobe Experience Manager.
   * Connect Adobe Experience Manager to Adobe Campaign by configuring a dedicated **[!UICONTROL Cloud Service]**.

