---
title: Creación de una dimensión de perfil personalizada
seo-title: Creación de una dimensión de perfil personalizada
description: Creación de una dimensión de perfil personalizada
seo-description: Aprenda a crear una dimensión de perfil personalizada basada en datos de perfil personalizados.
page-status-flag: no activado nunca
uuid: f 75 e 005 b -5328-4 c 98-9 e 78-51 d 54 fd 0 e 246
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: informes
content-type: reference
topic-tags: personalizar informes
discoiquuid: b 6 d 3 de 63-3 add -4881-8917-04 a 6 f 8 b 6 be 4 d
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e9a4d99ddf311898c48b2b352fa13f5b59ed1fbe

---


# Creating a custom profile dimension{#creating-a-custom-profile-dimension}

Los informes también se pueden crear y administrar en función de los datos de perfil personalizados creados durante la extensión de recurso personalizado de perfil.

In this example, we want to create the custom profile field **Loyalty programs** which will be divided into three levels: gold, silver and bronze. Este perfil personalizado se ampliará para poder utilizarlo como una dimensión de perfil personalizada en informes dinámicos.

* [Paso 1: Crear un nuevo campo de perfil](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [Paso 2: Extender los registros de envío con el campo de perfil](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [Paso 3: Creación de destinatarios de segmentación de envío inscritos en el programa de lealtad](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Paso 4: Crear un informe dinámico para filtrar destinatarios con la dimensión de perfil personalizada](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Step 1: Create a new profile field {#step-1--create-a-new-profile-field}

We first need to create the new profile field **Loyalty program** that will assign loyalty level to our recipients: gold, silver or bronze.

>[!NOTE]
>
>Los recursos personalizados sólo pueden ser administrados por un administrador.

Para ello:

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.

   ![](assets/custom_profile_1.png)

1. From the **[!UICONTROL Data structure]** tab, in the **[!UICONTROL Fields]** category, click the **[!UICONTROL Add field]** button.

   ![](assets/custom_profile_2.png)

1. Enter the **[!UICONTROL Label]**, **[!UICONTROL ID]** and select the custom resource **[!UICONTROL Type]**. Here, we selected **[!UICONTROL Text]** since recipients will have the choice between gold, silver and bronze.

   ![](assets/custom_profile_3.png)

1. Click the ![](assets/custom_profile_22.png) icon to define your field.

   ![](assets/custom_profile_12.png)

1. Here, we need to specify the authorized values by checking **[!UICONTROL Specify a list of authorized valued]** and create each value by clicking **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Enter the **[!UICONTROL Label]** and **[!UICONTROL Value]** then click **[!UICONTROL Add]**. Para este ejemplo, necesitamos crear el valor gold, silver y bronce. Click **[!UICONTROL Confirm]** when done.

   ![](assets/custom_profile_14.png)

1. Select the **[!UICONTROL Screen definition]** tab. In the **[!UICONTROL Detail screen configuration]** drop-down, check **[!UICONTROL Add personalized fields]** section to create a new section in our profile.

   ![](assets/custom_profile_4.png)

1. Click the **[!UICONTROL Add an element]** button to create your new section. Select the **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** or **[!UICONTROL List]**, then the field to add in this new section.

   ![](assets/custom_profile_5.png)

1. You can also add a title to your section in the field **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Click **[!UICONTROL Save]** when the configuration is done.

   ![](assets/custom_profile_6.png)

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.
1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

El nuevo campo de perfil está listo para ser utilizado y seleccionado por sus destinatarios.

![](assets/custom_profile_8.png)

## Step 2: Extend the sending logs with the profile field {#step-2--extend-the-sending-logs-with-the-profile-field}

Ahora que se crea el campo de perfil, es necesario ampliar los registros de los registros con nuestro campo de perfil para crear la dimensión de perfil personalizada asociada en los informes dinámicos.

Before extending the log with our profile field, make sure that the PII window was accepted to have access to the **[!UICONTROL Sending logs extension]** tab. For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>Los registros solo pueden ampliarse con los campos de perfil por administrador.

1. From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** then the **[!UICONTROL Profile (profile)]** custom resource.
1. Open the **[!UICONTROL Sending logs extension]** drop-down.
1. Click the **[!UICONTROL Create element]** button.

   ![](assets/custom_profile_9.png)

1. Select your previously created field and click **[!UICONTROL Confirm]**.
1. Check **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** to create your custom profile dimension.

   ![](assets/custom_profile_10.png)

   Esta opción solo está disponible si se ha aceptado la ventana PII. For more on this, refer to this [page](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Click **[!UICONTROL Add]** then save your custom resource.
1. Como se modificó el recurso personalizado, es necesario publicarlo para implementar los nuevos cambios.

   From the advanced menu, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** to start publishing your custom resource.

1. Click **[!UICONTROL Prepare publication]** then when the preparation is done, click the **[!UICONTROL Publish]** button.

   ![](assets/custom_profile_7.png)

El perfil personalizado ya está disponible como dimensión de perfil personalizada en los informes.

Ahora que el campo se ha creado y que se han ampliado los registros de envío con este campo de perfil, puede iniciar los destinatarios de destino en los envíos.

## Step 3: Create a delivery targeting recipients enrolled in the loyalty program {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Una vez publicada su campo de perfil, puede iniciar la entrega. En este ejemplo, queremos enfocar a todos los destinatarios inscritos en el programa de lealtad.

1. From the **[!UICONTROL Marketing activities]** tab, click **[!UICONTROL Create]** then select **[!UICONTROL Email]**.
1. Choose an **[!UICONTROL Email type]** then enter your email's properties.
1. To target recipient enrolled in the loyalty program, drag and drop the **[!UICONTROL Profiles (attributes)]** activity.
1. Select your previously created field from the **[!UICONTROL Field]** drop-down.

   ![](assets/custom_profile_16.png)

1. Select your **[!UICONTROL Filter conditions]**. Aquí, queremos dirigir a los destinatarios que forman parte de uno de los tres niveles del programa de lealtad.

   ![](assets/custom_profile_17.png)

1. Click **[!UICONTROL Confirm]** then when done filtering, click **[!UICONTROL Next]**.
1. Defina y personalice el contenido del mensaje, el nombre del remitente y el asunto. For more information on email creation refer to this [page](../../designing/using/about-email-content-design.md#about-the-email-designer).

   Then, click **[!UICONTROL Create]**.

1. Cuando esté listo, puede obtener una vista previa y enviar el mensaje. For more information on how to prepare and send your message, refer to this [page](../../sending/using/preparing-the-send.md).

Una vez que el correo electrónico se envía correctamente a los destinatarios seleccionados, puede comenzar a filtrar los datos y realizar un seguimiento del éxito de la entrega con los informes.

## Step 4: Create a dynamic report to filter recipients with the custom profile dimension {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

After sending your delivery, you can breakdown reports using your custom profile dimension from the **[!UICONTROL Profile]** table.

1. From the **[!UICONTROL Reports]** tab, select an out-of-the-box report or click the **[!UICONTROL Create]** button to start one from scratch.

   ![](assets/custom_profile_18.png)

1. In the **[!UICONTROL Dimensions]** category, click **[!UICONTROL Profile]** then drag and drop your custom **Loyalty program** profile dimension to your freeform table.

   ![](assets/custom_profile_19.png)

1. Drag and drop the **[!UICONTROL Processed/Sent]** and **[!UICONTROL Open]** metrics to start filtering your data.

   ![](assets/custom_profile_20.png)

1. Arrastre y suelte una visualización en su espacio de trabajo, si es necesario.

   ![](assets/custom_profile_21.png)

