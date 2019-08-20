---
title: Configuración de la estructura de datos del recurso
seo-title: Configuración de la estructura de datos del recurso
description: Configuración de la estructura de datos del recurso
seo-description: Descubra cómo configurar la estructura de datos.
page-status-flag: no activado nunca
uuid: 60 fe 80 c 0-9 df 6-4808-a 432-60 a 1977216 ea ea
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: adición-ampliación-a-recurso
discoiquuid: 4 f 22 ee 35-1 d 5 f -4 c 75-95 b 4-3 e 38 b 85 de 26 e
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 888cf4cd7bfa7f82bfe70c408f8c2785c51c36e2

---


# Configuración de la estructura de datos del recurso{#configuring-the-resource-s-data-structure}

Después de crear un nuevo recurso personalizado, debe configurar la estructura de datos.

Al editar el recurso, puede **[!UICONTROL Data structure]** agregar:

* [Campos](../../developing/using/configuring-the-resource-s-data-structure.md#adding-fields-to-a-resource)
* [Claves de identificación](../../developing/using/configuring-the-resource-s-data-structure.md#defining-identification-keys)
* [Índices](../../developing/using/configuring-the-resource-s-data-structure.md#defining-indexes)
* [Vínculos](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)
* [Envío de registros](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

## Adición de campos a un recurso {#adding-fields-to-a-resource}

Puede agregar campos nuevos a un recurso para almacenar datos que no forman parte del modelo de datos de cuadro.

1. Utilice **[!UICONTROL Create element]** el botón para crear un campo.
1. Especifique una etiqueta, un ID, un tipo de campo y defina la longitud máxima autorizada para este campo.

   **[!UICONTROL ID]** El campo es obligatorio y debe ser único para cada campo agregado.

   >[!NOTE]
   >
   >Si deja el **[!UICONTROL Label]** campo vacío, se completará automáticamente desde el ID.
   >Recomendamos utilizar 30 caracteres como máximo.

   ![](assets/schema_extension_4.png)

1. Para modificar uno de los campos, marque **[!UICONTROL Edit Properties]** el botón.

   ![](assets/schema_extension_24.png)

1. En **[!UICONTROL Field definition]** la pantalla, puede definir una categoría que se utilizará para la audiencia y la segmentación, o incluso agregar una descripción.

   ![](assets/schema_extension_5.png)

1. Marque **[!UICONTROL Specify a list of authorized values]** la opción si necesita definir valores que se vayan a ofrecer al usuario (valores de enumeración).

   A continuación, haga clic y **[!UICONTROL Create element]** especifique un **[!UICONTROL Label]** y **[!UICONTROL Value]**. Añada tantos valores como sea necesario.

1. Una vez agregados los campos, marque **[!UICONTROL Add audit fields]** la casilla para incluir campos que detallen la fecha de creación, el usuario que creó el recurso, la fecha y el autor de la última modificación.
1. Marque **[!UICONTROL Add access authorization management fields]** la casilla para incluir los campos que indican quién tiene derechos de acceso a ese recurso en particular.

   Estos campos aparecen en los datos y los metadatos que se pueden mostrar una vez completada la actualización de la base de datos. Para obtener más información, consulte la [sección Actualizar la estructura](../../developing/using/updating-the-database-structure.md) de la base de datos.

1. Marque **[!UICONTROL Add automatic ID]** el campo para generar automáticamente un ID. Tenga en cuenta que las entidades existentes permanecerán vacías.
1. Para modificar la forma en que el nombre de los elementos de recursos aparecerá en las listas y los pasos de creación, marque **[!UICONTROL Personalize the resource title]** la casilla. Seleccione un campo de los que ha creado para este recurso.

   ![](assets/schema_extension_18.png)

Ahora se definen los campos de su recurso.

## Definición de claves de identificación {#defining-identification-keys}

Cada recurso debe tener al menos una clave única. Por ejemplo, puede especificar una clave para que dos productos no puedan tener el mismo ID en una tabla de compra.

1. Especifique en **[!UICONTROL Automatic primary key]** la sección el tamaño del almacenamiento si desea que se genere una clave técnica automática y gradualmente.

   ![](assets/schema_extension_6.png)

1. Utilice **[!UICONTROL Create element]** el botón para crear una clave.

   Los campos **[!UICONTROL Label]** y **[!UICONTROL ID]** los campos se completan de forma predeterminada pero se pueden editar.

   >[!NOTE]
   >
   >Recomendamos utilizar 30 caracteres como máximo.

1. Para definir los elementos que componen esta clave, haga clic **[!UICONTROL Create element]** y seleccione los campos que ha creado para este recurso.

   ![](assets/schema_extension_7.png)

   Las claves creadas se muestran en **[!UICONTROL Custom keys]** la sección.

Ahora se crean las claves de identificación para el recurso.

## Definición de índices {#defining-indexes}

Un índice puede hacer referencia a uno o varios campos de recurso. Los índices permiten que la base de datos ordene los registros para recuperarlos más fácilmente. Optimizan el rendimiento de las consultas SQL.

Se recomienda definir índices, pero no es obligatorio.

1. Utilice **[!UICONTROL Create element]** el botón para crear un índice.

   ![](assets/schema_extension_26.png)

1. Los campos **[!UICONTROL Label]** y **[!UICONTROL ID]** los campos se completan de forma predeterminada, pero puede editarlos.

   >[!NOTE]
   >
   >Recomendamos utilizar 30 caracteres como máximo.

1. Para definir los elementos que conforman este índice, seleccione los campos de los que haya creado para este recurso.

   ![](assets/schema_extension_27.png)

1. Click **[!UICONTROL Confirm]**.

Los índices que se crearon aparecen en la lista de **[!UICONTROL Index]** la sección.

## Definición de vínculos con otros recursos {#defining-links-with-other-resources}

Un vínculo detalla la asociación que una tabla tiene con otras tablas.

1. Utilice **[!UICONTROL Create element]** el botón para crear un vínculo a un recurso de destino.
1. Click **[!UICONTROL Select a target resource]**.

   ![](assets/schema_extension_28.png)

1. Los recursos se muestran en orden alfabético y se pueden filtrar por nombre. Su nombre técnico se muestra entre corchetes.

   Seleccione un elemento de la lista y haga clic **[!UICONTROL Confirm]** en.

   ![](assets/schema_extension_9.png)

1. Seleccione los **[!UICONTROL Link type]** de acuerdo con la cardinalidad. Según el tipo de cardinalidad seleccionado, el comportamiento si los registros se eliminan o se duplican pueden variar.

   Los diversos tipos de vínculos son los siguientes:

   * **[!UICONTROL 1 cardinality simple link]**: una incidencia de la tabla de origen puede tener como máximo una incidencia correspondiente de la tabla de destino.
   * **[!UICONTROL N cardinality collection link]**: una incidencia de la tabla de origen puede tener varias incidencias correspondientes de la tabla de destino, pero una incidencia de la tabla de destino puede tener como máximo una incidencia correspondiente de la tabla de origen.
   * **[!UICONTROL 0 or 1 cardinality simple link]**: una incidencia de la tabla de origen puede tener como máximo una incidencia correspondiente de la tabla de destino o ninguno. Tenga en cuenta que este tipo **[!UICONTROL Link type]** de problema puede provocar problemas de rendimiento.
   ![](assets/schema_extension_29.png)

1. En **[!UICONTROL New link]** la pantalla, **[!UICONTROL Label]** los campos y **[!UICONTROL ID]** los campos se completan de forma predeterminada, pero puede editarlos.

   >[!NOTE]
   >
   >Recomendamos utilizar 30 caracteres como máximo.

   >[!CAUTION]
   >
   >No es posible cambiar el nombre de un vínculo después de crearlo. Para cambiar el nombre de un vínculo, debe eliminarlo y crearlo de nuevo.

1. La **[!UICONTROL Category for the audience and targeting]** lista permite asignar este vínculo a una categoría que la hace más visible en la herramienta Editor de consultas.
1. Si es necesario, la **[!UICONTROL Reverse link definition]** sección le permite mostrar la etiqueta y el ID del recurso en el recurso de destino.
1. Defina el comportamiento de los registros a los que hace referencia el vínculo en **[!UICONTROL Behavior if deleted/duplicated]** la sección.

   De forma predeterminada, el registro de destino se eliminará una vez que el vínculo deje de hacer referencia a él.

   ![](assets/schema_extension_16.png)

1. En **[!UICONTROL Join definition]** la sección, se selecciona la **[!UICONTROL Use the primary keys to make the join]** opción predeterminada, pero puede elegir entre dos opciones:

   * **[!UICONTROL Use the primary key to make the join]**: Esta definición de unión permite utilizar la clave principal de perfiles para reconciliarla con la clave principal de las compras.
   * **[!UICONTROL Define specific join conditions]**: Esta definición de unión permite seleccionar manualmente los campos que se unirán a ambos recursos. Tenga en cuenta que si los datos no están correctamente configurados, el **registro de compra** no estará visible.
   ![](assets/schema_extension_17.png)

Los vínculos creados se muestran en la lista de **[!UICONTROL Links]** la sección.

**Ejemplo: Vinculación de un recurso creado con el recurso'Perfiles '**

En este ejemplo, queremos vincular una nueva **compra de recursos** con el recurso personalizado **Perfiles** :

1. Cree su nuevo **recurso de compra** .
1. Para vincularlo con el recurso personalizado **Perfiles** , despliegue la **[!UICONTROL Links]** sección en **[!UICONTROL Data structure]** la ficha y haga clic **[!UICONTROL Create element]** en.
1. Seleccione el recurso de destino aquí **[!UICONTROL Profiles (profile)]**.
1. En este ejemplo, mantenga seleccionado el tipo **[!UICONTROL 1 cardinality simple link]** de vínculo predeterminado.

   ![](assets/custom_resource_link_to_profile_2.png)

1. Elija una definición de unión, mantenga el valor predeterminado **[!UICONTROL Use the primary key to make the join]**.

   ![](assets/custom_resource_link_to_profile_3.png)

1. Si es necesario, puede definir una pantalla de detalles para poder editar **la compra** y vincularla a un perfil.

   Despliegue la **[!UICONTROL Detail screen configuration]** sección y marque la **[!UICONTROL Define a detail screen]** opción para configurar la pantalla que corresponde a cada elemento del recurso. Si no marca esta casilla, la vista de detalles de los elementos de este recurso no será accesible.

1. Click **[!UICONTROL Create element]**.
1. Seleccione el recurso vinculado y haga clic **[!UICONTROL Add]** en.

   El nuevo recurso estará disponible en el menú avanzado seleccionando **[!UICONTROL Client data]** &gt; **[!UICONTROL Purchase]**.

   ![](assets/custom_resource_link_to_profile_4.png)

1. Una vez realizada la configuración, haga clic **[!UICONTROL Confirm]** en.

   Ahora puede publicar su nuevo recurso.

Al agregar este vínculo, se **agrega una** ficha Compra a la pantalla de detalles de perfiles desde **[!UICONTROL Profiles & audiences]** el **[!UICONTROL Profiles]** menú &gt;. Tenga en cuenta que esto es específico del **[!UICONTROL Profile]** recurso.

![](assets/custom_resource_link_to_profile.png)

## Definición de la extensión de registros de envío {#defining-sending-logs-extension}

La extensión de registro que envía le permite:

* para ampliar las capacidades de informes dinámicos **agregando campos personalizados de perfil**
* para ampliar los datos de registro con **código de segmento y datos de perfil**

**Extender con un código de segmento**

El usuario puede ampliar los registros con el código de segmento procedente del motor de flujo de trabajo.

El código de segmento debe definirse en el flujo de trabajo.

Para activar esta extensión, marque la opción **[!UICONTROL Add segment code]**.

![](assets/sendinglogsextension_1.png)

Para obtener más información sobre el código de segmento, consulte la sección [Segmentación](../../automating/using/segmentation.md) .

**Ampliar con un campo de perfil**

>[!NOTE]
>
>El administrador debería haber ampliado el recurso de perfil con un campo personalizado.

![](assets/sendinglogsextension_2.png)

Haga clic y **[!UICONTROL Add field]** seleccione cualquier campo personalizado del recurso de perfil.

Para generar una nueva subdimensión vinculada a la dimensión Perfil, marque **[!UICONTROL Add this field in Dynamic reporting as a new dimension]** la opción.

![](assets/sendinglogsextension_3.png)

En Informes dinámicos, puede arrastrar y soltar la dimensión del campo personalizado en una tabla improvisada.

Para obtener más información sobre Informes dinámicos, consulte [la lista de componentes](../../reporting/using/list-of-components-.md).

>[!CAUTION]
>
>El número de campos enviados a Informes dinámicos está limitado a 20.

## Edición de propiedades de recursos {#editing-resource-properties}

En la pantalla de recursos personalizados, el **[!UICONTROL Summary]** panel indica el estado del recurso recién creado. Puede administrar su acceso y sus propiedades generales.

![](assets/schema_extension_3.png)

1. Haga clic en **[!UICONTROL Edit properties]** el botón para agregar una descripción.

   ![](assets/schema_extension_30.png)

1. Si es necesario, modifique la etiqueta y el ID del recurso.

   >[!NOTE]
   >
   >Recomendamos utilizar 30 caracteres como máximo.

1. Si necesita restringir el acceso a este recurso a ciertas unidades de organización, indíquelas aquí. Solo los usuarios de las unidades autorizadas podrán trabajar con este recurso en la aplicación.
1. Guarde las modificaciones.

Se guardarán las modificaciones. Debe publicar el recurso de nuevo para aplicarlo.

## Generación de un ID exclusivo para perfiles y recursos personalizados {#generating-a-unique-id-for-profiles-and-custom-resources}

De forma predeterminada, los perfiles y recursos personalizados no tienen ID de empresa cuando se crean. Puede habilitar una opción que genere automáticamente un ID único cuando se crean elementos. Este ID se puede utilizar para:

* Identifique los registros exportados fácilmente en una herramienta externa.
* Concilie los registros al importar datos actualizados procesados en otra aplicación.

Solo se puede habilitar para perfiles y recursos personalizados.

1. Cree una extensión al recurso de perfiles o cree un nuevo recurso.
1. En la definición de estructura de datos, marque la **[!UICONTROL Add automatic ID field]** opción, debajo **[!UICONTROL Fields]** de la sección.
1. Guarde y publique la modificación realizada en el recurso. Si desea que este mecanismo se aplique a los elementos creados mediante la API, marque la opción para ampliar la API.

**[!UICONTROL ACS ID]** El campo ya está disponible y se llena automáticamente cuando se crean nuevos elementos manualmente, desde la API o insertados desde un flujo de trabajo de importación. El campo ID de ACS es un campo UUID y se indexa.

Al exportar perfiles o recursos personalizados, ahora puede agregar **[!UICONTROL ACS ID]** la columna si se ha habilitado para ese recurso. Puede reutilizar este ID en las herramientas externas para identificar registros.

![](assets/export_id_field.png)

Al volver a importar los datos procesados/actualizados en otra aplicación (por ejemplo, CRM), puede conciliarlos fácilmente con este ID exclusivo.

>[!NOTE]
>
>El **[!UICONTROL ACS ID]** campo no se actualiza para los perfiles o elementos creados antes de activar la opción. Solo los registros nuevos tendrán un ID ACS. Este campo se encuentra en modo de solo lectura. No se puede modificar.

