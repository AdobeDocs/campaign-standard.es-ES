---
title: Creación de un correo electrónico
description: Siga estos pasos para crear un correo electrónico de un solo envío en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Beginner
exl-id: 4483e469-0a2b-494d-b768-950168759727
source-git-commit: add823f51b0907628ed52cb2f4453743bc939cbf
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 20%

---

# Creación de un correo electrónico{#creating-an-email}

Puede crear un correo electrónico a partir de un [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity), desde Adobe Campaign [página principal](../../start/using/interface-description.md#home-page)o en la variable [lista de actividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities). También puede crear correos electrónicos recurrentes y de un solo envío a partir de un flujo de trabajo.

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#video)

1. Una vez que haya empezado a crear una actividad de marketing por correo electrónico, seleccione la plantilla que desee utilizar.

   De forma predeterminada, puede elegir entre varias plantillas para cada actividad de marketing. Esto le permite preconfigurar ciertos parámetros según sus necesidades y también asignar una marca al envío. Para obtener más información, consulte [Administración de plantillas](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Las plantillas de prueba A/B y de seguimiento están ocultas de forma predeterminada. Marque las casillas en el lado izquierdo ( **[!UICONTROL Filter]** panel lateral) si desea mostrarlos.

1. Introduzca las propiedades generales del correo electrónico. Puede introducir un nombre en la variable **Etiqueta** y edite el ID.

   {{$include /help/_includes/channel-activities-name-id-fields.md}}

   Puede añadir una descripción que el usuario pueda ver en el contenido de la campaña.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puede crear el correo electrónico dentro de una campaña principal desde la página principal o la lista de actividades de marketing. Selecciónela entre las campañas que ya se hayan creado.

1. Defina el destinatario del mensaje en función de los criterios empresariales. Consulte [Acerca de los perfiles](../../audiences/using/about-profiles.md).

   También puede definir los perfiles de prueba que validarán el mensaje. Consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Defina y personalice el contenido del mensaje, el nombre del remitente y el asunto mediante la variable [Diseñador de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md). Para obtener más información, consulte [Acerca del diseño de contenido de correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Puede diseñar el mensaje directamente utilizando una plantilla de contenido predefinida o utilizando Dreamweaver o Adobe Experience Manager. Si no se siente como un diseñador, también puede cargar un contenido que se haya preparado para usted o importar un contenido existente de una dirección URL. Consulte [Selección de contenido existente](../../designing/using/using-existing-content.md).

1. Previsualice el mensaje. Consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md).
1. Confirme el correo electrónico que ha creado.

   >[!NOTE]
   >
   >Para poder guardar el correo electrónico, primero debe realizar algunas modificaciones en el contenido. Si hace clic en **[!UICONTROL Cancel]** en este punto, no completará el asistente y su correo electrónico no se creará.

   A continuación, se muestra el panel de correo electrónico. Permite comprobar el mensaje y [preparar el envío](../../sending/using/preparing-the-send.md).

   La variable **[!UICONTROL Edit properties]** en la esquina superior derecha permite editar las propiedades del correo electrónico. Por ejemplo, puede configurar el correo electrónico para que su etiqueta se calcule en el momento de la preparación del envío.  Los parámetros disponibles se enumeran en [esta sección](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Programe el envío. Consulte [Programación de mensajes](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepare el mensaje para analizar su destinatario. Consulte [Preparación del envío](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Puede establecer reglas globales de fatiga entre canales que excluyan automáticamente los perfiles superpuestos de las campañas. Para obtener más información, consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

1. Envíe pruebas para comprobar y validar el mensaje y supervisar el procesamiento de la bandeja de entrada. Consulte [Envío de prueba](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Envíe el mensaje y compruebe su entrega a través del panel de mensajes y los registros. Consulte [Envío de mensajes](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Mida el impacto del mensaje con los informes de envío. Para obtener más información sobre los informes, consulte [esta sección](../../reporting/using/about-dynamic-reports.md).

**Temas relacionados**:

* [Creación de un correo electrónico personalizado](../../channels/using/key-steps-to-send-a-message.md) guía paso a paso
* [Integración de Adobe Campaign y Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integración con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear un correo electrónico.

>[!VIDEO](https://video.tv.adobe.com/v/23721?quality=12)

Hay disponibles vídeos prácticos adicionales del Campaign Standard [here](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
