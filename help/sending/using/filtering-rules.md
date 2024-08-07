---
title: Reglas de filtrado
description: Utilice reglas de filtrado para restringir la audiencia de sus mensajes.
audience: administration
content-type: reference
topic-tags: working-with-typology-rules
feature: Typology Rules
role: User
level: Intermediate
exl-id: 43e97f3c-ed82-4fcc-ac0d-fcee6a22da35
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 23%

---

# Reglas de filtrado {#filtering-rules}

Las reglas de filtrado le permiten excluir una parte del destinatario de mensajes según los criterios definidos en una consulta, como perfiles en cuarentena o perfiles que ya se han enviado un determinado número de correos electrónicos.

## Reglas de tipología de filtrado predeterminadas {#default-filtering-typology-rules}

La siguiente tabla proporciona información sobre las reglas de filtrado listas para usar, así como sus canales relacionados.

| Etiqueta | Canal | Descripción |
| ---------|----------|---------|
| **[!UICONTROL Address not specified]** | Todos | Excluye la población objetivo sin una dirección especificada (correo electrónico, dirección postal, etc.) según el canal seleccionado). |
| **[!UICONTROL Address on denylist]** | Todos | Excluye las direcciones que se encuentran en la lista de bloqueados de la. |
| **[!UICONTROL Duplicate]** | Todos | Excluye duplicados según el campo de población de destinatarios **[!UICONTROL Address]**. |
| **[!UICONTROL Exclude mobile applications]** | Aplicación móvil | Excluye las suscripciones de la aplicación que no coinciden con la aplicación móvil definida en el mensaje. |
| **[!UICONTROL Exclude mobile applications for In-App]** | En la aplicación | Excluye las suscripciones de la aplicación que no coinciden con la aplicación móvil definida en el mensaje (plantilla en la aplicación). |
| **[!UICONTROL Exclude mobile applications for In-App broadcast]** | En la aplicación | Excluye las suscripciones a aplicaciones que no coinciden con la aplicación móvil definida en el mensaje (plantilla de difusión en la aplicación) |
| **[!UICONTROL Exclude mobile applications for Push]** | Aplicación móvil | Excluye las suscripciones de la aplicación que no coinciden con la aplicación móvil definida en el mensaje (para push) |
| **[!UICONTROL Quarantined address]** | Todos | Excluye las direcciones en cuarentena. |
| **[!UICONTROL Target limited in size]** | Todos | Comprueba si se ha alcanzado el tamaño máximo de envío para el destino. Se aplica a los envíos de correo directo con la opción &quot;delivery limit&quot; activada. |

Además de estas reglas de filtrado predeterminadas, hay dos reglas de exclusión disponibles:

* **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** )
* **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ).

Durante el análisis del correo electrónico, estas reglas comparan las direcciones de correo de los destinatarios con las direcciones o nombres de dominio prohibidos incluidos en una lista de supresión global encriptada que se administra en la instancia de envío. Si se encuentra una coincidencia, el mensaje no se envía a ese destinatario.

El objetivo de esto es evitar que se incluya el servicio en una lista de bloqueados de actividad maliciosa, especialmente a través de Spamtrap. Por ejemplo, si se utiliza un Spamtrap para suscribirse a través de uno de sus formularios web, se envía un mensaje de correo electrónico de confirmación automáticamente a ese Spamtrap y esto hace que incluya su dirección lista de bloqueados automáticamente.

>[!NOTE]
>
>Las direcciones y los nombres de dominio contenidos en la lista de supresión global están ocultos. En los registros de análisis de envío solo se indica el número de destinatarios excluidos.

## Creación de una regla de filtrado {#creating-a-filtering-rule}

Puede crear sus propias reglas de filtrado según sus necesidades. Por ejemplo, puede filtrar la población objetivo de los boletines informativos para que los suscriptores menores de 18 años no reciban nunca comunicaciones.

Para crear una regla de tipología de filtrado, siga estos pasos:

1. Cree una nueva regla de tipología. Los pasos principales para crear reglas de tipología se detallan en [esta sección](../../sending/using/managing-typology-rules.md).

1. Seleccione el tipo de regla **[!UICONTROL Filtering]** y, a continuación, especifique el canal deseado.

1. En la ficha **[!UICONTROL Filtering criteria]**, seleccione las suscripciones en la categoría **[!UICONTROL Subscription]**.

   ![](assets/typology_create-rule-subscription.png)

1. En la ficha **[!UICONTROL Explorer]** del editor de consultas, arrastre y suelte el nodo **[!UICONTROL Subscriber]** en la parte principal de la pantalla.

   ![](assets/typology_create-rule-subscriber.png)

1. Seleccione el campo **[!UICONTROL Age]** y defina las condiciones de filtrado para que la edad de los suscriptores sea inferior a 18 años.

   ![](assets/typology_create-rule-age.png)

1. En la ficha **[!UICONTROL Typologies]**, vincule esta regla a una tipología.

   ![](assets/typology_create-rule-typology.png)

1. Asegúrese de que la tipología esté seleccionada en la entrega o en la plantilla de envíos que desee utilizar. Para obtener más información, consulte [esta sección](../../sending/using/managing-typologies.md#applying-typologies-to-messages).

   ![](assets/typology_template.png)

Siempre que se utilice esta regla en un mensaje, se excluirá automáticamente a los suscriptores que se consideren menores.

## Configuración del contexto de segmentación de reglas de filtrado {#configuring-filtering-rules-targeting-context}

El Campaign Standard le permite configurar las dimensiones **Segmentación** y **Filtrado** para usarlas según los datos a los que desee destinarlas.

Para ello, abra las propiedades de la regla de tipología y luego acceda a la sección **[!UICONTROL Advanced information]**.

De manera predeterminada, el filtrado se realiza en **[!UICONTROL Profiles]**. Por ejemplo, si la regla está dirigida a una aplicación móvil, **[!UICONTROL Filtering dimension]** se puede cambiar a **[!UICONTROL Subscriptions to an application]**.

![](assets/typology_rule-order_2.png)

## Restricción de la aplicabilidad de una regla de filtrado {#restricting-the-applicability-of-a-filtering-rule}

Puede restringir la aplicabilidad de una regla de filtrado según el mensaje que se va a enviar.

1. En la ficha **[!UICONTROL Application criteria]** de la regla de tipología, desmarque la opción **[!UICONTROL Apply the rule on all deliveries]**, que está habilitada de forma predeterminada.

   ![](assets/typology_limit.png)

1. Utilice el editor de consultas para definir un filtro. Por ejemplo, puede aplicar la regla solo en mensajes cuya etiqueta comience por una palabra determinada o cuyo ID contenga determinadas letras.

   ![](assets/typology_limit-rule.png)

En este caso, la regla solo se aplica a los mensajes que corresponden a los criterios definidos.
