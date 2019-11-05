---
title: Reglas de filtrado
description: Utilice las reglas de filtrado para reducir la audiencia de los mensajes.
page-status-flag: nunca activado
uuid: ed3eea62-3a47-4318-ae22-d82aa857448f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administración
content-type: referencia
topic-tags: reglas de trabajo con tipología
discoiquuid: 7ddaf36c-74e6-4501-b3eb-3d03f005aaa6
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Reglas de filtrado{#filtering-rules}

Las reglas de filtrado permiten excluir una parte del objetivo de mensaje según los criterios definidos en una consulta, como perfiles en cuarentena o perfiles que ya se han enviado un determinado número de correos electrónicos.

Por ejemplo, puede filtrar los suscriptores de la newsletter para que los suscriptores menores de 18 años nunca reciban comunicaciones.

## Creación de una regla de filtrado {#creating-a-filtering-rule}

1. Cree una regla de tipología de **filtrado** que se pueda aplicar a todos los canales de comunicación.

   ![](assets/typology_create-rule.png)

1. En la **[!UICONTROL Filtering criteria]** ficha, seleccione las suscripciones de la **[!UICONTROL Subscription]** categoría.

   ![](assets/typology_create-rule-subscription.png)

1. En la **[!UICONTROL Explorer]** ficha del editor de consultas, arrastre y suelte el **[!UICONTROL Subscriber]** nodo en la parte principal de la pantalla.

   ![](assets/typology_create-rule-subscriber.png)

1. Seleccione el **[!UICONTROL Age]** campo y defina las condiciones de filtrado para que la edad de los suscriptores sea de 18 años o más.

   ![](assets/typology_create-rule-age.png)

1. En la **[!UICONTROL Typologies]** ficha, vincule esta regla a una tipología.

   ![](assets/typology_create-rule-typology.png)

1. Asegúrese de que la tipología en cuestión está seleccionada en la plantilla de envío que desea utilizar.

   ![](assets/typology_template.png)

   >[!NOTE]
   >
   >Para acceder a las plantillas de envío, seleccione **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** en el menú de navegación, al que se puede acceder desde el logotipo de Adobe Campaign.

Siempre que se utilice esta regla en un mensaje, los suscriptores que se consideren menores de edad se excluirán automáticamente.

## Restricción de la aplicabilidad de una regla de filtrado {#restricting-the-applicability-of-a-filtering-rule}

Puede restringir la aplicabilidad de una regla de filtrado según el mensaje que se va a enviar.

1. En la **[!UICONTROL Application criteria]** ficha de la regla de tipología, desactive la **[!UICONTROL Apply the rule on all deliveries]** opción, que está activada de forma predeterminada.

   ![](assets/typology_limit.png)

1. Utilice el editor de consultas para definir un filtro. Por ejemplo, puede aplicar la regla solo a los mensajes cuya etiqueta comience por una palabra determinada o cuyo ID contenga determinadas letras.

   ![](assets/typology_limit-rule.png)

En este caso, la regla solo se aplica a los mensajes que corresponden a los criterios definidos.

## Reglas de exclusión de envío predeterminadas {#default-deliverability-exclusion-rules}

Two filtering rules are available by default: **[!UICONTROL Exclusion of addresses]** ( **[!UICONTROL addressExclusions]** ) and **[!UICONTROL Exclusion of domains]** ( **[!UICONTROL domainExclusions]** ). Durante el análisis del correo electrónico, estas reglas comparan las direcciones de correo de los destinatarios con las direcciones o nombres de dominio prohibidos incluidos en una lista de supresión global encriptada que se administra en la instancia de envío. Si se encuentra una coincidencia, el mensaje no se envía a ese destinatario.

El objetivo de esto es evitar que se añada el servicio a una lista negra de actividad maliciosa, especialmente a través de Spamtrap. Por ejemplo, si se utiliza un Spamtrap para suscribirse a través de uno de sus formularios Web, se envía un mensaje de correo electrónico de confirmación automáticamente a ese Spamtrap y esto hace que añada su dirección automáticamente a la lista negra.

>[!NOTE]
>
>Las direcciones y los nombres de dominio contenidos en la lista de supresión global están ocultos. En los registros de análisis de envío solo se indica el número de destinatarios excluidos.

