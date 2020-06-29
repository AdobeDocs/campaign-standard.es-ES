---
title: Identificación de duplicados antes de un envío
description: El siguiente ejemplo ilustra una deduplicación que permite excluir los duplicados de un destinatario antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.
page-status-flag: never-activated
uuid: 11a22a9c-3bfe-4953-8a52-2f4e93c128fb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: e7a5e1e7-4680-46c7-98b8-0a47bb7be2b8
context-tags: dedup,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 0%

---


# Identificación de duplicados antes de un envío {#identifying-duplicates-before-a-delivery}

El siguiente ejemplo ilustra una deduplicación que permite excluir los duplicados de un destinatario antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.

El flujo de trabajo se compone de:

![](assets/deduplication_example_workflow.png)

* Una [Consulta](../../automating/using/query.md) que permite definir el destinatario del correo electrónico. Aquí, el flujo de trabajo destinatario todos los perfiles de entre 18 y 25 años que han estado en la base de datos del cliente durante más de un año.

   ![](assets/deduplication_example_query.png)

* Una actividad de [Deduplicación](../../automating/using/deduplication.md) que permite identificar los duplicados que provienen de la consulta anterior. En este ejemplo, solo se guarda un registro por cada duplicado. Los duplicados se identifican mediante la dirección de correo electrónico. Esto significa que el envío de correo electrónico solo se puede enviar una vez para que cada dirección de correo electrónico esté presente en el objetivo.

   El método de deduplicación seleccionado es **[!UICONTROL Non-empty value]**. Esto le permite asegurarse de que entre los registros guardados en caso de duplicados, se da prioridad a aquellos en los que se ha proporcionado el **Nombre** . Esto hará que sea más coherente si el nombre se utiliza en los campos de personalización del contenido del correo electrónico.

   Además, se añade una transición adicional para mantener los duplicados y poder listas.

   ![](assets/deduplication_example_dedup.png)

* Un envío [de](../../automating/using/email-delivery.md) correo electrónico ubicado después de la transición de salida principal de la deduplicación.
* Se coloca una actividad [Guardar audiencia](../../automating/using/save-audience.md) después de la transición adicional de la deduplicación para guardar los duplicados en una audiencia de **Duplicados** . Esta audiencia se puede reutilizar para excluir directamente a sus miembros de cada envío de correo electrónico.
