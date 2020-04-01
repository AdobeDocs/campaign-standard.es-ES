---
title: Creación de perfiles
description: Obtenga información sobre cómo crear perfiles y recopilar datos de sus contactos mediante API, funciones de importación, adquisición en línea, actualizaciones automáticas o manuales.
page-status-flag: never-activated
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-profiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a1bc9d23163d12517c4501a572fc92aac6aacbc6

---


# Creación de perfiles{#creating-profiles}

En Adobe Campaign, los perfiles se utilizan de forma predeterminada para definir el destinatario principal de los mensajes.

Para crear o actualizar un perfil en Campaña, puede:

* Importación de una lista de perfil desde un archivo mediante un [flujo de trabajo](../../automating/using/importing-data.md#example--import-workflow-template)
* Recopilar datos en línea, mediante [páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md)
* Creación masiva mediante la API de [REST](../../api/using/about-campaign-standard-apis.md)
* Sincronizar perfiles de [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* Introduzca datos mediante las pantallas de interfaz gráfica, tal como se explica a continuación

Por ejemplo, para crear un nuevo perfil directamente en la interfaz de usuario, siga los pasos a continuación:

1. En la página de inicio Adobe Campaign, haga clic en la tarjeta Perfiles **del** cliente o en la ficha **Perfiles** para acceder a la lista de perfiles.

   ![](assets/profile_creation_1.png)

1. A continuación, haga clic en **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Introduzca los datos de perfil.

   ![](assets/profile_creation1.png)

   * La información de contacto, como el nombre, apellidos, sexo, fecha de nacimiento, foto, idioma preferido (para correos electrónicos [](../../channels/using/creating-a-multilingual-email.md)multilingües) ayuda a personalizar mejor los envíos.
   * El perfil **[!UICONTROL Time zone]** se utiliza para enviar envíos en el huso horario del perfil. Para obtener más información, consulte [esta sección](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * La **[!UICONTROL Channels]** categoría, que contiene la dirección de correo electrónico, el número de teléfono móvil y la información de exclusión, le permite saber en qué canal se puede acceder al perfil.
   * La **[!UICONTROL No longer contact]** categoría se actualiza en cuanto el perfil se cancela la suscripción a un canal.
   * La **[!UICONTROL Address]** categoría contiene la dirección postal que debe rellenarse junto con la **[!UICONTROL Address specified]** opción de enviar correo [directo](../../channels/using/about-direct-mail.md) a este perfil. Si la **[!UICONTROL Address specified]** opción no está marcada, este perfil se excluirá de todos los envíos de correo directo.
   * La **[!UICONTROL Access authorization]** categoría indica las unidades organizativas del perfil (para [administrar permisos](../../administration/using/about-access-management.md)). Consulte también [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).
   * La **[!UICONTROL Traceability]** categoría se actualiza automáticamente con información relativa al usuario que creó o modificó el perfil.

1. Haga clic en **[!UICONTROL Create]** para guardar el perfil.

El perfil aparecerá ahora en la lista.

>[!NOTE]
>
>También es posible crear Perfiles mediante la API de Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](../../api/using/creating-profiles.md).

Los Perfiles también pueden dividirse en función de sus dependencias orgánicas. Para agregar los campos de organización a sus perfiles, consulte la sección perfiles [de](../../administration/using/organizational-units.md#partitioning-profiles) partición.

>[!NOTE]
>
>El campo de idioma preferido se utiliza para seleccionar el idioma al enviar mensajes multilingües. Para obtener más información sobre los mensajes multilingües, [consulte esta página](../../channels/using/creating-a-multilingual-email.md).

**Temas relacionados:**

* [Guía paso a paso de páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md)
* [Vídeo sobre la importación de perfiles](https://video.tv.adobe.com/v/24993?captions=spa)
