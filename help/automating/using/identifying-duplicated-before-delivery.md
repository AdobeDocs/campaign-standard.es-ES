---
title: Identificación de duplicados antes de un envío
description: El siguiente ejemplo ilustra una deduplicación que le permite excluir los duplicados de un destinatario antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 79%

---

# Identificación de duplicados antes de un envío {#identifying-duplicates-before-a-delivery}

El siguiente ejemplo ilustra una deduplicación que le permite excluir los duplicados de un destinatario antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.

El flujo de trabajo consta de:

![](assets/deduplication_example_workflow.png)

* A [Consulta](../../automating/using/query.md) , que permite definir el destinatario del correo electrónico. Aquí, el flujo de trabajo se dirige a todos los perfiles de entre 18 y 25 años que han estado en la base de datos del cliente durante más de un año.

  ![](assets/deduplication_example_query.png)

* A [Deduplicación](../../automating/using/deduplication.md) actividad, que le permite identificar los duplicados que provienen de la consulta anterior. En este ejemplo, solo se guarda un registro para cada duplicado. Los duplicados se identifican mediante la dirección de correo electrónico. Esto significa que la entrega de correo electrónico solo se puede enviar una vez para que cada dirección de correo electrónico esté presente en la segmentación.

  El método de deduplicación seleccionado es **[!UICONTROL Non-empty value]**. Esto le permite asegurarse de que entre los registros guardados en caso de duplicados, se da prioridad a aquellos en los que se ha proporcionado el **Nombre**. Esto hará que sea más coherente si el nombre se utiliza en los campos de personalización del contenido del correo electrónico.

  Además, se añade una transición adicional para mantener los duplicados y poder enumerarlos.

  ![](assets/deduplication_example_dedup.png)

* Un [Envío de correo electrónico](../../automating/using/email-delivery.md) se coloca después de la transición saliente principal de la deduplicación.
* A [Guardar audiencia](../../automating/using/save-audience.md) actividad colocada después de la transición adicional de la deduplicación para guardar los duplicados en una **Duplicados** audiencia. Esta audiencia se puede reutilizar para excluir directamente a sus miembros de cada entrega de correo electrónico.
