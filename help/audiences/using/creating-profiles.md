---
title: Creación de perfiles
description: Aprenda a crear perfiles y recopilar datos de sus contactos mediante API, funciones de importación, adquisición en línea y actualizaciones automáticas o manuales.
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
source-git-commit: c1147c4512b1485ae5d927a32970adcd41b540e7
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 97%

---


# Creación de perfiles{#creating-profiles}

En Adobe Campaign, los perfiles se utilizan de forma predeterminada para definir el destinatario principal de los mensajes.

>[!NOTE]
>
>También es posible crear perfiles mediante la API de Adobe Campaign Standard. Para obtener más información, consulte [la documentación dedicada](../../api/using/creating-profiles.md).

Para crear o actualizar un perfil en Campaign, puede:

* Importar una lista de perfil desde un archivo mediante un [flujo de trabajo](../../automating/using/creating-import-workflow-templates.md)
* Recopilar datos en línea, mediante [páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md)
* Realizar una creación masiva mediante la [API de REST](../../api/using/get-started-apis.md)
* Sincronizar perfiles de [Microsoft Dynamics](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md)
* Introduzca datos mediante las pantallas de interfaz gráfica, tal como se explica a continuación.

Por ejemplo, para crear un nuevo perfil directamente en la interfaz de usuario, siga los pasos a continuación:

1. En la página de inicio de Adobe Campaign, haga clic en la tarjeta **Perfiles del cliente** o en la pestaña **Perfiles** para acceder a la lista de perfiles.

   ![](assets/profile_creation_1.png)

1. Haga clic **[!UICONTROL Create]**.

   ![](assets/profile_creation.png)

1. Introduzca los datos del perfil.

   ![](assets/profile_creation1.png)

   * La información de contacto, como el nombre, apellidos, sexo, fecha de nacimiento, foto, idioma preferido (para [correos electrónicos multilingües](../../channels/using/creating-a-multilingual-email.md)) ayuda a personalizar mejor los envíos.
   * El **[!UICONTROL Time zone]** del perfil se utiliza para realizar envíos en el huso horario adecuado. Para obtener más información, consulte [esta sección](../../sending/using/sending-messages-at-the-recipient-s-time-zone.md).
   * La categoría **[!UICONTROL Channels]**, que contiene la dirección de correo electrónico, el número de teléfono móvil y la información de exclusión, le permite saber por qué canal se puede acceder al perfil.
   * La categoría **[!UICONTROL No longer contact]** se actualiza en cuanto el perfil cancela la suscripción a un canal.
   * La categoría **[!UICONTROL Address]** contiene la dirección postal que debe rellenarse junto con la opción **[!UICONTROL Address specified]** para enviar [correo postal](../../channels/using/about-direct-mail.md) a dicho perfil. Si la opción **[!UICONTROL Address specified]** no está marcada, este perfil se excluye de todos los envíos de correo postal.
   * The **[!UICONTROL Access authorization]** category indicates the profile&#39;s organizational units to [manage permissions](../../administration/using/about-access-management.md). Para añadir los campos organizativos a los perfiles, consulte la sección [Partición de perfiles](../../administration/using/organizational-units.md#partitioning-profiles).
   * La categoría **[!UICONTROL Traceability]** se actualiza automáticamente con información relativa al usuario que ha creado o modificado el perfil.

1. Haga clic en **[!UICONTROL Create]** para guardar el perfil.

El perfil aparece ahora en la lista.

>[!NOTE]
>El campo de idioma preferido se utiliza para seleccionar el idioma al enviar mensajes multilingües. Para obtener más información sobre los mensajes multilingües, [consulte esta página](../../channels/using/creating-a-multilingual-email.md).

**Temas relacionados:**

* Guía paso a paso de [páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md)
* Vídeo sobre la [importación de perfiles](https://video.tv.adobe.com/v/24993?captions=spa)
