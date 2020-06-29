---
title: envío entre canales
description: Este caso de uso muestra cómo crear un envío entre canales
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,wait,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 2%

---


# Creación de una entrega multicanal{#cross-channel-delivery}

Este documento le permite descubrir la siguiente funcionalidad de Adobe Campaign mediante un caso de uso estándar: creación de un flujo de trabajo de envío entre canales.

El objetivo aquí es seleccionar una audiencia de los destinatarios de la base de datos y segmentarla en dos grupos diferentes con el fin de enviar un correo electrónico al primer grupo y un mensaje SMS al segundo grupo.

![](assets/wkf_segment_overview.png)

Para obtener más información sobre los flujos de trabajo y los diferentes canales disponibles en Adobe Campaign, consulte los siguientes documentos:

* [Descubrimiento de flujos de trabajo](../../automating/using/get-started-workflows.md)
* [Descubrimiento de canales de comunicación](../../channels/using/get-started-communication-channels.md)

## Creación de un flujo de trabajo {#creating-workflow}

Para enviar dos envíos diferentes a un grupo determinado, primero debe definir el destinatario.

Para ello, deberá crear una consulta para identificar los destinatarios y, por lo tanto, deberá crear un flujo de trabajo.

Cree un nuevo flujo de trabajo en el programa o en la campaña que elija:

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

Los pasos detallados para crear un flujo de trabajo se presentan en la sección [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md) .

## Creating a Query activity {#creating-query-activity}

Una vez creado el flujo de trabajo, puede acceder a su interfaz.

Inserte una actividad de Consulta en el flujo de trabajo para destinatario de los perfiles que recibirán sus envíos.

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md) .
1. Haga clic con el Doble en la actividad.
1. En la **[!UICONTROL Target]** ficha, examine los métodos abreviados y seleccione una de sus [audiencias](../../audiences/using/about-audiences.md).
1. Arrastre y suelte el acceso directo en la zona de edición. Según el tipo de acceso directo seleccionado, aparecerá una ventana.
1. Configure los elementos de objetivo y confirme la consulta.

![](assets/wkf_segment_query.png)

Puede crear una consulta en uno o varios elementos.

Utilice el **[!UICONTROL Count]** botón para ver una estimación del número de perfiles objetivo por la consulta.

## Creación de una actividad de segmentación {#creating-segmentation-activity}

Una vez identificado el destinatario por la actividad de Consulta, debe seleccionar un criterio para segmentar el destinatario en dos poblaciones diferentes: uno recibirá un correo electrónico y el otro recibirá un SMS.

Debe utilizar una actividad [de segmentación](../../automating/using/segmentation.md) para crear uno o varios segmentos a partir de una población calculada en sentido ascendente en una consulta.

![](assets/wkf_segment_activity.png)

El grupo **Correo electrónico** destinatario los destinatarios que tienen una dirección de correo electrónico definida pero no un número de teléfono móvil. El grupo **SMS** contendrá los destinatarios cuyo número de teléfono móvil se guarda en su perfil.

Para configurar la primera transición (correo electrónico):

1. En la **[!UICONTROL Segments]** ficha, hay un primer segmento presente de forma predeterminada. Edite sus propiedades para configurar ese segmento.

   ![](assets/wkf_segment_properties.png)

1. Seleccione el perfil **[!UICONTROL Email]** como criterio de filtrado.

   ![](assets/wkf_segment_email.png)

1. En la nueva ventana que aparece en la pantalla, seleccione el **[!UICONTROL Is not empty]** operador.

   ![](assets/wkf_segment_email_not_empty.png)

1. Añada un segundo criterio de filtrado **[!UICONTROL Mobile]** y seleccione el operador **[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Todos los perfiles procedentes de la consulta que tengan un correo electrónico, pero no un número de teléfono móvil definido, estarán en esta transición.

1. Para que el flujo de trabajo sea más claro, puede editar la etiqueta de transición. Confirme los cambios.

   ![](assets/wkf_segment_transition_label.png)

Se ha configurado la primera transición. Para configurar la segunda transición (SMS):

1. Haga clic en el **[!UICONTROL Add an element]** botón para agregar una nueva transición.
1. Defina una condición que le permita recuperar todos los perfiles cuyos números de teléfono móvil se hayan proporcionado. Para ello, cree una regla en el **[!UICONTROL Mobile]** campo con el operador **[!UICONTROL Is not empty]** lógico.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Todos los perfiles procedentes de la consulta que tengan un número de teléfono móvil definido estarán en esta transición.

1. Puede editar la etiqueta de la transición. Confirme los cambios.

La segunda transición ahora también está configurada.

![](assets/wkf_segment_transitions.png)

## Creación de envíos {#creating-deliveries}

Como ya se han creado dos transiciones, ahora debe agregar dos tipos de envíos a las transiciones salientes de la actividad de segmentación: una actividad [de envío](../../automating/using/email-delivery.md) de correo electrónico y una actividad de envío [de](../../automating/using/sms-delivery.md) SMS.

Adobe Campaign le permite agregar envíos a un flujo de trabajo. Para ello, seleccione un envío de la **[!UICONTROL Channels]** categoría de la paleta actividad del flujo de trabajo.

![](assets/wkf_segment_deliveries1.png)

Para crear un envío de correo electrónico:

1. Arrastre y suelte una actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico después del primer segmento.
1. Haga clic con el Doble en la actividad para editarla.
1. Seleccione **[!UICONTROL Simple email]**.
1. Seleccione **[!UICONTROL Add an outbound transition with the population]** y haga clic en **[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   La transición saliente le permitirá recuperar la población y los registros de seguimiento. Podrá usar esto, por ejemplo, para enviar un segundo correo a las personas que no hicieron clic en el primer correo.

1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, seleccione **[!UICONTROL Use the Email Designer]**.
1. Edite y guarde el contenido.
1. En la **[!UICONTROL Schedule]** sección del panel de mensajes, anule la selección de la opción **[!UICONTROL Solicitar confirmación antes de enviar mensajes}** .

Para crear un envío SMS:

1. Arrastre y suelte una actividad de envío [](../../automating/using/sms-delivery.md) SMS después del otro segmento.
1. Haga clic con el Doble en la actividad para editarla.
1. Seleccione **[!UICONTROL SMS]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla SMS y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de SMS y haga clic en **[!UICONTROL Next]**.
1. Edite y guarde el contenido.

Una vez creados y editados los envíos, el flujo de trabajo estará listo para iniciarse.

![](assets/wkf_segment_deliveries.png)

## Ejecución del flujo de trabajo {#running-the-workflow}

Una vez iniciado el flujo de trabajo, la población objetivo de la **[!UICONTROL Query]** actividad se segmentará para recibir un envío de correo electrónico o SMS.

Para ejecutar el flujo de trabajo, haga clic en el **[!UICONTROL Start]** botón de la barra de acciones.

Puede acceder a sus envíos desde el menú **[!UICONTROL Marketing plans]** > **[!UICONTROL Marketing activities]** avanzado a través del logotipo del Adobe Campaign. Haga clic en el envío y, a continuación, en el **[!UICONTROL Reports]** botón para acceder a los [informes de envío](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports), como el resumen del envío, la velocidad de apertura o el procesamiento por correo electrónico según la bandeja de entrada del mensaje de destinatario.
