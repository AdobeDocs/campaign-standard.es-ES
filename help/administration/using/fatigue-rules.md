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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Reglas de fatiga{#fatigue-rules}

## Acerca de las reglas de fatiga {#about-fatigue-rules}

Las reglas de fatiga permiten a los especialistas en mercadotecnia establecer reglas comerciales globales de múltiples canales que excluirán automáticamente los perfiles sobresolicitados de las campañas.

Para implementar reglas de fatiga, debe definir un número máximo de mensajes por perfil y seleccionar un período en el que se aplicará la regla. Durante la preparación de la entrega, los perfiles se excluyen de la entrega, en función de la cantidad de mensajes que se hayan enviado.

>[!NOTE]
>
>Para aplicar reglas de fatiga, debe definir una fecha de contacto para su envío. Si decide enviar mensajes inmediatamente, no se aplicará la regla de fatiga.

Temas relacionados:

* [Preparación](../../administration/using/configuring-email-channel.md#preparation)
* [Administración de tipologías](../../administration/using/about-typology-rules.md#managing-typologies)
* [Reglas de tipología](../../administration/using/about-typology-rules.md#typology-rules)
* [Optimización de la frecuencia de comunicación para evitar fatiga de contacto](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

## Creación de una regla de fatiga {#creating-a-fatigue-rule}

Para crear y configurar una regla **[!UICONTROL Fatigue]** de tipología, aplique los siguientes pasos:

1. Haga clic en el logotipo de Adobe Campaign, en la esquina superior izquierda de la interfaz, y seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. En la lista de reglas de tipología, haga clic **[!UICONTROL Create]** en.

   ![](assets/fatigue.png)

1. En **[!UICONTROL Rule type]** el campo, seleccione **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. En **[!UICONTROL Channel]** el campo, seleccione el canal al que se aplicará su regla. Puede seleccionar un único canal (correo electrónico, SMS, correo directo, aplicación móvil) o seleccionar **[!UICONTROL All channels]**. Consulte [Selección del canal](../../administration/using/fatigue-rules.md#choosing-the-channel).

   ![](assets/fatigue5.png)

1. En la **[!UICONTROL General]** ficha, defina el método para calcular el número máximo de mensajes por perfil. Puede elegir un umbral constante o una variable. También puede reducir el umbral de los perfiles y las entregas. Para obtener más información, consulte [Definición del umbral](../../administration/using/fatigue-rules.md#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Elija una **[!UICONTROL Sliding period]** en la que se aplicará la regla de tipología. Para obtener más información, consulte [Configuración del periodo deslizante](../../administration/using/fatigue-rules.md#setting-the-sliding-period).

   ![](assets/fatigue6.png)

   En este ejemplo (ver capturas de pantalla anteriores), decidimos enviar un número máximo de 4 mensajes durante un período deslizante de 15 días.

1. En **[!UICONTROL Application criteria]** la ficha, puede elegir aplicar esta regla a todos los envíos o restringir la aplicabilidad de la regla según el mensaje que enviar. La regla sólo se ejecutará si se cumple la condición de aplicación. Por ejemplo, puede aplicar la regla únicamente en mensajes con una etiqueta que comience con una palabra dada o con un ID que contenga determinadas letras. Consulte [Restricción de la aplicabilidad de una regla de filtrado](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule).

   ![](assets/fatigue20.png)

1. Seleccione **[!UICONTROL Typologies]** la ficha y vincule la regla de tipología a la tipología utilizada para sus envíos. Consulte [Administración de tipologías](../../administration/using/about-typology-rules.md#managing-typologies) y [reglas de tipología](../../administration/using/about-typology-rules.md#typology-rules).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >La tipología se puede definir en la plantilla de entrega para aplicar automáticamente a todos los envíos creados con esta plantilla.

Durante la preparación de la entrega, los perfiles se excluyen de la entrega, en función de la cantidad de envíos que se hayan enviado a ellos. Puede ver los resultados de la ejecución de la regla de fatiga en los registros de entrega. Consulte [Visualización de resultados de fatiga](../../administration/using/fatigue-rules.md#viewing-the-fatigue-results).

![](assets/fatigue16.png)

>[!CAUTION]
>
>Para que funcionen las reglas de fatiga, debe definir una fecha de contacto para su envío. Si decide enviar mensajes inmediatamente, no se aplicará la regla de fatiga.

## Selección del canal {#choosing-the-channel}

Las reglas de fatiga están disponibles para varios canales. El canal se define en **[!UICONTROL Channel]** el campo de la configuración de la regla de tipología. Puede seleccionar un único canal o seleccionar **[!UICONTROL All channels]**.

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

**Los mensajes transaccionales** pueden utilizarse para enviar mensajes de servicio dirigidos a un evento (rtevent), así como mensajes de marketing (perfiles de objetivo), por ejemplo, un mensaje de remarketing. Las reglas de fatiga solo son compatibles con los mensajes de marketing (perfiles de objetivo). Los mensajes transaccionales de evento no contienen información de perfil, por lo que no son compatibles con las reglas de fatiga (incluso en el caso de un enriquecimiento con perfiles). Con la compatibilidad de mensajes de marketing en mensajes transaccionales, **puede aplicar una regla de fatiga a todos los canales, incluidos los mensajes transaccionales de marketing**.

## Definición del umbral {#defining-the-threshold}

Cada regla de fatiga define un umbral, es decir, el número máximo de mensajes que pueden enviarse a un perfil durante un período determinado. Una vez alcanzado este umbral, no se pueden realizar más entregas hasta el final del período considerado. Este proceso permite excluir automáticamente un perfil de una entrega si un mensaje supera el umbral establecido, evitando así la sobresolicitud excesiva.

Los valores de umbral pueden ser constantes o variables. Esto significa que, durante un período determinado, los umbrales pueden variar de un perfil a otro o incluso para el mismo perfil.

**Uso de un umbral de corrección**

El umbral representa la mayor cantidad de mensajes que pueden enviarse a un perfil durante el período de referencia.

De forma predeterminada, el umbral es constante y es necesario indicar un número máximo de mensajes autorizados por la regla.

![](assets/fatigue2.png)

**Uso de un umbral de variable**

Para definir un umbral de variable, seleccione **[!UICONTROL Depends on the recipient]** el valor en **[!UICONTROL Threshold type]** el campo.

![](assets/fatigue15.png)

A continuación, tiene dos opciones:

* seleccione un campo de perfil: el umbral variará para cada perfil según el campo seleccionado. Por ejemplo, si ha ampliado el recurso de perfiles con un campo de frecuencia de comunicación, haga clic en el botón de la derecha del **[!UICONTROL Threshold computation formula]** campo y seleccione el campo. Para cada perfil, el umbral tomará el valor del campo'Frecuencia de comunicación '.

   ![](assets/fatigue21.png)

* defina una fórmula: haga clic en el segundo botón de la derecha del **[!UICONTROL Threshold computation formula]** campo para definir una fórmula de cálculo de umbral avanzada. Por ejemplo, puede indexar el número de mensajes autorizados según el segmento al que pertenezca el perfil. Esto significa que un perfil que pertenece al segmento'Web'puede recibir más mensajes que otros perfiles. Una fórmula **[!UICONTROL Iif (@origin='Web', 5, 3)]** de tipo autoriza la entrega de 5 mensajes a los perfiles del segmento Web y 3 para otros segmentos.

   ![](assets/fatigue14.png)

**Perfeccionamiento del umbral de perfiles y entregas**

De forma predeterminada, todos los mensajes se tienen en cuenta para el cálculo de umbral. Marque **[!UICONTROL Refine Threshold on profiles and deliveries]** la casilla para filtrar los perfiles y las entregas que se deben contar al preparar la entrega.

En el siguiente ejemplo, solo se cuentan los perfiles masculinos y solo se cuentan los envíos con una etiqueta que comienza con **Newsletters** .

![](assets/fatigue13.png)

El refinamiento del umbral en los envíos es diferente de restringir la aplicabilidad de toda la regla ( **[!UICONTROL Application criteria]** ficha):

* **[!UICONTROL Application criteria]**: elige ejecutar la regla o no según criterios específicos. Por ejemplo, si la condición de aplicación es'Etiqueta comienza con Newsletter ', la regla solo se aplicará a los envíos que respetan esta condición. Si la etiqueta de la entrega comienza con'Promoción ', la regla no se ejecutará.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**: todas las entregas que utilicen esta regla de tipología ejecutarán la regla, pero usted decide, entre las entregas pasadas y programadas, cuáles desea contar. Por ejemplo, si la restricción es'Etiqueta comienza con Newsletter ', la regla se ejecutará incluso aunque la etiqueta de envío comience por'Promoción '. Se contará, durante el período deslizante seleccionado, el número de entregas cuya etiqueta comienza con'Newsletter '.

## Configuración del período deslizante {#setting-the-sliding-period}

Las reglas de fatiga se definen en períodos móviles de n-day. El período está configurado en **[!UICONTROL Sliding period]** la sección, por ejemplo 2 semanas, 7 días o 5 horas.

![](assets/fatigue6.png)

Cuando se ejecuta la regla, se tienen en cuenta los envíos anteriores y los envíos programados. Esto garantiza que, en un período deslizante determinado, nunca se exceda el umbral.

Por ejemplo, si define un período de 48 horas, el sistema verá 48 horas **antes de la fecha de contacto** y 48 horas **después de la fecha de contacto**. Por lo tanto, el período seleccionado se duplica para permitir la integración de entregas futuras, así como las anteriores.

Para restringir los envíos tomados en cuenta a un período de 2 semanas, introduzca **Día** y **7** o 1 semana **en** la sección Período deslizante. En el cálculo se tendrán en cuenta los envíos enviados hasta 7 días antes de la fecha de entrega y programados hasta siete días después de la fecha de entrega en la que se aplicará la regla.

## Visualización de resultados de fatiga {#viewing-the-fatigue-results}

Durante la preparación de la entrega, los perfiles se excluyen de la entrega, en función de la cantidad de envíos que se hayan enviado a ellos. Para ver los resultados de ejecución de la regla de fatiga, haga clic en el botón situado en la esquina inferior derecha del **[!UICONTROL Deployment]** bloque.

![](assets/fatigue22.png)

Hay tres fichas disponibles, que muestran los detalles de los resultados de la ejecución de fatiga, incluido el nombre de la regla aplicada:

* Registros de entrega:

   ![](assets/fatigue17.png)

* Registros de exclusión:

   ![](assets/fatigue18.png)

* La exclusión provoca:

   ![](assets/fatigue19.png)

## Visualización del informe de resumen de la regla de fatiga {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign incluye un informe dedicado sobre reglas de fatiga para ayudarle a comprender cómo se aplican a las campañas. Esto le permite conocer cómo se afectan las campañas y realizar los ajustes adecuados.

Se puede acceder al **[!UICONTROL Fatigue rules summary]** informe desde **[!UICONTROL Reports]** el botón, en la esquina superior derecha de cada programa, campaña y mensaje.

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

## Ejemplos {#examples}

Existen muchas posibilidades en cuanto a la implementación de administración de fatiga. Estos son algunos ejemplos de lo que puede hacer:

* Cree una regla de fatiga con un umbral **constante** que se aplique a **todos los canales**:

   Supongamos que crea una regla multicanal, con un umbral constante de 3 en un período deslizante de 7 días.

   Última semana, sus perfiles Premium recibieron un correo electrónico de promoción y un correo electrónico de remercadotecnia de transacción. También programó un SMS que se enviará la semana siguiente. Hoy, decide enviar una notificación push para todos los perfiles. Los perfiles premium se excluirán del push de hoy porque ya se ha alcanzado su número máximo de mensajes durante un período de 2 semanas.

   ![](assets/fatigue23.png)

* Cree una regla de fatiga con un umbral **de variable** basado en un campo **de perfil**:

   Ha ampliado el recurso de perfiles con un campo'Límite de comunicación'para definir un umbral diferente para cada perfil. En la regla de fatiga, defina un umbral de variable basado en este campo y seleccione un período deslizante de 2 días. Veamos dos ejemplos de perfiles: John tiene un límite de comunicación de 1 y David tiene un umbral de 2. Ambos ya recibieron un correo electrónico de la newsletter ayer. Usted decide enviarles otro mensaje de correo electrónico hoy mismo. Solo David lo recibirá, porque John ha sido excluido del objetivo.

   ![](assets/fatigue24.png)

* Cree una regla de fatiga con una **fórmula de cálculo de umbral**:

   Desea cambiar el umbral según la edad de los perfiles. Si un perfil es menor que 40, quiere definir un límite de 4 y de perfiles anteriores, un límite de 2. En lugar de definir este umbral para cada perfil con un campo extendido, puede crear una fórmula directamente en la regla de fatiga para calcular el umbral según la edad de los perfiles. En nuestro ejemplo, la fórmula sería **[!UICONTROL Iif (@age<40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Esta sección también incluye un ejemplo paso a paso de una regla de fatiga utilizando una fórmula de cálculo de umbral.

* Cree una regla de fatiga que **limpie el umbral** de los perfiles y las entregas:

   Ha ampliado el recurso de perfiles con un campo'Puntaje'y también ha ampliado el recurso de envíos con un campo'Tipo '. Desea definir un umbral constante de 3 pero desea excluir del recuento todas las entregas del tipo'Alerta'o'Black Friday'y todos los perfiles con una puntuación mayor que 10. Cuando se ejecute la regla, se contará, entre las entregas pasadas y programadas, todas las entregas que no sean del tipo'Alerta'o del "Black Friday'enviado a perfiles cuya puntuación sea menor a 10.

   ![](assets/fatigue26.png)

A continuación se muestra un ejemplo paso a paso de una regla de fatiga utilizando una fórmula de cálculo de umbral.

En este caso de uso, queremos crear una regla de tipología para evitar que se envíen más de 2 mensajes por semana a perfiles Premium y 2 mensajes por semana a perfiles estándar.

Para identificar clientes y posibles clientes, ampliamos el recurso de perfiles con **[!UICONTROL Status]** el campo, que contiene 0 para perfiles Premium y 1 para perfiles estándar.

Para crear la regla, aplique los siguientes pasos:

1. Cree una nueva **regla de tipología** de tipo Fatiga.
1. En **[!UICONTROL Threshold]** la sección, queremos crear una fórmula para calcular el umbral según cada perfil. Seleccione **[!UICONTROL Depends on the recipient]** el valor en **[!UICONTROL Threshold type]** el campo y, a continuación, haga clic en el icono del segundo botón situado a la derecha del **[!UICONTROL Threshold computation formula]** campo.

   ![](assets/fatigue7.png)

1. En **[!UICONTROL List of functions]** la sección, haga doble clic en **la función Iif** del **[!UICONTROL Others]** nodo.

   ![](assets/fatigue8.png)

1. A continuación, seleccione **el estado del perfil** en **[!UICONTROL Available fields]** la sección.

   ![](assets/fatigue9.png)

1. Introduzca los valores deseados para crear la fórmula siguiente: **Iif (@ status = 0,2,4)**

   ![](assets/fatigue10.png)

   Esta fórmula permite asignar el valor 2 si el estado es igual a 0 y el valor 4 para todos los demás estados.

1. Haga clic en **[!UICONTROL Confirm]** para aprobar la fórmula.
1. Indique el **[!UICONTROL Sliding period]** en el que se aplicará la regla: 7 días, en este caso, para restringir los envíos tomados en cuenta a un período de 2 semanas.

   ![](assets/fatigue11.png)

1. Ahora vincule la regla que acaba de crear a una tipología para aplicarla a los envíos. Para ello, seleccione **[!UICONTROL Typologies]** la ficha, haga clic **[!UICONTROL Create element]** y seleccione la tipología utilizada para los envíos.

   ![](assets/fatigue12.png)

1. Guarde la regla para aprobar la creación.

La regla se aplicará a todas las entregas basadas en la tipología.
