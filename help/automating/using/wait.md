---
title: Espera
description: La actividad de espera suspende momentáneamente la ejecución de una parte de un flujo de trabajo.
page-status-flag: nunca activado
uuid: 396a3de1-6ffa-4385-ac9f-15fdeae5a366
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: execute-activity
discoiquuid: 377821e6-69f8-41cc-a1ad-8a2f5ed4d409
context-tags: wait,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Espera{#wait}

## Descripción {#description}

![](assets/wait.png)

La **[!UICONTROL Wait]** actividad suspende momentáneamente la ejecución de una parte de un flujo de trabajo. Activa su transición de salida después de un retraso que puede oscilar entre unos segundos y varios meses, lo que ejecuta las actividades posteriores.

## Contexto de uso {#context-of-use}

La **[!UICONTROL Wait]** actividad se utiliza para permitir que transcurra una cierta cantidad de tiempo entre dos actividades que se ejecutan. Por ejemplo, para esperar varios días después de una actividad de envío de correo electrónico, analice las aperturas y los clics generados durante este período antes de realizar cualquier operación de seguimiento (correo electrónico de recordatorio, creación de una audiencia, etc.).

## Configuración {#configuration}

1. Arrastre y suelte una **[!UICONTROL Wait]** actividad en el flujo de trabajo.
1. Seleccione la actividad y, a continuación, ábrala con el ![](assets/edit_darkgrey-24px.png) botón de las acciones rápidas que aparecen.
1. Especifique la duración **[!UICONTROL Duration]** de la espera entre la activación de las transiciones de entrada y salida de la actividad.

   Puede introducir manualmente la duración o utilizar el selector disponible en el campo.

   ![](assets/wait_duration.png)

1. Confirme la configuración de la actividad y guarde el flujo de trabajo.

## Ejemplo {#example}

El siguiente ejemplo ilustra la actividad en un caso de uso típico **[!UICONTROL Wait]** . Se envía una invitación por correo electrónico a un evento. 24 horas después de que se enviara, se analizan los registros de entrega de correo electrónico y se envía un correo electrónico de recordatorio a las personas que recibieron el primer correo electrónico pero no se registraron.

El flujo de trabajo se presenta de la siguiente manera:

![](assets/wait_example_workflow.png)

* Un primer **[!UICONTROL Query]** objetivo son los perfiles a los que se enviará la invitación por correo electrónico.
* Un **[!UICONTROL Email delivery]** mensaje envía la invitación por primera vez a los perfiles seleccionados.
* Una actividad **[!UICONTROL Wait]** de 24 horas coloca una pausa entre el momento en que se envió la invitación y el resto del flujo de trabajo.
* Un segundo **[!UICONTROL Query]** se dirige a los perfiles que recibieron el primer correo electrónico pero que no hicieron clic en el vínculo de suscripción dentro.
* Un segundo **[!UICONTROL Email delivery]** envía un recordatorio de la invitación a las personas seleccionadas.

