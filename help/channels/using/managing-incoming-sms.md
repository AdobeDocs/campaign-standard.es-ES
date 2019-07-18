---
title: Administración de SMS entrante
seo-title: Administración de SMS entrante
description: Administración de SMS entrante
seo-description: Descubra cómo administrar STOP SMS y almacenar SMS entrante en Adobe Campaign.
page-status-flag: no activado nunca
uuid: f 063052 b -96 ef -41 b 6-bf 1 b -4006 de 73 f 0 b 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: sms-messages
discoiquuid: ee 1970 e 6-1 ated -46 e 0-94 e 6-8337768300 ee ee
delivercontext-tags: entrega, smscontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Managing incoming SMS{#managing-incoming-sms}

## Managing STOP SMS {#managing-stop-sms}

Cuando un perfil responde a un mensaje SMS que se envió mediante Campaign, puede configurar los mensajes que se devuelven automáticamente a él, así como la acción que se realizará.

This configuration is defined in the **[!UICONTROL Automatic reply sent to the MO]** section of the [SMS Routing external account](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO representa'Mobile Originated ', lo que significa que puede configurar una respuesta automática al dispositivo móvil que envió el SMS.

Para ello:

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. Under the **[!UICONTROL Automatic reply sent to the MO]** category, click **[!UICONTROL Create element]** to start configuring your automatic reply.

   ![](assets/sms_mo_1.png)

1. Elija la palabra clave que activará esta respuesta automática. Las palabras clave no distinguen mayúsculas de minúsculas. Por ejemplo, si los destinatarios envían la palabra clave "STOP", recibirán la respuesta automática.

   Deje vacía esta columna si desea enviar la misma respuesta sin importar cuál sea la palabra clave.

   ![](assets/sms_mo_2.png)

1. In the **[!UICONTROL Short code]** field, specify a number that is usually used to send deliveries and will serve as a sender name. You can also decide to leave the **[!UICONTROL Short code]** column empty, to send the same reply no matter what the short code.

   ![](assets/sms_mo_4.png)

1. Type in the answer you want to send to your recipients in the field **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. Por ejemplo, esto permite eliminar de cuarentena el número de teléfono de un usuario que responde con un mensaje distinto de "STOP".

   ![](assets/sms_mo_3.png)

1. In the **[!UICONTROL Additional action]** field, link an action to your automatic reply:

   * **[!UICONTROL Send to quarantine]** La acción coloca automáticamente en cuarentena el número de teléfono del perfil.
   * The **[!UICONTROL Remove from quarantine]** action removes the profile phone number from quarantine.
   * The **[!UICONTROL None]** action allows you to only send the message to your recipients without carrying an action.
   For example, in the configuration below, if recipients send the keyword "STOP", they will automatically receive an unsubscription confirmation and their phone number will be sent to quarantine with the **[!UICONTROL Blacklisted]** status. Este estado solo se refiere al número de teléfono, el perfil no está bloqueado para que el usuario siga recibiendo mensajes de correo electrónico.

   ![](assets/sms_mo.png)

Ahora, los destinatarios pueden cancelarse de forma automática a sus mensajes y enviarse a cuarentena con esta respuesta automática. The quarantined recipients are listed in the **[!UICONTROL Addresses]** table available through the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** menu. For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Estos SMS entrantes se pueden almacenar si es necesario. For more information on this, refer to this [section](../../channels/using/managing-incoming-sms.md#storing-incoming-sms).

## Storing incoming SMS {#storing-incoming-sms}

In the **[!UICONTROL SMS routing via SMPP]** external account, you can choose to store incoming messages for example when a subscriber replies "STOP" to an SMS message in order to be removed from your recipient lists.

![](assets/sms_config_mo_1.png)

By checking **[!UICONTROL Store incoming MO in the database]** in the **[!UICONTROL SMPP channel settings]** category, all SMS will be stored in the inSMS table and can be retrieved via a query activity in a workflow.

Para ello:

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleccione el tipo de flujo de trabajo.
1. Edit the properties of your workflow, then click **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. In the **[!UICONTROL Properties]** tab of the query, choose **[!UICONTROL Incoming SMS (inSMS)]** in the **[!UICONTROL Resource]** field.

   ![](assets/sms_config_mo_4.png)

1. Then, in the **[!UICONTROL Target]** tab, drag and drop the **[!UICONTROL Incoming SMS attributes]** rule.

   ![](assets/sms_config_mo_5.png)

1. Aquí, queremos enfocar cada mensaje entrante del día anterior. In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. In **[!UICONTROL Filter type]**, select **[!UICONTROL Relative]** then in **[!UICONTROL Level of precision]**, choose **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Luego puede elegir recuperar datos de hoy, el día anterior o los últimos días. Click **[!UICONTROL Confirm]** when your query is configured.

Esta consulta recuperará cada mensaje STOP recibido según el intervalo de tiempo elegido.

La actividad le permite, por ejemplo, crear una población y personalizar mejor sus envíos.
