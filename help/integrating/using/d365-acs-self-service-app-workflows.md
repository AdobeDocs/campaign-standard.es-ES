---
title: Flujos de trabajo de las aplicaciones de integración
description: Flujos de trabajo de integración de Campaign y Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Integración de Microsoft CRM
role: Arquitecto de datos
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 1%

---


# Campaign: flujos de trabajo de integración con Microsoft Dynamics 365

La página **[!UICONTROL Workflows]** enumera los flujos de trabajo técnicos y su estado.

La aplicación de integración incluye tres flujos de trabajo:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 a Campaign**
* Enviar *contactos* de Microsoft Dynamics 365 a Adobe Campaign
* *Entidades* personalizadas: Incorpore tablas personalizadas de Microsoft Dynamics 365 a Adobe Campaign. [Obtenga más información](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Esto también se conoce como **Ingreso** (en referencia a la ingesta de datos de Microsoft Dynamics 365 a Adobe Campaign)

**Campaign a Microsoft Dynamics 365**
* Los eventos de marketing por correo electrónico de Adobe Campaign Standard se envían a Dynamics 365 (envío de correo electrónico, apertura, clic, rechazo). [Obtenga más información](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Esto también se conoce como **Egress** (en referencia a la salida de datos de Adobe Campaign a Microsoft Dynamics 365)

**Inclusión/exclusión**

Los estados de exclusión (por ejemplo, la  de lista de bloqueados) se pueden sincronizar de Microsoft Dynamics 365 a Adobe Campaign o de Adobe Campaign a Microsoft Dynamics 365. Los datos también pueden sincronizarse bidireccionalmente (es decir, flujos de datos en ambas direcciones). [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Se recomienda detener el flujo de trabajo **Microsoft Dynamics 365 to Campaign** antes de publicar los cambios en Adobe Campaign Standard o Microsoft Dynamics 365. Estos cambios incluyen actualizaciones de recursos/entidades (y sus campos asociados), vínculos, columnas de identificadores, etc. que la integración está utilizando actualmente. Si no lo hace, podría causar la pérdida de datos o que el flujo de trabajo se detenga de forma inesperada.

## Retraso de flujo de trabajo

Esta aplicación de integración primero lee los datos y después escribe los datos en el destino. La columna **[!UICONTROL Backlog]** indica el número de registros que se han puesto en cola y que están a la espera de ser escritos. Se espera que este valor crezca cuando tenga una gran cantidad de datos para procesar (por ejemplo, está ejecutando la integración por primera vez, está reproduciendo los datos, etc.).

>[!NOTE]
>Si los registros de Microsoft Dynamics 365 y/o Campaign no se actualizan, primero debe comprobar si hay un gran número de registros esperando a que se escriban en el destino.


## Estado del flujo de trabajo {#workflow-status}

La columna **[!UICONTROL Status]** indica el estado de los procesos en segundo plano asociados al flujo de trabajo. Los valores posibles son:

* **EJECUTANDO**: El proceso se está ejecutando y los datos deben sincronizarse.
* **DETENIDO**: El proceso no se está ejecutando actualmente, por lo que no debería esperar que los datos se sincronicen.
* **INICIO**: Ha solicitado que se inicie el flujo de trabajo. La aplicación aún no ha comenzado a sincronizar los datos asociados con este flujo de trabajo, pero puede esperar que lo haga después de unos minutos (cuando luego mostrará el estado de **EJECUTANDO**)
* **ERROR**: Los procesos de flujo de trabajo se estaban ejecutando, pero se encontraron errores y no se pudieron recuperar de ellos.

## Acciones disponibles

A continuación se enumeran las posibles acciones.

* **Editar**: Al hacer clic en el icono de lápiz, se le enviará a otra página que le permitirá actualizar el flujo de trabajo. Tenga en cuenta que cualquier cambio que realice NO tendrá efecto hasta que detenga el flujo de trabajo y luego lo reinicie.

* **Inicio**: Un botón Start solicita que se inicie un flujo de trabajo detenido. Este botón solo aparece cuando los procesos asociados con el flujo de trabajo están actualmente detenidos. Los procesos cambiarán primero a &quot;INICIO&quot; y después a &quot;EJECUCIÓN&quot;. Los datos asociados con el flujo de trabajo no se sincronizarán hasta que el flujo de trabajo esté en estado &quot;EN EJECUCIÓN&quot;.

   El botón de inicio es un botón de alternancia. Si los procesos del flujo de trabajo ya se han iniciado, el botón cambiará a un botón **Stop**.

* **Detener**: Un  **** Stopbutton solicita que se detenga un flujo de trabajo en ejecución. Este botón solo aparece cuando los procesos asociados al flujo de trabajo se estén ejecutando.

Al editar un flujo de trabajo, las actualizaciones NO se incorporan inmediatamente a las reglas de los procesos en ejecución, hasta que detenga el flujo de trabajo y, a continuación, haga clic en el botón **Start**. A continuación, las actualizaciones se incorporan a los procesos en ejecución (una vez que el proceso vuelve a estar en estado **EJECUTANDO**).

Se agrega una indicación de advertencia al botón **Stop** para informarle cuando (a) ha realizado actualizaciones en el flujo de trabajo, pero (b) no ha realizado una detención/inicio de este flujo de trabajo.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
