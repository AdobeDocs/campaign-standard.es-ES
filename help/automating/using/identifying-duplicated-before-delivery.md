---
title: Identificación de duplicados antes de un envío
description: El siguiente ejemplo ilustra una deduplicación que le permite excluir los duplicados de un destinatario antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: dedup,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: a09b101b-f76f-4377-9854-1fcffaad4f9a
TQID: 'https://experienceleague.adobe.com/4t0TujgM3kHTT36-Gy2lmiVQIRMy3OeChAw-Xx5MnWY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
topic_v2:
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '287'
ht-degree: 79%
---
# Identificación de duplicados antes de un envío {#identifying-duplicates-before-a-delivery}

El siguiente ejemplo ilustra una deduplicación que le permite excluir los duplicados de un destinatario antes de enviar un correo electrónico. Esto significa que evita enviar una comunicación varias veces al mismo perfil.

El flujo de trabajo consta de:

![](assets/deduplication_example_workflow.png)

* Una [consulta](../../automating/using/query.md) que le permite definir el destinatario del correo electrónico. Aquí, el flujo de trabajo se dirige a todos los perfiles de entre 18 y 25 años que han estado en la base de datos del cliente durante más de un año.

  ![](assets/deduplication_example_query.png)

* Una actividad [Deduplication](../../automating/using/deduplication.md) que le permite identificar los duplicados procedentes de la consulta anterior. En este ejemplo, solo se guarda un registro para cada duplicado. Los duplicados se identifican mediante la dirección de correo electrónico. Esto significa que la entrega de correo electrónico solo se puede enviar una vez para que cada dirección de correo electrónico esté presente en la segmentación.

  El método de deduplicación seleccionado es **[!UICONTROL Non-empty value]**. Esto le permite asegurarse de que entre los registros guardados en caso de duplicados, se da prioridad a aquellos en los que se ha proporcionado el **Nombre**. Esto hará que sea más coherente si el nombre se utiliza en los campos de personalización del contenido del correo electrónico.

  Además, se añade una transición adicional para mantener los duplicados y poder enumerarlos.

  ![](assets/deduplication_example_dedup.png)

* [Envío de correo electrónico](../../automating/using/email-delivery.md) después de la transición saliente principal de la anulación de duplicación.
* Una actividad [Guardar audiencia](../../automating/using/save-audience.md) colocada después de la transición adicional de la anulación de duplicación para guardar los duplicados en una audiencia **Duplicados**. Este público se puede reutilizar para excluir directamente a sus miembros de cada entrega de correo electrónico.
