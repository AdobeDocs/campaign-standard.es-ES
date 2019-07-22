---
title: Acerca de las reglas de tipología
seo-title: Acerca de las reglas de tipología
description: Acerca de las reglas de tipología
seo-description: Descubra cómo funcionan las reglas de tipología en Adobe Campaign.
page-status-flag: no activado nunca
uuid: a 98 ebc 36-172 d -4 f 46-b 6 ee-b 2636 a 1007 c 9
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 2590 d 94 c -51 ef -4 c 0 f-b 1 ec-c 2837 e 94 da 40
context-tags: tipología, información general; Typologyrule, main; Typologyrule, información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e5532c0769fe33016eaee994bdaae9c70a7eaa5

---


# About typology rules{#about-typology-rules}

Una tipología es un conjunto de reglas ejecutado durante la fase de análisis de mensaje, que permite que el objetivo, el contenido y la configuración de los siguientes elementos se validen: el asunto, la URL, las imágenes, el vínculo de cancelación de suscripción, el tamaño de la prueba, etc.

En Adobe Campaign, cada mensaje contiene un vínculo a una tipología. This link is defined in the advanced parameters of the delivery template's properties (for more on this, refer to the [Preparation](../../administration/using/configuring-email-channel.md#preparation) section).

>[!NOTE]
>
>Solo se puede asignar una tipología única a cada mensaje.

For each typology, the **[!UICONTROL Typology rules]** section lists the set of rules for this typology.

![](assets/typology_typo-rule-list.png)

## Managing typologies {#managing-typologies}

De forma predeterminada, existen varias tipologías en la aplicación. Según sus necesidades, puede crear sus propias tipologías o modificar las existentes.

1. Access the **[!UICONTROL List of typologies]** from the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** menu.
1. Seleccione una tipología para modificar su contenido y propiedades o crear uno nuevo.

   ![](assets/typology_list.png)

1. Definir el tipo de tipología. Las tipologías pueden ser estándar o filtrado de tipografías.
1. Add the typology rules you need using the **[!UICONTROL Add an element]** button or remove the ones you do not want to use.

   Puede modificar el orden en que se aplican las reglas para una tipología determinada. Para ello, mueva los elementos a fin de modificar el orden en que aparecen en la pantalla. A continuación, los números correspondientes al orden de ejecución se recalculan automáticamente. The rule application mode is presented in the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

   Se puede acceder a las reglas mostradas en esta pantalla en modo de solo lectura.

Su tipología está lista para usarse. Puede seleccionarlo en propiedades de mensaje o en propiedades de plantilla de mensaje.

>[!NOTE]
>
>The **[!UICONTROL IP affinity]** field allows you to manage the affinities according to your configuration. Se definen en el archivo de configuración de la instancia. Si desea utilizar las afinidades, póngase en contacto con su administrador.

## Typology rules {#typology-rules}

Las reglas de tipología son reglas comerciales que se aplican durante la preparación de los mensajes. Se utilizan para comprobar si un mensaje es válido y cumple los criterios de calidad. También comprueban si cada miembro de la audiencia objetivo puede recibir el mensaje.

Typology rules are available under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Typologies]** &gt; **[!UICONTROL Typology rules]** menu.

Existen dos tipos de reglas:

* **Reglas de filtrado** : permite excluir una parte del objetivo del mensaje según los criterios definidos en una consulta, como perfiles en cuarentena o perfiles que ya se han enviado a un determinado número de correos electrónicos. See [Filtering rules](../../administration/using/filtering-rules.md).
* **Reglas de fatiga** : le permite definir un número máximo de mensajes por perfil para evitarlos. See [Fatigue rules](../../administration/using/fatigue-rules.md).
* **Reglas de control** : permitir al usuario comprobar la validez y la calidad de los mensajes antes de enviarlos, como visualización de caracteres, tamaño de mensaje SMS, formato de dirección, etc. See [Control rules](../../administration/using/control-rules.md).

Una regla de tipología solo se puede aplicar a un canal o a todos los canales.

![](assets/typology_channel.png)

In the **[!UICONTROL Properties]** of a typology rule, you can set its execution order. Cuando se deben aplicar varias reglas, el orden de ejecución de cada regla determina los que se deben procesar primero. For more on this, refer to the [Typology rules execution order](../../administration/using/about-typology-rules.md#typology-rules-execution-order) section.

![](assets/typology_rule-active.png)

A typology rule can be deactivated through its **[!UICONTROL Properties]** if you do not want the rule to be applied at the moment that the messages concerned by the rule are analyzed.

![](assets/typology_rule-order.png)

In the **[!UICONTROL Targeting context]** category, you can select the **Targeting dimension** and **Filtering dimension** depending on the data that you want to target.

By default, filtering is carried out on the **[!UICONTROL Profiles]**. For example, if the rule is aimed at a mobile application, the **[!UICONTROL Filtering dimension]** can be changed to **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Typology rules execution order {#typology-rules-execution-order}

Las reglas de tipología se ejecutan en un orden especificado durante las fases de segmentación, análisis y personalización de mensajes.

En el modo de operación estándar, las reglas se aplican en la secuencia siguiente:

1. Reglas de control, si se aplican al principio de la segmentación.
1. Reglas de filtrado:

   * Reglas nativas de aplicación para la cualificación de direcciones: dirección definida/dirección no verificada/dirección bloqueada/dirección de dirección en cuarentena.
   * Reglas de filtrado definidas por el usuario.

1. Reglas de control, si se aplican al final de la segmentación.
1. Reglas de control, si se aplican al principio de la personalización.
1. Reglas de control, si se aplican al final de la personalización.

Sin embargo, puede adaptar el orden de ejecución del mismo tipo de reglas en cada tipología. De hecho, cuando se ejecutan varias reglas durante la misma fase de procesamiento de mensaje, puede elegir el orden en que se aplican.

Por ejemplo, una regla de filtrado cuyo orden de ejecución se coloque en el número 20 se ejecutará antes de una regla de filtrado cuyo orden de ejecución se coloque en el número 30.
