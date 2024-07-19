---
title: Creación de una dimensión de perfil personalizada
description: Obtenga información sobre cómo crear una dimensión de perfil personalizada basada en datos de perfil personalizados.
audience: reporting
content-type: reference
topic-tags: customizing-reports
feature: Reporting
role: Leader
level: Intermediate
exl-id: 98516af1-d4dd-4c1f-b360-f19208c22f82
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 5%

---

# Creación de una dimensión de perfil personalizada{#creating-a-custom-profile-dimension}

Los informes también se pueden crear y administrar en función de los datos de perfil personalizados creados durante la extensión de recurso personalizado de perfil.

En este ejemplo, deseamos crear el campo de perfil personalizado **Programas de fidelización**, que se dividirá en tres niveles: oro, plata y bronce. A continuación, se ampliará este perfil personalizado para que pueda utilizarlo como dimensión de perfil personalizada en informes dinámicos.

* [Paso 1: Creación de un nuevo campo de perfil](#step-1--create-a-new-profile-field)
* [Paso 2: Ampliación de los registros de envío con el campo de perfil](#step-2--extend-the-sending-logs-with-the-profile-field)
* [Paso 3: Creación de una entrega dirigido a los destinatarios inscritos en el programa de fidelidad](#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program)
* [Paso 4: Crear un informe dinámico para filtrar los destinatarios con la dimensión de perfil personalizada](#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension)

## Paso 1: Creación de un nuevo campo de perfil {#step-1--create-a-new-profile-field}

Primero necesitamos crear el nuevo campo de perfil **Programa de fidelidad** que asignará el nivel de fidelidad a nuestros destinatarios: oro, plata o bronce.

>[!NOTE]
>
>Solo un administrador puede administrar los recursos personalizados.

Para ello:

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** y luego el recurso personalizado **[!UICONTROL Profile (profile)]**.

   ![](assets/custom_profile_1.png)

1. En la ficha **[!UICONTROL Data structure]**, en la categoría **[!UICONTROL Fields]**, haga clic en el botón **[!UICONTROL Add field]**.

   ![](assets/custom_profile_2.png)

1. Escriba **[!UICONTROL Label]**, **[!UICONTROL ID]** y seleccione el recurso personalizado **[!UICONTROL Type]**. Aquí, seleccionamos **[!UICONTROL Text]**, ya que los destinatarios tendrán la opción entre oro, plata y bronce.

   ![](assets/custom_profile_3.png)

1. Haga clic en el icono ![](assets/custom_profile_22.png) para definir el campo.

   ![](assets/custom_profile_12.png)

1. Aquí, necesitamos especificar los valores autorizados marcando **[!UICONTROL Specify a list of authorized valued]** y crear cada valor haciendo clic en **[!UICONTROL Create element]**.

   ![](assets/custom_profile_13.png)

1. Escriba **[!UICONTROL Label]** y **[!UICONTROL Value]** y haga clic en **[!UICONTROL Add]**. Para este ejemplo, necesitamos crear el valor oro, plata y bronce. Haga clic en **[!UICONTROL Confirm]** cuando termine.

   ![](assets/custom_profile_14.png)

1. Seleccione la pestaña **[!UICONTROL Screen definition]** En la lista desplegable **[!UICONTROL Detail screen configuration]**, marque la sección **[!UICONTROL Add personalized fields]** para crear una nueva sección en su perfil.

   ![](assets/custom_profile_4.png)

1. Haga clic en el botón **[!UICONTROL Add an element]** para crear la nueva sección. Seleccione **[!UICONTROL Type]**: **[!UICONTROL Input field]**, **[!UICONTROL Value]** o **[!UICONTROL List]** y, a continuación, el campo que desea agregar en esta nueva sección.

   ![](assets/custom_profile_5.png)

1. También puede agregar un título a la sección en el campo **[!UICONTROL Customize the title of the section where the fields will be displayed]**.

   Haga clic en **[!UICONTROL Save]** cuando finalice la configuración.

   ![](assets/custom_profile_6.png)

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para iniciar la publicación del recurso personalizado.
1. Haga clic en **[!UICONTROL Prepare publication]** y, cuando termine la preparación, haga clic en el botón **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

El nuevo campo de perfil ya está listo para que lo utilicen y seleccionen los destinatarios.

![](assets/custom_profile_8.png)

## Paso 2: Ampliación de los registros de envío con el campo de perfil {#step-2--extend-the-sending-logs-with-the-profile-field}

Ahora que se ha creado el campo de perfil, es necesario ampliar los registros de envío con nuestro campo de perfil para crear la dimensión de perfil personalizada asociada en los informes dinámicos.

Antes de ampliar el registro con nuestro campo de perfil, asegúrese de que se aceptó la ventana PII para tener acceso a la pestaña **[!UICONTROL Sending logs extension]**. Para obtener más información, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

>[!NOTE]
>
>El administrador solo puede ampliar los registros con campos de perfil.

1. En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom resources]** y luego el recurso personalizado **[!UICONTROL Profile (profile)]**.
1. Abra la lista desplegable **[!UICONTROL Sending logs extension]**.
1. Haga clic en el botón **[!UICONTROL Create element]**.

   ![](assets/custom_profile_9.png)

1. Seleccione el campo creado anteriormente y haga clic en **[!UICONTROL Confirm]**.
1. Marque **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** para crear su dimensión de perfil personalizada.

   ![](assets/custom_profile_10.png)

   Esta opción solo está disponible si se ha aceptado la ventana PII. Para obtener más información, consulte esta [página](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

1. Haga clic en **[!UICONTROL Add]** y guarde el recurso personalizado.
1. Dado que el recurso personalizado se ha modificado, es necesario publicarlo para implementar los nuevos cambios.

   En el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Publication]** para iniciar la publicación del recurso personalizado.

1. Haga clic en **[!UICONTROL Prepare publication]** y, cuando termine la preparación, haga clic en el botón **[!UICONTROL Publish]**.

   ![](assets/custom_profile_7.png)

El perfil personalizado ya está disponible como dimensión de perfil personalizada en los informes.

Ahora que el campo se ha creado y que los registros de envío se han ampliado con este campo de perfil, puede empezar a dirigirse a los destinatarios en las entregas.

## Paso 3: Creación de una entrega dirigido a los destinatarios inscritos en el programa de fidelidad {#step-3--create-a-delivery-targeting-recipients-enrolled-in-the-loyalty-program}

Una vez publicado el campo de perfil, puede iniciar la entrega. En este ejemplo, queremos dirigirnos a todos los destinatarios inscritos en el programa de fidelización.

1. En la pestaña **[!UICONTROL Marketing activities]**, haga clic en **[!UICONTROL Create]** y seleccione **[!UICONTROL Email]**.
1. Elija un(a) **[!UICONTROL Email type]** e introduzca las propiedades del correo electrónico.
1. Para dirigirse al destinatario inscrito en el programa de fidelización, arrastre y suelte la actividad **[!UICONTROL Profiles (attributes)]**.
1. Seleccione el campo creado anteriormente en la lista desplegable **[!UICONTROL Field]**.

   ![](assets/custom_profile_16.png)

1. Seleccione su **[!UICONTROL Filter conditions]**. En este caso, queremos segmentar a los destinatarios que forman parte de uno de los tres niveles del programa de fidelidad.

   ![](assets/custom_profile_17.png)

1. Haga clic en **[!UICONTROL Confirm]** y, cuando termine el filtrado, haga clic en **[!UICONTROL Next]**.
1. Defina y personalice el contenido del mensaje, el nombre del remitente y el asunto. Para obtener más información sobre la creación de correo electrónico, consulte esta [página](../../designing/using/designing-content-in-adobe-campaign.md).

   A continuación, haga clic en **[!UICONTROL Create]**.

1. Cuando esté listo, puede obtener una vista previa y enviar el mensaje. Para obtener más información sobre cómo preparar y enviar el mensaje, consulte esta [página](../../sending/using/preparing-the-send.md).

Una vez que el correo electrónico se haya enviado correctamente a los destinatarios seleccionados, puede empezar a filtrar los datos y realizar un seguimiento del éxito de la entrega con informes.

## Paso 4: Crear un informe dinámico para filtrar los destinatarios con la dimensión de perfil personalizada {#step-4--create-a-dynamic-report-to-filter-recipients-with-the-custom-profile-dimension}

Después de realizar el envío, puede desglosar informes usando la dimensión de perfil personalizada de la tabla **[!UICONTROL Profile]**.

1. En la ficha **[!UICONTROL Reports]**, seleccione un informe predeterminado o haga clic en el botón **[!UICONTROL Create]** para iniciar uno desde cero.

   ![](assets/custom_profile_18.png)

1. En la categoría **[!UICONTROL Dimensions]**, haga clic en **[!UICONTROL Profile]** y, a continuación, arrastre y suelte la dimensión de perfil **Programa de fidelidad** personalizada en la tabla de forma libre.

   ![](assets/custom_profile_19.png)

1. Arrastre y suelte las métricas **[!UICONTROL Processed/Sent]** y **[!UICONTROL Open]** para empezar a filtrar los datos.

   ![](assets/custom_profile_20.png)

1. Arrastre y suelte una visualización en el espacio de trabajo si es necesario.

   ![](assets/custom_profile_21.png)

**Temas relacionados:**

* [Uso de datos de perfil personalizados para crear informes reveladores](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Reportandshareinsightswithallstakeholders)
