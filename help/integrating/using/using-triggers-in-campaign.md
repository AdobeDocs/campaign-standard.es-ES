---
title: Uso de activadores en Campaign
seo-title: Uso de activadores en Campaign
description: Uso de activadores en Campaign
seo-description: null
page-status-flag: no activado nunca
uuid: d 844 d 013-b 38 a -4 e 69-9 df 5-0 edc 01 fa 9 c 6 e
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: trabajar con campaña y activadores
discoiquuid: a 524 c 700-bad 6-4 fcf -857 a-c 31 bfae 4 d 30 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Using Triggers in Campaign{#using-triggers-in-campaign}

## Creating a mapped trigger in Campaign {#creating-a-mapped-trigger-in-campaign}

You should make sure to define the behaviors that you want to monitor beforehand in Adobe Experience Cloud ( **[!UICONTROL Triggers]** core service). For more on this, refer to the [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html). Tenga en cuenta que al definir el activador, debe activar los alias. Para cada comportamiento (navegación/abandono de formulario, adición/eliminación de productos, sesión caducada, etc.), se debe agregar un nuevo activador en Adobe Experience Cloud.

Ahora tiene que crear un evento desencadenador en Adobe Campaign basado en un activador de Adobe Experience Cloud existente.

You can watch this [video](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) to help you understand how triggers are set up in Adobe Campaign.

Los pasos para colocar esto son:

1. Click the **[!UICONTROL Adobe Campaign]** logo, in the top left corner, then select **[!UICONTROL Marketing plans]** &gt; **[!UICONTROL Transactional messages]** &gt; **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Click the **[!UICONTROL Create]** button. El asistente para creación que abre muestra la lista de todos los activadores definidos en Adobe Experience Cloud. The **[!UICONTROL Fired by Analytics]** column displays the number of events sent by the Adobe Experience Cloud trigger to Campaign. Se trata de la asignación de activadores creados en la interfaz de Experience Cloud.

   ![](assets/remarketing_2.png)

1. Select the Adobe Experience Cloud trigger that you want to use and click **[!UICONTROL Next]**.
1. Configure las propiedades generales del activador. At this step of the wizard, also specify the channel and the targeting dimension to use for the trigger (see [targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources)). A continuación, confirme la creación del activador.
1. Click the button to the right of the **[!UICONTROL Event content and enrichment]** field to view the content of the payload. Esta pantalla también permite enriquecer los datos de eventos con datos de perfil almacenados en la base de datos de Adobe Campaign. El enriquecimiento se realiza de la misma manera que para un mensaje de transacción estándar.

   ![](assets/remarketing_3.png)

1. In the **[!UICONTROL Transactional message validity duration]** field, define the duration for which the message will stay valid after the event is sent by Analytics. Si se define una duración de 2 días, el mensaje ya no se enviará después de que haya transcurrido esa duración. Si coloca varios mensajes en espera, esto garantiza que esos mensajes no se envíen si se reanudan después de un determinado período de tiempo.

   ![](assets/remarketing_4.png)

1. If a propensity scoring is defined in Analytics (see the [Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/insight/client/c_visitor_propensity.html)), you can choose not to send the message if the customer has a high probability of coming back to the website in the near future. El contenido de la puntuación y el umbral están disponibles en el contenido de la carga útil para que pueda utilizar esos valores para personalizar el mensaje. Para utilizar esta opción, marque la casilla en la parte inferior de la pantalla. Los clientes con una fuerte probabilidad de regresar al sitio próximamente no recibirán ningún mensaje.
1. Click the **[!UICONTROL Publish]** button to start publishing the trigger event.
1. If you need to make a change in your trigger schema even after publishing your trigger event, click the **[!UICONTROL Update schema]** button to retrieve the latest changes.

   Tenga en cuenta que esta acción cancelará la publicación del activador y el mensaje de transacción, por lo que será necesario volver a publicarlos posteriormente.

   ![](assets/remarketing_11.png)

The **[!UICONTROL Show Trigger in Experience Cloud]** button allows you to view the trigger definition in Adobe Experience Cloud.

Una vez publicada el evento, se crea automáticamente una plantilla transaccional vinculada al nuevo evento. A continuación, debe modificar y publicar la plantilla que acaba de crear. For more on this, refer to the [Editing the template](../../start/using/about-templates.md) section.

## Editing the transactional message template {#editing-the-transactional-message-template}

Una vez creado y publicado el evento de desencadenador, la plantilla transaccional correspondiente se crea automáticamente. For more on this, refer to the [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign) section.

Para que el evento active enviar un mensaje de transacción, debe personalizar la plantilla, luego probarla y publicarla. Estos pasos son los mismos que para un mensaje transaccional estándar. For more on this, refer to the [Transactional template](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message) section.

>[!NOTE]
>
>Si cancela la publicación, cancelará automáticamente el evento desencadenador.

Al editar contenido, puede agregar un campo de personalización basado en la información enviada por el activador de Analytics. Si enriquece los datos del evento con los datos de perfil de Adobe Campaign, puede personalizar el mensaje según esta información. To personalize your message, select **[!UICONTROL Transactional event]** &gt; **[!UICONTROL Event context]** and select a field.

![](assets/remarketing_8.png)

## Accessing the reports {#accessing-the-reports}

To view the dedicated trigger report in Adobe Campaign, open the trigger event that you previously created, and click **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

El informe muestra el número de eventos procesados en comparación con el número de eventos enviados por Analytics. También muestra una lista de todos los desencadenadores recientes.

![](assets/trigger_uc_browse_14.png)

