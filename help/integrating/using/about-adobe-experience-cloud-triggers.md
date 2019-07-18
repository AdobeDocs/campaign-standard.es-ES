---
title: Acerca de Adobe Experience Cloud Triggers
seo-title: Acerca de Adobe Experience Cloud Triggers
description: Acerca de Adobe Experience Cloud Triggers
seo-description: Al rastrear comportamientos específicos de clientes con Adobe Analytics, ahora puede enviar correos electrónicos personalizados a sus clientes en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 0 aa 4 bd 6 e -1 bb 5-4 d 0 b -913 b-eca 93 f 050 acd
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: integrar
content-type: reference
topic-tags: trabajar con campaña y activadores
discoiquuid: e 526 b 205-2 d 01-4 a 8 b -9685-ba 1 d 9 a 1 f 459 f f
context-tags: trigger, overview; activador, principal
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# About Adobe Experience Cloud Triggers{#about-adobe-experience-cloud-triggers}

Integration between the Experience Cloud Activation core service **[!UICONTROL Triggers]** and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).

En Adobe Experience Cloud, usted define los distintos activadores, es decir, los comportamientos del cliente que desea monitorear, como todos los clientes que abandonaron su visita en el sitio Web, realizaron una búsqueda en su sitio Web pero no realizaron una compra, ni siquiera los clientes cuya sesión caducó. Al crear un activador, se define la condición del activador y los datos que se enviarán en el evento (proceso de carga) a Adobe Campaign.

En Adobe Campaign, se selecciona el activador que se creó anteriormente, se enriquecen los datos del evento con datos de datos y se define una plantilla de mensaje transaccional vinculada a dicho activador. Por ejemplo, cuando un cliente abandona su visita en el sitio Web, se envía un evento a Adobe Campaign, el cual puede aprovechar este evento a través de un correo electrónico de remercadotecnia que se envía al cliente en un plazo de 15 minutos.

**Temas relacionados:**

* Learn about the different types of triggers: [Adobe Experience Cloud documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/triggers.html).
* Watch the [Trigger Remarketing Messages based on Site Activity](https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html#step-two) video.
* Discover our two [Abandonment Triggers use cases](../../integrating/using/abandonment-triggers-use-cases.md).

## Triggers user process {#triggers-user-process}

>[!CAUTION]
>
>Antes de ejecutar los pasos principales del usuario, es necesario configurar la funcionalidad. For more on this refer to [Activating the functionality](../../integrating/using/configuring-triggers-in-experience-cloud.md#activating-the-functionality), [Configuring solutions and services](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services) and [Creating a mapped trigger in Campaign](../../integrating/using/using-triggers-in-campaign.md#creating-a-mapped-trigger-in-campaign).

Los pasos principales del proceso de usuario, en Adobe Campaign, son los siguientes:

1. Cree un evento desencadenador vinculado a un activador de Adobe Experience Cloud existente.
1. Publique el evento desencadenador.
1. Defina el contenido de la plantilla de mensaje transaccional.
1. Pruebe la plantilla (cree un perfil de prueba y envíe una prueba).
1. Publique la plantilla de mensaje transaccional.

Complete use cases are described in [this section](../../integrating/using/abandonment-triggers-use-cases.md).

## Important notes {#important-notes}

A continuación se indican algunas notas importantes que hay que tener en cuenta antes de utilizar Activadores - Integración de campañas:

* Las notificaciones push no son compatibles con activadores. Solo se admiten correo electrónico y SMS.
* Puede enriquecer el activador con metadatos capturados a través de Analytics, como ID de correo electrónico, nombre de página, etc.
* Puede reconciliar el activador a un perfil almacenado en Campaign Standard y utilizar los campos del perfil para personalizar el mensaje.
* Tan pronto como se recibe un activador, se procesa y se reconcilia y se envía. Se tarda unos 5 ó 15 minutos en variar según el volumen de activadores recibidos, el número de campos de personalización que se utilizan en la plantilla.

>[!NOTE]
>
>For more on best practices and technical limitations, refer to [Triggers best practices and limitations](../../integrating/using/configuring-triggers-in-experience-cloud.md#triggers-best-practices-and-limitations).

