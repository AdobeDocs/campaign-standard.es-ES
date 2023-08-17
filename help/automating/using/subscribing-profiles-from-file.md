---
title: Suscripción de perfiles de un archivo a un servicio específico
description: Este caso de uso muestra cómo importar un archivo que contiene perfiles y suscribirlos a un servicio existente.
audience: automating
content-type: reference
topic-tags: data-management-activities
context-tags: setOfService,workflow,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 06ae4a5c-f112-4aac-b776-437ac35a8f02
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 53%

---

# Suscripción de perfiles a un servicio específico después de importar un archivo {#subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este ejemplo ilustra cómo importar un archivo que contiene perfiles y suscribirlos a un servicio existente. Después de importar el archivo, es necesario llevar a cabo una reconciliación para que los datos importados puedan identificarse como perfiles. Para asegurarse de que el archivo no contenga duplicados, se ejecutará un proceso de anulación de duplicación en los datos.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/subscription_activity_example1.png)

* A [Cargar archivo](../../automating/using/load-file.md) la actividad carga el archivo de perfil y define la estructura de las columnas importadas.

  Para este ejemplo, el archivo cargado tiene el formato .csv y contiene los datos siguientes:

  ```
  lastname;firstname;email;birthdate;subdate
  jackman;megan;megan.jackman@testmail.com;07/08/1975;10/08/2017
  phillips;edward;phillips@testmail.com;09/03/1986;10/08/2017
  weaver;justin;justin_w@testmail.com;11/15/1990;10/08/2017
  martin;babeth;babeth_martin@testmail.net;11/25/1964;10/08/2017
  reese;richard;rreese@testmail.com;02/08/1987;11/08/2017
  cage;nathalie;cage.nathalie227@testmail.com;07/03/1989;11/08/2017
  xiuxiu;andrea;andrea.xiuxiu@testmail.com;09/12/1992;11/08/2017
  grimes;daryl;daryl_890@testmail.com;12/06/1979;12/08/2017
  tycoon;tyreese;tyreese_t@testmail.net;10/08/1971;12/08/2017
  ```

  ![](assets/subscription_activity_example2.png)

* A [Reconciliación](../../automating/using/reconciliation.md) La actividad identifica los datos del archivo como pertenecientes a la dimensión de perfil de la base de datos de Adobe Campaign. Solo se configura la pestaña **[!UICONTROL Identification]**. Identifica los datos del archivo según las direcciones de correo electrónico de los perfiles.

  ![](assets/subscription_activity_example3.png)

* A [Deduplicación](../../automating/using/deduplication.md) basado en el **email** el campo del recurso temporal (resultante de la reconciliación) identifica cualquier duplicado. Si los datos importados del archivo contienen duplicados, la suscripción a un servicio genera un error en todos los datos.

  ![](assets/subscription_activity_example5.png)

* A [Servicios de suscripción](../../automating/using/subscription-services.md) La actividad de permite seleccionar el servicio al que se deben suscribir los perfiles, el campo correspondiente a la fecha de suscripción y el origen de la suscripción.

  ![](assets/subscription_activity_example4.png)
