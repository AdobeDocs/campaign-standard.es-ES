---
solution: Campaign Standard
product: campaign
title: Uso de activadores en Campaign
description: null
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
translation-type: tm+mt
source-git-commit: a0ad969c86a5047f3f967a21fdc2d6040d7d939f
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 87%

---


# Uso de activadores en Campaign{#using-triggers-in-campaign}

## Creación de un activador asignado en Campaign {#creating-a-mapped-trigger-in-campaign}

Debe asegurarse de definir los comportamientos que desea supervisar de antemano en Adobe Experience Cloud (servicio principal de **[!UICONTROL Triggers]**). Para obtener más información, consulte la [documentación de Adobe Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/activation/triggers.html). Tenga en cuenta que cuando define el activador, debe activar los alias. Para cada comportamiento (navegación/abandono de formulario, adición/eliminación de productos, sesión caducada, etc.), se debe añadir un nuevo activador en Adobe Experience Cloud.

Ahora tiene que crear un evento de activación en Adobe Campaign basado en un activador de Adobe Experience Cloud existente.

Puede ver este [vídeo](https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html#step-two) para comprender mejor cómo se configuran los activadores en Adobe Campaign.

Los pasos para ponerlo en práctica son:

1. Haga clic en el logotipo de **[!UICONTROL Adobe Campaign]**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Haga clic en el botón **[!UICONTROL Create]**. El asistente de creación que se abre muestra la lista de todos los activadores definidos en Adobe Experience Cloud. La columna **[!UICONTROL Fired by Analytics]** muestra el número de eventos enviados por el activador de Adobe Experience Cloud a Campaign. Se trata de una asignación de activadores creados en la interfaz de Experience Cloud.

   ![](assets/remarketing_2.png)

1. Seleccione el activador de Adobe Experience Cloud que desee utilizar y haga clic en **[!UICONTROL Next]**.
1. Configure las propiedades generales del activador. En este paso del asistente, especifique también el canal y la dimensión de segmentación que se deben utilizar para el activador (consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources)). A continuación, confirme la creación del activador.
1. Haga clic en el botón situado a la derecha del campo **[!UICONTROL Event content and enrichment]** para ver el contenido de la carga. Esta pantalla también le permite enriquecer los datos de evento con los datos de perfil almacenados en la base de datos de Adobe Campaign. El enriquecimiento se realiza del mismo modo que en un mensaje transaccional estándar.

   ![](assets/remarketing_3.png)

1. En el campo **[!UICONTROL Transactional message validity duration]**, defina la duración durante la cual el mensaje sigue siendo válido después de que Analytics envíe el evento. Si se define una duración de 2 días, el mensaje deja de enviarse después de que haya pasado esa duración. Si pone varios mensajes en espera, esto garantiza que esos mensajes no se envíen si los reanuda después de un periodo de tiempo determinado.

   ![](assets/remarketing_4.png)

1. Ahora puede publicar sus activadores. Para obtener más información sobre esto, consulte [Publicación de un activador en Campaña](../../integrating/using/using-triggers-in-campaign.md#publishing-trigger-in-campaign).

## Publicación de un activador en la Campaña {#publishing-trigger-in-campaign}

Después de crear un evento desencadenador en Adobe Campaign basado en un activador de Adobe Experience Cloud existente, ahora debe publicarlo.

1. Desde el activador creado anteriormente, haga clic en el botón **[!UICONTROL Publish]** para inicio de publicar el evento desencadenador.

   ![](assets/trigger_publish_1.png)

1. Puede comprobar el progreso de la publicación desencadenadora en **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_2.png)

1. Cuando se haya realizado la publicación, el siguiente mensaje aparecerá en **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_3.png)

1. Si necesita realizar un cambio en el esquema de activación incluso después de publicar el evento, haga clic en el botón **[!UICONTROL Update schema]** para recuperar los cambios más recientes.

   Tenga en cuenta que esta acción cancela la publicación del activador y del mensaje transaccional, y que se le solicitará que vuelva a publicarlos posteriormente.

   ![](assets/trigger_publish_4.png)

1. Haga clic en el botón **[!UICONTROL Show Trigger in Experience Cloud]** para poder vista de la definición del activador en Adobe Experience Cloud.

Una vez publicado el evento, se crea automáticamente una plantilla transaccional vinculada al nuevo evento. Después debe modificar y publicar la plantilla que acaba de crear. Para obtener más información, consulte la sección [Modificación de la plantilla](../../start/using/marketing-activity-templates.md).

## Modificación de la plantilla de mensaje transaccional {#editing-the-transactional-message-template}

Una vez creado y publicado el evento de activación, la plantilla transaccional correspondiente se crea automáticamente. Para obtener más información, consulte [Creación de un activador asignado en Campaign](#creating-a-mapped-trigger-in-campaign).

Para que el evento active el envío de un mensaje transaccional, debe personalizar la plantilla, probarla y publicarla. Estos pasos son los mismos que para un mensaje transaccional estándar. Para obtener más información, consulte la sección [Plantilla transaccional](../../channels/using/event-transactional-messages.md#personalizing-a-transactional-message).

>[!NOTE]
>
>Si cancela la publicación de la plantilla, se cancela también y automáticamente la publicación del evento de activación.

Al editar contenido, puede añadir un campo de personalización basado en la información enviada por el activador de Analytics. Si enriquece los datos de evento con datos de perfil de Adobe Campaign, puede personalizar el mensaje en función de esta información. Para personalizar el mensaje, seleccione **[!UICONTROL Transactional event]** > **[!UICONTROL Event context]** y elija un campo.

![](assets/remarketing_8.png)

## Acceso a los informes {#accessing-the-reports}

Para ver el informe de activación en Adobe Campaign, abra el evento de activación que ha creado anteriormente y haga clic en **[!UICONTROL Show trigger report]**.

![](assets/remarketing_9.png)

El informe muestra el número de eventos procesados en comparación con el número de eventos enviados por Analytics. También muestra una lista de todos los activadores recientes.

![](assets/trigger_uc_browse_14.png)

