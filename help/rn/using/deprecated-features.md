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
source-git-commit: d8ad3801dba50e357c21a7551e897e0e2c5aedc5

---


# Funciones obsoletas y eliminadas {#deprecated-and-removed-features}

Adobe evalúa constantemente las capacidades del producto para identificar las funciones antiguas que deben reemplazarse con alternativas más modernas para mejorar el valor general del cliente, siempre bajo una cuidadosa consideración de la compatibilidad con versiones anteriores.

Para comunicar la inminente eliminación/reemplazo de las capacidades de Campaign Standard, se aplican las siguientes reglas:

* El anuncio de la desaprobación es el primero. Aunque las funciones obsoletas todavía pueden estar disponibles para los usuarios existentes, no se mejorarán ni se documentarán.
* La eliminación de funciones obsoletas se producirá en la siguiente versión como muy pronto. En esta página se anuncia la fecha objetivo real de eliminación.

Este proceso proporciona a los clientes al menos un ciclo de versiones para adaptar su implementación a una nueva versión o sucesor de una capacidad obsoleta, antes de la eliminación real.

>[!NOTE]
>Las versiones de Adobe Campaign Standard y las nuevas funciones se enumeran en las Notas [de la versión](../../rn/using/release-notes.md).


## Funciones obsoletas {#deprecated-features}

Esta sección enumera las funciones y capacidades que se han marcado como obsoletas con las últimas versiones de Campaign Standard.

Por lo general, las funciones que se planea eliminar en una versión futura se definen en primer lugar como obsoletas, con una alternativa proporcionada. Estas funciones y capacidades ya no están disponibles para los nuevos clientes de Campaign Standard o no deben usarse para ninguna implementación nueva. También se eliminan de la documentación del producto.

Se aconseja a los clientes que revisen si utilizan la función o la capacidad en su implementación actual y planeen cambiar su implementación para utilizar la alternativa proporcionada. Consulte la fecha de eliminación del objetivo para planificar el entorno y las actualizaciones del proyecto según corresponda.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notificaciones push con SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir de la versión 20.1, el SDK v4 ya no se utiliza. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Más información</a>.</p><br/>
   <p>El SDK <a href="https://aep-sdks.gitbook.io/docs/">de</a> Adobe Experience Platform Mobile (anteriormente conocido como v5) solo admitirá las funciones y funciones de Adobe Experience Cloud que se avecinan próximamente.</p></br>
     <p>Fecha de eliminación del objetivo: 30 de septiembre de 2020</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Creative SDK para Campaign Standard</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Creative SDK se ha retirado del mercado. Como consecuencia, la edición de imágenes con tecnología Creative SDK en correos electrónicos de Campaign Standard queda obsoleta a partir de la versión 20.1.</p></br>
  <p> Fecha de eliminación del objetivo: Marzo de 2020 - Versión de la campaña 20.2</p>
   </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Solicitudes de privacidad: API de campaña e interfaz</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir de la versión 19.4 de Campaign, el uso de la API de campaña y la interfaz para acceder y eliminar solicitudes está en desuso. La eliminación del perfil de dos pasos no estará disponible. Utilice <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Consulte también Administración <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">de privacidad en Campaign Standard</a>.</p>
  <p> Fecha de eliminación del objetivo: Julio de 2020 - Versión de la campaña 20.5</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Diseño de correo electrónico: editor de correo electrónico heredado</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir de la versión 19.0 de Campaign, el editor de correo electrónico heredado queda obsoleto. Utilice <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">el nuevo diseñador</a> de correo electrónico para crear y personalizar el contenido del correo electrónico. </p></br>
   <p>Lea <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">esta sección</a> para aprender a adaptar las plantillas de correo electrónico al nuevo editor.</p></br>
  <p> Fecha de eliminación del objetivo: Octubre de 2020: versión de Campaign 20.6</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Usuarios y seguridad: unidades geográficas</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir de la versión 18.7, las unidades geográficas quedan obsoletas. Las unidades organizativas y geográficas son construcciones idénticas en Campaign. Los usuarios deben utilizar las unidades organizativas solo para crear la jerarquía de permisos de usuario y acceso a datos. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Más información</a>. Tenga en cuenta que las nuevas instancias de Campaign Standard, así como las instancias existentes sin unidades geográficas creadas, no pueden tener esta capacidad implementada a partir de la versión 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>


## Fin de compatibilidad {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign y Adobe Experience Cloud han dejado de ofrecer compatibilidad con Microsoft Internet Explorer 11 a partir de la primavera de 2019 y la versión de Campaign 19.2. Cambie a Microsoft Edge u otro explorador compatible. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/getting-started/discovering-the-interface/compatible-browsers.html">Más información</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
