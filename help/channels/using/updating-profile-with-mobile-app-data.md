---
title: Creación y actualización de información de perfil basada en datos de aplicaciones móviles
description: Obtenga información sobre cómo crear y actualizar información de perfil basada en datos de aplicaciones móviles.
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: delivery,mobileAppContent,back
feature: Push
role: User
level: Intermediate
exl-id: 1b48456e-9aae-485c-a7c4-7e3e2f53cbca
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 5%

---

# Creación y actualización de información de perfil basada en datos de aplicaciones móviles

## Información general

En esta página se describen los pasos para desarrollar un flujo de trabajo que cree o actualice datos de perfil después de que una aplicación móvil envíe Recopilar datos PII de forma programada.

* **** PII es la sigla de &quot;Información de identificación personal&quot;. Puede ser cualquier dato, incluida información que no aparezca en la tabla Perfil de la base de datos de Campaign como, por ejemplo, Analytics para [Puntos de interés](../../integrating/using/about-campaign-points-of-interest-data-integration.md) móviles. La PII la define el Desarrollador de aplicaciones móviles, normalmente con un especialista en marketing.
* **Recopilar** PIIes una operación de POST HTTP para una API de Rest en Adobe Campaign Standard desde una aplicación móvil.

El objetivo de este caso de uso es crear o actualizar un perfil de Campaign Standard si los datos PII devueltos por una aplicación móvil contienen datos relacionados con el perfil.

## Requisitos previos

Hay que seguir varios pasos de configuración para habilitar las notificaciones push en el Campaign Standard, antes de poder crear o actualizar perfiles en función de los datos de suscripción de aplicaciones móviles:

1. [Crear una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)
1. [Integre el SDK de Adobe Mobile con su aplicación](https://helpx.adobe.com/es/campaign/kb/integrate-mobile-sdk.html) móvil.
1. [Configure Adobe Campaign para que envíe notificaciones](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html) push.

## Paso 1: Ampliación del recurso de perfil para notificaciones push/suscripciones

Para poder crear o actualizar el recurso Perfil con datos PII, primero debe ampliar el recurso Perfil con los campos deseados. Para ello, haga lo siguiente:

* Identifique los campos PII que envía la aplicación móvil.
* Identifique el campo que se utilizará para la reconciliación a fin de asociar los datos PII con los datos de perfil.

![](assets/update_profile1.png)

En este ejemplo, la sección **[!UICONTROL Fields]** refleja los datos PII enviados por la aplicación móvil. La sección **[!UICONTROL Link to profiles]** indica el campo que se utiliza para asociar la PII con los datos de perfil, donde **cusEmail** se asigna a **@email**.

La asignación para datos de perfil mientras se amplía el recurso **[!UICONTROL Subscriptions to an Application]** es de SOLO LECTURA. Se utiliza para la reconciliación. El perfil debe introducirse en el sistema con los datos necesarios para reconciliar el perfil con los datos PII. En nuestro caso, una dirección de correo electrónico para el perfil debe coincidir con un correo electrónico de la PII de recopilación para que se produzca la reconciliación:

* La recopilación de PII se recibe de una aplicación móvil para un usuario cuyo nombre es &quot;Jane, el apellido es &quot;Doe&quot; y la dirección de correo electrónico es janedoe@doe.com.
* Por otro lado, los datos de perfil deben existir (por ejemplo, los datos deben introducirse manualmente o ya provienen de otro recurso), donde la dirección de correo electrónico del perfil es janedoe@doe.com.

**Temas relacionados:**

* [Ampliación de las suscripciones a un recurso de aplicación](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Creación o ampliación de un recurso existente](../../developing/using/key-steps-to-add-a-resource.md).

## Paso 2: Creación del flujo de trabajo

El uso de un flujo de trabajo en el Campaign Standard permite que un administrador identifique y sincronice datos de forma única entre los datos de AppSubscription (Subscriber) y los datos de perfil o destinatario. Aunque una actualización basada en flujos de trabajo no sincroniza los datos de perfil en tiempo real, no debe provocar bloqueos o sobrecargas indebidos en la base de datos.

Los pasos principales para crear el flujo de trabajo son:

1. Utilice una actividad **[!UICONTROL Query]** o **[!UICONTROL Incremental query]** para obtener una lista de las últimas suscripciones.
1. Utilice una actividad **[!UICONTROL Reconciliation]** para asignar los datos PII al perfil.
1. Añada un proceso de verificación.
1. Utilice un **[!UICONTROL Update data]** para actualizar o crear el perfil con los datos PII.

En este flujo de trabajo se asumen los siguientes requisitos:

* Todos los campos que se hayan ampliado deben estar disponibles para crear o actualizar la tabla de perfil.
* La tabla Perfil se puede ampliar para admitir campos que no se admiten de forma nativa (por ejemplo, tamaño de camiseta).
* Los campos de la tabla AppSubscription que estén en blanco no deben actualizarse en la tabla de perfil.
* Cualquier registro que se haya actualizado en la tabla AppSubscription debe incluirse en la siguiente ejecución del flujo de trabajo.

Para crear el flujo de trabajo, arrastre y suelte las siguientes actividades en el espacio de trabajo y vincúlelas: **[!UICONTROL Start]**, **[!UICONTROL Scheduler]**, **[!UICONTROL Incremental query]**, **[!UICONTROL Update data]**.

![](assets/update_profile0.png)

A continuación, siga los pasos a continuación para configurar cada actividad.

### Configure la actividad **[!UICONTROL Scheduler]**

En la pestaña **[!UICONTROL General]**, configure **[!UICONTROL Execution frequency]** (por ejemplo, &quot;Diario&quot;), **[!UICONTROL Time]** (por ejemplo, &quot;1:00:00 AM&quot;) y **[!UICONTROL Start]** (por ejemplo, la fecha de hoy).

![](assets/update_profile2.png)

### Configure la actividad **[!UICONTROL Incremental query]**.

1. En la pestaña **[!UICONTROL Properties]**, haga clic en el icono **[!UICONTROL Select an element]** del campo **[!UICONTROL Resource]** y seleccione el elemento **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]**.

   ![](assets/update_profile3.png)

1. En la pestaña **[!UICONTROL Target]** , arrastre el filtro **[!UICONTROL Mobile application]** y, a continuación, seleccione un nombre de aplicación móvil.

   ![](assets/update_profile4.png)

1. En la pestaña **[!UICONTROL Processed data]**, seleccione **[!UICONTROL Use a date field]** y, a continuación, añada el campo **[!UICONTROL Last modified (lastModified)]** como **[!UICONTROL Path to the date field]**.

   ![](assets/update_profile5.png)

### Configure la actividad **[!UICONTROL Update data]**.

1. En la pestaña **[!UICONTROL Identification]**, asegúrese de que el campo **[!UICONTROL Dimension to update]** está configurado como &quot;Perfiles (perfil)&quot; y, a continuación, haga clic en el botón **[!UICONTROL Create element]** para agregar un campo como criterio de reconciliación.

   ![](assets/update_profile_createelement.png)

1. En el campo **[!UICONTROL Source]**, seleccione un campo de la tabla appSubscriptionRcp como campo de reconciliación. Puede ser el correo electrónico del perfil, crmId, marketingCloudId, etc. En este ejemplo, se utiliza el campo &quot;Correo electrónico (cusEmail)&quot;.

1. En el campo **[!UICONTROL Destination]**, seleccione un campo de la tabla de perfiles para reconciliar los datos de la tabla appSubscriptionRcp . Puede ser el correo electrónico del perfil o cualquier campo extendido como crmId, marketingCloudId, etc. En este ejemplo, es necesario seleccionar el campo &quot;Correo electrónico (correo electrónico)&quot; para asignarlo al campo &quot;Correo electrónico (cusEmail)&quot; de la tabla appSubscriptionRcp .

   ![](assets/update_profile7.png)

1. En la pestaña **[!UICONTROL Fields to update]**, haga clic en el botón **[!UICONTROL Create element]** y, a continuación, asigne los campos que proceden de la tabla appSubscriptionRcp (**[!UICONTROL Source]** ) con los campos que desea actualizar en la tabla Perfil (campo **[!UICONTROL Destination]** ).

1. En el campo **[!UICONTROL Enabled if]**, añada una expresión para asegurarse de que el campo correspondiente de la tabla Perfil se actualice solo si el campo de origen contiene un valor. Para ello, seleccione el campo de la lista y añada el &quot;!=&#39;&#39;&quot; (si el campo Origen es `[target/@cusEmail]` en el editor de expresiones, asegúrese de escribir `[target/@cusEmail] != ''"`).

   ![](assets/update_profile8.png)

>[!NOTE]
>
>En este caso, el flujo de trabajo realiza un UPSERT, pero como se basa en datos **[!UICONTROL Incremental query]** solo se inserta. Cambiar la consulta puede afectar a los datos que se insertan o actualizan.
>Además, la configuración de la pestaña Fields to update determina qué campos se insertan o actualizan en condiciones específicas. Esta configuración puede ser única para cada aplicación o cliente.
>Tenga cuidado al configurar estos ajustes, ya que puede haber consecuencias no deseadas, ya que la actualización de registros en el perfil basada en datos appSubscriptionRcp puede cambiar la información personal de los usuarios sin validación.

Cuando se hayan agregado todos los campos que se van a insertar/actualizar en Perfil, haga clic en **[!UICONTROL Confirm]**.

![](assets/update_profile9.png)

Guarde el flujo de trabajo y haga clic en **[!UICONTROL Start]** para ejecutar el flujo de trabajo.

![](assets/update_profile10.png)
