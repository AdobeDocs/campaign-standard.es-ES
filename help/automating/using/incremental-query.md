---
title: Consulta incremental
seo-title: Consulta incremental
description: Consulta incremental
seo-description: La actividad de consulta incremental permite filtrar y extraer una población de elementos desde la base de datos de Adobe Campaign.
page-status-flag: no activado nunca
uuid: 73 b 42422-e 815-43 ef -84 c 0-97 c 4433 ccc 98
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: segmentación de actividades
discoiquuid: 80961 e 73-42 ec -463 a -8496-cff 69 fab 0475
context-tags: incremental, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3e2081fc3377fe4edbdf3fb8c4765a9acda6d79e

---


# Incremental query{#incremental-query}

## Description {#description}

![](assets/incremental.png)

The **[!UICONTROL Incremental query]** activity allows you to filter and extract a population of elements from the Adobe Campaign database. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite segmentar solo los nuevos elementos.

You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso.

La actividad utiliza la herramienta Editor de consultas. This tool is detailed in a [dedicated section](../../automating/using/editing-queries.md#about-query-editor).

## Context of use {#context-of-use}

An **[!UICONTROL Incremental query]** has to be linked to a **[!UICONTROL Scheduler]** in order to define the execution frequency of the workflow, and therefore the query.

The **[!UICONTROL Processed data]** tab, which is specific to this activity, allows you to view any results of the activity's previous executions, if required.

The **[!UICONTROL Incremental query]** activity can be used for various types of uses:

* Segmentar a personas para definir el objetivo de un mensaje, audiencia, etc.
* Exportación de datos.

## Configuration {#configuration}

1. Drag and drop an **[!UICONTROL Incremental query]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. If you would like to run a query on a resource other than the profile resource, go to the activity's **[!UICONTROL Properties]** tab and select a **[!UICONTROL Resource]** and a **[!UICONTROL Targeting dimension]**.

   The **[!UICONTROL Resource]** allows you to refine the filters displayed in the palette whereas the **[!UICONTROL Targeting dimension]**, contextual with regard to the resource selected, corresponds to the type of population that you would like to obtain (identified profiles, deliveries, data linked to the selected resource, etc.).

1. In the **[!UICONTROL Target]** tab, run your query by defining and combining rules.
1. In the **[!UICONTROL Processed data]** tab, choose the incremental mode you want to use for the next executions of the workflow:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**: se excluyen los resultados de ejecuciones anteriores para cada nueva ejecución.
   * **[!UICONTROL Use a date field]**: Las ejecuciones siguientes solo tienen en cuenta los resultados que tienen el campo de fecha seleccionado mayor o igual a la última fecha de ejecución de **[!UICONTROL Incremental query]** la actividad. You can select any date field pertaining to the resource selected in the **[!UICONTROL Properties]** tab. Este modo tiene un mejor rendimiento al consultar recursos grandes como datos de registro.

      Después de la primera ejecución del flujo de trabajo, puede ver en esta ficha la última fecha de ejecución que se utilizará para la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Aún tiene la posibilidad de omitir este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.
   >[!NOTE]
   >
   >**[!UICONTROL Use a date field]** El modo permite mayor flexibilidad según el campo de fecha seleccionado. Por ejemplo, si el campo seleccionado corresponde a una fecha de modificación, el modo de campo de fecha le permitirá recuperar datos recientemente actualizados, mientras que el otro modo simplemente excluirá grabaciones que ya estaban dirigidas en una ejecución anterior, incluso si se han modificado desde la última ejecución del flujo de trabajo.

   ![](assets/incremental_query_usedatefield.png)

1. You can define **[!UICONTROL Additional data]** for the targeted population via a dedicated tab. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso. En concreto, puede agregar datos de las tablas de base de datos de Adobe Campaign vinculadas a la dimensión de segmentación de la consulta. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Enriching data {#enriching-data}

Just as for a query, you can enrich the data from an **[!UICONTROL Incremental query]**. Consult the [Enriching data](../../automating/using/query.md#enriching-data) section.

## Example: incremental query on subscribers to a service {#example--incremental-query-on-subscribers-to-a-service}

The following example shows the configuration of an **[!UICONTROL Incremental query]** activity which filters the profiles in the Adobe Campaign database that are subscribed to the **Running Newsletter** service, to send them a welcome email containing a promo code.

El flujo de trabajo está conformado por los siguientes elementos:

![](assets/incremental_query_example1.png)

* **[!UICONTROL Scheduler]** Actividad, para ejecutar el flujo de trabajo todos los lunes a las 6 am.

   ![](assets/incremental_query_example2.png)

* **[!UICONTROL Incremental query]** Una actividad, dirigida a todos los suscriptores actuales durante la primera ejecución, y luego solo a los nuevos suscriptores de esa semana durante las siguientes ejecuciones.

   ![](assets/incremental_query_example3.png)

* An **[!UICONTROL Email delivery]** activity. El flujo de trabajo se ejecuta una vez a la semana, pero puede agregar los mensajes de correo electrónico enviados y los resultados por mes, por ejemplo para generar informes durante un mes completo y no solo una semana.

   To do this, choose to create a **[!UICONTROL Recurring email]** here regrouping the emails and the results **[!UICONTROL By month]**.

   Defina el contenido del correo electrónico e inserte el código de promoción de bienvenida.

   For more on this, refer to the [Email delivery](../../automating/using/email-delivery.md) and [Defining email content](../../designing/using/about-personalization.md) sections.

A continuación, inicie la ejecución del flujo de trabajo. Cada semana, los nuevos suscriptores recibirán el correo electrónico de bienvenida con el código de promoción.

## Example: incremental query on delivery logs {#example--incremental-query-on-delivery-logs}

You can use an **[!UICONTROL Incremental query]** activity to regularly export new logs in files. Puede resultar útil, por ejemplo, si desea utilizar los datos de registro en informes externos o en las herramientas BI.

A complete example is available in the [Exporting logs](../../automating/using/exporting-logs.md) section.
