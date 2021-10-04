---
title: Enriquecimiento de datos de perfil con datos contenidos en un archivo
description: Este ejemplo muestra cómo enriquecer datos de perfil con datos de compra contenidos en un archivo.
audience: automating
content-type: reference
topic-tags: targeting-activities
context-tags: enrichment,main
feature: Workflows
role: Data Architect
level: Intermediate
exl-id: d5c19884-5a3e-4676-899c-53074a3b0efc
source-git-commit: ee7539914aba9df9e7d46144e437c477a7e52168
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 75%

---

# Enriquecimiento de datos de perfil con datos contenidos en un archivo {#enriching-profile-data-with-data-contained-in-a-file}

Este ejemplo muestra cómo enriquecer datos de perfil con datos de compra contenidos en un archivo. Aquí consideramos que los datos de compra se almacenan en un sistema de terceros. Cada perfil puede tener varias compras almacenadas en el archivo. El objetivo final del flujo de trabajo es enviar un mensaje de correo electrónico a los perfiles de destino que han comprado al menos dos artículos para agradecerles su lealtad.

El flujo de trabajo se configura de la siguiente manera:

![](assets/enrichment_example_workflow.png)

* Una actividad [Query](../../automating/using/query.md) dirigida a los perfiles que recibirán el mensaje.
* Una actividad [Load file](../../automating/using/load-file.md) que carga los datos de compra. Por ejemplo:

   ```
   tcode;tdate;customer;product;tamount
   aze123;21/05/2017;dannymars@example.com;TV;799
   aze124;28/05/2017;dannymars@example.com;Headphones;8
   aze125;31/07/2017;john.smith@example.com;Headphones;8
   aze126;14/12/2017;john.smith@example.com;Plastic Cover;4
   aze127;02/01/2018;dannymars@example.com;Case Cover;79
   aze128;04/03/2017;clara.smith@example.com;Phone;149
   ```

   Con este archivo de ejemplo, utilice la dirección de correo electrónico para reconciliar los datos con los perfiles de la base de datos. También puede habilitar ID únicos como se describe en [este documento](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).

* Una actividad [Enrichment](../../automating/using/enrichment.md) que crea un vínculo entre los datos de transacción cargados desde el archivo y los perfiles seleccionados en **[!UICONTROL Query]**. El vínculo se define en la pestaña **[!UICONTROL Advanced relations]** de la actividad. El vínculo se basa en la transición proveniente de la actividad de **[!UICONTROL Load file]**. Utiliza el campo “correo electrónico” del recurso de perfil y la columna “cliente” del archivo importado como criterios de reconciliación.

   ![](assets/enrichment_example_workflow2.png)

   Una vez creado el vínculo, se añaden dos conjuntos de **[!UICONTROL Additional data]**:

   * Recopilación de dos líneas correspondientes a las dos últimas transacciones de cada perfil. Para esta recopilación, el nombre del producto, la fecha de transacción y el precio del producto se añaden como datos adicionales. Se aplica un orden descendente a los datos. Para crear la recopilación, en la pestaña **[!UICONTROL Additional data]**:

      Seleccione el vínculo previamente definido en la pestaña **[!UICONTROL Advanced relations]** de la actividad.

      ![](assets/enrichment_example_workflow3.png)

      Marque **[!UICONTROL Collection]** y especifique el número de líneas que desea recuperar (2 en este ejemplo). En esta pantalla, puede personalizar el **[!UICONTROL Alias]** y la **[!UICONTROL Label]** de la recopilación. Estos valores están visibles en las siguientes actividades del flujo de trabajo al hacer referencia a esta recopilación.

      ![](assets/enrichment_example_workflow4.png)

      Como **[!UICONTROL Data]** que se deben conservar para la recopilación, seleccione las columnas que se deben usar en el envío final.

      ![](assets/enrichment_example_workflow6.png)

      Aplique un orden descendente en la fecha de transacción para asegurarse de recuperar las más recientes.

      ![](assets/enrichment_example_workflow7.png)

   * Un recuento acumulado del número total de transacciones para cada perfil. Este recuento se utiliza más adelante para filtrar perfiles que tengan al menos dos transacciones registradas. Para crear el recuento, en la pestaña **[!UICONTROL Additional data]**:

      Seleccione el vínculo previamente definido en la pestaña **[!UICONTROL Advanced relations]** de la actividad.

      ![](assets/enrichment_example_workflow3.png)

      Seleccione **[!UICONTROL Aggregate]**.

      ![](assets/enrichment_example_workflow8.png)

      Como **[!UICONTROL Data]** que se deben mantener, defina la opción de recuento **Contar todo**. Si es necesario, especifique un alias personalizado para buscarlo más rápido en las siguientes actividades.

      ![](assets/enrichment_example_workflow9.png)

* Una actividad [Segmentation](../../automating/using/segmentation.md) con un solo segmento, que recupera perfiles del destinatario inicial que tienen al menos dos transacciones registradas. Se excluyen los perfiles con una sola transacción. Para ello, la consulta de la segmentación se realiza en el recuento acumulado definido anteriormente.

   ![](assets/enrichment_example_workflow5.png)

* Una actividad [Email delivery](../../automating/using/email-delivery.md) que utiliza los datos adicionales definidos en el **[!UICONTROL Enrichment]** para recuperar dinámicamente las dos últimas compras realizadas por el perfil. Los datos adicionales se pueden encontrar en el nodo **Datos adicionales (TargetData)** al añadir un campo de personalización.

   ![](assets/enrichment_example_workflow10.png)

**Temas relacionados:**

* [Enriquecimiento de los perfiles de los clientes con datos externos](https://helpx.adobe.com/es/campaign/kb/simplify-campaign-management.html#Managedatatofuelengagingexperiences)
