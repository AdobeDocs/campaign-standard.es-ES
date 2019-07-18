---
title: Servicios de suscripción
seo-title: Servicios de suscripción
description: Servicios de suscripción
seo-description: La actividad Servicios de suscripción le permite tomar perfiles en masa y suscribirlos a un servicio o cancelarlos desde un servicio.
page-status-flag: no activado nunca
uuid: 56637024-15 ab -4145-9 c 48-3 fbd 27 ab 8 af 8 af 8
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: data-management-activities
discoiquuid: 74 a 6 df 0 e-fd 85-4404-a 42 c -9 a 7406512717
context-tags: Setofservice, workflow, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0454dac1a7976c1be2838c2a846d33e77e60c3b3

---


# Subscription Services{#subscription-services}

## Description {#description}

![](assets/wf_subscription.png)

The **[!UICONTROL Subscription Services]** activity allows you to take profiles in mass and subscribe them to a service or unsubscribe them from a service.

>[!CAUTION]
>
>Cuando se gestiona la suscripción en el contexto de un flujo de trabajo, los perfiles suscritos o sin suscripción no reciben los distintos correos electrónicos de confirmación definidos en las propiedades del servicio.

## Context of use {#context-of-use}

**[!UICONTROL Subscription Services]** La actividad es la única funcionalidad de Adobe Campaign que permite suscribirse o cancelar la suscripción de varios perfiles de un servicio en una única acción.

Puede utilizar esta actividad después de haber realizado o importar un archivo con datos identificados.

Si se especifica en un archivo a través de columnas dedicadas, esta actividad también permite elegir la acción (suscribirse o cancelar la suscripción) y el servicio en el que realizar la acción.

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Subscription Services]** activity into your workflow.
1. Conéctela después de otras actividades de segmentación, como una consulta o una reconciliación después de una importación.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Select the **[!UICONTROL Service]** for which you would like to manage the subscriptions using one of the following options:

   * **[!UICONTROL Select a specific service]**: seleccione manualmente un servicio.
   * **[!UICONTROL Select services from the inbound transition]**: el servicio se especifica en la transición entrante. Por ejemplo, puede importar un archivo que especifique el servicio que se va a administrar para cada línea. If you choose this option, make sure a link has been created beforehand between the data and the **Service** resource, as shown in [this example](../../automating/using/subscription-services.md#example--updating-multiple-subscription-statuses-from-a-file).

      El servicio en el que se realiza la operación se selecciona de forma dinámica para cada registro.

1. Select the **[!UICONTROL Operation type]** to execute using one of the following options:

   * **[!UICONTROL Select a specific operation type]**: seleccione manualmente si desea **[!UICONTROL Subscribe]****[!UICONTROL Unsubscribe]** o perfiles.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**: seleccione la columna de los datos de entrada que especifica la operación que se realizará para cada registro.

      En esta columna, la operación debe especificarse como booleano o Entero. Use **0** to unsubscribe a record and **1** to subscribe.

      In case the values contained in an imported file do not match the above requirements, you can still use the [Remapping of values](../../automating/using/load-file.md#column-format) option available in the **[!UICONTROL Load file]** activity

1. Si los datos de entrada contienen una columna con la correspondiente fecha de suscripción del perfil al servicio, selecciónela. Puede dejarlo vacío, pero no se establece ninguna fecha de suscripción al ejecutar el flujo de trabajo.
1. Definir el origen de la suscripción. You can set it to one of the fields of the inbound data or to a constant value of your choice by checking the **[!UICONTROL Set a constant as origin]** option. Puede dejarlo vacío, pero no se establece ningún origen al ejecutar el flujo de trabajo.
1. Si es necesario, puede generar una transición saliente. Esta transición contiene exactamente los mismos datos que en la actividad de entrada.
1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

   Ya está listo para ejecutarse. Una vez ejecutado, puede ver los perfiles que se han suscrito o cancelado la suscripción del servicio en los detalles del servicio.

## Example: Subscribing profiles to a specific service after importing a file {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este ejemplo ilustra cómo importar un archivo que contiene perfiles y suscribirlos a un servicio existente. Después de importar el archivo, se debe realizar una reconciliación para que los datos importados puedan identificarse como perfiles. Para asegurarse de que el archivo no contenga duplicados, se ejecutará una actividad de anulación de duplicación en los datos.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/subscription_activity_example1.png)

* **[!UICONTROL Load file]** Una actividad carga el archivo de perfil y define la estructura de las columnas importadas.

   Para este ejemplo, el archivo cargado está en formato. csv y contiene los siguientes datos:

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

* **[!UICONTROL Reconciliation]** Una actividad identifica los datos del archivo como pertenecientes a la dimensión de perfil de la base de datos de Adobe Campaign. Only the **[!UICONTROL Identification]** tab is configured. Identifica los datos del archivo según las direcciones de correo electrónico de los perfiles.

   ![](assets/subscription_activity_example3.png)

* A **[!UICONTROL Deduplication]** based on the **email** field of the temporary resource (resulting from the reconciliation) identifies any duplicates. Si los datos importados del archivo contienen duplicados, la suscripción a un servicio fallará en todos los datos.

   ![](assets/subscription_activity_example5.png)

* **[!UICONTROL Subscription Services]** Una actividad permite seleccionar el servicio al que se deben suscribir los perfiles, el campo correspondiente a la fecha de suscripción y el origen de la suscripción.

   ![](assets/subscription_activity_example4.png)

## Example: Updating multiple subscription statuses from a file {#example--updating-multiple-subscription-statuses-from-a-file}

Este ejemplo ilustra cómo importar un archivo que contiene perfiles y actualizar su suscripción a varios servicios especificados en el archivo. Después de importar el archivo, se debe realizar una reconciliación para que los datos importados puedan identificarse como perfiles con un vínculo a servicios. Para asegurarse de que el archivo no contenga duplicados, se ejecutará una actividad de anulación de duplicación en los datos.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/subscription_activity_example1.png)

* **[!UICONTROL Load file]** Una actividad carga el archivo de perfil y define la estructura de las columnas importadas.

   Para este ejemplo, el archivo cargado está en formato. csv y contiene los siguientes datos:

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

   Como puede notarse, la operación se especifica en el archivo como "sub" o "unsub". The system expects a **Boolean** or **Integer** value to recognize the operation to perform: "0" to unsubscribe and "1" to subscribe. Para cumplir este requisito, se realiza una reasignación de valores en los detalles de la columna "operation".

   ![](assets/subscription_example_remapping.png)

   Si el archivo ya utiliza "0" y "1" para identificar la operación, no necesita volver a asignar esos valores. Only make sure that the column is processed as a **Boolean** or **Integer** in the **[!UICONTROL Column definition]** tab.

* **[!UICONTROL Reconciliation]** Una actividad identifica los datos del archivo como pertenecientes a la dimensión de perfil de la base de datos de Adobe Campaign. Through the **[!UICONTROL Identification]** tab, the **email** field of the file is matched to the **email** field of the profile resource.

   ![](assets/subscription_activity_example3.png)

   In the **[!UICONTROL Relations]** tab, a link is created with the service resource to allow the **service** field of the file to be recognized. In this example, the values match the **name** field of the service resource.

   ![](assets/subscription_example_service_relation.png)

* A **[!UICONTROL Deduplication]** based on the **email** field of the temporary resource (resulting from the reconciliation) identifies duplicates. Es importante eliminar los duplicados, ya que la suscripción a un servicio fallará para todos los datos en caso de duplicados.

   ![](assets/subscription_activity_example5.png)

* A **[!UICONTROL Subscription Services]** identifies the services to update as coming from the transition, through the link created in the **[!UICONTROL Reconciliation]** activity.

   The **[!UICONTROL Operation type]** is identified as coming from the **operation** field of the file. Aquí solo se pueden seleccionar los campos Booleano o Entero. If the column of your file that contains the operation to perform does not appear in the list, make sure that you have correctly set your column format in the **[!UICONTROL Load file]** activity, as explained earlier in this example.

   ![](assets/subscription_activity_example_from_file.png)

