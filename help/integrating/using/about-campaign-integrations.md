---
title: Introducción a las integraciones de Campañas
description: Adobe Campaign le permite utilizar otras soluciones de Adobe y combinar sus diferentes funciones.
page-status-flag: never-activated
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: f7adb7a4725129727010c2486ca34bbc2021c539
workflow-type: tm+mt
source-wordcount: '592'
ht-degree: 19%

---


# Acerca de las integraciones de Campaign{#get-started-campaign-integrations}

Esta sección detalla las integraciones funcionales disponibles entre la versión actual de Adobe Campaign y otras soluciones y servicios.

Las diferentes integraciones presentadas a continuación le permiten combinar las funcionalidades de envío y gestión de la campaña avanzada de Adobe Campaign con un conjunto de soluciones creadas para ayudarle a personalizar la experiencia de sus usuarios.

>[!NOTE]
>
> De forma predeterminada, Adobe Campaign ya está vinculado a una cuenta de Adobe Experience Cloud.

Según el entorno, otras soluciones también se pueden vincular a Adobe Experience Cloud. Están vinculados como Organizaciones (también llamados Inquilinos).

Una organización es la entidad que permite a un administrador configurar grupos y usuarios y controlar el inicio de sesión único en Experience Cloud. La organización funciona como una empresa de inicio de sesión que abarca todos los productos y soluciones de Experience Cloud. Generalmente, la organización es el nombre de la empresa. Sin embargo, una empresa puede tener muchas organizaciones. La administración de usuarios y organizaciones se detalla en el portal [de ayuda de](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html)Adobe Experience Cloud.

Si desea integrar flujos de datos de otros sistemas con Adobe Campaign, consulte nuestra documentación [de](../../api/using/get-started-apis.md)API.

<table> 
 <thead> 
  <tr> 
   <th> Solución<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Consulte<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4, 6.5<br /> </td> 
   <td> Permite crear contenido de correo electrónico o formularios asignados a la base de datos de Adobe Campaign directamente en Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Trabajar con Campaña y Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">Integrar Experience Manager y Campaign Standard</a> <br/>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">crear un correo electrónico con Experience Manager y Campaña</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Destinatario<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Trabaje con Campaña y Destinatario</a> <br/>, <a href="https://docs.adobe.com/content/help/en/target/using/integrate/campaign-and-target.html">integre Campaña y Destinatario</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">personalice imágenes de correo electrónico en vídeo en tiempo</a> real (paso 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Le permite realizar un seguimiento del éxito de sus envíos de correo electrónico directamente en Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Compartir datos de Campaña con Analytics</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Compartir KPI para vídeo integrado de sistema de informes</a> de Campañas (paso 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager y servicio principal Personas (Perfiles y Audiencias)<br /> </td> 
   <td> Le permite intercambiar audiencias con las distintas aplicaciones de Adobe Experience Cloud que utilice.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Servicio principal de personas (Perfiles y Audiencias)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Servicio principal de recursos y Recursos On Demand<br /> </td> 
   <td> Permite insertar activos de la biblioteca de Adobe Experience Cloud en correos electrónicos y páginas de destino creadas en Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Servicio</a> principal de recursos o Recursos On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Puntos de interés (Analytics para dispositivos móviles)<br /> </td> 
   <td> Permite recopilar datos de puntos de interés de los suscriptores de la aplicación móvil para enviar mensajes de marketing personalizados con Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Envío de mensajes de marketing basados en la ubicación con datos</a> de Campaña y puntos de interés (Analytics para dispositivos móviles)<br /> </td> 
  </tr> 
  <tr> 
   <td> Activadores de Experience Cloud<br /> </td> 
   <td> Le permite enviar correos electrónicos personalizados a sus clientes en Adobe Campaign como reacción a comportamientos específicos que Adobe Analytics rastrea en su sitio web.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Utilizar activadores de Experience Cloud en casos</a><br/>de uso de Campaign Standard <a href="../../integrating/using/abandonment-triggers-use-cases.md">, activadores de</a><br/>abandono, casos <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">de uso de Campañas y mensajes de remercadotecnia de</a> activadores basados en vídeo de Actividaddel sitio (paso 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Permite editar un contenido de correo electrónico desde Dreamweaver y sincronizarlo con Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">Crear correos electrónicos personalizados con el vídeo de Dreamweaver</a> <br/>, <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">utilizar la extensión de Campaña para Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDK de Experience Platform<br /> </td> 
   <td> Permite la automatización del proceso de activación de la propiedad de la aplicación móvil en Adobe Campaign mediante los SDK de Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Configuración de una aplicación móvil mediante SDK de Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

