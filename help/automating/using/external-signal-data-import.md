---
title: Importación de datos y señales externas
description: El siguiente ejemplo ilustra la actividad External signal utilizada con la importación de datos.
audience: automating
content-type: reference
topic-tags: execution-activities
context-tags: signal,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: e2997cf5-861b-4202-aeb7-3a47c4d55bef
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 79%

---

# Importación de datos y señales externas {#external-signal-data-import}

El siguiente ejemplo ilustra la actividad **[!UICONTROL External signal]** en un caso de uso típico. La importación de datos se realiza en un flujo de trabajo de origen. Una vez completada la importación y actualizada la base de datos, se activa un segundo flujo de trabajo. Este segundo flujo de trabajo se utiliza para actualizar un acumulado de los datos importados.

El flujo de trabajo de origen se presenta de la siguiente manera:

* Una actividad de [Cargar archivo](../../automating/using/load-file.md) carga un archivo que contiene los nuevos datos de compra. Tenga en cuenta que la [base de datos se ha ampliado](../../developing/using/data-model-concepts.md) en consecuencia, ya que los datos de compra no están presentes de forma predeterminada en el data mart.

  Por ejemplo:

  ```
  tcode;tdate;customer;product;tamount
  aze123;21/05/2015;dannymars@example.com;A2;799
  aze124;28/05/2015;dannymars@example.com;A7;8
  aze125;31/07/2015;john.smith@example.com;A7;8
  aze126;14/12/2015;john.smith@example.com;A10;4
  aze127;02/01/2016;dannymars@example.com;A3;79
  aze128;04/03/2016;clara.smith@example.com;A8;149
  ```

* Una actividad de [reconciliación](../../automating/using/reconciliation.md) crea los vínculos entre los datos importados y la base de datos para que los datos de transacciones estén correctamente conectados a perfiles y productos.
* Una actividad de [actualización de datos](../../automating/using/update-data.md) inserta y actualiza el recurso de transacciones de la base de datos con los datos de entrada.
* Una actividad [End](../../automating/using/start-and-end.md) almacena en déclencheur el flujo de trabajo de destino, que se usa para actualizar los agregados.

![](assets/signal_example_source1.png)

El flujo de trabajo de destino se presenta de la siguiente manera:

* Una actividad [External signal](../../automating/using/external-signal.md) espera a que el flujo de trabajo de origen finalice correctamente.
* Una actividad de [consulta](../../automating/using/query.md#enriching-data) detecta perfiles y los enriquece con una recopilación configurada para recuperar la fecha de la última compra.
* Una actividad de [actualización de datos](../../automating/using/update-data.md) almacena los datos adicionales en un campo personalizado dedicado. Tenga en cuenta que el recurso de perfil se ha ampliado para añadir el campo **Última fecha de compra**.

![](assets/signal_example_source2.png)
