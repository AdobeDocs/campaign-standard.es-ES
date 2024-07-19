---
title: Ejemplos de consultas
description: Esta sección presenta un caso de uso al utilizar una actividad de consulta.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: query,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: 0a71e3a7-60e6-49ec-af2e-099ad0d69a15
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 76%

---

# Ejemplos de consultas {#query-samples}

Esta sección presenta un caso de uso al usar una actividad **[!UICONTROL Query]**. Para obtener más información sobre cómo usar una actividad **[!UICONTROL Query]**, consulte [esta sección](../../automating/using/query.md).

## Segmentación en atributos de perfil simples {#targeting-on-simple-profile-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para segmentar hombres de entre 18 y 30 años que viven en Londres.

![](assets/query_sample_1.png)

## Segmentación en atributos de correo electrónico {#targeting-on-email-attributes}

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de segmentación con el dominio de dirección de correo electrónico &quot;orange.co.uk&quot;.

![](assets/query_sample_emaildomain.png)

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destinatario cuya dirección de correo electrónico se ha proporcionado.

![](assets/query_sample_emailnotempty.png)

## Segmentación de perfiles cuyo cumpleaños es hoy {#targeting-profiles-whose-birthday-is-today}

El siguiente ejemplo muestra una actividad de consulta configurada para perfiles de destinatario cuyo cumpleaños es hoy.

1. Arrastre el filtro **[!UICONTROL Birthday]** a la consulta.

   ![](assets/query_sample_birthday.png)

1. Configure el **[!UICONTROL Filter type]** en **[!UICONTROL Relative]** y seleccione **[!UICONTROL Today]**.

   ![](assets/query_sample_birthday2.png)

## Segmentación de perfiles que abrieron un envío específico {#targeting-profiles-who-opened-a-specific-delivery}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles que abrieron el envío con la etiqueta &quot;Hora de verano&quot;.

1. Arrastre el filtro **[!UICONTROL Opened]** a la consulta.

   ![](assets/query_sample_opened.png)

1. Seleccione el envío y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/query_sample_opened2.png)

## Segmentación de perfiles para los que los envíos fallaron por un motivo específico {#targeting-profiles-for-whom-deliveries-failed-for-a-specific-reason}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles para los que los envíos fallaron porque el buzón estaba lleno. Esta consulta solo está disponible para usuarios con derechos de administración y pertenecientes a las unidades organizativas **[!UICONTROL All (all)]** (consulte [esta sección](../../administration/using/organizational-units.md)).

1. Seleccione el recurso **[!UICONTROL Delivery logs]** para filtrar directamente en la tabla de registro de envíos (consulte [Uso de recursos diferentes de dimensiones de segmentación](../../automating/using/using-resources-different-from-targeting-dimensions.md)).

   ![](assets/query_sample_failure1.png)

1. Arrastre el filtro **[!UICONTROL Nature of failure]** a la consulta.

   ![](assets/query_sample_failure2.png)

1. Seleccione el tipo de fallo que desea segmentar. En nuestro caso, es **[!UICONTROL Mailbox full]**.

   ![](assets/query_sample_failure3.png)

## Segmentación de perfiles no contactados durante los últimos 7 días {#targeting-profiles-not-contacted-during-the-last-7-days}

El siguiente ejemplo muestra una actividad de consulta configurada para filtrar perfiles a los que no se ha contactado durante los últimos 7 días.

1. Arrastre el filtro **[!UICONTROL Delivery logs (logs)]** a la consulta.

   ![](assets/query_sample_7days.png)

   Seleccione **[!UICONTROL Does not exist]** en la lista desplegable y arrastre el filtro **[!UICONTROL Delivery]**.

   ![](assets/query_sample_7days1.png)

1. Configure el filtro como se muestra a continuación.

   ![](assets/query_sample_7days2.png)

## Segmentación de perfiles que hicieron clic en un vínculo específico {#targeting-profiles-who-clicked-a-specific-link-}

1. Arrastre el filtro **[!UICONTROL Tracking logs (tracking)]** a la consulta.

   ![](assets/query_sample_trackinglogs.png)

1. Arrastre el filtro **[!UICONTROL Label (urlLabel)]**.

   ![](assets/query_sample_trackinglogs2.png)

1. En el campo **[!UICONTROL Value]**, escriba la etiqueta que se definió al insertar el vínculo en el envío y confirme.

   ![](assets/query_sample_trackinglogs3.png)
