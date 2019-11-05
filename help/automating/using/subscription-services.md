---
title: Servicios de suscripción
description: La actividad Servicios de suscripción le permite tomar perfiles en masa y suscribirlos a un servicio o cancelarlos de un servicio.
page-status-flag: nunca activado
uuid: 56637024-15ab-4145-9c48-3fbd27ab8af8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: gestión de datos-actividades
discoiquuid: 74a6df0e-fd85-4404-a42c-9a7406512717
context-tags: setOfService,workflow,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Servicios de suscripción{#subscription-services}

## Descripción {#description}

![](assets/wf_subscription.png)

La **[!UICONTROL Subscription Services]** actividad le permite tomar perfiles en masa y suscribirlos a un servicio o cancelarlos de un servicio.

>[!CAUTION]
>
>Cuando la suscripción se administra en el contexto de un flujo de trabajo, los perfiles suscritos o no suscritos no reciben los distintos correos electrónicos de confirmación definidos en las propiedades del servicio.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Subscription Services]** actividad es la única funcionalidad de Adobe Campaign que permite suscribirse a varios perfiles o cancelarlos de un servicio en una sola acción.

Puede utilizar esta actividad después de haber realizado la segmentación o de haber importado un archivo con datos identificados.

Si se especifica en un archivo a través de columnas dedicadas, esta actividad también le permite elegir la acción (suscripción o cancelación de suscripción) y el servicio en el que realizar la acción.

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Subscription Services]** actividad en el flujo de trabajo.
1. Conéctelo después de realizar otras actividades de segmentación, como una consulta o una reconciliación tras una importación.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Seleccione el **[!UICONTROL Service]** para el que desea administrar las suscripciones mediante una de las siguientes opciones:

   * **[!UICONTROL Select a specific service]**:: seleccione manualmente un servicio.
   * **[!UICONTROL Select services from the inbound transition]**:: el servicio se especifica en la transición de entrada. Por ejemplo, puede importar un archivo que especifique el servicio que se va a administrar para cada línea. Si elige esta opción, asegúrese de que se ha creado previamente un vínculo entre los datos y el recurso de **servicio** , como se muestra en [este ejemplo](#example--updating-multiple-subscription-statuses-from-a-file).

      El servicio en el que se realizará la operación se selecciona dinámicamente para cada registro.

1. Seleccione la **[!UICONTROL Operation type]** ejecución mediante una de las siguientes opciones:

   * **[!UICONTROL Select a specific operation type]**:: seleccione manualmente si desea **[!UICONTROL Subscribe]** o **[!UICONTROL Unsubscribe]** perfiles.
   * **[!UICONTROL Select an operation type from a path of inbound transition]**:: seleccione la columna de los datos de entrada que especifica la operación que se realizará para cada registro.

      En esta columna, la operación debe especificarse como booleana o como entero. Utilice **0** para cancelar la suscripción de un registro y **1** para suscribirse.

      Si los valores contenidos en un archivo importado no coinciden con los requisitos anteriores, puede seguir utilizando la opción [Reasignación de valores](../../automating/using/load-file.md#column-format) disponible en la **[!UICONTROL Load file]** actividad

1. Si los datos de entrada contienen una columna correspondiente a la fecha de suscripción del perfil para el servicio, selecciónelo. Puede dejarlo vacío, pero no se establece ninguna fecha de suscripción al ejecutar el flujo de trabajo.
1. Defina el origen de la suscripción. Puede definirlo en uno de los campos de los datos de entrada o en un valor constante de su elección marcando la **[!UICONTROL Set a constant as origin]** opción. Puede dejarlo vacío pero no se establece ningún origen al ejecutar el flujo de trabajo.
1. Si es necesario, puede generar una transición de salida. Esta transición contiene exactamente los mismos datos que en la actividad entrante.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

   Ahora está listo para ser ejecutado. Una vez ejecutados, puede ver los perfiles que se han suscrito o cancelado la suscripción al servicio en detalle.

## Ejemplo: Suscripción de perfiles a un servicio específico después de importar un archivo {#example--subscribing-profiles-to-a-specific-service-after-importing-a-file}

Este ejemplo ilustra cómo importar un archivo que contiene perfiles y suscribirlos a un servicio existente. Después de importar el archivo, es necesario llevar a cabo una reconciliación para que los datos importados puedan identificarse como perfiles. Para garantizar que el archivo no contenga duplicados, se ejecutará una actividad de desduplicación en los datos.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/subscription_activity_example1.png)

* Una **[!UICONTROL Load file]** actividad carga el archivo de perfil y define la estructura de las columnas importadas.

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

* Una **[!UICONTROL Reconciliation]** actividad identifica los datos del archivo como pertenecientes a la dimensión de perfil de la base de datos de Adobe Campaign. Solo se configura la **[!UICONTROL Identification]** ficha. Identifica los datos del archivo según las direcciones de correo electrónico de los perfiles.

   ![](assets/subscription_activity_example3.png)

* Un campo **[!UICONTROL Deduplication]** basado en el campo de **correo electrónico** del recurso temporal (resultante de la reconciliación) identifica los duplicados. Si los datos importados del archivo contienen duplicados, la suscripción a un servicio generará un error en todos los datos.

   ![](assets/subscription_activity_example5.png)

* Una **[!UICONTROL Subscription Services]** actividad permite seleccionar el servicio al que se deben suscribir los perfiles, el campo correspondiente a la fecha de suscripción y el origen de la suscripción.

   ![](assets/subscription_activity_example4.png)

## Ejemplo: Actualización de varios estados de suscripción desde un archivo {#example--updating-multiple-subscription-statuses-from-a-file}

Este ejemplo ilustra cómo importar un archivo que contiene perfiles y actualizar su suscripción a varios servicios especificados en el archivo. Después de importar el archivo, es necesario llevar a cabo una conciliación para que los datos importados puedan identificarse como perfiles con un vínculo a servicios. Para garantizar que el archivo no contenga duplicados, se ejecutará una actividad de desduplicación en los datos.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/subscription_activity_example1.png)

* Una **[!UICONTROL Load file]** actividad carga el archivo de perfil y define la estructura de las columnas importadas.

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

   Como puede haber notado, la operación se especifica en el archivo como "sub" o "unsub". El sistema espera que un valor **booleano** o **entero** reconozca la operación que se va a realizar: "0" para cancelar la suscripción y "1" para suscribirse. Para que coincida con este requisito, se realiza una reasignación de valores en los detalles de la columna "operación".

   ![](assets/subscription_example_remapping.png)

   Si el archivo ya utiliza "0" y "1" para identificar la operación, no es necesario volver a asignar esos valores. Solo asegúrese de que la columna se procesa como **booleano** o **entero** en la **[!UICONTROL Column definition]** ficha.

* Una **[!UICONTROL Reconciliation]** actividad identifica los datos del archivo como pertenecientes a la dimensión de perfil de la base de datos de Adobe Campaign. A través de la **[!UICONTROL Identification]** ficha, el campo de **correo electrónico** del archivo coincide con el campo de **correo electrónico** del recurso de perfil.

   ![](assets/subscription_activity_example3.png)

   En la **[!UICONTROL Relations]** ficha, se crea un vínculo con el recurso de servicio para permitir que se reconozca el campo de **servicio** del archivo. En este ejemplo, los valores coinciden con el campo **name** del recurso de servicio.

   ![](assets/subscription_example_service_relation.png)

* Un campo **[!UICONTROL Deduplication]** basado en el campo de **correo electrónico** del recurso temporal (resultante de la reconciliación) identifica los duplicados. Es importante eliminar los duplicados, ya que la suscripción a un servicio fallará en todos los datos en caso de duplicados.

   ![](assets/subscription_activity_example5.png)

* A **[!UICONTROL Subscription Services]** identifica los servicios que se van a actualizar como procedentes de la transición, a través del vínculo creado en la **[!UICONTROL Reconciliation]** actividad.

   El **[!UICONTROL Operation type]** se identifica como proveniente del campo de **operación** del archivo. Aquí solo se pueden seleccionar los campos booleano o entero. Si la columna del archivo que contiene la operación que se va a realizar no aparece en la lista, asegúrese de que ha configurado correctamente el formato de columna en la **[!UICONTROL Load file]** actividad, como se explicó anteriormente en este ejemplo.

   ![](assets/subscription_activity_example_from_file.png)

