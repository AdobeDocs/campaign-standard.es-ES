---
solution: Campaign Standard
product: campaign
title: Notas de la versión anteriores
description: Notas de la versión anteriores
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
hide: true
hidefromtoc: true
translation-type: tm+mt
source-git-commit: 26b401e18629f794ab3c1a836a28369d2f8f9605
workflow-type: tm+mt
source-wordcount: '2599'
ht-degree: 3%

---


# Nueva versión {#new-release}

[Planificación](../../rn/using/release-planning.md)  de la versión| Versiones [ de ](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html) Panel de control de Campaign| Actualizaciones [ ](../../rn/using/documentation-updates.md) de documentación| Notas [ de la versión ](../../rn/using/release-notes.md) más recientes| Funciones  [obsoletas](../../rn/using/deprecated-features.md)

En esta página se describen las nuevas funciones, mejoras y correcciones incluidas en la próxima versión del Campaign Standard.

>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización del entorno de la fase. Obtenga más información en la [página de planificación de la versión](../../rn/using/release-planning.md).


## Versión 21.1: febrero de 2021 {#release-21-1---febuary-2021}

**Novedades**

<table> 
<thead> 
<tr> 
<th> <strong>Servicio de comentarios de correo electrónico</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>El servicio de comentarios de correo electrónico (EFS) es un servicio escalable que mejora la precisión del sistema de informes al capturar los comentarios de correo electrónico directamente desde el MTA mejorado.</p>
<ul>
<li>Se capturan todas las categorías de eventos: Retrasos, Entregados, Para Enviar, Cancelar la suscripción (Vínculo, Lista), Comentarios (quejas de correo no deseado, eventos asincrónicos).</li>
<li>El cálculo de los indicadores enviados/entregados ahora se basa en los comentarios en tiempo real del MTA mejorado para mejorar la precisión y la reactividad.</li>
<li>EFS soluciona el problema de los retrasos en el sistema de informes de devoluciones sincrónicas y quita el 80 % de la carga del proceso en Mail.</li>
</ul>
<p>Esta capacidad se presenta como una <strong>versión beta privada</strong> y estará disponible progresivamente para todos los clientes en futuras versiones.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Mejoras en la integración con Adobe Experience Manager</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Se ha mejorado la integración de campañas con Adobe Experience Manager: ahora puede importar contenido multilingüe más fácilmente desde Adobe Experience Manager. <p>
<p>Adobe Campaign Standard ahora detecta automáticamente las variantes de idioma del contenido de Adobe Experience Manager y permite la importación y creación de variantes masivas, lo que simplifica considerablemente el número de pasos que debe seguir un profesional para crear una campaña multilingüe basada en el contenido de Adobe Experience Manager.</p>
</p>
</td> 
</tr> 
</tbody> 
</table>

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
<li>Ayuda mejorada del usuario: Al incluir el Experience League en el producto, los resultados de la búsqueda también incluyen resultados de foros de la comunidad y más contenido de vídeo, lo que facilita el acceso a más contenido para sacar el máximo partido de la aplicación. También hemos agregado un mecanismo de comentarios en el menú Ayuda, lo que facilita informar sobre problemas o compartir ideas.</li>
<li>Notificaciones mejoradas: la lista desplegable Notificaciones ahora tiene dos fichas: una para sus propias notificaciones de productos y otra para anuncios de productos globales.</li>
</ul>
</td> 
</tr> 
</tbody> 
</table>

**Mejoras**

* **La** integración de Microsoft Dynamics 3655 se ha mejorado con una aplicación de integración de autoservicio dedicada y un proceso de implementación mejorado. [Más información](../../integrating/using/d365-acs-get-started.md)

* Se ha realizado una mejora para facilitar la solución de problemas al encontrar problemas con el **proceso de mensajería transaccional**. Los administradores técnicos de Adobe ahora pueden utilizar el seguimiento en cualquier proceso sin reiniciarlo.

* La lista **Perfiles** ahora le permite buscar registros basados en uno de estos campos: correo electrónico, nombre, apellidos o campos personalizados que se han agregado en el filtrado avanzado al ampliar el recurso de perfil. Esta función también está disponible en las API de Campaign Standard mediante el parámetro filterType.

* Se ha ajustado un parámetro al número de contenedores que ejecutan el proceso de agrupación de bases de datos **Transactional messaging**. Esto permite que la carga se distribuya uniformemente en todos los contenedores utilizados y alcance un rendimiento óptimo.

* Ahora hay una nueva función **GetOption** disponible en actividades que utilizan variables de evento después de llamar a un flujo de trabajo con parámetros externos. Permite devolver el valor de una función especificada.

* Una nueva opción permite al Campaign Standard **comprobar la disponibilidad de la memoria física** en el sistema antes de iniciar un flujo de trabajo. Si la cantidad de memoria es demasiado baja, la ejecución del flujo de trabajo se retrasará hasta que la memoria del sistema alcance este umbral. Esto evita una mayor degradación del rendimiento y mitiga el riesgo de una interrupción del servicio. El flujo de trabajo se reanudará automáticamente una vez que se haya relajado el estrés del servidor.  Si la ejecución del flujo de trabajo se retrasa, intente volver a programar este flujo de trabajo en un momento de menor actividad e inténtelo de nuevo. Tenga en cuenta que esta opción es de solo lectura y no se puede modificar.

**Otros cambios**

* Se ha cambiado un error a una advertencia durante la preparación del mensaje, cuando se alcanza el límite de 100 descargas de contenido por hora móvil. Ahora se muestra una advertencia cuando se alcanza el límite, que permite continuar con el envío.

* Al enriquecer el contenido de un mensaje transaccional, los vínculos ya no se recuperan al recuperar datos de la tabla de Perfil, lo que reduce la latencia durante la preparación del mensaje y evita los datos de perfil vacíos debido a una relación incorrecta definida con la tabla de perfil.

* La configuración técnica de la instancia se ha optimizado para garantizar la estabilidad. (CAMP-45681)

* Se ha mejorado la administración de sesiones para optimizar la memoria. (CAMP-45901, CAMP-46767)

* La actividad **Transferir archivo** ahora genera una variable adicional (filesCount) que contiene el número de archivos cargados o descargados. (CAMP-45842)

* El **conector SMS** ahora puede enviar varios parámetros opcionales con cada mensaje.

* Los usuarios con la función DATAMODEL ahora pueden publicar extensiones de registro de envío. (CAMP-46604)

* Se ha aclarado el mensaje de error que se mostraba al intentar publicar un recurso con un recurso personalizado que ya no existe. (CAMP-46893)

* Se han agregado los siguientes idiomas a la lista **Idioma preferido**: Indonesio - Indonesia (in-id), Inglés - Suecia (en-se), Inglés - Asia Pacífico (en-ap), Inglés - Japón (en-jp), Español - América Latina (es-la). (CAMP-46351)

* El selector de selección de perfiles al probar una página de aterrizaje utilizará ahora el recurso profilBase en lugar de perfil para evitar el tiempo de espera.

* Se ha mejorado el formato de registro de SMPP.

* Se han agregado parámetros opcionales a las funciones cryptString y decryptString JS para que coincidan con las API de Adobe Campaign Classic.

* Se han mejorado los mensajes de advertencia o error en los registros de preparación de envío.

* Se mejoraron los registros de errores al intentar conectarse al servicio Identity Management de Adobe (IMS).

* Ahora puede filtrar aún más las dimensiones de Envío y Campaña mediante la barra de búsqueda de **sistema de informes dinámico**.

* La fecha de validez del mensaje SMS transaccional ahora se puede definir mediante el valor establecido para el parámetro de caducidad en la **API de Mensajes transaccionales**. (CAMP-36600)

* En el sistema de informes dinámico, el **informe integrado de resumen de Envío** mostraba datos incorrectos para la métrica de tasa sin suscribir. Se ha agregado una nueva métrica con el nombre **baja único** para corregir esto. (CAMP-46445)

**Parches**

* Se ha corregido un problema que provocaba que los envíos se ejecutaran muy lentamente debido a ciertos procesos. Esto se debe a unidades incorrectas definidas para varios parámetros (milisegundos en lugar de segundos, por ejemplo).
* Se ha corregido un problema en flujos de trabajo que se podía producir al copiar y pegar una actividad **de Deduplicación** que se había ejecutado una vez y que aprovechaba un recurso temporal. Una vez duplicado, el recurso de la actividad se definía automáticamente en vacío, lo que producía problemas en otras actividades del flujo de trabajo. Una vez pegado, el recurso de la actividad seguirá siendo el mismo para que el error se active lo antes posible en lugar de más tarde en el flujo de trabajo. (CAMP-46903)
* Se corrigió un problema cuando el SDK de Mobile enviaba una solicitud de seguimiento abierta basada en la condición de que deliveryID/MessageID no fuera nulo. Esto resultaría en errores 404 para envíos con seguimiento deshabilitado. Una variable adicional (acsDeliveryTracking) con información sobre el estado de seguimiento del envío ahora se envía en la carga útil. Esta variable puede tener dos valores activados o desactivados según el estado de seguimiento establecido.
* Se ha corregido un problema que impedía que los informes de envío se ejecutaran cuando se mostraban 5000 filas.
* Se ha corregido un problema con la prueba A/B que impedía que el contenido de la variante B se actualizara después de que se hubiera modificado la Plantilla de envíos. (CAMP-45235)
* Se ha corregido un problema que provocaba que el proceso de mensajería Transactional se quedara atascado, evitando que se enviaran mensajes.
* Se corrigió un problema que ocasionaba que fallara la análisis de envío al enviar un mensaje push transaccional usando la dimensión de destinatario de Perfil. Ahora hay disponible una nueva asignación de envíos (mapRtEventAppSubRcp) para los mensajes push transaccionales dirigidos a perfiles. El envío, la exclusión y los registros de seguimiento de estos envíos estarán ahora disponibles en las tablas broadLogAppSubRcp, excludeLogAppSubRcp y trackingLogAppSubRcp.
* Se ha corregido un problema que podía provocar problemas de navegación al hacer clic en un vínculo interno (por ejemplo, al acceder al envío principal desde una pantalla de resumen de prueba).
* Se ha corregido un problema que impedía que se mostraran todas las plantillas de contenido de Experience Manager disponibles al crear un envío. (CAMP-45990)
* Se ha corregido un problema en flujos de trabajo que podía impedir que se mostraran mensajes de error en los registros de envío después de agregar la columna **Motivo** a la ficha de datos adicional. (CAMP-45139)
* Se ha corregido un problema que se podía producir cuando dos llamadas de suscripción de aplicación tenían el mismo ID de Marketing Cloud (&#39;el valor de clave de duplicado infringe el error de restricción única&#39;).
* Se ha corregido un problema que podía provocar problemas de lentitud al arrastrar y soltar actividades en un flujo de trabajo que contenía una gran cantidad de actividades **de Consulta** y **de audiencia de lectura**. (CAMP-44511)
* Se ha corregido un error que podía producirse al final de la preparación del mensaje transaccional, impidiendo que la información de redirección se cargara en los servidores de seguimiento.
* Se ha corregido un problema que podía mostrar mensajes de error al intentar abrir plantillas de importación o trabajos de importación anteriores después de haber personalizado el recurso de flujo de trabajo. (CAMP-46183)
* Se ha corregido un problema que podía impedir que se ejecutara una actividad **Leer audiencia** si estaba configurada con un nombre de audiencia dinámica. (CAMP-46047)
* Se ha corregido un problema que impedía que se mostrara el botón **Exportar lista**
* Se ha corregido un problema que podía provocar un error en el flujo de trabajo **agregados de Sistema de informes**. (CAMP-45979)
* Se ha corregido un problema al crear un recurso personalizado con una clave compuesta personalizada (contenido dinámico de texto/fecha).
* Se ha corregido un problema que podía impedir que se mostraran los datos de transición de consultas. (CAMP-45669)
* Se corrigieron problemas de consumo de memoria relacionados con la publicación de recursos personalizados.
* Se ha corregido un problema que se producía al configurar un envío para enviarlo en una fecha específica. Si el envío se estableció para enviarse inmediatamente después de confirmarse, se produjo un error en la preparación del envío y se tuvo en cuenta la fecha especificada inicialmente. (CAMP-44107)
* Se ha corregido un problema que podía impedir que se abrieran plantillas transaccionales. (CAMP-47181)
* Se ha corregido un problema en el proceso de publicación de mensaje transaccional que podía provocar reglas de tipología y tipologías de duplicado con nombres que superaran el tamaño de cadena permitido. (CAMP-47104)
* Se corrigió un problema en la actividad **API externa** que se producía cuando un parámetro de entrada devolvía un registro que no existía. (CAMP-47023)
* Se ha corregido un problema que podía impedir que el conector SMPP se reconectara.
* Se ha corregido un problema que se producía en la actividad **Transferencia de archivos** al descargar un archivo que contenía un punto en su nombre. Los caracteres que siguen al punto se consideraron como la extensión del archivo. (CAMP-46624)
* Se ha corregido un problema que impedía que se realizara el agrupamiento de bases de datos, lo que provocaba que los mensajes transaccionales quedaran atascados en la cola del enrutador.
* Se corrigió un error que no evitaba que se enviaran los registros de envío cancelados.
* Se ha corregido un problema que podía provocar un error en un flujo de trabajo al usar una actividad **AND-join**. La actividad cambió automáticamente el conjunto Principal a la última transición cableada, incluso si mostraba visualmente la primera transición cableada. (CAMP-46900)
* Se ha corregido un problema que podía hacer que las direcciones que se pusieron en cuarentena correctamente tuvieran su estado configurado incorrectamente en Válido, eliminándolas así de la cuarentena.
* Se ha corregido un problema que podía impedir que se mostraran campos personalizados si contenían caracteres especiales. (CAMP-46805)
* Se ha corregido un problema que podía impedir que se mostrara una vista detallada específica para un perfil. Esto ocurría si el recurso de perfil se había ampliado con campos personalizados con la opción **Añadir una sección de campos personalizados** habilitada.
* Se ha corregido un problema que podía devolver un código de error 500 al enviar eventos transaccionales. (CAMP-46811)
* Se ha corregido un problema que podía impedir que recibiera informes programados por correo electrónico. (CAMP-46891)
* Se ha corregido un problema que se producía al vincular un recurso personalizado al recurso de perfil con un vínculo simple de cardinalidad 1. Al acceder a un perfil con el campo de recurso personalizado vacío, ahora se muestra un mensaje de error en lugar de una lista vacía.
* Se ha corregido un problema que se producía al utilizar la sustitución de perfiles en un flujo de trabajo, en el que la página no podía cargar los perfiles de envío al seleccionar el perfil que se va a reemplazar. (CAMP-46522)
* Se corrigió una regresión en la que el flujo de trabajo técnico **Database Cleanup** intentaba eliminar las tablas de trabajo de envío caducadas, lo que daba como resultado los siguientes errores: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Se corrigió el siguiente error que se producía en algunos casos al usar el filtro personalizado en los recursos personalizados: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Se corrigió un problema en el cual la preparación de la notificación Push tardaba demasiado en completarse. Esto se debía a que faltaba un índice en las tablas de trabajo transitorias.
* Se corrigió un error que se podía producir al utilizar la opción **Dimension para reconciliar** en una actividad **Reconciliación** en un flujo de trabajo si ya se había definido una relación entre un recurso personalizado y un recurso de perfil.
* Se corrigió un problema que se producía al agregar vínculos a través de una actividad **Reconciliación** o **Enriquecimiento**. Los vínculos seleccionados no se mostraban en la transición de salida.
* Se corrigió un problema al usar una actividad **Segmentación** con envíos recurrentes en un flujo de trabajo que hacía que el envío se enviara a la audiencia incorrecta. (CAMP-46275, CAMP-46470)
* Se corrigió un error en el que la publicación de recursos personalizados fallaba al intentar ampliar el recurso de Perfil para crear dimensiones de perfil personalizadas para sistema de informes dinámico. (CAMP-46266)
* Se corrigió un error que se producía al agregar un vínculo a una tabla de importación de archivos. Después de agregar una actividad **Enriquecimiento** a la actividad **Importación de archivos**, el vínculo previamente configurado desapareció. (CAMP-46557)
* Se ha corregido un problema que se producía al utilizar recursos personalizados vinculados a datos de Perfil, en el que el orden de visualización en la pantalla de configuración de detalle se cambiaba al guardar. (CAMP-46312)
* Se ha corregido un problema que podía impedir que se mostraran datos en sistema de informes dinámico debido a envíos basados en una asignación de envío personalizada.
* Se ha corregido un error que podía impedir que se seleccionara una colección con un destinatario de recursos incorrecto en una actividad de consulta de flujo de trabajo.
* Se ha corregido un problema que podía hacer que el proceso de InMail validara las devoluciones en firme de forma incorrecta.
* Se corrigió un error que se producía al abrir una pantalla de perfil debido a un error de vínculo.
* Se ha corregido un problema que podía impedir que se eliminaran datos de RGPD del flujo de trabajo de limpieza.
* Se corrigió un error que se producía cuando la configuración de programación se actualizaba manualmente con el teclado de tipo en los parámetros de programación de envío de correo electrónico.
* Se ha corregido un problema que impedía editar un perfil debido a parámetros incorrectos en la unidad organizativa.
* Se ha corregido un problema que permitía que el campo de extensión Servicio estuviera vacío e imposible de establecer en las propiedades Correo electrónico, incluso si se había establecido en la Plantilla de envíos.
* Se ha corregido un problema que podía provocar que las pruebas tardaran más en procesarse. (CAMP-45048)
* Se ha corregido un problema que podía impedir que se ordenaran columnas en una pantalla de información general de perfil.
* Se ha corregido un problema de generación de miniaturas que podía ocurrir en Azure en las variantes de correo electrónico que contenían caracteres chinos. (CAMP-47152)
* Se corrigió una regresión introducida en 20.4 que podría llevar a tasas abiertas incorrectas para Gmail debido al filtrado de eventos de seguimiento recibidos de cuentas de Gmail. (CAMP-46504)
* Se ha corregido un problema que podía impedir la importación de contenido HTML en una Plantilla de mensaje transaccional. (CAMP-47318)
* Se ha corregido un problema que podía ralentizar la visualización de las representaciones en el informe de procesamiento de correo electrónico. (CAMP-46226)
* Se ha corregido un problema que podía impedir la publicación de recursos personalizados configurados con un elemento de tipo Lista en la definición de pantalla. (CAMP-47217)
* Se ha corregido un problema en el Diseñador de correo electrónico que impedía que los divisores de línea se representaran correctamente en Microsoft Outlook al colocarse en la parte superior del contenido del correo electrónico. (CAMP-46294)
* Se ha corregido un problema que provocaba que la reconciliación de KPI con el flujo de trabajo técnico de Adobe Analytics se quedara atascada. (CAMP-46576)
* Se ha corregido un problema en el Diseñador de correo electrónico que impedía que los fragmentos se mostraran automáticamente en los cuadros de búsqueda al insertar bloques de contenido. (CAMP-44205)
* Se ha corregido un problema en el Diseñador de correo electrónico que provocaba que se mostraran caracteres no deseados en los correos electrónicos enviados al usar emojis en fragmentos. (CAMP-46621)
* Se corrigió la regresión introducida en 20.4 en el Diseñador de correo electrónico que afectaba al componente divisor, lo que daba como resultado alturas de línea adicionales y distorsiones de imagen en el contenido. (CAMP-46663)
* Se corrigió un problema que obligaba a los botones predeterminados a permanecer centrados cuando se enviaba el mensaje a un buzón de Outlook, aunque estos botones estuvieran alineados a la derecha o a la izquierda en el Diseñador de correo electrónico. (CAMP-46466)
* Se ha corregido un problema que impedía que la lista de perfiles de prueba se actualizara al buscar perfiles en la previsualización de Email Designer. (CAMP-45265)
* Se ha corregido un problema que impedía que se mostraran perfiles de prueba personalizados en la lista al buscar perfiles en la previsualización de Email Designer. (CAMP-45589)
* Se ha corregido un problema que hacía que se mostraran fechas que no coincidían correctamente al generar gráficos de tendencias desde el informe de resumen de envíos. (CAMP-45521)
