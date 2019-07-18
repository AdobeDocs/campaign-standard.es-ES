---
title: Creación de un mensaje SMS
seo-title: Creación de un mensaje SMS
description: Creación de un mensaje SMS
seo-description: Siga estos pasos para crear un mensaje SMS de envío único en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 591 ae 97 e -2 d 19-4 f 93-be 4 b-d 8 d 20 f 1 d 2 d 12
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: sms-messages
discoiquuid: b 27381 a 9-19 e 5-4 b 65-b 194-c 72 f 475 ba 54 d
delivercontext-tags: Deliverycreation, wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: d50d486ed77cb7989df47133bb49fde3227ae3a5

---


# Creating an SMS message{#creating-an-sms-message}

La creación de una entrega SMS es muy similar a la creación de un correo electrónico normal. Los pasos siguientes describen la configuración específica de este canal. Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

Advanced SMS parameters are detailed in the [SMS configuration](../../administration/using/configuring-sms-channel.md) section.

Para crear y enviar mensajes SMS a un teléfono móvil, necesita:

* A **[!UICONTROL Routing]** external account configured on the **[!UICONTROL Mobile (SMS)]** channel with the **[!UICONTROL Bulk delivery]** mode. For more on this, refer to the [Routing](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) section.
* Una plantilla de envío que está correctamente vinculada a esta cuenta externa.

1. Cree un envío SMS. You can do it from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in the [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   También puede agregar una actividad de SMS en un flujo de trabajo. For more on this, refer to the [Workflows](../../automating/using/sms-delivery.md) guide.

   Al crear un mensaje, se muestra un asistente para indicarle los pasos más importantes. Lo que se define a través del asistente puede editarse posteriormente desde el panel de mensajes.

1. Seleccione la plantilla que desee utilizar. Puede elegir la plantilla SMS predeterminada o una de sus propias plantillas.

   ![](assets/sms_creation_1.png)

   Para entregar a un teléfono móvil, la plantilla de envío debe estar correctamente vinculada a la cuenta externa de enrutamiento SMS.

1. Introduzca las propiedades generales del SMS.

   ![](assets/sms_creation_2.png)

   Tanto la etiqueta de actividad como su ID aparecen en la interfaz, pero no son visibles para los destinatarios del mensaje.

1. Especifique la audiencia a la que desee dirigir. Puede seleccionar una audiencia existente o dirigirse directamente a una población definiendo y combinando reglas.

   ![](assets/sms_creation_3.png)

1. Agregue contenido al SMS. You can also define the content by clicking the **[!UICONTROL Content]** section of the delivery dashboard, once the SMS creation is finalized. See [About SMS content design](../../designing/using/about-sms-and-push-content-design.md).

   Si ha insertado campos de personalización o texto condicional en el contenido del mensaje SMS, la longitud del mensaje puede variar de un destinatario a otro. De hecho, estos factores pueden introducir caracteres que la codificación GSM no tenga en cuenta. Por este motivo, la longitud del mensaje debe evaluarse una vez completada la personalización. See [Personalizing SMS messages](../../channels/using/personalizing-sms-messages.md).

   ![](assets/sms_creation_4.png)

1. Confirme la creación del mensaje. Se muestra su tablero.
1. Programe el envío. El SMS se puede enviar manualmente después de la preparación del mensaje o automáticamente a una fecha programada. See [Scheduling messages](../../sending/using/about-scheduling-messages.md).
1. Prepare el mensaje para analizar su validez, personalización y objetivo.

   ![](assets/sms_creation_6.png)

   >[!NOTE]
   >
   >Puede establecer reglas globales de fatiga de canales múltiples que excluyan automáticamente perfiles sobresoltados de las campañas. See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Envíe pruebas para comprobar y validar el mensaje y controlar su representación de bandeja de entrada. See the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Confirme el envío del mensaje. El envío se iniciará de acuerdo con la programación definida.

   ![](assets/sms_creation_7.png)

Se envía el mensaje. Puede comprobar su entrega a través del panel de mensajes y registros.

Una vez que haya terminado el envío, puede empezar a medir el impacto del mensaje con los informes de entrega integrados o integrados.

**Temas relacionados:**

* [Acerca de SMS y edición de contenido push](../../designing/using/about-sms-and-push-content-design.md)
* [Administración de plantillas](../../start/using/about-templates.md)
* [Creación de un vídeo de envío](https://helpx.adobe.com/campaign/kt/acs/using/acs-creating-a-sms-delivery-feature-video-use.html) SMS

