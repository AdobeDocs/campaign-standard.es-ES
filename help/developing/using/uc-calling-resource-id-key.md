---
title: Llamada a un recurso mediante una clave de identificación formada por dos campos
seo-title: Llamada a un recurso mediante una clave de identificación formada por dos campos
description: Llamada a un recurso mediante una clave de identificación formada por dos campos
seo-description: Aprenda a llamar a un recurso utilizando una clave de identificación formada por dos campos
translation-type: tm+mt
source-git-commit: b46579e3bf270b26986e107be9d8e07a39841b38

---


# Llamada a un recurso mediante una clave de identificación formada por dos campos

En algunos casos, es posible que necesite definir para un recurso una clave de identificación formada por dos campos. Una vez configurada la clave de identificación, debe configurar una definición de filtro para poder llamar al recurso con esta clave de identificación, ya sea desde la interfaz de Campaign Standard o desde las API.

In this use case, the **Profile** resource has been extended with custom **"CRM ID"** and **"category"** field. Crearemos una clave de identificación para el recurso Perfil que se compondrá de estos dos campos. A continuación, configuraremos una definición de filtro para poder acceder al recurso Perfil mediante la clave de identificación.

Estos son los pasos principales para este caso de uso:

1. Configure la clave de identificación para el recurso Perfil, en función de los dos campos.
1. Configure la definición del filtro para poder llamar al recurso Profile utilizando su clave de identificación.
1. Llame al recurso Perfil desde la interfaz o desde las API.

Temas relacionados:

* [Creación o ampliación del recurso](help/developing/using/creating-or-extending-the-resource.md)
* [Definición de claves de identificación](help/developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [API de REST de campaña estándar](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## Paso 1: Configurar la clave de identificación

>[!NOTE]
> Global concepts when configuring identification keys are detailed in [this section](help/developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Antes de configurar la clave de identificación, asegúrese de que el recurso se haya ampliado con los campos deseados y que se haya publicado. For more on this, refer to [this section](help/developing/using/creating-or-extending-the-resource.md).

1. Go to the **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** menu, then open the **[!UICONTROL Profile]** resource.

   ![](assets/uc_idkey1.png)

1. In the **[UICONTROL Identification keys]** section, click the **[!UICONTROL Create element]** button.

   ![](assets/uc_idkey2.png)

1. Add the two custom "CRM ID" and "Category" fields, then click **[UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > If you want to display the two custom fields in the profile's interface, configure the **[UICONTROL Screen definition]** tab. For more on this, refer to [this section](help/developing/using/configuring-the-screen-definition.md).

1. Ahora puede configurar la definición de filtro para poder llamar al recurso utilizando su clave de identificación.

## Paso 2: Configurar la definición del filtro

>[!NOTE]
> Global concepts when configuring filter definitions are detailed in [this section](help/developing/using/configuring-filter-definition.md).

1. In the **[UICONTROL Filter definition]** tab, click **[UICONTROL Add an element]**, then enter the filter definition's label and ID.

1. Edite las propiedades de la definición del filtro para configurar sus reglas.

   ![](assets/uc_idkey4.png)

1. Arrastre y suelte en el espacio de trabajo la tabla que contiene los campos utilizados en la clave de identificación.

   ![](assets/uc_idkey5.png)

1. Select the first field used in the identification key ("CRM ID"), then activate the **[UICONTROL Switch to parameters]** option.

   ![](assets/uc_idkey6.png)

1. In the **[UICONTROL Filter conditions]** section, keep the **[UICONTROL Equal]** operator, then define the parameter's name and click the plus sign to create it.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Una vez que haya hecho clic en el botón más, el nombre del parámetro se genera automáticamente. Tenga en cuenta esta información, ya que la necesitará para utilizar el filtro de las API.

1. Repita los pasos anteriores con todos los campos que componen la clave de identificación ("category") y, a continuación, guarde los cambios.

   ![](assets/uc_idkey8.png)

1. La definición del filtro ahora está configurada. Puede publicar el recurso para que el filtro esté disponible.

## Paso 3: Recurra al recurso en función de su clave de identificación

Una vez configurada la clave de identificación y su definición de filtro, puede utilizarlos para llamar al recurso, ya sea desde la interfaz estándar de Campaign o desde las API de REST.

To use the filter definition from the interface, use a **[UICONTROL Query]** activity in a workflow (see [this section](help/automating/using/query.md)). El filtro está disponible en el panel izquierdo.

![](assets/uc_idkey9.png)

Para utilizar la definición de filtro desde las API de REST de Campaign Standard, utilice la sintaxis siguiente:

\ «GET /profileAndServicesExt/ &lt; resourcename &gt; &lt; filtername &gt;? &lt; param 1_ parameter &gt; = &lt; value &gt; &amp; &lt; param 2_ parameter &gt; = &lt; value &gt;\ "

En nuestro caso, la sintaxis para recuperar un perfil de la categoría "primavera" y con el ID de CRM "123456" sería:

\ «GET https://mc.adobe.io/ &lt; ORGANIZATION &gt;/campaign/profileandservicesext/profile/identification_ key? category_ parameter = spring &amp; crm_ id_ parameter = 123456\ "

For more details, refer to [Campaign Standard REST APIs documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).