---
title: Reglas de fatiga
description: Cree reglas de fatiga para administrar la sobrecomunicación con perfiles.
page-status-flag: nunca activado
uuid: fa5e3ded-36c2-4f16-b97a-119b85adf679
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: reglas de trabajo con tipología
discoiquuid: 4337a80b-0fb9-4a37-bce3-fe2121a66586
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Reglas de fatiga{#fatigue-rules}

## Acerca de las reglas de fatiga {#about-fatigue-rules}

Las reglas de fatiga permiten a los especialistas en mercadotecnia establecer reglas comerciales globales entre canales que excluyen automáticamente los perfiles solicitados en exceso de las campañas.

Para implementar reglas de fatiga, debe definir un número máximo de mensajes por perfil y seleccionar un período en el que se aplicará la regla. Durante la preparación de la entrega, los perfiles se excluyen de la entrega, si procede, en función del número de mensajes que ya se les hayan enviado.

>[!NOTE]
>
>Para aplicar las reglas de fatiga, debe definir una fecha de contacto para la entrega. Si decide enviar mensajes inmediatamente, no se aplicará la regla de fatiga.

Temas relacionados:

* [Preparación](../../administration/using/configuring-email-channel.md#preparation)
* [Administración de tipologías](../../administration/using/about-typology-rules.md#managing-typologies)
* [Reglas de tipología](../../administration/using/about-typology-rules.md#typology-rules)
* [Optimización de la frecuencia de comunicación para prevenir la fatiga de contacto](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)

## Creación de una regla de fatiga {#creating-a-fatigue-rule}

To create and configure a **[!UICONTROL Fatigue]** typology rule, apply the following steps:

1. Haga clic en el logotipo de Adobe Campaign, en la esquina superior izquierda de la interfaz, y luego seleccione **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]**.

   ![](assets/fatigue4.png)

1. En la lista de reglas de tipología, haga clic en **[!UICONTROL Create]**.

   ![](assets/fatigue.png)

1. En el **[!UICONTROL Rule type]** campo, seleccione **[!UICONTROL Fatigue]**.

   ![](assets/fatigue3.png)

1. En el **[!UICONTROL Channel]** campo, seleccione a qué canal se aplicará la regla. Puede seleccionar un solo canal (correo electrónico, SMS, correo directo, aplicación móvil) o seleccionar **[!UICONTROL All channels]**. Consulte [Selección del canal](#choosing-the-channel).

   ![](assets/fatigue5.png)

1. En la **[!UICONTROL General]** ficha, defina el método para calcular el número máximo de mensajes por perfil. Puede elegir un umbral constante o una variable. También puede reducir el umbral en perfiles y envíos. Para obtener más información sobre esto, consulte [Definición del umbral](#defining-the-threshold).

   ![](assets/fatigue2.png)

1. Elija un **[!UICONTROL Sliding period]** punto en el que se aplicará la regla de tipología. Para obtener más información sobre esto, consulte [Configuración del período](#setting-the-sliding-period)deslizante.

   ![](assets/fatigue6.png)

   En este ejemplo (consulte capturas de pantalla anteriores), elegimos enviar un número máximo de 4 mensajes durante un período deslizante de 15 días.

1. En la **[!UICONTROL Application criteria]** ficha, puede elegir aplicar esta regla a todas las entregas o restringir la aplicabilidad de la regla según el mensaje que se va a enviar. La regla solo se ejecutará si se cumple la condición de la aplicación. Por ejemplo, puede aplicar la regla solo en mensajes con una etiqueta que comience por una palabra determinada o con un ID que contenga determinadas letras. Consulte [Restricción de la aplicabilidad de una regla](../../administration/using/filtering-rules.md#restricting-the-applicability-of-a-filtering-rule)de filtrado.

   ![](assets/fatigue20.png)

1. Seleccione la **[!UICONTROL Typologies]** ficha y vincule la regla de tipología a la tipología utilizada para los envíos. Consulte [Administración de tipologías](../../administration/using/about-typology-rules.md#managing-typologies) y reglas [de tipología](../../administration/using/about-typology-rules.md#typology-rules).

   ![](assets/fatigue12.png)

   >[!NOTE]
   >
   >La tipología se puede definir en la plantilla de envío para que se aplique automáticamente a todos los envíos creados con esta plantilla.

Durante la preparación de la entrega, los perfiles se excluyen de la entrega, si procede, según el número de entregas ya enviadas. Puede ver los resultados de la ejecución de reglas de fatiga en los registros de entrega. Consulte [Visualización de los resultados](#viewing-the-fatigue-results)de fatiga.

![](assets/fatigue16.png)

>[!CAUTION]
>
>Para que funcionen las reglas de fatiga, debe definir una fecha de contacto para la entrega. Si decide enviar mensajes inmediatamente, no se aplicará la regla de fatiga.

## Selección del canal {#choosing-the-channel}

Las reglas de fatiga están disponibles para varios canales. El canal se define en el **[!UICONTROL Channel]** campo de la configuración de la regla de tipología. Puede seleccionar un solo canal o seleccionar **[!UICONTROL All channels]**.

![](assets/fatigue5.png)

**Canales disponibles**

Están disponibles los siguientes canales:

* Correo electrónico
* Móvil
                            (SMS)
* Correo postal
* Aplicación móvil: este canal le permite enviar notificaciones push a perfiles o suscriptores de la aplicación. Si decide enviar notificaciones a los perfiles, serán compatibles con las reglas de fatiga multicanal.

   >[!CAUTION]
   >
   >Las reglas de fatiga no son compatibles con las notificaciones push enviadas a los suscriptores de la aplicación. Si envía mensajes a los suscriptores de la aplicación, no se aplicarán las reglas de fatiga.

* Todos los canales: esta opción le permite aplicar la regla a todos los canales. Por ejemplo, puede decidir enviar un máximo de 3 mensajes al mes en cualquier canal. Si la semana pasada enviaste dos correos electrónicos a un perfil e intentas enviar una notificación push hoy, se excluirá el mismo perfil.

**Tipos de envío**

Las reglas de fatiga son compatibles con todos los tipos de envío: entregas únicas, entregas recurrentes, entregas de flujo de trabajo y mensajes transaccionales.

**Los mensajes** transaccionales pueden utilizarse para enviar mensajes de servicio dirigidos a un evento (rtEvent), así como mensajes de marketing (perfiles de objetivo), por ejemplo un mensaje de remarketing. Las reglas de fatiga solo son compatibles con los mensajes de marketing (perfiles de objetivo). Los mensajes transaccionales de eventos no contienen información de perfil, por lo tanto no son compatibles con las reglas de fatiga (incluso en el caso de un enriquecimiento con perfiles). Con la compatibilidad de los mensajes de marketing en los mensajes transaccionales, puede **aplicar una regla de fatiga a todos los canales, incluidos los mensajes** transaccionales de marketing.

## Definición del umbral {#defining-the-threshold}

Cada regla de fatiga define un umbral, es decir, el número máximo de mensajes que se pueden enviar a un perfil durante un período determinado. Una vez alcanzado este umbral, no se pueden realizar más envíos hasta el final del periodo. Este proceso le permite excluir automáticamente un perfil de una entrega si un mensaje supera el umbral establecido, evitando así una solicitud excesiva.

Los valores de umbral pueden ser constantes o variables. Esto significa que para un período determinado, los umbrales pueden variar de un perfil a otro, o incluso para el mismo perfil.

**Uso de un umbral de corrección**

El umbral representa el número más alto de mensajes que se pueden enviar a un perfil durante el período en cuestión.

De forma predeterminada, el umbral es constante y es necesario indicar un número máximo de mensajes autorizados por la regla.

![](assets/fatigue2.png)

**Uso de un umbral de variable**

Para definir un umbral de variable, seleccione el **[!UICONTROL Depends on the recipient]** valor en el **[!UICONTROL Threshold type]** campo.

![](assets/fatigue15.png)

A continuación, tiene dos opciones:

* seleccione un campo de perfil: el umbral variará para cada perfil según el campo seleccionado. Por ejemplo, si ha ampliado el recurso de perfiles con un campo 'Frecuencia de comunicación', haga clic en el botón de la derecha del **[!UICONTROL Threshold computation formula]** campo y seleccione el campo. Para cada perfil, el umbral tomará el valor del campo 'Frecuencia de comunicación'.

   ![](assets/fatigue21.png)

* definir una fórmula: haga clic en el segundo botón de la derecha del **[!UICONTROL Threshold computation formula]** campo para definir una fórmula de cálculo de umbral avanzada. Por ejemplo, puede indexar el número de mensajes autorizados según el segmento al que pertenece el perfil. Esto significa que un perfil que pertenece al segmento 'Web' puede recibir más mensajes que otros perfiles. Una fórmula de **[!UICONTROL Iif (@origin='Web', 5, 3)]** tipo autoriza el envío de 5 mensajes a perfiles del segmento Web y 3 para otros segmentos.

   ![](assets/fatigue14.png)

**Mejora del umbral de perfiles y entregas**

De forma predeterminada, todos los mensajes tienen en cuenta el cálculo de umbral. Marque la **[!UICONTROL Refine Threshold on profiles and deliveries]** casilla para filtrar los perfiles y envíos que se van a contar al preparar la entrega.

En el siguiente ejemplo, solo se cuentan los perfiles masculinos y solo se cuentan los envíos con una etiqueta que comienza con **boletines informativos** .

![](assets/fatigue13.png)

Refinar el umbral en las entregas es diferente a restringir la aplicabilidad de toda la regla ( **[!UICONTROL Application criteria]** ficha):

* **[!UICONTROL Application criteria]**:: se decide ejecutar la regla o no según criterios específicos. Por ejemplo, si la condición de la aplicación es 'La etiqueta comienza con la newsletter', la regla solo se aplicará a los envíos que respeten esta condición. Si la etiqueta de la entrega empieza por 'Promoción', la regla no se ejecutará en absoluto.
* **[!UICONTROL Refine threshold on profiles and deliveries > Deliveries to count]**:: todas las entregas que utilicen esta regla de tipología ejecutarán la regla, pero usted decide, entre las entregas anteriores y programadas, cuáles desea contar. Por ejemplo, si la restricción es 'La etiqueta comienza con la newsletter', la regla se ejecutará aunque la etiqueta de entrega comience por 'Promo'. Durante el período deslizante seleccionado, se contará el número de entregas cuya etiqueta comienza con 'Newsletter'.

## Configuración del período deslizante {#setting-the-sliding-period}

Las reglas de fatiga se definen en los períodos móviles n días. El período se configura en la **[!UICONTROL Sliding period]** sección, por ejemplo 2 semanas, 7 días o 5 horas.

![](assets/fatigue6.png)

Cuando se ejecuta la regla, se tienen en cuenta las entregas anteriores y las programadas. Esto garantiza que, en un período deslizante determinado, el umbral nunca se supere.

Por ejemplo, si define un período de 48 horas, el sistema buscará 48 horas **antes de la fecha** de contacto y 48 horas **después de la fecha** de contacto. Por lo tanto, el período seleccionado se duplica para permitir la integración de las entregas futuras así como las anteriores.

Para restringir los envíos en cuenta a un período de 2 semanas, ingrese **Día** y **7** o 1 semana en la sección Período **** deslizante. Las entregas enviadas hasta 7 días antes de la fecha de entrega y programadas hasta 7 días después de la fecha de entrega en la que se aplica la regla se tendrán en cuenta en el cálculo.

## Ver los resultados de fatiga {#viewing-the-fatigue-results}

Durante la preparación de la entrega, los perfiles se excluyen de la entrega, si procede, según el número de entregas ya enviadas. Para ver los resultados de ejecución de regla de fatiga, haga clic en el botón en la esquina inferior derecha del **[!UICONTROL Deployment]** bloque.

![](assets/fatigue22.png)

Hay tres fichas disponibles que muestran los detalles de los resultados de la ejecución de fatiga, incluido el nombre de la regla que se aplicó:

* Registros de envío:

   ![](assets/fatigue17.png)

* Registros de exclusión:

   ![](assets/fatigue18.png)

* Causas de exclusión:

   ![](assets/fatigue19.png)

## Visualización del informe de resumen de regla de fatiga {#viewing-the-fatigue-rule-summary-report}

Adobe Campaign incluye un informe dedicado sobre las reglas de fatiga para ayudarle a comprender cómo se aplican a sus campañas. Esto le permite conocer cómo las campañas se afectan entre sí y realizar los ajustes adecuados.

Se puede acceder al **[!UICONTROL Fatigue rules summary]** informe desde el **[!UICONTROL Reports]** botón, en la esquina superior derecha de cada programa, campaña y mensaje.

![](assets/fatigue27.png)

En la parte izquierda de la pantalla, puede filtrar los datos del informe en la fecha de contacto de los envíos. De forma predeterminada, el período seleccionado comienza 15 días antes de la fecha actual y finaliza 15 días después. También puede filtrar por una regla de fatiga específica.

El gráfico circular muestra la siguiente información sobre el período seleccionado:

* **[!UICONTROL Total targeted]**:: el objetivo total antes de la preparación del mensaje
* **[!UICONTROL Excluded]**:: el número total de exclusiones debidas a la aplicación de reglas de fatiga
* **[!UICONTROL Other exclusions]**:: el número total de exclusiones debidas a otras reglas de tipología
* **[!UICONTROL To deliver]**:: el número total de mensajes que se enviarán tras la preparación del mensaje ( **[!UICONTROL To deliver]** = **[!UICONTROL Total targeted]** - **[!UICONTROL Excluded]** - **[!UICONTROL Other exclusions]** )

A la derecha del gráfico, encontrará el número de exclusiones, desglosado por regla de fatiga.

La tabla inferior muestra todos los envíos dentro del período seleccionado. Para cada entrega, puede ver las reglas de fatiga aplicadas y las exclusiones correspondientes. Las entregas que no tengan fecha de contacto también se muestran en la tabla.

* **[!UICONTROL 0]** significa que la regla de fatiga se aplicó pero no hubo exclusión.
* **[!UICONTROL -N]** significa que no se produjeron exclusiones.
* un campo vacío significa que no se aplicó la regla de fatiga.

>[!NOTE]
>
>Los datos mostrados no son contextuales para el programa, mensaje o campaña desde el que se accede al informe. Este informe muestra todas las reglas de fatiga y entregas de todas las unidades organizativas. Esto le permite obtener una vista global de todos los envíos a fin de comprender cómo otras personas influyen en sus campañas.

## Ejemplos {#examples}

Existen muchas posibilidades en cuanto a la implementación de la gestión de fatiga. Estos son algunos ejemplos de lo que puede hacer:

* Cree una regla de fatiga usando un umbral **** constante que se aplique a **todos los canales**:

   Supongamos que crea una regla multicanal, con un umbral constante de 3 durante un período deslizante de 7 días.

   La semana pasada, sus perfiles Premium recibieron un correo electrónico de promoción y un correo electrónico de remercadotecnia transaccional. También programaste un SMS que se enviará la semana que viene. Hoy, decide enviar una notificación push dirigida a todos sus perfiles. Los perfiles Premium se excluirán de la inserción de hoy porque ya se ha alcanzado el número máximo de mensajes durante un período de 2 semanas.

   ![](assets/fatigue23.png)

* Cree una regla de fatiga usando un umbral **de** variable basado en un campo **de** perfil:

   Ha ampliado el recurso de perfiles con un campo 'Límite de comunicación' para definir un umbral diferente para cada perfil. En la regla de fatiga, defina un umbral de variable basado en este campo y seleccione un período deslizante de 2 días. Veamos dos ejemplos de perfiles: John tiene un límite de comunicación de 1 y David tiene un umbral de 2. Ambos ya recibieron un correo electrónico con newsletter ayer. Usted decide enviarles otro correo electrónico hoy. Sólo David lo recibirá, porque John ha sido excluido del objetivo.

   ![](assets/fatigue24.png)

* Cree una regla de fatiga usando una fórmula **de cálculo de** umbral:

   Desea cambiar el umbral según la edad de los perfiles. Si un perfil es menor a 40, desea definir un límite de 4 y, para perfiles más antiguos, un límite de 2. En lugar de definir este umbral para cada perfil con un campo extendido, puede crear una fórmula directamente en la regla de fatiga para calcular el umbral según la edad de los perfiles. En nuestro ejemplo, la fórmula sería **[!UICONTROL Iif (@age<40, 4, 2)]**.

   ![](assets/fatigue25.png)

   >[!NOTE]
   >
   >Esta sección también incluye un ejemplo paso a paso de una regla de fatiga que utiliza una fórmula de cálculo de umbral.

* Cree una regla de fatiga que **ajuste el umbral** en perfiles y entregas:

   Ha ampliado el recurso de perfiles con un campo 'Puntuación' y también ha ampliado el recurso de entregas con un campo 'Tipo'. Desea definir un umbral constante de 3, pero desea excluir del recuento todas las entregas del tipo 'Alerta' o 'Viernes negro' y todos los perfiles con una puntuación mayor que 10. Cuando la regla se ejecute, contará, entre las entregas anteriores y programadas, todas las entregas que no sean del tipo 'Alerta' o 'Viernes Negro' enviadas a perfiles cuya puntuación sea menor que 10.

   ![](assets/fatigue26.png)

Este es un ejemplo paso a paso de una regla de fatiga que utiliza una fórmula de cálculo de umbral.

En este caso de uso, queremos crear una regla de tipología para evitar la entrega de más de 2 mensajes por semana a perfiles Premium y 2 mensajes por semana a perfiles estándar.

Para identificar clientes y posibles clientes, hemos ampliado el recurso de perfiles con el **[!UICONTROL Status]** campo, que contiene 0 para perfiles Premium y 1 para perfiles estándar.

Para crear la regla, siga los siguientes pasos:

1. Create a new **Fatigue** type typology rule.
1. En la **[!UICONTROL Threshold]** sección, queremos crear una fórmula para calcular el umbral en función de cada perfil. Seleccione el **[!UICONTROL Depends on the recipient]** valor en el **[!UICONTROL Threshold type]** campo y, a continuación, haga clic en el icono del segundo botón situado a la derecha del **[!UICONTROL Threshold computation formula]** campo.

   ![](assets/fatigue7.png)

1. En la **[!UICONTROL List of functions]** sección, haga doble clic en la función **Iif** en el **[!UICONTROL Others]** nodo.

   ![](assets/fatigue8.png)

1. A continuación, seleccione el **estado** del perfil en la **[!UICONTROL Available fields]** sección .

   ![](assets/fatigue9.png)

1. Introduzca los valores deseados para crear la fórmula siguiente: **Iif(@status=0,2,4)**

   ![](assets/fatigue10.png)

   Esta fórmula permite asignar el valor 2 si el estado es igual a 0 y el valor 4 para todos los demás estados.

1. Click **[!UICONTROL Confirm]** to approve the formula.
1. Indique la **[!UICONTROL Sliding period]** forma en que se aplicará la regla: 7 días en este caso, para limitar las entregas a un período de 2 semanas.

   ![](assets/fatigue11.png)

1. Ahora vincule la regla que acaba de crear a una tipología para aplicarla a las entregas. Para ello, seleccione la **[!UICONTROL Typologies]** ficha, haga clic en **[!UICONTROL Create element]** y seleccione la tipología utilizada para los envíos.

   ![](assets/fatigue12.png)

1. Guarde la regla para aprobar la creación.

La regla se aplicará a todos los envíos según la tipología.
