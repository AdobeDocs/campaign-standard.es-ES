---
title: Creación de un mensaje SMS
description: Siga estos pasos para crear un mensaje SMS de un solo envío en Adobe Campaign.
page-status-flag: never-activated
uuid: 591ae97e-2d19-4f93-be4b-d8d20f1d2d12
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: b27381a9-19e5-4b65-b194-c72f475ba54d
delivercontext-tags: deliveryCreation,wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d8a46a53f2abd453aaf0ff8322b7f9b942ec1c6

---


# Creación de un mensaje SMS{#creating-an-sms-message}

Crear una entrega de SMS es muy similar a crear un correo electrónico normal. Los pasos siguientes describen la configuración específica de este canal. Consulte [Creación de un correo electrónico](../../channels/using/creating-an-email.md) para obtener más información sobre otras opciones.

Los parámetros avanzados de SMS se detallan en la sección de configuración [de](../../administration/using/configuring-sms-channel.md) SMS.

Para crear y enviar mensajes SMS a un teléfono móvil, necesita:

* Cuenta **[!UICONTROL Routing]**externa configurada en el**[!UICONTROL Mobile (SMS)]** canal con el **[!UICONTROL Bulk delivery]**modo. For more on this, refer to the[Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)section.
* Una plantilla de entrega que está correctamente vinculada a esta cuenta externa.

1. Crear un envío de SMS. Puede hacerlo desde la página [de](../../start/using/interface-description.md#home-page)inicio de Adobe Campaign, en una [campaña](../../start/using/marketing-activities.md#creating-a-marketing-activity) o en la lista [de actividades de](../../start/using/programs-and-campaigns.md#creating-a-campaign)marketing.

   También puede agregar una actividad de SMS en un flujo de trabajo. For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   Al crear un mensaje, se muestra un asistente para guiarle por los pasos más importantes. Lo que se define a través del asistente se puede editar posteriormente desde el tablero de mensajes.

1. Seleccione la plantilla que desee utilizar. Puede elegir la plantilla de SMS lista para usar o una de sus propias plantillas.

   ![](assets/sms_creation_1.png)

   Para realizar envíos a un teléfono móvil, la plantilla de envío debe estar correctamente vinculada a la cuenta externa de enrutamiento SMS.

1. Introduzca las propiedades generales del SMS.

   ![](assets/sms_creation_2.png)

   Tanto la etiqueta de actividad como su ID aparecen en la interfaz, pero no son visibles para los destinatarios del mensaje.

1. Especifique la audiencia a la que desea dirigirse. Puede seleccionar una audiencia existente o dirigirse directamente a una población definiendo y combinando reglas.

   ![](assets/sms_creation_3.png)

1. Agrega contenido a tu SMS. También puede definir el contenido haciendo clic en la sección **[!UICONTROL Content]**del panel de envío, una vez que se haya finalizado la creación de SMS. Consulte[Acerca del diseño](../../channels/using/about-sms-and-push-content-design.md)de contenido SMS.

   Si ha insertado campos de personalización o texto condicional en el contenido de su mensaje SMS, la longitud del mensaje puede variar de un destinatario a otro. de hecho, estos factores pueden introducir caracteres que no se tienen en cuenta en la codificación GSM. Por este motivo, la longitud del mensaje debe evaluarse una vez realizada la personalización. See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Confirme la creación del mensaje. A continuación, se muestra su tablero.
1. Programe el envío. El SMS se puede enviar manualmente inmediatamente después de la preparación del mensaje o automáticamente en una fecha programada. Consulte [Programación de mensajes](../../sending/using/about-scheduling-messages.md).
1. Prepare el mensaje para analizar su validez, personalización y destino.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Puede establecer reglas de fatiga globales entre canales que excluyan automáticamente perfiles superpuestos de las campañas. Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md).

1. Envíe pruebas para comprobar y validar el mensaje y supervisar el procesamiento de la bandeja de entrada. Consulte la sección [Prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) de envío.
1. Confirme el envío del mensaje. El envío empezará según la programación que haya definido.

   ![](assets/sms_creation_7.png)

Se envía el mensaje. Puede comprobar su entrega a través del tablero de mensajes y los registros.

Una vez finalizado el envío, puede empezar a medir el impacto del mensaje con informes de envío integrados o personalizados.

**Temas relacionados:**

* [Acerca de SMS y push content edition](../../channels/using/about-sms-and-push-content-design.md)
* [Administración de plantillas](../../start/using/marketing-activity-templates.md)
* [Creación de un vídeo de envío](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/sms/sms-delivery.html) SMS

