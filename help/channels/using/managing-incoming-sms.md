---
title: Administración de SMS entrantes
description: Obtenga información sobre cómo administrar STOP SMS y almacenar los mensajes de texto entrantes en Adobe Campaign.
page-status-flag: nunca activado
uuid: f063052b-96ef-41b6-bf1b-4006de73f0b9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: sms-messages
discoiquuid: ee1970e6-1ced-46e0-94e6-8337768300ee
delivercontext-tags: entrega,smsContent,retroceso
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Administración de SMS entrantes{#managing-incoming-sms}

## Administración de SMS STOP {#managing-stop-sms}

Cuando un perfil responde a un mensaje SMS que se envió mediante Campaign, puede configurar los mensajes que se le envían automáticamente, así como la acción que se va a realizar.

Esta configuración se define en la **[!UICONTROL Automatic reply sent to the MO]** sección de la cuenta [externa de enrutamiento de](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)SMS. MO significa 'Mobile Originated', lo que significa que puedes configurar una respuesta automática al móvil que envió el SMS.

Para ello:

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration > Application settings > External accounts]** la cuenta **[!UICONTROL SMS routing via SMPP]** externa.
1. En la **[!UICONTROL Automatic reply sent to the MO]** categoría, haga clic **[!UICONTROL Create element]** para comenzar a configurar la respuesta automática.

   ![](assets/sms_mo_1.png)

1. Elija la palabra clave que activará esta respuesta automática. Las palabras clave no distinguen entre mayúsculas y minúsculas. Por ejemplo: si los destinatarios envían la palabra clave "STOP", recibirán la respuesta automática.

   Deje esta columna vacía si desea enviar la misma respuesta sin importar la palabra clave.

   ![](assets/sms_mo_2.png)

1. En el **[!UICONTROL Short code]** campo, especifique un número que se utilice normalmente para enviar envíos y que sirva como nombre del remitente. También puede decidir dejar la **[!UICONTROL Short code]** columna vacía para enviar la misma respuesta sin importar el código corto.

   ![](assets/sms_mo_4.png)

1. Escriba la respuesta que desee enviar a los destinatarios en el campo **[!UICONTROL Reply]**.

   To carry out an action without sending a reply, leave the **[!UICONTROL Reply]** column empty. Por ejemplo, esto le permite quitar de la cuarentena el número de teléfono de un usuario que responde con un mensaje que no sea "STOP".

   ![](assets/sms_mo_3.png)

1. En el **[!UICONTROL Additional action]** campo, vincule una acción a la respuesta automática:

   * La **[!UICONTROL Send to quarantine]** acción pone en cuarentena automáticamente el número de teléfono del perfil.
   * La **[!UICONTROL Remove from quarantine]** acción elimina el número de teléfono del perfil de la cuarentena.
   * La **[!UICONTROL None]** acción solo permite enviar el mensaje a los destinatarios sin realizar ninguna acción.
   Por ejemplo: en la configuración siguiente, si los destinatarios envían la palabra clave "STOP", recibirán automáticamente una confirmación de cancelación de suscripción y su número de teléfono se enviará a cuarentena con el **[!UICONTROL Blacklisted]** estado. Este estado hace referencia únicamente al número de teléfono, el perfil no está bloqueado para que el usuario siga recibiendo mensajes de correo electrónico.

   ![](assets/sms_mo.png)

Ahora los destinatarios pueden cancelar la suscripción a sus mensajes automáticamente y enviarlos a cuarentena con esta respuesta automática. Los destinatarios en cuarentena se enumeran en la **[!UICONTROL Addresses]** tabla disponible a través del menú **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Quarantines]** . For more information on quarantines, refer to this [section](../../sending/using/understanding-quarantine-management.md).

Estos SMS entrantes se pueden almacenar si es necesario. For more information on this, refer to this [section](#storing-incoming-sms).

## Almacenamiento de SMS entrantes {#storing-incoming-sms}

En la cuenta externa, puede elegir almacenar los mensajes entrantes, por ejemplo, cuando un suscriptor responde "STOP" a un mensaje SMS para que se elimine de las listas de destinatarios. **[!UICONTROL SMS routing via SMPP]**

![](assets/sms_config_mo_1.png)

Al marcar **[!UICONTROL Store incoming MO in the database]** la **[!UICONTROL SMPP channel settings]** categoría, todos los SMS se almacenarán en la tabla en SMS y se podrán recuperar mediante una actividad de consulta en un flujo de trabajo.

Para ello:

1. En el **[!UICONTROL SMPP channel settings]** campo, marque **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. En la **[!UICONTROL Marketing activities]** ficha, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleccione el tipo de flujo de trabajo.
1. Edite las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**. For more on workflows creation, refer to this [section](../../automating/using/building-a-workflow.md).
1. Arrastre y suelte una **[!UICONTROL Query]** actividad y haga doble clic en ella.
1. En la **[!UICONTROL Properties]** ficha de la consulta, elija **[!UICONTROL Incoming SMS (inSMS)]** en el **[!UICONTROL Resource]** campo.

   ![](assets/sms_config_mo_4.png)

1. A continuación, en la **[!UICONTROL Target]** ficha, arrastre y suelte la **[!UICONTROL Incoming SMS attributes]** regla.

   ![](assets/sms_config_mo_5.png)

1. Aquí, queremos dirigir todos los mensajes entrantes del día anterior. En la **[!UICONTROL Field]** categoría, seleccione **[!UICONTROL Creation date (created)]**.
1. En **[!UICONTROL Filter type]**, seleccione **[!UICONTROL Relative]** luego en **[!UICONTROL Level of precision]**, elija **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Luego puede elegir recuperar datos de hoy, el día anterior o los últimos días. Haga clic **[!UICONTROL Confirm]** cuando se configure la consulta.

Esta consulta recuperará cada mensaje STOP recibido en función del intervalo de tiempo seleccionado.

La actividad le permite, por ejemplo, crear una población y personalizar mejor los envíos.
