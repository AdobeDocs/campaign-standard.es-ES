---
title: Reconciliación de un público de archivo con la base de datos
description: Este ejemplo muestra cómo utilizar la actividad Leer audiencia para reconciliar una audiencia creada directamente a partir de una importación de archivos.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: readAudience,main
feature: Workflows
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 6a59907d-850e-4d61-b1f7-8fc8b915580e
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 87%

---

# Reconciliación de un público de archivo con la base de datos {#example--reconcile-a-file-audience-with-the-database}

Este ejemplo muestra cómo utilizar la actividad **[!UICONTROL Read audience]** para reconciliar un público creado directamente a partir de una importación de archivos.

Al importar un archivo, puede guardar directamente su contenido en un público. Este público es un público de archivo y sus datos no están vinculados a ningún recurso de base de datos.

El flujo de trabajo de importación está diseñado de la siguiente manera:

![](assets/readaudience_activity_example3.png)

* Una actividad de [Cargar archivos](../../automating/using/load-file.md) carga un archivo que contiene datos de perfiles extraídos de una herramienta externa.

  Por ejemplo:

  ```
  lastname;firstname;birthdate;email;crmID
  Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
  Mars;Daniel;17/11/1987;dannymars@example.com;123545
  Smith;Clara;08/02/1989;hayden.smith@example.com;124567
  Durance;Allison;15/12/1978;allison.durance@example.com;120987
  Lucassen;Jody;28/03/1988;jody.lucassen@example.com;127634
  Binder;Tom;19/01/1982;tombinder@example.com;128653
  Binder;Tommy;19/01/1915;tombinder@example.com;134576
  Connor;Jade;10/10/1979;connor.jade@example.com;132452
  Mack;Clarke;02/03/1985;clarke.mack@example.com;149876
  Ross;Timothy;04/07/1986;timross@example.com;157643
  ```

* Una actividad de [Guardar público](../../automating/using/save-audience.md) guarda los datos de entrada como un público. Como los datos aún no están reconciliados, el público es un público de archivo y sus datos no se reconocen como datos de perfil.

El flujo de trabajo de reconciliación está diseñado de la siguiente manera:

![](assets/readaudience_activity_example2.png)

* Una actividad [Leer audiencia](../../automating/using/read-audience.md) carga la audiencia de archivo creada en el flujo de trabajo de importación. Los datos de público aún no están reconciliados con la base de datos de Adobe Campaign.
* Una actividad de [reconciliación](../../automating/using/reconciliation.md) identifica los datos de entrada como perfiles en la pestaña **[!UICONTROL Identification]**. Por ejemplo, utilizando el campo de **correo electrónico** como criterios de reconciliación.
* Una actividad de [actualización de datos](../../automating/using/update-data.md) inserta y actualiza el recurso de perfiles de la base de datos con los datos de entrada. Como los datos ya están identificados como perfiles, puede seleccionar la opción **[!UICONTROL Directly using the targeting dimension]** y seleccionar **[!UICONTROL Profiles]** en la pestaña **[!UICONTROL Identification]** de la actividad. A continuación, simplemente tiene que añadir la lista de campos que deben actualizarse en la pestaña adecuada.
