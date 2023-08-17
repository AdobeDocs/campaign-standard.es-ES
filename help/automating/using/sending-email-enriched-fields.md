---
title: Envío de un correo electrónico con campos enriquecidos
description: El ejemplo siguiente muestra cómo enviar un correo electrónico con datos adicionales recuperados de un archivo externo a través de la actividad de carga de archivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: fileImport,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 5ca7571d-d4d2-4b59-86d4-4f1f3a620b54
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 75%

---

# Envío de un correo electrónico con campos enriquecidos {#sending-email-enriched-fields}

<!--A new example showing how to send an email containing additional data retrieved from a load file activity has been added. [Read more](example-2-email-with-enriched-fields)-->

La actividad de carga de archivo también permite enviar un correo electrónico enriquecido con datos adicionales de un archivo externo en el mismo flujo de trabajo.

El ejemplo siguiente muestra cómo enviar un correo electrónico con datos adicionales recuperados de un archivo externo a través de la actividad de carga de archivo. En este ejemplo, el archivo externo contiene una lista de perfiles con su número de cuenta asociado. Quiere importar estos datos para enviar un correo electrónico a cada perfil con su número de cuenta.

![](assets/load_file_workflow_ex2.png)

Para crear el flujo de trabajo, siga estos pasos:

1. Arrastrar y soltar una [Consulta](../../automating/using/query.md) en el flujo de trabajo y ábralo para definir el destinatario principal.

   <!--The Query activity is presented in the [Query](../../automating/using/query.md) section.-->

1. Arrastrar y soltar una [Cargar archivo](../../automating/using/load-file.md) actividad para asignar algunos datos a un perfil. En este ejemplo, cargue un archivo que contenga los números de cuenta correspondientes a algunos perfiles de la base de datos.

   ![](assets/load_file_activity.png)

1. Arrastre y suelte un [Enriquecimiento](../../automating/using/enrichment.md) en el flujo de trabajo y vincule la carga de archivo y las actividades de consulta.

1. En la pestaña **[!UICONTROL Advanced relations]** de la actividad de enriquecimiento, seleccione **[!UICONTROL 0 or 1 cardinality simple link]** y defina los campos que se utilizarán para la reconciliación. Aquí utilizamos el apellido para reconciliar los datos con los perfiles de la base de datos.

   ![](assets/load_file_enrichment_relation.png)

1. En la pestaña **[!UICONTROL Additional data]**, seleccione los elementos que desee utilizar en el correo electrónico. Aquí seleccione Número de cuenta (columna del archivo que recuperó a través de la actividad de carga de archivo).

   ![](assets/load_file_enrichment_select_element.png)

   <!--![](assets/load_file_enrichment_additional_data.png)-->

   Para obtener más información, consulte la sección [Enriquecimiento](../../automating/using/enrichment.md).

1. Arrastrar y soltar una [Segmentación](../../automating/using/segmentation.md) en el flujo de trabajo y ábralo para restringir el destinatario principal.

   ![](assets/load_file_segmentation.png)

   Para obtener más información, consulte la sección [Segmentación](../../automating/using/segmentation.md).

1. Arrastre y suelte un [Envío de correo electrónico](../../automating/using/email-delivery.md) en el flujo de trabajo y ábralo.

   <!--The Email delivery activity is presented in the [Email delivery](../../automating/using/email-delivery.md) section.-->

1. Añada un campo de personalización y seleccione los datos adicionales definidos en la actividad de enriquecimiento (aquí Número de cuenta) del nodo **[!UICONTROL Additional data (targetData)]**. Esto permite recuperar dinámicamente el número de cuenta de cada perfil del contenido del correo electrónico.

   ![](assets/load_file_perso_field.png)

1. Guarde el correo electrónico e inicie el flujo de trabajo.

El correo electrónico se manda a los destinatarios. Cada perfil recibe el correo electrónico con su correspondiente número de cuenta.

![](assets/load_file_email.png)
