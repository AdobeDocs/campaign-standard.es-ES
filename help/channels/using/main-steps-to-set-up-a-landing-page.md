---
title: Pasos principales para configurar una página de aterrizaje
seo-title: Pasos principales para configurar una página de aterrizaje
description: Pasos principales para configurar una página de aterrizaje
seo-description: Conozca los pasos principales para configurar una página de aterrizaje
page-status-flag: nunca activado
uuid: b316bf47-7d98-46fa-ab4f-67ff50de8095
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: landing-pages
discoiquuid: ca8d1698-6e8a-4f5a-b017-74a152e14286
context-tags: landingPage,asistente;landingPage,información general;landingPage,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1f100f6b041c6dbb298113b4ecc7830951714131

---


# Pasos principales para configurar una página de aterrizaje {#main-steps-create-a-landing-page}

## Acerca de la creación de páginas de aterrizaje

Los pasos principales para configurar las páginas de aterrizaje son los siguientes:

![](assets/lp_steps.png)

En esta página encontrará información sobre cada uno de estos pasos, así como referencias a las documentaciones dedicadas para obtener más detalles.

## Configurar la plantilla de página de aterrizaje {#configure-the-landing-page-template}

Antes de configurar una página de aterrizaje, el primer paso es configurar una plantilla de página de aterrizaje que se ajuste a sus necesidades. Una vez preparada la plantilla, todas las páginas de aterrizaje basadas en ella se preconfigurarán con los parámetros deseados.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]** y, a continuación, duplique la plantilla que desee utilizar.
1. En las propiedades de la plantilla, especifique todos los parámetros que las páginas de aterrizaje deben tener en común.  Por ejemplo: la dimensión de objetivo, los parámetros de acceso a la página para visitantes identificados o no identificados, las acciones específicas para la validación del formulario por parte de un visitante, la marca o logotipo que se va a utilizar en el contenido, etc.
1. Guarde las modificaciones.

For more on landing page templates, refer to [this section](../../channels/using/about-landing-pages.md).

![](assets/lp-steps1.png)

##  Crear y configurar la página de aterrizaje {#create-and-configure-the-landing-page}

A partir de la plantilla definida en el paso anterior, cree una nueva página de aterrizaje en un programa o campaña.

1. Cree la página de aterrizaje según la plantilla deseada.
1. Introduzca los parámetros generales de la página de aterrizaje (etiqueta, descripción, etc.).
1. Luego accederá al tablero de la página de aterrizaje. Si es necesario, edite las propiedades de la página de aterrizaje. De forma predeterminada, las propiedades son las configuradas en la plantilla de página de aterrizaje.
Por motivos de seguridad y rendimiento de la plataforma, le recomendamos encarecidamente que establezca una fecha de caducidad en las propiedades de la página de aterrizaje. Una vez finalizada, la página de aterrizaje se cancelará automáticamente la publicación en la fecha seleccionada. For more on validity parameters, refer to [this section](../../channels/using/sharing-a-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

   >[!NOTE]
   >
   >Las modificaciones solo son efectivas para la página de aterrizaje que se está editando. Si desea aplicar estas modificaciones a otras páginas de aterrizaje, puede llevarlas a cabo en una plantilla dedicada y luego crear otras páginas de aterrizaje a partir de esa plantilla.

## Diseñar la página de aterrizaje {#design-the-landing-page}

Ahora puede definir el contenido de la página de aterrizaje. De forma predeterminada, la página de aterrizaje contiene tres páginas a las que se puede acceder mediante flechas de desplazamiento: la página de contenido principal, una página de confirmación y una página de error.

![](assets/lp-steps4.png)

Hay varios campos configurados de forma predeterminada en cada página. Si es necesario, puede editar sus propiedades y la asignación.

También puede configurar la forma en que el botón de confirmación se comportará cuando un perfil haga clic en él y personalizar el contenido según sus necesidades (imagen, campos de personalización, etc.). Por ejemplo, puede insertar el nombre de un perfil en la página de confirmación de la página de aterrizaje para darles las gracias por registrarse.

Para obtener más información sobre el diseño de la página de aterrizaje, consulte [esta sección](../../channels/using/designing-a-landing-page.md).

## Probar la página de aterrizaje {#test-the-landing-page}

Una vez definida la página de aterrizaje, puede simular la forma en que se ejecutará y comportará cuando esté disponible en línea.

![](assets/lp-steps5.png)

>[!CAUTION]
>
>Las pruebas de la página de aterrizaje sólo pueden realizarse con perfiles, y no con perfiles de prueba. Cuando se envía el formulario, los datos del perfil seleccionado se actualizarán para que sean reales. Para evitar modificar perfiles reales, utilice un perfil de cliente falso.

Si está satisfecho con el comportamiento de la página de aterrizaje, puede publicarla para que esté disponible en línea.

Para obtener más información sobre cómo probar una página de aterrizaje, consulte [esta sección](../../channels/using/sharing-a-landing-page.md#testing-the-landing-page-).

## Publicar la página de aterrizaje {#publish-the-landing-page}

Una vez que las pruebas se hayan realizado correctamente, puede publicar la página de aterrizaje con el **[!UICONTROL Publish]** botón de la barra de acciones del tablero. Un bloque de monitoreo muestra la progresión y el estado de la publicación.

La publicación de la página de aterrizaje la hace accesible en línea. Una vez publicada, siempre puede actualizarla: para ello, debe volver a publicarla después de cada modificación. También puede cancelar la publicación de una página de aterrizaje en cualquier momento para que ya no esté disponible.

![](assets/lp-steps6.png)

Una vez publicada, la página de aterrizaje está lista para utilizarse. A continuación, puede establecer diferentes mecanismos que le permitan acceder a ellos para adquirir nuevos perfiles en la base de datos o para obtener información adicional sobre los perfiles existentes.

Para obtener más información sobre la publicación de la página de aterrizaje, consulte [esta sección](../../channels/using/sharing-a-landing-page.md#publishing-a-landing-page).
