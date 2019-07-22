---
title: Adición de un bloque de contenido
seo-title: Adición de un bloque de contenido
description: Adición de un bloque de contenido
seo-description: Descubra los diversos bloques de contenido dinámicos predeterminados que puede utilizar para personalizar sus mensajes y aprender a crear bloques de contenido personalizados.
page-status-flag: no activado nunca
uuid: 08153 ea 0-42 fb -4 c 0 b -8 d 4 b -9407540748 d 6
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: personalizar contenido
discoiquuid: 3 ffda 143-f 42 a -4 cf 9-b 43 c-e 53 d 24549025
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 84bc011b079c9f620ea672bf081e54adc023aa07

---


# Adding a content block{#adding-a-content-block}

Adobe Campaign ofrece una lista de bloques de contenido preconfigurados. Estos bloques de contenido son dinámicos, personalizados y tienen un procesamiento específico. Por ejemplo, puede agregar un saludo o un vínculo a la página de reflejo.

>[!NOTE]
>
>The images below show how to insert a content block using the [Email Designer](../../designing/using/about-email-content-design.md#about-the-email-designer) for an email.

Para agregar un bloque de contenido:

1. Click inside a text block, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert content block]**. For more on the Email Designer interface, see [this section](../../designing/using/about-email-content-design.md#email-designer-interface).

   ![](assets/email_content_block_1.png)

1. Seleccione el bloque de contenido que desee insertar. Los bloques disponibles varían según el contexto (correo electrónico o página de aterrizaje).

   ![](assets/email_content_block_2.png)

1. Click **[!UICONTROL Save]**.

El nombre del bloque de contenido aparece en el editor y se resalta en amarillo. Se adaptará automáticamente al perfil cuando se genere la personalización.

![](assets/email_content_block_3.png)

Los bloques de contenido predeterminados son:

* **[!UICONTROL Database URL in emails (EmailUrlBase)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Mirror page URL (MirrorPageUrl)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Link to mirror page (MirrorPage)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Greetings (Greetings)]**
* **[!UICONTROL Unsubscription link (UnsubscriptionLink)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Social network sharing links (LandingPageViralLinks)]**: Este bloque de contenido sólo se puede utilizar en una **página de aterrizaje**.
* **[!UICONTROL Default sender name (DefaultSenderName)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Name of default reply-to email address (DefaultReplyName)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Email address of default sender (DefaultSenderAddress)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Default error email address (DefaultErrorAddress)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Default reply-to email address (DefaultReplyAddress)]**: Este bloque de contenido solo se puede utilizar en **una entrega**.
* **[!UICONTROL Brand name (BrandingUsualName)]**
* **[!UICONTROL Link to the brand website (BrandingWebSiteLink)]**
* **[!UICONTROL Brand logo (BrandingLogo)]**
* **[!UICONTROL Notification style (notificationStyle)]**

## Creating custom content blocks {#creating-custom-content-blocks}

Puede definir nuevos bloques de contenido que se insertarán en un mensaje o página de aterrizaje.

Para crear un bloque de contenido, siga estos pasos:

1. Click **[!UICONTROL Resources > Content blocks]** from the advanced menu to access the list of content blocks.
1. Click the **[!UICONTROL Create]** button or duplicate a pre-existing content block.

   ![](assets/content_bloc_01.png)

1. Introduzca una etiqueta.
1. Select the block's **[!UICONTROL Content type]**. Existen tres opciones disponibles:

   * **[!UICONTROL Shared]**: El bloque de contenido se puede utilizar en una entrega o en una página de aterrizaje.
   * **[!UICONTROL Delivery]**: El bloque de contenido solo se puede utilizar en una entrega.
   * **[!UICONTROL Landing page]**: El bloque de contenido sólo se puede utilizar en una página de aterrizaje.
   ![](assets/content_bloc_02.png)

1. You can select a **[!UICONTROL Targeting dimension]**. For more on this, see [About targeting dimension](../../designing/using/adding-a-content-block.md#about-targeting-dimension).

   ![](assets/content_bloc_04.png)

1. You can select the **[!UICONTROL Depends on format]** option to define two different blocks: one for HTML emails, and one for emails in text format. En el editor (HTML y texto) se mostrarán dos fichas para definir el contenido correspondiente.

   ![](assets/content_bloc_03.png)

1. Enter the content of the content block(s), and click the **[!UICONTROL Create]** button.

El bloque de contenido ahora se puede utilizar en el editor de contenido de un mensaje o una página de aterrizaje.

>[!CAUTION]
>
>When editing the content of a block, make sure there are no extra white spaces between the beginning and the end of your *if* statements. En HTML, los espacios en blanco se muestran en pantalla y, por lo tanto, afectan la presentación del contenido.

## About targeting dimension {#about-targeting-dimension}

La dimensión de objetivo permite definir en qué tipo de mensaje puede utilizar el bloque de contenido. Esto sirve para evitar el uso de bloques incorrectos en un mensaje, lo que puede provocar errores.

De hecho, al editar un mensaje, solo puede seleccionar bloques de contenido con una dimensión de objetivo que sea compatible con la dimensión de targeting del mensaje.

For example, the **[!UICONTROL Unsubscription link]** block's targeting dimension is **[!UICONTROL Profiles]** because it contains personalization fields specific to the **[!UICONTROL Profiles]** resource. Therefore, you cannot use an **[!UICONTROL Unsubscription link]** block in an [event transactional message](../../channels/using/event-transactional-messages.md), because the targeting dimension of that type of message is **[!UICONTROL Real-time events]**. However, you can use the **Unsubscription link** block in a [profile transactional message](../../channels/using/profile-transactional-messages.md), because the targeting dimension of that type of message is **Profiles**. Finally, the **[!UICONTROL Link to mirror page]** block does not have a targeting dimension, so you can use it in any message.

Si deja este campo vacío, el bloque de contenido será compatible con todos los mensajes, independientemente de la dimensión de objetivo. Si establece una dimensión de objetivo, dicho bloque solo será compatible con mensajes que tengan la misma dimensión de objetivo.

For more on this, refer to [Targeting dimensions and resources](../../automating/using/query.md#targeting-dimensions-and-resources).
