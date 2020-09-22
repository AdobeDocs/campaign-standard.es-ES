---
title: Añadir un grupo de control al enviar un mensaje
description: Aprenda a añadir un grupo de control al definir el destinatario de un mensaje con Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: execution-activities
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: workflow,use-case,query,segmentation,delivery
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cd38d849052e44e5a50c69d7f8184feb2227fdf4
workflow-type: tm+mt
source-wordcount: '1332'
ht-degree: 7%

---


# Adición de un grupo de control {#adding-control-group}

Puede utilizar grupos de control para evitar el envío de mensajes a una parte de la audiencia a fin de medir el impacto de sus campañas.

Para hacerlo en Adobe Campaign, cree un <b>grupo de control</b> al definir el destinatario del envío. Los perfiles se agregan al grupo de control aleatoriamente, se filtran o no, o se basan en criterios.

A continuación, podrá comparar el comportamiento de la población de destinatarios que recibió el mensaje con el comportamiento de los contactos que no estaban segmentados. En función de los registros de envío, también puede realizar el destinatario de un grupo de control en campañas futuras.

<!--The control group is built when the delivery is prepared.-->

## Información general {#overview}

El grupo de control se puede extraer aleatoriamente del destinatario principal y/o seleccionar de una población específica. Por lo tanto, hay dos formas principales de definir un grupo de control:
* **Extraiga** varios perfiles del destinatario principal.
* **Excluya** algunos perfiles según los criterios definidos en una consulta.

Puede utilizar ambos métodos al definir un grupo de control.

Todos los perfiles que formen parte del grupo de control en la fase de preparación del envío se eliminarán del destinatario principal. No recibirán el mensaje una vez que se envíe.

## Extracción de la población de destinatarios {#extraction-target-population}

Para definir un grupo de control, puede elegir extraer, aleatoriamente o en función de una ordenación, un porcentaje o un número fijo de perfiles de la población de destinatarios.

### Extracción destinatario {#target-extraction}

En primer lugar, defina la forma en que se extraerán los perfiles del destinatario: **aleatoriamente** o en función de una **clasificación**.

En la **[!UICONTROL Target extraction]** sección , seleccione una de las siguientes opciones:

* **[!UICONTROL Random sampling]**:: al preparar el envío, Adobe Campaign extraerá aleatoriamente un número de perfiles correspondiente al porcentaje o al número máximo que se establecerá como límite [de](#size-limit)tamaño.

   For example, if you then set the threshold to 10 in the **[!UICONTROL Limits]** section, the control group will be made up of 10% selected randomly from the targeted population.<!--Change screenshot to match example)-->

   ![](assets/control-group-random-sampling.png)

* **[!UICONTROL Keep only the first records after sorting]**: esta opción permite definir una limitación basada en uno o varios órdenes de clasificación.

   Por ejemplo:

   * Seleccione el **[!UICONTROL Age]** campo como criterio de ordenación.
   * Defina 100 como el umbral en la **[!UICONTROL Limits]** sección (consulte Límite [de](#size-limit)tamaño).
   * Leave the **[!UICONTROL Descending sort]** option checked.

   Como resultado, el grupo de control estará compuesto por los 100 destinatarios más antiguos.<!--Change screenshot to match example)-->

   ![](assets/control-group-keep-first-records.png)

   Puede ser interesante definir un grupo de control que incluya a perfiles que realizan pocas compras o con frecuencia, y comparar su comportamiento con el de los destinatarios con los que se contactó.

>[!NOTE]
>
>Seleccione **[!UICONTROL No extraction]** si no desea utilizar la **[!UICONTROL Target extraction]** opción.

<!--![](assets/control-group-no-extraction.png)-->

### Límite de tamaño {#size-limit}

Tanto si seleccionó **[!UICONTROL Random sampling]** como **[!UICONTROL Keep only the first records after sorting]**, debe definir cómo va a limitar el número de perfiles que extrae del destinatario principal. Realice una de las siguientes acciones:

* Seleccione **[!UICONTROL Size (as a % of the initial population)]** y rellene el marco correspondiente.

   Por ejemplo, si establece 10, en función de la opción seleccionada arriba, Adobe Campaign:
   * Extraer aleatoriamente el 10% de la población de destinatarios.
   * Si seleccionó el **[!UICONTROL Age]** campo como criterio de ordenación, extraiga los perfiles 10 % más antiguos de la población de destinatarios.

   >[!NOTE]
   >
   >Si desmarca la **[!UICONTROL Descending sort]** opción, se extraerán los perfiles más jóvenes en un 10 %.

* Seleccione **[!UICONTROL Maximum size]** y rellene el marco correspondiente.

   Por ejemplo, si establece 100, Adobe Campaign:
   * Extraer aleatoriamente 100 perfiles de la población de destinatarios.
   * Si seleccionó el **[!UICONTROL Age]** campo como criterio de ordenación, extraiga los 100 perfiles más antiguos de la población de destinatarios.

   >[!NOTE]
   >
   >Si desmarca la **[!UICONTROL Descending sort]** opción, se extraerán los 100 perfiles más jóvenes.

## Exclusión de una población específica {#excluding-specific-population}

Otra forma de definir un grupo de control es excluir una población específica del destinatario mediante una consulta.

Para ello:

1. From the **[!UICONTROL Target exclusion]** section, click **[!UICONTROL Define target exclusion]**.

   ![](assets/control-group-define-target-exclusion.png)

1. Defina los criterios de exclusión mediante el editor [de](../../automating/using/editing-queries.md)consultas. También puede seleccionar una [audiencia](../../audiences/using/about-audiences.md) que se haya creado anteriormente.

   ![](assets/control-group-target-exclusion.png)

1. Haga clic **[!UICONTROL Confirm]**.

Los perfiles que coincidan con el resultado de la consulta se excluirán del destinatario.

<!--For more on using the query editor, see the [Editing queries](../../automating/using/editing-queries.md) section.-->

## Caso de uso: configurar un grupo de control {#control-group-example}

A continuación se muestra un ejemplo que muestra cómo definir un grupo de control mediante ambos métodos: extraer perfiles del destinatario principal y utilizar una consulta para excluir una población específica.

1. Creación de un flujo de trabajo. Los pasos detallados para crear un flujo de trabajo se describen en la sección [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md).
1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md) . Haga clic con el doble en la actividad y defina el destinatario. <!--For example, in **[!UICONTROL Shortcuts]**, drag and drop **[!UICONTROL Profile]**, select **[!UICONTROL Age]** with the operator **[!UICONTROL Greater than]** and type 25 in the **[!UICONTROL Value]** field.-->

1. En **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arrastre y suelte una actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico después del segmento de destinatario principal y edítela.
1. Haga clic en el **[!UICONTROL Audience]** bloque del panel de envío.

1. Seleccione la pestaña **[!UICONTROL Control group]**

   ![](assets/control-group-tab.png)

1. From the **[!UICONTROL Target extraction]** section, select **[!UICONTROL Keep only the first records after sorting]**.
1. Ordenar según la edad y dejar la opción de **[!UICONTROL Descending]** ordenación activada.

   ![](assets/control-group-sorting-column.png)

1. Establezca 100 como el tamaño máximo. Se extraerán los 100 perfiles más antiguos de su destinatario.

1. En la **[!UICONTROL Target exclusion]** sección, defina los perfiles que se excluirán del destinatario, según los criterios de su elección mediante el editor [de](../../automating/using/editing-queries.md)consultas. Por ejemplo, &quot;La edad es menor de 20 años&quot;.

   ![](assets/control-group-target-exclusion-example.png)

   Quedan excluidos los perfiles menores de 20 años.

1. Inicie la preparación [de](../../sending/using/preparing-the-send.md) envío y [confirme el envío](../../sending/using/confirming-the-send.md).

Los perfiles extraídos (los 100 perfiles más antiguos) y los definidos en función de la consulta (perfiles menores de 20 años) se retirarán del destinatario principal. No recibirán el mensaje.

## Comparación de los resultados {#delivery-logs}

Ahora que enviaste a tu envío, ¿qué puedes hacer con el grupo de control?

Puede extraer los registros **de** envío para comparar cómo actuó el grupo de control que no recibió la comunicación en comparación con el destinatario efectivo. También puede usar los registros de envío para **crear otro objetivo**.

>[!IMPORTANT]
>
>Debe tener una función [de](../../administration/using/users-management.md#functional-administrators) administrador y formar parte de la unidad **[!UICONTROL All]** [](../../administration/using/organizational-units.md) organizativa para poder conectarse a Adobe Campaign. Si desea restringir el acceso de un usuario o grupo de usuarios en particular, no lo vincule a **[!UICONTROL All]** unidades para poder acceder a registros de envío.

### Comprobación de los registros de envío {#checking-logs}

Para ver qué perfiles se eliminaron del destinatario después de que se enviara el mensaje, consulte la **[!UICONTROL Delivery logs]**. Para obtener más información sobre los registros de envío y cómo acceder a ellos, consulte [esta sección](../../sending/using/monitoring-a-delivery.md#delivery-logs).

* En la **[!UICONTROL Sending logs]** ficha, puede ver los perfiles extraídos y excluidos. Tienen el **[!UICONTROL Ignored]** estatus y **[!UICONTROL Control group]** la razón del fracaso.

   ![](assets/control-group-sending-logs.png)

* También puede marcar la **[!UICONTROL Exclusion causes]** ficha para ver el número de perfiles que no se incluyeron en el envío.

   ![](assets/control-group-exclusion-causes.png)

### Uso de los registros de grupo de control {#using-logs}

Una vez enviado el envío, puede usar los registros de envío para filtrar los perfiles que no recibieron el mensaje. Siga estos pasos:

1. Creación de un flujo de trabajo. Los pasos detallados para crear un flujo de trabajo se describen en la sección [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md).
1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md) .
1. En la **[!UICONTROL Properties]** ficha, defina **[!UICONTROL Delivery logs]** como **[!UICONTROL Resource]** y **[!UICONTROL Profile]** como **[!UICONTROL Targeting dimension]**.

   ![](assets/control-group-delivery-properties.png)

1. En la pestaña **[!UICONTROL Target]**, haga clic en **[!UICONTROL Delivery logs]**.
1. Arrastre y suelte **[!UICONTROL Status]** y seleccione **[!UICONTROL Ignored]** como condición de filtro.

   ![](assets/control-group-status-ignored.png)

1. Haga clic **[!UICONTROL Confirm]**.

1. En la **[!UICONTROL Target]** ficha, arrastre y suelte **[!UICONTROL Nature of failure]** y seleccione **[!UICONTROL Control group]** como condición de filtro.

   ![](assets/control-group-nature-of-failure.png)

1. Haga clic **[!UICONTROL Confirm]**.

   ![](assets/control-group-delivery-target.png)

A continuación, puede exportar los datos de registro mediante una actividad de archivo **** Extract seguida de una actividad de archivo **** Transfer, por ejemplo. Esto le permitirá analizar en su propia herramienta de sistema de informes los resultados de su campaña sobre el destinatario efectivo en comparación con el grupo de control. For more on exporting logs, see [this section](../../automating/using/exporting-logs.md).

### Dirigirse al grupo de control {#targeting-control-group}

Para realizar un objetivo basado en los perfiles que no recibieron el mensaje, también puede usar los registros de envío. Siga estos pasos:

1. Creación de un flujo de trabajo. Los pasos detallados para crear un flujo de trabajo se describen en la sección [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md).
1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una primera actividad de [Consulta](../../automating/using/query.md) .
1. En la **[!UICONTROL Properties]** ficha, asegúrese de que el **[!UICONTROL Profile]** recurso está seleccionado como **[!UICONTROL Resource]** y **[!UICONTROL Targeting dimension]**.

   ![](assets/control-group-delivery-properties-profile.png)

1. En la **[!UICONTROL Target]** ficha, expanda **[!UICONTROL Delivery]** y arrastre y suelte **[!UICONTROL Delivery logs]**.

   ![](assets/control-group-query-delivery-logs.png)

1. En la **[!UICONTROL Add a rule]** ventana, arrastre y suelte **[!UICONTROL Delivery]**.

   ![](assets/control-group-rule-delivery.png)

1. Seleccione el correo electrónico enviado como condición de filtro. Haga clic **[!UICONTROL Confirm]**.

   ![](assets/control-group-email-sent.png)

1. Vuelva a la **[!UICONTROL Add a rule]** ventana, arrastre y suelte **[!UICONTROL Status]** y seleccione **[!UICONTROL Ignored]** como condición de filtro. Haga clic **[!UICONTROL Confirm]**.

   ![](assets/control-group-status-ignored.png)

1. Arrastre y suelte **[!UICONTROL Nature of failure]** y seleccione **[!UICONTROL Control group]** como condición de filtro. Haga clic **[!UICONTROL Confirm]**.

   ![](assets/control-group-nature-of-failure.png)

1. Asegúrese de que todas las condiciones están alineadas con el operador booleano **AND** .

   ![](assets/control-group-delivery-logs-conditions.png)

1. Haga clic **[!UICONTROL Confirm]**.

Ahora puede enviar un destinatario a los perfiles que no recibieron su primer mensaje porque formaban parte del grupo de control y enviarles otro correo electrónico.

En el mismo flujo de trabajo, también puede crear otra consulta para destinatario de los perfiles que recibieron el correo electrónico y enviarles un mensaje diferente.

![](assets/control-group-targeted-by-delivery.png)