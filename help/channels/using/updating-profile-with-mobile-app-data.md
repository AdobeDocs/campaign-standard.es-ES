---
title: Creación y actualización de información de perfil basada en datos de aplicaciones móviles
description: Obtenga información sobre cómo crear y actualizar la información de perfil en función de los datos de aplicaciones móviles.
page-status-flag: nunca activado
uuid: 8cf74cad-b1ba-4aad-83bd-7289cb22d5f4
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: push-notifications
discoiquuid: dc944c85-2059-46df-b396-676fe3617dd1
context-tags: entrega,mobileAppContent,retroceso
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creación y actualización de información de perfil basada en datos de aplicaciones móviles

## Información general

En esta página se describen los pasos para desarrollar un flujo de trabajo que cree o actualice datos de perfil después de que una aplicación móvil envíe Recopilar datos PII de forma programada.

* **PII** significa "Información de identificación personal". Puede ser cualquier dato, incluida la información que no aparece en la tabla Perfil de la base de datos de campañas como, por ejemplo, Analytics para [puntos de interés](../../integrating/using/about-campaign-points-of-interest-data-integration.md)móviles. La PII la define Mobile App Developer, normalmente con un especialista en marketing.
* **Recopilar PII** es una operación HTTP-POST a una API de descanso en Adobe Campaign Standard desde una aplicación móvil.

El objetivo de este caso de uso es crear o actualizar un perfil de Campaign Standard, si los datos PII devueltos por una aplicación móvil contienen datos relacionados con el perfil.

## Requisitos previos

Hay que seguir varios pasos de configuración para activar las notificaciones push en Campaign Standard, antes de poder crear o actualizar perfiles en función de los datos de suscripción de aplicaciones móviles:

1. [Crear una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)
1. [Integre el SDK de Adobe Mobile con su aplicación](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html)móvil.
1. [Configure Adobe Campaign para que envíe notificaciones](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html)push.

## Paso 1: Extender el recurso de perfil para notificaciones push/suscripciones

Para poder crear o actualizar el recurso Perfil con datos PII, primero debe ampliar el recurso Perfil con los campos deseados. Para ello:

* Identifique los campos PII que envía la aplicación móvil.
* Identifique el campo que se usará para la reconciliación para asociar los datos de PII con los datos de perfil.

![](assets/update_profile1.png)

En este ejemplo, la **[!UICONTROL Fields]** sección refleja los datos PII enviados por la aplicación móvil. La **[!UICONTROL Link to profiles]** sección indica el campo que se utiliza para asociar la PII con los datos de perfil, donde **cusEmail** se asigna a **@email**.

La asignación de datos de perfil mientras se amplía el **[!UICONTROL Subscriptions to an Application]** recurso es de SOLO LECTURA. Se utiliza para la reconciliación. El perfil debe introducirse en el sistema con los datos necesarios para conciliar el perfil con los datos PII. En nuestro caso, una dirección de correo electrónico del perfil debe coincidir con un correo electrónico de la PII de recopilación para que se produzca la reconciliación:

* La recopilación de PII se recibe de una aplicación móvil para un usuario cuyo nombre es "Jane", el apellido es "Doe" y la dirección de correo electrónico es janedoe@doe.com.
* Por separado, los datos de perfil deben existir (por ejemplo, los datos deben introducirse manualmente o ya proceden de otro recurso), donde la dirección de correo electrónico del perfil es janedoe@doe.com.

**Temas relacionados:**

* [Ampliación de las suscripciones a un recurso de aplicación](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Crear o ampliar un recurso](../../developing/using/key-steps-to-add-a-resource.md)existente.

## Paso 2: Creación del flujo de trabajo

El uso de un flujo de trabajo en Campaign Standard permite que un administrador identifique y sincronice de forma exclusiva los datos entre los datos de AppSubscription (suscriptor) y los datos de perfil o destinatario. Aunque una actualización basada en flujos de trabajo no sincroniza datos de perfil en tiempo real, no debe provocar bloqueos o sobrecargas indebidos de la base de datos.

Los pasos principales para crear el flujo de trabajo son:

1. Use una **[!UICONTROL Query]** o **[!UICONTROL Incremental query]** actividad para obtener una lista de las suscripciones más recientes.
1. Utilice una **[!UICONTROL Reconciliation]** actividad para asignar los datos de PII al perfil.
1. Agregue un proceso de verificación.
1. Utilice un **[!UICONTROL Update data]** para actualizar o crear el perfil con los datos de PII.

En este flujo de trabajo se asumen los siguientes requisitos:

* Todos los campos que se hayan ampliado deben estar disponibles para crear o actualizar la tabla de perfil.
* La tabla Perfil se puede ampliar para admitir campos no admitidos de forma nativa (por ejemplo, Tamaño de camiseta).
* Los campos de la tabla AppSubscription que estén en blanco no deben actualizarse en la tabla de perfiles.
* Cualquier registro que se haya actualizado en la tabla AppSubscription debe incluirse en la siguiente ejecución del flujo de trabajo.

Para crear un flujo de trabajo, siga los pasos siguientes:

1. Arrastre y suelte las siguientes actividades en el espacio de trabajo y vincúlelas:
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. Configure the **[!UICONTROL Scheduler]** activity. En la **[!UICONTROL General]** ficha, establezca los valores **[!UICONTROL Execution frequency]** (por ejemplo, "Diario"), **[!UICONTROL Time]** (por ejemplo, "1:00:00 AM") y **[!UICONTROL Start]** (por ejemplo, Fecha de hoy).

   ![](assets/update_profile2.png)

1. Configure the **[!UICONTROL Incremental query]** activity.
   1. En la **[!UICONTROL Properties]** ficha, haga clic en el **[!UICONTROL Select an element]** icono del **[!UICONTROL Resource]** campo y, a continuación, seleccione el **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** elemento.

      ![](assets/update_profile3.png)

   1. En la **[!UICONTROL Target]** ficha, arrastre el **[!UICONTROL Mobile application]** filtro y seleccione un nombre de aplicación móvil.

      ![](assets/update_profile4.png)

   1. En la **[!UICONTROL Processed data]** ficha, seleccione **[!UICONTROL Use a date field]**, luego agregue el **[!UICONTROL Last modified (lastModified)]** campo como **[!UICONTROL Path to the date field]**.

      ![](assets/update_profile5.png)

1. Configure the **[!UICONTROL Update data]** activity.
   1. En la **[!UICONTROL Identification]** ficha, asegúrese de que el **[!UICONTROL Dimension to update]** campo está definido como "Perfiles (perfil)" y, a continuación, haga clic en el **[!UICONTROL Create element]** botón para agregar un campo como criterio de reconciliación.

      ![](assets/update_profile_createelement.png)

   1. En el **[!UICONTROL Source]** campo, seleccione un campo de la tabla appSubscrsiptionRcp como campo de reconciliación. Puede ser el correo electrónico del perfil, crmId, marketingCloudId, etc. En este caso de ejemplo, utilizaremos el campo "Correo electrónico (cusEmail)".
   1. En el **[!UICONTROL Destination]** campo, seleccione un campo de la tabla de perfiles para reconciliar los datos de la tabla appSubscriptionRcp. Puede ser el correo electrónico del perfil o cualquier campo extendido como crmId, marketingCloudId, etc. En este ejemplo, necesitamos seleccionar el campo "Correo electrónico (correo electrónico)" para asignarlo al campo "Correo electrónico (cusEmail)" de la tabla appSubscriptionRcp.

      ![](assets/update_profile7.png)

   1. En la **[!UICONTROL Fields to update]** ficha, haga clic en el **[!UICONTROL Create element]** botón y, a continuación, asigne los campos que proceden de la tabla appSubscriptionRcp (**[!UICONTROL Source]** campo) a los campos que desea actualizar en la tabla Perfil (**[!UICONTROL Destination]** campo).
   1. En el **[!UICONTROL Enabled if]** campo, agregue una expresión para asegurarse de que el campo correspondiente de la tabla Perfil se actualiza solo si el campo de origen contiene un valor. Para ello, seleccione el campo de la lista y, a continuación, añada el "!expresión =''" (si el campo Origen está `[target/@cusEmail]` en el editor de expresiones, asegúrese de escribir `[target/@cusEmail] != ''"`).

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >En este caso, el flujo de trabajo realiza una UPSERT, pero ya que se basa en datos de consulta incremental solo se inserta. Cambiar la consulta puede afectar a los datos que se insertan o actualizan.
      >Además, la configuración de la ficha Campos para actualizar determina qué campos se insertan o actualizan en condiciones específicas. Esta configuración puede ser única para cada aplicación o cliente. Tenga cuidado al configurar estos ajustes, ya que puede haber consecuencias no deseadas, ya que la actualización de los registros en el perfil basada en datos appSubscriptionRcp puede cambiar la información personal de los usuarios sin validación.

   1. Cuando se hayan agregado todos los campos para insertar/actualizar en Perfil, haga clic en **[!UICONTROL Confirm]**.

      ![](assets/update_profile9.png)

1. Guarde el flujo de trabajo y haga clic en Iniciar para iniciar el proceso de flujo de trabajo.

   ![](assets/update_profile10.png)
