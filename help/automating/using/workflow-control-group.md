---
title: Creación de un grupo de control
description: Este caso de uso muestra cómo crear un grupo de control.
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
source-git-commit: 68e689e6bc362f4e948593c3b251f3825aab20ac
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 4%

---


# Creación de un grupo de control {#building-control-group}

Para medir el impacto de un envío, es posible que desee excluir algunos perfiles del destinatario para que no reciban un mensaje determinado. Este grupo de control se puede utilizar para comparar el comportamiento de la población de destinatarios que recibió el mensaje.

Para hacerlo en Adobe Campaign Standard, puede crear un flujo de trabajo que incluya las siguientes actividades:
* actividad de [Consulta](../../automating/using/query.md) para el destinatario de una población determinada.
* Una actividad [de segmentación](../../automating/using/segmentation.md) para aislar un grupo de control aleatorio de esta población.
* actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico para enviar un mensaje al destinatario principal.
* Una actividad de [actualización de datos](../../automating/using/update-data.md) para actualizar los perfiles excluidos del destinatario (el grupo de control aleatorio).

![](assets/wkf_control-group.png)

## Ampliación del recurso de Perfil {#extending-profile}

En primer lugar, debe ampliar el **[!UICONTROL Profile]** recurso con un nuevo campo correspondiente al grupo de control. Una vez ejecutado el flujo de trabajo, este campo se comprobará en busca de los perfiles que se excluyeron del destinatario.

1. En **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Custom Resources]**, haga clic en **[!UICONTROL Create]**.
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

## Creating a Query activity {#create-a-query-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Targeting]**, arrastre y suelte una actividad de [Consulta](../../automating/using/query.md) .
1. Haga clic con el Doble en la actividad para definir el destinatario.
1. Por ejemplo, en **[!UICONTROL Shortcuts]**, arrastre y suelte **[!UICONTROL Profile]**, seleccione **[!UICONTROL Age]** con el operador **[!UICONTROL Greater than]** y escriba 25 en el **[!UICONTROL Value]** campo.
1. Haga clic **[!UICONTROL Confirm]**.

## Creación de una actividad de segmentación {#creating-a-segmentation-activity}

1. Arrastre y suelte una actividad [de segmentación](../../automating/using/segmentation.md) y haga clic en ella con el doble.
1. En la **[!UICONTROL Segments]** ficha, seleccione un segmento para editar.
1. En la **[!UICONTROL Configuration]** ficha de ese segmento, seleccione la **[!UICONTROL Limit the population of this segment]** opción.

   ![](assets/wkf_control-segment-configuration.png)

1. En la **[!UICONTROL Limitation]** ficha, asegúrese de que la **[!UICONTROL Random sampling]** opción está seleccionada.

   ![](assets/wkf_control-segment-limitation.png)

1. Defina un porcentaje de la población inicial, por ejemplo 10 %, y haga clic en **[!UICONTROL Confirm]**. El grupo de control se compondrá del 10% de la población objetivo, seleccionada al azar.
1. En la **[!UICONTROL Advanced options]** ficha, seleccione la **[!UICONTROL Generate complement]** opción y rellene los campos **[!UICONTROL Transition label]** y **[!UICONTROL Segment code]** .

   ![](assets/wkf_control-segment-advanced.png)

1. Haga clic **[!UICONTROL Confirm]**.

## Creating an Email activity {#creating-an-email-activity}

1. En **[!UICONTROL Activities]** > **[!UICONTROL Channels]**, arrastre y suelte una actividad de envío [de](../../automating/using/email-delivery.md) correo electrónico después del segmento de destinatario principal.
1. Haga clic en la actividad y seleccione ![](assets/edit_darkgrey-24px.png) para editarla.
1. Seleccione **[!UICONTROL Single send email]** y haga clic en **[!UICONTROL Next]**.
1. Seleccione una plantilla de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Introduzca las propiedades de correo electrónico y haga clic en **[!UICONTROL Next]**.
1. Para crear el diseño del correo electrónico, haga clic en **[!UICONTROL Use the Email Designer]**.
1. Edite y guarde el contenido.
1. En la **[!UICONTROL Schedule]** sección del panel de mensajes, anule la selección de la opción **[!UICONTROL Solicitar confirmación antes de enviar mensajes}** .

## Creación de una actividad de datos de actualización {#creating-update-data-activity}

1. Arrastre y suelte una actividad de [actualización de datos](../../automating/using/update-data.md) después del segmento de grupo de control.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. En la pestaña **[!UICONTROL General]**, en la lista desplegable **[!UICONTROL Operation type]**, seleccione **[!UICONTROL Update]**.
1. En la **[!UICONTROL Identification]** ficha, seleccione la **[!UICONTROL Directly using the targeting dimension]** opción.
1. Seleccione el **[!UICONTROL Profile]** recurso que ha ampliado anteriormente como la dimensión que desea actualizar.

   ![](assets/wkf_control-update-identification.png)

1. En la **[!UICONTROL Fields to update]** ficha, seleccione el campo de grupo de control que ha agregado al **[!UICONTROL Profile]** recurso como **[!UICONTROL Destination]** y escriba true como condición.

   ![](assets/wkf_control-update-fields-to-update.png)

1. Haga clic **[!UICONTROL Confirm]**.

## Ejecución del flujo de trabajo {#running-the-workflow}

Click **[!UICONTROL Start]** to run the workflow.

Una vez ejecutado el flujo de trabajo, se excluye la población del grupo de control y se envía el mensaje al destinatario principal restante.

El **[!UICONTROL Profile]** recurso se actualiza de la siguiente manera: si un perfil estaba en el grupo de control, se marca el campo correspondiente.

![](assets/wkf_control-group-profile-checked.png)

Ahora puede comparar cómo reaccionarán los destinatarios del mensaje en comparación con el grupo pequeño que fue excluido del mensaje y no lo recibió.

## Reutilización del mismo grupo de control {#reusing-same-control-group}

El ejemplo anterior permite crear un grupo de control global, ya que se almacena como un atributo de perfil independientemente de los envíos. De hecho, el nuevo campo &quot;Grupo de control&quot; que se creó como parte de la extensión de **[!UICONTROL Profile]** recurso se actualiza después de ejecutar el flujo de trabajo anterior.

En consecuencia, la próxima vez que desee utilizar el mismo grupo de control, puede segmentar en el nuevo campo &quot;Grupo de control&quot; en lugar de realizar una segmentación aleatoria.

Para ello:
1. Al crear la **[!UICONTROL Segmentation]** actividad, seleccione el segmento que desea editar en la **[!UICONTROL Segments]** ficha.
1. En la **[!UICONTROL Configuration]** ficha de ese segmento, asegúrese de no seleccionar la **[!UICONTROL Limit the population of this segment]** opción.
1. En la **[!UICONTROL Filtering]** ficha, arrastre y suelte **[!UICONTROL Profiles (attributes)]** en el espacio de trabajo principal.

   ![](assets/wkf_control-group-segment-profiles-attributes.png)

1. En la **[!UICONTROL Add a rule - Profiles (attributes)]** ventana, seleccione &quot;Grupo de control&quot; (el campo que ha agregado al **[!UICONTROL Profile]** recurso) y seleccione **[!UICONTROL Yes]** como condición de filtro.

   ![](assets/wkf_control-group-segment-profiles-attributes-field.png)
