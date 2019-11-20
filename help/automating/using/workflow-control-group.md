---
title: '"Caso de uso del flujo de trabajo: Grupo de control"'
seo-title: '"Caso de uso del flujo de trabajo: Grupo de control"'
description: '"Caso de uso del flujo de trabajo: Grupo de control"'
seo-description: '"Caso de uso del flujo de trabajo: Grupo de control"'
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
source-git-commit: 2912e3b75b817347b832f9c89ca2320868cbc355

---


# Caso de uso del flujo de trabajo: Creación de un grupo de control {#building-control-group}

Para medir el impacto de una entrega, es posible que desee excluir algunos perfiles del objetivo para que no reciban un mensaje determinado. Este grupo de control puede utilizarse para realizar una comparación con el comportamiento de la población objetivo que recibió el mensaje.

Para hacerlo en Adobe Campaign Standard, puede crear un flujo de trabajo que incluya las siguientes actividades:
* Una actividad de consulta para dirigirse a una población determinada.
* Una actividad de segmentación para aislar un grupo de control aleatorio de esta población.
* Una actividad de envío de correo electrónico para enviar un mensaje al destino principal.
* Una actividad de actualización de datos para actualizar los perfiles excluidos del destino (el grupo de control aleatorio).

![](assets/wkf_control-group.png)

## Ampliación del recurso Perfil {#extending-profile}

En primer lugar, debe ampliar el **[!UICONTROL Profile]** recurso con un nuevo campo correspondiente al grupo de control. Una vez ejecutado el flujo de trabajo, este campo se comprobará en busca de los perfiles excluidos del destino.

1. En **[!UICONTROL Administration]** &gt; **[!UICONTROL Development]** &gt; **[!UICONTROL Custom Resources]**, haga clic en **[!UICONTROL Create]**.
1. Si aún no lo ha ampliado, seleccione **[!UICONTROL Extend an existing resource]** y elija el **[!UICONTROL Profile]** recurso.
1. En la **[!UICONTROL Data structure]** ficha, agregue un nuevo campo para el grupo de control y seleccione **[!UICONTROL Boolean]** para el **[!UICONTROL Type]** campo.

   ![](assets/wkf_control-group-profile-field.png)

1. En la **[!UICONTROL Screen definition]** ficha, despliegue la **[!UICONTROL Detail screen configuration]** sección y seleccione el campo que acaba de crear para que se muestre para cada perfil.

   ![](assets/wkf_control-group-profile-field-screen.png)

1. Guarde los cambios.
1. Actualice la estructura de la base de datos para publicar el recurso **[!UICONTROL Profile]** ampliado. Consulte [Publicación de un recurso](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)personalizado.

Para obtener más información sobre cómo ampliar un recurso personalizado, consulte Pasos [clave para agregar un recurso](../../developing/using/key-steps-to-add-a-resource.md).

## Creación de un flujo de trabajo {#creating-a-workflow}

1. En **[!UICONTROL Marketing Activities]**, haga clic **[!UICONTROL Create]** y seleccione **[!UICONTROL Workflow]**.
1. Seleccione **[!UICONTROL New Workflow]** como tipo de flujo de trabajo y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades del flujo de trabajo y haga clic en **[!UICONTROL Create]**.

Los pasos detallados para crear un flujo de trabajo se presentan en la sección [Creación de un flujo de trabajo](../../automating/using/building-a-workflow.md) .

## Creación de una actividad de consulta {#create-a-query-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Targeting]**, arrastre y suelte una **[!UICONTROL Query activity]**.
1. Haga doble clic en la actividad para definir el objetivo.
1. Por ejemplo, en **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profile]**, seleccione **[!UICONTROL Age]** con el operador **[!UICONTROL Greater than]** y escriba 25 en el **[!UICONTROL Value]** campo.
1. Click **[!UICONTROL Confirm]**.

Los pasos detallados para crear una actividad de consulta se presentan en la sección [Consulta](../../automating/using/query.md) .

## Creación de una actividad de segmentación {#creating-a-segmentation-activity}

1. Arrastre y suelte una **[!UICONTROL Segmentation]** actividad y haga doble clic en ella.
1. En la **[!UICONTROL Segments]** ficha, seleccione un segmento para editar.
1. En la **[!UICONTROL Configuration]** ficha de ese segmento, seleccione la **[!UICONTROL Limit the population of this segment]** opción.

   ![](assets/wkf_control-segment-configuration.png)

1. En la **[!UICONTROL Limitation]** ficha, asegúrese de que la **[!UICONTROL Random sampling]** opción está seleccionada.

   ![](assets/wkf_control-segment-limitation.png)

1. Defina un porcentaje de la población inicial, por ejemplo 10 %, y haga clic en **[!UICONTROL Confirm]**. El grupo de control se compondrá del 10 % de la población objetivo, seleccionada al azar.
1. En la **[!UICONTROL Advanced options]** ficha, seleccione la **[!UICONTROL Generate complement]** opción y rellene los campos **[!UICONTROL Transition label]** y **[!UICONTROL Segment code]** .

   ![](assets/wkf_control-segment-advanced.png)

1. Click **[!UICONTROL Confirm]**.

Los pasos detallados para crear una actividad de segmentación se presentan en la sección [Segmentación](../../automating/using/segmentation.md) .

## Creación de una actividad de correo electrónico {#creating-an-email-activity}

1. En **[!UICONTROL Activities]** &gt; **[!UICONTROL Channels]**, arrastre y suelte un elemento **[!UICONTROL Email Delivery]** después del segmento de destino principal.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Single send email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Use the Email Designer]**.
1. Edite y guarde el contenido.
1. En la **[!UICONTROL Schedule]** sección del tablero de mensajes, anule la selección de la opción **[!UICONTROL Solicitar confirmación antes de enviar mensajes}** .

Los pasos detallados para crear una actividad de correo electrónico se presentan en la sección Envío por [correo electrónico](../../automating/using/email-delivery.md) .

## Creación de una actividad de actualización de datos {#creating-update-data-activity}

1. Arrastre y suelte una **[!UICONTROL Update data]** actividad después del segmento del grupo de control.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. En la **[!UICONTROL General]** ficha, seleccione **[!UICONTROL Update]** en la lista **[!UICONTROL Operation type]** desplegable.
1. En la **[!UICONTROL Identification]** ficha, seleccione la **[!UICONTROL Directly using the targeting dimension]** opción.
1. Seleccione el **[!UICONTROL Profile]** recurso que ha ampliado anteriormente como la dimensión que desea actualizar.

   ![](assets/wkf_control-update-identification.png)

1. En la **[!UICONTROL Fields to update]** ficha, seleccione el campo de grupo de control que ha agregado al **[!UICONTROL Profile]** recurso como **[!UICONTROL Destination]** y escriba true como condición.

   ![](assets/wkf_control-update-fields-to-update.png)

1. Click **[!UICONTROL Confirm]**.

Los pasos detallados para generar una actividad de actualización de datos se presentan en la sección [Actualizar datos](../../automating/using/update-data.md) .

## Ejecución del flujo de trabajo {#running-the-workflow}

Haga clic en **[!UICONTROL Start]** para ejecutar el flujo de trabajo.

Una vez ejecutado el flujo de trabajo, se excluye la población del grupo de control y se envía el mensaje al destino principal restante.

El **[!UICONTROL Profile]** recurso se actualiza de la siguiente manera: si un perfil estaba en el grupo de control, se marca el campo correspondiente.

![](assets/wkf_control-group-profile-checked.png)

Ahora puede comparar cómo reaccionarán los destinatarios del mensaje en comparación con el grupo pequeño que fue excluido del mensaje y no lo recibió.

## Reutilización del mismo grupo de control {#reusing-same-control-group}

El ejemplo anterior permite crear un grupo de control global, ya que se almacena como un atributo de perfil independientemente de las entregas. De hecho, el nuevo campo "Grupo de control" que se creó como parte de la extensión de **[!UICONTROL Profile]** recurso se actualiza después de ejecutar el flujo de trabajo anterior.

En consecuencia, la próxima vez que desee utilizar el mismo grupo de control, puede segmentar en el nuevo campo "Grupo de control" en lugar de realizar una segmentación aleatoria.

Para ello:
1. Al crear la **[!UICONTROL Segmentation]** actividad, seleccione el segmento que desea editar en la **[!UICONTROL Segments]** ficha.
1. En la **[!UICONTROL Configuration]** ficha de ese segmento, asegúrese de no seleccionar la **[!UICONTROL Limit the population of this segment]** opción.
1. En la **[!UICONTROL Filtering]** ficha, arrastre y suelte **[!UICONTROL Profiles (attributes)]** en el espacio de trabajo principal.

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. En la **[!UICONTROL Add a rule - Profiles (attributes)]** ventana, seleccione "Grupo de control" (el campo que ha agregado al **[!UICONTROL Profile]** recurso) y seleccione **[!UICONTROL Yes]** como condición de filtro.

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)