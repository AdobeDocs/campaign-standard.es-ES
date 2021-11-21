---
title: Introducción a la integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo empezar a utilizar la integración con Microsoft Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: fa0f790d-6a4d-4b83-a51f-f565e9545a1a
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 5%

---

# Introducción a la integración con Microsoft Dynamics 365

Active sus datos CRM en la comunicación entre canales: obtenga información sobre cómo pasar contactos de Microsoft Dynamics 365 a Adobe Campaign y compartir datos de rendimiento de campañas (envíos, aperturas, clics y devoluciones) de Adobe Campaign a Microsoft Dynamics 365.

Esta integración requiere las siguientes versiones de software:

* Solo Microsoft Dynamics 365 para ventas en línea, versión más reciente

* Adobe Campaign Standard, última versión

>[!CAUTION]
>
>Esta capacidad no está disponible de forma predeterminada como parte del producto. La implementación requiere la participación de Adobe Consulting. Póngase en contacto con el representante de su Adobe para obtener más información.

## Principios

La integración de Adobe Campaign Standard con Microsoft Dynamics 365 permite la sincronización de todos los datos de contacto disponibles en el sistema CRM, lo que hace que todos los datos de contacto relevantes estén disponibles para las actividades de campaña.

Por el contrario, a medida que los perfiles de Adobe Campaign Standard interactúan con los mensajes, esos datos (p. ej.: envía, abre, hace clic y salta) se transfiere automáticamente a Microsoft Dynamics 365 para mantener los registros de contacto completos con la actividad de marketing.

La integración también admite la activación de [entidades personalizadas](../../integrating/using/d365-acs-self-service-app-settings.md) en Dynamics 365 para sincronizar con **recursos personalizados** en Campaign.

Esta integración está diseñada para admitir cuatro casos de uso principales:

1. Sincronización de contactos de Dynamics 365 a Campaign para que se puedan segmentar en las campañas de marketing
1. Sincronización de entidades personalizadas de Dynamics 365 a Campaign para que se puedan utilizar para la segmentación y la personalización
1. Envío de eventos de marketing por correo electrónico (envíos, aperturas, clics, devoluciones) de Campaign a Dynamics 365 para mostrarlos en el repositorio de ventas en la interfaz de Dynamics 365
1. Sincronizar los estados de exclusión (por ejemplo, no enviar correo electrónico) entre Dynamics 365 y Campaign para mantener las preferencias de privacidad del cliente.

Los beneficios principales son:

* Mensajería coherente entre ventas y marketing: la integración de Adobe Campaign Standard con Dynamics 365 proporciona a ambos sistemas acceso a la perspectiva del cliente y al historial de marketing por correo electrónico, lo que permite que todos los mensajes al cliente compartan la misma mensajería coherente.

* Vista holística de todos los datos de clientes y posibles clientes: al integrar Adobe Campaign Standard con Dynamics 365, es posible compartir y acceder al historial de marketing por correo electrónico en cada contacto desde el sistema CRM.

* Active los datos de Dynamics 365 en cualquier canal: con los datos de contacto sincronizados con Adobe Campaign, las comunicaciones se pueden enviar en cualquier canal en línea o sin conexión con Campaign, incluidos los mensajes push, en la aplicación, el correo electrónico o el correo postal móviles. La campaña &quot;ha cubierto&quot; independientemente del canal preferido de cada contacto.

>[!CAUTION]
>
>Esta integración considera a Dynamics 365 como la fuente de verdad para la sincronización de contactos y entidades personalizadas.  Cualquier cambio en los atributos sincronizados debe realizarse en Dynamics 365, no en Adobe Campaign Standard.  Si los cambios se realizan en Campaign, finalmente se pueden sobrescribir durante la sincronización.

## Pasos clave para implementar la integración con Microsoft Dynamics 365{#request-and-implement-this-integration}

Para aprovisionar esta integración, debe seguir los pasos a continuación.

Siga los detalles del diagrama de flujo y del diagrama de flujo a continuación para solicitar y configurar la integración.

![](assets/provisioning-wf.png)

Detalles del diagrama de flujo (se asigna a los pasos anteriores):

* **Paso 1** - Se da por hecho que ya dispone de una licencia para Microsoft Dynamics 365 for Sales y para Adobe Campaign Standard o está en proceso de adquirirla.
* **Paso 2** - La oferta de integración estándar es gratuita para todos los clientes; sin embargo, pueden aplicarse costes adicionales en función de sus necesidades. Más información sobre [Prácticas recomendadas y limitaciones](../../integrating/using/d365-acs-notices-and-recommendations.md). Será necesario firmar un nuevo pedido de ventas (SO) para aprovechar la integración si no se incluyó en el SO original.
* **Paso 3** - Complete los pasos previos a la integración para Dynamics 365 y Campaign. Consulte [Configurar esta integración](#configure-this-integration).
* **Paso 4** : El equipo de incorporación de Adobe le proporcionará acceso a la interfaz de usuario (IU) de la aplicación de integración.
* **Paso 5** : podrá configurar sus asignaciones de datos, reemplazos, filtros, etc. y pruebe la integración desde la interfaz de usuario de la aplicación de integración.

   >[!IMPORTANT]
   >
   > Si necesita la configuración de exclusión bidireccional o de Campaign a Dynamics 365, deberá realizar la solicitud al contacto técnico de Adobe para que los flujos de trabajo de exclusión se configuren en la instancia de Campaign. [Más información](../../integrating/using/d365-acs-notices-and-recommendations.md#opt-out).

### Configurar esta integración {#configure-this-integration}

Se deben aprovisionar y configurar tres sistemas para esta integración:

* **Adobe Campaign Standard**: debe configurar el acceso a la API y configurar una nueva integración para la herramienta de integración. Para conseguirlo, consulte [este artículo](../../integrating/using/d365-acs-configure-adobe-io.md).
* **Microsoft Dynamics 365**: debe crear un nuevo registro de aplicación y permitir que un usuario de la aplicación utilice la integración.  Para configurar Microsoft Dynamics 365 para esta integración, consulte [este artículo](../../integrating/using/d365-acs-configure-d365.md).
* **Integración de Adobe Campaign Standard con la aplicación de autoservicio de Microsoft Dynamics 365**: tendrá que seguir los pasos indicados en [este artículo](../../integrating/using/d365-acs-self-service-app-control-access.md).

>[!IMPORTANT]
>
>Para cada sistema, estos pasos debe realizarlos un **administrador**.
>
>Los pasos de esta documentación le guiarán a través de la creación de integraciones/registros que implican la asignación de permisos y/o acceso de administrador.  Es su responsabilidad asegurarse de que estos pasos cumplan con las políticas de su empresa antes de realizarlas y realizarlas con cuidado.

### Solicitud de asistencia

Los tickets de asistencia técnica se pueden registrar con el Servicio de atención al cliente de Adobe.

Para cualquier problema con los flujos de datos de integración, asegúrese de incluir la siguiente información:

* **Propietario del proceso**: Arquitectos de Ingeniería
* **ID de proceso ES**: Proporcionado durante el proceso de incorporación
* **Título del proceso**: Integración de Microsoft Dynamics 365/Adobe Campaign Standard
* **Descripción del problema**: Descripción del problema

La cobertura de soporte de integración es actualmente de 24x5 (disponible de lunes a viernes, excluyendo feriados de Adobe y periodos de descanso).
