---
title: Notas de la versión anteriores
description: Notas de la versión anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1072'
ht-degree: 100%

---

# Notas de la versión anteriores {#new-release}

Esta página describe las nuevas funciones, mejoras y correcciones incluidas en la próxima versión de Campaign Standard.

>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Obtenga más información en la [página de planificación de versiones](../../rn/using/release-planning.md).

## Versión 21.3: septiembre de 2021 {#release-21-3---sept-2021}

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
* Se ha añadido una comprobación de coherencia al crear índices en recursos personalizados y se han mejorado los mensajes de error.

**Otros cambios**

* El conector de datos de Adobe Experience Platform y el servicio Destinos de audiencia ya no se utilizan en Campaign Standard. Si utiliza estas funciones, debe pasar a Orígenes y destinos de Adobe y adaptar la implementación. [Más información](../../integrating/using/get-started-sources-destinations.md)
* Las funciones obsoletas y eliminadas se enumeran en [esta página](deprecated-features.md).
* Se ha introducido una nueva función de agregado StringAgg para concatenar los valores de una columna de tipo cadena. (CAMP-47077)
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
