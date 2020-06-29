---
title: Envío de un correo electrónico con campos enriquecidos
description: El ejemplo siguiente muestra cómo enviar un correo electrónico con datos adicionales recuperados de un archivo externo a través de la actividad de cargar archivo.
page-status-flag: never-activated
uuid: 69af12cc-6f82-4977-9f53-aa7bc26f5d7e
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: data-management-activities
discoiquuid: 584ff893-9b1b-46c9-9628-714ab349ab88
context-tags: fileImport,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c3911232a3cce00c2b9a2e619f090a7520382dde
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 0%

---


# Envío de un correo electrónico con campos enriquecidos {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

La actividad del archivo de carga también permite enviar un correo electrónico enriquecido con datos adicionales de un archivo externo en el mismo flujo de trabajo.

El ejemplo siguiente muestra cómo enviar un correo electrónico con datos adicionales recuperados de un archivo externo a través de la actividad de cargar archivo. En este ejemplo, el archivo externo contiene una lista de perfiles con su número de cuenta asociado. Desea importar estos datos para enviar un correo electrónico a cada perfil con su número de cuenta.

![](assets/load_file_workflow_ex2.png)

Para generar el flujo de trabajo, siga estos pasos:

1. Arrastre y suelte una actividad de [Consulta](../../automating/using/query.md) en el flujo de trabajo y ábrala para definir el destinatario principal.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Arrastre y suelte una actividad [Cargar archivo](../../automating/using/load-file.md) para asignar algunos datos a un perfil. En este ejemplo, cargue un archivo que contenga los números de cuenta correspondientes a algunos perfiles de la base de datos.

   ![](assets/load_file_activity.png)

1. Arrastre y suelte una actividad de [Enriquecimiento](../../automating/using/enrichment.md) en el flujo de trabajo y vincule el archivo de carga y las actividades de consulta.

1. En la **[!UICONTROL Advanced relations]** ficha de la actividad enriquecimiento, seleccione los campos **[!UICONTROL 0 or 1 cardinality simple link]** y defina los campos que se utilizarán para la reconciliación. Aquí utilizamos el apellido para reconciliar los datos con los perfiles de la base de datos.

   ![](assets/load_file_enrichment_relation.png)

1. En la **[!UICONTROL Additional data]** ficha, seleccione los elementos que desee utilizar en el correo electrónico. Aquí seleccione Número de cuenta (columna del archivo que recuperó a través de la actividad del archivo de carga).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   For more on this, see the [Enrichment](../../automating/using/enrichment.md) section.

1. Arrastre y suelte una actividad de [segmentación](../../automating/using/segmentation.md) en el flujo de trabajo y ábrala para refinar el destinatario principal.

   ![](assets/load_file_segmentation.png)

   For more on this, see the [Segmentation](../../automating/using/segmentation.md) section.

1. Arrastre y suelte una actividad [de envío](../../automating/using/email-delivery.md) de correo electrónico en el flujo de trabajo y ábrala.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Añada un campo de personalización y seleccione los datos adicionales definidos en la actividad de enriquecimiento (aquí Número de cuenta) del **[!UICONTROL Additional data (targetData)]** nodo. Esto permite recuperar dinámicamente el número de cuenta de cada perfil del contenido del correo electrónico.

   ![](assets/load_file_perso_field.png)

1. Guarde el correo electrónico y el inicio del flujo de trabajo.

El correo electrónico se envía al destinatario. Cada perfil recibe el correo electrónico con su correspondiente número de cuenta.

![](assets/load_file_email.png)
