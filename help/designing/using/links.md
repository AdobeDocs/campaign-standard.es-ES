---
title: Adición de vínculos
description: Descubra cómo administrar vínculos con el Diseñador de correo electrónico.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7642ae3d027351abe1c44e173d3db50b9568bfcd

---


# Adición de vínculos {#links}

## Inserción de un enlace {#inserting-a-link}

El editor le permite personalizar un correo electrónico o una página de aterrizaje mediante la inserción de vínculos en los elementos de contenido HTML.

Puede insertar un enlace en cualquier elemento de página: imagen, palabra, grupo de palabras, bloque de texto, etc.

>[!NOTE]
>
>Las siguientes imágenes muestran cómo insertar un vínculo mediante el Diseñador de [correo electrónico](../../designing/using/designing-content-in-adobe-campaign.md) en un mensaje de correo electrónico.

1. Seleccione un elemento y haga clic en **[!UICONTROL Insert link]**en la barra de herramientas contextual.

   ![](assets/des_insert_link.png)

1. Elija el tipo de vínculo que desea crear:

   * **Vínculo** externo: inserte un vínculo a una URL externa.

      Puede definir la personalización de las direcciones URL. Consulte [Personalización de direcciones URL](../../designing/using/using-reusable-content.md#creating-a-content-fragment).

   * **Página** de aterrizaje: proporcione acceso a una página de aterrizaje de Adobe Campaign.
   * **Vínculo** de suscripción: inserte un vínculo para suscribirse a un servicio de Adobe Campaign.
   * **Vínculo** de cancelación de suscripción: inserte un vínculo para cancelar la suscripción a un servicio de Adobe Campaign.
   * **Vínculo que define una acción**: define una acción cuando se hace clic en un elemento de la página de aterrizaje.

      >[!NOTE]
      >
      >Este tipo de vínculo solo está disponible para páginas de aterrizaje.

1. Puede modificar el texto mostrado al destinatario.
1. Puede establecer el comportamiento del explorador cuando el usuario haga clic en el vínculo (por ejemplo, abra una ventana nueva).

   >[!NOTE]
   >
   >La definición del comportamiento del explorador solo se aplica a las páginas de aterrizaje.

1. Guarde los cambios.

Una vez creado el vínculo, puede modificarlo desde el panel Configuración. Haga clic en el icono del lápiz para editar sus parámetros.

![](assets/des_link_edit.png)

Al editar un correo electrónico con el Diseñador [de](../../designing/using/designing-content-in-adobe-campaign.md)correo electrónico, puede acceder y modificar fácilmente los vínculos que ha creado a partir de la tabla que enumera todas las direcciones URL incluidas en el correo electrónico. Esta lista le permite tener una vista centralizada y localizar cada URL en el contenido del correo electrónico. Para acceder a él, consulte [Acerca de las direcciones URL](#about-tracked-urls)rastreadas.

![](assets/des_link_list.png)

>[!NOTE]
>
>Las direcciones URL personalizadas, como la URL **de página** espejo o el vínculo de **cancelación de suscripción** , no se pueden modificar desde esta lista. Todos los demás vínculos son editables.

**Temas relacionados**:

* [Inserción de un campo personalizado](../../designing/using/personalization.md#inserting-a-personalization-field)
* [Adición de bloques de contenido](../../designing/using/personalization.md#adding-a-content-block)
* [Definición de contenido dinámico](../../designing/using/personalization.md#defining-dynamic-content-in-an-email)

## Acerca de las direcciones URL rastreadas {#about-tracked-urls}

Adobe Campaign permite rastrear el comportamiento de los destinatarios cuando hacen clic en una dirección URL incluida en un mensaje de correo electrónico. Para obtener más información sobre el seguimiento, consulte [esta sección](../../sending/using/tracking-messages.md#about-tracking).

El **[!UICONTROL Links]**icono de la barra de acciones muestra automáticamente la lista de todas las direcciones URL del contenido que se rastreará.

![](assets/des_links.png)

>[!NOTE]
>
>El seguimiento está activado de forma predeterminada. Esta funcionalidad solo está disponible para correos electrónicos, si el seguimiento se ha activado en Adobe Campaign. For more on the tracking parameters, refer to [this section](../../administration/using/configuring-email-channel.md#tracking-parameters).

La dirección URL, la categoría, la etiqueta y el tipo de seguimiento de cada vínculo se pueden modificar desde esta lista. Para editar un vínculo, haga clic en el icono de lápiz correspondiente.

![](assets/des_links_tracking.png)

Para cada URL rastreada, puede establecer el modo de seguimiento en uno de estos valores:

* **Seguimiento**: activa el seguimiento en esta dirección URL.
* **Página** de reflejo: considera que esta URL es una URL de página reflejada.
* **Nunca**: nunca activa el seguimiento de esta dirección URL. Esta información se guarda: si la dirección URL vuelve a aparecer en un mensaje futuro, su seguimiento se desactiva automáticamente.
* **Exclusión**: considera esta URL como una URL de exclusión o de cancelación de suscripción.

![](assets/des_link_tracking_type.png)

También puede desactivar o activar el seguimiento de cada URL.

>[!NOTE]
>
>De forma predeterminada, en Adobe Campaign, se realiza un seguimiento de todas las direcciones URL de contenido, excepto la URL **de la página** de reflejo y el vínculo de **cancelación de suscripciones** .

Puede reagrupar las direcciones URL editando el **[!UICONTROL Category]**campo, según las direcciones URL utilizadas en el mensaje. Estas categorías pueden mostrarse en informes, como en[direcciones URL y flujos](../../reporting/using/urls-and-click-streams.md)de clics.

![](assets/des_link_tracking_category.png)

Al crear un informe, desde la **[!UICONTROL Components]**ficha, seleccione**[!UICONTROL Dimension]** y desplácese hacia abajo en la lista para acceder a los componentes de seguimiento. Por ejemplo, arrastre y suelte **[!UICONTROL Tracking URL Category]**en el espacio de trabajo para mostrar los resultados según la categoría de seguimiento de cada URL en la que se hizo clic.

![](assets/des_link_tracking_report.png)

Para obtener más información sobre la creación de informes personalizados, consulte [esta sección](../../reporting/using/about-dynamic-reports.md).
