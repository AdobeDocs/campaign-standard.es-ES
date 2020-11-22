---
solution: Campaign Standard
product: campaign
title: Creación de un correo electrónico
description: Siga estos pasos para crear un correo electrónico de un solo envío en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '549'
ht-degree: 22%

---


# Creación de un correo electrónico{#creating-an-email}

You can create an email from a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity), from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), or in the [marketing activity list](../../start/using/marketing-activities.md#about-marketing-activities). También puede crear correos electrónicos recurrentes y de un solo envío a partir de un flujo de trabajo.

1. Una vez que haya empezado a crear una actividad de marketing por correo electrónico, seleccione la plantilla que desee utilizar.

   De forma predeterminada, puede elegir entre varias plantillas para cada actividad de mercadotecnia. Esto le permite preconfigurar ciertos parámetros según sus necesidades y también asignar una marca al envío. For more on this, see [Managing templates](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Las plantillas de prueba A/B y de seguimiento están ocultas de forma predeterminada. Marque las casillas del lado izquierdo (panel **[!UICONTROL Filter]** lateral) si desea mostrarlas.

1. Introduzca las propiedades generales del correo electrónico. You can enter a name in the **Label** field and edit the ID. Tanto el nombre de la actividad como su ID aparecen en la interfaz, pero no son visibles para los destinatarios de mensajes.

   Puede añadir una descripción que el usuario pueda ver en el contenido de la campaña.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puede crear el correo electrónico dentro de una campaña principal desde la página de inicio o la lista de actividades de marketing. Selecciónelo entre las campañas que ya se han creado.

1. Defina el destinatario del mensaje en función de los criterios comerciales. See [About profiles](../../audiences/using/about-profiles.md).

   También puede definir los perfiles de prueba que validarán el mensaje. Consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Defina y personalice el contenido del mensaje, el nombre del remitente y el asunto mediante el Diseñador de [correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md). For more on this, see [About email content design](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Puede diseñar el mensaje directamente con una plantilla de contenido predefinida o con Dreamweaver o Adobe Experience Manager. Si no se siente como un diseñador, también puede cargar un contenido preparado para usted o importar un contenido existente desde una dirección URL. Consulte [Selección de contenido existente](../../designing/using/using-existing-content.md).

1. Previsualice el mensaje. Consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md).
1. Confirme el correo electrónico que ha creado.

   >[!NOTE]
   >
   >Para poder guardar el correo electrónico, primero debe realizar algunas modificaciones en el contenido. Si hace clic **[!UICONTROL Cancel]** en este punto, no completará el asistente y su correo electrónico no se creará.

   A continuación, se muestra el panel de correo electrónico. Le permite comprobar su mensaje y [preparar el envío](../../sending/using/preparing-the-send.md).

   El **[!UICONTROL Edit properties]** botón situado en la esquina superior derecha permite editar las propiedades del correo electrónico. Por ejemplo, puede configurar el correo electrónico para que su etiqueta se calcule en el momento de la preparación del envío.  Available parameters are listed in [this section](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Programe el envío. Consulte [Programación de mensajes](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepare el mensaje para analizar su destinatario. See [Preparing the send](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Puede establecer reglas globales de fatiga entre canales que excluyan automáticamente los perfiles superpuestos de las campañas. For more on this, see [Fatigue rules](../../sending/using/fatigue-rules.md).

1. Envíe pruebas para comprobar y validar el mensaje y supervisar el procesamiento de la bandeja de entrada. Consulte [Envío de prueba](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Envíe el mensaje y compruebe su envío a través del panel de mensajes y los registros. Consulte [Envío de mensajes](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Mida el impacto del mensaje con informes de envío. For more on reporting, see [this section](../../reporting/using/about-dynamic-reports.md).

**Temas relacionados**:

* Vídeo de la [Creación de un correo electrónico](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/create-email-from-homepage.html)
* [Creación de una guía paso a paso de correo electrónico](https://helpx.adobe.com/es/campaign/kb/acs-get-started-with-emails.html) personalizada
* [Vídeo de integración](https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/designing-content/email-designer/dreamweaver-integration.translate.html) de Adobe Campaign y Dreamweaver
* [Integración con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)
