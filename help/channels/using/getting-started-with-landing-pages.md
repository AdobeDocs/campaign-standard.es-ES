---
title: Pasos principales para configurar una página de aterrizaje
description: Conozca los pasos principales para configurar una página de aterrizaje.
audience: channels
content-type: reference
topic-tags: landing-pages
context-tags: landingPage,wizard;landingPage,overview;landingPage,main
feature: Landing Pages
role: User
exl-id: 8015c555-9521-478c-8669-66b9cc145887
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '1025'
ht-degree: 97%

---

# Introducción a las páginas de aterrizaje {#getting-started-with-landing-pages}

Los pasos principales para configurar páginas de aterrizaje son los siguientes:

![](assets/lp_steps.png)

En esta página encontrará información sobre cada uno de estos pasos, así como referencias a la documentación relevante para obtener más detalles.

![](assets/do-not-localize/how-to-video.png) [Descubra cómo crear páginas de aterrizaje en vídeo](#video)

**Temas relacionados:**

* [Creación de un servicio](../../audiences/using/creating-a-service.md)
* [Configuración de un proceso de inclusión doble](setting-up-a-double-opt-in-process.md)

## Limitaciones de las páginas de aterrizaje{#landing-page-limitations}

La sección siguiente enumera las limitaciones que debe tener en cuenta antes de comenzar a configurar páginas de aterrizaje.

**Escritura y actualización de datos**

* Las páginas de aterrizaje se limitan a **[!UICONTROL Profile]** y solo a recursos de **[!UICONTROL Subscription]**. El registro se puede guardar y actualizar en **[!UICONTROL Profile]**, así como una suscripción/baja en un **[!UICONTROL Service]**.
Para obtener más información sobre la configuración de recursos, consulte [Configuración de la estructura de datos del recurso](../../developing/using/configuring-the-resource-s-data-structure.md).

>[!IMPORTANT]
>
>Una página de aterrizaje no puede mostrar ni actualizar datos de ningún otro recurso que no sea **[!UICONTROL Profile]** y **[!UICONTROL Subscription]**.

**Precarga**

* La página de aterrizaje no puede mostrar una lista de registros automáticamente y no puede enumerar a los servicios a los que perfiles ya se han suscrito. Para obtener más información sobre los servicios, consulte esta [página](../../audiences/using/creating-a-service.md).

* Solo se puede acceder a la página de aterrizaje con un formulario previamente completado (con datos cargados previamente con la página) desde un correo electrónico de Adobe Campaign. No es posible acceder a este formulario desde una página web.

**Reconciliación**

* El comportamiento de reconciliación es el siguiente: tan pronto como se encuentra una coincidencia, el proceso de reconciliación se detiene. Esto significa que la reconciliación solo se puede realizar en un registro de perfil y no en varios registros cuando hay duplicados.

Por ejemplo, desea enviar la siguiente página de aterrizaje de adquisición a sus perfiles para actualizar la base de datos de Campaign con los números móviles de sus perfiles.

![](assets/landing_page_limitation_1.png)

Si uno de los perfiles rellena la página de aterrizaje con información nueva, pero ya tiene un perfil duplicado, el perfil coincidente con la fecha de creación más temprana se actualizará, ya que los perfiles se priorizan según la fecha de creación.

Aquí solo se actualizó el primer perfil porque era la entrada más antigua.

![](assets/landing_page_limitation_2.png)

**Prueba de páginas de aterrizaje**

* Las páginas de aterrizaje solo funcionan en perfiles y no en perfiles de prueba, lo que significa que las páginas de aterrizaje no se pueden probar como parte de una prueba de correo electrónico.

## Paso 1: Configuración de la plantilla de página de aterrizaje {#configure-the-landing-page-template}

Antes de configurar una página de aterrizaje, el primer paso es configurar una plantilla de página de aterrizaje que se ajuste a sus necesidades. Una vez preparada la plantilla, todas las páginas de aterrizaje basadas en ella se preconfigurarán con los parámetros deseados.

1. En el menú avanzado, en el logotipo de Adobe Campaign, seleccione **[!UICONTROL Resources]** / **[!UICONTROL Templates]** / **[!UICONTROL Landing page templates]** y, a continuación, duplique la plantilla que desee utilizar.
1. En las propiedades de la plantilla, especifique todos los parámetros que sus páginas de aterrizaje deben tener en común. Por ejemplo: la dimensión de segmentación, los parámetros de acceso a la página para visitantes identificados o no identificados, las acciones específicas para la validación del formulario por parte de un visitante, la marca o el logotipo que se utilizará en el contenido, etc. Para obtener más información sobre las propiedades de las páginas de aterrizaje, consulte [esta sección](../../channels/using/configuring-landing-page.md).
1. Guarde las modificaciones.

Para obtener más información sobre plantillas de páginas de aterrizaje, consulte [esta sección](../../channels/using/getting-started-with-landing-pages.md).

![](assets/lp-steps1.png)

## Paso 2: Creación y configuración de la página de aterrizaje {#create-and-configure-the-landing-page}

A partir de la plantilla definida en el paso anterior, cree una nueva página de aterrizaje en un programa o una campaña.

1. Cree la página de aterrizaje en función de la plantilla deseada.
1. Introduzca los parámetros generales de la página de aterrizaje (etiqueta, descripción, etc.).
1. A continuación, accederá al panel de página de aterrizaje. Si es necesario, edite las propiedades de la página de aterrizaje (consulte [Configuración de una página de aterrizaje](../../channels/using/configuring-landing-page.md)). De forma predeterminada, las propiedades son las configuradas en la plantilla de página de aterrizaje.
Por motivos de seguridad y el rendimiento de la plataforma, le recomendamos encarecidamente que defina una fecha de vencimiento en las propiedades de la página de aterrizaje. Una vez hecho, la publicación de la página de aterrizaje se cancelará automáticamente en la fecha seleccionada. Para obtener más información sobre los parámetros de validez, consulte [esta sección](../../channels/using/testing-publishing-landing-page.md#setting-up-validity-parameters).

   ![](assets/lp-steps3.png)

>[!NOTE]
>
>Las modificaciones solo son efectivas para la página de aterrizaje que se está editando. Si desea aplicar estas modificaciones a otras páginas de aterrizaje, puede llevarlas a cabo en una plantilla específica y, a continuación, crear otras páginas de aterrizaje a partir de esa plantilla.

## Paso 3: Diseño de la página de aterrizaje {#design-the-landing-page}

Ahora puede definir el contenido de la página de aterrizaje. De forma predeterminada, la página de aterrizaje contiene tres páginas a las que se puede acceder mediante flechas de desplazamiento: la página de contenido principal, una página de confirmación y una página de error.

![](assets/lp-steps4.png)

Hay varios campos configurados de forma predeterminada en cada página. Si es necesario, puede editar las propiedades y la asignación.

También puede configurar la forma en que el botón de confirmación se comporta una vez que un perfil hace clic en él y personalizar el contenido según sus necesidades (imagen, campos de personalización, etc.). Por ejemplo, puede insertar el nombre de un perfil en la página de confirmación de la página de aterrizaje, para agradecerles su registro.

Para obtener más información sobre el diseño de la página de aterrizaje, consulte [esta sección](../../channels/using/designing-a-landing-page.md).

## Paso 4: Prueba de la página de aterrizaje {#test-the-landing-page}

Una vez definida la página de aterrizaje, puede simular la forma en que se ejecutará y comportará cuando esté disponible en línea.

![](assets/lp-steps5.png)

>[!IMPORTANT]
>
>Las pruebas de la página de aterrizaje solo pueden realizarse con perfiles, pero no con perfiles de prueba. Cuando se envía el formulario, los datos del perfil seleccionado se actualizarán para que sean reales. Para evitar la modificación de perfiles reales, utilice un perfil de cliente falso.

Si está satisfecho con el comportamiento de la página de aterrizaje, puede publicarla para que esté disponible en línea.

Para obtener más información sobre cómo probar una página de aterrizaje, consulte [esta sección](../../channels/using/testing-publishing-landing-page.md#testing-the-landing-page-).

## Paso 5: Publicación de la página de aterrizaje {#publish-the-landing-page}

Una vez realizadas las pruebas correctamente, puede publicar la página de aterrizaje con el botón **[!UICONTROL Publish]** de la barra de acciones del panel. Un bloque de monitorización muestra la progresión y el estado de la publicación.

La publicación de la página de aterrizaje la hace accesible en línea. Una vez publicada, siempre puede actualizarla: para ello, debe volver a publicarla después de cada modificación. También puede cancelar la publicación de una página de aterrizaje en cualquier momento para que ya no esté disponible.

![](assets/lp-steps6.png)

Una vez publicada, la página de aterrizaje estará lista para utilizarse. A continuación, puede establecer diferentes mecanismos que le permitan acceder a ellos para adquirir nuevos perfiles en la base de datos o para obtener información adicional sobre perfiles existentes.

Para obtener más información sobre la publicación de la página de aterrizaje, consulte [esta sección](../../channels/using/testing-publishing-landing-page.md#publishing-a-landing-page).

## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear y editar una página de aterrizaje.

>[!VIDEO](https://video.tv.adobe.com/v/24093?quality=12)

Hay disponibles más vídeos de procedimientos para el Campaign Standard [aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
