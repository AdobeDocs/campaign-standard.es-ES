---
title: Ejemplos de consultas
description: Esta sección presenta el caso de uso al utilizar una actividad de Consulta.
page-status-flag: never-activated
uuid: b3c629fa-370e-481c-b347-fcf9f5a5e847
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: targeting-activities
discoiquuid: 8d46ce28-0101-4f13-865a-2208ed6d6139
context-tags: query,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 2d994d85f126951215f1227301599c554c1f12c8
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---


# Ejemplos de consultas {#query-samples}

Esta sección presenta el caso de uso al utilizar una **[!UICONTROL Query]** actividad. For more on how to use a **[!UICONTROL Query]** activity, refer to [this section](../../automating/using/query.md).

## Targeting on simple profile attributes {#targeting-on-simple-profile-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para destinatario de hombres de entre 18 y 30 años que viven en Londres.

![](assets/query_sample_1.png)

## Objetivo en atributos de correo electrónico {#targeting-on-email-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destinatario con el dominio de dirección de correo electrónico &quot;orange.co.uk&quot;.

![](assets/query_sample_emaildomain.png)

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destinatario cuya dirección de correo electrónico se ha proporcionado.

![](assets/query_sample_emailnotempty.png)

## Dirigirse a perfiles cuyo cumpleaños es hoy {#targeting-profiles-whose-birthday-is-today}

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destinatario cuyo cumpleaños es hoy.

1. Arrastre el **[!UICONTROL Birthday]** filtro en la consulta.

   ![](assets/query_sample_birthday.png)

1. Configure el **[!UICONTROL Filter type]** en **[!UICONTROL Relative]** y seleccione **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## perfiles de objetivo que abrieron un envío específico {#targeting-profiles-who-opened-a-specific-delivery}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles que abrieron el envío con la etiqueta &quot;Hora de verano&quot;.

1. Arrastre el **[!UICONTROL Opened]** filtro en la consulta.

   ![](assets/query_sample_opened.png)

1. Seleccione el envío y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## perfiles de objetivo para los que los envíos fallaron por un motivo específico {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles para los que los envíos fallaron porque su buzón estaba lleno. Esta consulta sólo está disponible para usuarios con derechos de administración y pertenecientes a las **[!UICONTROL All (all)]** unidades organizativas (ver [esta sección](../../administration/using/organizational-units.md)).

1. Seleccione el **[!UICONTROL Delivery logs]** recurso para filtrar directamente en la tabla de registro de envíos (consulte [Uso de recursos diferentes de dimensiones de segmentación](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Arrastre el **[!UICONTROL Nature of failure]** filtro en la consulta.

   ![](assets/query_sample_failure2.png)

1. Seleccione el tipo de error que desee destinatario. En nuestro caso **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## No se contactó con perfiles de objetivos durante los últimos 7 días {#targeting-profiles-not-contacted-during-the-last-7-days}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles a los que no se ha contactado durante los últimos 7 días.

1. Arrastre el **[!UICONTROL Delivery logs (logs)]** filtro en la consulta.

   ![](assets/query_sample_7days.png)

   Seleccione **[!UICONTROL Does not exist]** en la lista desplegable y arrastre el **[!UICONTROL Delivery]** filtro.

   ![](assets/query_sample_7days1.png)

1. Configure el filtro como se muestra a continuación.

   ![](assets/query_sample_7days2.png)

## perfiles de objetivo que hicieron clic en un vínculo específico {#targeting-profiles-who-clicked-a-specific-link-}

1. Arrastre el **[!UICONTROL Tracking logs (tracking)]** filtro en la consulta.

   ![](assets/query_sample_trackinglogs.png)

1. Arrastre el **[!UICONTROL Label (urlLabel)]** filtro.

   ![](assets/query_sample_trackinglogs2.png)

1. En el **[!UICONTROL Value]** campo, escriba la etiqueta que se definió al insertar el vínculo en el envío y confirme.

   ![](assets/query_sample_trackinglogs3.png)
