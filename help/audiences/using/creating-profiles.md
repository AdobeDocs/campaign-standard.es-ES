---
title: Creación de perfiles
description: Aprenda a crear perfiles y recopilar datos de sus contactos mediante API, funciones de importación, adquisición en línea y actualizaciones automáticas o manuales.
audience: audiences
content-type: reference
topic-tags: managing-profiles
feature: Profiles
role: User
level: Beginner
exl-id: 827df9f6-070c-466a-890c-e363de6b129b
TQID: https://experienceleague.adobe.com/STHpDRtsdjT7OMDg3aOtVHdzqLokzOxvM2PI0ho9WLA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
subfeature_v2:
  - id: bf97c196-a4d1-4fa3-a151-e68a114c8ac0
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 395
ht-degree: 84%

---

# Creación de perfiles{#creating-profiles}

En Adobe Campaign, los perfiles se utilizan de forma predeterminada para definir el destinatario principal de los mensajes.

>[!NOTE]
>
>También es posible crear perfiles mediante la API de Adobe Campaign Standard. Para obtener más información, consulte [la documentación dedicada](../../api/using/creating-profiles-api.md).

![](assets/do-not-localize/how-to-video.png) [Descubra cómo importar perfiles mediante un flujo de trabajo en vídeo](#video)

Para crear o actualizar un perfil en Campaign, puede:

* Importar una lista de perfil desde un archivo mediante un [flujo de trabajo](../../automating/using/creating-import-workflow-templates.md)
* Recopilar datos en línea, mediante [páginas de destino](../../channels/using/getting-started-with-landing-pages.md)
* Realizar una creación masiva mediante la [API de REST](../../api/using/get-started-apis.md)
* Sincronizar perfiles de [Microsoft Dynamics](../../integrating/using/d365-acs-get-started.md)
* Introduzca datos mediante la interfaz de usuario de, como se explica a continuación

Por ejemplo, para crear un nuevo perfil directamente en la interfaz de usuario, siga los pasos a continuación:

1. En la página de inicio de Adobe Campaign, haga clic en la tarjeta **Perfiles del cliente** o en la pestaña **Perfiles** para acceder a la lista de perfiles.

   ![](assets/profile_creation_1.png)

1. Haga clic **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Introduzca los datos del perfil.

   ![](assets/profile_creation1.png)

   * La información de contacto, como el nombre, apellidos, género, fecha de nacimiento, foto, idioma preferido (para [correos electrónicos multilingües](../../channels/using/creating-a-multilingual-email.md)) ayuda a personalizar mejor los envíos.
   * El **[!UICONTROL Time zone]** del perfil se utiliza para realizar envíos en el huso horario adecuado. Para obtener más información, consulte [esta sección](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * La categoría **[!UICONTROL Channels]**, que contiene la dirección de correo electrónico, el número de teléfono móvil y la información de exclusión, le permite saber por qué canal se puede acceder al perfil.

     >[!NOTE]
     > Los números de teléfono móvil siempre deben tener formato internacional (`+<country><number>`) en la tabla de perfiles.

   * La categoría **[!UICONTROL No longer contact]** se actualiza en cuanto el perfil cancela la suscripción a un canal.
   * La categoría **[!UICONTROL Address]** contiene la dirección postal que debe rellenarse junto con la opción **[!UICONTROL Address specified]** para enviar [correo directo](../../channels/using/about-direct-mail.md) a dicho perfil. Si la opción **[!UICONTROL Address specified]** no está marcada, este perfil se excluye de todos los envíos de correo directo.
   * La categoría **[!UICONTROL Access authorization]** indica las unidades organizativas del perfil para [administrar permisos](../../administration/using/about-access-management.md). Para añadir los campos organizativos a los perfiles, consulte la sección [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).
   * La categoría **[!UICONTROL Traceability]** se actualiza automáticamente con información relativa al usuario que ha creado o modificado el perfil.

1. Haga clic en **[!UICONTROL Create]** para guardar el perfil.

El perfil aparece ahora en la lista.

>[!NOTE]
>El campo de idioma preferido se utiliza para seleccionar el idioma al enviar mensajes multilingües. Para obtener más información sobre los mensajes multilingües, [consulte esta página](../../channels/using/creating-a-multilingual-email.md).

## Tutorial en vídeo {#video}

Este vídeo muestra cómo importar perfiles con un flujo de trabajo.

>[!VIDEO](https://video.tv.adobe.com/v/24993?quality=12)

Hay disponibles [más vídeos de procedimientos para Campaign Standard aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
