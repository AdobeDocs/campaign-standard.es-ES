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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Creación de una dimensión de perfil personalizada{#creating-a-custom-profile-dimension}

Los informes también se pueden crear y administrar en función de los datos de perfil personalizados creados durante la extensión de recurso personalizado de perfil.

En este ejemplo, queremos crear los programas de lealtad del campo **de perfil personalizados** que se dividirán en tres niveles: oro, plata y bronce. Este perfil personalizado se ampliará para poder utilizarlo como una dimensión de perfil personalizada en informes dinámicos.

* [Paso 1: Crear un nuevo campo de perfil](../../reporting/using/creating-a-custom-profile-dimension.md#step-1--create-a-new-profile-field)
* [Paso 2: Extender los registros de envío con el campo de perfil](../../reporting/using/creating-a-custom-profile-dimension.md#step-2--extend-the-sending-logs-with-the-profile-field)
* [Paso 3: Creación de destinatarios de segmentación de envío inscritos en el programa de lealtad](../../reporting/using/creating-a-custom-profile-dimension.md#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Paso 4: Crear un informe dinámico para filtrar destinatarios con la dimensión de perfil personalizada](../../reporting/using/creating-a-custom-profile-dimension.md#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Paso 1: Crear un nuevo campo de perfil {#step-1--create-a-new-profile-field}

Primero necesitamos crear el nuevo programa **de lealtad del campo de perfil** que asignará nivel de lealtad a nuestros destinatarios: oro, plata o bronce.

>[!NOTE]
>
>Los recursos personalizados sólo pueden ser administrados por un administrador.

Para ello:

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** y luego el medio **[!UICONTROL Profile (profile)]** personalizado.

   ![](assets/custom_profile_1.png)

1. En **[!UICONTROL Data structure]** la ficha, en **[!UICONTROL Fields]** la categoría, haga clic en el **[!UICONTROL Add field]** botón.

   ![](assets/custom_profile_2.png)

1. Introduzca el **[!UICONTROL Label]** y **[!UICONTROL ID]** seleccione el recurso **[!UICONTROL Type]** personalizado. Aquí seleccionamos **[!UICONTROL Text]** , ya que los destinatarios tendrán la opción entre oro, plata y bronce.

   ![](assets/custom_profile_3.png)

1. Haga clic ![](assets/custom_profile_22.png) en el icono para definir el campo.

   ![](assets/custom_profile_12.png)

1. Aquí, necesitamos especificar los valores autorizados comprobando **[!UICONTROL Specify a list of authorized valued]** y creando cada valor haciendo clic **[!UICONTROL Create element]** en.

   ![](assets/custom_profile_13.png)

1. Introduzca el **[!UICONTROL Label]** y **[!UICONTROL Value]** haga clic **[!UICONTROL Add]** en. Para este ejemplo, necesitamos crear el valor gold, silver y bronce. Haga clic **[!UICONTROL Confirm]** en cuando termine.

   ![](assets/custom_profile_14.png)

1. Seleccione **[!UICONTROL Screen definition]** la ficha. En la **[!UICONTROL Detail screen configuration]** lista desplegable, consulte **[!UICONTROL Add personalized fields]** la sección para crear una nueva sección en nuestro perfil.

   ![](assets/custom_profile_4.png)

1. Haga clic en **[!UICONTROL Add an element]** el botón para crear la nueva sección. Seleccione lo **[!UICONTROL Type]** siguiente: **[!UICONTROL Input field]** o **[!UICONTROL Value]** , a continuación, **[!UICONTROL List]** el campo que agregar en esta nueva sección.

   ![](assets/custom_profile_5.png)

1. También puede agregar un título a la sección en el campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Haga clic **[!UICONTROL Save]** en cuando se realice la configuración.

   ![](assets/custom_profile_6.png)

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** para comenzar a publicar el recurso personalizado.
1. Haga clic **[!UICONTROL Prepare publication]** en y después cuando finalice la preparación, haga clic **[!UICONTROL Publish]** en el botón.

   ![](assets/custom_profile_7.png)

El nuevo campo de perfil está listo para ser utilizado y seleccionado por sus destinatarios.

![](assets/custom_profile_8.png)

## Paso 2: Extender los registros de envío con el campo de perfil {#step-2--extend-the-sending-logs-with-the-profile-field}

Ahora que se crea el campo de perfil, es necesario ampliar los registros de los registros con nuestro campo de perfil para crear la dimensión de perfil personalizada asociada en los informes dinámicos.

Antes de ampliar el registro con nuestro campo de perfil, asegúrese de que la ventana PII se ha aceptado para tener acceso a **[!UICONTROL Sending logs extension]** la ficha. Para obtener más información, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>Los registros solo pueden ampliarse con los campos de perfil por administrador.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom resources]** y luego el medio **[!UICONTROL Profile (profile)]** personalizado.
1. Abra la **[!UICONTROL Sending logs extension]** lista desplegable.
1. Haga clic en **[!UICONTROL Create element]** el botón.

   ![](assets/custom_profile_9.png)

1. Seleccione el campo creado anteriormente y haga clic **[!UICONTROL Confirm]** en.
1. Compruebe **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** si desea crear su dimensión de perfil personalizada.

   ![](assets/custom_profile_10.png)

   Esta opción solo está disponible si se ha aceptado la ventana PII. Para obtener más información, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Haga clic **[!UICONTROL Add]** en y guarde el recurso personalizado.
1. Como se modificó el recurso personalizado, es necesario publicarlo para implementar los nuevos cambios.

   En el menú avanzado, seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Publication]** para comenzar a publicar el recurso personalizado.

1. Haga clic **[!UICONTROL Prepare publication]** en y después cuando finalice la preparación, haga clic **[!UICONTROL Publish]** en el botón.

   ![](assets/custom_profile_7.png)

El perfil personalizado ya está disponible como dimensión de perfil personalizada en los informes.

Ahora que el campo se ha creado y que se han ampliado los registros de envío con este campo de perfil, puede iniciar los destinatarios de destino en los envíos.

## Paso 3: Creación de destinatarios de segmentación de envío inscritos en el programa de lealtad {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Una vez publicada su campo de perfil, puede iniciar la entrega. En este ejemplo, queremos enfocar a todos los destinatarios inscritos en el programa de lealtad.

1. En la **[!UICONTROL Marketing activities]** ficha, haga clic **[!UICONTROL Create]** en y seleccione **[!UICONTROL Email]**.
1. Elija una **[!UICONTROL Email type]** y luego introduzca las propiedades de su correo electrónico.
1. Para dirigir a los destinatarios inscritos en el programa de fidelidad, arrastre y suelte la **[!UICONTROL Profiles (attributes)]** actividad.
1. Seleccione el campo creado previamente en la **[!UICONTROL Field]** lista desplegable.

   ![](assets/custom_profile_16.png)

1. Seleccione su **[!UICONTROL Filter conditions]**. Aquí, queremos dirigir a los destinatarios que forman parte de uno de los tres niveles del programa de lealtad.

   ![](assets/custom_profile_17.png)

1. Haga clic **[!UICONTROL Confirm]** en y después cuando termine de filtrar, haga clic **[!UICONTROL Next]** en.
1. Defina y personalice el contenido del mensaje, el nombre del remitente y el asunto. Para obtener más información sobre la creación de correo electrónico, consulte esta [página](../../designing/using/about-email-content-design.md#about-the-email-designer).

   A continuación, haga clic **[!UICONTROL Create]** en.

1. Cuando esté listo, puede obtener una vista previa y enviar el mensaje. Para obtener más información sobre cómo preparar y enviar el mensaje, consulte esta [página](../../sending/using/preparing-the-send.md).

Una vez que el correo electrónico se envía correctamente a los destinatarios seleccionados, puede comenzar a filtrar los datos y realizar un seguimiento del éxito de la entrega con los informes.

## Paso 4: Crear un informe dinámico para filtrar destinatarios con la dimensión de perfil personalizada {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Después de enviar la entrega, puede desglosar informes utilizando su dimensión de perfil personalizada desde la **[!UICONTROL Profile]** tabla.

1. Desde **[!UICONTROL Reports]** la ficha, seleccione un informe predeterminado o haga clic en **[!UICONTROL Create]** el botón para comenzar uno desde cero.

   ![](assets/custom_profile_18.png)

1. En **[!UICONTROL Dimensions]** la categoría, haga clic **[!UICONTROL Profile]** y arrastre la dimensión de perfil del **programa** de lealtad personalizada a la tabla improvisada.

   ![](assets/custom_profile_19.png)

1. Arrastre y suelte las **[!UICONTROL Processed/Sent]****[!UICONTROL Open]** métricas para comenzar a filtrar los datos.

   ![](assets/custom_profile_20.png)

1. Arrastre y suelte una visualización en su espacio de trabajo, si es necesario.

   ![](assets/custom_profile_21.png)

**Tema relacionado:**

* [Uso de datos de perfil personalizados para crear informes perspicaces](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
