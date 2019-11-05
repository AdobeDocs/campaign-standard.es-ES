---
title: Acerca de las integraciones de Campaign
description: Adobe Campaign le permite utilizar otras soluciones de Adobe y combinar sus diferentes capacidades.
page-status-flag: nunca activado
uuid: 59d7cd99-a6f7-47f1-9b5c-c50e27a2bef8
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: about-campaign-integrations
discoiquuid: 9633e9ca-3323-499b-8259-45165d59a4d0
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca de las integraciones de Campaign{#about-campaign-integrations}

Esta sección detalla las integraciones funcionales disponibles entre la versión actual de Adobe Campaign y otras soluciones y servicios.

Las distintas integraciones que se presentan a continuación le permiten combinar las funcionalidades de administración de campañas avanzadas y de entrega de Adobe Campaign con un conjunto de soluciones creadas para ayudarle a personalizar la experiencia de los usuarios.

>[!NOTE]
>
> De forma predeterminada, Adobe Campaign ya está vinculado a una cuenta de Adobe Experience Cloud.

Según el entorno, otras soluciones también se pueden vincular a Adobe Experience Cloud. Están vinculados como Organizaciones (también llamados Inquilinos).

Una organización es la entidad que permite a un administrador configurar grupos y usuarios y controlar el inicio de sesión único en Experience Cloud. La organización funciona como una empresa de inicio de sesión que abarca todos los productos y soluciones de Experience Cloud. Generalmente, la organización es el nombre de la empresa. Sin embargo, una empresa puede tener muchas organizaciones. La administración de usuarios y organizaciones se detalla en el portal [de ayuda de](https://marketing.adobe.com/resources/help/en_US/mcloud/organizations.html)Adobe Experience Cloud.

Si desea integrar flujos de datos de otros sistemas con Adobe Campaign, consulte nuestra documentación [](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html)de API.

>[!NOTE]
>
>Adobe Campaign Standard también se puede conectar a Microsoft Dynamics 365: esta integración permite la sincronización de todos los datos de contacto disponibles en el sistema CRM, lo que hace que todos los datos de contacto relevantes estén disponibles para las actividades de campaña. Para obtener más información sobre esta integración, consulte [Uso de Campaign y Dynamics 365](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).


<table> 
 <thead> 
  <tr> 
   <th> Solución<br /> </th> 
   <th> Use Case<br /> </th> 
   <th> Consulte <br />. </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Experience Manager<br /> 6.1, 6.2, 6.3, 6.4<br /> </td> 
   <td> Permite crear contenido de correo electrónico o formularios asignados a la base de datos de Adobe Campaign directamente en Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Trabajar con Campaign y Experience Manager</a><br/>, <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">integrar Experience Manager y Campaign Standard</a> <br/>, <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_AEM.html">crear un correo electrónico con Experience Manager y Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Target<br /> Classic, Standard<br /> </td> 
   <td> Allows you to insert images that are dynamically computed by Adobe Target when an email created and sent by Adobe Campaign is opened.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Trabajar con Campaign y Target</a> <br/>, <a href="https://marketing.adobe.com/resources/help/en_US/target/a4t/c_campaign_and_target.html">integrar campaña y objetivo</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">personalizar imágenes de correo electrónico en vídeo en tiempo</a> real (paso 3)
    </td> 
  </tr> 
  <tr> 
   <td> Analytics<br /> Standard, Premium <br /> </td> 
   <td> Permite realizar un seguimiento del éxito de los envíos de correo electrónico directamente en Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Compartir datos de campaña con Analytics</a><br/>, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Compartir KPI para vídeo integrado de informes</a> de campaña (paso 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager y el servicio principal Personas (Profiles &amp; Audiences)<br /> </td> 
   <td> Le permite intercambiar audiencias con las distintas aplicaciones de Adobe Experience Cloud que utilice.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Servicio principal Personas (Profiles &amp; Audiences)</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Servicio principal de recursos y Recursos On Demand<br /> </td> 
   <td> Permite insertar activos de la biblioteca de Adobe Experience Cloud en correos electrónicos y páginas de destino creadas en Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Servicio</a> principal de recursos o Recursos On Demand<br /> </td> 
  </tr> 
  <tr> 
   <td> Puntos de interés (Analytics para móviles)<br /> </td> 
   <td> Permite recopilar datos de puntos de interés de los suscriptores de la aplicación móvil para enviar mensajes de marketing personalizados con Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Envío de mensajes de marketing basados en la ubicación con datos</a> de campañas y puntos de interés (Analytics para móviles)<br /> </td> 
  </tr> 
  <tr> 
   <td> Activadores de Experience Cloud<br /> </td> 
   <td> Le permite enviar correos electrónicos personalizados a sus clientes en Adobe Campaign como reacción a comportamientos específicos que Adobe Analytics rastrea en su sitio web.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Utilizar los activadores de Experience Cloud en Campaign Standard</a><br/>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">Desencadenadores de abandono: casos</a><br/>de uso de campañas, <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Desencadenar mensajes de remercadotecnia en función del vídeo Actividad</a> del sitio (paso 2)
    </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver<br /> </td> 
   <td> Permite editar un contenido de correo electrónico desde Dreamweaver y sincronizarlo con Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">Crear correos electrónicos personalizados con el vídeo de Dreamweaver</a> <br/>, <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">usar la extensión de campaña para Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> Creative SDK<br /> </td> 
   <td> Le permite editar imágenes y utilizar un conjunto completo de funciones con tecnología Adobe Creative SDK para mejorar sus imágenes directamente en el editor de contenido.<br /> </td> 
   <td> <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">Modificación de imágenes con el SDK de Adobe Creative</a><br /> </td> 
  </tr> 
  <tr> 
   <td> SDK de la plataforma de experiencia<br /> </td> 
   <td> Permite la automatización del proceso de activación de la propiedad de la aplicación móvil en Adobe Campaign mediante los SDK de la plataforma de experiencia.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">Configuración de una aplicación móvil mediante los SDK de la plataforma de experiencia</a><br /> </td> 
  </tr> 
 </tbody> 
</table>

