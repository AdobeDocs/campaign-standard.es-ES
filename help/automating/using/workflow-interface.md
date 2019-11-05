---
title: Interfaz de flujo de trabajo
description: Conozca la interfaz y las opciones para crear, editar y ejecutar un flujo de trabajo.
page-status-flag: nunca activado
uuid: aafe33ed-fa07-4dd9-825e-242099334f1a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: acerca de los flujos de trabajo y la administración de datos
discoiquuid: 147fbb0d-17d2-444b-a215-9ad14179c549
context-tags: flujo de trabajo,principal;flujo de trabajo,descripción general
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Interfaz de flujo de trabajo{#workflow-interface}

Puede crear flujos de trabajo para administrar procesos completos en sus campañas y programas.

La pantalla de edición del flujo de trabajo consta de los siguientes elementos:

* La [paleta](#palette), que hace referencia a las actividades disponibles.
* El [espacio de trabajo](#workspace), en el que se configuran y organizan las actividades.
* La barra [de](#action-bar)acciones, compuesta por botones que le permiten interactuar con el flujo de trabajo y/o sus componentes.
* Las acciones [](#quick-actions)rápidas, que aparecen alrededor de una actividad seleccionada, le permiten interactuar con ella.

![](assets/wkf_overview.png)

## Paleta {#palette}

La paleta se encuentra en el lado izquierdo de la pantalla. Todas las actividades disponibles se clasifican en varias categorías:

* [Objetivo](../../automating/using/about-targeting-activities.md): actividades específicas para dirigir, manipular datos de población y filtrar actividades
* [Ejecución](../../automating/using/about-execution-activities.md): actividades específicas para organizar y ejecutar flujos de trabajo
* [Canales](../../automating/using/about-channel-activities.md): actividades que representan los distintos canales de comunicación disponibles
* [Administración de datos (ETL)](../../automating/using/about-data-management-activities.md): actividades específicas para manipular datos

Para utilizar una actividad de la paleta en el flujo de trabajo, arrástrela y suéltela en el espacio de trabajo.

Debe configurar cada actividad agregada desde la paleta antes de iniciar el flujo de trabajo.

![](assets/workflow_palette.png)

## Espacio de trabajo {#workspace}

El espacio de trabajo es la zona central del editor de flujo de trabajo. Es en esta zona donde puede soltar sus actividades, vincularlas mediante transiciones y configurarlas.

Para vincular dos actividades, mueva el final de la flecha de la primera actividad a la siguiente hasta que se conecten. También puede mover la actividad hacia el punto de la flecha que hay detrás para vincularla a la actividad anterior. Si mueve alguna de las actividades, permanecerán vinculadas.

Las transiciones que siguen a actividades que procesan datos contienen las poblaciones intermediarias. Puede acceder a ellos si marca la **[!UICONTROL Keep interim results]** opción en la **[!UICONTROL Execution]** sección de las propiedades del flujo de trabajo.

Cuando se selecciona una actividad, aparecen acciones rápidas alrededor de la actividad, lo que le permite interactuar con ella. Por ejemplo, para configurar una actividad, selecciónela y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px_table.png) botón de las acciones rápidas.

Determinadas funciones solo están habilitadas en el espacio de trabajo:

* Seleccione varias actividades y transiciones dibujando una zona a su alrededor.
* Pulse **Ctrl** + clic izquierdo para seleccionar varias actividades y/o transiciones.
* Pulse **Intro** para ver los detalles de la actividad o transición seleccionada actualmente.
* Pulse **Eliminar** para eliminar la actividad seleccionada.
* Pulse **Ctrl + C** para copiar las actividades seleccionadas y **Ctrl + V** para pegarlas en el espacio de trabajo.

![](assets/workflow_workspace.png)

## Barra de acciones {#action-bar}

Según los elementos seleccionados en el espacio de trabajo o el estado de ejecución del flujo de trabajo, los botones disponibles en la barra de acciones pueden variar.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Permite editar las propiedades del flujo de trabajo.

<img height="21px" src="assets/play_darkgrey-24px_table.png" /> **[!UICONTROL Start]**<br/>Inicia el flujo de trabajo.

<img height="21px" src="assets/pause_darkgrey-24px_table.png" /> **[!UICONTROL Pause]**<br/>Detiene el flujo de trabajo.

<img height="21px" src="assets/stop_darkgrey-24px_table.png" /> **[!UICONTROL Stop]**<br/>Interrumpe la ejecución del flujo de trabajo. No se puede reanudar desde donde se detuvo.

<img height="21px" src="assets/pauseplay_darkgrey-24px_table.png" /> **[!UICONTROL Restart]**<br/>Reinicia el flujo de trabajo.

<img height="21px" src="assets/printpreview_darkgrey-24px_table.png" /> **[!UICONTROL Log and tasks]**<br/>Abre el registro de ejecución del flujo de trabajo.

<img height="21px" src="assets/checkcircle_darkgrey-24px_table.png" /> **[!UICONTROL Enable multi-selection]**<br/>Habilita el modo de selección múltiple. El flujo de trabajo debe estar compuesto por al menos dos actividades.

<img height="21px" src="assets/closecircle_darkgrey-24px_table.png" /> **[!UICONTROL Disable multi-selection]**<br/>Desactiva el modo de selección múltiple.<br />

<img height="21px" src="assets/targeted.png" /> **[!UICONTROL Open transition]**<br/>Abre la transición seleccionada.<br />

<img height="21px" src="assets/check_darkgrey-24px_table.png" />  **[!UICONTROL Normal execution]**<br/>Vuelve a activar la selección si ya se ha desactivado o marcado como pausado.<br />

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Detiene el flujo de trabajo en la actividad seleccionada.<br />

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Deshabilita la actividad.<br />

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina las actividades seleccionadas.<br />

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia las actividades seleccionadas.

<img height="21px" src="assets/paste_24px.png" /> **[!UICONTROL Paste]**<br/>Pega las actividades copiadas.

## Acciones rápidas {#quick-actions}

Cuando se selecciona una actividad, aparecen botones de acción rápida alrededor de la actividad, que le permiten interactuar con ella.

<img height="21px" src="assets/edit_darkgrey-24px.png" /> **[!UICONTROL Open activity]**<br/>Abre la actividad seleccionada.

<img height="21px" src="assets/copy_24px.png" /> **[!UICONTROL Copy selection]**<br/>Copia la actividad seleccionada.

<img height="21px" src="assets/wkf_dlv_act_params_icon.png" /> **[!UICONTROL Open the activity's advanced options]**<br/>Abre las opciones avanzadas de la actividad de envío por correo electrónico o SMS seleccionada.

<img height="21px" src="assets/check_darkgrey-24px_table.png" /> **[!UICONTROL Normal execution]**<br/>Vuelve a activar la selección si ya se ha desactivado o marcado como pausado.

<img height="21px" src="assets/check_pause_darkgrey-24px_table.png" /> **[!UICONTROL Execution suspended]**<br/>Detiene el flujo de trabajo en la actividad seleccionada.

<img height="21px" src="assets/checkdisable.png" /> **[!UICONTROL No execution]**<br/>Deshabilita la actividad.

<img height="21px" src="assets/pending_darkgrey-24px_table.png" /> **[!UICONTROL Immediate execution]**<br/>Fuerza el procesamiento inmediato de la selección. Este botón solo está disponible para las actividades <span class="uicontrol">Programador</span> y <span class="uicontrol">Espera</span> .

<img height="21px" src="assets/delete_darkgrey-24px_table.png" /> **[!UICONTROL Delete selection]**<br/>Elimina las actividades seleccionadas.

## Duplicar actividades de flujo de trabajo {#duplicating-workflow-activities}

El espacio de trabajo permite duplicar actividades de flujo de trabajo copiándolas y pegándolas en el mismo flujo de trabajo o en otro flujo de trabajo de la misma instancia de Campaign.

Una vez duplicada una actividad, se mantiene toda la configuración. Para las actividades de entrega (correo electrónico, SMS, notificaciones push...), se duplica el objeto de entrega adjunto a la actividad.

>[!NOTE]
>
>Las actividades de flujo de trabajo no se pueden duplicar de una instancia a otra. No se pueden duplicar las actividades de los flujos de trabajo técnicos.

Para duplicar una actividad, siga los pasos a continuación:

1. Seleccione la actividad y, a continuación, haga clic en el **[!UICONTROL Copy selection]** botón de las acciones rápidas.

   También puede utilizar el método abreviado de teclado **Ctrl + C** .

   ![](assets/wkf_copypaste1.png)

1. Haga clic con el botón secundario en el espacio de trabajo del flujo de trabajo de destino y, a continuación, haga clic en el **[!UICONTROL Paste]** botón.

   También puede utilizar el método abreviado de teclado **CTRL + V** .

   ![](assets/wkf_copypaste2.png)

1. La actividad se duplica, con todas las configuraciones que se configuraron inicialmente.

También es posible copiar y pegar varias actividades, lo que permite duplicar un flujo de trabajo completo.

Para ello, seleccione las actividades dibujando una zona a su alrededor. a continuación, haga clic en el **[!UICONTROL Copy selection]** botón de la barra de acciones (o pulse **Ctrl + C**). A continuación, puede pegarlos en la ubicación deseada.

![](assets/wkf_copypaste3.png)

