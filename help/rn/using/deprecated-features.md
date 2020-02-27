---
title: Funciones obsoletas y eliminadas de Campaign Standard
description: Esta página enumera las funciones obsoletas y eliminadas de Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-deprecated-features
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6ffbf03a7eb4fc1b5bfbd523c0c5342d41cfd211

---


# Funciones obsoletas y eliminadas de Campaign Standard {#deprecated-and-removed-features}

Adobe evalúa constantemente las capacidades del producto para identificar las funciones antiguas que deben reemplazarse con alternativas más modernas para mejorar el valor general del cliente, siempre bajo una cuidadosa consideración de la compatibilidad con versiones anteriores.

Para comunicar la inminente eliminación/reemplazo de las capacidades de Campaign Standard, se aplican las siguientes reglas:

* El anuncio de la desaprobación es el primero. Aunque las funciones obsoletas todavía pueden estar disponibles para los usuarios existentes, no se mejorarán ni se documentarán.
* La eliminación de funciones obsoletas se producirá en la siguiente versión como muy pronto. En esta página se anuncia la fecha objetivo real de eliminación.

Este proceso proporciona a los clientes al menos un ciclo de versiones para adaptar su implementación a una nueva versión o sucesor de una capacidad obsoleta, antes de la eliminación real.

>[!NOTE]
>Las versiones de Adobe Campaign Standard y las nuevas funciones se enumeran en las Notas [de la versión](../../rn/using/release-notes.md).


## Funciones obsoletas {#deprecated-features}

Esta sección enumera las funciones y capacidades que se han marcado como obsoletas con las últimas versiones de Campaign Standard. Por lo general, las funciones que se planea eliminar en una versión futura se definen en primer lugar como obsoletas, con una alternativa proporcionada. Estas funciones y capacidades ya no están disponibles para los nuevos clientes de Campaign Standard o no deben usarse para ninguna implementación nueva. También se eliminan de la documentación del producto.

Se aconseja a los clientes que revisen si utilizan la función o la capacidad en su implementación actual y planeen cambiar su implementación para utilizar la alternativa proporcionada.  Consulte la fecha de eliminación del objetivo para planificar el entorno y las actualizaciones del proyecto según corresponda.

<table> 
 <thead> 
  <tr> 
   <th> Versión<br /> </th> 
   <th> Funciones<br /> </th> 
   <th> Sustitución<br /> </th> 
    <th> Fecha de eliminación del objetivo<br /> </th>
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Push Notifications<br /> </td> 
    <td> El SDK <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">de</a> Adobe Experience Platform Mobile (anteriormente conocido como v5) solo admitirá las funciones y funciones de Adobe Experience Cloud que se avecinan próximamente. <br /> </td> 
    <td> 30 de septiembre de 2020<br /> </td> 
  </tr> 
  <tr> 
   <td> 20.1<br /> </td> 
   <td> Creative SDK para Campaign Standard<br /> </td> 
  <td> Adobe Creative SDK se ha retirado del mercado. Como consecuencia, la edición de imágenes con tecnología Creative SDK en correos electrónicos de Campaign Standard ya no se utiliza.<br /> </td>
  <td> Marzo de 2020 - Versión de la campaña 20.2<br /> </td> 
  </tr> 
  <tr> 
   <td> 19.4<br /> </td> 
   <td> Solicitudes de privacidad: API de campaña e interfaz<br /> </td>
    <td> El uso de la API de campaña y la interfaz para acceder y eliminar solicitudes está en desuso. Utilice Privacy Core Service. <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Más información</a>. Consulte también Administración <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">de privacidad en Campaign Standard</a>.<br /> </td>
    <td> Julio de 2020 - Versión de la campaña 20.5<br /> </td> 
  </tr>
  <tr> 
   <td> 19.0<br /> </td> 
   <td> Diseño de correo electrónico: editor de correo electrónico heredado<br /> </td>
    <td> El editor de correo electrónico heredado ya no se utiliza. Utilice el nuevo diseñador de correo electrónico para crear y personalizar el contenido del correo electrónico. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">Más información</a>. Lea <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">esta sección</a> para aprender a adaptar las plantillas de correo electrónico al nuevo editor.<br /> </td>
    <td> Octubre de 2020: versión de Campaign 20.6<br /> </td> 
  </tr>
  <tr> 
   <td> 18.7<br /> </td> 
   <td> Usuarios y seguridad: unidades geográficas<br /> </td>
    <td> Las unidades organizativas y geográficas son construcciones idénticas en Campaign. Los usuarios deben utilizar las unidades organizativas solo para crear la jerarquía de permisos de usuario y acceso a datos. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Más información</a>. Tenga en cuenta que las nuevas instancias de Campaign Standard, así como las instancias existentes sin unidades geográficas creadas, no pueden tener esta capacidad implementada a partir de la versión 18.7.<br /> </td>
    <td> N/D<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Fin de compatibilidad {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> Versión<br /> </th> 
   <th> Funciones<br /> </th> 
   <th> Sustitución<br /> </th> 
 </tr> 
 </thead> 
 <tbody>
<tr> 
   <td> 19.2<br /> </td> 
   <td> Solicitudes de privacidad: API de campaña e interfaz<br /> </td>
    <td> Adobe Campaign y Adobe Experience Cloud han dejado de ofrecer compatibilidad con Microsoft Internet Explorer 11 a partir de la primavera de 2019 y la versión de Campaign 19.2. Cambie a Microsoft Edge u otro explorador compatible.  <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">Más información</a>.<br /> </td>
    <td><br /> </td> 
  </tr>
  </tbody> 
</table>
