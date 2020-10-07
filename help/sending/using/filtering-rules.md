---
title: Reglas de filtrado
description: Utilice las reglas de filtrado para reducir la audiencia de los mensajes.
page-status-flag: never-activated
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 14%

---


# Reglas de filtrado {#filtering-rules}

Las reglas de filtrado permiten excluir una parte del destinatario de mensajes según los criterios definidos en una consulta, como perfiles en cuarentena o perfiles que ya se han enviado un determinado número de correos electrónicos.

## Reglas de tipología de filtrado predeterminadas {#default-filtering-typology-rules}

La tabla siguiente proporciona información sobre las reglas de filtrado integradas, así como sus canales relacionados.

| Etiqueta | Canal | Descripción |
---------|----------|---------
| **[!UICONTROL Address not specified]** | Todo | Excluye la población de destinatarios sin dirección especificada (correo electrónico, dirección postal, etc.) según el canal seleccionado). |
| **[!UICONTROL Address on denylist]** | Todo | Excluye las direcciones que se encuentran en la lista de bloqueados. |
| **[!UICONTROL Duplicate]** | Todo | Excluye duplicados en función del campo de población de destinatarios **[!UICONTROL Address]** . |
| **[!UICONTROL Exclude mobile applications]** | Aplicación móvil | Excluye las suscripciones de la aplicación que no coinciden con la aplicación móvil definida en el mensaje. |
| **[!UICONTROL Exclude mobile applications for In-App]** | En la aplicación | Excluye las suscripciones de la aplicación que no coinciden con la aplicación móvil definida en el mensaje (plantilla en la aplicación). |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | En la aplicación | Excluye las suscripciones de la aplicación que no coinciden con la aplicación móvil definida en el mensaje (plantilla de retransmisión en la aplicación) |
| **[!UICONTROL Exclude mobile applications for Push]** | Aplicación móvil | Excluye las suscripciones de la aplicación que no coinciden con la aplicación móvil definida en el mensaje (para push) |
| **[!UICONTROL Quarantined address]** | Todo | Excluye direcciones en cuarentena. |
| **[!UICONTROL Target limited in size]** | Todo | Comprueba si se ha alcanzado el tamaño máximo de envío para el destinatario. Se aplica a envíos de correo directo con la opción &quot;límite de envíos&quot; activada. |

Además de estas reglas de filtrado predeterminadas, hay dos reglas de exclusión disponibles:

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

Durante el análisis del correo electrónico, estas reglas comparan las direcciones de correo de los destinatarios con las direcciones o nombres de dominio prohibidos incluidos en una lista de supresión global encriptada que se administra en la instancia de envío. Si se encuentra una coincidencia, el mensaje no se envía a ese destinatario.

Esto es para evitar ser agregado a la  de lista de bloqueados debido a actividad maliciosa, especialmente el uso de Spamtrampa. Por ejemplo, si se utiliza un Spamtrampa para suscribirse a través de uno de sus formularios web, se enviará automáticamente un correo electrónico de confirmación a dicho Spamtrampa, lo que hará que su dirección se añada automáticamente a la  de lista de bloqueados.

>[!NOTE]
>
>Las direcciones y los nombres de dominio contenidos en la lista de supresión global están ocultos. En los registros de análisis de envío solo se indica el número de destinatarios excluidos.

## Creación de una regla de filtrado {#creating-a-filtering-rule}

Puede crear sus propias reglas de filtrado según sus necesidades. Por ejemplo, puede filtrar la población de destinatarios de las newsletters para que los suscriptores menores de 18 años nunca reciban comunicaciones.

Para crear una reglas de tipología de filtrado, siga estos pasos:

1. Cree una nueva reglas de tipología. The main steps to create typology rules are detailed in [this section](../../sending/using/managing-typology-rules.md).

1. Seleccione el tipo de **[!UICONTROL Filtering]** regla y luego especifique el canal que desee.

1. En la **[!UICONTROL Filtering criteria]** ficha, seleccione las suscripciones de la **[!UICONTROL Subscription]** categoría.

   ![](assets/typology_create-rule-subscription.png)

1. En la **[!UICONTROL Explorer]** ficha del editor de consultas, arrastre y suelte el **[!UICONTROL Subscriber]** nodo en la parte principal de la pantalla.

   ![](assets/typology_create-rule-subscriber.png)

1. Seleccione el **[!UICONTROL Age]** campo y defina las condiciones de filtrado para que la edad de los suscriptores sea de 18 años o más.

   ![](assets/typology_create-rule-age.png)

1. In the **[!UICONTROL Typologies]** tab, link this rule to a typology.

   ![](assets/typology_create-rule-typology.png)

1. Asegúrese de que la tipología está seleccionada en el envío o la Plantilla de envíos que desea utilizar. Para obtener más información, consulte [esta sección](../../sending/using/managing-typologies.md#applying-typologies-to-messages).

   ![](assets/typology_template.png)

Siempre que se utilice esta regla en un mensaje, los suscriptores que se consideren menores de edad se excluirán automáticamente.

## Configuración del contexto de objetivo de las reglas de filtrado {#configuring-filtering-rules-targeting-context}

Campaign Standard le permite configurar las dimensiones **Segmentación** y **Filtrado** para que se utilicen en función de los datos que desee destinatario.

Para ello, abra las propiedades de la reglas de tipología y, a continuación, acceda a la **[!UICONTROL Advanced information]** sección.

By default, filtering is carried out on the **[!UICONTROL Profiles]**. Por ejemplo, si la regla está dirigida a una aplicación móvil, **[!UICONTROL Filtering dimension]** se puede cambiar a **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

Puede restringir la aplicabilidad de una regla de filtrado según el mensaje que se va a enviar.

1. En la ficha **[!UICONTROL Application criteria]** de la reglas de tipología, desactive la opción **[!UICONTROL Apply the rule on all deliveries]** , que está activada de forma predeterminada.

   ![](assets/typology_limit.png)

1. Utilice el editor de consultas para definir un filtro. Por ejemplo, puede aplicar la regla solo a los mensajes cuya etiqueta inicio con una palabra determinada o cuyo ID contenga determinadas letras.

   ![](assets/typology_limit-rule.png)

En este caso, la regla solo se aplica a los mensajes que corresponden a los criterios definidos.
