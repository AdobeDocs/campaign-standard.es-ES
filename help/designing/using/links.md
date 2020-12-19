---
solution: Campaign Standard
product: campaign
title: Añadir vínculos
description: Descubra cómo administrar vínculos con el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 10%

---


# Añadiendo vínculos {#links}

## Inserción de un vínculo {#inserting-a-link}

El editor le permite personalizar un correo electrónico o una página de aterrizaje mediante la inserción de vínculos en los elementos de contenido HTML.

Puede insertar un vínculo en cualquier elemento de página: imagen, palabra, grupo de palabras, bloque de texto, etc.

>[!NOTE]
>
>Las siguientes imágenes muestran cómo insertar un vínculo mediante [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md) en un mensaje de correo electrónico.

1. Seleccione un elemento y haga clic en **[!UICONTROL Insert link]** en la barra de herramientas contextual.

   ![](assets/des_insert_link.png)

1. Elija el tipo de vínculo que desea crear:

   * **Vínculo** externo: inserte un vínculo a una URL externa.

      Puede definir la personalización de las direcciones URL. Consulte [Personalización de direcciones URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Página de aterrizaje**: dar acceso a una página de aterrizaje de Adobe Campaign.
   * **Vínculo** de suscripción: inserte un vínculo para suscribirse a un servicio de Adobe Campaign.
   * **Vínculo** baja: inserte un vínculo para cancelar la suscripción a un servicio de Adobe Campaign.
   * **Vínculo que define una acción**: define una acción cuando se hace clic en un elemento de la página de aterrizaje.

      >[!NOTE]
      >
      >Este tipo de vínculo solo está disponible para páginas de aterrizaje.

1. Puede modificar el texto mostrado en el destinatario.
1. Puede establecer el comportamiento del explorador cuando el usuario haga clic en el vínculo (por ejemplo, abra una ventana nueva).

   >[!NOTE]
   >
   >La definición del comportamiento del navegador solo se aplica a páginas de aterrizaje.

1. Guarde los cambios.

Una vez creado el vínculo, puede modificarlo desde el panel Configuración. Haga clic en el icono del lápiz para editar sus parámetros.

![](assets/des_link_edit.png)

Al editar un mensaje de correo electrónico con [Email Designer](../../designing/using/designing-content-in-adobe-campaign.md), puede acceder y modificar fácilmente los vínculos que creó a partir de la tabla que enumera todas las direcciones URL incluidas en el mensaje de correo electrónico. Esta lista le permite tener una vista centralizada y localizar cada URL en el contenido del correo electrónico. Para acceder a él, consulte [Acerca de las direcciones URL rastreadas](#about-tracked-urls).

![](assets/des_link_list.png)

>[!NOTE]
>
>Las direcciones URL personalizadas como **URL de Página espejo** o **vínculo Baja** no se pueden modificar desde esta lista. Todos los demás vínculos son editables.

**Temas relacionados**:

* [Inserción de un campo de personalización](../../designing/using/personalization.md#inserting-a-personalization-field).
* [Añadir bloques de contenido](../../designing/using/personalization.md#adding-a-content-block)
* [Definición de contenido dinámico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Acerca de las direcciones URL rastreadas {#about-tracked-urls}

Adobe Campaign le permite rastrear el comportamiento de sus destinatarios cuando hacen clic en una URL incluida en un mensaje de correo electrónico. Para obtener más información de seguimiento, consulte [esta sección](../../sending/using/tracking-messages.md#about-tracking).

El icono **[!UICONTROL Links]** de la barra de acciones muestra automáticamente la lista de todas las direcciones URL del contenido que se rastreará.

![](assets/des_links.png)

>[!NOTE]
>
>El seguimiento está activado de forma predeterminada. Esta funcionalidad solo está disponible para correos electrónicos, si el seguimiento se ha activado en Adobe Campaign. Para obtener más información sobre los parámetros de seguimiento, consulte [esta sección](../../administration/using/configuring-email-channel.md#tracking-parameters).

La dirección URL, la categoría, la etiqueta y el tipo de seguimiento de cada vínculo se pueden modificar desde esta lista. Para editar un vínculo, haga clic en el icono de lápiz correspondiente.

![](assets/des_links_tracking.png)

Para cada URL rastreada, puede establecer el modo de seguimiento en uno de estos valores:

* **Seguimiento**: activa el seguimiento en esta dirección URL.
* **Mirror page**: considera esta URL como una URL de página espejo.
* **Never**: nunca activa el seguimiento de esta dirección URL. Esta información se guarda: si la dirección URL vuelve a aparecer en un mensaje futuro, su seguimiento se desactiva automáticamente.
* **Opt-out**: considera esta URL como una URL de exclusión o de baja.

![](assets/des_link_tracking_type.png)

También puede desactivar o activar el seguimiento de cada URL.

>[!NOTE]
>
>De forma predeterminada, en Adobe Campaign, se realiza un seguimiento de todas las direcciones URL de contenido excepto **URL de Página espejo** y **vínculo Baja**.

Puede reagrupar las direcciones URL editando el campo **[!UICONTROL Category]**, según las direcciones URL utilizadas en el mensaje. Estas categorías se pueden mostrar en informes, por ejemplo en [direcciones URL y haga clic en flujos](../../reporting/using/urls-and-click-streams.md).

![](assets/des_link_tracking_category.png)

Al crear un informe, en la ficha **[!UICONTROL Components]**, seleccione **[!UICONTROL Dimension]** y desplácese hacia abajo por la lista para acceder a los componentes de seguimiento. Por ejemplo: arrastre y suelte **[!UICONTROL Tracking URL Category]** en el área de trabajo para mostrar los resultados según la categoría de seguimiento de cada dirección URL en la que se hizo clic.

![](assets/des_link_tracking_report.png)

Para obtener más información sobre la creación de informes personalizados, consulte [esta sección](../../reporting/using/about-dynamic-reports.md).
