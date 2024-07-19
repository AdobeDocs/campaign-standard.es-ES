---
title: Uso de activadores en Campaign
description: Cree un evento de déclencheur en Adobe Campaign basado en un déclencheur de Adobe Experience Cloud existente.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 6b8d5118-89ed-49c2-b601-0aff472fcadd
source-git-commit: cf2ded703e53d6db27e62712734f7ea846da9a21
workflow-type: tm+mt
source-wordcount: '736'
ht-degree: 74%

---

# Uso de activadores en Campaign{#using-triggers-in-campaign}

## Creación de un déclencheur asignado en Campaign {#creating-a-mapped-trigger-in-campaign}

>[!NOTE]
>
>Para crear Déclencheur, necesitará el rol **[!UICONTROL Administration]** o para estar en el grupo de seguridad **[!UICONTROL Administrators]**. Para obtener más información, consulte esta [página](../../administration/using/list-of-roles.md).

Debe asegurarse de definir los comportamientos que desea supervisar de antemano en Adobe Experience Cloud (**[!UICONTROL Triggers]** servicio principal). Para obtener más información, consulte la [documentación de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/experience-cloud/triggers/create.html?lang=es). Tenga en cuenta que cuando define el activador, debe activar los alias. Para cada comportamiento (navegación/abandono de formulario, adición/eliminación de productos, sesión caducada, etc.), se debe añadir un nuevo activador en Adobe Experience Cloud.

Ahora tiene que crear un evento de activación en Adobe Campaign basado en un activador de Adobe Experience Cloud existente.

Los pasos para ponerlo en práctica son estos:

1. Haga clic en el logotipo de **Adobe**, en la esquina superior izquierda, y luego seleccione **[!UICONTROL Marketing plans]** > **[!UICONTROL Transactional messages]** > **[!UICONTROL Experience Cloud Triggers]**.

   ![](assets/remarketing_1.png)

1. Haga clic en el botón **[!UICONTROL Create]**. El asistente de creación que se abre muestra la lista de todos los activadores definidos en Adobe Experience Cloud. La columna **[!UICONTROL Fired by Analytics]** muestra el número de eventos enviados por el activador de Adobe Experience Cloud a Campaign. Se trata de una asignación de activadores creados en la interfaz de Experience Cloud.

   ![](assets/remarketing_2.png)

1. Seleccione el activador de Adobe Experience Cloud que desee utilizar y haga clic en **[!UICONTROL Next]**.
1. Configure las propiedades generales del activador. En este paso del asistente, especifique también el canal y la dimensión de segmentación que se deben utilizar para el activador (consulte [Dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources)). A continuación, confirme la creación del activador.
1. Haga clic en el botón situado a la derecha del campo **[!UICONTROL Event content and enrichment]** para ver el contenido de la carga. Esta pantalla también le permite enriquecer los datos de evento con los datos de perfil almacenados en la base de datos de Adobe Campaign. El enriquecimiento se realiza del mismo modo que en un mensaje transaccional estándar.

   ![](assets/remarketing_3.png)

1. En el campo **[!UICONTROL Transactional message validity duration]**, defina la duración durante la cual el mensaje sigue siendo válido después de que Analytics envíe el evento. Si se define una duración de 2 días, el mensaje deja de enviarse después de que haya pasado esa duración. Si pone varios mensajes en espera, esto garantiza que esos mensajes no se envíen si los reanuda después de un periodo de tiempo determinado.

   ![](assets/remarketing_4.png)

1. Ahora puede publicar sus déclencheur. Para obtener más información, consulte [Publicación de un déclencheur en Campaign](../../integrating/using/using-triggers-in-campaign.md#publishing-trigger-in-campaign).

## Publicación de un déclencheur en Campaign {#publishing-trigger-in-campaign}

Después de crear un evento de déclencheur en Adobe Campaign basado en un déclencheur de Adobe Experience Cloud existente, ahora debe publicarlo.

1. Desde el déclencheur creado anteriormente, haga clic en el botón **[!UICONTROL Publish]** para iniciar la publicación del evento de déclencheur.

   ![](assets/trigger_publish_1.png)

1. Puede comprobar el progreso de la publicación de déclencheur en **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_2.png)

1. Cuando finalice la publicación, aparecerá el siguiente mensaje en **[!UICONTROL Publication]**.

   ![](assets/trigger_publish_3.png)

1. Si necesita realizar un cambio en el esquema de activación incluso después de publicar el evento, haga clic en el botón **[!UICONTROL Update schema]** para recuperar los cambios más recientes.

   Tenga en cuenta que esta acción cancela la publicación del activador y del mensaje transaccional, y que se le solicitará que vuelva a publicarlos posteriormente.

   ![](assets/trigger_publish_4.png)

1. El botón **[!UICONTROL Show Trigger in Experience Cloud]** le permite ver la definición del déclencheur en Adobe Experience Cloud.

Una vez publicado el evento, se crea automáticamente una plantilla transaccional vinculada al nuevo evento. Después debe modificar y publicar la plantilla que acaba de crear. Para obtener más información, consulte la sección [Modificación de la plantilla](../../start/using/marketing-activity-templates.md).

## Edición de la plantilla de mensaje transaccional {#editing-the-transactional-message-template}

Una vez creado y publicado el evento de activación, la plantilla transaccional correspondiente se crea automáticamente. Para obtener más información, consulte [Creación de un activador asignado en Campaign](#creating-a-mapped-trigger-in-campaign).

Para que el evento active el envío de un mensaje transaccional, debe personalizar la plantilla, probarla y publicarla. Estos pasos son los mismos que para un mensaje transaccional estándar. Para obtener más información, consulte la sección [Edición de un mensaje transaccional](../../channels/using/editing-transactional-message.md).

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
