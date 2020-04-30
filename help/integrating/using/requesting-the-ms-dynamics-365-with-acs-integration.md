---
title: Solicitar y configurar la integración de Microsoft Dynamics 365
description: Obtenga información sobre cómo solicitar y configurar Microsoft Dynamics 365 con la integración de Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 277663c4cf0e810f691eeebfade17bf8dd73698e

---


# Solicitar y configurar la integración de Microsoft Dynamics 365

Para aprovisionar esta integración, deberá seguir los pasos a continuación.

Please note that this integration uses a third-party provider, Unifi.  En relación con sus solicitudes de asistencia, es posible que Adobe deba compartir la información de su instancia de Adobe Campaign con Unifi.

Para solicitar y configurar la integración, siga los detalles de diagrama de flujo y diagrama de flujo que se indican a continuación.

![](assets/provisioning-wf.png)

Detalles del diagrama de flujo (se asigna a los pasos anteriores):

1. Ya debe tener aprovisionado Campaign Standard y Microsoft Dynamics 365, con acceso de administrador a inicio para implementar esta integración.

1. Lea este artículo, avisos de comprobación y pasos de configuración.

1. Enviar una solicitud de cuenta a adobe-support@unifisoftware.com; Unifi requerirá la siguiente información cuando solicite una cuenta:
   * Nombre del usuario
   * Apellido del usuario
   * Correo electrónico del usuario
   * Nombre de Compañía
   * Región (Norteamérica, EMEA o APAC)
   * Tipo de uso:  Tipo de cliente (usuarios de clientes que utilizarán sus datos de producción en esta integración), o Tipo de socio (consultores de socios que están probando la integración para comprender mejor cómo pueden ayudar a sus clientes de Campaña) o Tipo interno (usuarios internos de Adobe que están probando la integración para comprender mejor la solución)
   * Estado de datos del Campaign Standard (comenzando con una base de datos limpia o llevando los datos existentes a la integración)
   * ID de inquilino de Campaña (consulte la sección 3 de configuración de la integración de Campaña para obtener su ID de inquilino)
   * URL de instancia de Campaña
   Tiempo de respuesta esperado de Unifi: 1 hora durante el horario laboral habitual de EE.UU. (de 9:00 a 17:00, hora del Pacífico, de lunes a viernes, excluidas las vacaciones).

1. Complete los pasos posteriores al aprovisionamiento para Microsoft Dynamics 365 y para Campaign Standard.
Además, envíe un ticket al Servicio de atención al cliente de Adobe (directamente o a través de su contacto de Adobe) para habilitar el indicador de inicio de sesión único en la instancia de Campaña. Los socios deben ponerse en contacto con el representante de la zona de pruebas de su socio de Adobe, en lugar de ponerse en contacto con el Servicio de atención al cliente de Adobe, para habilitar el indicador de la función.
Si tiene datos existentes en Campaña que tiene previsto incorporar a la integración, siga las instrucciones de &quot;Datos de Campaña existentes&quot; y consulte con su contacto técnico de Adobe antes de continuar.

1. Complete los pasos iniciales de incorporación en Unifi navegando a Unifi, haciendo clic en las pantallas de embarque, rellenando las credenciales de cuenta de Dynamics 365 y Campaign Standard y notificando a Unifi cuando se haya completado.

1. Unifi solicitará al cliente la configuración de exclusión deseada y la asignación de atributos de exclusión.

1. El cliente indicará la configuración de exclusión seleccionada y la asignación de atributos de exclusión.
Tiempo de respuesta esperado de Unifi: 1 día hábil (de lunes a viernes, excluidos los festivos)

1. La configuración de Unifi implica la revisión de asignaciones de OOTB, filtros, trabajos, etc. y efectuar modificaciones, si es necesario.  Consulte la Guía del usuario de Unifi para obtener más información.
Este paso implica establecer la frecuencia de ejecución de los programas Unifi
* Establecer la frecuencia de ejecución de las programaciones en la pantalla de programaciones de Unifi; sin embargo, para las programaciones de &quot;ingreso&quot; y &quot;egreso&quot;, ejecútelas manualmente una vez antes de establecer la frecuencia de programación
* Se recomiendan las siguientes frecuencias de programación: Ingreso (15 minutos), Salida (15 minutos), Eliminaciones (una vez al día), Opciones de exclusión (una vez al día)

**Se recomienda que trabaje con Unifi y/o con asesores de Adobe (póngase en contacto con el equipo de su cuenta de Adobe) al configurar Unifi.**

Para habilitar la integración entre Adobe Campaign Standard y Microsoft Dynamics 365, los clientes deben crear una cuenta de usuario con Unifi, un proveedor de terceros, como se describe en este documento.   Como usuario final del sistema Unifi, para cualquier consulta relacionada con solicitudes de datos iniciadas por clientes dentro del sistema Unifi, el cliente debe ponerse en contacto con Unifi.

## Configuración de esta integración

Es necesario aprovisionar y configurar tres sistemas para esta integración: Adobe Campaign Standard, Microsoft Dynamics 365 para ventas y Unifi. Los artículos de configuración están vinculados a continuación.

>[!CAUTION]
>
>Para cada sistema, estos pasos deben ser realizados por un administrador.
>
>Los pasos de los artículos siguientes le guiarán a través de la creación de integraciones/registros que implican la asignación de permisos y/o acceso de administrador.  Es su responsabilidad asegurarse de que estos pasos cumplan con las directivas de compañía antes de realizar el proceso y llevarlos a cabo con cuidado.

En ADOBE CAMPAIGN, debe configurar el acceso a la API y configurar una nueva integración para Unifi. Para lograrlo, consulte [este artículo](../../integrating/using/configure-adobe-io-for-ms-dynamic.md).

En MICROSOFT DYNAMICS 365, debe crear un nuevo registro de aplicación y permitir que un usuario de la aplicación utilice la integración.  Para configurar Microsoft Dynamics 365 para esta integración, consulte [este artículo](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md).

En UNIFI, debe configurar la integración y configurar la asignación o agregar atributos personalizados. Para configurar Unifi para esta integración, consulte [este artículo](../../integrating/using/configure-unifi-for-microsoft-dynamics-365-integration.md).

## Solicitud de asistencia

Si tiene problemas, póngase en contacto con el servicio de asistencia al cliente de Unifi: [support@unifisoftware.atlassian.net](mailto:support@unifisoftware.atlassian.net).

Tiempo de respuesta esperado de Unifi: 4 horas durante el horario laboral habitual de EE.UU. (de 9:00 a 17:00, hora del Pacífico, de lunes a viernes, excluidas las vacaciones).

>[!CAUTION]
>
>En relación con su solicitud de asistencia, es posible que Adobe deba compartir la información de su instancia de Adobe Campaign con Unifi.