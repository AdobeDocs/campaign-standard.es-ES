---
title: '"Caso de uso del flujo de trabajo: Entrega en varios canales"'
description: '"Caso de uso del flujo de trabajo: Entrega en varios canales"'
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
source-git-commit: f959441647d1fea41ecce2fc41e3cad3cb536bac

---


# Caso de uso del flujo de trabajo: Creación de una entrega multicanal{#cross-channel-delivery}

Este documento le permite descubrir la siguiente funcionalidad de Adobe Campaign mediante un caso de uso estándar: creación de un flujo de trabajo de entrega multicanal.

El objetivo aquí es seleccionar una audiencia entre los destinatarios de la base de datos y segmentarla en dos grupos diferentes con el objetivo de enviar un correo electrónico al primer grupo y un mensaje SMS al segundo grupo.

![](assets/wkf_segment_overview.png)

Para obtener más información sobre los flujos de trabajo y los distintos canales disponibles en Adobe Campaign, consulte los siguientes documentos:

* [Descubrimiento de flujos de trabajo](../../automating/using/discovering-workflows.md)
* [Descubrimiento de canales de comunicación](../../channels/using/discovering-communication-channels.md)

## Creación de un flujo de trabajo {#creating-workflow}

Para enviar dos entregas diferentes a un grupo determinado, primero debe definir el objetivo.

Para ello, deberá crear una consulta para identificar a los destinatarios y, por lo tanto, deberá crear un flujo de trabajo.

Cree un nuevo flujo de trabajo en el programa o en la campaña que desee:

1. En **[!UICONTROL Marketing Activities]**, haga clic**[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]**como tipo de flujo de trabajo y haga clic en**[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

Los pasos detallados para crear un flujo de trabajo se presentan en la sección [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md) .

## Creación de una actividad de consulta {#creating-query-activity}

Una vez creado el flujo de trabajo, puede acceder a su interfaz.

Inserte una actividad de consulta en el flujo de trabajo para segmentar los perfiles que recibirán los envíos.

1. En **[!UICONTROL Activities]**>**[!UICONTROL Targeting]**, arrastre y suelte una **[!UICONTROL Query activity]**.
1. Haga doble clic en la actividad.
1. En la **[!UICONTROL Target]**ficha, examine los métodos abreviados y seleccione una de las[audiencias](../../audiences/using/about-audiences.md).
1. Arrastre y suelte el acceso directo en la zona de edición. Según el tipo de acceso directo seleccionado, aparecerá una ventana.
1. Configure los elementos de objetivo y confirme la consulta.

![](assets/wkf_segment_query.png)

Puede crear una consulta en uno o varios elementos.

Utilice el **[!UICONTROL Count]**botón para ver una estimación del número de perfiles dirigidos por la consulta.

Los pasos detallados para crear una actividad de consulta se presentan en la sección [Consulta](../../automating/using/query.md) .

## Creación de una actividad de segmentación {#creating-segmentation-activity}

Una vez identificado el objetivo por la actividad Consulta, debe seleccionar un criterio para segmentar el objetivo en dos poblaciones diferentes: uno recibirá un correo electrónico y el otro recibirá un SMS.

Debe utilizar una actividad de segmentación para crear uno o varios segmentos a partir de una población calculada en sentido ascendente en una consulta.

![](assets/wkf_segment_activity.png)

El grupo **Correo electrónico** se dirigirá a los destinatarios que tengan una dirección de correo electrónico definida pero no un número de teléfono móvil. El grupo **SMS** contendrá los destinatarios cuyo número de teléfono móvil se guardará en su perfil.

Para configurar la primera transición (correo electrónico):

1. En la **[!UICONTROL Segments]**ficha, hay un primer segmento presente de forma predeterminada. Edite sus propiedades para configurar ese segmento.

   ![](assets/wkf_segment_properties.png)

1. Seleccione el perfil **[!UICONTROL Email]**como criterio de filtrado.

   ![](assets/wkf_segment_email.png)

1. En la nueva ventana que aparece en la pantalla, seleccione el **[!UICONTROL Is not empty]**operador.

   ![](assets/wkf_segment_email_not_empty.png)

1. Agregue un segundo criterio de filtrado **[!UICONTROL Mobile]**y seleccione el operador**[!UICONTROL Is empty]**.

   ![](assets/wkf_segment_mobile_empty.png)

   Todos los perfiles procedentes de la consulta que tengan un correo electrónico, pero no un número de teléfono móvil definido, estarán en esta transición.

1. Para que el flujo de trabajo sea más claro, puede editar la etiqueta de transición. Confirme los cambios.

   ![](assets/wkf_segment_transition_label.png)

Se ha configurado la primera transición. Para configurar la segunda transición (SMS):

1. Haga clic en el **[!UICONTROL Add an element]**botón para agregar una nueva transición.
1. Defina una condición que le permita recuperar todos los perfiles cuyos números de teléfono móvil se hayan proporcionado. Para ello, cree una regla en el **[!UICONTROL Mobile]**campo con el operador**[!UICONTROL Is not empty]** lógico.

   ![](assets/wkf_segment_mobile_not_empty.png)

   Todos los perfiles que provienen de la consulta y que tienen un número de teléfono móvil definido estarán en esta transición.

1. Puede editar la etiqueta de la transición. Confirme los cambios.

La segunda transición ya está configurada.

![](assets/wkf_segment_transitions.png)

Los pasos detallados para crear una actividad de segmentación se presentan en la sección [Segmentación](../../automating/using/segmentation.md) .

## Creación de envíos {#creating-deliveries}

Como ya se han creado dos transiciones, ahora debe agregar dos tipos de entregas a las transiciones de salida de la actividad de segmentación: un **[!UICONTROL Email delivery]**y un**[!UICONTROL SMS delivery]**.

Adobe Campaign permite agregar entregas a un flujo de trabajo. Para ello, seleccione una entrega en la **[!UICONTROL Channels]**categoría de la paleta de actividades del flujo de trabajo.

![](assets/wkf_segment_deliveries1.png)

Para crear una entrega por correo electrónico:

1. Arrastre y suelte un **[!UICONTROL Email delivery]**segmento después del primero.
1. Haga doble clic en la actividad para editarla.
1. Select **[!UICONTROL Simple email]**.
1. Seleccione **[!UICONTROL Add an outbound transition with the population]**y haga clic en**[!UICONTROL Next]**.

   ![](assets/wkf_segment_deliveries2.png)

   La transición saliente le permitirá recuperar la población y los registros de seguimiento. Podrá usar esto, por ejemplo, para enviar un segundo correo a las personas que no hicieron clic en el primer correo.

1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, seleccione **[!UICONTROL Use the Email Designer]**.
1. Edite y guarde el contenido.
1. En la **[!UICONTROL Schedule]**sección del tablero de mensajes, anule la selección de la opción**[!UICONTROL Solicitar confirmación antes de enviar mensajes}**.

Los pasos detallados para crear una actividad de correo electrónico se presentan en la sección Envío por [correo electrónico](../../automating/using/email-delivery.md) .

Para crear una entrega de SMS:

1. Arrastre y suelte un **[!UICONTROL SMS delivery]**segmento después del otro.
1. Haga doble clic en la actividad para editarla.
1. Seleccione **[!UICONTROL SMS]**y haga clic en**[!UICONTROL Next]**.
1. Seleccione una plantilla SMS y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de SMS y haga clic en **[!UICONTROL Next]**.
1. Edite y guarde el contenido.

Los pasos detallados para construir una actividad de SMS se presentan en la sección de envío [de](../../automating/using/sms-delivery.md) SMS.

Una vez que se hayan creado y editado los envíos, el flujo de trabajo estará listo para iniciarse.

![](assets/wkf_segment_deliveries.png)

## Ejecución del flujo de trabajo {#running-the-workflow}

Una vez iniciado el flujo de trabajo, la población segmentada por la actividad Consulta se segmentará para recibir un envío por correo electrónico o por SMS.

Para ejecutar el flujo de trabajo, haga clic en el **[!UICONTROL Start]**botón de la barra de acciones.

Puede acceder a las entregas desde el menú **[!UICONTROL Marketing plans]**>**[!UICONTROL Marketing activities]** avanzado a través del logotipo de Adobe Campaign. Haga clic en el envío y, a continuación, en el **[!UICONTROL Reports]**botón para acceder a los informes[de](../../reporting/using/about-dynamic-reports.md#accessing-dynamic-reports)envío, como el resumen de envío, la velocidad de apertura o la representación por correo electrónico según la bandeja de entrada de mensajes de los destinatarios.