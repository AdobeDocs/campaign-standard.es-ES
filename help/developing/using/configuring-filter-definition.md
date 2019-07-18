---
title: Configuración de la definición del filtro
seo-title: Configuración de la definición del filtro
description: Configuración de la definición del filtro
seo-description: Descubrir la función de filtro para administrar un conjunto de datos grande.
page-status-flag: no activado nunca
uuid: c 9 db 95 fe-e 9 aa -40 f 8-9 c 0 a-e 74 bb 21 ac 14 b
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: desarrollar
content-type: reference
topic-tags: adición-ampliación-a-recurso
discoiquuid: 993 ab 2 bd-e 05 f -468 e -9 ef 8-a 603761247 f 8
context-tags: Cusresource, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 806dc4736ffb395a0eea102090c688102478aaca

---


# Configuring filter definition{#configuring-filter-definition}

In the **[!UICONTROL Filter definition]** tab, you can create advanced filters that users can directly access when creating complex queries, such as when defining an audience.

Este paso no es obligatorio porque aún podrá rellenar el recurso y acceder a sus datos a través de flujos de trabajo, audiencias y API de REST.

![](assets/custom_resource_filter-definition.png)

Estos filtros se utilizan en el editor de consultas en forma de reglas preconfiguradas. Permiten limitar la cantidad de pasos necesarios para obtener la configuración deseada, lo cual puede resultar particularmente beneficioso para las segmentaciones repetitivas.

Por ejemplo, puede crear un filtro que permita seleccionar todas las transacciones mayores que una cierta cantidad dentro de los últimos tres meses.

To do this, you need to extend the **[!UICONTROL Profiles]** resource and define a filter linking to a transaction table (that you have previously created) with a rule indicating that the transaction price must be greater than or equal to a given parameter and that the transaction date must fall within a range corresponding to the last three months.

1. Asegúrese de crear y publicar una tabla de transacciones. See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Este procedimiento utiliza el ejemplo de una tabla de transacciones personalizada. Para su caso, ajústelo a sus necesidades comerciales.

1. Before defining a filter related to the transaction table in the **[!UICONTROL Profiles]** resource, make sure you define the link to this table and publish your changes. See [Defining links with other resources](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) and [Updating the database structure](../../developing/using/updating-the-database-structure.md).
1. In the **[!UICONTROL Definition]** tab of your new filter's definition screen, select the transaction table.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. In the **[!UICONTROL Add a rule - Profiles/Transactions]** window, drag and drop the transaction table into the workspace. En la siguiente ventana que se muestra, seleccione el campo que desee utilizar.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. In the **[!UICONTROL Optional parameter settings]** of the **[!UICONTROL Add a rule - Transactions]** window, check the **[!UICONTROL Switch to parameters]** box.

   In the **[!UICONTROL Filter conditions]**, select the **[!UICONTROL Greater than or equal to]** operator. In the **[!UICONTROL Parameters]** field, enter a name and click the plus sign to create the new parameter.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Confirme los cambios. Esta definición corresponde a un campo configurable que el usuario debe rellenar más tarde para ejecutar la consulta.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combine esta regla con otra regla especifique que la fecha de transacción debe estar dentro de un intervalo correspondiente a los últimos tres meses.

   ![](assets/custom_resource_filter-definition_example.png)

1. Elija la categoría en la que se mostrará el filtro.

   ![](assets/custom_resource_filter-definition_category.png)

1. In the **[!UICONTROL Parameters]** tab of the filter definition screen, modify the description and the label to clearly indicate the subject of your filter to the users. Esta información aparecerá en el editor de consultas.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Si define varios campos configurables, puede modificar el orden en que aparecen en la interfaz.

1. Guarde los cambios y publique los recursos. For more on this, refer to the [Updating the database structure](../../developing/using/updating-the-database-structure.md) section.

Once the **[!UICONTROL Profiles]** resource extension is published, the users will see this filter under the shortcuts tab in the [query editor](../../automating/using/editing-queries.md) interface.

Esto permitirá al usuario definir fácilmente a la audiencia al crear un correo electrónico para enviarlo a todos los clientes que gastaron más de una cierta cantidad en los últimos tres meses.

![](assets/custom_resource_filter-definition_email-audience.png)

En lugar de configurarlos ellos mismos, simplemente tienen que introducir la cantidad deseada en el cuadro de diálogo que aparece.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

