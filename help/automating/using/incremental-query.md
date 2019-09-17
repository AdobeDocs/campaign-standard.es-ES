---
title: Consulta incremental
seo-title: Consulta incremental
description: Consulta incremental
seo-description: La actividad de consulta incremental permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign.
page-status-flag: nunca activado
uuid: 73b42422-e815-43ef-84c0-97c4433ccc98
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: segmentación-actividades
discoiquuid: 80961e73-42ec-463a-8496-cff69fab0475
context-tags: incremental,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ea825afe573959d95d0f7f3f6e79dd38ac5a678a

---


# Consulta incremental{#incremental-query}

## Descripción {#description}

![](assets/incremental.png)

La **[!UICONTROL Incremental query]** actividad permite filtrar y extraer una población de elementos de la base de datos de Adobe Campaign. Cada vez que se ejecuta esta actividad, se excluyen los resultados de las ejecuciones anteriores. Esto le permite segmentar solo elementos nuevos.

Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso.

La actividad utiliza la herramienta de edición de consultas. Esta herramienta se detalla en una sección [](../../automating/using/editing-queries.md#about-query-editor)dedicada.

## Contexto de uso {#context-of-use}

Un **[!UICONTROL Incremental query]** debe estar vinculado a un **[!UICONTROL Scheduler]** para definir la frecuencia de ejecución del flujo de trabajo y, por lo tanto, la consulta.

La **[!UICONTROL Processed data]** ficha, que es específica de esta actividad, permite ver los resultados de las ejecuciones anteriores de la actividad, si es necesario.

La **[!UICONTROL Incremental query]** actividad se puede utilizar para varios tipos de usos:

* Segmentación de individuos para definir el destino de un mensaje, una audiencia, etc.
* Exportando datos.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Incremental query]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Si desea ejecutar una consulta en un recurso que no sea el recurso de perfil, vaya a la ficha de la actividad **[!UICONTROL Properties]** y seleccione un **[!UICONTROL Resource]** y un **[!UICONTROL Targeting dimension]**.

   El **[!UICONTROL Resource]** permite refinar los filtros mostrados en la paleta, mientras que el **[!UICONTROL Targeting dimension]**, contextual con respecto al recurso seleccionado, corresponde al tipo de población que desea obtener (perfiles identificados, entregas, datos vinculados al recurso seleccionado, etc.).

1. En la **[!UICONTROL Target]** ficha, ejecute la consulta definiendo y combinando reglas.
1. En la **[!UICONTROL Processed data]** ficha, seleccione el modo incremental que desee utilizar para las próximas ejecuciones del flujo de trabajo:

   * **[!UICONTROL Use the exclusion of the results of previous executions]**:: se excluyen los resultados de ejecuciones anteriores para cada nueva ejecución.
   * **[!UICONTROL Use a date field]**:: las siguientes ejecuciones solo tienen en cuenta los resultados que tienen el campo de fecha seleccionado mayor o igual a la fecha de la última ejecución de la **[!UICONTROL Incremental query]** actividad. Puede seleccionar cualquier campo de fecha que pertenezca al recurso seleccionado en la **[!UICONTROL Properties]** ficha. Este modo ofrece un mejor rendimiento al consultar recursos de gran tamaño, como datos de registro.

      Después de la primera ejecución del flujo de trabajo, puede ver en esta ficha la última fecha de ejecución que se utilizará para la siguiente ejecución. Se actualiza automáticamente cada vez que se ejecuta el flujo de trabajo. Todavía tiene la posibilidad de anular este valor introduciendo manualmente uno nuevo para que se ajuste a sus necesidades.
   >[!NOTE]
   >
   >El **[!UICONTROL Use a date field]** modo permite una mayor flexibilidad en función del campo de fecha seleccionado. Por ejemplo, si el campo seleccionado corresponde a una fecha de modificación, el modo de campo de fecha le permitirá recuperar datos que se actualizaron recientemente, mientras que el otro modo excluirá simplemente las grabaciones que ya estaban segmentadas en una ejecución anterior, aunque se hayan modificado desde la última ejecución del flujo de trabajo.

   ![](assets/incremental_query_usedatefield.png)

1. Puede definir **[!UICONTROL Additional data]** para la población objetivo mediante una ficha dedicada. Estos datos se almacenan en columnas adicionales y solo se pueden utilizar para el flujo de trabajo en curso. En particular, puede agregar datos de las tablas de base de datos de Adobe Campaign vinculadas a la dimensión de objetivo de la consulta. Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data) .
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Enriquecimiento de datos {#enriching-data}

Al igual que para una consulta, puede enriquecer los datos de una **[!UICONTROL Incremental query]**. Consulte la sección [Enriquecimiento de datos](../../automating/using/query.md#enriching-data) .

## Ejemplo: consulta incremental en suscriptores de un servicio {#example--incremental-query-on-subscribers-to-a-service}

En el siguiente ejemplo se muestra la configuración de una **[!UICONTROL Incremental query]** actividad que filtra los perfiles de la base de datos de Adobe Campaign suscritos al servicio **de newsletter** en ejecución para enviarles un correo electrónico de bienvenida que contenga un código de promoción.

El flujo de trabajo se compone de los siguientes elementos:

![](assets/incremental_query_example1.png)

* Una **[!UICONTROL Scheduler]** actividad para ejecutar el flujo de trabajo todos los lunes a las 6 de la mañana.

   ![](assets/incremental_query_example2.png)

* Una **[!UICONTROL Incremental query]** actividad, que se dirige a todos los suscriptores actuales durante la primera ejecución y, a continuación, solo a los nuevos suscriptores de esa semana durante las siguientes ejecuciones.

   ![](assets/incremental_query_example3.png)

* Una **[!UICONTROL Email delivery]** actividad. El flujo de trabajo se ejecuta una vez por semana, pero puede agregar los correos electrónicos enviados y los resultados por mes, por ejemplo para generar informes a lo largo de un período de un mes entero y no sólo una semana.

   Para ello, elija crear un **[!UICONTROL Recurring email]** aquí que reagrupe los correos electrónicos y los resultados **[!UICONTROL By month]**.

   Defina el contenido del correo electrónico e inserte el código de promoción de bienvenida.

   Para obtener más información sobre esto, consulte las secciones Envío [de](../../automating/using/email-delivery.md) correo electrónico y [Definición de contenido](../../designing/using/personalization.md) de correo electrónico.

A continuación, inicie la ejecución del flujo de trabajo. Cada semana los nuevos suscriptores recibirán el correo electrónico de bienvenida con el código de promoción.

## Ejemplo: consulta incremental en los registros de entrega {#example--incremental-query-on-delivery-logs}

Puede utilizar una **[!UICONTROL Incremental query]** actividad para exportar con regularidad nuevos registros en archivos. Puede resultar útil, por ejemplo, si desea utilizar los datos de registro en informes externos o en herramientas de BI.

Encontrará un ejemplo completo en la sección [Exportar registros](../../automating/using/exporting-logs.md) .
