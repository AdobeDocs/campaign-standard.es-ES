---
title: Esperar
seo-title: Esperar
description: Esperar
seo-description: La actividad de espera suspende momentáneamente la ejecución de una parte de un flujo de trabajo.
page-status-flag: no activado nunca
uuid: 396 a 3 de 1-6 ffa -4385-ac 9 f -15 fdeae 5 a 366
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: ejecución actividades
discoiquuid: 377821 e 6-69 f 8-41 cc-a 1 ad -8 a 2 f 5 ed 4 d 409
context-tags: esperar, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e384a0cef325bc01eb5ea050b0f3d926aea9a88f

---


# Wait{#wait}

## Description {#description}

![](assets/wait.png)

The **[!UICONTROL Wait]** activity momentarily suspends executing a part of a workflow. Activa la transición saliente después de un retraso que puede abarcar de unos segundos a varios meses, lo que ejecuta las actividades colocadas posteriormente.

## Context of use {#context-of-use}

The **[!UICONTROL Wait]** activity is used to allow a certain amount of time to pass between two activities being executed. Por ejemplo, para esperar varios días después de una actividad de envío de correo electrónico, analice las aperturas y los clics generados durante este período antes de realizar cualquier operación de seguimiento (correo electrónico de recordatorio, crear una audiencia, etc.).

## Configuration {#configuration}

1. Drag and drop a **[!UICONTROL Wait]** activity into your workflow.
1. Select the activity, then open it using the ![](assets/edit_darkgrey-24px.png) button from the quick actions that appear.
1. Specify the **[!UICONTROL Duration]** of the wait between when the inbound and outbound transitions of the activity are activated.

   Puede introducir manualmente la duración o utilizar el selector disponible en el campo.

   ![](assets/wait_duration.png)

1. Confirme la configuración de su actividad y guarde el flujo de trabajo.

## Example {#example}

The following example illustrates the **[!UICONTROL Wait]** activity in a typical use case. Se envía una invitación por correo electrónico a un evento. 24 horas después de enviarse, se analizan los registros de envío de correo electrónico y se envía un recordatorio de recordatorio a las personas que recibieron el primer correo electrónico pero que no se registraron.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/wait_example_workflow.png)

* A first **[!UICONTROL Query]** targets the profiles that will be sent the email invitation.
* An **[!UICONTROL Email delivery]** sends the invitation for the first time to the profiles selected.
* **[!UICONTROL Wait]** Una actividad de 24 h coloca una pausa entre el momento en que se envió la invitación y el resto del flujo de trabajo.
* A second **[!UICONTROL Query]** targets the profiles that received the first email but did not click on the subscription link inside.
* A second **[!UICONTROL Email delivery]** sends a reminder of the invitation to the people selected.

