---
title: Reglas de fatiga
seo-title: Reglas de fatiga
description: Reglas de fatiga
seo-description: Cree reglas de fatiga para administrar la comunicación excesiva con perfiles.
page-status-flag: no activado nunca
uuid: fa 5 e 3 ded -36 c 2-4 f 16-b 97 a -119 b 85 adf 679
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 4337 a 80 b -0 fb 9-4 a 37-bce 3-fe 2121 a 66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Fatigue rules{#fatigue-rules}

## About fatigue rules {#about-fatigue-rules}

Las reglas de fatiga permiten a los especialistas en mercadotecnia establecer reglas comerciales globales de múltiples canales que excluirán automáticamente los perfiles sobresolicitados de las campañas.

Para implementar reglas de fatiga, debe definir un número máximo de mensajes por perfil y seleccionar un período en el que se aplicará la regla. Durante la preparación de la entrega, los perfiles se excluyen de la entrega, en función de la cantidad de mensajes que se hayan enviado.

>[!NOTE]
>
>Para aplicar reglas de fatiga, debe definir una fecha de contacto para su envío. Si decide enviar mensajes inmediatamente, no se aplicará la regla de fatiga.

Temas relacionados:

* [Preparación](../../administration/using/configuring-email-channel.md#preparation)
* [Administración de tipologías](../../administration/using/about-typology-rules.md#managing-typologies)
* [Reglas de tipología](../../administration/using/about-typology-rules.md#typology-rules)

## Creating a fatigue rule {#creating-a-fatigue-rule}

To create and configure a **[!UICONTROL Fatigue]** typology rule, apply the following steps:

1. Click the Adobe Campaign logo, in the top left corner of the interface, then select **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. From the list of typology rules, click **[!UICONTROL Create]**.

   ![](assets/fatigue.png)

1. In the **[!UICONTROL Rule type]** field, select **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. In the **[!UICONTROL Channel]** field, select which channel your rule will apply to. You can either select a single channel (email, SMS, direct mail, mobile application) or select **[!UICONTROL All channels]**. See [Choosing the channel](../../administration/using/fatigue-rules.md#choosing-the-channel).

   ![](assets/fatigue5.png)

1. In the **[!UICONTROL General]** tab, define the method for calculating the maximum number of messages per profile. Puede elegir un umbral constante o una variable. También puede reducir el umbral de los perfiles y las entregas. For more on this, refer to [Defining the threshold](../../administration/using/fatigue-rules.md#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Choose a **[!UICONTROL Sliding period]** on which the typology rule will apply. For more on this, refer to [Setting the sliding period](../../administration/using/fatigue-rules.md#setting-the-sliding-period).

   ![](assets/fatigue6.png)

   En este ejemplo (ver capturas de pantalla anteriores), decidimos enviar un número máximo de 4 mensajes durante un período deslizante de 15 días.

1. In the **[!UICONTROL Application criteria]** tab, you can choose to apply this rule to all deliveries or restrict the applicability of the rule according to the message to send. La regla sólo se ejecutará si se cumple la condición de aplicación. Por ejemplo, puede aplicar la regla únicamente en mensajes con una etiqueta que comience con una palabra dada o con un ID que contenga determinadas letras. See [Restricting the applicability of a filtering rule](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule).

   ![](assets/fatigue20.png)

1. Select the **[!UICONTROL Typologies]** tab and link your typology rule to the typology used for your deliveries. See [Managing typologies](../../administration/using/about-typology-rules.md#managing-typologies) and [Typology rules](../../administration/using/about-typology-rules.md#typology-rules).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >La tipología se puede definir en la plantilla de entrega para aplicar automáticamente a todos los envíos creados con esta plantilla.

Durante la preparación de la entrega, los perfiles se excluyen de la entrega, en función de la cantidad de envíos que se hayan enviado a ellos. Puede ver los resultados de la ejecución de la regla de fatiga en los registros de entrega. See [Viewing the fatigue results](../../administration/using/fatigue-rules.md#viewing-the-fatigue-results).

![](assets/fatigue16.png)

>[!CAUTION]
>
>Para que funcionen las reglas de fatiga, debe definir una fecha de contacto para su envío. Si decide enviar mensajes inmediatamente, no se aplicará la regla de fatiga.

## Choosing the channel {#choosing-the-channel}

Las reglas de fatiga están disponibles para varios canales. The channel is defined in the **[!UICONTROL Channel]** field of the typology rule settings. You can either select a single channel or select **[!UICONTROL All channels]**.

![](assets/fatigue5.png)

**Canales disponibles**

Están disponibles los canales siguientes:

* Correo electrónico
* Móvil (SMS)
* Correo directo
* Aplicación móvil: este canal permite enviar notificaciones push a perfiles o a suscriptores de la aplicación. Si decide enviar notificaciones a los perfiles, será compatible con reglas de fatiga multicanal.

   >[!CAUTION]
   >
   >Las reglas de fatiga no son compatibles con las notificaciones push enviadas a los suscriptores de la aplicación. Si va a enviar mensajes a los suscriptores de la aplicación, no se aplicarán las reglas de fatiga.

* Todos los canales: esta opción le permite aplicar la regla a todos los canales. Por ejemplo, puede decidir enviar un máximo de 3 mensajes al mes en cualquier canal. Si ha enviado 2 correos electrónicos a un perfil la semana pasada e intenta enviar una notificación Push hoy mismo, se excluirá el mismo perfil.

**Tipos de envío**

Las reglas de fatiga son compatibles con todos los tipos de envío: entregas de una sola toma, entregas recurrentes, envíos de flujo de trabajo y mensajes transaccionales.

**Los mensajes transaccionales** pueden utilizarse para enviar mensajes de servicio dirigidos a un evento (rtevent), así como mensajes de marketing (perfiles de objetivo), por ejemplo, un mensaje de remarketing. Las reglas de fatiga solo son compatibles con los mensajes de marketing (perfiles de objetivo). Los mensajes transaccionales de evento no contienen información de perfil, por lo que no son compatibles con las reglas de fatiga (incluso en el caso de un enriquecimiento con perfiles). With the support of marketing messages in transactional messaging, you can **apply a fatigue rule to all channels including marketing transactional messages**.

## Defining the threshold {#defining-the-threshold}

Cada regla de fatiga define un umbral, es decir, el número máximo de mensajes que pueden enviarse a un perfil durante un período determinado. Una vez alcanzado este umbral, no se pueden realizar más entregas hasta el final del período considerado. Este proceso permite excluir automáticamente un perfil de una entrega si un mensaje supera el umbral establecido, evitando así la sobresolicitud excesiva.

Los valores de umbral pueden ser constantes o variables. Esto significa que, durante un período determinado, los umbrales pueden variar de un perfil a otro o incluso para el mismo perfil.

**Uso de un umbral de corrección**

El umbral representa la mayor cantidad de mensajes que pueden enviarse a un perfil durante el período de referencia.

De forma predeterminada, el umbral es constante y es necesario indicar un número máximo de mensajes autorizados por la regla.

![](assets/fatigue2.png)

**Uso de un umbral de variable**

To define a variable threshold, select the **[!UICONTROL Depends on the recipient]** value in the **[!UICONTROL Threshold type]** field.

![](assets/fatigue15.png)

A continuación, tiene dos opciones:

* seleccione un campo de perfil: el umbral variará para cada perfil según el campo seleccionado. For example, if you have extended the profiles resource with a 'Communication frequency' field, click the button on the right of the **[!UICONTROL Threshold computation formula]** field and select your field. Para cada perfil, el umbral tomará el valor del campo'Frecuencia de comunicación '.

   ![](assets/fatigue21.png)

* define a formula: click the second button on the right of the **[!UICONTROL Threshold computation formula]** field to define an advanced threshold calculation formula. Por ejemplo, puede indexar el número de mensajes autorizados según el segmento al que pertenezca el perfil. Esto significa que un perfil que pertenece al segmento'Web'puede recibir más mensajes que otros perfiles. An **[!UICONTROL Iif (@origin='Web', 5, 3)]** type formula authorizes the delivery of 5 messages to profiles of the Web segment and 3 for other segments.

   ![](assets/fatigue14.png)

**Perfeccionamiento del umbral de perfiles y entregas**

De forma predeterminada, todos los mensajes se tienen en cuenta para el cálculo de umbral. Check the **[!UICONTROL Refine Threshold on profiles and deliveries]** box to filter the profiles and deliveries to count when preparing the delivery.

In the following example, only male profiles are counted and only deliveries with a label starting with **Newsletters** are counted.

![](assets/fatigue13.png)

Refining the threshold on deliveries is different than restricting the applicability of the entire rule ( **[!UICONTROL Application criteria]** tab):

* **[!UICONTROL Application criteria]**: elige ejecutar la regla o no según criterios específicos. Por ejemplo, si la condición de aplicación es'Etiqueta comienza con Newsletter ', la regla solo se aplicará a los envíos que respetan esta condición. Si la etiqueta de la entrega comienza con'Promoción ', la regla no se ejecutará.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**: todas las entregas que utilicen esta regla de tipología ejecutarán la regla, pero usted decide, entre las entregas pasadas y programadas, cuáles desea contar. Por ejemplo, si la restricción es'Etiqueta comienza con Newsletter ', la regla se ejecutará incluso aunque la etiqueta de envío comience por'Promoción '. Se contará, durante el período deslizante seleccionado, el número de entregas cuya etiqueta comienza con'Newsletter '.

## Setting the sliding period {#setting-the-sliding-period}

Las reglas de fatiga se definen en períodos móviles de n-day. The period is configured in the **[!UICONTROL Sliding period]** section, for example 2 weeks, 7 days or 5 hours.

![](assets/fatigue6.png)

Cuando se ejecuta la regla, se tienen en cuenta los envíos anteriores y los envíos programados. Esto garantiza que, en un período deslizante determinado, nunca se exceda el umbral.

For example, if you define a 48-hour period, the system will be looking 48 hours **before the contact date ** and 48 hours **after the contact date**. Por lo tanto, el período seleccionado se duplica para permitir la integración de entregas futuras, así como las anteriores.

To restrict the deliveries taken into account to a 2-week period, enter **Day** and **7** or 1 week in the **Sliding period** section. En el cálculo se tendrán en cuenta los envíos enviados hasta 7 días antes de la fecha de entrega y programados hasta siete días después de la fecha de entrega en la que se aplicará la regla.

## Viewing the fatigue results {#viewing-the-fatigue-results}

Durante la preparación de la entrega, los perfiles se excluyen de la entrega, en función de la cantidad de envíos que se hayan enviado a ellos. To view fatigue rule execution results, click the button in the bottom right corner of the **[!UICONTROL Deployment]** block.

![](assets/fatigue22.png)

Hay tres fichas disponibles, que muestran los detalles de los resultados de la ejecución de fatiga, incluido el nombre de la regla aplicada:

* Registros de entrega:

   ![](assets/fatigue17.png)

* Registros de exclusión:

   ![](assets/fatigue18.png)

* La exclusión provoca:

   ![](assets/fatigue19.png)

## Viewing the fatigue rule summary report {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign incluye un informe dedicado sobre reglas de fatiga para ayudarle a comprender cómo se aplican a las campañas. Esto le permite conocer cómo se afectan las campañas y realizar los ajustes adecuados.

The **[!UICONTROL Fatigue rules summary]** report can be accessed from the **[!UICONTROL Reports]** button, in the top right corner of each program, campaign, and message.

![](assets/fatigue27.png)

En la parte izquierda de la pantalla, puede filtrar los datos del informe en la fecha de contacto de los envíos. De forma predeterminada, el período seleccionado comienza 15 días antes de la fecha actual y finaliza 15 días después. También puede filtrar una regla de fatiga específica.

El gráfico circular muestra la siguiente información sobre el período seleccionado:

* **[!UICONTROL Total targeted]**: El objetivo total antes de la preparación de los mensajes
* **[!UICONTROL Excluded]**: el número total de exclusiones debido a la aplicación de reglas de fatiga
* **[!UICONTROL Other exclusions]**: el número total de exclusiones debido a otras reglas de tipología
* **[!UICONTROL To deliver]**: el número total de mensajes que se entregarán después de la preparación del mensaje ( **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]** )

A la derecha del gráfico, encontrará el número de exclusiones, desglosadas por regla de fatiga.

La tabla inferior muestra todos los envíos dentro del período seleccionado. Para cada entrega, puede ver las reglas de fatiga que se aplican y las exclusiones correspondientes. Los envíos que no tienen una fecha de contacto también se muestran en la tabla.

* **[!UICONTROL 0]** significa que la regla de fatiga se aplicó pero no hubo exclusión.
* **[!UICONTROL -N]** significa que se han producido exclusiones N.
* un campo vacío significa que no se aplicó la regla de fatiga.

>[!NOTE]
>
>Los datos mostrados no son contextuales con el programa, mensaje o campaña desde donde se obtiene acceso al informe. Este informe muestra todas las reglas de fatiga y las entregas para todas las unidades de la organización. Esto le permite obtener una vista global de todas las entregas para comprender cómo las influencian las campañas.

## Examples {#examples}

Existen muchas posibilidades en cuanto a la implementación de administración de fatiga. Estos son algunos ejemplos de lo que puede hacer:

* Create a fatigue rule using a **constant threshold** that applies to **all channels**:

   Supongamos que crea una regla multicanal, con un umbral constante de 3 en un período deslizante de 7 días.

   Última semana, sus perfiles Premium recibieron un correo electrónico de promoción y un correo electrónico de remercadotecnia de transacción. También programó un SMS que se enviará la semana siguiente. Hoy, decide enviar una notificación push para todos los perfiles. Los perfiles premium se excluirán del push de hoy porque ya se ha alcanzado su número máximo de mensajes durante un período de 2 semanas.

   ![](assets/fatigue23.png)

* Create a fatigue rule using a **variable threshold** based on a **profile field**:

   Ha ampliado el recurso de perfiles con un campo'Límite de comunicación'para definir un umbral diferente para cada perfil. En la regla de fatiga, defina un umbral de variable basado en este campo y seleccione un período deslizante de 2 días. Veamos dos ejemplos de perfiles: John tiene un límite de comunicación de 1 y David tiene un umbral de 2. Ambos ya recibieron un correo electrónico de la newsletter ayer. Usted decide enviarles otro mensaje de correo electrónico hoy mismo. Solo David lo recibirá, porque John ha sido excluido del objetivo.

   ![](assets/fatigue24.png)

* Create a fatigue rule using a **threshold computation formula**:

   Desea cambiar el umbral según la edad de los perfiles. Si un perfil es menor que 40, quiere definir un límite de 4 y de perfiles anteriores, un límite de 2. En lugar de definir este umbral para cada perfil con un campo extendido, puede crear una fórmula directamente en la regla de fatiga para calcular el umbral según la edad de los perfiles. In our example, the formula would be **[!UICONTROL Iif (@age<40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Esta sección también incluye un ejemplo paso a paso de una regla de fatiga utilizando una fórmula de cálculo de umbral.

* Create a fatigue rule that **refines the threshold** on profiles and deliveries:

   Ha ampliado el recurso de perfiles con un campo'Puntaje'y también ha ampliado el recurso de envíos con un campo'Tipo '. Desea definir un umbral constante de 3 pero desea excluir del recuento todas las entregas del tipo'Alerta'o'Black Friday'y todos los perfiles con una puntuación mayor que 10. Cuando se ejecute la regla, se contará, entre las entregas pasadas y programadas, todas las entregas que no sean del tipo'Alerta'o del "Black Friday'enviado a perfiles cuya puntuación sea menor a 10.

   ![](assets/fatigue26.png)

A continuación se muestra un ejemplo paso a paso de una regla de fatiga utilizando una fórmula de cálculo de umbral.

En este caso de uso, queremos crear una regla de tipología para evitar que se envíen más de 2 mensajes por semana a perfiles Premium y 2 mensajes por semana a perfiles estándar.

To identify customers and prospects, we extended the profiles resource with the **[!UICONTROL Status]** field, which contains 0 for premium profiles and 1 for standard profiles.

Para crear la regla, aplique los siguientes pasos:

1. Create a new **Fatigue** type typology rule.
1. In the **[!UICONTROL Threshold]** section, we want to create a formula to calculate the threshold depending on each profile. Select the **[!UICONTROL Depends on the recipient]** value in the **[!UICONTROL Threshold type]** field, then click the icon the second button on the right of the **[!UICONTROL Threshold computation formula]** field.

   ![](assets/fatigue7.png)

1. In the **[!UICONTROL List of functions]** section, double-click the **Iif** function in the **[!UICONTROL Others]** node.

   ![](assets/fatigue8.png)

1. Then select the profile's **Status** in the **[!UICONTROL Available fields]** section.

   ![](assets/fatigue9.png)

1. Enter the desired values to create the following formula: **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   Esta fórmula permite asignar el valor 2 si el estado es igual a 0 y el valor 4 para todos los demás estados.

1. Click **[!UICONTROL Confirm]** to approve the formula.
1. Indicate the **[!UICONTROL Sliding period]** on which the rule will apply: 7 days in this case, to restrict the deliveries taken into account to a 2-week period.

   ![](assets/fatigue11.png)

1. Ahora vincule la regla que acaba de crear a una tipología para aplicarla a los envíos. To do this, select the **[!UICONTROL Typologies]** tab, click **[!UICONTROL Create element]** and select the typology used for your deliveries.

   ![](assets/fatigue12.png)

1. Guarde la regla para aprobar la creación.

La regla se aplicará a todas las entregas basadas en la tipología.
