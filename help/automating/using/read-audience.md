---
title: Leer audiencia
description: La actividad Leer audiencia permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.
page-status-flag: nunca activado
uuid: 58c54e71-f4a7-4ae9-80a3-33c379ab1db9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: segmentación-actividades
discoiquuid: 674684e5-8830-4d2f-ba97-59ed4ba7422f
context-tags: readAudience,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Leer audiencia{#read-audience}

## Descripción {#description}

![](assets/prefill.png)

La **[!UICONTROL Read audience]** actividad permite recuperar una audiencia existente y refinarla mediante la aplicación de condiciones de filtrado adicionales.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Read audience]** actividad es una versión más sencilla de la **[!UICONTROL Query]** actividad diseñada para casos en los que solo es necesario seleccionar una audiencia existente.

## Configuración {#configuration}

1. Coloque una **[!UICONTROL Read audience]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione la audiencia que desee recuperar desde la **[!UICONTROL Properties]** ficha.

   Puede recuperar audiencias de los siguientes tipos: **[!UICONTROL List]**, **[!UICONTROL Query]**, **[!UICONTROL File]** y **[!UICONTROL Experience Cloud]**. Para obtener más información sobre los tipos de audiencia, consulte la documentación de [Audiencias](../../audiences/using/about-audiences.md) .

   La **[!UICONTROL Use a dynamic audience]** opción le permite definir el nombre de la audiencia objetivo en función de las variables de eventos del flujo de trabajo. Para obtener más información sobre esto, consulte la sección [Personalización de actividades con variables](../../automating/using/calling-a-workflow-with-external-parameters.md#customizing-activities-with-events-variables) de eventos.

   ![](assets/readaudience_activity1.png)

1. Si desea aplicar filtros adicionales a la audiencia seleccionada, agregue condiciones mediante la **[!UICONTROL Source filtering]** ficha de la actividad.

   Para obtener más información sobre la creación de condiciones de filtrado, consulte la documentación [Creación de consultas](../../automating/using/editing-queries.md#creating-queries) .

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo: Reconciliación de una audiencia de archivo con la base de datos {#example--reconcile-a-file-audience-with-the-database}

En este ejemplo se muestra cómo utilizar la actividad para reconciliar una audiencia creada directamente a partir de una importación de archivos. **[!UICONTROL Read audience]**

Al importar un archivo, puede guardar directamente su contenido en una audiencia. Esta audiencia es una audiencia de archivo y sus datos no están vinculados a ningún recurso de base de datos.

El flujo de trabajo de importación está diseñado de la siguiente manera:

![](assets/readaudience_activity_example3.png)

* Una actividad [Cargar archivo](../../automating/using/load-file.md) carga un archivo que contiene datos de perfiles extraídos de una herramienta externa.

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

* Una **[!UICONTROL Read audience]** actividad carga la audiencia Archivo creada en el flujo de trabajo de importación. Los datos de audiencia aún no se han conciliado con la base de datos de Adobe Campaign.
* Una actividad de [reconciliación](../../automating/using/reconciliation.md) identifica los datos entrantes como perfiles a través de su **[!UICONTROL Identification]** ficha. Por ejemplo, utilizando el campo de **correo electrónico** como criterios de reconciliación.
* Una actividad de [actualización de datos](../../automating/using/update-data.md) inserta y actualiza el recurso de perfiles de la base de datos con los datos entrantes. Como los datos ya están identificados como perfiles, puede seleccionar la **[!UICONTROL Directly using the targeting dimension]** opción y seleccionarla **[!UICONTROL Profiles]** en la **[!UICONTROL Identification]** ficha de la actividad. A continuación, simplemente tiene que agregar la lista de campos que deben actualizarse en la ficha de acuerdo.

## Ejemplo: Unión en dos audiencias refinadas {#example--union-on-two-refined-audiences}

El flujo de trabajo definido en este ejemplo muestra la unión de dos **[!UICONTROL Read audience]** actividades. El objetivo de este flujo de trabajo es enviar un correo electrónico a los socios Gold o Silver que tengan entre 18 y 30 años.

Ya se han creado audiencias específicas en el sistema para realizar un seguimiento de los miembros Gold y Silver.

El flujo de trabajo está diseñado de la siguiente manera:

![](assets/readaudience_activity_example1.png)

* Primera **[!UICONTROL Read audience]** actividad que recupera la audiencia de miembros Gold y la refina seleccionando solo perfiles con edades comprendidas entre 18 y 30 años.
* Una segunda **[!UICONTROL Read audience]** actividad que recupera la audiencia de los miembros de Silver y la perfecciona seleccionando solo perfiles de entre 18 y 30 años.
* Actividad **[!UICONTROL Union]** que une poblaciones de ambas **[!UICONTROL Read audiences]** actividades en una población final.
* Actividad **[!UICONTROL Email delivery]** que envía el correo electrónico a la población que proviene de la **[!UICONTROL Union]** actividad.

