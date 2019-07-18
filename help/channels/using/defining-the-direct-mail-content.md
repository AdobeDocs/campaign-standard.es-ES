---
title: Definición del contenido de correo directo
seo-title: Definición del contenido de correo directo
description: Definición del contenido de correo directo
seo-description: Descubra cómo definir el contenido para la entrega de correo directo.
page-status-flag: no activado nunca
uuid: c 1234 c 06-4 d 22-46 d 7-ad 1 b -3 c 88660 f 9 b 06
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: correo directo
discoiquuid: 9 e 73 d 6 b 5-41 b 4-474 b-a 880-a 0 cd 5999 c 2 d 1
context-tags: delivery, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Defining the direct mail content{#defining-the-direct-mail-content}

You can either define the content in the last screen of the creation wizard or by clicking on the **Content** section of the delivery dashboard.

![](assets/direct_mail_6.png)

The **[!UICONTROL Content]** definition screen is specific to the direct mail channel. It is divided into four tabs: **[!UICONTROL Extraction]**, **[!UICONTROL File structure]**, **[!UICONTROL Header]** and **[!UICONTROL Footer]**.

![](assets/direct_mail_11.png)

## Defining the extraction {#defining-the-extraction}

1. Comience definiendo el nombre del archivo de extracción. Click on the button to the right of the **[!UICONTROL Output file]** field and enter the desired label. You can use personalization fields, content blocks and dynamic text (see [Defining content](../../designing/using/example--email-personalization.md)). Por ejemplo, puede completar la etiqueta con el ID de entrega o la fecha de extracción.

   ![](assets/direct_mail_12.png)

1. Click the **[!UICONTROL +]** or **[!UICONTROL Add an element]** button to add an output column. The **[!UICONTROL Output columns]** let you define the profile information (columns) to be exported into the output file.

   >[!CAUTION]
   >
   >Asegúrese de que los perfiles incluyan una dirección postal, ya que esta información es esencial para el proveedor de correo directo. Also make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. See [Recommendations](../../channels/using/about-direct-mail.md#recommendations).

   ![](assets/direct_mail_13.png)

1. Cree tantas columnas como necesite. Puede editar columnas haciendo clic en sus expresiones y etiquetas.

>[!NOTE]
>
>For more information on output column definition, refer to the [Extract file](../../automating/using/extract-file.md) workflow activity section.

## Defining the file structure {#defining-the-file-structure}

The **File structure** tab allows you to configure the output, date, and number formats for the file that will be exported.

![](assets/direct_mail_14.png)

>[!NOTE]
>
>The available options are detailed in the [Extract file](../../automating/using/extract-file.md) workflow activity sections.

## Defining the header and footer {#defining-the-header-and-footer}

A veces es necesario agregar información al principio o al final del archivo de extracción. For this, use the **[!UICONTROL Header]** and **[!UICONTROL Footer]** tabs of the **[!UICONTROL Content]** configuration screen.

![](assets/direct_mail_7.png)

Por ejemplo, es posible que desee incluir, para el proveedor de correo directo, la información del remitente en el encabezado del archivo. Es posible personalizar el pie de página y el encabezado con información disponible en el contexto del envío. See [Defining content](../../designing/using/example--email-personalization.md).

The sender address is defined in the **[!UICONTROL Send]** section of the direct mail properties or at the template level.

![](assets/direct_mail_24.png)

