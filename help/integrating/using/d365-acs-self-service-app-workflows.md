---
title: Flujos de trabajo de la aplicación de integración
description: Flujos de trabajo de integración de campaña y Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 6be7a20cde8fcaee73972b8919765ea631f2f1ee
workflow-type: tm+mt
source-wordcount: '645'
ht-degree: 1%

---


# Campaña: flujos de trabajo de integración de Microsoft Dynamics 365

La página **[!UICONTROL Workflows]** lista los flujos de trabajo técnicos y su estado.

La aplicación de integración incluye tres flujos de trabajo:

![](assets/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 a Campaña**
* Enviar *contactos* de Microsoft Dynamics 365 a Adobe Campaign
* *Entidades* personalizadas: Inserte tablas personalizadas de Microsoft Dynamics 365 en Adobe Campaign. [Más información](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Esto también se conoce como **Ingress** (que se refiere a la ingesta de datos de Microsoft Dynamics 365 a Adobe Campaign)

**Campaña a Microsoft Dynamics 365**
* Los eventos de marketing por correo electrónico de Adobe Campaign Standard se envían a Dynamics 365 (envío por correo electrónico, apertura, clic, devolución). [Más información](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Esto también se conoce como **Egress** (refiriéndose al ingreso de datos de Adobe Campaign a Microsoft Dynamics 365)

**Inclusión/exclusión**

Los estados de exclusión (por ejemplo, lista de bloqueados de Microsoft Dynamics 365 a Adobe Campaign o de Adobe Campaign a Microsoft Dynamics 365. Los datos también pueden sincronizarse bidireccionalmente (es decir, flujos de datos en ambas direcciones). [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Es muy recomendable que detenga el flujo de trabajo **de Microsoft Dynamics 365 a Campaña** antes de publicar los cambios en Adobe Campaign Standard o Microsoft Dynamics 365. Estos cambios incluyen actualizaciones de recursos/entidades (y sus campos asociados), vínculos, columnas de identificadores, etc. que están siendo utilizados por la integración. Si no lo hace, se podrían perder datos y/o detener inesperadamente el flujo de trabajo.

## Retraso de flujo de trabajo

Esta aplicación de integración primero lee los datos y luego los escribe en el destino. La columna **[!UICONTROL Backlog]** indica el número de registros que se han colocado en la cola y que están esperando ser escritos. Se espera que este valor crezca cuando tenga una gran cantidad de datos para procesar (por ejemplo, si está ejecutando la integración por primera vez, está reproduciendo los datos, etc.).

>[!NOTE]
>Si los registros de Microsoft Dynamics 365 y/o Campaña no se actualizan, debe comprobar primero si hay un gran número de registros pendientes de escribir en el destino.


## Estado del flujo de trabajo {#workflow-status}

La columna **[!UICONTROL Status]** indica el estado de los procesos en segundo plano asociados con el flujo de trabajo. Los valores posibles son:

* **EJECUTANDO**: El proceso se está ejecutando y los datos deben sincronizarse.
* **DETENIDO**: El proceso no se está ejecutando actualmente, por lo que no debe esperar que los datos se sincronizen.
* **INICIO**: Ha solicitado que el flujo de trabajo se procese para inicio. La aplicación aún no ha comenzado a sincronizar los datos asociados con este flujo de trabajo, pero puede esperar que lo haga después de unos minutos (cuando mostrará el estado de **EJECUTANDO**)
* **ERROR**: Los procesos de flujo de trabajo se estaban ejecutando pero se encontraron errores y no se pudieron recuperar de ellos.

## Acciones disponibles

A continuación se enumeran las posibles acciones.

* **Editar**: Al hacer clic en el icono del lápiz, se le enviará a otra página que le permitirá realizar actualizaciones en el flujo de trabajo. Tenga en cuenta que los cambios que realice NO tendrán efecto hasta que detenga el flujo de trabajo y lo reinicie.

* **Inicio**: Un botón de Inicio solicita que se inicie un flujo de trabajo detenido. Este botón solo aparecerá cuando los procesos asociados con el flujo de trabajo se detengan actualmente. Los procesos cambiarán primero a &quot;INICIO&quot; y luego a &quot;EJECUCIÓN&quot;. Los datos asociados con el flujo de trabajo no inicios en la sincronización hasta que el flujo de trabajo esté en estado &quot;EN EJECUCIÓN&quot;.

   El botón inicio es un botón de alternancia. Si los procesos de flujo de trabajo ya se han iniciado, el botón cambiará a un botón **Detener**.

* **Detener**: Un  **** botón Stopbutton solicita que se detenga un flujo de trabajo en ejecución. Este botón solo aparecerá cuando los procesos asociados con el flujo de trabajo se estén ejecutando.

Cuando edita un flujo de trabajo, las actualizaciones NO se incorporan inmediatamente a las reglas de los procesos en ejecución hasta que detenga el flujo de trabajo y, a continuación, haga clic en el botón **Inicio**. A continuación, las actualizaciones se incorporan a los procesos en ejecución (una vez que el proceso vuelve a un estado **EJECUTANDO**).

Se agrega una indicación de advertencia al botón **Detener** para informarle de cuándo (a) ha realizado actualizaciones en el flujo de trabajo, pero (b) no ha realizado un Inicio/detención de este flujo de trabajo.

![](assets/d365-to-acs-icon-stop-with-changes.png)
