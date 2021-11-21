---
title: Invocación de un recurso mediante una clave de identificación compuesta
description: Obtenga información sobre cómo llamar a un recurso mediante una clave de identificación compuesta
feature: Data Model
role: Developer
level: Experienced
exl-id: c7aca0c3-525d-4195-8c04-2fad32ca43b7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 7%

---

# Invocación de un recurso mediante una clave de identificación compuesta{#calling-a-resource-using-a-composite-identification-key}

En algunos casos, es posible que necesite definir para un recurso una clave de identificación compuesta por dos campos. Una vez configurada la clave de identificación, debe configurar una definición de filtro para poder llamar al recurso con esta clave de identificación, ya sea desde la interfaz de Campaign Standard o las API.

En este caso de uso, la variable **Perfil** el recurso se ha ampliado con **&quot;ID de CRM&quot;** y **&quot;category&quot;** campos. Crearemos una clave de identificación para el recurso Perfil , que se compone de estos dos campos. A continuación, configuraremos una definición de filtro para que podamos acceder al recurso Perfil mediante la clave de identificación.

Los pasos principales para este caso de uso son:

1. Configure la clave de identificación para el recurso Perfil , en función de los dos campos.
1. Configure la definición del filtro para poder llamar al recurso Perfil mediante su clave de identificación.
1. Llame al recurso Perfil desde la interfaz o desde el APis.

Temas relacionados:

* [Creación o ampliación del recurso](../../developing/using/creating-or-extending-the-resource.md)
* [Definición de claves de identificación](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [API de REST del Campaign Standard](../../api/using/get-started-apis.md)

## Paso 1: Configuración de la clave de identificación{#step-1-configure-the-identification-key}

>[!NOTE]
> Los conceptos globales al configurar claves de identificación se detallan en [esta sección](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys).

1. Antes de configurar la clave de identificación, asegúrese de que el recurso se ha ampliado con los campos deseados y que se ha publicado. Para obtener más información, consulte [esta sección](../../developing/using/creating-or-extending-the-resource.md).

1. Vaya a la **[!UICONTROL Administration]** / **[!UICONTROL Development]** / **[!UICONTROL Custom resources]** y, a continuación, abra **[!UICONTROL Profile]** recurso.

   ![](assets/uc_idkey1.png)

1. En el **[!UICONTROL Identification keys]** , haga clic en el botón **[!UICONTROL Create element]** botón.

   ![](assets/uc_idkey2.png)

1. Añada los dos campos personalizados &quot;CRM ID&quot; y &quot;Category&quot; y, a continuación, haga clic en **[!UICONTROL Confirm]**.

   ![](assets/uc_idkey3.png)

   >[!NOTE]
   > Si desea mostrar los dos campos personalizados en la interfaz del perfil, configure la variable **[!UICONTROL Screen definition]** pestaña . Para obtener más información, consulte [esta sección](../../developing/using/configuring-the-screen-definition.md).

1. Ahora puede configurar la definición del filtro para poder llamar al recurso mediante su clave de identificación.

## Paso 2: Configuración de la definición del filtro{#step-2-configure-the-filter-definition}

>[!NOTE]
> Los conceptos globales al configurar definiciones de filtros se detallan en [esta sección](../../developing/using/configuring-filter-definition.md).

1. En el **[!UICONTROL Filter definition]** , haga clic en **[!UICONTROL Add an element]** y, a continuación, introduzca la etiqueta y el ID de la definición del filtro.

1. Edite las propiedades de la definición del filtro para configurar sus reglas.

   ![](assets/uc_idkey4.png)

1. Arrastre y suelte en el espacio de trabajo la tabla que contiene los campos utilizados en la clave de identificación.

   ![](assets/uc_idkey5.png)

1. Seleccione el primer campo utilizado en la clave de identificación (&quot;CRM ID&quot;) y, a continuación, active la variable **[!UICONTROL Switch to parameters]** .

   ![](assets/uc_idkey6.png)

1. En el **[!UICONTROL Filter conditions]** mantenga la **[!UICONTROL Equal]** , defina el nombre del parámetro y haga clic en el signo más para crearlo.

   ![](assets/uc_idkey7.png)

   >[!NOTE]
   > Una vez que haya hecho clic en el **+** , el nombre del parámetro se genera automáticamente. Tenga en cuenta esta información, ya que necesitará que utilice el filtro de las API.

1. Repita los pasos anteriores con todos los campos que componen la clave de identificación (&quot;categoría&quot;) y, a continuación, guarde los cambios.

   ![](assets/uc_idkey8.png)

1. La definición del filtro ya está configurada. Puede publicar el recurso para que el filtro esté disponible.

## Paso 3: Llame al recurso en función de su clave de identificación{#step-3-call-the-resource-based-on-its-identification-key}

Una vez configurados la clave de identificación y su definición de filtro, puede utilizarla para llamar al recurso, ya sea desde la interfaz estándar de Campaign o las API de REST.

Para utilizar la definición de filtro de la interfaz, utilice un **[!UICONTROL Query]** actividad en un flujo de trabajo (consulte [esta sección](../../automating/using/query.md)). El filtro está disponible en el panel izquierdo.

![](assets/uc_idkey9.png)

Para utilizar la definición de filtro de las API de REST de Campaign Standard, utilice la siguiente sintaxis:

```
GET /profileAndServicesExt/<resourceName>/by<filterName>?<param1_parameter>=<value>&<param2_parameter>=<value>
```

>[!NOTE]
>Para llamar a un filtro personalizado, utilice el prefijo &quot;by&quot; seguido del nombre del filtro definido al configurar la definición del filtro en [paso 2](../../developing/using/uc-calling-resource-id-key.md#step-2-configure-the-filter-definition).

En nuestro caso, la sintaxis para recuperar un perfil de la categoría &quot;primavera&quot; con el ID de CRM &quot;123456&quot; sería:

```
GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/profile/byidentification_key?category_parameter=spring&crm_id_parameter=123456
```

Para obtener más información, consulte [Documentación de las API de REST del Campaign Standard](../../api/using/filtering.md).
