---
title: Creación de perfiles
description: Obtenga información sobre cómo crear perfiles y recopilar datos de sus contactos mediante API, funciones de importación, adquisición en línea, actualizaciones automáticas o manuales.
page-status-flag: nunca activado
uuid: a5f5a58a-e798-400f-8648-05dc843d5557
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: referencia
topic-tags: administrar-perfiles
discoiquuid: 4ab8a984-f898-4fff-ad8c-ed8f95362f96
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creación de perfiles{#creating-profiles}

En Adobe Campaign, los perfiles se utilizan de forma predeterminada para definir el objetivo principal de los mensajes.

Para crear o actualizar un perfil en Campaign, puede:

* Importar una lista de perfiles de un archivo mediante un [flujo de trabajo](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)
* Recopilar datos en línea, a través de páginas [de aterrizaje](../../channels/using/about-landing-pages.md)
* Creación masiva mediante la API de [REST](http://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)
* Sincronizar perfiles de [Microsoft Dynamics](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html)
* Introduzca datos mediante las pantallas de interfaz gráfica, tal como se explica a continuación

Por ejemplo, para crear un nuevo perfil directamente en la interfaz de usuario, siga los pasos a continuación:

1. En la página de inicio de Adobe Campaign, haga clic en la tarjeta Perfiles **del** cliente o en la ficha **Perfiles** para acceder a la lista de perfiles.

   ![](assets/profile_creation_1.png)

1. A continuación, haga clic en **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Introduzca los datos de perfil.

   ![](assets/profile_creation1.png)

   * La información de contacto, como el nombre, apellidos, sexo, fecha de nacimiento, foto, idioma preferido (para correos electrónicos [](../../channels/using/creating-a-multilingual-email.md)multilingües) ayuda a personalizar mejor los partos.
   * El perfil **[!UICONTROL Time zone]** se utiliza para enviar envíos en el huso horario del perfil. Para obtener más información, consulte [esta sección](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * La **[!UICONTROL Channels]** categoría, que contiene la dirección de correo electrónico, el número de teléfono móvil y la información de exclusión, le permite saber en qué canal se puede acceder al perfil.
   * La **[!UICONTROL No longer contact]** categoría se actualiza en cuanto el perfil se cancela la suscripción a un canal.
   * La **[!UICONTROL Address]** categoría contiene la dirección postal que debe rellenarse junto con la **[!UICONTROL Address specified]** opción de enviar correo [directo](../../channels/using/about-direct-mail.md) a este perfil. Si la **[!UICONTROL Address specified]** opción no está marcada, este perfil se excluirá de cada envío directo por correo.
   * La **[!UICONTROL Access authorization]** categoría indica las unidades organizativas del perfil (para [administrar permisos](../../administration/using/about-access-management.md)). Consulte también [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).
   * La **[!UICONTROL Traceability]** categoría se actualiza automáticamente con información relativa al usuario que creó o modificó el perfil.

1. Haga clic en **[!UICONTROL Create]** para guardar el perfil.

El perfil ahora aparecerá en la lista.

>[!NOTE]
>
>También es posible crear perfiles mediante la API de Adobe Campaign Standard. For more on this, refer to the [dedicated documentation](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#creating-profiles) .

Los perfiles también pueden dividirse en función de sus dependencias orgánicas. Para agregar los campos de organización a sus perfiles, consulte la sección Perfiles [de](../../administration/using/organizational-units.md#partitioning-profiles) partición.

>[!NOTE]
>
>El campo de idioma preferido se utiliza para seleccionar el idioma al enviar mensajes multilingües. Para obtener más información sobre los mensajes multilingües, [consulte esta página](../../channels/using/creating-a-multilingual-email.md).

**Temas relacionados:**

* [Acerca de las páginas](../../channels/using/about-landing-pages.md) de aterrizaje, guía paso a paso
* [Importación de perfiles](https://helpx.adobe.com/campaign/kt/acs/using/acs-importing-profiles-feature-video-using.html)

