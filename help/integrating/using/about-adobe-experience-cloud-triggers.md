---
title: Acerca de los activadores de Adobe Experience Cloud
description: Al seguir comportamientos específicos de clientes con Adobe Analytics, ahora puede enviar correos electrónicos personalizados a sus clientes en Adobe Campaign.
page-status-flag: never-activated
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-triggers
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: trigger,overview;trigger,main
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 100%

---


# Acerca de los activadores de Adobe Experience Cloud{#about-adobe-experience-cloud-triggers}

La integración entre el servicio principal de activación de Experience Cloud **[!UICONTROL Triggers]** y Adobe Campaign le permite enviar mensajes de correo electrónico personalizados a sus clientes como una reacción ante comportamientos específicos rastreados en el sitio web mediante Adobe Analytics (en 15 minutos).

En Adobe Experience Cloud, define los distintos activadores; es decir, los comportamientos de cliente que desea monitorizar, como todos los clientes que abandonaron su visita en el sitio web; aquellos que realizaron una búsqueda en el sitio web, pero no realizaron una compra; o incluso los clientes cuya sesión expiró. Al crear un activador, se define la condición del activador y los datos que se enviarán en el evento (carga) a Adobe Campaign.

En Adobe Campaign, se selecciona el activador creado anteriormente, se enriquecen los datos de evento con datos datamart y se define una plantilla de mensaje transaccional vinculada a dicho activador. Por ejemplo, cuando un cliente abandona su visita a su sitio web, se envía un evento a Adobe Campaign que puede aprovechar este evento mediante un correo electrónico de remarketing que se envía al cliente en un plazo de 15 minutos.

El diagrama siguiente detalla cómo funciona esta integración.

![](assets/triggers_diagram.png)

**Temas relacionados:**

* Obtenga información sobre los distintos tipos de activadores: [Documentación de Adobe Experience Cloud](https://docs.adobe.com/content/help/es-ES/core-services/interface/activation/triggers.html).
* Vea los [mensajes de remarketing de activador basados en el vídeo de Actividad del sitio](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two).
* Descubra nuestros dos [ejemplos prácticos de activadores de abandono](../../integrating/using/abandonment-triggers-use-cases.md).

## Activa el proceso de usuario {#triggers-user-process}

>[!CAUTION]
>
>Antes de ejecutar los pasos principales del usuario, es necesario configurar la funcionalidad. Para obtener más información al respecto, consulte [Activación de la funcionalidad](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuración de soluciones y servicios](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) y [Creación de un activador asignado en Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

Los pasos principales del proceso del usuario en Adobe Campaign son estos:

1. Cree un evento activador vinculado a un activador de Adobe Experience Cloud existente.
1. Publique el evento activador.
1. Defina el contenido de la plantilla de mensaje transaccional.
1. Pruebe la plantilla (cree un perfil de prueba y envíe una prueba).
1. Publique la plantilla de mensaje transaccional.

Los casos de uso completos se describen en [esta sección](../../integrating/using/abandonment-triggers-use-cases.md).

## Notas importantes {#important-notes}

Estas son algunas notas importantes que deben tenerse en cuenta antes de utilizar la integración Activadores - Campaign:

* Las notificaciones push no son compatibles con los activadores. Solo se admiten mensajes de correo electrónico y SMS.
* Puede enriquecer el activador con metadatos capturados a través de Analytics, como ID de correo electrónico, nombre de página, etc.
* Puede reconciliar el activador con un perfil almacenado en Campaign Standard y utilizar los campos del perfil para personalizar el mensaje.
* En cuanto se recibe un activador, se procesa, se concilia y se envía. Tarda entre 5 y 15 minutos en función del volumen de activadores recibidos y el número de campos de personalización utilizados en la plantilla.

>[!NOTE]
>
>Para obtener más información sobre las prácticas recomendadas y las limitaciones técnicas, consulte [Activadores, prácticas recomendadas y limitaciones](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

