---
solution: Campaign Standard
product: campaign
title: Actualización de varios estados de suscripción de un archivo
description: Este caso de uso muestra cómo importar un archivo que contiene perfiles y actualizar su suscripción a varios servicios especificados en el archivo.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Flujos de trabajo
role: Arquitecto de datos
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 76%

---


# Actualización de varios estados de suscripción de un archivo {#updating-multiple-subscription-statuses-from-a-file}

Este ejemplo ilustra cómo importar un archivo que contiene perfiles y actualizar su suscripción a varios servicios especificados en el archivo. Después de importar el archivo, es necesario llevar a cabo una reconciliación para que los datos importados puedan identificarse como perfiles con un vínculo a los servicios. Para asegurarse de que el archivo no contenga duplicados, se ejecutará un proceso de anulación de duplicación en los datos.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/subscription_activity_example1.png)

* Una actividad de [Load file](../../automating/using/load-file.md) carga el archivo de perfil y define la estructura de las columnas importadas.

   Para este ejemplo, el archivo cargado tiene el formato .csv y contiene los datos siguientes:

   ```
   lastname;firstname;email;birthdate;service;operation
   jackman;megan;megan.jackman@testmail.com;07/08/1975;SVC2;sub
   phillips;edward;phillips@testmail.com;09/03/1986;SVC3;unsub
   weaver;justin;justin_w@testmail.com;11/15/1990;SVC3;sub
   martin;babeth;babeth_martin@testmail.net;11/25/1964;SVC3;unsub
   reese;richard;rreese@testmail.com;02/08/1987;SVC3;sub
   cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;SVC3;sub
   xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;SVC4;sub
   grimes;daryl;daryl_890@testmail.com;12/06/1979;SVC3;unsub
   tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;SVC2;sub
   ```

   ![](assets/subscription_example_load_file.png)

   Como ha visto, la operación se especifica en el archivo como “sub” o “unsub”. El sistema espera que un valor **booleano** o **entero** reconozca la operación que se va a realizar: “0” para cancelar la suscripción y “1” para suscribirse. Para que coincida con este requisito, se realiza una reasignación de valores en los detalles de la columna “operación”.

   ![](assets/subscription_example_remapping.png)

   Si el archivo ya utiliza “0” y “1” para identificar la operación, no es necesario volver a asignar esos valores. Solo asegúrese de que la columna se procesa como **booleano** o **entero** en la pestaña **[!UICONTROL Column definition]**.

* Una actividad [Reconciliation](../../automating/using/reconciliation.md) identifica los datos del archivo como pertenecientes a la dimensión de perfil de la base de datos de Adobe Campaign. A través de la pestaña **[!UICONTROL Identification]**, el campo de **correo electrónico** del archivo coincide con el campo de **correo electrónico** del recurso de perfil.

   ![](assets/subscription_activity_example3.png)

   En la pestaña **[!UICONTROL Relations]**, se crea un vínculo con el recurso de servicio para permitir que se reconozca el campo de **servicio** del archivo. En este ejemplo, los valores coinciden con el campo de **nombre** del recurso de servicio.

   ![](assets/subscription_example_service_relation.png)

* Una [Deduplication](../../automating/using/deduplication.md) basada en el campo **email** del recurso temporal (resultante de la reconciliación) identifica duplicados. Es importante eliminar duplicados, ya que son los causantes de que falle la suscripción a un servicio para todos los datos.

   ![](assets/subscription_activity_example5.png)

* Una actividad de [Subscription Services](../../automating/using/subscription-services.md) identifica los servicios que se van a actualizar como procedentes de la transición, a través del vínculo creado en la actividad **[!UICONTROL Reconciliation]**.

   El **[!UICONTROL Operation type]** se identifica como proveniente del campo de **operación** del archivo. Aquí solo se pueden seleccionar los campos booleano o entero. Si la columna del archivo que contiene la operación que se va a realizar no aparece en la lista, asegúrese de que ha configurado correctamente el formato de columna en la actividad de **[!UICONTROL Load file]**, como se ha explicado anteriormente en este ejemplo.

   ![](assets/subscription_activity_example_from_file.png)
