---
solution: Campaign Standard
product: campaign
title: Creación de una dimensión de perfil personalizada
description: Obtenga información sobre cómo crear una dimensión de perfil personalizada basada en datos de perfil personalizados.
audience: reporting
content-type: reference
topic-tags: customizing-reports
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 5%

---


# Creación de una dimensión de perfil personalizada{#creating-a-custom-profile-dimension}

Los informes también se pueden crear y administrar en función de los datos de perfil personalizados creados durante la extensión de recursos personalizados de perfil.

En este ejemplo, queremos crear el campo de perfil personalizado **programas de lealtad** que se dividirá en tres niveles: oro, plata y bronce. Este perfil personalizado se ampliará para poder utilizarlo como dimensión de perfil personalizada en los informes dinámicos.

* [Paso 1: Crear un nuevo campo de perfil](#step-1--create-a-new-profile-field)
* [Paso 2: Extender los registros de envío con el campo perfil](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Paso 3: Creación de destinatarios de objetivo de envío inscritos en el programa de lealtad](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Paso 4: Crear un informe dinámico para filtrar destinatarios con la dimensión de perfil personalizada](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Paso 1: Crear un nuevo campo de perfil {#step-1--create-a-new-profile-field}

Primero necesitamos crear el nuevo campo de perfil **programa de lealtad** que asignará el nivel de lealtad a nuestros destinatarios: oro, plata o bronce.

>[!NOTE]
>
>Los recursos personalizados solo pueden ser administrados por un administrador.

Para ello:

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** y, a continuación, el **[!UICONTROL Profile (profile)]** recurso personalizado.

   ![](assets/custom_profile_1.png)

1. En la ficha **[!UICONTROL Data structure]**, en la categoría **[!UICONTROL Fields]**, haga clic en el botón **[!UICONTROL Add field]**.

   ![](assets/custom_profile_2.png)

1. Escriba **[!UICONTROL Label]**, **[!UICONTROL ID]** y seleccione el recurso personalizado **[!UICONTROL Type]**. Aquí seleccionamos **[!UICONTROL Text]** ya que los destinatarios tendrán la opción entre oro, plata y bronce.

   ![](assets/custom_profile_3.png)

1. Haga clic en el icono ![](assets/custom_profile_22.png) para definir el campo.

   ![](assets/custom_profile_12.png)

1. Aquí, necesitamos especificar los valores autorizados marcando **[!UICONTROL Specify a list of authorized valued]** y crear cada valor haciendo clic en **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Introduzca **[!UICONTROL Label]** y **[!UICONTROL Value]** y haga clic en **[!UICONTROL Add]**. Para este ejemplo, necesitamos crear el valor oro, plata y bronce. Haga clic en **[!UICONTROL Confirm]** cuando termine.

   ![](assets/custom_profile_14.png)

1. Seleccione la pestaña **[!UICONTROL Screen definition]** En la lista desplegable **[!UICONTROL Detail screen configuration]**, marque **[!UICONTROL Add personalized fields]** para crear una nueva sección en nuestro perfil.

   ![](assets/custom_profile_4.png)

1. Haga clic en el botón **[!UICONTROL Add an element]** para crear la nueva sección. Seleccione **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** o **[!UICONTROL List]**, luego el campo que se agregará en esta nueva sección.

   ![](assets/custom_profile_5.png)

1. También puede agregar un título a la sección en el campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Haga clic en **[!UICONTROL Save]** cuando finalice la configuración.

   ![](assets/custom_profile_6.png)

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para publicar en inicio su recurso personalizado.
1. Haga clic en **[!UICONTROL Prepare publication]** y, cuando termine la preparación, haga clic en el botón **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

El nuevo campo de perfil ya está listo para ser utilizado y seleccionado por sus destinatarios.

![](assets/custom_profile_8.png)

## Paso 2: Extender los registros de envío con el campo perfil {#step-2--extend-the-sending-logs-with-the-profile-field}

Ahora que se ha creado el campo de perfil, necesitamos ampliar los registros de envío con nuestro campo de perfil para crear la dimensión de perfil personalizada asociada en los informes dinámicos.

Antes de extender el registro con nuestro campo de perfil, asegúrese de que la ventana PII se ha aceptado para tener acceso a la ficha **[!UICONTROL Sending logs extension]**. Para obtener más información, consulte [esta página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>Los registros solo pueden ampliarse con campos de perfil por parte del administrador.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** y, a continuación, el **[!UICONTROL Profile (profile)]** recurso personalizado.
1. Abra la lista desplegable **[!UICONTROL Sending logs extension]**.
1. Haga clic en el botón **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Seleccione el campo creado anteriormente y haga clic en **[!UICONTROL Confirm]**.
1. Seleccione **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** para crear la dimensión de perfil personalizada.

   ![](assets/custom_profile_10.png)

   Esta opción solo está disponible si se ha aceptado la ventana PII. Para obtener más información, consulte [esta página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Haga clic en **[!UICONTROL Add]** y guarde el recurso personalizado.
1. Dado que el recurso personalizado se modificó, debemos publicarlo para implementar los nuevos cambios.

   En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para publicar en inicio su recurso personalizado.

1. Haga clic en **[!UICONTROL Prepare publication]** y, cuando termine la preparación, haga clic en el botón **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

El perfil personalizado ya está disponible como dimensión de perfil personalizada en los informes.

Ahora que el campo se ha creado y que los registros de envío se han ampliado con este campo de perfil, puede realizar inicios de destinatarios de objetivo en envíos.

## Paso 3: Cree destinatarios de objetivo de envío inscritos en el programa de lealtad {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Una vez publicado el campo perfil, puede realizar el inicio del envío. En este ejemplo, queremos destinatarios para cada destinatario inscrito en el programa de lealtad.

1. En la pestaña **[!UICONTROL Marketing activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Email]**.
1. Elija un **[!UICONTROL Email type]** y luego introduzca las propiedades del correo electrónico.
1. Para destinatario de destinatario inscrito en el programa de lealtad, arrastre y suelte la actividad **[!UICONTROL Profiles (attributes)]**.
1. Seleccione el campo creado anteriormente en la lista desplegable **[!UICONTROL Field]**.

   ![](assets/custom_profile_16.png)

1. Seleccione su **[!UICONTROL Filter conditions]**. Aquí, queremos destinatario a destinatarios que son parte de uno de los tres niveles de programa de lealtad.

   ![](assets/custom_profile_17.png)

1. Haga clic en **[!UICONTROL Confirm]** y, cuando termine de filtrar, haga clic en **[!UICONTROL Next]**.
1. Defina y personalice el contenido del mensaje, el nombre del remitente y el asunto. Para obtener más información sobre la creación de correo electrónico, consulte esta [página](../../designing/using/designing-content-in-adobe-campaign.md).

   A continuación, haga clic en **[!UICONTROL Create]**.

1. Cuando esté listo, puede enviar su mensaje y previsualización. Para obtener más información sobre cómo preparar y enviar su mensaje, consulte esta [página](../../sending/using/preparing-the-send.md).

Una vez que el correo electrónico se haya enviado correctamente a los destinatarios seleccionados, puede filtrar los inicios de datos y realizar un seguimiento del éxito del envío con los informes.

## Paso 4: Crear un informe dinámico para filtrar destinatarios con la dimensión de perfil personalizada {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Después de enviar el envío, puede desglosar los informes mediante la dimensión de perfil personalizada desde la tabla **[!UICONTROL Profile]**.

1. En la ficha **[!UICONTROL Reports]**, seleccione un informe listo para usar o haga clic en el botón **[!UICONTROL Create]** para inicio uno desde cero.

   ![](assets/custom_profile_18.png)

1. En la categoría **[!UICONTROL Dimensions]**, haga clic en **[!UICONTROL Profile]** y, a continuación, arrastre y suelte la dimensión de perfil personalizada **programa de lealtad** en la tabla improvisada.

   ![](assets/custom_profile_19.png)

1. Arrastre y suelte las métricas **[!UICONTROL Processed/Sent]** y **[!UICONTROL Open]** para filtrar los datos en inicio.

   ![](assets/custom_profile_20.png)

1. Arrastre y suelte una visualización en el espacio de trabajo si es necesario.

   ![](assets/custom_profile_21.png)

**Temas relacionados:**

* [Uso de datos de perfil personalizados para crear informes perspicaces](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
