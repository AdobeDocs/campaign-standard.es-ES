---
title: Interfaz de flujo de trabajo
description: Conozca la interfaz y las opciones para crear, editar y ejecutar un flujo de trabajo.
audience: automating
content-type: reference
topic-tags: about-workflows-and-data-management
context-tags: workflow,main;workflow,overview
feature: Workflows
old-role: Data Architect
role: Developer
level: Beginner
exl-id: a3f35bb9-e61e-4f3f-b855-1d677422f75a
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 4%

---

# Interfaz de flujo de trabajo{#workflow-interface}

Puede crear flujos de trabajo para administrar procesos completos en sus campañas y programas.

La pantalla de edición del flujo de trabajo se compone de los siguientes elementos:

* La [Paleta](#palette), que hace referencia a las actividades disponibles.
* [Workspace](#workspace), en el que se configuran y organizan las actividades.
* La [barra de acciones](#action-bar), que está formada por botones que le permiten interactuar con el flujo de trabajo o sus componentes.
* Las [acciones rápidas](#quick-actions), que aparecen alrededor de una actividad seleccionada, le permiten interactuar con ella.

![](assets/wkf_overview.png)

![](assets/do-not-localize/how-to-video.png) [Descubra cómo crear un flujo de trabajo en vídeo](#video)

## Paleta {#palette}

La paleta se encuentra en el lado izquierdo de la pantalla. Todas las actividades disponibles se clasifican en varias categorías:

* [Segmentación](../../automating/using/about-targeting-activities.md): actividades específicas para la segmentación, manipulación de datos de población y filtrado de actividades
* [Ejecución](../../automating/using/about-execution-activities.md): actividades específicas para organizar y ejecutar flujos de trabajo
* [Canales](../../automating/using/about-channel-activities.md): actividades que representan los diferentes canales de comunicación disponibles
* [Administración de datos (ETL)](../../automating/using/about-data-management-activities.md): actividades específicas para manipular datos

Para utilizar una actividad de la paleta en el flujo de trabajo, arrástrela y suéltela en el espacio de trabajo.

Debe configurar cada actividad agregada desde la paleta antes de iniciar el flujo de trabajo.

![](assets/workflow_palette.png)

## Espacio de trabajo {#workspace}

El espacio de trabajo es la zona central del editor de flujo de trabajo. Es en esta zona donde puede soltar las actividades, vincularlas entre sí mediante transiciones y configurarlas.

Para vincular dos actividades, mueva el final de la flecha desde la primera actividad hasta la siguiente actividad hasta que se conecten. También puede mover la actividad hacia el punto de la flecha detrás de ella para vincularla a la actividad anterior. Si mueve cualquiera de las actividades, permanecerán vinculadas.

Las transiciones que siguen a actividades que procesan datos contienen las poblaciones intermediarias. Puede acceder a ellas si marca la opción **[!UICONTROL Keep interim results]** en la sección **[!UICONTROL Execution]** de las propiedades del flujo de trabajo.

>[!CAUTION]
>
>Esta opción consume mucho espacio en el disco y está diseñada para ayudarle a crear un flujo de trabajo y garantizar una configuración y un comportamiento adecuados. Deje sin marcar las instancias de producción.


Cuando se selecciona una actividad, aparecen acciones rápidas en torno a ella, lo que le permite interactuar con ella. Por ejemplo, para configurar una actividad, selecciónela y ábrala con el botón ![](assets/edit_darkgrey-24px_table.png) en las acciones rápidas.

Algunas funciones solo están habilitadas en el espacio de trabajo:

* Seleccione varias actividades y transiciones dibujando una zona alrededor de ellas.
* Presione **Ctrl** + clic izquierdo para seleccionar varias actividades y/o transiciones.
* Pulse **Intro** para ver los detalles de la actividad o transición seleccionada actualmente.
* Pulse **Eliminar** para eliminar la actividad seleccionada actualmente.
* Presione **Ctrl + C** para copiar las actividades seleccionadas y **Ctrl + V** para pegarlas en el área de trabajo.

![](assets/workflow_workspace.png)

## Barra de acciones {#action-bar}

Según los elementos seleccionados en el espacio de trabajo o el estado de ejecución del flujo de trabajo, los botones disponibles en la barra de acciones pueden variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar las propiedades del flujo de trabajo.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Inicia el flujo de trabajo.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Pausa el flujo de trabajo.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrumpe la ejecución del flujo de trabajo. No se puede reanudar desde donde se detuvo.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Reinicia el flujo de trabajo.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Abre el registro de ejecución del flujo de trabajo.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Habilita el modo de selección múltiple. El flujo de trabajo debe estar compuesto por al menos dos actividades.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Deshabilita el modo de selección múltiple.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Abre la transición seleccionada.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Vuelve a habilitar la selección si anteriormente se ha deshabilitado o marcado como en pausa.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa el flujo de trabajo en la actividad seleccionada.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Deshabilita la actividad.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina las actividades seleccionadas.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia las actividades seleccionadas.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Pega las actividades que se han copiado.

## Acciones rápidas {#quick-actions}

Cuando se selecciona una actividad, aparecen botones de acción rápida alrededor de la actividad que le permiten interactuar con ella.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Abre la actividad seleccionada.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia la actividad seleccionada.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre las opciones avanzadas de la actividad de envío de correo electrónico o SMS seleccionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Vuelve a habilitar la selección si anteriormente se ha deshabilitado o marcado como en pausa.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Pausa el flujo de trabajo en la actividad seleccionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Deshabilita la actividad.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Obliga al procesamiento inmediato de la selección. Este botón solo está disponible para las actividades <span class="uicontrol">Scheduler</span> y <span class="uicontrol">Wait</span>.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina las actividades seleccionadas.

## Duplicado de actividades de flujo de trabajo {#duplicating-workflow-activities}

El espacio de trabajo permite duplicar las actividades de flujo de trabajo copiándolas y pegándolas en el mismo flujo de trabajo o en otro flujo de trabajo de la misma instancia de Campaign.

Una vez duplicada una actividad, se conserva toda su configuración. Para las actividades de envío (correo electrónico, SMS, notificaciones push...), el objeto de envío adjunto a la actividad está duplicado.

>[!NOTE]
>
>Las actividades de flujo de trabajo no se pueden duplicar de una instancia a otra. Las actividades de los flujos de trabajo técnicos no se pueden duplicar.

Para duplicar una actividad, siga los pasos a continuación:

1. Seleccione la actividad y haga clic en el botón **[!UICONTROL Copy selection]** en las acciones rápidas.

   También puede usar el método abreviado de teclado **Ctrl + C**.

   ![](assets/wkf_copypaste1.png)

1. Haga clic con el botón derecho en el área de trabajo de flujo de trabajo de destino y luego haga clic en el botón **[!UICONTROL Paste]**.

   También puede usar el método abreviado de teclado **CTRL + V**.

   ![](assets/wkf_copypaste2.png)

1. La actividad está duplicada, con todas las configuraciones que se han configurado inicialmente.

También es posible copiar y pegar varias actividades, lo que permite duplicar un flujo de trabajo completo.

Para ello, seleccione las actividades dibujando una zona alrededor de ellas. a continuación, haga clic en el botón **[!UICONTROL Copy selection]** de la barra de acciones (o presione **Ctrl + C**). A continuación, puede pegarlos en la ubicación deseada.

![](assets/wkf_copypaste3.png)

## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear un flujo de trabajo.

>[!VIDEO](https://video.tv.adobe.com/v/23937?quality=12)

Hay disponibles [más vídeos de procedimientos para Campaign Standard aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
