---
title: Solicitar y configurar la integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo solicitar y configurar Microsoft Dynamics 365 con la integración de Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0ce73bf7e250c5e88bbb525854e81ef27662ab06
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 3%

---


# Solicitar y configurar la integración con Microsoft Dynamics 365

Para aprovisionar esta integración, deberá seguir los pasos a continuación.

Para solicitar y configurar la integración, siga los detalles de diagrama de flujo y diagrama de flujo que se indican a continuación.

![](assets/provisioning-wf.png)

Detalles del diagrama de flujo (se asigna a los pasos anteriores):

* **Paso 1** : se supone que ya dispone de una licencia para Microsoft Dynamics 365 para ventas y para Adobe Campaign Standard, o que está en proceso de adquirirla.

* **Paso 2** : la oferta de integración estándar es gratuita para todos los clientes; sin embargo, puede que se apliquen costos adicionales en función de sus necesidades (consulte [Barreras y límites](../../integrating/using/ms-dynamics-365-integration-guardrails.md)de integración. Será necesario firmar un nuevo pedido de ventas para aprovechar la integración.

* **Paso 3** : Complete los pasos previos a la integración para Dynamics 365 y la Campaña. Consulte [Configurar esta integración](#configure-this-integration).

* **Pasos 4-7** : El equipo de Adobe que se incorpora trabajará con usted a través del proceso de integración.

## Configurar esta integración {#configure-this-integration}

Es necesario aprovisionar y configurar tres sistemas para esta integración: Adobe Campaign Standard, Microsoft Dynamics 365 for Sales y la herramienta de integración. Los artículos de configuración están vinculados a continuación.

>[!CAUTION]
>
>Para cada sistema, estos pasos deben ser realizados por un administrador.
>
>Los pasos de los artículos siguientes le guiarán a través de la creación de integraciones/registros que implican la asignación de permisos y/o acceso de administrador.  Es su responsabilidad asegurarse de que estos pasos cumplan con las directivas de compañía antes de realizar el proceso y llevarlos a cabo con cuidado.

En ADOBE CAMPAIGN, debe configurar el acceso a la API y configurar una nueva integración para la herramienta de integración. Para lograrlo, consulte [este artículo](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

En MICROSOFT DYNAMICS 365, debe crear un nuevo registro de aplicación y permitir que un usuario de la aplicación utilice la integración.  Para configurar Microsoft Dynamics 365 para esta integración, consulte [este artículo](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

Deberá trabajar con el equipo de integración de Adobe para configurar la configuración de los flujos de datos de entrada, salida y exclusión.


## Solicitar asistencia

Los tickets de asistencia técnica pueden registrarse con Adobe Custom Care, como de costumbre; El Servicio de atención al cliente proporcionará personal de asistencia, según sea necesario.

Para cualquier problema con los flujos de datos de integración, asegúrese de incluir el grupo de informes como parte de la descripción del problema, así como la siguiente información:

* **Propietario** del proceso: Arquitectos de ingeniería

* **ID** de proceso ES: Proporcionado durante el proceso de integración

* **Título** del proceso: Integración de Dynamics 365/Adobe Campaign Standard

* **Descripción** del problema: Descripción del problema

La cobertura de soporte de integración es actualmente de 24x5 (disponible de lunes a viernes, excluyendo feriados de Adobe y períodos de interrupción).