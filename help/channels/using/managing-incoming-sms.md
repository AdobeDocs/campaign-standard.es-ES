---
title: Administración de SMS entrantes
description: Conozca cómo administrar STOP SMS y almacenar los SMS entrantes en Adobe Campaign.
page-status-flag: never-activated
uuid: f063052b-96ef-41b6-bf1b-4006de73f0b9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: sms-messages
discoiquuid: ee1970e6-1ced-46e0-94e6-8337768300ee
delivercontext-tags: delivery,smsContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f15e28bed22e3defb29f16875fcf4c07f4af5a3
workflow-type: tm+mt
source-wordcount: '594'
ht-degree: 8%

---


# Administración de SMS entrantes{#managing-incoming-sms}

## Administración de SMS STOP {#managing-stop-sms}

Cuando un perfil responde a un mensaje SMS enviado por Campaign, puede configurar los mensajes que se le envían automáticamente, así como la acción que se va a realizar.

Esta configuración se define en la **[!UICONTROL Automatic reply sent to the MO]** sección de la cuenta externa [de Enrutamiento](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)SMS. MO significa &#39;Mobile Originated&#39;, lo que significa que puedes configurar una respuesta automática al móvil que envió el SMS.

Para ello:

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration > Application settings > External accounts]** then the **[!UICONTROL SMS routing via SMPP]** external account.
1. En la **[!UICONTROL Automatic reply sent to the MO]** categoría, haga clic en **[!UICONTROL Create element]** para configurar su respuesta automática en inicio.

   ![](assets/sms_mo_1.png)

1. Elija la palabra clave que activará esta respuesta automática. Las palabras clave no distinguen entre mayúsculas y minúsculas. Por ejemplo: si los destinatarios envían la palabra clave &quot;STOP&quot;, recibirán la respuesta automática.

   Deje esta columna vacía si desea enviar la misma respuesta sin importar la palabra clave.

   ![](assets/sms_mo_2.png)

1. En el **[!UICONTROL Short code]** campo, especifique un número que se utilice normalmente para enviar envíos y que servirá como nombre del remitente. También puede decidir dejar la **[!UICONTROL Short code]** columna vacía, para enviar la misma respuesta sin importar el código corto.

   ![](assets/sms_mo_4.png)

1. Escriba la respuesta que desee enviar a sus destinatarios en el campo **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. Por ejemplo, esto le permite quitar de la cuarentena el número de teléfono de un usuario que responde con un mensaje que no sea &quot;STOP&quot;.

   ![](assets/sms_mo_3.png)

1. En el **[!UICONTROL Additional action]** campo, vincule una acción a la respuesta automática:

   * La **[!UICONTROL Send to quarantine]** acción cuarentena automáticamente el número de teléfono de perfil.
   * La **[!UICONTROL Remove from quarantine]** acción elimina el número de teléfono de perfil de la cuarentena.
   * La **[!UICONTROL None]** acción le permite enviar el mensaje únicamente a sus destinatarios sin realizar ninguna acción.

   Por ejemplo: en la configuración siguiente, si los destinatarios envían la palabra clave &quot;STOP&quot;, recibirán automáticamente una confirmación baja y su número de teléfono se enviará a la cuarentena con el **[!UICONTROL Denylisted]** estado. Este estado hace referencia únicamente al número de teléfono; el perfil se incluida en la lista de bloqueados para que el usuario siga recibiendo mensajes de correo electrónico.

   ![](assets/sms_mo.png)

Sus destinatarios ahora pueden cancelarse automáticamente la suscripción a sus mensajes y enviarse a cuarentena con esta respuesta automática. The quarantined recipients are listed in the **[!UICONTROL Addresses]** table available through the **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]** menu. For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Estos SMS entrantes se pueden almacenar si es necesario. For more information on this, refer to this [section](#storing-incoming-sms).

## Almacenamiento de SMS entrantes {#storing-incoming-sms}

En la **[!UICONTROL SMS routing via SMPP]** cuenta externa, puede elegir almacenar los mensajes entrantes, por ejemplo, cuando un suscriptor responde &quot;STOP&quot; a un mensaje SMS para ser eliminado de sus listas de destinatario.

![](assets/sms_config_mo_1.png)

Al registrar **[!UICONTROL Store incoming MO in the database]** la **[!UICONTROL SMPP channel settings]** categoría, todos los SMS se almacenarán en la tabla en SMS y se podrán recuperar mediante una actividad de consulta en un flujo de trabajo.

Para ello:

1. In the **[!UICONTROL SMPP channel settings]** field, check **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. In the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleccione el tipo de flujo de trabajo.
1. Edite las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Drag and drop a **[!UICONTROL Query]** activity and double-click the activity.
1. En la **[!UICONTROL Properties]** ficha de la consulta, elija **[!UICONTROL Incoming SMS (inSMS)]** en el **[!UICONTROL Resource]** campo.

   ![](assets/sms_config_mo_4.png)

1. A continuación, en la **[!UICONTROL Target]** ficha, arrastre y suelte la **[!UICONTROL Incoming SMS attributes]** regla.

   ![](assets/sms_config_mo_5.png)

1. En este caso, deseamos destinatario de todos los mensajes entrantes del día anterior. In the **[!UICONTROL Field]** category, select **[!UICONTROL Creation date (created)]**.
1. En **[!UICONTROL Filter type]**, seleccione **[!UICONTROL Relative]** luego en **[!UICONTROL Level of precision]**, elija **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Luego puede elegir recuperar datos de hoy, el día anterior o los últimos días. Haga clic **[!UICONTROL Confirm]** cuando la consulta esté configurada.

Esta consulta recuperará cada mensaje STOP recibido en función del intervalo de tiempo seleccionado.

La actividad le permite, por ejemplo, construir una población y personalizar mejor sus envíos.
