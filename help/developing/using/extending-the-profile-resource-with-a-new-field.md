---
title: Ampliación del recurso de perfil con un nuevo campo
description: Obtenga información sobre cómo ampliar el recurso de perfil.
page-status-flag: never-activated
uuid: 9b99e95c-93ff-4187-90f7-db0baf5369ad
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: use-cases--extending-resources
discoiquuid: 1e0f8945-fc3c-46a9-a8e5-b181a1f5ffcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 95e01eb33097fc76caac3f4dd5f5591461b887cf

---


# Ampliación del recurso de perfil con un nuevo campo{#extending-the-profile-resource-with-a-new-field}

## Acerca de la ampliación de perfiles {#about-extending-profiles}

Este caso de uso explica cómo ampliar un perfil y un perfil de prueba con un campo dedicado.

Aquí, queremos actualizar nuestros perfiles con el nuevo campo usando una página de aterrizaje y luego segmentar perfiles con una newsletter específica para sus intereses.

Para ello, siga los pasos a continuación:

* [Paso 1: Ampliar el recurso de perfil](#step-1--extend-the-profile-resource)
* [Paso 2: Ampliar el perfil de prueba](#step-2--extend-the-test-profile)
* [Paso 3: Publicar el recurso personalizado](#step-3--publish-your-custom-resource)
* [Paso 4: Actualización y destino de perfiles con un flujo de trabajo](#step-4--update-and-target-profiles-with-a-workflow)

A continuación, se agregará el siguiente campo a nuestros perfiles y se puede definir como objetivo en una entrega:

![](assets/schema_extension_uc20.png)

Temas relacionados:

* [Acerca de los recursos personalizados](../../developing/using/data-model-concepts.md)
* [Administración de perfiles](../../audiences/using/about-profiles.md)
* [Administración de perfiles de prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)

## Paso 1: Ampliar el recurso de perfil {#step-1--extend-the-profile-resource}

Para crear el nuevo campo **Interés** para nuestros perfiles, primero debe ampliar el recurso listo para usar **[!UICONTROL Profiles (profile)]** .

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** y, a continuación, **[!UICONTROL Custom resources]**.
1. Si aún no ha ampliado el **[!UICONTROL Profiles]** recurso, haga clic en **[!UICONTROL Create]**.
1. Elija la **[!UICONTROL Extend an existing resource]** opción.
1. Seleccione el **[!UICONTROL Profile (profile)]** recurso.
1. Click **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc5.png)

1. En la **[!UICONTROL Fields]** categoría de la **[!UICONTROL Data structure]** ficha, haga clic en **[!UICONTROL Create element]**.

   >[!NOTE]
   >
   >Tenga en cuenta que si ya ha ampliado el **[!UICONTROL Profile]** recurso para fines anteriores, puede comenzar con este paso haciendo clic en **[!UICONTROL Add field]**.

   ![](assets/schema_extension_uc6.png)

1. Agregue un **[!UICONTROL Label]** y un **[!UICONTROL ID]**. Seleccione el **[!UICONTROL Text]** tipo y haga clic en **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc9.png)

1. Para configurar el campo, en la pestaña **[!UICONTROL Data structure]** debajo de la lista desplegable **[!UICONTROL Fields]**, haga clic en ![](assets/schema_extension_uc8.png) y después en ![](assets/schema_extension_uc7.png) desde el campo creado anteriormente.
1. En este ejemplo queremos agregar valores específicos, para hacerlo haga clic en **[!UICONTROL Specify a list of authorized values]**.

   ![](assets/schema_extension_uc10.png)

1. Haga clic en **[!UICONTROL Add an element]** y, a continuación, agregue todos los valores necesarios agregando un **[!UICONTROL Label]** y un **[!UICONTROL ID]** y haciendo clic en **[!UICONTROL Add]**.

   Aquí, crearemos los valores de Libros, Exposiciones, Películas y N/D para perfiles para elegir entre estas opciones.

   ![](assets/schema_extension_uc11.png)

1. Para agregar este campo en la **[!UICONTROL Profile]** pantalla, haga clic en la **[!UICONTROL Screen definition]** ficha.
1. En la **[!UICONTROL Detail screen configuration]** lista desplegable, haga clic en **[!UICONTROL Add a personalized fields section]** y en **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc12.png)

1. Seleccione un **[!UICONTROL Type]**. Aquí queremos agregar un campo de entrada. A continuación, seleccione el campo creado anteriormente y haga clic en **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc2.png)

1. Para agregar un separador para organizar mejor la ventana de perfil, haga clic en **[!UICONTROL Create an element]** y seleccione **[!UICONTROL Separator]** en la **[!UICONTROL Type]** lista desplegable.

   ![](assets/schema_extension_uc19.png)

El campo ya está configurado. Ahora tenemos que ampliarlo al perfil de prueba.

>[!NOTE]
>
>Si no necesita ampliar el recurso de perfil de prueba, puede ir al paso Publicación.

## Paso 2: Ampliar el perfil de prueba {#step-2--extend-the-test-profile}

Para comprobar si el nuevo campo creado está correctamente configurado, puede probarlo enviando la entrega a sus perfiles de prueba. En primer lugar, el nuevo campo también debe llevarse a cabo en los perfiles de ensayo.

1. En el menú avanzado, a través del logotipo de Adobe Campaign, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** y, a continuación, **[!UICONTROL Custom resources]**.
1. Si aún no ha ampliado el **[!UICONTROL Profiles]** recurso, haga clic en **[!UICONTROL Create]**.
1. Elija la **[!UICONTROL Extend an existing resource]** opción.
1. Seleccione el **[!UICONTROL Test profile (seedMember)]** recurso.
1. Click **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc13.png)

1. En la **[!UICONTROL Data structure]** ficha, haga clic en **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc15.png)

1. Seleccione el campo de recursos creado anteriormente y haga clic en **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc16.png)

1. Lleve a cabo los mismos pasos del paso 11 al 13 que el tutorial de perfil de extensión de arriba para agregar este campo a la **[!UICONTROL Test profile]** pantalla.
1. Click **[!UICONTROL Save]**.

Tanto los perfiles como los perfiles de prueba tendrán ahora su nuevo campo disponible. Para que esté correctamente configurado, debe publicar el recurso personalizado.

## Paso 3: Publicar el recurso personalizado {#step-3--publish-your-custom-resource}

Para aplicar los cambios realizados en los recursos y poder utilizarlos, debe realizar una actualización de la base de datos.

1. En el menú avanzado, seleccione **Administración** &gt; **Desarrollo** y, a continuación, **Publicación**.
1. De forma predeterminada, la opción **[!UICONTROL Determine modifications since the last publication]** está marcada, lo que significa que solo se aplicarán los cambios realizados desde la última actualización.

   ![](assets/schema_extension_uc14.png)

1. Haga clic en **[!UICONTROL Prepare publication]** para iniciar el análisis que actualizará la base de datos.
1. Una vez realizada la publicación, haga clic en el botón **Publicar** para aplicar las nuevas configuraciones.

   ![](assets/schema_extension_uc17.png)

1. Una vez publicado, el panel **Resumen** de cada recurso indica que el estado se ha **publicado** y especifica la fecha de la última publicación.

   ![](assets/schema_extension_uc18.png)

1. Seleccione la **[!UICONTROL Profiles]** ficha y haga clic en **[!UICONTROL New]** para ver si los cambios se han implementado correctamente.

   ![](assets/schema_extension_uc20.png)

El nuevo campo de recursos ya está listo para utilizarse y segmentarse, por ejemplo, en una entrega.

## Paso 4: Actualización y destino de perfiles con un flujo de trabajo {#step-4--update-and-target-profiles-with-a-workflow}

Para actualizar perfiles con datos para el nuevo campo personalizado, puede crear una página de aterrizaje con la **[!UICONTROL Profile acquisition]** plantilla. For more information on landing pages, refer to this [page](../../channels/using/getting-started-with-landing-pages.md).

Aquí, queremos establecer como objetivo los perfiles de flujo de trabajo que no hayan rellenado este campo. Recibirán un correo electrónico pidiéndoles que actualicen sus perfiles para recibir boletines informativos y ofertas personalizados. A continuación, cada perfil recibirá un boletín personalizado en función de los intereses elegidos.

Primero, debemos crear una página de aterrizaje que actualice los campos **Interés** de los perfiles de destino:

1. En el **[!UICONTROL Marketing activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Landing page]**.
1. Seleccione un tipo de página de aterrizaje. Aquí, ya que queremos actualizar nuestros perfiles, seleccione **[!UICONTROL Profile acquisition]**.
1. Click **[!UICONTROL Create]**.
1. Haga clic en el **[!UICONTROL Content]** bloque para empezar a editar el contenido de la página de aterrizaje.

   ![](assets/schema_extension_uc21.png)

1. Personalice la página de aterrizaje según sea necesario.
1. Haga clic en el campo configurado para los perfiles para elegir entre la selección de Intereses. En el panel izquierdo, seleccione el recurso personalizado **Interés** creado anteriormente.

   ![](assets/schema_extension_uc22.png)

1. Guarde la página de aterrizaje y pruébela para comprobar que los campos están correctamente configurados.
1. Haga clic **[!UICONTROL Publish]** cuando la página de aterrizaje esté lista.

La página de aterrizaje ya está lista. Para actualizar los perfiles, puede crear un flujo de trabajo que enviará una oferta especial en función del interés seleccionado.

1. En la **[!UICONTROL Marketing activities]** ficha, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Arrastre y suelte una **[!UICONTROL Query]** actividad para dirigirse a los perfiles o audiencias que necesite.
1. Arrastre y suelte una **[!UICONTROL Email delivery]** actividad para empezar a configurar el correo electrónico, que contendrá un vínculo a la página de aterrizaje. Seleccione el **[!UICONTROL Add an outbound transition with the population]**.

   ![](assets/schema_extension_uc3.png)

1. Cree y diseñe su correo electrónico según sea necesario. For more information on email personalization, refer to this [page](../../designing/using/quick-start.md).
1. Agregue un botón al correo electrónico que redireccione los perfiles a la página de aterrizaje.
1. Seleccione el botón agregado y haga clic ![](assets/schema_extension_uc7.png) en la **[!UICONTROL Link]** sección del panel izquierdo.

   ![](assets/schema_extension_uc23.png)

1. En la **[!UICONTROL Insert link]** ventana, seleccione **[!UICONTROL Landing page]** en la **[!UICONTROL Link type]** lista desplegable y luego seleccione la página de aterrizaje creada anteriormente.

   ![](assets/schema_extension_uc24.png)

1. Click **[!UICONTROL Save]**. El correo electrónico ya está listo, puede volver al flujo de trabajo.
1. Agregue una **[!UICONTROL Wait]** actividad para que los perfiles tengan tiempo de rellenar la página de aterrizaje.
1. Agregue una **[!UICONTROL Segmentation]** actividad para dividir la transición de salida según sus **intereses**.
1. Cree un segmento de salida para cada **interés**.

   ![](assets/schema_extension_uc4.png)

1. Agregue una **[!UICONTROL Email delivery]** actividad después de cada transición y cree un correo electrónico personalizado según el **interés** elegido.
1. Inicie el flujo de trabajo cuando haya finalizado la configuración.

   ![](assets/schema_extension_uc25.png)

Ahora, los perfiles recibirán un correo electrónico en el que se les pedirá que rellenen este campo de interés seguido de un correo electrónico personalizado en función del valor seleccionado.
