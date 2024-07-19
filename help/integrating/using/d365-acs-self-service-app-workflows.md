---
title: Flujos de trabajo de aplicación de integración
description: Flujos de trabajo de integración de Campaign y Dynamics
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: 51f07f08-5d57-4c4c-aff2-d03e5956ec6f
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 1%

---

# Flujos de trabajo de integración de Campaign - Microsoft Dynamics 365

La página **[!UICONTROL Workflows]** enumera los flujos de trabajo técnicos y su estado.

La aplicación de integración incluye tres flujos de trabajo:

![](assets/do-not-localize/d365-to-acs-ui-page-workflows.png)

**Microsoft Dynamics 365 a Campaign**
* Enviar *contactos* de Microsoft Dynamics 365 a Adobe Campaign
* *Entidades personalizadas*: Traiga tablas personalizadas de Microsoft Dynamics 365 a Adobe Campaign. [Más información](../../integrating/using/d365-acs-using-the-integration.md#data-flows)
* Esto también se conoce como **Ingreso** (en referencia al ingreso de datos de Microsoft Dynamics 365 a Adobe Campaign)

**Campaña a Microsoft Dynamics 365**
* Los eventos de marketing por correo electrónico de Adobe Campaign Standard se envían a Dynamics 365 (envío de correo electrónico, apertura, clic, rechazo). [Más información](../../integrating/using/d365-acs-using-the-integration.md#email-marketing-event-flow)
* Esto también se conoce como **salida** (en referencia a la salida de datos de Adobe Campaign a Microsoft Dynamics 365)

**Inclusión/Exclusión**

Los estados de exclusión (por ejemplo, lista de bloqueados de) se pueden sincronizar de Microsoft Dynamics 365 a Adobe Campaign o de Adobe Campaign a Microsoft Dynamics 365. Los datos también pueden sincronizarse bidireccionalmente (es decir, los datos fluyen en ambas direcciones). [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!IMPORTANT]
>
>Se recomienda detener el flujo de trabajo **Microsoft Dynamics 365 to Campaign** antes de publicar cambios en Adobe Campaign Standard o Microsoft Dynamics 365. Estos cambios incluyen actualizaciones de recursos/entidades (y sus campos asociados), vínculos, columnas de identificador, etc. que la integración está utilizando actualmente. Si no se hace esto, los datos se pueden perder o el flujo de trabajo podría detenerse inesperadamente.

## Registro de flujo de trabajo

Esta aplicación de integración lee primero los datos y luego los escribe en el destino. La columna **[!UICONTROL Backlog]** indica el número de registros que se han puesto en cola y que están a la espera de ser escritos. Se espera que este valor crezca cuando tenga una gran cantidad de datos para procesar (por ejemplo, cuando ejecute la integración por primera vez, cuando reproduzca los datos, etc.).

>[!NOTE]
>Si los registros de Microsoft Dynamics 365 o Campaign no se actualizan, primero debe comprobar si hay un gran número de registros esperando a escribirse en el destino.
>

## Estado del flujo de trabajo {#workflow-status}

La columna **[!UICONTROL Status]** indica el estado de los procesos en segundo plano asociados con el flujo de trabajo. Los valores posibles son:

* **EN EJECUCIÓN**: el proceso se está ejecutando actualmente y los datos deben sincronizarse.
* **DETENIDO**: el proceso no se está ejecutando, por lo que no debería esperar que los datos se sincronizaran.
* **INICIANDO**: ha solicitado que se inicien los procesos del flujo de trabajo. La aplicación aún no ha comenzado a sincronizar los datos asociados con este flujo de trabajo, pero se espera que sea después de unos minutos (cuando mostrará el estado de **EN EJECUCIÓN**)
* **ERROR**: los procesos de flujo de trabajo se estaban ejecutando, pero encontraron errores y no pudieron recuperarse de ellos.

## Acciones disponibles

Las acciones posibles se enumeran a continuación.

* **Editar**: Al hacer clic en el icono de lápiz, se le enviará a otra página que le permitirá realizar actualizaciones en el flujo de trabajo. Tenga en cuenta que los cambios que realice NO surtirán efecto hasta que detenga el flujo de trabajo y, a continuación, lo reinicie.

* **Inicio**: Un botón Inicio solicita que se inicie un flujo de trabajo detenido. Este botón solo aparece cuando los procesos asociados al flujo de trabajo están detenidos actualmente. Los procesos cambiarán primero a &quot;INICIO&quot; y luego a &quot;EN EJECUCIÓN&quot;. Los datos asociados con el flujo de trabajo no empezarán a sincronizarse hasta que el flujo de trabajo esté en estado &quot;EN EJECUCIÓN&quot;.

  El botón de inicio es una opción. Si los procesos de flujo de trabajo ya se han iniciado, el botón cambiará a **Detener**.

* **Stop**: Un botón **Stop** solicita que se detenga un flujo de trabajo en ejecución. Este botón solo aparece cuando los procesos asociados al flujo de trabajo se están ejecutando actualmente.

Cuando edita un flujo de trabajo, las actualizaciones NO se incorporan inmediatamente a las reglas de los procesos en ejecución, hasta que detiene el flujo de trabajo y, a continuación, hace clic en el botón **Iniciar**. A continuación, las actualizaciones se incorporarán a los procesos en ejecución (una vez que el proceso vuelva a un estado **EN EJECUCIÓN**).

Se agrega una indicación de advertencia al botón **Stop** para que sepa cuándo (a) ha realizado actualizaciones en el flujo de trabajo, pero (b) no ha realizado ninguna detención o inicio de este flujo de trabajo.

![](assets/do-not-localize/d365-to-acs-icon-stop-with-changes.png)
