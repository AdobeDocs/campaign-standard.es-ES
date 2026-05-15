---
title: Funciones obsoletas y eliminadas Campaign Standard
description: Esta página lista las funciones obsoletas y eliminadas de Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 03797137-c01c-48dc-b25b-8e72741abb04
TQID: https://experienceleague.adobe.com/S430SyqHAam2JE4LQppJUy3xuEdS6lw1qGQE9viVCS8
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
  - id: b631758a-142d-425f-b9aa-f756d85cb979
  - id: b82389f8-9b5e-4083-8e3b-3cef299fb8b9
subfeature_v2:
  - id: c8da4fdd-eb94-4751-a43c-f82733fb2d6e
  - id: cfc95e9b-b035-4403-a6a9-b27a8a053a37
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 1045
ht-degree: 50%

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
   <td> <p>La compatibilidad con los SDK de Adobe Experience Platform Mobile versión 4 finalizó el 31 de agosto de 2021. Si todavía utiliza esta versión heredada de SDK en Adobe Campaign Standard, debe actualizar la implementación con Adobe Experience Platform SDK <strong>antes del final de junio de 2024</strong>. </p></br>
   <p>Lea <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=es">este artículo</a> para aprender a adaptar la implementación y pasar a la última versión de Experience Platform SDK.</p></br>
   <p><strong>Precaución</strong>: SDK V4 ya no será compatible con Campaign Standard a partir de junio de 2024.</p>
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
   <td> <p> A partir de la versión 21.3 de Campaign Standard, la integración con el conector de datos de Adobe Experience Platform queda obsoleta.  Ahora se elimina.</p>
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
   <td> <p> A partir de la versión 20.1 de Campaign, SDK v4 queda obsoleto. Ahora se elimina. <a href="https://experienceleague.adobe.com/docs/discontinued/using/mobile-services.html?lang=es">Más información</a>.</p><br/>
   <p><a href="https://developer.adobe.com/client-sdks/documentation/">Adobe Experience Platform Mobile SDK</a> (anteriormente conocido como v5) ahora solo admite las funciones y funciones de Adobe Experience Cloud que se avecinan.</p>
   <p>Después del 31 de agosto de 2021, los clientes pueden seguir descargando y utilizando los SDK de la versión 4, pero no habrá asistencia técnica del Servicio de atención al cliente ni acceso a los foros.</p>
   <p>Obtenga información sobre cómo migrar de SDK v4 a Adobe Experience Platform Mobile SDK <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/sdkv4-migration.html?lang=es">en esta página</a>.</p></br>
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
