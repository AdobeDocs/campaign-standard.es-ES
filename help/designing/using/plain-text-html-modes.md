---
title: Edición de texto sin formato, HTML y formatos del correo electrónico móviles
description: Descubra los modos de texto sin formato y HTML
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '776'
ht-degree: 0%

---


# Edición de texto sin formato, HTML y formatos del correo electrónico móviles {#plain-text-and-html-modes}

El Diseñador de correo electrónico permite editar varias representaciones de los correos electrónicos. Puede generar una versión de texto de su correo electrónico, editar la fuente HTML de un correo electrónico y diseñar correos electrónicos para la vista móvil.

## Generación de una versión de texto del correo electrónico {#generating-a-text-version-of-the-email}

De forma predeterminada, la versión del **[!UICONTROL Plain text]** correo electrónico se genera automáticamente y se sincroniza con la **[!UICONTROL Edit]** versión.

Los campos de personalización y los bloques de contenido añadidos a la versión HTML también se sincronizan con la versión de texto sin formato.

>[!NOTE]
>
>Para utilizar bloques de contenido en versión de texto sin formato, asegúrese de que no contienen código HTML.

Para que una versión de texto sin formato sea distinta de la versión HTML, puede desactivar esta sincronización haciendo clic en el **[!UICONTROL Sync with HTML]** conmutador de la **[!UICONTROL Plain text]** vista del correo electrónico.

![](assets/email_designer_textversion.png)

A continuación, puede editar la versión de texto sin formato según lo desee.

>[!NOTE]
>
>Si edita la **[!UICONTROL Plain text]** versión mientras la sincronización está deshabilitada, la próxima vez que active la **[!UICONTROL Sync with HTML]** opción, todos los cambios realizados en la versión de texto sin formato se reemplazarán con la versión HTML. Los cambios realizados en la **[!UICONTROL Plain text]** vista no pueden reflejarse en la **[!UICONTROL HTML]** vista.

## Edición de una fuente de contenido de correo electrónico en HTML {#editing-an-email-content-source-in-html}

Para los usuarios y la depuración más avanzados, puede realizar la vista y edición del contenido del correo electrónico directamente en HTML.

Tiene dos formas de editar la versión HTML del correo electrónico:

* Seleccione **[!UICONTROL Edit]** > **[!UICONTROL HTML]** para abrir la versión HTML de todo el correo electrónico.

   ![](assets/email_designer_html1.png)

* En la interfaz WYSIWYG, seleccione un elemento y haga clic en el **[!UICONTROL Source code]** icono .

   Solo se muestra el origen del elemento seleccionado. Puede editar el código fuente si el elemento seleccionado es un componente de **[!UICONTROL HTML]** contenido. Otros componentes están en modo de solo lectura, pero se pueden editar en la versión HTML completa del correo electrónico.

   ![](assets/email_designer_html2.png)

Si modifica el código HTML, podría romperse la respuesta del correo electrónico. Asegúrese de probarlo con el **[!UICONTROL Preview]** botón. Consulte [Vista previa de mensajes](../../sending/using/previewing-messages.md).

## Diseño de correos electrónicos para representación móvil {#switching-to-mobile-view}

Puede ajustar el diseño interactivo de un correo electrónico editando por separado todas las opciones de estilo para la visualización móvil. Por ejemplo, puede adaptar los márgenes y el relleno, utilizar tamaños de fuente más pequeños o grandes, cambiar los botones o aplicar diferentes colores de fondo que sean específicos de la versión móvil del correo electrónico.

Todas las opciones de estilo están disponibles en la vista móvil. La configuración de estilo de Email Designer se presenta anteriormente en esta página.

1. Cree un correo electrónico y un inicio para editar el contenido. Para obtener más información sobre esto, consulte [Diseño de contenido de correo electrónico desde cero](../../designing/using/designing-from-scratch.md#designing-an-email-content-from-scratch).
1. Para acceder a la vista móvil dedicada, seleccione el **[!UICONTROL Switch to mobile view]** botón.

   ![](assets/email_designer_mobile_view_switch.png)

   Se muestra la versión móvil del correo electrónico. Contiene todos los componentes y estilos definidos en la vista de escritorio.

1. Edite de forma independiente todos los ajustes de estilo, como color de fondo, alineación, margen, familia de fuentes, color de texto, etc.

   ![](assets/email_designer_mobile_view.png)

1. Al editar cualquier ajuste de estilo en la vista móvil, las modificaciones solo se aplican a la pantalla móvil.

   Por ejemplo, reduzca el tamaño de una imagen, agregue un fondo verde y cambie el relleno en la vista móvil.

   ![](assets/email_designer_mobile_view_change.png)

1. Puede ocultar un componente cuando se muestra en un dispositivo móvil. Para ello, seleccione **[!UICONTROL Show only on desktop devices]** una de las opciones **[!UICONTROL Display options]**.

   También puede ocultar este componente en dispositivos de escritorio, lo que significa que solo se mostrará en dispositivos móviles. Para ello, seleccione **[!UICONTROL Show only on mobile devices]**.

   Por ejemplo, esta opción le permite mostrar una imagen específica en dispositivos móviles y otra imagen en dispositivos de escritorio.

   Puede establecer esta opción desde la vista móvil o de escritorio.

   ![](assets/email_designer_mobile_hide.png)

1. Vuelva a hacer clic en el **[!UICONTROL Switch to mobile view]** botón para volver a la vista de escritorio estándar. Los cambios de estilo que acaba de realizar no se reflejan.

   ![](assets/email_designer_mobile_view_desktop_no-change.png)

   >[!NOTE]
   >
   >La única excepción son los **[!UICONTROL Style inline]** ajustes. Cualquier cambio de configuración en línea de estilo también se aplica a la vista de escritorio estándar.

1. Cualquier otro cambio en la estructura o el contenido del correo electrónico, como ediciones de texto, carga de una nueva imagen, adición de un nuevo componente, etc. también se aplica a la vista estándar.

   Por ejemplo, vuelva a la vista móvil, edite texto y sustituya una imagen.

   ![](assets/email_designer_mobile_view_change_content.png)

1. Vuelva a hacer clic en el **[!UICONTROL Switch to mobile view]** botón para volver a la vista de escritorio estándar. Los cambios se reflejan.

   ![](assets/email_designer_mobile_view_desktop_content-change.png)

1. Al eliminar un estilo en la vista móvil, vuelve al estilo aplicado en el modo de escritorio.

   Por ejemplo, en la vista móvil, aplique un color de fondo verde a un botón.

   ![](assets/email_designer_mobile_view_background_mobile.png)

1. Cambie a la vista de escritorio y aplique un fondo gris al mismo botón.

   ![](assets/email_designer_mobile_view_background_desktop.png)

1. Vuelva a cambiar a la vista móvil y ahora deshabilite la **[!UICONTROL Background color]** configuración.

   ![](assets/email_designer_mobile_view_background_mobile_disabled.png)

   Ahora se aplica el color de fondo definido en la vista de escritorio: se vuelve gris (no en blanco).

   La única excepción es la **[!UICONTROL Border color]** configuración. Cuando está desactivado en la vista móvil, ya no se aplica ningún borde, incluso si se define un color de borde en la vista de escritorio.

>[!NOTE]
>
>La vista móvil no está disponible en [fragmentos](../../designing/using/using-reusable-content.md#about-fragments).
