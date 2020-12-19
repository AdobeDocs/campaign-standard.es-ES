---
solution: Campaign Standard
product: campaign
title: Administración de SMS entrantes
description: Conozca cómo administrar STOP SMS y almacenar los SMS entrantes en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: sms-messages
delivercontext-tags: delivery,smsContent,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 8%

---


# Administración de SMS entrantes{#managing-incoming-sms}

## Administración de SMS STOP {#managing-stop-sms}

Cuando un perfil responde a un mensaje SMS enviado por Campaign, puede configurar los mensajes que se le envían automáticamente, así como la acción que se va a realizar.

Esta configuración se define en la sección **[!UICONTROL Automatic reply sent to the MO]** de la cuenta externa [Enrutamiento SMS](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing). MO significa &#39;Mobile Originated&#39;, lo que significa que puedes configurar una respuesta automática al móvil que envió el SMS.

Para ello:

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration > Application settings > External accounts]** y luego la cuenta externa **[!UICONTROL SMS routing via SMPP]**.
1. En la categoría **[!UICONTROL Automatic reply sent to the MO]**, haga clic en **[!UICONTROL Create element]** para configurar su respuesta automática en inicio.

   ![](assets/sms_mo_1.png)

1. Elija la palabra clave que activará esta respuesta automática. Las palabras clave no distinguen entre mayúsculas y minúsculas. Por ejemplo: si los destinatarios envían la palabra clave &quot;STOP&quot;, recibirán la respuesta automática.

   Deje esta columna vacía si desea enviar la misma respuesta sin importar la palabra clave.

   ![](assets/sms_mo_2.png)

1. En el campo **[!UICONTROL Short code]**, especifique un número que se utilice normalmente para enviar envíos y que sirva como nombre del remitente. También puede decidir dejar la columna **[!UICONTROL Short code]** vacía para enviar la misma respuesta sin importar el código corto.

   ![](assets/sms_mo_4.png)

1. Escriba la respuesta que desee enviar a sus destinatarios en el campo **[!UICONTROL Reply]**.

   Para realizar una acción sin enviar una respuesta, deje la columna **[!UICONTROL Reply]** vacía. Por ejemplo, esto le permite quitar de la cuarentena el número de teléfono de un usuario que responde con un mensaje que no sea &quot;STOP&quot;.

   ![](assets/sms_mo_3.png)

1. En el campo **[!UICONTROL Additional action]**, vincule una acción a su respuesta automática:

   * La acción **[!UICONTROL Send to quarantine]** cuarentena automáticamente el número de teléfono del perfil.
   * La acción **[!UICONTROL Remove from quarantine]** elimina el número de teléfono de perfil de la cuarentena.
   * La acción **[!UICONTROL None]** le permite enviar sólo el mensaje a sus destinatarios sin realizar ninguna acción.

   Por ejemplo: en la configuración siguiente, si los destinatarios envían la palabra clave &quot;STOP&quot;, recibirán automáticamente una confirmación baja y su número de teléfono se enviará a la cuarentena con el estado **[!UICONTROL On denylist]**. Este estado hace referencia únicamente al número de teléfono, el perfil es para que el usuario siga recibiendo mensajes de correo electrónico.

   ![](assets/sms_mo.png)

Sus destinatarios ahora pueden cancelarse automáticamente la suscripción a sus mensajes y enviarse a cuarentena con esta respuesta automática. Los destinatarios en cuarentena se enumeran en la tabla **[!UICONTROL Addresses]** disponible a través del menú **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Quarantines]**. Para obtener más información sobre cuarentenas, consulte esta [sección](../../sending/using/understanding-quarantine-management.md).

Estos SMS entrantes se pueden almacenar si es necesario. Para obtener más información sobre esto, consulte esta [sección](#storing-incoming-sms).

## Almacenamiento de SMS entrantes {#storing-incoming-sms}

En la cuenta externa **[!UICONTROL SMS routing via SMPP]**, puede elegir almacenar los mensajes entrantes, por ejemplo, cuando un suscriptor responde &quot;STOP&quot; a un mensaje SMS para que se elimine de sus listas de destinatario.

![](assets/sms_config_mo_1.png)

Al marcar **[!UICONTROL Store incoming MO in the database]** en la categoría **[!UICONTROL SMPP channel settings]**, todos los SMS se almacenarán en la tabla inSMS y se podrán recuperar mediante una actividad de consulta en un flujo de trabajo.

Para ello:

1. En el campo **[!UICONTROL SMPP channel settings]**, marque **[!UICONTROL Store incoming MO in the database]**.

   ![](assets/sms_config_mo_2.png)

1. En la ficha **[!UICONTROL Marketing activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.

   ![](assets/sms_config_mo_3.png)

1. Seleccione el tipo de flujo de trabajo.
1. Edite las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**. Para obtener más información sobre la creación de flujos de trabajo, consulte esta [sección](../../automating/using/building-a-workflow.md).
1. Arrastre y suelte una **[!UICONTROL Query]** actividad y haga clic con el doble en la actividad.
1. En la ficha **[!UICONTROL Properties]** de la consulta, elija **[!UICONTROL Incoming SMS (inSMS)]** en el campo **[!UICONTROL Resource]**.

   ![](assets/sms_config_mo_4.png)

1. A continuación, en la ficha **[!UICONTROL Target]**, arrastre y suelte la regla **[!UICONTROL Incoming SMS attributes]**.

   ![](assets/sms_config_mo_5.png)

1. En este caso, deseamos destinatario de todos los mensajes entrantes del día anterior. En la categoría **[!UICONTROL Field]**, seleccione **[!UICONTROL Creation date (created)]**.
1. En **[!UICONTROL Filter type]**, seleccione **[!UICONTROL Relative]** y luego en **[!UICONTROL Level of precision]**, elija **[!UICONTROL Day]**.

   ![](assets/sms_config_mo_6.png)

1. Luego puede elegir recuperar datos de hoy, el día anterior o los últimos días. Haga clic **[!UICONTROL Confirm]** cuando se configure la consulta.

Esta consulta recuperará cada mensaje STOP recibido en función del intervalo de tiempo seleccionado.

La actividad le permite, por ejemplo, construir una población y personalizar mejor sus envíos.
