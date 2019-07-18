---
title: Compartir audiencias con los servicios principales de Audience Manager o Personas
seo-title: Compartir audiencias con los servicios principales de Audience Manager o Personas
description: Compartir audiencias con los servicios principales de Audience Manager o Personas
seo-description: Descubra cómo importar o exportar su audiencia dentro de las distintas soluciones de Adobe Experience Cloud.
page-status-flag: no activado nunca
uuid: a 3701 e 72-5846-4241-afee-d 713 b 499 a 27 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
discoiquuid: 77 af 0772-52 b 5-46 bc-a 964-675 b 45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 698466596fdacd005dc4d72b8071208c8c39f77d

---


# Sharing audiences with Audience Manager or People core service{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importing an audience {#importing-an-audience}

La integración del servicio principal Personas permite importar directamente una audiencia a Adobe Campaign a través de un flujo de trabajo técnico para enriquecer la base de datos. For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

Importing audiences/segments from People core service in Adobe Campaign can be carried out from the **[!UICONTROL Audiences]** menu only by users connected via IMS (authentication via Adobe ID).

1. Go to the **[!UICONTROL Audiences]** menu.
1. In the action bar, select **[!UICONTROL Create]** to be taken to the screen to create an audience.
1. Especifique la etiqueta de la nueva audiencia.
1. Set the audience **[!UICONTROL Type]** to **[!UICONTROL Experience Cloud]** to indicate that the audience being created is an audience that was imported from People core service.
1. From the **[!UICONTROL Name of the shared audience]** field, select the audience to import. Solo se pueden importar segmentos. Los datos granulares que incluyen pares de clave-valor, características y reglas no son compatibles.

   ![](assets/aam_import_audience.png)

1. Select the corresponding **[!UICONTROL Shared Data Source]**.

   If the selected data source is configured to use an encryption algorithm, an additional option offers you the possibility to **[!UICONTROL Force reconciliation with a profile]**. Check this option if the **[!UICONTROL Channel]** field of the data source is set to Email or Mobile (SMS) and if you want to leverage profile data.

   If you do not select the **[!UICONTROL Force reconciliation with a profile]** and if **[!UICONTROL Channel]** is set in AMC Data source to Email or Mobile (SMS) then all the encrypted declared IDs are decrypted. An audience of type **File** with a list of all the email addresses/mobile phone numbers is created/updated. De este modo, no se pierde ningún número de teléfono móvil o dirección de correo al importar una audiencia compartida a través de esta integración, aunque este perfil no exista en Campaign. Tenga en cuenta que este tipo de audiencias no se puede utilizar directamente porque es necesario reconciliarlas manualmente mediante flujos de trabajo.

1. Confirme la creación de la audiencia.

   La audiencia se importa a través de un flujo de trabajo técnico. Se compone de registros de los que el ID (' ID de visitante'o'ID declarado ') se pudo reconciliar con la dimensión de perfil. Los ID de los segmentos del servicio principal Personas que no son reconocidos por Adobe Campaign no se importan.

Ahora, su audiencia se importa en su base de datos de Adobe Campaign. El proceso de importación tarda entre 24 y 36 horas para sincronizarse, cuando los segmentos se importan directamente desde los servicios principales Personas o Audience Manager. Después de este período, podrá encontrar y utilizar la nueva audiencia en Adobe Campaign.

>[!NOTE]
>
>Si importa audiencias de Adobe Analytics a Adobe Campaign, estas audiencias deben compartirse primero en el servicio principal Personas o en Audience Manager. Este proceso tarda entre 12 y 24 horas, lo que debe agregarse a la sincronización de 24-36 horas con Campaign. En ese caso específico, el intervalo de tiempo para compartir audiencias puede ser de hasta 60 horas. For more information on Adobe Analytics audience sharing in People Core service and Audience manager, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exporting an audience {#exporting-an-audience}

An audience can be exported from Adobe Campaign to Audience Manager or People core service using a workflow and the **[!UICONTROL Save audience]** activity.

Se puede llevar a cabo en un nuevo flujo de trabajo y solo por usuarios conectados mediante IMS (autenticación mediante Adobe ID).

1. Cree un nuevo flujo de trabajo a partir de un programa, una campaña o una lista de actividades de marketing.
1. Con las distintas actividades disponibles, establezca un conjunto de perfiles.
1. After the targeting, drag and drop a **[!UICONTROL Save audience]** activity into the workflow, then open it.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Specify the audience using the **[!UICONTROL Shared audience]** field. En la ventana que se abre, tiene la opción de seleccionar una audiencia existente o crear una audiencia nueva:

   * Si selecciona una audiencia existente, solo se agregarán a la audiencia los nuevos registros.
   * To export your profile list into a new audience, complete the **[!UICONTROL Segment name]** field then click **[!UICONTROL Create]** before selecting the newly created audience.
   ![](assets/aam_save_audience_segment_picker.png)

   Para que se pueda sincronizar e intercambiar, los registros deben tener un ID de Adobe Experience Cloud (' ID de visitante'o'ID declarado '). Los registros no alineados se omiten al importar y exportar audiencias.

1. Para finalizar, haga clic en la marca de verificación situada en la parte superior derecha de la pantalla.
1. Select the corresponding **[!UICONTROL Shared Data Source]**.
1. If you like, check the **[!UICONTROL Generate an outbound transition]** box to use the profiles that were exported. Solo se exportan los perfiles que se pueden reconciliar.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo para exportar su audiencia. La sincronización entre el servicio principal de Adobe Campaign y Personas puede llevar varias horas

La sincronización entre el servicio principal de Adobe Campaign y Personas tarda 24-36 horas. Después de este período, podrá encontrar la nueva audiencia en el servicio principal Personas y reutilizarla en otras soluciones de Adobe Experience Cloud. For more information on using an Adobe Campaign shared audience in Adobe People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**Temas relacionados:**

* [Flujos de trabajo](../../automating/using/workflow-data-and-processes.md)
* [Audiencias](../../audiences/using/about-audiences.md)

