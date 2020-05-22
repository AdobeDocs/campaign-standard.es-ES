---
title: Última versión
description: Esta página lista todas las versiones recientes de Adobe Campaign Standard.
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
source-git-commit: e59562bd4f258c4259b8e8e5d9648397d5718792
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 5%

---


# Última versión{#latest-release}

[Planificación de versiones](../../rn/using/release-planning.md) | Versiones [del Panel de control](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html) | Actualizaciones [de documentación](../../rn/using/documentation-updates.md) | Notas de la versión [anteriores](../../rn/using/release-notes-2020.md) | Características [obsoletas](../../rn/using/deprecated-features.md)

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
<td> <p>La Ley de Protección de Datos Personales de Tailandia (PDPA, por sus siglas en inglés) es la nueva ley de privacidad que armoniza y moderniza los requerimientos de protección de datos para Tailandia. Esta regulación se aplica a los clientes de Adobe Campaign que tienen datos para sujetos de datos residentes en este país.</p>
<p>Además de las funciones de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), aprovechamos esta oportunidad para incluir funciones adicionales que le ayudarán a prepararse para el PDPA:</p>
<ul>
<li>Derecho de acceso y derecho de eliminación: estamos aprovechando las capacidades que se agregaron para el RGPD y la CCPA. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Más información</a> </li>
<li><p>Al crear una solicitud de privacidad, se ha agregado el tipo de regulación PDPA en el servicio principal de privacidad. Este método es el que debe utilizar para todas las solicitudes de acceso y eliminación. El uso de la API de Campaña y la interfaz para acceder y eliminar solicitudes está en desuso.  Consulte el artículo <a href="../../rn/using/deprecated-features.md">Funciones</a>obsoletas y eliminadas.</p></li>
</ul>
<p>Consulte el vídeo de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">procedimientos</a>.</p>
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
  <td> <p>La actividad de API <strong></strong> externa está pasando de beta a GA. Esta versión ofrece flexibilidad adicional al analizador de cuerpos de respuesta JSON. Ahora puede:</p>
<ul>
<li>analizar un JSON anidado con una profundidad máxima de 10 niveles. </li>
<li>analizar las propiedades seleccionadas como nodos de hoja de un JSON y acoplarlas en una sola fila de tabla.</li>
<li>seleccione y utilice un objeto de matriz de un JSON sin tener que nombrar al objeto "data" o hacer que esté en el nivel superior.</li>
</ul>
<p><strong>Precaución:</strong> Los clientes deberán <strong>reemplazar todas las actividades</strong> de API externas beta con actividades de API externas de GA en sus flujos de trabajo.  Los Flujos de trabajo que utilizan la versión beta de la API externa dejarán de funcionar en 20.3.</p>
<p>Para obtener más información, consulte la <a href="../../automating/using/external-api.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">videotutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

>[!NOTE]
>
>La renovación de certificados para subdominios CNAME se libera en el Panel de control de Campaña en mayo. Para obtener más información sobre esto, consulte la Nota [de revisión del Panel de](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html)control.

**Mejoras**

* El número de caracteres que se puede utilizar en el campo **Prefijo** para [probar mensajes con perfiles](../../sending/using/testing-messages-using-target.md) de destino se ha aumentado de 32 a 500 caracteres.
* El número máximo de eventos en tiempo real que se pueden publicar en una instancia ha aumentado de 350 a 2000. (CAMP-41608)
* La sincronización entre Adobe Launch y Campaign Standard se ha mejorado mediante el flujo de trabajo técnico syncWithLaunch. Este flujo de trabajo permite la importación automática de todas las propiedades móviles de Adobe Launch en Adobe Campaign Standard. Para obtener más información, consulte [esta página](../../administration/using/technical-workflows.md).

   Deberá enviar un ticket al Servicio de atención al cliente de Adobe (directamente o a través de su contacto de Adobe) para que el flujo de trabajo técnico de syncWithLaunch esté habilitado en la instancia de Campaña. (CAMP-40082)

**Mejoras en el Diseñador de correo electrónico**

* El diseñador de correo electrónico ahora puede gestionar un formato HTML más flexible que W3C estricto. (CAMP-42529)
* Se ha corregido un problema con las imágenes [en las que se](../../designing/using/links.md#inserting-a-link) podía hacer clic para evitar que se mostraran vínculos junto a la imagen en bloques de contenido. (CAMP-41586)
* Se corrigió un problema que impedía la redirección a una página de aterrizaje cuando la dirección URL [](../../designing/using/links.md#about-tracked-urls) rastreada tenía una categoría agregada en la plantilla. (CAMP-41537)
* Se ha corregido un problema con el relleno de botones en Outlook.
* Se ha corregido un problema que provocaba que las etiquetas HTML aparecieran en texto sin formato.
* La búsqueda de bloques de contenido ahora muestra los resultados de búsqueda de servidor, así como los resultados precargados. (CAMP-41870)

**Otros cambios**

* La interfaz de publicación de recursos personalizada se ha mejorado con mensajes de error más claros.
* Las asignaciones de envío no utilizadas se han eliminado de la interfaz.
* Se han eliminado funciones de administrador innecesarias de la interfaz.
* Ahora las casillas de verificación pueden ser obligatorias en una página de aterrizaje.
* Al descargar el archivo CSV de un informe dinámico, se ha eliminado el límite de 200 filas. Ahora puede incluir cada fila del informe. (CAMP-40810)
* Lenguaje ES-US Añadido en la lista de idiomas predeterminados para correos electrónicos multilingües. (CAMP-42279)
* Los archivos descargados con una actividad Transferir archivo ahora se eliminarán después de X días, donde X se determina mediante el campo **Historial en días** del menú **Ejecución** de las propiedades Flujo de trabajo. [Más información](../../automating/using/managing-execution-options.md)

**Integraciones de la plataforma de experiencias**

* Se ha mejorado la Activación de las Audiencias [de la plataforma de](../../automating/using/aep-targeting-audiences.md) experiencias de Adobe desde la actividad de audiencia **de** lectura para proporcionar un mejor rendimiento y estabilidad. Además, los registros de flujo de trabajo se han aclarado y detallado con respecto a los trabajos de activación, lo que facilita la supervisión y la resolución de problemas al leer audiencias de Adobe Experience Platform.

**Parches**

* Se corrigió un error que ocasionaba que se creara un recurso fantasma durante el trabajo de publicación de un recurso personalizado.
* Se ha corregido un problema que podía impedir que se mostrara el Historial de marketing de los perfiles si el recurso de Perfil se extendía con un recurso personalizado. (CAMP-41009)
* Se ha corregido un problema con las plantillas de página de aterrizaje integradas que mostraban su contenido en francés al abrir el editor. (CAMP-41639)
* Se ha corregido un problema en las notificaciones push con contenido dinámico que podía impedir que se mostraran emojis. (CAMP-40715)
* Se ha corregido un problema en la actividad de **Deduplicación** que podía hacer que se asignara un código de segmento incorrecto a una de las transiciones de complemento salientes. (CAMP-41400)
* Se corrigió un error que impedía que se eliminaran los informes programados. (CAMP-41302)
* Se ha corregido un problema que provocaba discrepancias entre el panel de envíos y el informe Resumen **de** Envíos. (CAMP-41145)
* Se ha corregido un problema que provocaba un problema de visualización de superposición de caracteres en los informes descargados.
* Se ha corregido un problema que impedía que la previsualización de un envío funcionara para la sustitución de pruebas.
* Se corrigió un error al eliminar campos personalizados de una notificación local en la aplicación.
* Se ha corregido un problema que impedía que la función charIndex funcionara con una actividad de transferencia **** End **o** File en un flujo de trabajo.
* Se ha corregido un problema en flujos de trabajo que se podía producir al usar una actividad de **Enriquecimiento** con dos actividades de entrada, incluidos los recursos de destinatario que tenían un vínculo entre ellos. (CAMP-42133)
* Se ha corregido un problema que podía impedir que se ejecutara un flujo de trabajo al usar funciones desconocidas. (CAMP-41873)
* Se ha corregido un problema en flujos de trabajo que se podía producir al crear audiencias con varias actividades **Guardar audiencia** con transiciones salientes complementarias. (CAMP-39992)
* Se ha corregido un problema que provocaba discrepancias en los datos al utilizar la personalización en correos electrónicos transaccionales. (CAMP-41842)
* Se han corregido problemas que se producían al eliminar campos personalizados en envíos de notificaciones push. (CAMP-37586)
* Se corrigió un error que impedía a los usuarios realizar cambios en los informes. (CAMP-42505)
