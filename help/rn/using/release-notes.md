---
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 7066cf1d8454ffdefa29bff5092ba2c3e1bac705
workflow-type: tm+mt
source-wordcount: '1766'
ht-degree: 99%

---


# Última versión{#latest-release}

## Versión 22.1: febrero de 2022 {#feb-2022}

**Novedades**

<table> 
<thead> 
<tr> 
<th> <strong>Actualización de seguridad para las vulnerabilidades de seguridad de Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j ha corregido las vulnerabilidades notificadas en la versión 2.17.1 de Apache log4j. Adobe Campaign Standard utiliza Apache log4j y esta versión incluye el último Apache log4j v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Correcciones de seguridad**

* Nuevo mecanismo de firma de URL para el seguimiento incluido en esta versión. El mecanismo previo se ha deshabilitado para evitar un problema que causaba que algunos vínculos de seguimiento válidos y firmados se bloquearan incorrectamente después de ser modificados por herramientas de seguridad de terceros. (CAMP-48983)

**Mejoras**

* Se ha mejorado el procesamiento de los datos de creación de informes para evitar sobrecargar el sistema. (CAMP-47578)
* Después de enviar los mensajes en la aplicación, puede optar por desactivar la entrega. Esto le permite eliminar su entrega sin perder datos de creación de informes. (CAMP-48469)
* Para evitar cualquier problema, los usuarios ya no pueden utilizar el mismo nombre para una columna de tabla personalizada que el utilizado para la clave principal automática en la base de datos. `"<dataType><resourceName>Id"`. (CAMP-49358)
* Ahora puede monitorizar su entrega y rastrear los registros de trabajos con el nuevo desplegable **Historial de trabajos** del tablero de los mensajes. (CAMP-49840)
* Se ha mejorado la estabilidad y el estado de la base de datos, al reducir las tuplas, cuando se envía un gran número de mensajes a través de todos los canales a lo largo del tiempo. (CAMP-49755, CAMP-49792, CAMP-49849)
* Para garantizar que las conexiones de base de datos se actualicen automáticamente en caso de que se bloquee o reinicie, se han implementado mejoras en el Agente de transferencia de correo de Campaign (MTA). (CAMP-48063)


**Parches**

* Se ha corregido un problema con la opción **Enviar informe ahora** en Informes dinámicos: los trabajos de generación de PDF fallaron con entregas que incluían varias variantes. (CAMP-49120)
* Se ha corregido un problema que impedía a los usuarios actualizar o desvincular contenido de Adobe Experience Manager (AEM) de sus envíos de Adobe Campaign Standard cuando un contenido duplicado en AEM compartía la misma clave (cq:uuid). (CAMP-49161)
* Se ha corregido un error al acceder a una instancia en la que las páginas no se cargaban, no se podían abrir los envíos o no se podía guardar ninguna modificación pendiente. (CAMP-50195)
* Se ha corregido un problema que impedía abrir los criterios de alerta de entrega si el campo **Filtro de entrega** aplicado por este criterio no se ha rellenado. (CAMP-49093)
* Se ha corregido un problema que se producía al editar el botón **Secundario** en entregas en la aplicación que impidieron que se tuvieran en cuenta los cambios. (CAMP-50250)
* Se ha corregido un error en las instancias de japonés que impedía a los usuarios elegir Varias veces al día como **Frecuencia de ejecución** en la actividad del **Planificador**. (CAMP-50247)
* Se ha corregido un problema que se producía al trabajar en una interfaz de usuario japonesa y que mostraba un mensaje de error al seleccionar una hora en una actividad del planificador. (CAMP-49289)
* Se ha corregido un error con los informes de notificaciones push que mostraban notificaciones push descartadas como **Apertura** en lugar de **Impresión**. (CAMP-45980)
* Se ha corregido un problema que podría provocar errores al abrir un informe. (CAMP-49222)
* Se ha corregido un problema que podría provocar que la preparación del correo electrónico falle después de eliminar un vínculo al contenido de AEM. (CAMP-49877)
* Para resolver varios problemas, se ha mejorado el mecanismo de reintentos de envíos, incluido el contenido importado de una dirección URL. [Más información](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Se ha corregido un problema que se producía después de crear un nuevo filtro en un recurso personalizado y, a continuación, utilizarlo como clave de reconciliación en una página de aterrizaje. Si el recurso personalizado se volvió a publicar, el filtro se eliminó de la lista de claves de reconciliación disponibles para la página de aterrizaje. (CAMP-49516)
* Se ha corregido un problema en las páginas de aterrizaje al usar condiciones dinámicas con casillas de verificación. (CAMP-48604)
* Se ha corregido un problema que se producía en una actividad de **Consulta** al usar la condición de filtro En octubre o antes. Al trabajar desde una instancia configurada en una zona horaria europea, el mes seleccionado para filtrar se mostraba en septiembre en lugar de octubre, debido a un problema al convertir la zona horaria. (CAMP-48602)
* Para optimizar la capacidad de envío, Adobe Campaign ahora envía correos electrónicos con codificación de 7 bits en lugar de 8 bits. Esto evita que los relés intermedios invaliden la firma DKIM que podría afectar a la autenticidad de los mensajes. (CAMP-49016)
* Se ha mejorado el rendimiento al duplicar audiencias para evitar cualquier problema al trabajar con audiencias grandes. (CAMP-49639)
* Se ha corregido un problema que podía impedir que un filtro personalizado mostrara los resultados correctos cuando se usaba en una actividad de **Consulta**. (CAMP-49417)
* Se ha corregido un error que mostraba un mensaje de error al intentar utilizar un fragmento en una entrega con una coma en su nombre. El problema se ha resuelto y ahora se pueden usar comas en los nombres de los fragmentos. (CAMP-49216)


## Versión 21.3: septiembre de 2021 {#release-21-3---sept-2021}

A continuación, se enumeran las nuevas funciones, mejoras y correcciones incluidas en la última versión de Campaign Standard.

**Novedades**

<table> 
<thead> 
<tr> 
<th> <strong>Interfaz de Experience Cloud unificada</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Se ha cambiado la barra de encabezado de Adobe Campaign para unificar y mejorar su experiencia en todos los productos y servicios de Experience Cloud. Estos cambios están diseñados para facilitar su vida, incluyendo:</p>
<ul>
<li>Es más fácil cambiar entre las organizaciones o a otra aplicación.</li>
<li>Guía del usuario mejorada: al incluir Experience League en el producto, los resultados de la búsqueda también incluyen resultados de foros de la comunidad y más contenido de vídeo, lo que facilita el acceso a más contenido para sacar el máximo partido de la aplicación. También hemos agregado un mecanismo de comentarios en el menú Ayuda, lo que facilita informar sobre problemas o compartir ideas.</li>
<li>Notificaciones mejoradas: la lista desplegable Notificaciones ahora tiene dos fichas (una para sus propias notificaciones de productos y otra para anuncios de productos globales).</li>
</ul>
<p>Para obtener más información, consulte la <a href="../../start/using/interface-description.md#top-bar">documentación detallada</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Pista de auditoría</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La nueva pista de auditoría captura, en tiempo real, una lista completa de las acciones y los eventos que se producen dentro de Adobe Campaign. Incluye una forma de autoservicio de acceder a un historial de datos para responder preguntas como las siguientes:</p>
<ul>
<li>¿Qué ha pasado con este flujo de trabajo y quién lo actualizó por última vez?</li>
<li>¿Quién hizo los últimos cambios?</li>
<li>¿Cuál era el estado anterior?</li>
</ul>
<p>Adobe Campaign ahora audita las acciones de creación, edición y eliminación para flujos de trabajo, opciones, recursos personalizados. También se realiza un seguimiento de las modificaciones de esos elementos.</p>
<p>Para obtener más información, consulte la <a href="../../administration/using/audit.md">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Modo de diagnóstico del flujo de trabajo</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Ahora puede ejecutar flujos de trabajo de la campaña en modo de diagnóstico. Este modo registra información para solucionar los problemas de ejecución. El plan de ejecución completo se registra si una consulta de flujo de trabajo tarda, de forma predeterminada, más de un minuto.</p>
<p>Para obtener más información, consulte la <a href="../../automating/using/managing-execution-options.md">documentación detallada</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Mejoras de seguridad**

* Se ha mejorado la seguridad para la protección contra los ataques SSRF. (CAMP-47836)
* La lista de usuarios está ahora restringida únicamente a los administradores. (CAMP-47260)
* Las variables de entorno ya no se pueden usar como parte de la expansión de parámetros en una dirección URL. (CAMP-47268)

**Mejoras**

* Al crear una entrega recurrente en un flujo de trabajo, vinculado a un contenido de Adobe Experience Manager, el estado de aprobación del contenido ahora se comprueba antes de enviarla.
* El límite de conexión a la base de datos ahora está alineado con el paquete de Campaign para evitar errores de conexión.
* Una nueva comprobación de coherencia en la publicación de recursos personalizados impide que los usuarios creen índices duplicados, lo que provoca que la publicación falle. Un mensaje de error mejorado pide al usuario que cambie el nombre del índice si es necesario. [Más información](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)

**Otros cambios**

* El conector de datos de Adobe Experience Platform y el servicio Destinos de audiencia ya no se utilizan en Campaign Standard. Si utiliza estas funciones, debe pasar a Orígenes y destinos de Adobe y adaptar la implementación. [Más información](../../integrating/using/get-started-sources-destinations.md)
* Las funciones obsoletas y eliminadas se enumeran en [esta página](deprecated-features.md).
* Se ha introducido una nueva función de agregado StringAgg para concatenar los valores de una columna de tipo cadena. (CAMP-47077) [Más información](../../automating/using/list-of-functions.md#aggregates)
* El flujo de trabajo técnico **Actualizar indicadores de entrega** (updateDeliveryIndicators) se ha mejorado para optimizar el rendimiento.
* Las plantillas de mensajería en la aplicación ya están disponibles para todos los idiomas compatibles con Campaign Standard.
* El tiempo de preparación de la entrega se ha optimizado para los mensajes transaccionales reduciendo el número de llamadas al servidor de seguimiento durante el análisis de la entrega.
* Un nuevo mensaje de alerta informa a los usuarios de una tasa de salida hacia otro sitio alta.
* Se han mejorado los mensajes y advertencias de error de registro para facilitar la depuración cuando no se recuperaban correctamente los registros de seguimiento. (CAMP-48939, CAMP-47360)
* Ahora puede personalizar completamente las direcciones URL, incluido el nombre de dominio. [Obtenga más información](../../designing/using/personalization.md#personalizing-urls)

**Parches**

* Se ha corregido un error de tiempo de espera al importar contenido de correo electrónico desde una dirección URL. (CAMP-49054)
* Se ha corregido un error (-69) que se producía al finalizar la sesión, al acceder a una dirección URL con marcador o al actualizar una página desde el explorador. (CAMP-49003, CAMP-48930, CAMP-48894)
* Se ha corregido un problema que se producía al sincronizar reglas desde el servidor de capacidad de entrega heredado al nuevo. (CAMP-48923)
* Se ha corregido un problema que se producía al cargar una plantilla de correo electrónico con etiquetas HTML en el Diseñador de correo electrónico. (CAMP-48243)
* Se ha corregido un error por el que el contenido de Adobe Experience Manager no se cargaba al crear mensajes transaccionales con el Diseñador de correo electrónico. (CAMP-49075)
* Se ha corregido un problema en la interfaz por el cual se añadía demasiado margen entre la barra superior y el contenido.
* Se ha corregido un problema con los mensajes transaccionales que podía provocar un error de publicación al utilizar bloques de contenido de Campaign en contenido de Adobe Experience Manager. (CAMP-49233)
* Se ha corregido un problema que podía provocar un mensaje de error cuando fallaba la autenticación. Ahora se redirige al usuario a la página de inicio de sesión.
* Se ha corregido un problema de visualización de tokens que podía impedir que los usuarios editaran o compartieran un informe.
* Se ha corregido un problema durante la publicación de un recurso personalizado mediante una expresión de filtro con relaciones de tabla 1-n. (CAMP-48740)
* Se ha corregido un problema de formato de fecha que impedía que las fechas de contacto de la entrega se recuperaran en transiciones de flujo de trabajo. (CAMP-48871)
* Se ha corregido un problema que impedía la extensión de registros de envío durante la creación de una dimensión de perfil personalizada.
* Se ha corregido un problema que podría provocar errores en los envíos con variantes de múltiples idiomas. A partir de ahora, si un usuario elimina la variante de idioma predeterminada, se debe configurar otra como predeterminada antes de crear copias de idiomas. (CAMP-48235)
* Se ha corregido un problema que hacía que los mensajes de correo electrónico mostraran espacios en blanco adicionales en Outlook si el usuario había seleccionado la opción **Mostrar solo en dispositivos móviles** al diseñar el mensaje. (CAMP-48902)
* Se ha corregido un problema que hacía que la última fecha de ejecución del campo de actividad de consulta incremental no apareciera en la pestaña **Datos procesados** después de ejecutar el flujo de trabajo de consulta incremental. (CAMP-48879)
* Se ha corregido un problema que impedía definir correctamente un código de segmento dinámico en la actividad de flujo de trabajo **Segmentación**. (CAMP-48727)
* Se ha corregido un error que se producía aleatoriamente al intentar guardar un flujo de trabajo después de editarlo. (CAMP-48695)
* Se ha corregido un problema que impedía publicar recursos personalizados, ya que el esquema de datos de un activador permanecía allí incluso después de su eliminación. (CAMP-48523)
* Se ha corregido un problema que impedía que se aceptaran las solicitudes del bucle de comentarios, ya que el proceso de InMail no podía recuperar los registros de envío para actualizar. (CAMP-48705)
* Se ha corregido un problema que impedía definir correctamente las opciones de exclusión en la actividad de flujo de trabajo **Exclusión**.(CAMP-48355)
* Se ha corregido un problema que se producía cuando las actividades de enriquecimiento en flujos de trabajo implicaban suscripciones o cancelaciones de suscripción de un servicio. Este problema provocaba un bloqueo.
* Se ha corregido un problema que podía impedir que se ejecutaran flujos de trabajo.
* Se ha corregido un problema que podía impedir que los usuarios cambiaran el nombre de los grupos de seguridad predeterminados o los eliminaran de la interfaz de usuario.
* Se ha corregido un problema que podía impedir que los usuarios eliminaran un trabajo de publicación de eventos incompleto.
* Se ha corregido un problema por el cual el flujo de trabajo de limpieza de la base de datos fallaba con un error. (CAMP-49097)
