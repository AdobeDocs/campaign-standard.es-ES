---
title: Modos de texto sin formato y HTML
description: Descubra los modos de texto sin formato y HTML
page-status-flag: nunca activado
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: diseñar
content-type: referencia
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Modos de texto sin formato y HTML {#plain-text-and-html-modes}

## Generación de una versión de texto del correo electrónico {#generating-a-text-version-of-the-email}

De forma predeterminada, la versión del **[!UICONTROL Plain text]** correo electrónico se genera automáticamente y se sincroniza con la **[!UICONTROL Edit]** versión.

Los campos de personalización y los bloques de contenido añadidos a la versión HTML también se sincronizan con la versión de texto sin formato.

>[!NOTE]
>
>Para utilizar bloques de contenido en versión de texto sin formato, asegúrese de que no contienen código HTML.

Para que una versión de texto sin formato sea distinta de la versión HTML, puede desactivar esta sincronización haciendo clic en el **[!UICONTROL Sync with HTML]** conmutador desde la **[!UICONTROL Plain text]** vista del correo electrónico.

![](assets/email_designer_textversion.png)

A continuación, puede editar la versión de texto sin formato según lo desee.

>[!NOTE]
>
>Si edita la **[!UICONTROL Plain text]** versión mientras la sincronización está deshabilitada, la próxima vez que active la **[!UICONTROL Sync with HTML]** opción, todos los cambios realizados en la versión de texto sin formato se reemplazarán con la versión HTML. Los cambios realizados en **[!UICONTROL Plain text]** la vista no pueden reflejarse en la **[!UICONTROL HTML]** vista.

## Edición de una fuente de contenido de correo electrónico en HTML {#editing-an-email-content-source-in-html}

Para los usuarios y la depuración más avanzados, puede ver y editar el contenido del correo electrónico directamente en HTML.

Tiene dos formas de editar la versión HTML del correo electrónico:

* Seleccione **[!UICONTROL Edit]** &gt; **[!UICONTROL HTML]** para abrir la versión HTML de todo el correo electrónico.

   ![](assets/email_designer_html1.png)

* En la interfaz WYSIWYG, seleccione un elemento y haga clic en el **[!UICONTROL Source code]** icono .

   Solo se muestra el origen del elemento seleccionado. Puede editar el código fuente si el elemento seleccionado es un componente de **[!UICONTROL HTML]** contenido. Otros componentes están en modo de solo lectura, pero se pueden editar en la versión HTML completa del correo electrónico.

   ![](assets/email_designer_html2.png)

Si modifica el código HTML, podría romperse la respuesta del correo electrónico. Asegúrese de probarlo con el **[!UICONTROL Preview]** botón. Consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md).
