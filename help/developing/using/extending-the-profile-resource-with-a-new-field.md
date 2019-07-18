---
title: Ampliación del recurso de perfil con un nuevo campo
seo-title: Ampliación del recurso de perfil con un nuevo campo
description: Ampliación del recurso de perfil con un nuevo campo
seo-description: Descubra cómo ampliar el recurso de perfil.
page-status-flag: no activado nunca
uuid: 9 b 99 e 95 c -93 ff -4187-90 f 7-db 0 baf 5369 ad
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: casos de uso—ampliación de recursos
discoiquuid: 1 e 0 f 8945-fc 3 c -46 a 9-a 8 e 5-b 181 a 1 f 5 ffcb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Extending the profile resource with a new field{#extending-the-profile-resource-with-a-new-field}

## About extending profiles {#about-extending-profiles}

Este caso de uso detalla cómo ampliar un perfil y un perfil de prueba con un campo dedicado.

Aquí, queremos actualizar nuestros perfiles con el nuevo campo utilizando una página de aterrizaje y luego dirigir perfiles con una newsletter específica de sus intereses.

Para ello, siga los pasos a continuación:

* [Paso 1: Ampliar el recurso de perfil](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-1--extend-the-profile-resource)
* [Paso 2: Ampliar el perfil de prueba](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-2--extend-the-test-profile)
* [Paso 3: Publicar el recurso personalizado](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-3--publish-your-custom-resource)
* [Paso 4: Actualizar y segmentar perfiles con un flujo de trabajo](../../developing/using/extending-the-profile-resource-with-a-new-field.md#step-4--update-and-target-profiles-with-a-workflow)

El campo siguiente se agregará a nuestros perfiles y se puede establecer como objetivo en una entrega:

![](assets/schema_extension_uc20.png)

Temas relacionados:

* [Acerca de los recursos personalizados](../../developing/using/data-model-concepts.md)
* [Administración de perfiles](../../audiences/using/about-profiles.md)
* [Administración de perfiles de prueba](../../sending/using/managing-test-profiles-and-sending-proofs.md#managing-test-profiles)

## Step 1: Extend the profile resource {#step-1--extend-the-profile-resource}

To create the new **Interest** field for our profiles, you first need to extend the out-of-the-box **[!UICONTROL Profiles (profile)]** resource.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. If you have not extended the **[!UICONTROL Profiles]** resource yet, click **[!UICONTROL Create]**.
1. Choose the **[!UICONTROL Extend an existing resource]** option.
1. Select the **[!UICONTROL Profile (profile)]** resource.
1. Click **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc5.png)

1. In the **[!UICONTROL Fields]** category of the **[!UICONTROL Data structure]** tab, click **[!UICONTROL Create element]**.

   >[!NOTE]
   >
   >Note that if you already extended the **[!UICONTROL Profile]** resource for previous purposes, you can start at this step by clicking **[!UICONTROL Add field]**.

   ![](assets/schema_extension_uc6.png)

1. Add a **[!UICONTROL Label]** and an **[!UICONTROL ID]**. Select the **[!UICONTROL Text]** type and click **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc9.png)

1. Para configurar el campo, en la pestaña **[!UICONTROL Data structure]** debajo de la lista desplegable **[!UICONTROL Fields]**, haga clic en ![](assets/schema_extension_uc8.png) y después en ![](assets/schema_extension_uc7.png) desde el campo creado anteriormente.
1. In this example we want to add specific values, to do so click **[!UICONTROL Specify a list of authorized values]**.

   ![](assets/schema_extension_uc10.png)

1. Click **[!UICONTROL Add an element]** then add as many value as needed by adding a **[!UICONTROL Label]** and an **[!UICONTROL ID]** and clicking **[!UICONTROL Add]**.

   Aquí, crearemos los valores de Libros, Muestras, Películas y N/D para perfiles para elegir entre estas opciones.

   ![](assets/schema_extension_uc11.png)

1. To add this field in the **[!UICONTROL Profile]** screen, click the **[!UICONTROL Screen definition]** tab.
1. In the **[!UICONTROL Detail screen configuration]** drop-down, click **[!UICONTROL Add a personalized fields section]** and click **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc12.png)

1. Select a **[!UICONTROL Type]**. Aquí se desea agregar un campo de entrada. Then, select your previously created field and click **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc2.png)

1. To add a separator to better organize your profile window, click **[!UICONTROL Create an element]** and select **[!UICONTROL Separator]** from the **[!UICONTROL Type]** drop-down.

   ![](assets/schema_extension_uc19.png)

El campo ahora está configurado. Ahora es necesario ampliarlo al perfil de prueba.

>[!NOTE]
>
>Si no necesita ampliar el recurso de perfil de prueba, puede ir al paso Publicación.

## Step 2: Extend the test profile {#step-2--extend-the-test-profile}

Para comprobar si el nuevo campo creado está correctamente configurado, puede probarlo enviando su entrega a los perfiles de la prueba. Primero, el nuevo campo también debe llevarse a cabo a los perfiles de prueba.

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Custom resources]**.
1. If you have not extended the **[!UICONTROL Profiles]** resource yet, click **[!UICONTROL Create]**.
1. Choose the **[!UICONTROL Extend an existing resource]** option.
1. Select the **[!UICONTROL Test profile (seedMember)]** resource.
1. Click **[!UICONTROL Create]**.

   ![](assets/schema_extension_uc13.png)

1. In the **[!UICONTROL Data structure]** tab, click **[!UICONTROL Create element]**.

   ![](assets/schema_extension_uc15.png)

1. Select your previously created resource field and click **[!UICONTROL Add]**.

   ![](assets/schema_extension_uc16.png)

1. Carry out the same steps from step 11 to 13 as the extend profile walkthrough above to add this field in the **[!UICONTROL Test profile]** screen.
1. Click **[!UICONTROL Save]**.

Tanto los perfiles como los perfiles de prueba tendrán ahora su nuevo campo disponible. Para que se configure correctamente, debe publicar el recurso personalizado.

## Step 3: Publish your custom resource {#step-3--publish-your-custom-resource}

Para aplicar los cambios realizados en los recursos y poder utilizarlos, debe realizar una actualización de base de datos.

1. From the advanced menu, select **Administration** &gt; **Development**, then **Publishing**.
1. By default, the option **[!UICONTROL Determine modifications since the last publication]** is checked, which means that only the changes carried out since the last update will be applied.

   ![](assets/schema_extension_uc14.png)

1. Click **[!UICONTROL Prepare publication]** to start the analysis which will update your database.
1. Once the publication has been carried out, click the **Publish** button to apply your new configurations.

   ![](assets/schema_extension_uc17.png)

1. Once published, the **Summary** pane of each resource indicates that the status is now **Published** and specifies the date of the last publication.

   ![](assets/schema_extension_uc18.png)

1. Select the **[!UICONTROL Profiles]** tab and click **[!UICONTROL New]** to see if your changes have been correctly implemented.

   ![](assets/schema_extension_uc20.png)

El nuevo campo de recursos ya está listo para utilizarse y como objetivo en una entrega.

## Step 4: Update and target profiles with a workflow {#step-4--update-and-target-profiles-with-a-workflow}

To update profiles with data for the new custom field, you can create a landing page using the **[!UICONTROL Profile acquisition]** template. For more information on landing pages, refer to this [page](../../channels/using/about-landing-pages.md).

Aquí, queremos segmentar en un perfil de workflow que no rellenó este campo. Recibirán un mensaje de correo electrónico pidiéndoles que actualicen sus perfiles para recibir boletines informativos personalizados y ofertas. Cada perfil recibirá una newsletter personalizada según los intereses que haya elegido.

First, we need to create a landing page that will update the **Interest** fields of the targeted profiles:

1. From the **[!UICONTROL Marketing activities]**, click **[!UICONTROL Create]** then select **[!UICONTROL Landing page]**.
1. Seleccione un tipo de página de aterrizaje. Here, since we want to update our profiles, select **[!UICONTROL Profile acquisition]**.
1. Click **[!UICONTROL Create]**.
1. Click the **[!UICONTROL Content]** block to start editing the content of your landing page.

   ![](assets/schema_extension_uc21.png)

1. Personalice la página de aterrizaje según sea necesario.
1. Haga clic en el campo configurado para que los perfiles elijan entre la selección de Intereses. In the left pane, select your previously created **Interest** custom resource.

   ![](assets/schema_extension_uc22.png)

1. Guarde la página de aterrizaje y pruébela para comprobar que los campos estén correctamente configurados.
1. Click **[!UICONTROL Publish]** when your landing page is ready.

La página de aterrizaje está lista. Para actualizar los perfiles, puede crear un flujo de trabajo que envíe una oferta especial según el interés elegido.

1. From the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Workflow]**.
1. Drag and drop a **[!UICONTROL Query]** activity to target the profiles or audiences you need.
1. Drag and drop an **[!UICONTROL Email delivery]** activity to start configuring your email which will contain a link to the landing page. Select the **[!UICONTROL Add an outbound transition with the population]**.

   ![](assets/schema_extension_uc3.png)

1. Cree y diseñe su correo electrónico según sea necesario. For more information on email personalization, refer to this [page](../../designing/using/designing-content-in-adobe-campaign.md).
1. Agregue un botón a su correo electrónico que redirija los perfiles a su página de aterrizaje.
1. Select the added button and click ![](assets/schema_extension_uc7.png) in the **[!UICONTROL Link]** section in the left pane.

   ![](assets/schema_extension_uc23.png)

1. In the **[!UICONTROL Insert link]** window, select **[!UICONTROL Landing page]** from the **[!UICONTROL Link type]** drop-down then select the previously created landing page.

   ![](assets/schema_extension_uc24.png)

1. Click **[!UICONTROL Save]**. El correo electrónico ya está listo, puede regresar al flujo de trabajo.
1. Add a **[!UICONTROL Wait]** activity to let some time for your profiles to fill the landing page.
1. Add a **[!UICONTROL Segmentation]** activity to split the outbound transition depending on their **Interests**.
1. Create an outbound segment for each **Interest**.

   ![](assets/schema_extension_uc4.png)

1. Add an **[!UICONTROL Email delivery]** activity after each transition and create a personalized email depending on the chosen **Interest**.
1. Inicie el flujo de trabajo cuando se realice la configuración.

   ![](assets/schema_extension_uc25.png)

Ahora los perfiles recibirán el mensaje de correo electrónico pidiéndole que rellene este campo de interés seguido de un correo electrónico personalizado según el valor elegido.
