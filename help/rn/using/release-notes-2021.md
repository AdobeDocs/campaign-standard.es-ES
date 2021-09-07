---
solution: Campaign Standard
product: campaign
title: Notas de la versión 2021
description: Esta página enumera todas las versiones de 2021 de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: b6cf7152-2200-43d7-8d0a-d65752bb2c9b
source-git-commit: a723d0c2b67d2a0d54a1bc2f89a16481da96f606
workflow-type: tm+mt
source-wordcount: '3509'
ht-degree: 100%

---

# Notas de la versión 2021{#release-notes-2021}

[Planificación de versiones](../../rn/using/release-planning.md) | [Versiones del Panel de control](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es) | [Actualizaciones de documentación](../../rn/using/documentation-updates.md) | [Notas de la versión anteriores](../../rn/using/release-notes-2020.md) | [Funciones obsoletas](../../rn/using/deprecated-features.md)

## Versión 21.2: junio de 2021 {#release-21-2---june-2021}

A continuación, se enumeran las nuevas funciones, mejoras y correcciones incluidas en esta versión de Campaign Standard. A continuación, se enumeran las nuevas funciones, mejoras y correcciones incluidas en esta versión de Campaign Standard.

**Mejoras**

* Al diseñar una página de destino, ahora puede añadir una casilla de verificación obligatoria que los perfiles deben seleccionar antes de enviar el formulario. Para obtener más información, consulte la [documentación detallada](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Para la integración de activadores, se ha mejorado el mensaje de error que se muestra cuando no hay datos de reconciliación en la carga útil del activador: Faltan datos de alias en la carga útil.

* Se ha mejorado el rendimiento para recuperar notificaciones push de la cola.

**Otros cambios**

* El mecanismo de firma de URL para el seguimiento de vínculos se ha deshabilitado para evitar un problema que causaba que algunos vínculos de seguimiento válidos y firmados se bloquearan incorrectamente después de ser modificados por herramientas de seguridad de terceros.

* En las entregas de múltiples variantes, los usuarios ya no pueden crear copias de idioma si se ha eliminado la variante predeterminada. Ahora se muestra un mensaje durante la creación de la copia de idioma. (CAMP-48235)

* El proceso de eliminación de perfiles en dos pasos (obsoleto a partir de la versión 19.4 de Campaign) ahora está desactivado de forma predeterminada. Antes, debía deshabilitarse manualmente desde la interfaz de Campaign antes de utilizar el servicio principal de privacidad. Si no se hacía, las solicitudes de eliminación permanecían en estado pendiente sin completarse.

* En los informes dinámicos, se ha eliminado el segmento **Excluir prueba**. (CAMP-46161)

* Se ha añadido un nuevo mensaje de advertencia para informar al usuario cuando se carga un certificado iOS sin el valor platformPrincipal en la aplicación Campaign.

* El tamaño máximo de un correo electrónico ahora es 100 MB de forma predeterminada. Este límite permite evitar cualquier error que pueda aumentar indefinidamente el tamaño de un correo electrónico, lo que puede bloquear el sistema. (CAMP-47445) [Más información](../../sending/using/design-and-personalize.md#email-size)

* Los usuarios estándar ahora pueden usar la integración del servicio principal Asset con el diseñador de correo electrónico.

* Se ha añadido un nuevo mensaje para confirmar que la migración de una aplicación push v4 a una aplicación push v5 se ha realizado correctamente.

* Durante la creación de tokens JSONWeb para autenticarse en la API de Campaign Standard, los perfiles de producto ahora se **consideran**. Esto significa que las unidades organizativas y las funciones asignadas al grupo de seguridad (que coincide con el perfil del producto en AdobeIO) se aplicarán a la cuenta técnica de IMS necesaria para las llamadas a la API Rest de Campaign Standard. (CAMP-47479)

**Parches**

* Se ha corregido un problema que impedía que se aplicara la opción de caducidad de la tabla de registro de procesos por lotes (**xtkjoblog**). Esto impedía que la tabla se purgara correctamente.

* Se ha corregido un problema que impedía cambiar el orden de los filtros en una actividad de flujo de trabajo de **Segmentación**. (CAMP-48357)

* Se ha corregido una regresión de la versión 20.4 que podía provocar que los envíos dieran un error de valor nulo. (CAMP-48591)

* Se ha corregido un problema que impedía enviar un informe a través del menú **Compartir** > **Enviar informe ahora** o **Enviar informe programado**. (CAMP-47798)

* Se ha corregido una regresión que podría llevar a tasas abiertas incorrectas para Gmail debido al filtrado de eventos de seguimiento recibidos de cuentas de Gmail. (CAMP-46504)

* Se han corregido varios problemas que provocaban discrepancias de datos entre informes en Adobe Campaign Standard e informes en Adobe Analytics. (CAMP-47671, CAMP-47296)

* Se ha corregido un problema que impedía acceder a los registros de envío después de que la preparación hubiera fallado. (CAMP-48296)

* Se ha corregido un problema que podía mostrar un mensaje de error al intentar editar, eliminar o enviar un informe personalizado. (CAMP-47789, CAMP-47798)

* Se ha corregido un problema que provocaba que las llamadas de API fallaran al crear un nuevo recurso personalizado y habilitar la opción **No sincronizar**. (CAMP-48014)

* Se ha corregido un problema por el cual los recursos personalizados con la opción **No sincronizar** habilitada podían hacer referencia a un esquema que se había vuelto a redactar o eliminado. Este problema provocaba un error al publicar los recursos personalizados.

* Se ha corregido un problema de exclusión de SMS al usar varios códigos cortos en la misma cuenta externa.

* Se ha corregido un problema que impedía acceder a un nuevo criterio de alerta de entrega (“el recurso al que está intentando acceder no está disponible”) después de publicar la base de datos. (CAMP-48221)

* Se ha corregido un problema por el que faltaban registros de seguimiento en algunas instancias de Campaign con informes dinámicos. Se ha añadido un nuevo [flujo de trabajo técnico](../../administration/using/technical-workflows.md) para restaurar estos registros de seguimiento. (CAMP-47885)

* Se ha corregido un problema por el cual no se mostraban datos de entrega en los informes dinámicos. Los informes estaban en 0. (CAMP-47480)

* Se ha corregido un problema que impedía que el cliente HTTP de JavaScript del servidor se conectara a una dirección URL externa.

* Se ha corregido un problema que restablecía una actividad de **Consulta incremental** después de cambiar el nombre interno del flujo de trabajo. Esto ocurría cuando se utilizaba un campo de fecha como modo incremental. (CAMP-47674)

* Se ha corregido un problema que impedía que la previsualización de la miniatura se mostrara en el resumen de la entrega al crear un correo electrónico multilingüe con la integración de Adobe Experience Manager. Este problema se producía al utilizar el botón **Creación de copia de idioma** para crear las variantes de correo electrónico. (CAMP-47810)

* Se ha corregido un problema que impedía a los usuarios acceder a la entrega principal desde la entrega secundaria de correo electrónico o SMS. (CAMP-47986)

* Se ha corregido un problema que podía provocar un exceso de consumo de CPU y memoria al enviar mensajes transaccionales a través de la API REST con un evento personalizado que faltaba. (CAMP-47147)

* Se ha corregido un error con la API de mensajería transaccional que, a veces, impedía que se enviaran mensajes en tiempo real.

* Se ha corregido un problema por el cual los informes no se recibían después de usar la opción **Enviar informe programado**. (CAMP-48583, CAMP-47786)

* Se ha corregido un problema por el cual los informes recibidos después de utilizar la opción **Enviar informe ahora** estaban incompletos y faltaban datos. (CAMP-48583)

* Se ha corregido un problema con el Diseñador de correo electrónico por el cual las dimensiones de una imagen se reducían al cargarla. (CAMP-47017)

* Se ha corregido un problema que impedía que se mostraran todas las plantillas de Experience Manager disponibles al crear una entrega. (CAMP-48132)

* Se ha corregido un error que impedía que el vínculo de Campaign de la página Resumen de una entrega enviada redirigiera a los usuarios a la campaña relacionada. (CAMP-48012)

* Se ha corregido un problema en el Diseñador de correo electrónico por el que la integración del servicio principal Asset seguía dando error al intentar seleccionar un recurso. (CAMP-47446)

* Se ha corregido un problema que bloqueaba algunos envíos de Journey Orchestration debido a que Campaign no admitía las marcas de hora con un valor exacto (es decir, que terminaran en 00) enviadas por eventos de Journey Orchestration.

## Versión 21.1: febrero de 2021 {#release-21-1---february-2021}

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
<p>El servicio de comentarios de correo electrónico (EFS) es un servicio escalable que captura los comentarios del MTA mejorado directamente, lo que mejora la precisión de la creación de informes. Esta capacidad se presenta como una versión beta privada y estará disponible de forma progresiva para todos los clientes en futuras versiones.</p>
<ul>
<li>Ahora se capturan todas las categorías de comentarios para obtener una creación de informes completa y precisa.</li>
<li>El cálculo del indicador <b>Entregado</b> ahora se basa en los comentarios en tiempo real del MTA mejorado para mejorar la precisión y la reactividad.</li>
<li>EFS soluciona el problema de los retrasos con la creación de informes de devoluciones en blanco sincrónicas.</li>
</ul>
<p>Para obtener más información, consulte la <a href="../../sending/using/confirming-the-send.md">documentación detallada</a>.
</p>
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
<p>Para obtener más información, consulte la <a href="../../integrating/using/creating-multilingual-email-aem.md">documentación detallada</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<!--
<table> 
<thead> 
<tr> 
<th> <strong>Unified Experience Cloud interface</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Adobe Campaign header bar has been changed to unify and improve your experience across all Experience Cloud products and services. These changes are designed to make your life easier, including:</p>
<ul>
<li>Easier switching between your organizations or to a different application.</li>
<li>Improved User Help – Bringing the Experience League into the product, search results also include results from community forums and more video content, giving you easier access to more content to help get the most out of the application. We've also added a feedback mechanism right in the Help menu, making it easier to report issues or share your ideas.</li>
<li>Improved Notifications – Notifications drop-down now has two tabs: one for your own product notifications, and one for more global product announcements.</li>
</ul>
<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>
<p>NOTE: This change will be progressively rolled out to all customer environments between Feb 10 and March 1st.
</p>
</td> 
</tr> 
</tbody> 
</table>
-->

**Mejoras**

* **La integración de Microsoft Dynamics 365** se ha mejorado con una aplicación de integración de autoservicio dedicada y un proceso de implementación mejorado. [Obtenga más información](../../integrating/using/d365-acs-get-started.md)

* Se ha realizado una mejora para facilitar la resolución de problemas al encontrar problemas con el proceso de mensajería transaccional. Los administradores técnicos de Adobe ahora pueden utilizar el seguimiento en cualquier proceso sin reiniciarlo.

* La lista **Perfiles** ahora le permite buscar registros basados en uno de estos campos: correo electrónico, nombre, apellidos o campos personalizados que se han agregado en el filtrado avanzado al ampliar el recurso de perfil. Esta función también está disponible en las API de Campaign Standard mediante el parámetro filterType. [Obtenga más información](../../audiences/using/integrated-customer-profile.md)

* Se ha ajustado un parámetro al número de contenedores que ejecutan el proceso de agrupación de bases de datos de mensajería transaccionales. Esto permite que la carga se distribuya uniformemente en todos los contenedores utilizados y alcance un rendimiento óptimo.

* Ahora hay una nueva función **GetOption** disponible en actividades que utilizan variables de evento después de llamar a un flujo de trabajo con parámetros externos. Permite devolver el valor de una función especificada. [Obtenga más información](../../automating/using/customizing-workflow-external-parameters.md)

* Una nueva opción permite a Campaign Standard **comprobar la disponibilidad de la memoria física** en el sistema antes de iniciar un flujo de trabajo. Si la cantidad de memoria es demasiado baja, la ejecución del flujo de trabajo se retrasará hasta que la memoria del sistema alcance este umbral. Esto evita una mayor degradación del rendimiento y mitiga el riesgo de una interrupción del servicio. El flujo de trabajo se reanudará automáticamente una vez que la carga en el servidor se haya reducido y la memoria aumente. Tenga en cuenta que esta opción es de solo lectura y no se puede modificar. [Obtenga más información](../../automating/using/best-practices-workflows.md#execution)

* Hay un nuevo proceso disponible en Adobe Campaign Standard que le permite migrar más fácilmente desde la aplicación móvil heredada SDK v4 a **SDK para móviles de Adobe Experience Platform**. Consulte [esta página](../../administration/using/sdkv4-migration.md).

**Otros cambios**

* Se ha cambiado un error a una advertencia durante la preparación del mensaje, cuando se alcanza el límite de 100 descargas de contenido por hora móvil. Ahora se muestra una advertencia cuando se alcanza el límite, lo que permite continuar con la entrega.

* Al enriquecer el contenido de un mensaje transaccional, los vínculos ya no se recuperan al recuperar datos de la tabla Perfil, lo que reduce la latencia durante la preparación del mensaje y evita los datos de perfil vacíos debido a una relación incorrecta definida con la tabla de perfil.

* La configuración técnica de la instancia se ha optimizado para garantizar la estabilidad. (CAMP-45681)

* Se ha mejorado la administración de sesiones para optimizar la memoria. (CAMP-45901, CAMP-46767)

* La actividad **Transferir archivo** ahora genera una variable adicional (filesCount) que contiene el número de archivos cargados o descargados. (CAMP-45842) [Obtenga más información](../../automating/using/transfer-file.md#output-variables)

* El conector SMS ahora puede enviar varios parámetros opcionales con cada mensaje. [Obtenga más información](../../administration/using/sms-protocol.md)

* Los usuarios con la función DATAMODEL ahora pueden publicar extensiones de registro de entrega. (CAMP-46604)

* Se ha aclarado el mensaje de error que se mostraba al intentar publicar un recurso direccionado a un recurso personalizado que ya no existe. (CAMP-46893)

* Se han agregado los siguientes idiomas a la lista **Idioma preferido**: Indonesio - Indonesia (in-id), Inglés - Suecia (en-se), Inglés - Asia Pacífico (en-ap), Inglés - Japón (en-jp) y Español - América Latina (es-la). (CAMP-46351)

* El selector de selección de perfiles al probar una página de aterrizaje utilizará ahora el recurso profilBase en lugar de perfil para evitar el tiempo de espera.

* Se ha mejorado el formato de registro de SMPP.

* Se han agregado parámetros opcionales a las funciones cryptString y decryptString JS para que coincidan con las API de Adobe Campaign Classic.

* Se han mejorado los mensajes de advertencia o error en los registros de preparación de entrega.

* Se han mejorado los registros de errores al intentar conectarse al servicio Identity Management de Adobe (IMS).

* Ahora puede filtrar más las dimensiones **Entrega** y **Campaign** mediante la barra de búsqueda en creación de informes dinámica.

* La fecha de validez del mensaje SMS transaccional ahora se puede definir mediante el valor establecido para el parámetro de caducidad en la API de Mensajes transaccionales. (CAMP-36600)

* En la creación de informes dinámica, el informe integrado de **Resumen de entrega** mostraba datos incorrectos para la métrica de tasa sin suscribir. Se ha agregado una nueva métrica con el nombre **baja única** para corregir esto. (CAMP-46445)

**Parches**

* Se ha corregido un problema que provocaba que las entregas se ejecutaran muy lentamente debido a ciertos procesos. Esto se debe a unidades incorrectas definidas para varios parámetros (milisegundos en lugar de segundos, por ejemplo).

* Se ha corregido un problema que se producía cuando el SDK de Mobile enviaba una solicitud de seguimiento abierta basada en la condición de que deliveryId/MessageID no fuera nulo. Esto resultaría en errores 404 para entregas con seguimiento deshabilitado. Una variable adicional (acsDeliveryTracking) con información sobre el estado de seguimiento de la entrega ahora se envía en la carga útil. Esta variable puede tener dos valores activados o desactivados según el estado de seguimiento establecido. [Obtenga más información](../../administration/using/push-tracking.md).

* Se ha corregido un problema con los flujos de trabajo que se podía producir al copiar y pegar una actividad de **anulación de duplicación** que se había ejecutado una vez y que aprovechaba un recurso temporal. Una vez duplicado, el recurso de la actividad se definía automáticamente en vacío, lo que producía problemas en otras actividades del flujo de trabajo. Una vez pegado, el recurso de la actividad seguirá siendo el mismo para que el error se active lo antes posible en lugar de más tarde en el flujo de trabajo. (CAMP-46903)

* Se ha corregido un problema que ocasionaba que fallara el análisis de entrega al enviar perfiles de direccionamiento de mensajes push transaccionales, al introducir una nueva [asignación de destino](../../administration/using/target-mappings-in-campaign.md): **Perfil: evento en tiempo real para push** (*mapRtEventAppSubRcp*). La entrega, la exclusión y los registros de seguimiento de las [notificaciones push transaccionales basadas en un perfil](../../channels/using/transactional-push-notifications.md#transactional-push-notifications-targeting-a-profile) se almacenarán ahora en las tablas *broadLogAppSubRcp*, *excludeLogAppSubRcp* y *trackingLogAppSubRcp*.

   >[!IMPORTANT]
   >
   >Debido a este cambio, si está utilizando una notificación transaccional basada en perfiles existente (creada antes de actualizar a Adobe Campaign 21.1), se recomienda actualizar la asignación de destino a la nueva y volver a publicar el mensaje. Consulte los pasos detallados [aquí](../../channels/using/transactional-push-notifications.md#change-target-mapping). El uso de la asignación de destino anterior **Perfil: evento de tiempo real** (*mapRtEventRcp*) puede provocar tiempos de preparación de envíos más largos y una degradación del rendimiento.

* Se ha corregido un problema que impedía que los informes de envío se ejecutaran cuando se mostraban 5000 filas.
* Se ha corregido un problema con las Pruebas A/B que impedía que el contenido de la variante B se actualizara después de que se hubiera modificado la plantilla de envíos. (CAMP-45235)
* Se ha corregido un problema que provocaba que el proceso de mensajería transaccional se quedara atascado, lo que evitaba que se enviaran mensajes.
* Se ha corregido un problema que podía provocar problemas de navegación al hacer clic en un vínculo interno (por ejemplo, al acceder a la entrega principal desde una pantalla de resumen de prueba).
* Se ha corregido un problema que impedía que se mostraran todas las plantillas de contenido de Experience Manager disponibles al crear una entrega. (CAMP-45990)
* Se ha corregido un problema con flujos de trabajo que podía impedir que se mostraran mensajes de error en los registros de envío después de agregar la columna **Motivo** a la pestaña de datos adicional. (CAMP-45139)
* Se ha corregido un problema que se podía producir cuando dos llamadas de suscripción de aplicación tenían el mismo ID de Marketing Cloud (&#39;el valor de clave de duplicado infringe el error de restricción única&#39;).
* Se ha corregido un problema que podía provocar problemas de lentitud al arrastrar y soltar actividades en un flujo de trabajo que contenía una gran cantidad de actividades de **Consulta** y **Leer lectura**. (CAMP-44511)
* Se ha corregido un error que podía producirse al final de la preparación del mensaje transaccional, lo que imped&#39;ia que la información de redirección se cargara en los servidores de seguimiento.
* Se ha corregido un problema que podía mostrar mensajes de error al intentar abrir plantillas de importación o trabajos de importación anteriores después de haber personalizado el recurso de flujo de trabajo. (CAMP-46183)
* Se ha corregido un problema que podía impedir que se ejecutara una actividad **Leer audiencia** si estaba configurada con un nombre de audiencia dinámica. (CAMP-46047)
* Se ha corregido un problema que impedía que se mostrara el botón **Exportar lista**
* Se ha corregido un problema que podía provocar un error en el flujo de trabajo **Agregados de creación de informes**. (CAMP-45979)
* Se ha corregido un problema al crear un recurso personalizado con una clave compuesta personalizada (contenido dinámico de texto/fecha).
* Se ha corregido un problema que podía impedir que se mostraran los datos de transición de consultas. (CAMP-45669)
* Se han corregido problemas de consumo de memoria relacionados con la publicación de recursos personalizados.
* Se ha corregido un problema que se producía al configurar una entrega para enviarla en una fecha específica. Si la entrega se estableció para enviarse inmediatamente después de confirmarse, se produjo un error en la preparación de la entrega y se tuvo en cuenta la fecha especificada inicialmente. (CAMP-44107)
* Se ha corregido un problema que podía impedir que se abrieran plantillas transaccionales. (CAMP-47181)
* Se ha corregido un problema en el proceso de publicación de mensaje transaccional que podía provocar reglas de tipología y tipologías de duplicado con nombres que superaran el tamaño de cadena permitido. (CAMP-47104)
* Se ha corregido un problema con la actividad **API externa** que se producía cuando un parámetro de entrada devolvía un registro que no existía. (CAMP-47023)
* Se ha corregido un problema que podía impedir que el conector SMPP se reconectara.
* Se ha corregido un problema que se producía con la actividad **Transferencia de archivos** al descargar un archivo que contenía un punto en su nombre. Los caracteres que siguen al punto se consideraron como la extensión del archivo. (CAMP-46624)
* Se ha corregido un problema que impedía que se realizara el agrupamiento de bases de datos, lo que provocaba que los mensajes transaccionales quedaran atascados en la cola del enrutador.
* Se ha corregido un error que no evitaba que se enviaran los registros de envío cancelados.
* Se ha corregido un problema que podía provocar un error en un flujo de trabajo al usar una actividad **AND-join**. La actividad cambió automáticamente el conjunto Principal a la última transición cableada, incluso si mostraba visualmente la primera transición cableada. (CAMP-46900)
* Se ha corregido un problema que podía hacer que las direcciones que se pusieron en cuarentena correctamente tuvieran su estado configurado incorrectamente en Válido, con lo que se eliminaron, así, de la cuarentena.
* Se ha corregido un problema que podía impedir que se mostraran campos personalizados si contenían caracteres especiales. (CAMP-46805)
* Se ha corregido un problema que podía impedir que se mostrara una vista detallada específica para un perfil. Esto ocurría si el recurso de perfil se había ampliado con campos personalizados con la opción **Añadir una sección de campos personalizados** habilitada.
* Se ha corregido un problema que podía devolver un código de error 500 al enviar eventos transaccionales. (CAMP-46811)
* Se ha corregido un problema que podía impedir que recibiera informes programados por correo electrónico. (CAMP-46891)
* Se ha corregido un problema que se producía al vincular un recurso personalizado al recurso de perfil con un vínculo simple de cardinalidad 1. Al acceder a un perfil con el campo de recurso personalizado vacío, ahora se muestra un mensaje de error en lugar de una lista vacía.
* Se ha corregido un problema que se producía al utilizar la sustitución de perfiles en un flujo de trabajo, en el que la página no podía cargar los perfiles de entrega al seleccionar el perfil que se va a reemplazar. (CAMP-46522)
* Se ha corregido una regresión en la que el flujo de trabajo técnico **Database Cleanup** intentaba eliminar las tablas de trabajo de entrega caducadas, lo que daba como resultado los siguientes errores: (CAMP-46536)

```
   PGS-220000 PostgreSQL error: ERROR: table ""wkdlv_24439460_data"" does not exist and WDB-200001 SQL statement 'DROP TABLE wkdlv_24448131_data' could not be executed.
```

* Se ha corregido el siguiente error que se producía en algunos casos al usar el filtro personalizado en los recursos personalizados: (CAMP-46509)

```
   The 'profile/xxxx' field used in the filter 'xxxxx' does not exist in custom resource 'xxx'
```

* Se ha corregido un problema en el cual la **preparación de la notificación push** tardaba demasiado en completarse. Esto se debía a que faltaba un índice en las tablas de trabajo transitorias.
* Se ha corregido un error que se podía producir al utilizar la opción **Dimensión para reconciliar** en una actividad de **Reconciliación** en un flujo de trabajo si ya se había definido una relación entre un recurso personalizado y un recurso de perfil.
* Se ha corregido un problema que se producía al agregar vínculos a través de una actividad de **Reconciliación** o **Enriquecimiento**. Los vínculos seleccionados no se mostraban en la transición de salida.
* Se ha corregido un problema al usar una actividad de **Segmentación** con entregas recurrentes en un flujo de trabajo que hacía que la entrega se enviara a la audiencia incorrecta. (CAMP-46275, CAMP-46470)
* Se ha corregido un error en el que la publicación de recursos personalizados fallaba al intentar ampliar el recurso de perfil para crear dimensiones de perfil personalizadas para creación de informes dinámica. (CAMP-46266)
* Se ha corregido un error que se producía al agregar un vínculo a una tabla de importación de archivos. Después de agregar una actividad **Enriquecimiento** a la actividad **Importación de archivos**, el vínculo previamente configurado desapareció. (CAMP-46557)
* Se ha corregido un problema al usar recursos personalizados vinculados a datos de perfil en el cual el orden de visualización en la pantalla de configuración **Detalles** se cambiaba al guardar. (CAMP-46312)
* Se ha corregido un problema que podía impedir que se mostraran datos en creación de informes dinámica debido a entregas basadas en una asignación de entrega personalizada.
* Se ha corregido un error que podía impedir que seleccionara una colección con un destinatario de recursos incorrecto en una actividad de flujo de trabajo **Consulta**.
* Se ha corregido un problema que podía hacer que el proceso de InMail validara las devoluciones en firme de forma incorrecta.
* Se ha corregido un error que se producía al abrir una pantalla de perfil debido a un error de vínculo.
* Se ha corregido un problema que podía impedir que se eliminaran datos de RGPD del flujo de trabajo de limpieza.
* Se ha corregido un error que se producía cuando la configuración de programación se actualizaba manualmente con el teclado en los parámetros de programación de entrega de correo electrónico.
* Se ha corregido un problema que impedía editar un perfil debido a parámetros incorrectos en la unidad organizativa.
* Se ha corregido un problema que permitía que el campo de extensión **Servicio** estuviera vacío e imposible de establecer en las **propiedades de correo electrónico**, incluso si se había establecido en la Plantilla de envíos.
* Se ha corregido un problema que podía provocar que las pruebas tardaran más en procesarse. (CAMP-45048)
* Se ha corregido un problema que podía impedir que se ordenaran columnas en una pantalla de información general de perfil.
* Se ha corregido un problema de generación de miniaturas que podía ocurrir en Azure en las variantes de correo electrónico que contenían caracteres chinos. (CAMP-47152)
* Se ha corregido una regresión introducida en Campaign 20.4 que podría llevar a tasas abiertas incorrectas para Gmail debido al filtrado de eventos de seguimiento recibidos de cuentas de Gmail. (CAMP-46504)
* Se ha corregido un problema que podía impedir la importación de contenido HTML en una plantilla de mensaje transaccional. (CAMP-47318)
* Se ha corregido un problema que podía ralentizar la visualización de las representaciones en el **informe de procesamiento de correo electrónico**. (CAMP-46226)
* Se ha corregido un problema que podía impedir la publicación de recursos personalizados configurados con un elemento de tipo lista en la definición de pantalla. (CAMP-47217)
* Se ha corregido un problema con el Diseñador de correo electrónico que impedía que los divisores de línea se representaran correctamente en **Microsoft Outlook** al colocarse en la parte superior del contenido del correo electrónico. (CAMP-46294)
* Se ha corregido un problema que provocaba que la reconciliación de KPI con el flujo de trabajo técnico de **Adobe Analytics** se quedara atascada. (CAMP-46576)
* Se ha corregido un problema con el **Diseñador de correo electrónico** que impedía que los fragmentos se mostraran automáticamente en los cuadros de búsqueda al insertar bloques de contenido. (CAMP-44205)
* Se ha corregido un problema con el **Diseñador de correo electrónico** que provocaba que se mostraran caracteres no deseados en los correos electrónicos enviados al usar emojis en fragmentos. (CAMP-46621)
* Se ha corregido la regresión introducida en 20.4 con el **Diseñador de correo electrónico** que afecta al componente divisor, lo que resultaba en alturas de línea adicionales y distorsiones de imagen en el contenido. (CAMP-46663)
* Se ha corregido un problema que obligaba a los botones predeterminados a permanecer centrados cuando se enviaba el mensaje a un buzón de Outlook, aunque estos botones estuvieran alineados a la derecha o a la izquierda en el **Diseñador de correo electrónico**. (CAMP-46466)
* Se ha corregido un problema que impedía que la lista de perfiles de prueba se actualizara al buscar perfiles en la previsualización del **Diseñador de correo electrónico**. (CAMP-45265)
* Se ha corregido un problema que impedía que se mostraran perfiles de prueba personalizados en la lista al buscar perfiles en la previsualización del **Diseñador de correo electrónico**. (CAMP-45589)
* Se ha corregido un problema que provocaba que se mostraran fechas no coincidentes al generar gráficos de tendencias desde el **Informe de resumen de entrega**. (CAMP-45521)
