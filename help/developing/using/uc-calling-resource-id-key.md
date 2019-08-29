---
title: Llamada a un recurso con una clave de identificación compuesta
seo-title: Llamada a un recurso con una clave de identificación compuesta
description: Llamada a un recurso con una clave de identificación compuesta
seo-description: Aprenda a llamar a un recurso utilizando una clave de identificación compuesta
translation-type: tm+mt
source-git-commit: ff9861a2b8a59843cc668cec9f89b9ea76822d66

---


# Llamada a un recurso con una clave de identificación compuesta

En algunos casos, es posible que necesite definir para un recurso una clave de identificación formada por dos campos. Una vez configurada la clave de identificación, debe configurar una definición de filtro para poder llamar al recurso con esta clave de identificación, ya sea desde la interfaz de Campaign Standard o desde las API.

En este caso de uso, el recurso **Perfil** se ha ampliado con el campo personalizado **«ID de CRM»** y **«categoría»** . Crearemos una clave de identificación para el recurso Perfil que se compondrá de estos dos campos. A continuación, configuraremos una definición de filtro para poder acceder al recurso Perfil mediante la clave de identificación.

Los pasos principales para este caso de uso son:

1. Configure la clave de identificación para el recurso Perfil, en función de los dos campos.
1. Configure la definición del filtro para poder llamar al recurso Profile utilizando su clave de identificación.
1. Llame al recurso Perfil desde la interfaz o desde las API.

Temas relacionados:

* [Creación o ampliación del recurso](../../developing/using/creating-or-extending-the-resource.md)
* [Definición de claves de identificación](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [API de REST de campaña estándar](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)

## Paso 1: Configurar la clave de identificación

>[!NOTE]
> En [esta sección se describen los conceptos globales al configurar claves de identificación](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Antes de configurar la clave de identificación, asegúrese de que el recurso se haya ampliado con los campos deseados y que se haya publicado. For more on this, refer to [this section](../../developing/using/creating-or-extending-the-resource.md).

1. Vaya al menú **[!UICONTROL Administration]** / **[!UICONTROL Developement]** / **[!UICONTROL Custom resources]** y luego abra **[!UICONTROL Profile]** el recurso.

   ![](assets/uc_idkey1.png)

1. En **[!UICONTROL Identification keys]** la sección, haga clic en **[!UICONTROL Create element]** el botón.

   ![](assets/uc_idkey2.png)

1. Agregue los dos campos personalizados "ID de CRM" y "Categoría", luego haga clic **[!UICONTROL Confirm]** en.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Si desea mostrar los dos campos personalizados en la interfaz del perfil, configure **[!UICONTROL Screen definition]** la ficha. For more on this, refer to [this section](../../developing/using/configuring-the-screen-definition.md).

1. Ahora puede configurar la definición de filtro para poder llamar al recurso utilizando su clave de identificación.

## Paso 2: Configurar la definición del filtro

>[!NOTE]
> En [esta sección se describen los conceptos globales al configurar definiciones de filtro](../../developing/using/configuring-filter-definition.md).

1. En **[!UICONTROL Filter definition]** la ficha, haga clic en **[!UICONTROL Add an element]** y, a continuación, introduzca la etiqueta y el ID de la definición del filtro.

1. Edite las propiedades de la definición del filtro para configurar sus reglas.

   ![](assets/uc_idkey4.png)

1. Arrastre y suelte en el espacio de trabajo la tabla que contiene los campos utilizados en la clave de identificación.

   ![](assets/uc_idkey5.png)

1. Seleccione el primer campo utilizado en la clave de identificación ("ID de CRM") y, a continuación, active **[!UICONTROL Switch to parameters]** la opción.

   ![](assets/uc_idkey6.png)

1. En **[!UICONTROL Filter conditions]** la sección, mantenga el **[!UICONTROL Equal]** operador y, a continuación, defina el nombre del parámetro y haga clic en el signo más para crearlo.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Una vez que haya hecho clic en el botón más, el nombre del parámetro se genera automáticamente. Tenga en cuenta esta información, ya que la necesitará para utilizar el filtro de las API.

1. Repita los pasos anteriores con todos los campos que componen la clave de identificación ("category") y, a continuación, guarde los cambios.

   ![](assets/uc_idkey8.png)

1. La definición del filtro ahora está configurada. Puede publicar el recurso para que el filtro esté disponible.

## Paso 3: Recurra al recurso en función de su clave de identificación

Una vez configurada la clave de identificación y su definición de filtro, puede utilizarlos para llamar al recurso, ya sea desde la interfaz estándar de Campaign o desde las API de REST.

Para utilizar la definición de filtro desde la interfaz, utilice una **[!UICONTROL Query]** actividad en un flujo de trabajo (consulte [esta sección](../../automating/using/query.md)). El filtro está disponible en el panel izquierdo.

![](assets/uc_idkey9.png)

Para utilizar la definición de filtro desde las API de REST de Campaign Standard, utilice la sintaxis siguiente:

```
GET /profileAndServicesExt/<resourceName><filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

En nuestro caso, la sintaxis para recuperar un perfil de la categoría "primavera" y con el ID de CRM "123456" sería:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/identification_key?category_parameter=spring&crm_id_parameter=123456
```

Para obtener más información, consulte la documentación de las API de REST [de Campaign Standard](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#filtering).