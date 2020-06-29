---
title: Reconciliación de una audiencia de archivo con la base de datos
description: Este ejemplo muestra cómo utilizar la actividad Leer audiencia para reconciliar una audiencia creada directamente a partir de una importación de archivos.
page-status-flag: never-activated
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7ffa48365875883a98904d6b344ac005afe26e18
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# Reconciliación de una audiencia de archivo con la base de datos {#example--reconcile-a-file-audience-with-the-database}

Este ejemplo muestra cómo utilizar la **[!UICONTROL Read audience]** actividad para reconciliar una audiencia creada directamente a partir de una importación de archivos.

Al importar un archivo, puede guardar directamente su contenido en una audiencia. Esta audiencia es una audiencia de archivo y sus datos no están vinculados a ningún recurso de base de datos.

El flujo de trabajo de importación está diseñado de la siguiente manera:

![](assets/readaudience_activity_example3.png)

* Una actividad de [carga de archivos](../../automating/using/load-file.md) carga un archivo que contiene datos de perfiles extraídos de una herramienta externa.

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

* Una actividad [Guardar audiencia](../../automating/using/save-audience.md) guarda los datos entrantes como una audiencia. Como los datos aún no se han conciliado, la audiencia es una audiencia de archivo y sus datos no se reconocen como datos de perfil.

El flujo de trabajo de reconciliación está diseñado de la siguiente manera:

![](assets/readaudience_activity_example2.png)

* Una actividad de audiencia [de](../../automating/using/read-audience.md) lectura carga la audiencia de archivo creada en el flujo de trabajo de importación. Los datos de audiencia aún no se han conciliado con la base de datos de Adobe Campaign.
* Una actividad [de reconciliación](../../automating/using/reconciliation.md) identifica los datos entrantes como perfiles a través de su **[!UICONTROL Identification]** ficha. Por ejemplo, utilizando el campo de **correo electrónico** como criterios de reconciliación.
* Una actividad de [actualización de datos](../../automating/using/update-data.md) inserta y actualiza el recurso de perfiles de la base de datos con los datos entrantes. Como los datos ya están identificados como perfiles, puede seleccionar la **[!UICONTROL Directly using the targeting dimension]** opción y seleccionarla **[!UICONTROL Profiles]** en la **[!UICONTROL Identification]** ficha de la actividad. A continuación, simplemente tiene que agregar la lista de campos que deben actualizarse en la ficha de acuerdo.
