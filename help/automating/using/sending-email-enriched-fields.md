---
solution: Campaign Standard
product: campaign
title: Envío de un correo electrónico con campos enriquecidos
description: El ejemplo siguiente muestra cómo enviar un correo electrónico con datos adicionales recuperados de un archivo externo a través de la actividad de carga de archivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 74%

---


# Envío de un correo electrónico con campos enriquecidos {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

La actividad de carga de archivo también permite enviar un correo electrónico enriquecido con datos adicionales de un archivo externo en el mismo flujo de trabajo.

El ejemplo siguiente muestra cómo enviar un correo electrónico con datos adicionales recuperados de un archivo externo a través de la actividad de carga de archivo. En este ejemplo, el archivo externo contiene una lista de perfiles con su número de cuenta asociado. Quiere importar estos datos para enviar un correo electrónico a cada perfil con su número de cuenta.

![](assets/load_file_workflow_ex2.png)

Para crear el flujo de trabajo, siga estos pasos:

1. Arrastre y suelte una actividad [Query](../../automating/using/query.md) en el flujo de trabajo y ábrala para definir el destinatario principal.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Arrastre y suelte una actividad [Load file](../../automating/using/load-file.md) para asignar algunos datos a un perfil. En este ejemplo, cargue un archivo que contenga los números de cuenta correspondientes a algunos perfiles de la base de datos.

   ![](assets/load_file_activity.png)

1. Arrastre y suelte una actividad [Enrichment](../../automating/using/enrichment.md) en el flujo de trabajo y vincule las actividades de carga de archivo y consulta.

1. En la pestaña **[!UICONTROL Advanced relations]** de la actividad enriquecimiento, seleccione **[!UICONTROL 0 or 1 cardinality simple link]** y defina los campos que se utilizarán para la reconciliación. Aquí utilizamos el apellido para reconciliar los datos con los perfiles de la base de datos.

   ![](assets/load_file_enrichment_relation.png)

1. En la pestaña **[!UICONTROL Additional data]**, seleccione los elementos que desee utilizar en el correo electrónico. Aquí seleccione Número de cuenta (columna del archivo que recuperó a través de la actividad de carga de archivo).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Para obtener más información, consulte la sección [Enriquecimiento](../../automating/using/enrichment.md).

1. Arrastre y suelte una actividad [Segmentation](../../automating/using/segmentation.md) en el flujo de trabajo y ábrala para restringir el destinatario principal.

   ![](assets/load_file_segmentation.png)

   Para obtener más información, consulte la sección [Segmentación](../../automating/using/segmentation.md).

1. Arrastre y suelte una actividad [Email delivery](../../automating/using/email-delivery.md) en el flujo de trabajo y ábrala.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Añada un campo de personalización y seleccione los datos adicionales definidos en la actividad de enriquecimiento (aquí Número de cuenta) del nodo **[!UICONTROL Additional data (targetData)]**. Esto permite recuperar dinámicamente el número de cuenta de cada perfil del contenido del correo electrónico.

   ![](assets/load_file_perso_field.png)

1. Guarde el correo electrónico e inicie el flujo de trabajo.

El correo electrónico se manda a los destinatarios. Cada perfil recibe el correo electrónico con su correspondiente número de cuenta.

![](assets/load_file_email.png)
