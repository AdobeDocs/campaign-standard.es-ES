---
title: Creación y actualización de información de perfil basada en datos de aplicaciones móviles
seo-title: Creación y actualización de información de perfil basada en datos de aplicaciones móviles
description: Creación y actualización de información de perfil basada en datos de aplicaciones móviles
seo-description: Aprenda a crear y actualizar información de perfil en base a los datos de aplicaciones móviles.
page-status-flag: no activado nunca
uuid: 8 cf 74 cad-b 1 ba -4 aad -83 bd -7289 cb 22 d 5 f 4
contentOwner: lemaitre
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: notificaciones push
discoiquuid: dc 944 c 85-2059-46 df-b 396-676 fe 3617 dd 1
context-tags: delivery, mobileappcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 64c7de127285ca56b6af398b0a0c3f1470756fe4

---


# Creación y actualización de información de perfil basada en datos de aplicaciones móviles

## Información general

En esta página se describen los pasos para desarrollar un flujo de trabajo que crea o actualiza datos de perfil después de que una aplicación móvil envía datos de PII, programados.

* **PII** significa «Información personal identificable». Puede ser cualquier dato, incluida la información que no aparece en la tabla Perfil de la base de datos de campañas como, por ejemplo, Analytics para puntos de [interés móviles](../../integrating/using/about-campaign-points-of-interest-data-integration.md). El PII es definido por el desarrollador de aplicaciones móviles, normalmente con un especialista en marketing.
* **Recopilar PII** es una operación HTTP-POST a una API de Rest en Adobe Campaign Standard desde una aplicación móvil.

El objetivo de este caso de uso es crear o actualizar un perfil de Campaign Standard si los datos PII devueltos por una aplicación móvil contienen datos relacionados con el perfil.

## Requisitos previos

Hay que seguir varios pasos de configuración para activar las notificaciones push en Campaign Standard, antes de crear o actualizar perfiles en función de los datos de suscripción de la aplicación móvil:

1. [Crear una aplicación móvil](../../administration/using/configuring-a-mobile-application.md)
1. [Integre el SDK de Adobe Mobile con su aplicación móvil](https://helpx.adobe.com/campaign/kb/integrate-mobile-sdk.html).
1. [Configure Adobe Campaign para enviar notificaciones Push](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html).

## Paso 1: Ampliación del recurso de perfil para notificaciones push/suscripciones

Para poder crear o actualizar el recurso de perfil con datos PII, primero debe ampliar el recurso de perfil con los campos deseados. Para ello:

* Identifique los campos PII enviados por la aplicación móvil.
* Identifique el campo que se utilizará para la reconciliación para asociar los datos PII con los datos de perfil.

![](assets/update_profile1.png)

En este ejemplo, la **[!UICONTROL Fields]** sección refleja los datos PII enviados por la aplicación móvil. La **[!UICONTROL Link to profiles]** sección indica el campo que se utiliza para asociar PII con los datos de perfil, donde **cusemail** se asigna a **@ email**.

La asignación de datos de perfil al ampliar **[!UICONTROL Subscriptions to an Application]** el recurso ES SOLO LECTURA. Se utiliza para la reconciliación. El perfil debe introducirse en el sistema con los datos necesarios para reconciliar el perfil con los datos PII. En nuestro caso, una dirección de correo electrónico para el perfil debe coincidir con un correo electrónico de Recopilar PII para que se produzca la reconciliación:

* Recopilar PII se recibe desde una aplicación móvil para un usuario donde su nombre es «Jane, Apellido es «Doe» y la dirección de correo electrónico es janedoe@doe.com.
* Por otro lado, los datos de perfil deben existir (por ejemplo, los datos se deben introducir manualmente o proceder de algún otro recurso) donde la dirección de correo electrónico del perfil sea janedoe@doe.com.

**Temas relacionados:**

* [Ampliar las suscripciones a un recurso de aplicación](../../developing/using/extending-the-subscriptions-to-an-application-resource.md).
* [Creación o ampliación de un recurso existente](../../developing/using/key-steps-to-add-a-resource.md).

## Paso 2: Creación del flujo de trabajo

El uso de un flujo de trabajo en Campaign Standard permite a un administrador identificar y sincronizar exclusivamente los datos entre los datos de appsubscription (suscriptor) y los datos de perfil o de destinatario. Aunque una actualización basada en flujo de trabajo no sincroniza los datos de perfil en tiempo real, no debe provocar bloqueos ni sobrecarga de bases de datos indebidas.

Los principales pasos para generar el flujo de trabajo son:

1. Utilice una **[!UICONTROL Query]** o **[!UICONTROL Incremental query]** actividad para obtener una lista de las suscripciones más recientes.
1. Use una **[!UICONTROL Reconciliation]** actividad para asignar los datos PII con el perfil.
1. Agregue un proceso de verificación.
1. Utilice un **[!UICONTROL Update data]** para actualizar o crear el perfil con los datos PII.

En este flujo de trabajo se asumen los siguientes requisitos:

* Cualquiera/Todos los campos que se hayan ampliado deberían estar disponibles para crear o actualizar la tabla de perfiles.
* La tabla Perfil se puede ampliar para admitir campos que no sean compatibles de forma nativa (por ejemplo, Tamaño de camiseta).
* Cualquier campo de la tabla appsubscription que esté en blanco no debe actualizarse en la tabla de perfiles.
* Cualquier registro que se haya actualizado en la tabla appsubscription debe incluirse en la siguiente ejecución del flujo de trabajo.

Para generar el flujo de trabajo, siga los pasos a continuación:

1. Arrastre y suelte las siguientes actividades en el espacio de trabajo y vincularlas juntos:
   1. **[!UICONTROL Start]**
   1. **[!UICONTROL Scheduler]**
   1. **[!UICONTROL Incremental query]**
   1. **[!UICONTROL Update data]**
   ![](assets/update_profile0.png)

1. Configure la **[!UICONTROL Scheduler]** actividad. En la **[!UICONTROL General]** ficha, establezca el **[!UICONTROL Execution frequency]** (por ejemplo, "Diario"), el **[!UICONTROL Time]** (por ejemplo, "1:00:00 AM") y el **[!UICONTROL Start]** (por ejemplo, Fecha de hoy).

   ![](assets/update_profile2.png)

1. Configure la **[!UICONTROL Incremental query]** actividad.
   1. En **[!UICONTROL Properties]** la ficha, haga clic en **[!UICONTROL Select an element]** el icono del **[!UICONTROL Resource]** campo y seleccione **[!UICONTROL Subscriptions to an application (nms:appSubscriptionRcp:appSubscriptionRcpDetail)]** el elemento.

      ![](assets/update_profile3.png)

   1. En **[!UICONTROL Target]** la ficha, arrastre **[!UICONTROL Mobile application]** el filtro y, a continuación, seleccione un nombre de aplicación móvil.

      ![](assets/update_profile4.png)

   1. En **[!UICONTROL Processed data]** la ficha, seleccione **[!UICONTROL Use a date field]** y agregue **[!UICONTROL Last modified (lastModified)]** el campo como **[!UICONTROL Path to the date field]**.

      ![](assets/update_profile5.png)

1. Configure la **[!UICONTROL Update data]** actividad.
   1. En **[!UICONTROL Identification]** la ficha, asegúrese de que **[!UICONTROL Dimension to update]** el campo está configurado en "Perfiles (perfil)" y, a continuación, haga clic en **[!UICONTROL Create element]** el botón para agregar un campo como criterio de reconciliación.

      ![](assets/update_profile_createelement.png)

   1. En **[!UICONTROL Source]** el campo, seleccione un campo de la tabla appsubscrsiptionrcp como campo de reconciliación. Puede ser el correo electrónico del perfil, crmid, marketingcloudid, etc. En este caso de ejemplo, utilizaremos el campo «Correo electrónico (cusemail)».
   1. En **[!UICONTROL Destination]** el campo, seleccione un campo de la tabla de perfil para reconciliar los datos de la tabla appsubscriptionrcp. Puede ser el correo electrónico del perfil o cualquier campo ampliado como crmid, marketingcloudid, etc. En este ejemplo, necesitamos seleccionar el campo «Correo electrónico (correo electrónico)» para asignarlo con el campo «Correo electrónico (cusemail)» de la tabla appsubscriptionrcp.

      ![](assets/update_profile7.png)

   1. En **[!UICONTROL Fields to update]** la ficha, haga clic en **[!UICONTROL Create element]** el botón y asigne los campos que provienen de la tabla appsubscriptionrcp (**[!UICONTROL Source]** field) con los campos que desea actualizar en la tabla Perfil (**[!UICONTROL Destination]** campo).
   1. En **[!UICONTROL Enabled if]** el campo, agregue una expresión para asegurarse de que el campo correspondiente de la tabla Perfil se actualiza solo si el campo de origen contiene un valor. Para ello, seleccione el campo de la lista y, a continuación, agregue el= "" expresión (si el campo Origen está `[target/@cusEmail]` en el editor de expresiones asegúrese de escribir `[target/@cusEmail] != ''"`).

      ![](assets/update_profile8.png)

      >[!NOTE]
      >
      >En este caso, el flujo de trabajo ejecuta UPSERT, pero se basa en los datos de Incremental Query únicamente insertados. Cambiar la consulta puede afectar a los datos que se van a insertar o actualizar.
      >Además, la configuración de la ficha Campos para actualizar determina los campos que se insertan o actualizan en condiciones específicas. Estos ajustes pueden ser únicos para cada aplicación o cliente. Tenga cuidado al configurar esta configuración porque puede haber consecuencias no deseadas, ya que actualizar registros en el perfil basado en datos de appsubscriptionrcp puede cambiar la información personal de los usuarios sin validación.

   1. Cuando se hayan agregado todos los campos para insertar o actualizar en Perfil, haga clic **[!UICONTROL Confirm]** en.

      ![](assets/update_profile9.png)

1. Guarde el flujo de trabajo y, a continuación, haga clic en Iniciar para iniciar el proceso de flujo de trabajo.

   ![](assets/update_profile10.png)
