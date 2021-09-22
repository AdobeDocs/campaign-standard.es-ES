---
title: Introducción a las integraciones de Campaign
description: Utilice otras soluciones de Adobe y combine sus diferentes capacidades con Campaign.
audience: integrating
content-type: reference
topic-tags: get-started-campaign-integrations
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: ecf88c7d-6729-4b3a-85c4-60427bb57442
source-git-commit: affd4f9716235a283df20de5539e43c4832762f7
workflow-type: tm+mt
source-wordcount: '711'
ht-degree: 83%

---

# Acerca de las integraciones de Campaign{#get-started-campaign-integrations}

Esta sección detalla las integraciones funcionales disponibles entre la versión actual de Adobe Campaign y otras soluciones y servicios.

Las diferentes integraciones presentadas a continuación le permiten combinar las funcionalidades de entrega y avanzadas de administración de campaña de Adobe Campaign con un conjunto de soluciones creadas para personalizar la experiencia del usuario.

>[!NOTE]
>
> De forma predeterminada, Adobe Campaign ya está vinculado a una cuenta de Adobe Experience Cloud.

Según el entorno, otras soluciones también se pueden vincular con Adobe Experience Cloud. Están vinculadas como Organizaciones (también llamados Inquilinos).

Una organización es la entidad que permite a un administrador configurar grupos y usuarios y controlar el inicio de sesión único en Experience Cloud. La organización funciona como una empresa de inicio de sesión que abarca todos los productos y soluciones de Experience Cloud. Generalmente, la organización es el nombre de la empresa. Sin embargo, una empresa puede tener muchas organizaciones. La administración de usuarios y organizaciones se detalla en el [portal de ayuda de Adobe Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html?lang=es).

Si desea integrar flujos de datos de otros sistemas con Adobe Campaign, consulte nuestra [documentación de API](../../api/using/get-started-apis.md).

>[!NOTE]
>
>Adobe Campaign Standard también puede conectarse a Microsoft Dynamics 365. Esta integración permite la sincronización de todos los datos de contacto disponibles en el sistema CRM, haciendo que todos los datos de contacto relevantes estén disponibles para las actividades de campaña. Para obtener más información sobre esta integración, consulte [Trabajo con Campaign y Dynamics 365](../../integrating/using/d365-acs-get-started.md).


<table> 
 <thead> 
  <tr> 
   <th> Solución<br /> </th> 
   <th> Ejemplo de uso<br /> </th> 
   <th> Consulte<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Adobe Experience Manager<br /> </td> 
   <td> Permite crear contenido de correo electrónico o formularios asignados a la base de datos de Adobe Campaign directamente en Adobe Experience Manager.<br /> </td> 
   <td> 
     <a href="../../integrating/using/integrating-with-experience-manager.md">Trabaje con Campaign y el Experience Manager</a>,  <a href="https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/campaignstandard.html">integre el Experience Manager y el Campaign Standard</a> y  <a href="https://experienceleague.adobe.com/docs/experience-manager-65/administering/integration/campaignstandard.html">cree un correo electrónico con el Experience Manager y Campaign</a> 
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Target<br /> </td> 
   <td> Permite insertar imágenes que Adobe Target calcula dinámicamente cuando se abre un correo electrónico que Adobe Campaign crea y envía.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-target-integration.md">Trabajar con Campaign y Target</a>,  <a href="https://experienceleague.adobe.com/docs/target/using/integrate/campaign-and-target.html?lang=es">integrar Campaign y Target</a>,  <a href="https://helpx.adobe.com/es/marketing-cloud/how-to/email-marketing.html">personalizar imágenes de correo electrónico en vídeo en tiempo </a> real (paso 3)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Analytics<br /> </td> 
   <td> Le permite realizar un seguimiento del éxito de sus envíos de correo electrónico directamente en Adobe Analytics.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-campaign-analytics-integration.md">Compartir datos de Campaign con Analytics</a>, vídeo <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">Compartir KPI para el sistema de informes de Campaign integrado</a> (paso 1)
    </td> 
  </tr> 
  <tr> 
   <td> Adobe Audience Manager y Servicio principal People (Perfiles y audiencias)<br /> </td> 
   <td> Le permite intercambiar audiencias con las distintas aplicaciones de Adobe Experience Cloud que utiliza.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">Servicio principal People (Perfiles y audiencias)</a><br /> </td> 
  </tr> 
   <tr> 
   <td> Plataforma de datos de clientes en tiempo real de Adobe (RTCDP)<br /> </td> 
   <td> La integración entre Adobe Campaign y la plataforma de datos del cliente en tiempo real de Adobe (RTCDP) le permite compartir datos de segmentos e importar audiencias a Adobe Campaign.</td>
   <td><a href="../../integrating/using/get-started-sources-destinations.md">Introducción a orígenes y destinos</a></td>
  </tr> 
  <tr> 
   <td> Servicio principal de recursos de Adobe y Recursos On Demand<br /> </td> 
   <td> Permite insertar activos de la biblioteca de Adobe Experience Cloud en correos electrónicos y páginas de destino creadas en Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">Servicio principal de recursos</a> o Recursos bajo demanda<br /> </td> 
  </tr> 
  <tr> 
   <td> Puntos de interés (Analytics para dispositivos móviles)<br /> </td> 
   <td> Permite recopilar datos de puntos de interés de las aplicaciones móviles de los suscriptores para enviar mensajes de marketing personalizados con Adobe Campaign.<br /> </td> 
   <td> <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">Envío de mensajes de marketing según la ubicación con datos</a> de Campaign y puntos de interés (Analytics para dispositivos móviles)<br /> </td> 
  </tr> 
  <tr> 
   <td> Activadores de Adobe Experience Cloud<br /> </td> 
   <td> Le permite enviar correos electrónicos personalizados a sus clientes en Adobe Campaign como reacción a los comportamientos específicos que Adobe Analytics rastrea en su sitio web.<br /> </td> 
   <td> 
    <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">Utilización de los activadores de Experience Cloud en Campaign Standard</a>, <a href="../../integrating/using/abandonment-triggers-use-cases.md">Ejemplos de uso de los activadores de abandono</a>, y vídeo de <a href="https://helpx.adobe.com/marketing-cloud/how-to/email-marketing.html">mensajes de remarketing del activador basados en la Actividad del sitio</a> (paso 2)
    </td> 
  </tr> 
    <tr> 
   <td> Journey Orchestration de Adobe<br /> </td> 
   <td> Permite enviar correos electrónicos, notificaciones push y SMS utilizando las funciones de mensajería transaccional de Adobe Campaign Standard en el contexto del Journey Orchestration de Adobes, a través de una acción predeterminada.<br /> </td> 
   <td> <a href="https://experienceleague.adobe.com/docs/journeys/using/action-journeys/working-with-adobe-campaign.html?lang=en">Uso de Adobe Journey Orchestration y Adobe Campaign Standard</a><br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Dreamweaver<br /> </td> 
   <td> Permite editar un contenido de correo electrónico de Dreamweaver y sincronizarlo con Adobe Campaign.<br /> </td> 
   <td> 
    <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=es">Creación de correos electrónicos personalizados con </a> Dreamweavervideo,  <a href="https://helpx.adobe.com/es/dreamweaver/using/working-with-dreamweaver-and-campaign.html">uso de la extensión de Campaign para Dreamweaver</a> 
  </td> 
  </tr> 
  <tr> 
   <td> SDK de Adobe Experience Platform<br /> </td> 
   <td> Permite la automatización del proceso de activación de la Propiedad de la aplicación móvil en Adobe Campaign mediante los SDK de Experience Platform.<br /> </td> 
   <td> <a href="https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html">Configuración de una aplicación móvil mediante los SDK de Experience Platform</a><br /> </td> 
  </tr> 
 </tbody> 
</table>
