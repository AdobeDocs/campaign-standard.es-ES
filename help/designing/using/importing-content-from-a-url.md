---
title: Importación de contenido desde una URL
seo-title: Importación de contenido desde una URL
description: Importación de contenido desde una URL
seo-description: Obtenga información sobre cómo cargar contenido desde una URL existente al crear un correo electrónico.
page-status-flag: no activado nunca
uuid: 7 db 6 c 20 f -7004-4 fb 8-add 9-362 eab 3 d 2795
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: cargar contenido
discoiquuid: 738 b 7 c 8 a -88 eb -491 c-a 4 d 0-078 b 0959 b 973
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Importing content from a URL{#importing-content-from-a-url}

Antes de importar contenido desde una URL, asegúrese de que sigue los requisitos siguientes:

* El contenido debe estar disponible públicamente a través de esta URL.
* For security reasons, only URLs beginning with **[!UICONTROL https]** are allowed.
* Asegúrese de que todos los recursos (imágenes, CSS) estén configurados en vínculos absolutos y en HTTPS. De lo contrario, después de enviar el correo electrónico, la página reflejada se mostrará sin sus recursos. Este es un ejemplo de definición absoluta de vínculo:

   ```
   <a href="https://www.mywebsite.com/images/myimage.png">
   ```

>[!NOTE]
>
>La carga de contenido desde una URL solo está disponible para el canal de correo electrónico.

Para recuperar el contenido existente de una dirección URL, siga los pasos a continuación:

1. From the Email Designer home page, select the **[!UICONTROL Import from URL]** button.

   ![](assets/email_designer_importfromurl.png)

1. Defina la URL desde la que se recuperará el contenido.
1. Click **[!UICONTROL Confirm]**.

**Tema relacionado:**

[Importación de contenido desde](https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html#Workingwithexistingcontent) un vídeo de URL

## Retrieving content from a URL automatically at preparation time {#retrieving-content-from-a-url-automatically-at-preparation-time}

La importación de contenido desde una URL durante la preparación de los mensajes le permite recuperar el contenido HTML más reciente cada vez que se prepare el correo electrónico. De este modo, el contenido de los correos electrónicos recurrentes siempre estará actualizado al momento de su envío. Esta función también permite crear un mensaje programado en una fecha específica aunque el contenido aún no esté listo.

Para recuperar contenido al momento de la preparación, siga los pasos a continuación:

1. Select the **[!UICONTROL Content imported during preparation]** option.

   ![](assets/email_designer_importfromurl2.png)

1. El contenido URL se muestra en el editor como solo lectura.

   >[!CAUTION]
   >
   >En este paso, no se debe tener en cuenta la visualización HTML en el editor de contenido. Se recuperará en la fase de preparación.

1. To preview the URL content that has been retrieved, open the message once it is created then click the **[!UICONTROL Preview]** button.

Es posible personalizar la URL remota desde la que se recuperará el contenido. Para ello, siga los pasos a continuación:

1. Click the email label on top of the screen to acces the Email Designer **[!UICONTROL Properties]** tab.
1. Find the **[!UICONTROL Remote URL]** field.

   ![](assets/email_designer_importfromurl4.png)

1. Inserte el campo de personalización, el bloque de contenido o el texto dinámico que desee.

   The **[!UICONTROL Current date - YYYYMMDD]** content block, for example, enables you to insert the date of the day.

   >[!NOTE]
   >
   >The available personalization fields are linked to **Delivery** attributes only (email creation date, status, campaign label...).

