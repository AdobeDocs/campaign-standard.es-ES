---
title: Acerca de los activadores de Adobe Experience Cloud
description: Al rastrear comportamientos específicos de clientes con Adobe Analytics, ahora puede enviar correos electrónicos personalizados a sus clientes en Adobe Campaign.
page-status-flag: nunca activado
uuid: 0aa4bd6e-1bb5-4d0b-913b-eca93f050acd
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: trabajar con campaña y activadores
discoiquuid: e526b205-2d01-4a8b-9685-ba1d9a1f459f
context-tags: desencadenador,descripción general;activador,principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de los activadores de Adobe Experience Cloud{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

En Adobe Experience Cloud, usted define los distintos activadores, es decir, los comportamientos de cliente que desea supervisar, como todos los clientes que abandonaron su visita en el sitio web, realizaron una búsqueda en el sitio web pero no realizaron una compra o incluso los clientes cuya sesión expiró. Al crear un activador, se define la condición del activador y los datos que se enviarán en el evento (carga) a Adobe Campaign.

 En Adobe Campaign, se selecciona el activador que se creó anteriormente, se enriquecen los datos del evento con datos de datamart y se define una plantilla de mensaje transaccional vinculada a ese activador. Por ejemplo, cuando un cliente abandona su visita a su sitio web, se envía un evento a Adobe Campaign, el cual puede aprovechar este evento mediante un correo electrónico de remercadotecnia que se envía al cliente en un plazo de 15 minutos.

**Temas relacionados:**

* Obtenga información sobre los distintos tipos de activadores: Documentación [de](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html)Adobe Experience Cloud.
* Vea el vídeo [Activador de mensajes de remercadotecnia basado en la actividad](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) del sitio.
* Descubrir nuestros dos [activadores de abandono utilizan casos](../../integrating/using/abandonment-triggers-use-cases.md).

## Activa el proceso de usuario {#triggers-user-process}

>[!CAUTION]
>
>Antes de ejecutar los pasos principales del usuario, es necesario configurar la funcionalidad. Para obtener más información sobre esto, consulte [Activación de la funcionalidad](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuración de soluciones y servicios](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) y [Creación de un activador asignado en Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

Los pasos principales del proceso de usuario, en Adobe Campaign, son:

1. Cree un evento desencadenador vinculado a un activador existente de Adobe Experience Cloud.
1. Publique el evento desencadenador.
1. Defina el contenido de la plantilla de mensaje transaccional.
1. Pruebe la plantilla (cree un perfil de prueba y envíe una prueba).
1. Publique la plantilla de mensaje transaccional.

Los casos de uso completo se describen en [esta sección](../../integrating/using/abandonment-triggers-use-cases.md).

## Notas importantes {#important-notes}

Estas son algunas notas importantes que deben tenerse en cuenta antes de utilizar la integración Triggers - Campaign:

* Las notificaciones push no son compatibles con los activadores. Solo se admiten los mensajes de correo electrónico y SMS.
* Puede enriquecer el activador con metadatos capturados a través de Analytics, como ID de correo electrónico, nombre de página, etc.
* Puede reconciliar el activador con un perfil almacenado en Campaign Standard y utilizar los campos del perfil para personalizar el mensaje.
* En cuanto se recibe un activador, se procesa, se concilia y se envía. Tarda entre 5 y 15 minutos en función del volumen de activadores recibidos, el número de campos de personalización utilizados en la plantilla.

>[!NOTE]
>
>Para obtener más información sobre las prácticas recomendadas y las limitaciones técnicas, consulte [Activadores, prácticas recomendadas y limitaciones](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

