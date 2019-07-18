---
title: Actualización de la estructura de la base de datos
seo-title: Actualización de la estructura de la base de datos
description: Actualización de la estructura de la base de datos
seo-description: Descubra cómo actualizar la base de datos de Adobe Campaign.
page-status-flag: no activado nunca
uuid: 6 c 802 f 4 f-d 298-4 ca 4-acdb -09 f 2 ad 3865 b 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: adición-ampliación-a-recurso
discoiquuid: 2448 b 126-66 b 8-4608-aa 6 c -8028 fb 1902 a 4
context-tags: implementar, main; Eventcusresource, información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Updating the database structure{#updating-the-database-structure}

Para que las modificaciones del modelo de datos sean eficaces y poder utilizarlas, es necesario actualizar la estructura de la base de datos.

>[!NOTE]
>
>Los recursos personalizados se actualizan automáticamente durante las actualizaciones automáticas realizadas por Adobe.

## Publishing a custom resource {#publishing-a-custom-resource}

Para aplicar los cambios realizados en los recursos, debe realizar una actualización de base de datos.

>[!NOTE]
>
>Si se modifica o elimina un campo de un recurso personalizado en un evento, el evento correspondiente se cancelará automáticamente. See [Configuring Transactional messaging](../../administration/using/configuring-transactional-messaging.md).

1. From the advanced menu, via the Adobe Campaign logo, select **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]**, then **[!UICONTROL Publishing]**.
1. By default, the option **[!UICONTROL Determine modifications since the last publication]** is checked, which means that only the changes carried out since the last update will be applied.

   >[!NOTE]
   >
   >The **[!UICONTROL Repair database structure]** reestablishes a correct configuration if the publication failed before completing. Todas las modificaciones que se realicen directamente en la base de datos y no utilicen recursos personalizados se eliminarán.

   ![](assets/schema_extension_12.png)

1. Click the **[!UICONTROL Prepare publication]** button to start the analysis. Tenga en cuenta que las actualizaciones de tabla grandes deben realizarse cuando la instancia no está intensa por los flujos de trabajo.

   To learn more on the action to perform on the Profiles &amp; Services API, refer to [Publishing a resource with API extension](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).

   ![](assets/schema_extension_13.png)

1. Once the publication has been carried out, click the **[!UICONTROL Publish]** button to apply your new configurations.
1. Once published, the **[!UICONTROL Summary]** pane of each resource indicates that the status is now **[!UICONTROL Published]** and specifies the date of the last publication.

   >[!NOTE]
   >
   >Si realiza nuevos cambios en un recurso, debe repetir esta operación para que se apliquen los cambios.

   If resources have the **[!UICONTROL Pending re-draft]** status before publishing, then an additional message will appear inviting you to check your actions because publishing will result in definitive changes (deleting columns, tables...). To help you carry out this last change, an **[!UICONTROL SQL Script]** tab is available. Proporciona el comando SQL que se ejecutará durante la publicación.

   ![](assets/schema_extension_scriptsql.png)

   >[!NOTE]
   >
   >You can stop the Re-draft process by clicking the **[!UICONTROL Cancel re-draft]** button. Esta acción revertirá el estado del recurso a su original.

1. If your publication failed, you can always go back to the previous publication by clicking **[!UICONTROL Back to latest successful publication]**.

   Tenga en cuenta que, si deja la publicación en estado de error, se abrirá una ventana emergente en cuanto inicie sesión en la instancia para recordarle que corrija esta publicación. Su instancia no se actualizará con versiones de producto nuevas hasta que se corrija la publicación.

   ![](assets/schema_extension_31.png)

## Publishing a resource with API extension {#publishing-a-resource-with-api-extension}

Puede crear la API de perfil y servicios en los siguientes casos:

* When you extend the custom resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]**, you can perform an update of the Profiles and Services API to integrate the fields declared in the custom resources extension.
* When you define a custom resource and you create a link between the resources **[!UICONTROL Profiles]** or **[!UICONTROL Services]** and the custom resource, you can perform an update to include the new resource in the API.

Puede seleccionar esta opción en la pantalla de publicación.

* Si la API todavía no se ha publicado (significa que nunca ha extendido el recurso o si nunca ha seleccionado esta opción para este recurso u otro recurso), tiene la opción de crearla o no.

   ![](assets/create-profile-and-services-api.png)

* Si la API ya se ha publicado (significa que ya ha ampliado el recurso y ha seleccionado esta opción una vez), se forzará la actualización de la API.

   De hecho, una vez que se ha creado, la API se actualiza automáticamente cada vez que vuelve a publicarla. Esto sirve para evitar romper el perfil de servicio o de servicio de esta API y dañar su instancia.

Note that by default, the custom resource is integrated, but, for a specific behavior, if you don't want to publish this resource, you can select the option **[!UICONTROL Hide this resource from APIs]** available in the **[!UICONTROL Resource Properties]**.

![](assets/removefromextoption.png)

After the **[!UICONTROL Prepare Publication]** step, Adobe Campaign displays the delta between the current version of the API and the future version after the publication in the tab **[!UICONTROL Profiles & Services API Preview]**. Si amplía la API por primera vez, el delta compara la definición de recurso personalizada predeterminada con la extensión.

La información mostrada en la ficha se divide en tres secciones: agregados, eliminados y modificados.

![](assets/extendpandsapi_diff.png)

El análisis del delta es un paso obligatorio, ya que el paso de publicación modificará el comportamiento de la API y lo más probable es que afecte al desarrollo que lo rodea en un efecto domino.

>[!NOTE]
>
>This publication updates the **[!UICONTROL profilesAndServicesExt]** API. **[!UICONTROL profilesAndServices]** La API no se actualiza.

For more information on the Adobe Campaign API, consult the dedicated Adobe Campaign documentation on [Adobe IO](https://docs.campaign.adobe.com/doc/standard/en/adobeio.html).
