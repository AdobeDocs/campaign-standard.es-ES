---
title: Notas de la versión más recientes de 2020
description: Esta página enumera todas las versiones recientes de Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a6b0dd550dc0f6815cbf25f03fd199f4105de9c3

---


# Última versión{#latest-release}

[Planificación](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) de versiones| [Versiones](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) del Panel de control| Actualizaciones [de documentación](../../rn/using/documentation-updates.md) | Notas de revisión [anteriores](../../rn/using/release-notes-2019.md) | Características [obsoletas](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Versión 20.1.4: febrero de 2020 {#release-20-1-4---february-2020}

* Se ha corregido un problema que se producía al abrir una actividad **Leer audiencia** en flujos de trabajo existentes. (CAMP-41002)

## Versión 20.1.3: febrero de 2020 {#release-20-1-3---february-2020}

* Se ha corregido un problema de regresión introducido en 20.1 por CAMP-39273 para los clientes que utilizan la laguna. Se revirtió el CAMP-39273.

## Versión 20.1.2: febrero de 2020 {#release-20-1-2---february-2020}

**Mejoras en el Diseñador de correo electrónico**

* Se corrigió un problema que agregaba un elemento de etiqueta HTML en un fragmento obsoleto al realizar un parche y, a continuación, guardar el contenido. (CAMP-40685)
* Se ha corregido un problema que agregaba un espacio al usar contenido dinámico. (CAMP-40605)
* Se ha corregido un problema al configurar una plantilla de correo electrónico transaccional. (CAMP-40604)

## Versión 20.1: febrero de 2020 {#release-20-1---february-2020}

**Novedades?**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Conector de datos de la plataforma de Adobe Experience (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>El conector de datos de la plataforma Adobe Experience está ahora integrado con Adobe Campaign Standard. Puede hacer que los datos de campaña estén disponibles en la plataforma de Adobe Experience Platform asignando datos XTK (datos ingestados en Campaign) al Modelo de datos de la plataforma de experiencia de Adobe (XDM). </p>
    <p>Tenga en cuenta que esta capacidad solo está disponible para los clientes alojados en Azure. Para obtener más información sobre esta capacidad y condiciones para activarla, consulte la documentación <a href="../../administration/using/aep-about-data-connector.md"></a> detallada y el vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">de</a>procedimientos.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Destinos de audiencia (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Los destinos de audiencia le permiten compartir segmentos de Adobe Experience Platform con Adobe Campaign.</p>
    <p>Tenga en cuenta que esta capacidad solo está disponible para los clientes alojados en Azure. Para obtener más información sobre esta capacidad y condiciones para activarla, consulte la documentación <a href="../../audiences/using/aep-about-audience-destinations-service.md"></a> detallada y el vídeo <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.html">de</a>procedimientos. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Disponibilidad global del MTA mejorado: los mensajes (incluidos los mensajes transaccionales) ahora son enviados por el MTA mejorado de Adobe Campaign, que proporciona una infraestructura de envío mejorada que permite mejorar la entrega, el rendimiento y la gestión de devoluciones. [Más información](https://helpx.adobe.com/campaign/kb/campaign-enhanced-mta.html)

* Se ha mejorado la administración de zonas horarias. Ahora puede definir una zona horaria [](../../automating/using/building-a-workflow.md) específica para todo un flujo de trabajo. La zona horaria seleccionada se aplicará a todas las actividades del flujo de trabajo. La información sobre la zona horaria configurada para el operador o el servidor ahora se muestra en la interfaz (en registros y después de seleccionar una zona horaria). (CAMP-37672)

* Las API de Campaign Standard ahora permiten realizar paginación al usar tablas grandes, agregando el `_forcePagination=true` parámetro a la dirección URL de la llamada. [Más información](../../api/using/pagination.md)

* El ID de registro de envío (que es un identificador único para cada registro) ya está disponible en los recursos de registros de envío y seguimiento para todas las dimensiones de objetivo. Esto permite identificar los registros de envío o seguimiento al exportar, por ejemplo. [Más información](../../automating/using/exporting-logs.md)

**Mejoras en el Diseñador de correo electrónico**

* Se agregaron instrucciones de texto obligatorias que faltaban al crear una audiencia.
* Se ha corregido un problema al hacer clic en el botón **Cambiar contenido** en el asistente del editor de correo electrónico preexistente.
* Se ha corregido un problema que impedía que los encabezados se alinearan con el contenido del informe Resumen de servicios. (CAMP-38103)
* Se ha corregido un problema que impedía que las variantes de contenido dinámico se eliminaran sin afectar al resto de la línea de asunto. (CAMP-40096)
* Se corrigió un problema con la prueba A/B al usar la variante B en la línea de asunto. (CAMP-40327)
* Se ha corregido un problema que impedía arrastrar y soltar archivos al utilizar la función de importación de HTML de carga. (CAMP-39326)
* Se ha corregido un problema que impedía copiar y pegar texto desde un editor de texto. (CAMP-39028)
* Se ha corregido un problema que impedía que se mostraran las sugerencias de palabra. (CAMP-38970)
* Se ha corregido un problema que impedía a los usuarios guardar fragmentos. (ATU-2447)
* Se ha corregido un problema que impedía que las estructuras dinámicas se duplicaran. (CAMP-38367)
* Se ha corregido un problema que impedía que el contenido dinámico conservara las condiciones cuando se duplicaba. (CAMP-39051)

**Otros cambios**

* El filtro &quot;Entregas con error de preparación&quot; ahora tiene en cuenta la fecha de creación de las entregas en lugar de la fecha de la última modificación.
* La unidad organizativa del grupo de seguridad Administradores ya no se puede cambiar.
* Al crear un perfil, ahora se debe rellenar el campo Unidad organizativa.
* Ahora, un activador de Experience Cloud solo se puede eliminar si se eliminan tanto el evento como la plantilla de transacción vinculados a él.
* Adobe Creative SDK se ha retirado del mercado. Ahora está en desuso en Campaign Standard. Consulte la página Funciones [](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)obsoletas y eliminadas.


**Parches**

* Se ha corregido un problema al realizar una solicitud de eliminación de privacidad que impedía que los datos de usuario se eliminaran en los registros de exclusión. (CAMP-39003)
* Se ha corregido un problema que provocaba problemas de accesibilidad al cambiar el tamaño del texto en un elemento contenedor.
* Se ha corregido un problema que impedía a los usuarios descartar la ventana emergente Calendario que aparece al pasar el ratón por encima en las actividades de marketing.
* Se corrigió un problema en la **[!UICONTROL External API]** actividad que mostraba el **[!UICONTROL Confirm]** botón aunque no se modificaran los datos.
* Se ha corregido un problema al usar una **[!UICONTROL Union]** actividad en consultas con diferentes dimensiones de objetivo. Los datos de transición solo mostraban registros de la dimensión de objetivo del conjunto principal. (CAMP-36831)
* Se ha corregido un problema que podía dar lugar a un error al usar una **[!UICONTROL Reconciliation]** actividad en contextos específicos, por ejemplo, con dos actividades entrantes, una de las cuales era una actividad de exclusión. (CAMP-37490)
* Se han corregido problemas de rendimiento que podían producirse al seleccionar y actualizar perfiles de prueba. (CAMP-37976)
* Se ha corregido un problema que podía mostrar páginas de error al suscribirse o cancelar la suscripción a través de páginas de aterrizaje. (CAMP-37771)
* Se ha corregido un problema que se producía al cargar contenido en formato zip, con archivos PNG referenciados en HTML con su extensión en mayúsculas. (CAMP-37913)
* Se ha corregido un problema que impedía que se enviaran mensajes en la aplicación al agregar un perfil de prueba a la entrega.
* Se corrigió un error con la actividad de flujo de trabajo de API externa que fallaba al vincularse a actividades de enriquecimiento.
* Se ha corregido un problema que podía hacer que el estado de los mensajes SMS se mostrara incorrectamente.
* Se ha corregido un problema con los recursos personalizados que hacía que aparecieran entradas duplicadas en diferentes extremos de API.
* Se ha corregido un problema que impedía que las páginas de aterrizaje estuvieran disponibles después de la publicación. (CAMP-38695)
* Se ha corregido un error que se producía al mostrar datos de una transición de intersección procedentes de dos recursos diferentes. (CAMP-38974)
* Se ha corregido un problema que provocaba que el valor de enumeración de una plantilla de entrega se configurara incorrectamente. (CAMP-38388)
* Se corrigió un error con las entregas masivas por correo electrónico que mostraba el estado de las entregas como Pendiente y el estado Enviado como Finalizado. (CAMP-35355)
* Se ha corregido un error que mostraba el dominio del remitente de forma incorrecta en los informes dinámicos. (CAMP-33123)
* Se ha corregido un problema que provocaba discrepancias en los recuentos de cancelación de suscripciones en los informes dinámicos. (CAMP-39949)
* Se ha corregido un problema que impedía que las direcciones se mostraran en la pantalla de registro de envío al enviar mensajes en la aplicación.
* Se ha corregido un problema que impedía que los registros de envío de SMS se actualizaran con el número correcto de devoluciones. (CAMP-38395)
* Se corrigió un error que permitía que las llamadas posteriores a la suscripción de la aplicación actualizaran los tokens de notificación push. (CAMP-39273)
