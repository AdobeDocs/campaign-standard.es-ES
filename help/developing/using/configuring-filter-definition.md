---
title: Configuración de la definición del filtro
description: Descubrir la función de filtro para administrar grandes conjuntos de datos.
page-status-flag: never-activated
uuid: c9db95fe-e9aa-40f8-9c0a-e74bb21ac14b
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: developing
content-type: reference
topic-tags: adding-or-extending-a-resource
discoiquuid: 993ab2bd-e05f-468e-9ef8-a603761247f8
context-tags: cusResource,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cabe064632c9c2e3de93bc1cff6fa217b4fdf3e6
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 1%

---


# Configuración de la definición del filtro{#configuring-filter-definition}

En la **[!UICONTROL Filter definition]** ficha, puede crear filtros avanzados a los que los usuarios pueden acceder directamente al crear consultas complejas, como cuando se define una audiencia.

Este paso no es obligatorio, ya que aún podrá rellenar el recurso y acceder a sus datos a través de flujos de trabajo, audiencias y REST API.

![](assets/custom_resource_filter-definition.png)

Estos filtros se utilizan en el editor de consultas en forma de reglas preconfiguradas. Permiten limitar el número de pasos necesarios para obtener la configuración deseada, lo que puede resultar especialmente beneficioso para las segmentaciones repetitivas.

Por ejemplo, puede crear un filtro que permita seleccionar todas las transacciones buenas que no sean una determinada cantidad en los últimos tres meses.

Para ello, debe ampliar el recurso y definir un filtro que vincule a una tabla de transacciones (que ha creado anteriormente) con una regla que indique que el precio de transacción debe ser bueno o igual a un parámetro determinado y que la fecha de transacción debe estar dentro de un rango correspondiente a los últimos tres meses. **[!UICONTROL Profiles]**

1. Asegúrese de crear y publicar una tabla de transacciones. See [Creating or extending the resource](../../developing/using/creating-or-extending-the-resource.md).

   >[!NOTE]
   >
   >Este procedimiento utiliza el ejemplo de una tabla de transacciones personalizada. Para su caso, ajústelo a sus necesidades comerciales.

1. Antes de definir un filtro relacionado con la tabla de transacciones del **[!UICONTROL Profiles]** recurso, asegúrese de definir el vínculo a esta tabla y publicar los cambios. Consulte [Definición de vínculos con otros recursos](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources) y [Actualización de la estructura](../../developing/using/updating-the-database-structure.md)de la base de datos.
1. En la **[!UICONTROL Definition]** ficha de la pantalla de definición del nuevo filtro, seleccione la tabla de transacciones.

   ![](assets/custom_resource_filter-definition_example-empty.png)

1. En la **[!UICONTROL Add a rule - Profiles/Transactions]** ventana, arrastre y suelte la tabla de transacciones en el espacio de trabajo. En la siguiente ventana que se muestra, seleccione el campo que desee utilizar.

   ![](assets/custom_resource_filter-definition_example-field.png)

1. En la parte **[!UICONTROL Optional parameter settings]** de la **[!UICONTROL Add a rule - Transactions]** ventana, marque la **[!UICONTROL Switch to parameters]** casilla.

   En el **[!UICONTROL Filter conditions]**, seleccione el **[!UICONTROL Greater than or equal to]** operador. En el **[!UICONTROL Parameters]** campo, introduzca un nombre y haga clic en el signo más para crear el nuevo parámetro.

   ![](assets/custom_resource_filter-definition_example-parameter.png)

1. Confirme los cambios. Esta definición corresponde a un campo configurable que el usuario debe rellenar más tarde para ejecutar la consulta.

   ![](assets/custom_resource_filter-definition_ex_edit-rule.png)

1. Combine esta regla con otra regla que especifique que la fecha de transacción debe estar dentro de un intervalo correspondiente a los últimos tres meses.

   ![](assets/custom_resource_filter-definition_example.png)

1. Elija la categoría en la que se mostrará el filtro.

   ![](assets/custom_resource_filter-definition_category.png)

1. En la **[!UICONTROL Parameters]** ficha de la pantalla de definición del filtro, modifique la descripción y la etiqueta para indicar claramente el asunto del filtro a los usuarios. Esta información aparecerá en el editor de consultas.

   ![](assets/custom_resource_filter-definition_parameters.png)

   Si define varios campos configurables, puede modificar el orden en que aparecen en la interfaz.

1. Guarde los cambios y publique los recursos. Para obtener más información sobre esto, consulte la sección [Actualización de la estructura](../../developing/using/updating-the-database-structure.md) de la base de datos.

Una vez publicada la extensión del **[!UICONTROL Profiles]** recurso, los usuarios verán este filtro en la ficha Métodos abreviados de la interfaz del editor [de](../../automating/using/editing-queries.md) consultas.

Esto permitirá al usuario definir fácilmente su audiencia al crear un correo electrónico para enviarlo a todos los clientes que gastaron más de una determinada cantidad en los últimos tres meses.

![](assets/custom_resource_filter-definition_email-audience.png)

En lugar de configurarlo ellos mismos, simplemente tienen que introducir la cantidad deseada en el cuadro de diálogo que aparece.

![](assets/custom_resource_filter-definition_email-audience_filter.png)

Una vez configurado el filtro, puede utilizarlo desde las API de Campaign Standard mediante esta sintaxis:

`GET https://mc.adobe.io/<ORGANIZATION>/campaign/profileAndServicesExt/<resourceName>/by<customFilterName>?<customFilterparam>=<customFilterValue>`

Para obtener más información sobre esto, consulte la documentación [de las API de](../../api/using/filtering.md#custom-filters)Campaign Standard.
