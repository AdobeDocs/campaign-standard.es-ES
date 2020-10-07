---
title: Creación y actualización de información de perfil basada en datos de aplicaciones móviles
description: Obtenga información sobre cómo crear y actualizar la información de perfil en función de los datos de aplicaciones móviles.
page-status-flag: never-activated
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: delivery,mobileAppContent,back
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 5%

---


# Creación y actualización de información de perfil basada en datos de aplicaciones móviles

## Información general

En esta página se describen los pasos para desarrollar un flujo de trabajo que cree o actualice datos de perfil después de que una aplicación móvil envíe Recopilar datos PII de forma programada.

* **PII** significa &quot;Información de identificación personal&quot;. Puede ser cualquier dato, incluida la información que no aparece en la tabla de Perfiles de la base de datos de Campañas como, por ejemplo, Analytics para [puntos de interés](../../integrating/using/about-campaign-points-of-interest-data-integration.md)móviles. La PII la define Mobile App Developer, normalmente con un especialista en marketing.
* **Recopilar PII** es una operación de POST HTTP para una API de descanso en Adobe Campaign Standard desde una aplicación móvil.

El objetivo de este caso de uso es crear o actualizar un perfil de Campaign Standard, si los datos PII devueltos por una aplicación móvil contienen datos relacionados con el perfil.

## Requisitos previos

Hay que seguir varios pasos de configuración para activar las notificaciones push en Campaign Standard, antes de poder crear o actualizar Perfiles en función de los datos de Suscripción de aplicaciones móviles:

1. [Creación de una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)
1. [Integre el SDK de Adobe Mobile con su aplicación](https://helpx.adobe.com/es/campaign/kb/integrate-mobile-sdk.html)móvil.
1. [Configure Adobe Campaign para que envíe notificaciones](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html)push.

## Paso 1: Ampliación del recurso de Perfil para notificaciones/Suscripciones push

Para poder crear o actualizar el recurso de Perfil con datos PII, primero debe extender el recurso de Perfil con los campos deseados. Para ello:

* Identifique los campos PII que envía la aplicación móvil.
* Identifique el campo que se usará para la reconciliación para asociar los datos de PII con los datos de Perfil.

![](assets/update_profile1.png)

En este ejemplo, la **[!UICONTROL Fields]** sección refleja los datos PII enviados por la aplicación móvil. La **[!UICONTROL Link to profiles]** sección indica el campo que se utiliza para asociar la PII con los datos de Perfil, donde **cusEmail** se asigna a **@email**.

La asignación de datos de Perfil mientras se amplía el **[!UICONTROL Subscriptions to an Application]** recurso es de SOLO LECTURA. Se utiliza para la reconciliación. El perfil debe introducirse en el sistema con los datos necesarios para conciliar el perfil con los datos PII. En nuestro caso, una dirección de correo electrónico para el perfil debe coincidir con un correo electrónico de la PII de recopilación para que se produzca la reconciliación:

* La recopilación de PII se recibe de una aplicación móvil para un usuario cuyo nombre es &quot;Jane&quot;, el apellido es &quot;Doe&quot; y la dirección de correo electrónico es janedoe@doe.com.
* Por separado, los datos de Perfil deben existir (por ejemplo, los datos deben introducirse manualmente o ya proceden de otro recurso), donde la dirección de correo electrónico del perfil es janedoe@doe.com.

**Temas relacionados:**

* [Ampliación de las suscripciones a un recurso de aplicación](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Crear o ampliar un recurso](../../developing/using/key-steps-to-add-a-resource.md)existente.

## Paso 2: Creación del flujo de trabajo

El uso de un flujo de trabajo en el Campaign Standard permite que un administrador identifique y sincronice de forma exclusiva los datos entre los datos de AppSubscription (suscriptor) y los datos de Perfil o Destinatario. Aunque una actualización basada en flujos de trabajo no sincroniza los datos de perfil en tiempo real, no debe provocar bloqueos o sobrecargas indebidos de la base de datos.

Los pasos principales para crear el flujo de trabajo son:

1. Use una **[!UICONTROL Query]** o **[!UICONTROL Incremental query]** actividad para obtener una lista de las últimas suscripciones.
1. Utilice una **[!UICONTROL Reconciliation]** actividad para asignar los datos PII con el perfil.
1. Añada algún proceso de verificación.
1. Utilice un **[!UICONTROL Update data]** para actualizar o crear el perfil con los datos de PII.

En este flujo de trabajo se asumen los siguientes requisitos:

* Todos los campos que se hayan ampliado deben estar disponibles para crear o actualizar la tabla de Perfil.
* La tabla Perfil se puede ampliar para admitir campos que no son compatibles de forma nativa (por ejemplo, tamaño de camiseta).
* Los campos de la tabla AppSubscription que estén en blanco no deben actualizarse en la tabla Perfil.
* Cualquier registro que se haya actualizado en la tabla AppSubscription debe incluirse en la siguiente ejecución del flujo de trabajo.

Para generar el flujo de trabajo, arrastre y suelte las siguientes actividades en el espacio de trabajo y vincúlelas juntas: **[!UICONTROL Start]**, **[!UICONTROL Scheduler]**, **[!UICONTROL Incremental query]**, **[!UICONTROL Update data]**.

![](assets/update_profile0.png)

A continuación, siga los pasos a continuación para configurar cada actividad.

### Configure the **[!UICONTROL Scheduler]** activity

En la **[!UICONTROL General]** ficha, establezca los valores **[!UICONTROL Execution frequency]** (por ejemplo, &quot;Diario&quot;), **[!UICONTROL Time]** (por ejemplo, &quot;1:00:00 AM&quot;) y **[!UICONTROL Start]** (por ejemplo, Fecha de hoy).

![](assets/update_profile2.png)

### Configure la actividad **[!UICONTROL Incremental query]**.

1. En la **[!UICONTROL Properties]** ficha, haga clic en el **[!UICONTROL Select an element]** icono del **[!UICONTROL Resource]** campo y, a continuación, seleccione el **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** elemento.

   ![](assets/update_profile3.png)

1. En la **[!UICONTROL Target]** ficha, arrastre el **[!UICONTROL Mobile application]** filtro y seleccione un nombre de aplicación móvil.

   ![](assets/update_profile4.png)

1. En la **[!UICONTROL Processed data]** ficha, seleccione **[!UICONTROL Use a date field]** y, a continuación, agregue el **[!UICONTROL Last modified (lastModified)]** campo como **[!UICONTROL Path to the date field]**.

   ![](assets/update_profile5.png)

### Configure la actividad **[!UICONTROL Update data]**.

1. En la **[!UICONTROL Identification]** ficha, asegúrese de que el **[!UICONTROL Dimension to update]** campo está definido como &quot;Perfiles (perfil)&quot; y, a continuación, haga clic en el **[!UICONTROL Create element]** botón para agregar un campo como criterio de reconciliación.

   ![](assets/update_profile_createelement.png)

1. En el **[!UICONTROL Source]** campo, seleccione un campo de la tabla appSubscrsiptionRcp como campo de reconciliación. Puede ser el correo electrónico del perfil, crmId, marketingCloudId, etc. En este caso de ejemplo, utilizaremos el campo &quot;Correo electrónico (cusEmail)&quot;.

1. En el **[!UICONTROL Destination]** campo, seleccione un campo de la tabla perfil para reconciliar los datos de la tabla appSubscriptionRcp. Puede ser el correo electrónico del perfil o cualquier campo extendido como crmId, marketingCloudId, etc. En este ejemplo, necesitamos seleccionar el campo &quot;Correo electrónico (correo electrónico)&quot; para asignarlo al campo &quot;Correo electrónico (cusEmail)&quot; de la tabla appSubscriptionRcp.

   ![](assets/update_profile7.png)

1. En la **[!UICONTROL Fields to update]** ficha, haga clic en el **[!UICONTROL Create element]** botón y, a continuación, asigne los campos que proceden de la tabla appSubscriptionRcp (**[!UICONTROL Source]** campo) a los campos que desea actualizar en la tabla Perfil (**[!UICONTROL Destination]** campo).

1. En el **[!UICONTROL Enabled if]** campo, agregue una expresión para asegurarse de que el campo correspondiente de la tabla de Perfil se actualiza solo si el campo de origen contiene un valor. Para ello, seleccione el campo de la lista y, a continuación, añada el &quot;!expresión =&#39;&#39;&quot; (si el campo Origen está `[target/@cusEmail]` en el editor de Expresiones, asegúrese de escribir `[target/@cusEmail] != ''"`).

   ![](assets/update_profile8.png)

>[!NOTE]
>
>En este caso, el flujo de trabajo realiza una función UPSERT, pero como se basa en **[!UICONTROL Incremental query]** datos solo se inserta. Cambiar la Consulta puede afectar a los datos que se insertan o actualizan.
>Además, la configuración de la ficha Campos para actualizar determina qué campos se insertan o actualizan en condiciones específicas. Esta configuración puede ser única para cada aplicación o cliente.
>Tenga cuidado al configurar estos ajustes, ya que puede haber consecuencias no deseadas, ya que la actualización de registros en el Perfil basados en datos appSubscriptionRcp puede cambiar la información personal de los usuarios sin validación.

Cuando se hayan agregado todos los campos para insertar/actualizar en Perfil, haga clic en **[!UICONTROL Confirm]**.

![](assets/update_profile9.png)

Guarde el flujo de trabajo y haga clic en **[!UICONTROL Start]** para ejecutarlo.

![](assets/update_profile10.png)
