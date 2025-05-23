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
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 15%

---

# Creación de un correo electrónico{#creating-an-email}

Puede crear un mensaje de correo electrónico a partir de una [campaña](../../start/using/marketing-activities.md#creating-a-marketing-activity), desde la [página de inicio](../../start/using/interface-description.md#home-page) de Adobe Campaign o desde la [lista de actividades de marketing](../../start/using/marketing-activities.md#about-marketing-activities). También puede crear correos electrónicos recurrentes y de un solo envío a partir de un flujo de trabajo.

![](assets/do-not-localize/how-to-video.png) [Descubra esta funcionalidad en vídeo](#video)

1. Una vez que haya empezado a crear una actividad de marketing por correo electrónico, seleccione la plantilla que desee utilizar.

   De forma predeterminada, puede elegir entre varias plantillas para cada actividad de marketing. Esto le permite preconfigurar ciertos parámetros según sus necesidades y también asignar una marca a su envío. Para obtener más información, consulte [Administración de plantillas](../../start/using/marketing-activity-templates.md).

   ![](assets/email_creation_1.png)

   >[!NOTE]
   >
   >Las plantillas de prueba A/B y de seguimiento están ocultas de forma predeterminada. Marque las casillas del lado izquierdo (panel lateral **[!UICONTROL Filter]**) si desea mostrarlas.

1. Introduzca las propiedades generales del correo electrónico. Puede escribir un nombre en el campo **Etiqueta** y editar el identificador.

   >[!NOTE]
   >
   >Tanto el nombre de la actividad como su ID aparecen en la interfaz, pero no son visibles para los destinatarios de mensajes.
   >
   >Asegúrese de que el campo ID no contenga ningún espacio en blanco para evitar discrepancias, por ejemplo, al integrarse con Adobe Analytics.

   Puede añadir una descripción que el usuario pueda ver en el contenido de la campaña.

   ![](assets/email_creation_2.png)

   >[!NOTE]
   >
   >Puede crear su correo electrónico dentro de una campaña principal desde la página principal o la lista de actividades de marketing. Selecciónelo entre las campañas que ya se han creado.

1. Defina el destinatario del mensaje en función de los criterios empresariales. Ver [Acerca de los perfiles](../../audiences/using/about-profiles.md).

   También puede definir los perfiles de prueba que validarán el mensaje. Consulte [Administración de perfiles de prueba](../../audiences/using/managing-test-profiles.md).

   ![](assets/email_creation_3.png)

1. Defina y personalice el contenido del mensaje, el nombre del remitente y el asunto con [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md). Para obtener más información, consulte [Acerca del diseño del contenido del correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/email_creation_4.png)

   Puede diseñar el mensaje directamente con una plantilla de contenido predefinida o con Dreamweaver o Adobe Experience Manager. Si no se siente como un diseñador, también puede cargar un contenido que se haya preparado para usted o importar un contenido existente de una dirección URL. Consulte [Selección de contenido existente](../../designing/using/using-existing-content.md).

1. Previsualice el mensaje. Consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md).
1. Confirme el correo electrónico que ha creado.

   >[!NOTE]
   >
   >Para poder guardar el correo electrónico, primero debe realizar algunas ediciones en el contenido. Si hace clic en **[!UICONTROL Cancel]** en este momento, no completará el asistente y no se creará el correo electrónico.

   A continuación, se muestra el panel de correo electrónico. Le permite comprobar el mensaje y [preparar el envío](../../sending/using/preparing-the-send.md).

   El botón **[!UICONTROL Edit properties]** en la esquina superior derecha le permite editar las propiedades del correo electrónico. Por ejemplo, puede configurar el correo electrónico para que su etiqueta se calcule en el momento de la preparación de la entrega.  Los parámetros disponibles se enumeran en [esta sección](../../administration/using/configuring-email-channel.md#list-of-email-properties).

   ![](assets/delivery_dashboard_2.png)

1. Programe el envío. Consulte [Programación de mensajes](../../sending/using/about-scheduling-messages.md).

   ![](assets/delivery_planning.png)

1. Prepare el mensaje para analizar su destinatario. Ver [Preparando el envío](../../sending/using/confirming-the-send.md).

   ![](assets/preparing_delivery_2.png)

   >[!NOTE]
   >
   >Puede establecer reglas globales de fatiga entre canales que excluyan automáticamente los perfiles superpuestos de las campañas. Para obtener más información, consulte [Reglas de fatiga](../../sending/using/fatigue-rules.md).

1. Envíe pruebas para comprobar y validar el mensaje y supervisar el procesamiento de la bandeja de entrada. Consulte [Envío de prueba](../../sending/using/sending-proofs.md).

   ![](assets/bat_select.png)

1. Envíe el mensaje y compruebe su entrega a través del panel de mensajes y los registros. Consulte [Envío de mensajes](../../sending/using/confirming-the-send.md).

   ![](assets/confirm_delivery.png)

1. Mida el impacto del mensaje con informes de envío. Para obtener más información sobre los informes, consulte [esta sección](../../reporting/using/about-dynamic-reports.md).

**Temas relacionados**:

* [Creación de un correo electrónico personalizado](../../channels/using/key-steps-to-send-a-message.md) guía paso a paso
* [Integración de Adobe Campaign y Dreamweaver](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)
* [Integración con Adobe Experience Manager](../../integrating/using/integrating-with-experience-manager.md)

## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear un correo electrónico.

>[!VIDEO](https://video.tv.adobe.com/v/29750?quality=12&captions=spa)

Hay disponibles [más vídeos de procedimientos para el Campaign Standard aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
