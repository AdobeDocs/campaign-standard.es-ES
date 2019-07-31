---
title: Interfaz de flujo de trabajo
seo-title: Interfaz de flujo de trabajo
description: Interfaz de flujo de trabajo
seo-description: Conozca la interfaz y las opciones para crear, editar y ejecutar un flujo de trabajo.
page-status-flag: no activado nunca
uuid: aafe 33 ed-fa 07-4 dd 9-825 e -242099334 f 1 a
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: acerca de los flujos de trabajo y gestión de datos
discoiquuid: 147 fbb 0 d -17 d 2-444 b-a 215-9 ad 14179 c 549
context-tags: workflow, main; flujo de trabajo, información general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6748e59aaeafce9dc6e77dc0664a9024a53c3e35

---


# Workflow interface{#workflow-interface}

Puede crear flujos de trabajo para administrar procesos completos en sus campañas y programas.

La pantalla de edición del flujo de trabajo está formada por los siguientes elementos:

* [Paleta](../../automating/using/workflow-interface.md#palette), que hace referencia a las actividades disponibles.
* [Workspace](../../automating/using/workflow-interface.md#workspace), en el que las actividades están configuradas y organizadas.
* The [Action bar](../../automating/using/workflow-interface.md#action-bar), which is made up of buttons that allow you to interact with the workflow and/or its components.
* The [Quick actions](../../automating/using/workflow-interface.md#quick-actions), which appear around a selected activity, allow you to interact with it.

![](assets/wkf_overview.png)

## Palette {#palette}

La paleta se encuentra en el lado izquierdo de la pantalla. Todas las actividades disponibles se clasifican en varias categorías:

* [Objetivo](../../automating/using/about-targeting-activities.md): actividades específicas de segmentación, manipulación de datos de población y filtrado de actividades
* [Ejecución](../../automating/using/about-execution-activities.md): actividades específicas para organizar y ejecutar flujos de trabajo
* [Canales](../../automating/using/about-channel-activities.md): actividades que representan los distintos canales de comunicación disponibles
* [Administración de datos (ETL)](../../automating/using/about-data-management-activities.md): actividades específicas para manipular datos

Para utilizar una actividad de la paleta del flujo de trabajo, arrástrela y suéltela en su espacio de trabajo.

Debe configurar cada actividad agregada desde la paleta antes de iniciar el flujo de trabajo.

![](assets/workflow_palette.png)

## Workspace {#workspace}

El espacio de trabajo es la zona central del editor de flujo de trabajo. En esta zona puede colocar sus actividades, vincularlas a través de transiciones y configurarlas.

Para vincular dos actividades, mueva el final de la flecha de la primera actividad hasta la siguiente actividad hasta que se conecte. También puede mover la actividad hacia el punto de la flecha detrás para vincularla a la actividad anterior. Si mueve cualquiera de las actividades, permanecerá vinculado.

Las transiciones que siguen a las actividades que procesan datos contienen poblaciones intermediarias. You can access them if you check the **[!UICONTROL Keep interim results]** option in the **[!UICONTROL Execution]** section of the workflow properties.

Cuando se selecciona una actividad, aparecen acciones rápidas alrededor de la actividad, lo que permite interactuar con ella. For example, to configure an activity, select it then open it using the ![](assets/edit_darkgrey-24px_table.png) button in the quick actions.

Ciertas funciones solo están habilitadas en el espacio de trabajo:

* Seleccione varias actividades y transiciones dibujando una zona alrededor de ellas.
* Press **Ctrl** + left click to select several activities and/or transitions.
* Press **Enter** to view the detail of the currently selected activity or transition.
* Press **Delete** to delete the currently selected activity.
* Press **Ctrl + C** to copy the selected activities, and **Ctrl + V** to paste them into the workspace.

![](assets/workflow_workspace.png)

## Action bar {#action-bar}

Según los elementos seleccionados en el espacio de trabajo o el estado de ejecución del flujo de trabajo, los botones disponibles en la barra de acciones pueden variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar las propiedades del flujo de trabajo.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Inicia el flujo de trabajo.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Detiene el flujo de trabajo.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrumpe la ejecución del flujo de trabajo. No se puede reanudar desde donde se detuvo.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Reinicia el flujo de trabajo.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Abre el registro de ejecución del flujo de trabajo.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Habilita el modo de selección múltiple. El flujo de trabajo debe estar formado por al menos dos actividades.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Desactiva el modo de selección múltiple.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Abre la transición seleccionada.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Vuelve a habilitar la selección si antes se había deshabilitado o marcado como pausada.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Detiene el flujo de trabajo en la actividad seleccionada.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desactiva la actividad.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina las actividades seleccionadas.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia las actividades seleccionadas.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Pega las actividades que se han copiado.

## Quick actions {#quick-actions}

Cuando se selecciona una actividad, aparecen botones de acción rápida alrededor de la actividad, lo que permite interactuar con él.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Abre la actividad seleccionada.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia la actividad seleccionada.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre las opciones avanzadas de la actividad de envío de correo electrónico o SMS seleccionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Vuelve a habilitar la selección si antes se había deshabilitado o marcado como pausada.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Detiene el flujo de trabajo en la actividad seleccionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Desactiva la actividad.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Fuerza el procesamiento inmediato de la selección. This button is only available for the <span class="uicontrol">Scheduler</span> and <span class="uicontrol">Wait</span> activities.

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina las actividades seleccionadas.

## Duplicating workflow activities {#duplicating-workflow-activities}

El espacio de trabajo le permite duplicar actividades de flujo de trabajo copiándolas y pegándolas en el mismo flujo de trabajo o en otro flujo de trabajo desde la misma instancia de Campaña.

Una vez que la actividad se duplique, se conserva toda la configuración. Para las actividades de envío (correo electrónico, SMS, notificación push…), se duplica el objeto de entrega adjunto a la actividad.

>[!NOTE]
>
>Las actividades de flujo de trabajo no se pueden duplicar desde una instancia a otra. Las actividades de flujos de trabajo técnicos no se pueden duplicar.

Para duplicar una actividad, siga los pasos a continuación:

1. Select the activity, then click the **[!UICONTROL Copy selection]** button from the quick actions.

   You can also use the **Ctrl + C** keyboard shortcut.

   ![](assets/wkf_copypaste1.png)

1. Right-click in the target workflow workspace, then click the **[!UICONTROL Paste]** button.

   You can also use the **CTRL + V** keyboard shortcut.

   ![](assets/wkf_copypaste2.png)

1. La actividad se duplica, con todas las configuraciones configuradas inicialmente.

También es posible copiar y pegar varias activaciones, lo que permite duplicar un flujo completo.

Para ello, seleccione las actividades dibujando una zona alrededor de ellas. then click the **[!UICONTROL Copy selection]** button from the action bar (or press **Ctrl + C**). A continuación, puede pegarlas en la ubicación deseada.

![](assets/wkf_copypaste3.png)

