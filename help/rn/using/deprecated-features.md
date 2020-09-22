---
title: Funciones obsoletas y eliminadas de Campaign Standard
description: Esta página lista las funciones de Adobe Campaign Standard que ya no se utilizan y que se han eliminado.
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
source-git-commit: 5203f3b3c520f38d91627df2159a90ab5912e6b6
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 35%

---


# Funciones obsoletas y eliminadas {#deprecated-and-removed-features}

Adobe evalúa constantemente las funciones de sus productos para identificar aquellas que sean antiguas y que deban reemplazarse con alternativas más modernas para mejorar la experiencia de los clientes, intentando garantizar en todo momento la compatibilidad con versiones anteriores.

Para comunicar la inminente eliminación/sustitución de las capacidades del Campaign Standard, se aplican las siguientes reglas:

* Primero, se anuncia que la función quedará obsoleta. Aunque las funciones obsoletas todavía pueden estar disponibles para los usuarios existentes, no se mejorarán ni se documentarán.
* La eliminación completa de la función se producirá en la siguiente versión como muy pronto. En esta página se anuncia la fecha objetivo real de la eliminación.

Este proceso proporciona a los clientes al menos un ciclo de versiones para actualizar su implementación a una nueva versión o a la versión sucesora de la función obsoleta antes de su eliminación real.

>[!NOTE]
>Adobe Campaign Standard releases and new capabilities are listed in the [Release Notes](../../rn/using/release-notes.md).


## Funciones obsoletas {#deprecated-features}

Esta sección lista las funciones y funciones que se han marcado como obsoletas en las últimas versiones de Campaign Standard.

Por lo general, las funciones que se planea eliminar en una versión futura se definen en primer lugar como obsoletas, y se proporciona una función alternativa a ellas. Estas funciones y funcionalidades ya no están disponibles para los nuevos usuarios de Campaign Standard, o no deben usarse para ninguna implementación nueva. También se eliminan de la documentación del producto.

Se aconseja a los clientes que comprueben si utilizan la función o la capacidad en su implementación actual y que cambien su implementación para utilizar la alternativa proporcionada. Consulte la versión de eliminación de destinatarios para planificar las actualizaciones de entornos y proyectos según corresponda.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notificaciones push con SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir de la versión 20.1, el SDK v4 ya no se utiliza. <a href="https://aep-sdks.gitbook.io/docs/version-4-sdk-end-of-support-faq">Más información</a>.</p><br/>
   <p>El SDK <a href="https://aep-sdks.gitbook.io/docs/">de</a> Adobe Experience Platform Mobile (anteriormente denominado v5) admitirá exclusivamente las funciones y funciones de Adobe Experience Cloud que se avecinan.</p></br>
     <p>
     <em>Fecha de eliminación del destinatario: 30 de septiembre de 2020</em></p>
     </td> 
  </tr> 
 </tbody> 
</table>
<table> 
 <thead> 
  <tr> 
   <th> <strong>Solicitudes de privacidad: API de Campaña e interfaz</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>A partir de la versión 19.4 de la Campaña, el uso de la API de Campaña y la interfaz para acceder y eliminar solicitudes está obsoleto. La eliminación del perfil de 2 pasos no estará disponible. Utilice <a href="https://www.adobe.io/apis/experiencecloud/gdpr.html">Adobe Privacy Core Service</a>.</p></br>
   <p>Consulte también Administración <a href="https://helpx.adobe.com/campaign/kb/acs-privacy.html">de privacidad en Campaign Standard</a>.</p>
  <p> 
  <em>Fecha de eliminación objetivo: 2021</em></p>
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
   <td> <p>A partir de la versión 19.0 de la Campaña, el editor de correo electrónico heredado queda obsoleto. Utilice <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html">el nuevo diseñador</a> de correo electrónico para crear y personalizar el contenido del correo electrónico. </p></br>
   <p>Lea <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard/using/designing-content/building-email-content/using-existing-content.html">esta sección</a> para aprender a adaptar las plantillas de correo electrónico al nuevo editor.</p></br>
  <p> 
  <em>Fecha de eliminación objetivo: 2021</em></p>
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
   <td> <p>A partir de la versión 18.7, las unidades geográficas quedan obsoletas. Las unidades orgánicas y geográficas son construcciones idénticas en Campaña. Los usuarios deben utilizar las unidades organizativas solo para crear la jerarquía de permisos de usuario y acceso a datos. <a href="https://helpx.adobe.com/campaign/standard/administration/using/organizational-units.html">Más información</a>. Tenga en cuenta que las nuevas instancias de Campaign Standard, así como las instancias existentes sin crear unidades geográficas, no pueden tener esta capacidad implementada a partir de la versión 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Removed Features {#removed-features}

Esta sección enumera las funciones y capacidades que se han eliminado de Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Puntuación de tendencia con activadores de Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>La Puntuación <b>de tendencia</b> se ha eliminado de Adobe Experience Cloud Triggers. Como consecuencia, esta opción se ha eliminado de Adobe Campaign Standard. Para evitar valores obsoletos de la puntuación de tendencia en los esquemas de Enriquecimiento, recomendamos actualizar esquemas para recuperar los cambios más recientes y volver a publicar los activadores existentes. Para obtener más información, consulte <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html#publishing-trigger-in-campaign"> Publicación de un activador en Campaña </a>.
</p></br>
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
   <td> <p>El SDK de Adobe Creative se ha retirado del mercado. Como consecuencia, la edición de imágenes con tecnología Creative SDK en correos electrónicos de Campaign Standard ya no está disponible a partir de la versión 20.2 de la Campaña.</p></br>
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
   <td> <p>Adobe Campaign y Adobe Experience Cloud han dejado de ofrecer compatibilidad con Microsoft Internet Explorer 11 a partir de la primavera de 2019 y con la versión 19.2 de Campaña. Cambie a Microsoft Edge u otro explorador compatible. <a href="https://docs.adobe.com/content/help/en/campaign-standard/using/administrating/about-configuration-guidelines.html#compatible-browsers">Más información</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
