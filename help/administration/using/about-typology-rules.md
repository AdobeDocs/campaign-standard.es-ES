---
title: Acerca de las reglas de tipología
description: Descubra cómo funcionan las reglas de tipología en Adobe Campaign.
page-status-flag: nunca activado
uuid: a98ebc36-172d-4f46-b6ee-b2636a1007c9
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: reglas de trabajo con tipología
discoiquuid: 2590d94c-51ef-4c0f-b1ec-c2837e94da40
context-tags: tipología,información general;tipologíaRegla,principal;tipologíaRegla,información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de las reglas de tipología{#about-typology-rules}

Una tipología es un conjunto de reglas, ejecutadas durante la fase de análisis de mensajes, que permiten validar el destino, el contenido y la configuración de los siguientes elementos: asunto, URL, imágenes, vínculo de cancelación de suscripción, tamaño de prueba, etc.

En Adobe Campaign, cada mensaje contiene un vínculo a una tipología. Este vínculo se define en los parámetros avanzados de las propiedades de la plantilla de envío (para obtener más información sobre esto, consulte la sección [Preparación](../../administration/using/configuring-email-channel.md#preparation) ).

>[!NOTE]
>
>A cada mensaje solo se le puede asignar una única tipología.

Para cada tipología, la **[!UICONTROL Typology rules]** sección enumera el conjunto de reglas para esta tipología.

![](assets/typology_typo-rule-list.png)

## Administración de tipologías {#managing-typologies}

Hay varias tipologías de forma predeterminada en la aplicación. En función de sus necesidades, puede crear sus propias tipologías o modificar las existentes.

1. Acceda al **[!UICONTROL List of typologies]** desde el menú **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** .
1. Seleccione una tipología para modificar su contenido y propiedades o crear una nueva.

   ![](assets/typology_list.png)

1. Defina el tipo de tipología. Las tipologías pueden ser estándar o de filtrado.
1. Agregue las reglas de tipología que necesite con el **[!UICONTROL Add an element]** botón o elimine las que no desee utilizar.

   Puede modificar el orden en que se aplican las reglas para una tipología determinada. Para ello, mueva los elementos para modificar el orden en que aparecen en la pantalla. Los números correspondientes al orden de ejecución se vuelven a calcular automáticamente. El modo de aplicación de reglas se presenta en la sección Orden [de ejecución de reglas de](#typology-rules-execution-order) tipología.

   Se puede acceder a las reglas que se muestran en esta pantalla en modo de solo lectura.

Su tipología está lista para usarse. Puede seleccionarlo en propiedades de mensaje o en propiedades de plantilla de mensaje.

>[!NOTE]
>
>El **[!UICONTROL IP affinity]** campo permite administrar las afinidades según la configuración. Se definen en el archivo de configuración de la instancia. Si desea utilizar las afinidades, póngase en contacto con el administrador.

## Reglas de tipología {#typology-rules}

Las reglas de tipología son reglas comerciales que se aplican durante la preparación del mensaje. Se utilizan para comprobar si un mensaje es válido y cumple los criterios de calidad. También comprueban si cada miembro de la audiencia de destino puede recibir el mensaje.

Las reglas de tipología están disponibles en el menú **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** .

Existen dos tipos de reglas:

* **Filtrado** de reglas: le permite excluir una parte del objetivo de mensaje según los criterios definidos en una consulta, como perfiles en cuarentena o perfiles que ya se han enviado un determinado número de correos electrónicos. Consulte [Filtrado de reglas](../../administration/using/filtering-rules.md).
* **Reglas de fatiga** : le permite definir un número máximo de mensajes por perfil para evitar que se les solicite demasiado. Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md).
* **Reglas de control** : permitir al usuario comprobar la validez y calidad de los mensajes antes de enviarlos, como la visualización de caracteres, el tamaño del mensaje SMS, el formato de la dirección, etc. Consulte Reglas [de control](../../administration/using/control-rules.md).

Una regla de tipología puede aplicarse a un solo canal o a todos los canales.

![](assets/typology_channel.png)

En el caso **[!UICONTROL Properties]** de una regla de tipología, puede establecer su orden de ejecución. Cuando hay que aplicar varias reglas, el orden de ejecución de cada regla determina las que se procesarán primero. Para obtener más información sobre esto, consulte la sección Orden [de ejecución de reglas de](#typology-rules-execution-order) tipología.

![](assets/typology_rule-active.png)

Una regla de tipología se puede desactivar mediante su **[!UICONTROL Properties]** aplicación si no desea que la regla se aplique en el momento en que se analizan los mensajes relacionados con la regla.

![](assets/typology_rule-order.png)

En la **[!UICONTROL Targeting context]** categoría, puede seleccionar la dimensión **** Segmentación y la dimensión **** Filtrado en función de los datos que desee segmentar.

De forma predeterminada, el filtrado se realiza en el **[!UICONTROL Profiles]**. Por ejemplo, si la regla está dirigida a una aplicación móvil, **[!UICONTROL Filtering dimension]** se puede cambiar a **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Orden de ejecución de reglas de tipología {#typology-rules-execution-order}

Las reglas de tipología se ejecutan en un orden especificado durante las fases de segmentación, análisis y personalización de mensajes.

En el modo de operación estándar, las reglas se aplican en la siguiente secuencia:

1. Reglas de control, si se aplican al principio del objetivo.
1. Reglas de filtrado:

   * Reglas de aplicación nativas para la revisión de direcciones: dirección definida/dirección no verificada/dirección en lista negra/dirección en cuarentena/calidad de la dirección.
   * Reglas de filtrado definidas por el usuario.

1. Reglas de control, si se aplican al final del objetivo.
1. Reglas de control, si se aplican al inicio de la personalización.
1. Reglas de control, si se aplican al final de la personalización.

Sin embargo, puede adaptar el orden de ejecución del mismo tipo de reglas en cada tipología. De hecho, cuando se ejecutan varias reglas durante la misma fase de procesamiento de mensajes, puede elegir el orden en que se aplican.

Por ejemplo, una regla de filtrado cuya orden de ejecución se sitúa en el número 20 se ejecutará antes que una regla de filtrado cuya orden de ejecución se posicione en el número 30.
