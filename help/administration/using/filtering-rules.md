---
title: Reglas de filtrado
seo-title: Reglas de filtrado
description: Reglas de filtrado
seo-description: Utilice reglas de filtrado para restringir la audiencia de sus mensajes.
page-status-flag: no activado nunca
uuid: ed 3 eea 62-3 a 47-4318-ae 22-d 82 aa 857448 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: administración
content-type: reference
topic-tags: working-with-typology-rules
discoiquuid: 7 ddaf 36 c -74 e 6-4501-b 3 eb -3 d 03 f 005 aaa 6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Filtering rules{#filtering-rules}

Las reglas de filtrado permiten excluir una parte del objetivo del mensaje según los criterios definidos en una consulta, como perfiles en cuarentena o perfiles que ya se han enviado a un determinado número de correos electrónicos.

Por ejemplo, puede filtrar los suscriptores del boletín informativo para que los suscriptores que tengan menos de 18 años nunca reciban comunicaciones.

## Creating a filtering rule {#creating-a-filtering-rule}

1. Create a **Filtering** typology rule, one that can be applied on all communication channels.

   ![](assets/typology_create-rule.png)

1. In the **[!UICONTROL Filtering criteria]** tab, select the subscriptions in the **[!UICONTROL Subscription]** category.

   ![](assets/typology_create-rule-subscription.png)

1. In the **[!UICONTROL Explorer]** tab of the query editor, drag and drop the **[!UICONTROL Subscriber]** node into the main part of the screen.

   ![](assets/typology_create-rule-subscriber.png)

1. Select the **[!UICONTROL Age]** field and define the filtering conditions so that the age of the subscribers is 18 or above.

   ![](assets/typology_create-rule-age.png)

1. In the **[!UICONTROL Typologies]** tab, link this rule to a typology.

   ![](assets/typology_create-rule-typology.png)

1. Asegúrese de que la tipología en cuestión está seleccionada en la plantilla de entrega que desee utilizar.

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >To access the delivery templates, select **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** in the navigation menu, which can be accessed via the Adobe Campaign logo.

Siempre que se utilice esta regla en un mensaje, los suscriptores considerados menores se excluirán automáticamente.

## Restricting the applicability of a filtering rule {#restricting-the-applicability-of-a-filtering-rule}

Puede restringir la aplicabilidad de una regla de filtrado según el mensaje que se va a enviar.

1. In the typology rule's **[!UICONTROL Application criteria]** tab, uncheck the **[!UICONTROL Apply the rule on all deliveries]** option, which is enabled by default.

   ![](assets/typology_limit.png)

1. Utilice el editor de consultas para definir un filtro. Por ejemplo, puede aplicar la regla únicamente en mensajes cuya etiqueta comience con una palabra dada o cuyo ID contenga determinadas letras.

   ![](assets/typology_limit-rule.png)

En este caso, la regla solo se aplica a los mensajes que se corresponden con los criterios definidos.

## Default deliverability exclusion rules {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). Durante el análisis de correo electrónico, estas reglas comparan las direcciones de correo electrónico del destinatario con las direcciones o los nombres de dominio prohibidos de una lista de supresión global cifrada administrada en la instancia de entrega. Si hay una coincidencia, el mensaje no se envía a dicho destinatario.

Esto es para evitar quedar bloqueados debido a una actividad malintencionada, especialmente el uso de un reventado. Por ejemplo, si se utiliza un reventado para suscribirse a través de uno de los formularios Web, se envía automáticamente un mensaje de correo electrónico de confirmación a ese reventado, por lo que la dirección se bloquea automáticamente.

>[!NOTE]
>
>Las direcciones y los nombres de dominio contenidos en la lista de supresión global están ocultos. En los registros de análisis de entrega solo se indica el número de destinatarios excluidos.

