---
title: Funciones obsoletas y eliminadas Campaign Standard
description: Esta página lista las funciones obsoletas y eliminadas de Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: tm+mt
source-wordcount: '882'
ht-degree: 58%

---

# Funciones obsoletas y eliminadas {#deprecated-and-removed-features}

Adobe evalúa constantemente las funciones de sus productos para identificar aquellas que sean antiguas y que deban reemplazarse con alternativas más modernas para mejorar la experiencia de los clientes, intentando garantizar en todo momento la compatibilidad con versiones anteriores.

Para comunicar la inminente eliminación/sustitución de las funciones de Campaign Standard, se aplican las siguientes reglas:

* Primero, se anuncia que la función quedará obsoleta. Aunque las funciones obsoletas todavía pueden estar disponibles para los usuarios existentes, no se mejorarán ni se documentarán.
* La eliminación completa de la función se producirá en la siguiente versión como muy pronto. En esta página se anuncia la fecha objetivo real de la eliminación.

Este proceso proporciona a los clientes al menos un ciclo de versiones para actualizar su implementación a una nueva versión o a la versión sucesora de la función obsoleta antes de su eliminación real.

>[!NOTE]
>Las versiones de Adobe Campaign Standard y las nuevas funciones se enumeran en las [Notas de la versión](../../rn/using/release-notes.md).


## Funciones obsoletas {#deprecated-features}

Esta sección enumera las funciones y capacidades que se han marcado como obsoletas en las últimas versiones de Campaign Standard.

Por lo general, las funciones que se planea eliminar en una versión futura se definen en primer lugar como obsoletas, y se proporciona una función alternativa a ellas. Estas funciones y funcionalidades ya no están disponibles para los nuevos usuarios de Campaign Standard, o no deben usarse para ninguna implementación nueva. También se eliminan de la documentación del producto.

Se aconseja a los clientes que comprueben si utilizan la función o la capacidad en su implementación actual y que cambien su implementación para utilizar la alternativa proporcionada. Consulte la versión de eliminación objetivo para planificar el entorno y las actualizaciones del proyecto según corresponda.



<table> 
 <thead> 
  <tr> 
   <th> <strong>SDK V4 para aplicaciones móviles</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>La compatibilidad con los SDK de Adobe Experience Platform Mobile versión 4 finalizó el 31 de agosto de 2021. Si todavía utiliza esta versión heredada del SDK en Adobe Campaign Standard, debe actualizar la implementación con el SDK de Adobe Experience Platform <strong>antes del final de junio de 2024</strong>. </p></br>
   <p>Lea <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=es">este artículo</a> para aprender a adaptar la implementación y pasar al SDK de Experience Platform más reciente.</p></br>
   <p><strong>Precaución</strong>: El SDK V4 ya no será compatible con Campaign Standard a partir de finales de junio de 2024.</p>
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
   <td> <p>A partir de la versión 19.0 de la Campaña, el editor de correo electrónico heredado queda obsoleto. Use <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/designing-content-in-adobe-campaign.html?lang=es">Campaign Email Designer</a> para crear y personalizar el contenido de su correo electrónico. </p></br>
   <p>Lea <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/building-email-content/using-existing-content.html?lang=es">esta sección</a> para aprender a adaptar las plantillas de correo electrónico al nuevo editor.</p></br>
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
   <td> <p>A partir de la versión 18.7 de Campaign, las unidades geográficas quedan obsoletas. Las unidades orgánicas y geográficas son construcciones idénticas en Campaña. Los usuarios deben utilizar las unidades organizativas solo para crear la jerarquía de permisos de usuario y acceso a datos. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/users-and-security/organizational-units.html?lang=es#administrating">Más información</a>. Tenga en cuenta que las nuevas instancias de Campaign Standard, así como las instancias existentes sin crear unidades geográficas, no pueden tener esta capacidad implementada a partir de la versión 18.7.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

## Funciones eliminadas {#removed-features}

Esta sección enumera las funciones y capacidades que se han eliminado de Campaign Standard.

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integración con el servicio Audience Destinations</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir de la versión 21.3 de Campaign Standard, la integración con el servicio Audience Destinations queda obsoleta.  Ahora se elimina.</p>
   <p>Para la nueva implementación, ya no puede integrar el servicio Audience Destinations con Adobe Campaign Standard. Sin embargo, puede integrar Campaign y Adobe Experience Platform mediante Fuentes y destinos. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=es">Más información</a>.</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integración con el conector de datos de Adobe Experience Platform</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir de la versión 21.3 del Campaign Standard, la integración con el conector de datos de Adobe Experience Platform queda obsoleta.  Ahora se elimina.</p>
   <p>Para la nueva implementación, ya no puede integrar el Conector de datos de Adobe Experience Platform con Adobe Campaign Standard. Sin embargo, puede integrar Campaign y Adobe Experience Platform mediante Fuentes y destinos. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/aep-sources-destinations/get-started-sources-destinations.html?lang=es">Más información</a>.</p>
     </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Notificaciones push con SDK v4</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir de la versión Campaign 20.1, el SDK v4 queda obsoleto. Ahora se elimina. <a href="https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=es">Más información</a>.</p><br/>
   <p>El <a href="https://developer.adobe.com/client-sdks/documentation/">SDK de Adobe Experience Platform Mobile</a> (anteriormente conocido como v5) ahora admite exclusivamente funciones y funcionalidades de Adobe Experience Cloud.</p>
   <p>Después del 31 de agosto de 2021, los clientes pueden seguir descargando y utilizando los SDK de la versión 4, pero no habrá asistencia técnica del Servicio de atención al cliente ni acceso a los foros.</p>
   <p>Obtenga información sobre cómo migrar del SDK v4 al SDK de Adobe Experience Platform Mobile <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=es">en esta página</a>.</p></br>
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
   <td> <p>A partir de Campaign versión 21.2, el uso de la API y la interfaz de Campaign para las solicitudes de acceso y eliminación quedarán obsoletas. La eliminación del perfil de 2 pasos ya no está disponible. Usar <a href="https://developer.adobe.com/experience-platform-apis/references/privacy-service">Servicio principal de privacidad de Adobe</a>.</p></br>
   <p>Consulte también <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy-requests.html?lang=es">Administración de solicitudes</a>de privacidad.</p>
  </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
 <tr> 
   <th> <strong>Línea de asunto predictiva</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p> A partir de abril de 2021, la capacidad de línea de asunto predictivo quedará fuera de servicio.</p><br/>
   <p>Le sugerimos que aproveche las capacidades de correo electrónico con tecnología de IA para analizar y predecir las tasas abiertas, los tiempos de envío óptimos y la probable reproducción basada en las métricas de participación históricas. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/preparing-and-testing-messages/predictive.html?lang=es">Más información</a></p></br>
     </td> 
  </tr> 
  </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Puntuación de tendencia con activadores de Experience Cloud</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>La Puntuación <b>de tendencia</b> se ha eliminado de Adobe Experience Cloud Triggers. Como consecuencia, esta opción se ha eliminado de Adobe Campaign Standard. Para evitar valores obsoletos de la puntuación de tendencia en los esquemas de Enriquecimiento, recomendamos actualizar esquemas para recuperar los cambios más recientes y volver a publicar los activadores existentes. Para obtener más información, consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/working-with-campaign-and-triggers/using-triggers-in-campaign.html?lang=es"> Publicación de un activador en Campaña </a>.
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
   <td> <p>[!DNL Adobe Creative SDK] se ha retirado del mercado. Como consecuencia, la edición de imágenes con tecnología [!DNL Creative SDK] en correos electrónicos de Campaign Standard ya no está disponible a partir de la versión 20.2 de Campaign.</p></br>
   </td> 
  </tr> 
 </tbody> 
</table>

## Fin de la compatibilidad {#end-of-compatibility}

<table> 
 <thead> 
  <tr> 
   <th> <strong>Microsoft Internet Explorer 11</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Adobe Campaign y Adobe Experience Cloud han dejado de ofrecer compatibilidad con Microsoft Internet Explorer 11 a partir de la primavera de 2019 y con la versión 19.2 de Campaña. Cambie a Microsoft Edge u otro explorador compatible. <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/about-configuration-guidelines.html?lang=es">Más información</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>
