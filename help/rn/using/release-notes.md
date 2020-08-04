---
title: Última versión
description: Esta página muestra todas las versiones recientes de Adobe Campaign Standard.
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
source-git-commit: f45985c030c3d5059bfef444287c10b842298f49
workflow-type: tm+mt
source-wordcount: '1160'
ht-degree: 90%

---


# Última versión{#latest-release}

[Planificación de versiones](../../rn/using/release-planning.md) | [Versiones del Panel de control](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html) | [Actualizaciones de documentación](../../rn/using/documentation-updates.md) | [Notas de la versión anteriores](../../rn/using/release-notes-2020.md) | [Funciones obsoletas](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **Nuevo lanzamiento del Panel de control de Campaign en junio** con monitorización de perfiles activos, auditoría de entregas de subdominios y administración de claves GPG. [Más información](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html).

## Versión 20.3: mayo de 2020 {#release-20-3---may-2020}

**Novedades**

<table> 
<thead> 
<tr> 
<th> <strong>Ley de Protección de Datos Personales de Tailandia (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La Ley de Protección de Datos Personales de Tailandia (PDPA, por sus siglas en inglés) es la nueva ley de privacidad que armoniza y actualiza los requisitos de protección de datos para Tailandia. Esta ley se aplica a los clientes de Adobe Campaign que mantienen datos de sujetos de datos que residen en la UE.</p>
<p>Además de las funciones de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimientos, la configuración de retención de datos y los roles de usuario), aprovechamos esta oportunidad para incluir funciones adicionales que le ayudarán a prepararse para la PDPA:</p>
<ul>
<li>Derecho al acceso y derecho a la eliminación: aprovechamos las funciones añadidas para el RGPD y la CCPA. <a href="https://helpx.adobe.com/content/help/es/campaign/kb/acs-privacy.html#righttoaccess">Más información</a> </li>
<li><p>Al crear una solicitud de privacidad, se ha agregado el tipo de regulación PDPA en el servicio principal de privacidad. Este método es el que debe utilizar para todas las solicitudes de acceso y eliminación. El uso de la API y la interfaz de Campaign para las solicitudes de acceso y eliminación quedará obsoleto.  Consulte el artículo <a href="../../rn/using/deprecated-features.md">Funciones obsoletas y eliminadas</a>.</p></li>
</ul>
<p>Consulte el vídeo de <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/privacy/privacy-overview.translate.html">procedimiento</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Actividad de API externa (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>La actividad de <strong>API externa</strong> está pasando de beta a GA. Esta versión ofrece más flexibilidad al analizador de cuerpos de respuesta JSON. Ahora puede hacer lo siguiente:</p>
<ul>
<li>Analizar un JSON anidado con una profundidad máxima de 10 niveles. </li>
<li>Analizar las propiedades seleccionadas como nodos de hoja de un JSON y acoplarlas en una sola fila de tabla.</li>
<li>Seleccionar y utilizar un objeto de matriz de un JSON sin tener que nombrar al objeto "data" ni tenerlo en el nivel superior.</li>
</ul>
<p><strong>Precaución:</strong> Los clientes deberán <strong>reemplazar todas las actividades de API externas beta</strong> con actividades de API externas de GA en sus flujos de trabajo.  Los flujos de trabajo que utilizan la versión beta de la API externa dejarán de funcionar en la versión 20.3.</p>
<p>Para obtener más información, consulte la <a href="../../automating/using/external-api.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.translate.html">videotutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Funciones** adicionales (a partir del 13 de julio)

* **Optimización de tiempo de envío con tecnología AI y puntuación** de perfiles: ahora puede optimizar el diseño y el envío de los viajes de los clientes para predecir las preferencias de participación de cada individuo. Con Journey AI, el Adobe Campaign puede analizar y predecir las tasas abiertas, los tiempos de envío óptimos y la probable reproducción basada en métricas de participación históricas. [Más información](../../sending/using/predictive.md)
* **La nueva regulación** de privacidad de Brasil - Además de las capacidades de privacidad ya disponibles en Campaña, Adobe le ayuda a facilitar su preparación para el Lei Geral de Proteçao de Datos (LGPD) de Brasil. Al crear una solicitud de privacidad, se ha agregado la normativa LGPD al servicio principal de privacidad de Adobe. [Más información](https://helpx.adobe.com/es/campaign/kb/campaign-privacy-overview.html)

**Mejoras**

* El número de caracteres que se puede utilizar en el campo **Prefijo** para [probar mensajes con perfiles de destino](../../sending/using/testing-messages-using-target.md) se ha aumentado de 32 a 500 caracteres.
* La cantidad máxima de eventos en tiempo real que se puede publicar en una instancia ha aumentado de 350 a 2000. (CAMP-41608)
* La sincronización entre Adobe Launch y Campaign Standard se ha mejorado mediante el flujo de trabajo técnico syncWithLaunch. Este flujo de trabajo permite la importación automática de todas las propiedades móviles de Adobe Launch a Adobe Campaign Standard. Para obtener más información, consulte [esta página](../../administration/using/technical-workflows.md).

   Deberá enviar un ticket al Servicio de atención al cliente de Adobe (directamente o a través de su contacto de Adobe) para que el flujo de trabajo técnico de syncWithLaunch esté habilitado en la instancia de Campaign. (CAMP-40082)

**Mejoras en el diseñador de correo electrónico**

* El diseñador de correo electrónico ahora puede gestionar un formato HTML más flexible que W3C estricto. (CAMP-42529)
* Se ha corregido un problema con las [imágenes en las que se puede hacer clic](../../designing/using/links.md#inserting-a-link) para evitar que se muestren vínculos junto a la imagen en bloques de contenido. (CAMP-41586)
* Se ha corregido un problema que impedía la redirección a una página de aterrizaje cuando la dirección [URL rastreada](../../designing/using/links.md#about-tracked-urls) tenía una categoría añadida en la plantilla. (CAMP-41537)
* Se ha corregido un problema con el relleno de botones en Outlook.
* Se ha corregido un problema que provocaba que las etiquetas HTML aparecieran en texto sin formato.
* La búsqueda de bloques de contenido ahora muestra resultados de búsqueda del servidor, así como resultados precargados. (CAMP-41870)

**Otros cambios**

* La interfaz de publicación de recursos personalizada se ha mejorado con mensajes de error más claros.
* Las asignaciones de envío no utilizadas se han eliminado de la interfaz.
* Se han eliminado funciones de administrador innecesarias de la interfaz.
* Ahora las casillas de verificación pueden ser obligatorias en una página de aterrizaje.
* Al descargar el archivo CSV de un informe dinámico, se ha eliminado el límite de 200 filas. Ahora puede incluir cada fila del informe. (CAMP-40810)
* Se ha añadido el lenguaje ES-US a la lista de idiomas predeterminados para correos electrónicos multilingües. (CAMP-42279)
* Los archivos descargados con una actividad Transferir archivo ahora se eliminarán después de X días, donde X se determina con el campo **Historial en días** en el menú **Ejecución** de las propiedades Flujo de trabajo. [Más información](../../automating/using/managing-execution-options.md)

**Integraciones de Experience Platform**

* Se ha mejorado la activación de audiencias de [Experience Platform](../../automating/using/aep-targeting-audiences.md) de Adobe desde la actividad **Leer audiencia** para proporcionar un mejor rendimiento y estabilidad. Además, los registros de flujo de trabajo se han simplificado para añadir claridad y detallado con respecto a los trabajos de activación, lo que facilita la monitorización y la resolución de problemas al leer audiencias de Adobe Experience Platform.

**Parches**

* Se ha corregido un error que hacía que se creara un recurso fantasma durante el trabajo de publicación de un recurso personalizado.
* Se ha corregido un problema que podía impedir que se mostrara el Historial de marketing de los perfiles si el recurso Perfil se ampliaba con un recurso personalizado. (CAMP-41009)
* Se ha corregido un problema con las plantillas de la página de aterrizaje integradas que mostraban su contenido en francés al abrir el editor. (CAMP-41639)
* Se ha corregido un problema en las notificaciones push con contenido dinámico que podía impedir que se mostraran emojis. (CAMP-40715)
* Se ha corregido un problema con la actividad **Deduplicación** que podía hacer que se asignara un código de segmento incorrecto a una de las transiciones de complemento salientes. (CAMP-41400)
* Se ha corregido un error que impedía que se eliminaran informes programados. (CAMP-41302)
* Se ha corregido un problema que provocaba discrepancias entre el panel de envíos y el informe **Resumen de envíos**. (CAMP-41145)
* Se ha corregido un problema que provocaba un problema de visualización de superposición de caracteres en informes descargados.
* Se ha corregido un problema que impedía que la previsualización de un envío funcionara para la sustitución de pruebas.
* Se ha corregido un error al eliminar campos personalizados de una notificación local en la aplicación.
* Se ha corregido un problema que impedía que la función charIndex funcionara con una actividad **Fin** o **Transferir archivo** en un flujo de trabajo.
* Se ha corregido un problema con flujos de trabajo que se podía producir al usar una actividad de **Enriquecimiento** con dos actividades de entrada, incluidos los recursos de destinatario que tenían un vínculo entre ellos. (CAMP-42133)
* Se ha corregido un problema que podía impedir que se ejecutara un flujo de trabajo al usar funciones desconocidas. (CAMP-41873)
* Se ha corregido un problema con flujos de trabajo que se podía producir al crear audiencias con varias actividades **Guardar audiencia** con transiciones salientes complementarias. (CAMP-39992)
* Se ha corregido un problema que provocaba discrepancias en los datos al utilizar la personalización en correos electrónicos transaccionales. (CAMP-41842)
* Se han corregido problemas que se producían al eliminar campos personalizados en envíos de notificaciones push. (CAMP-37586)
* Se ha corregido un error que impedía a los usuarios realizar cambios en los informes. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **El nuevo Panel de control de Campaign puede lanzarse** con la renovación de certificados para subdominios CNAME. [Más información](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html).
