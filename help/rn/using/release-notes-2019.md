---
title: Notas de la versión 2019
description: Esta página enumera todas las versiones de 2019 de Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '7674'
ht-degree: 9%

---

# Notas de la versión 2019{#release-notes-2019}

## Versión 19.4: diciembre de 2019 {#release-19-4---october-2019}

**Novedades**

<table> 
 <thead> 
  <tr> 
   <th> <strong>California Consumer Privacy Act (CCPA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>La CCPA es la nueva ley de privacidad del Estado de California que armoniza y moderniza los requisitos de protección de datos y entrará en vigencia el 1 de enero de 2020. La CCPA se aplica a los clientes de Adobe Campaign que albergan datos de sujetos de datos que residen en California.</p>
   <p>Además de las funciones de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimientos, la configuración de retención de datos y las funciones de usuario), aprovechamos esta oportunidad para incluir funciones adicionales que le ayudarán a prepararse para la CCPA:</p>
   <ul>
    <li>Derecho de acceso y derecho de eliminación: estamos aprovechando las capacidades agregadas para el RGPD. <a href="https://helpx.adobe.com/content/help/es/campaign/kb/acs-privacy.html#righttoaccess">Más información</a> </li>
    <li><p>Al crear una solicitud de privacidad, se ha agregado el tipo de regulación (RGPD o CCPA) en el servicio principal de privacidad. Este método es el que debe utilizar para todas las solicitudes de acceso y eliminación. El uso de la API y la interfaz de Campaign para las solicitudes de acceso y eliminación quedará obsoleto.  Consulte el artículo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes">Funciones obsoletas y eliminadas</a>.</p></li>
    <li>A <strong>Opción de exclusión de CCPA</strong> Se ha añadido un campo de a la variable Perfiles para permitir a los usuarios de Adobe Campaign realizar un seguimiento si un consumidor se ha excluido de la venta de Información personal. <a href="https://helpx.adobe.com/es/content/help/es-ES/campaign/kb/acs-privacy.html#ccpa">Más información</a>.</li>
  </ul>
    <p>Consulte el vídeo de <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">procedimiento</a>.</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integración de Microsoft Dynamics 365 (GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>Ya está disponible la integración entre Adobe Campaign Standard y Microsoft Dynamics 365. Podrá transferir los registros de contacto y de entidad personalizada de Dynamics 365 a Campaign y recuperar los datos de eventos de correo electrónico de Campaign en Dynamics 365 para mejorar la alineación de ventas y marketing.</p>
    <p>Consulte la <a href="../../integrating/using/d365-acs-get-started.md">documentación detallada</a> para configurar esta integración.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Mejoras**

* La ventana emergente de consentimiento para la creación de informes dinámica se ha actualizado para incluir la integración de Adobe Campaign Standard y Microsoft Dynamics 365. Al aceptar los términos, los datos de perfil se incluirán al utilizar la integración de Adobe Campaign Standard / Microsoft Dynamics 365 y el sistema de informes dinámico. [Más información](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) (CAMP-29766)
* Se ha corregido un problema que mostraba fechas de contacto incorrectas al recibir alertas de entrega.
* Cuando se envía un evento de mensaje transaccional con un parámetro de contexto desconocido, Campaign ahora devuelve un mensaje de error 400 en lugar de 500. (CAMP-28632)
* Un nuevo **Excluir revisión** El segmento se ha añadido a la creación de informes dinámica. Este segmento está seleccionado de forma predeterminada para filtrar los informes. [Más información](../../reporting/using/list-of-components-.md#segments)
* El **Caducidad del mensaje** se ha añadido a la notificación push. Permite especificar una fecha de caducidad en la que Apple (APNS) o Android (FCM) ya no enviarán el mensaje. [Más información](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Se han realizado mejoras en el **Cargar archivo** actividad: los registros de flujo de trabajo se han simplificado para añadir claridad y detallado sobre el error que se produce cuando no se puede cargar un archivo. La transición saliente generada al activar el **Mantener los rechazos en un archivo** se ha cambiado el nombre de la opción **Rechazos**. [Más información](../../automating/using/load-file.md)
* Se han añadido registros relacionados multilingües a los registros de envío para comprender mejor los errores de envío debido a la falta de idiomas en los archivos CSV cargados.

**Mejoras de seguridad**

* Se ha corregido un problema que se producía al eliminar la información de un perfil en cuarentena a través de una solicitud de privacidad, lo que eliminaba todos los datos excepto la dirección de correo electrónico en la lista de cuarentena.
* Se ha mejorado la seguridad para la protección contra inyecciones en encabezados de correo electrónico.
* Se ha mejorado la seguridad para la protección contra ataques SSRF en los que se pueden utilizar expresiones xtk (HTML de correo electrónico, contenido de texto y asunto, SMS y contenido de notificaciones push).

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que impedía que se realizara un seguimiento de los vínculos de baja, suscripción y página de aterrizaje al insertarlos en un correo electrónico. (CAMP-37809)
* Se ha corregido un problema que podría provocar errores al crear un nuevo correo electrónico y seleccionar una plantilla. (CAMP-38000)
* Al editar un vínculo con el Diseñador de correo electrónico, ahora puede utilizar la variable **Subrayar vínculo** opción. Además, una **Target** se ha agregado con el valor predeterminado establecido en **Ninguno**. [Más información](../../designing/using/styles.md#about-styling-links)
* Se ha corregido un problema de color en los vínculos de los componentes de texto del cuerpo de un correo electrónico. (CAMP-37330)
* Se ha corregido un problema que impedía que se eliminaran los vínculos asociados al eliminar una imagen. (CAMP-37234)
* Se ha corregido un problema que impedía guardar modificaciones en el **Pedido** configuración del contenido dinámico en una condición. (CAMP-36883)
* Se ha corregido un problema al buscar páginas de aterrizaje. La búsqueda se ha ampliado de las 50 primeras creadas a todas las bases de datos. (CAMP-36839)
* Se ha corregido un problema al guardar modificaciones en el remitente del correo electrónico en la **De: Nombre** field. (CAMP-36606)
* La advertencia de compatibilidad del componente de carrusel se ha modificado para reflejar los clientes de correo electrónico admitidos.
* Se ha corregido un problema de visualización en dispositivos móviles. El atributo height ahora siempre se establece en &quot;height: auto&quot; al añadir o cargar una imagen nueva en un correo electrónico. (CAMP-35497)
* Se ha corregido un problema que dejaba etiquetas de estilo y metadatos en el HTML al eliminar un fragmento de un componente de estructura. (CAMP-35390)
* Se ha corregido un problema con los fragmentos al actualizar contenido reutilizable. (CAMP-35186)
* Se ha corregido un problema que se producía al mostrar solo contenido condicional móvil en correos electrónicos. (CAMP-35155)
* Se ha corregido un problema que mostraba de forma aleatoria espacios de no separación de anchura cero. (CAMP-35116)
* Se ha corregido un problema con la posición de los botones en la **Guardar como fragmento** Cuadro de diálogo.
* Se ha corregido un problema con la vista previa al añadir una etiqueta de HTML en un título de imagen y texto alternativo.
* Se ha corregido un problema al editar, en el Diseñador de correo electrónico, los vínculos creados en correos electrónicos desde el editor heredado.
* Se ha corregido un problema que dejaba etiquetas de estilo duplicadas en el contenido.
* Se ha corregido un problema con el formato de fecha al insertar un campo de personalización en un correo electrónico.
* Se ha corregido un problema que se producía al guardar al cambiar del modo HTML a texto sin formato.
* Se ha corregido un problema que se producía al hacer clic en la opción de bloqueo y desbloqueo, que añadía valores de margen en el panel de propiedades de estilo en línea.
* Se ha corregido un problema con el tamaño de la vista previa para móviles para un mejor procesamiento.
* Se ha corregido un problema con el tamaño de los botones en las plantillas y los fragmentos.
* Se ha corregido un problema con el tamaño de las imágenes al insertarlas en un componente de botón.

**Otros cambios**

* El intervalo de tiempo predeterminado para el cual se muestran los datos en las páginas de KPI de entrega y en la página de creación de informes dinámica se ha alineado para evitar discrepancias en los resultados de la creación de informes. (CAMP-35148)
* Se agregó un mensaje de error en los registros cuando el certificado de la aplicación caducó.
* La previsualización del cálculo de carga útil ahora incluye un tamaño de campo personalizado para evitar errores de notificaciones push. (CAMP-35303)
* El nombre del **Rechaza el archivo** en el **Cargar archivo** ahora, la actividad se puede personalizar en el mismo estado que en el **Exportación de archivos** actividad.
* Ahora se puede acceder a todas las entidades personalizadas que no están vinculadas a ninguna entidad predeterminada a través de la API.
* Rendimiento de base de datos mejorado en recursos grandes.
* Se han aclarado las descripciones de algunos errores que se producen al enviar mensajes SMS. (CAMP-36558)
* Ahora aparece un mensaje de error al ejecutar el flujo de trabajo de **Planificador** actividad conectada a sí misma, ya sea directamente o a través de varias actividades, ya que esto podría provocar que el servidor de flujo de trabajo de la instancia se bloqueara.
* Se han realizado mejoras para solucionar los problemas de los mensajes transaccionales: el vínculo &quot;Datos&quot; ha pasado a denominarse &quot;Últimos eventos transaccionales&quot; en la pantalla de configuración de eventos y ahora enumera los eventos recibidos ordenados en orden descendente. Además, se ha creado un nuevo estado de evento transaccional: &quot;targetingFailed&quot;. Cuando el módulo de mensajería transaccional no puede enriquecer un vínculo que se utiliza para el direccionamiento de mensajes, el evento transaccional ahora estará en este nuevo estado (en lugar del estado &quot;routingFailed&quot;).
* Se ha mejorado la interfaz al restringir el acceso a las páginas de aterrizaje a unidades geográficas u organizativas específicas. El objetivo es advertir que la página de aterrizaje puede estar sujeta a condiciones de visibilidad: la selección de una unidad geográfica y organizativa al crear una página de aterrizaje ahora es obligatoria. Ahora se muestra un titular con información relacionada una vez seleccionada una unidad. Se ha aclarado el mensaje de error que se muestra al probar la página de aterrizaje.
* En las API de Campaign Standard, las claves personalizadas no se pueden modificar mediante una operación de PATCH si el valor de la clave es diferente de la clave de origen o si utiliza su propia clave comercial como URI en lugar de la proporcionada por Adobe.
* Se ha añadido el idioma &quot;Albanés - Macedonia&quot; a la lista desplegable de idioma preferido. (CAMP-35396)

**Parches**

* Se ha corregido un problema que impedía que se ordenaran o buscaran informes programados.
* Se ha corregido un problema con las reglas de Déclencheur que provocaba que las reglas AND y OR se confundieran.
* Se ha corregido un problema que mostraba la propiedad Mobile como Eliminada en Launch. (CAMP-35382)
* Se ha corregido un problema que impedía que las propiedades móviles de Adobe de Launch se sincronizaran en Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Se ha corregido un problema en el cual los mensajes push transaccionales fallaban cuando los eventos se enriquecieron con datos de perfil. (CAMP-34385)
* Se ha corregido un problema con las propiedades móviles, que no se sincronizaban en varios entornos. (CAMP-37060)
* Se ha corregido un problema que se producía al seleccionar, en una notificación push, una plantilla con una fórmula de fecha de contacto. (CAMP-35300)
* Se ha corregido un problema que podría provocar que el servicio de envío de mensajes se bloqueara. (CAMP-35287)
* Se ha corregido un problema con los correos postales recurrentes, todos definidos con la primera fecha del evento. (CAMP-35139)
* Se ha corregido un problema con los **Perfiles** recursos personalizados que no estaban disponibles para consultas. (CAMP-35119)
* Se ha corregido el **Reparar estructura de base de datos** modo para instancias con la configuración de uso compartido activada. (CAMP-35118)
* Se ha corregido un problema que provocaba un error de registro de SQL al añadir datos acumulados en broadlogs. (CAMP-35034)
* Se ha corregido un problema con las transiciones al crear una **Segmentación** actividad. (CAMP-35033)
* Se ha corregido un problema en **Consulta** actividad que impedía que **encryption_aescbcDecrypt** descifrar la función **encryption_aescbcEncrypt** función. (CAMP-34952)
* Se ha corregido un problema que podía impedir que **Registros de seguimiento** de mostrarse en las entregas. (CAMP-34855)
* Se ha corregido un problema al usar un **Optimización del tiempo de envío** fórmula de fecha personalizada, que podría evitar que se enviaran notificaciones push debido a errores con los datos adicionales del flujo de trabajo. (CAMP-30336)
* Se ha corregido un problema que podía impedir que se publicaran recursos personalizados. (CAMP-37425)
* Se ha corregido un problema que impedía a los usuarios administradores modificar paquetes de importación.  (CAMP-37176)
* Se ha corregido un problema en los flujos de trabajo que impedía que se enviaran pruebas si la actividad de entrega estaba conectada a un vacío **Leer audiencia** actividad. (CAMP-37164)
* Se ha corregido un problema que impedía que los recursos personalizados se importaran en un entorno nuevo. (CAMP-36506)
* Se ha corregido un problema en los informes de clics interactivos que podía hacer que las imágenes ocultaran porcentajes (CAMP -36407)
* Se ha corregido un problema que se producía al intentar exportar un campo de descripción de entrega. (CAMP-35467)
* Se ha corregido un problema que podía dejar el estado de una entrega como &quot;Inicio pendiente&quot;, aunque la entrega había finalizado. (CAMP-35355)
* Se ha corregido un problema que impedía que se mostraran los registros de flujo de trabajo después de habilitar y, a continuación, deshabilitar los registros SQL.

## Versión 19.3: julio de 2019 {#release-19-3---july-2019}

**Novedades**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Actividad de API externa (beta pública)<br /> </td> 
   <td> <p>Para una personalización más detallada, la actividad de API externa permite introducir datos de sistemas externos en un flujo de trabajo mediante una llamada de API de REST. Los extremos de REST pueden ser un sistema de administración de clientes, un extremo de REST de Adobe I/O Runtime o Adobe Experience Cloud (por ejemplo, Data Platform, Target, Analytics, Campaign).</p><p>Esta funcionalidad se encuentra actualmente en versión de beta pública.</p><p>Para obtener más información, consulte la <a href="../../automating/using/external-api.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">videotutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Informe sobre segmento de flujo de trabajo<br /> </td> 
   <td> <p>Esta función permite a los especialistas en marketing desglosar el rendimiento de entrega por código de segmento. Cuando crea un flujo de trabajo y utiliza una actividad de segmentación para asignar segmentos a la población de entrega, estos segmentos ahora pueden entrar en el mismo envío. Esto le permite mostrar las estadísticas de aperturas/clics basadas en varios segmentos dentro de un envío.</p><p>Para obtener más información, consulte la <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">videotutorial</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Mejoras de seguridad**

* Se ha corregido un problema de seguridad para evitar ataques de denegación de servicio (DoS) en solicitudes no válidas para obtener imágenes. (CAMP-33454)

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que añadía etiquetas de estilo de HTML adicionales a una plantilla de HTML cada vez que se añadía un componente, lo que podía aumentar drásticamente el tamaño de la plantilla. (CAMP-34694)
* Se ha corregido un problema que podía impedir que algunas opciones del menú de la barra de herramientas superior derecha estuvieran disponibles. (CAMP-34577)
* Se ha corregido un problema que se producía cuando el bloque de contenido de URL de la página espejo se insertaba en un contenido de correo electrónico. (CAMP-34779)
* Se ha corregido un problema que se producía al utilizar el código JSP en un correo electrónico, lo que dificultaba la edición del contenido. (CAMP-34574)
* Se ha corregido un problema que provocaba que las imágenes se truncaran en la parte superior al agregarles un hipervínculo. (CAMP-34382)
* Se ha corregido un problema con la visualización al utilizar el Diseñador de correo electrónico con Firefox. (CAMP-34364)
* Se han corregido varios problemas que se producían con el modo Avanzado al definir contenido dinámico en un mensaje de correo electrónico. (CAMP-34351, CAMP-34333, CAMP-34331)
* Se han corregido varios problemas que había con el editor de reglas de contenido dinámico (CAMP-34304, CAMP-34303).
* Se ha corregido un problema que podía impedir que el campo Vínculo se mostrara en el panel Configuración del Diseñador de correo electrónico (CAMP-33749).
* Se ha corregido un problema con el icono de YouTube que era demasiado grande en los correos electrónicos enviados. (CAMP-33726)
* Se ha corregido un problema de seguridad que hacía que el contenido de la página espejo se pudiera editar. (CAMP-33691)
* Se ha corregido un problema que rompía la salida del HTML al usar el símbolo mayor que en el contenido dinámico. (CAMP-33688)
* Se ha corregido un problema que se producía al utilizar la opción Deshacer al editar texto en el Diseñador de correo electrónico. (CAMP-32565)
* Se ha corregido un problema que creaba etiquetas adicionales al deshacer estilos en lugar de eliminarlos. (CAMP-32359)
* Ahora puede definir si cada componente utilizado en un correo electrónico se mostrará solo en dispositivos de escritorio o solo en dispositivos móviles.
* Ahora puede establecer la anchura y la altura de un componente de contenido social.
* Se ha corregido un problema que impedía que el contenido dinámico y el código fuente antiguo se eliminaran después de eliminar ese contenido dinámico.
* Se ha corregido un problema que podía impedir que el asunto de un correo electrónico se actualizara después de modificarse.
* Se ha corregido un problema que impedía que se seleccionara una estructura de columna n:n una vez colocada en el espacio de trabajo.
* Se ha corregido un problema que hacía que la miniatura del mensaje pareciera borrosa en el panel de correo electrónico.
* Se ha corregido un problema que impedía que el fondo se mostrara correctamente para los correos electrónicos recibidos en Outlook.
* Se han corregido algunos problemas de ordenación en la página de inicio del Diseñador de correo electrónico.
* Se ha corregido un problema que se producía al duplicar variantes al utilizar contenido dinámico.
* Se han eliminado algunos campos no deseados del panel Configuración del Diseñador de correo electrónico.

**Otras mejoras**

* Gracias a la integración con los servicios de ubicación de Adobe Experience Platform, ahora Adobe Campaign es compatible para enviar mensajes de marketing basados en la ubicación a los suscriptores de la aplicación móvil mediante el SDK de Experience Platform. Para obtener más información, consulte la [documentación detallada](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* La función de creación de informes se ha mejorado para mejorar la experiencia. Para utilizar esta función, debe aceptar el Contrato de uso de creación de informes dinámicos. Para obtener más información, consulte [documentación detallada](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* En los flujos de trabajo, se ha añadido una nueva opción para previsualizar las siguientes diez ejecuciones de un flujo de trabajo. Para obtener más información, consulte [documentación detallada](../../automating/using/scheduler.md).
* En la actividad Scheduler, una nueva opción le permite seleccionar un día específico de una semana específica para las entregas mensuales. Para obtener más información, consulte [documentación detallada](../../automating/using/scheduler.md).
* Al crear envíos recurrentes sin periodo de acumulación, el panel de envío ahora le permite solicitar confirmación antes de realizar la entrega. Para obtener más información, consulte [documentación detallada](../../sending/using/confirming-the-send.md).
* Ahora puede personalizar la etiqueta de una entrega con variables de evento que se han declarado en la actividad de señal externa del flujo de trabajo. Para obtener más información, consulte [documentación detallada](../../automating/using/calling-a-workflow-with-external-parameters.md).
* Se ha mejorado la consulta de eliminación del RGPD para obtener un mejor rendimiento. (CAMP-33504)
* La opción &quot;ftp&quot; se ha eliminado de la interfaz de configuración de cuenta externa. (CAMP-34472)
* Ahora puede habilitar y deshabilitar la opción de modo de prueba SMTP para cada mensaje de correo electrónico. Para obtener más información, consulte [documentación detallada](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Otros cambios**

* Se ha añadido una advertencia en la interfaz de propiedades de entrega. Especifica que las entregas se preparan en función de su periodo de agregación y se descongelan para llamar al flujo de trabajo varias veces al día; debe asegurarse de que no tengan ningún periodo. (CAMP-34393)
* Se ha agregado una advertencia en las pantallas de configuración de recursos personalizadas. Se recomienda usar un máximo de 30 caracteres para los ID de recursos personalizados. Esto también se aplica a los campos de recursos personalizados, las claves, los índices y los vínculos.
* Ahora aparece un mensaje al intentar eliminar un mensaje transaccional que una página de aterrizaje utiliza como mensaje de confirmación.
* Ahora aparece una advertencia en los registros de flujos de trabajo cuando una actividad se ha estado ejecutando durante más de 6 horas. Esto no se aplica a las actividades Push notification, Delivery, Signal, Start, End, Fork , AND-Joint, Schedule y Wait.
* Ahora aparece una advertencia en los registros de flujos de trabajo cuando se alcanza el número máximo de flujos de trabajo que se están ejecutando simultáneamente.
* Los flujos de trabajo que han estado en pausa o en estado de error durante más de 7 días ahora se detienen para consumir menos espacio en disco. La tarea de limpieza se muestra en los registros del flujo de trabajo.
* Cuando se utiliza una actividad &quot;Transferir archivo&quot;, ahora se registra un error si el tamaño del archivo supera el espacio en disco disponible.
* La acción Redirigir a URL de destino ya no se puede seleccionar para el botón secundario en los mensajes en la aplicación.

**Parches**

* Se ha corregido un problema que podría provocar que las solicitudes de acceso al RGPD fallaran.
* Se ha corregido un problema que podría provocar que los déclencheur se descarten cuando se reciben varios déclencheur para un perfil único.
* Se ha corregido un problema que podría provocar un mensaje de error de publicación de recursos personalizados erróneo tras el inicio de sesión.
* Se ha corregido un problema que mostraba una página en blanco al crear o ampliar un recurso personalizado.
* Se ha corregido un problema que impedía que una audiencia con appSubscriptionsRcp como dimensión de segmentación estuviera disponible para la segmentación en una entrega móvil.
* Se ha corregido un error que impedía que las direcciones de correo electrónico de devoluciones duras se pusieran en cuarentena. (CAMP-24587)
* Se ha corregido un problema que se producía al agregar una regla de tipología y, a continuación, eliminarla antes de guardar la tipología. (CAMP-32789)
* Se ha corregido un problema que podía impedir que se mostrara el contenido de la página de aterrizaje al deshabilitar contenido dinámico. (CAMP-32924)
* Se ha corregido un problema con los envíos recurrentes que se producía al utilizar la personalización en los atributos de un envío principal. (CAMP-32983)
* Se ha corregido un problema en los flujos de trabajo que impedía leer los resultados de una transición que contenía datos de mensajes SMS entrantes. (CAMP-33134)
* Se ha corregido un problema con los flujos de trabajo que se producía al combinar actividades de bifurcación y exclusión para crear audiencias. (CAMP-33401)
* Se ha corregido un problema que podía impedir que se mostrara el contenido de la página espejo y que se enviaran mensajes de prueba para entregas recurrentes. (CAMP-33413)
* Se ha corregido un problema que provocaba un error al usar una actividad de unión entre perfiles y audiencias. Este problema se debía a una incompatibilidad de las claves de identificación en las transiciones de entrada. (CAMP-33713)
* Se ha corregido un problema en las actividades Test que impedía que la expresión &quot;recCount&quot; utilizara la sintaxis correcta al hacer doble clic en ella. (CAMP-33756)
* Se ha corregido un problema que podría provocar un mensaje de error al abrir los registros del flujo de trabajo técnico Facturación. (CAMP-34313)
* Se ha corregido un problema en las páginas de aterrizaje que se podía producir al configurar campos de casilla de verificación con suscripciones. (CAMP-34369)
* Se ha corregido un problema que se producía al configurar una lista y agregarle el campo &quot;icono&quot;. (CAMP-34585)
* Se ha corregido un problema que impedía usar los símbolos &quot;|&quot; y &quot;%&quot; como separadores de fecha y hora en las actividades de flujo de trabajo de Cargar archivo. (CAMP-34706)
* Se ha corregido un problema que se producía al usar condiciones de visibilidad con casillas de verificación en páginas de aterrizaje. (CAMP-34802)
* Se ha corregido un problema en la actividad Enriquecimiento que impedía que los campos se mostraran en la pestaña &quot;Datos adicionales&quot; si la dimensión de filtrado se establecía en registros de seguimiento y la dimensión de destino en perfil.
* Se ha corregido un problema que provocaba un mensaje de error al exportar un recurso &quot;workflowTemplate&quot;.
* Se ha corregido un problema al crear un nuevo perfil, que impedía guardar el campo &quot;Código de país/región&quot; si se seleccionaba en el cuadro de diálogo.
* Se han corregido varios problemas que se producían al utilizar la plantilla de importación Correo directo (updateQuarantinesDeliveryLogsDirectMail).
* Se ha corregido un problema relacionado con la integración de Assets on Demand.
* Se ha corregido un problema que se producía al ampliar la vista Línea de tiempo. (CAMP-33628)
* Se ha corregido un problema que impedía que se enviaran pruebas instantáneamente para mensajes de correo electrónico con una fecha y una hora programadas. (CAMP-33723)
* Se ha corregido un problema relacionado con los mensajes transaccionales que generaban registros de error cuando un usuario cerraba sesión. (CAMP-31698)
* Se ha corregido un error que se podía producir en entornos específicos al programar un mensaje de correo electrónico.
* Se ha corregido un problema que provocaba que fallara el flujo de trabajo de ejecución del envío de actualización.
* Se ha corregido un problema de seguridad que rompía el contenido del correo electrónico cuando el asunto contenía varias líneas.


## Versión 19.2.7: julio de 2019 {#release-19-2-7---july-2019}

**Mejoras**

* Se ha mejorado la consulta de eliminación del RGPD para obtener un mejor rendimiento.
* Se ha corregido un problema que podría provocar bloqueos de la web después de la actualización a la versión 19.2. (CAMP-34862)
* Se ha corregido un problema que podía impedir que los usuarios que no eran administradores guardaran o programaran informes. (CAMP-31133)
* Se ha corregido un problema que se producía al usar &quot;|&quot; como separador de fechas en la actividad de flujo de trabajo Cargar archivo. (CAMP-34706)

## Versión 19.2.4: junio de 2019 {#release-19-2-4---june-2019}

**Diseñador de correos electrónicos**

* Se ha corregido un problema que impedía que los usuarios editaran fragmentos cuando se utilizaban etiquetas de estilo vacías en el HTML. Esta es una corrección de seguimiento para CAMP-33778 en 19.2.3.

## Versión 19.2.3: junio de 2019 {#release-19-2-3---june-2019}

**Diseñador de correos electrónicos**

Se ha introducido una serie de mejoras y correcciones para optimizar los fragmentos en la versión 19.2. Los fragmentos recién creados funcionarán sin problemas. Los fragmentos creados anteriormente se han atenuado y deben migrarse al nuevo formato. Para ello, haga clic en cada fragmento y valide su migración al nuevo formato. Le recomendamos que pruebe algunos fragmentos antes de migrarlos todos.

* Se ha corregido un problema que impedía a los usuarios editar un fragmento después de desbloquearlo. Esto afectaba a los fragmentos existentes al actualizar a 19.2. (CAMP-33778)
* Se ha corregido un problema al usar contenido dinámico. Se han añadido espacios adicionales en el HTML.

**Otras mejoras**

* Se ha corregido un problema que podía impedir que el envío de SMS se reanudara después de una desconexión del conector SMS.
* Se ha corregido un problema que podía cerrar las conexiones SMPP cuando TLS estaba habilitado.
* Se ha corregido un problema que podía cerrar las conexiones SMPP cuando TLS estaba habilitado.
* La opción &quot;Launch_URL_Campaign&quot; se ha añadido en Campaign para administrar las propiedades de las aplicaciones móviles creadas con el SDK para móviles de Adobe Experience Platform.
* Se ha corregido un error que provocaba que la opción de entorno de espacio aislado se desactivara después de cargar el certificado de una propiedad móvil recién creada y de salir de la página de propiedades de la aplicación móvil.
* Se ha corregido un problema que impedía enriquecer el contenido de un mensaje transaccional con información del recurso Servicio. (CAMP-33707)
* Se ha corregido un problema en las páginas de aterrizaje de lista de bloqueados de la que se producía al intentar cancelar la suscripción de perfiles de un servicio.

## Versión 19.2: mayo de 2019 {#release-19-2---may-2019}

**Novedades**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Panel de control<br /> </td> 
   <td> <p>Para aumentar la eficacia de su trabajo como usuario administrador, puede supervisar fácilmente la capacidad y administrar la configuración de las instancias (empezando por la administración de servidores SFTP).</p><p>Para obtener más información, consulte la <a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=es">videotutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notificaciones locales<br /> </td> 
   <td> <p>Los mensajes de notificación locales permiten informar a los usuarios de que hay nuevos datos disponibles en sus aplicaciones móviles, incluso sin tener acceso a Internet o sin ejecutar la aplicación en primer plano. Las notificaciones locales se activan mediante una aplicación móvil en un momento determinado y según un evento.</p><p>Para obtener más información, consulte la <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentación detallada</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Mejora del flujo de trabajo: Añada una carga útil a una actividad de señal externa<br /> </td> 
   <td> <p>Inicie un flujo de trabajo con una carga útil cuando las condiciones definidas se cumplan correctamente con otro flujo de trabajo o una llamada de API REST para integrarlos con los sistemas externos. Esto también incluye una nueva <strong>prueba</strong> actividad en la que puede ejecutar pruebas en esta funcionalidad.</p><p>Para obtener más información, consulte la <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">videotutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Mejora de las páginas de destino: Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveche Google reCAPTCHA para evitar el correo no deseado en las páginas de aterrizaje sin que sus clientes tengan que hacer nada.</p><p>Para obtener más información, consulte la <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">documentación detallada</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Mejoras de seguridad**

* Se ha corregido un posible problema de seguridad de secuestro de clics en el espacio de trabajo de informes.

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que se producía al duplicar fragmentos y al intentar utilizarlos en el Diseñador de correo electrónico. (CAMP-33193)
* Se ha corregido un problema que creaba espacios no deseados al utilizar elementos en línea en la interfaz del Diseñador de correo electrónico. (CAMP-32163)
* Se ha corregido un problema que eliminaba algunos atributos de etiquetas de HTML adicionales agregados por el usuario después de guardar el contenido del correo electrónico en el Diseñador de correo electrónico. (CAMP-32162)
* Se ha corregido un problema que mostraba una etiqueta de Microsoft Office en el modo de HTML del Diseñador de correo electrónico incluso después de eliminarla. (CAMP-32141)
* Si ha creado un correo electrónico con una versión anterior del Diseñador de correo electrónico, al abrir este contenido del correo electrónico, una ventana emergente ahora le pedirá al usuario que actualice a la versión más reciente. (CAMP-31529)
* Se ha corregido un problema que podía distorsionar imágenes de un correo electrónico creado con el Diseñador de correo electrónico cuando se enviaba a algunos clientes de mensajería. (CAMP-31407)
* Se ha corregido un problema que impedía que algunos elementos, como listas o botones, se mostraran correctamente en modo de texto sin formato al crearse en modo HTML. (CAMP-32582, CAMP-32542)
* Se ha corregido un problema que impedía mostrar más de 50 unidades organizativas en una plantilla de contenido o propiedades de fragmento. (CAMP-32932)
* Se ha corregido un problema con el color de fondo de la ventanilla móvil al recibir un correo electrónico creado con el Diseñador de correo electrónico en Outlook. (CAMP-31402)
* Se ha corregido un problema que podía impedir que el contenido del correo electrónico creado con el Diseñador de correo electrónico respondiera cuando se abría en Outlook. (CAMP-31400)
* Se ha corregido un problema que impedía que el contenido dinámico funcionara correctamente cuando se usaba en un asunto de correo electrónico. (CAMP-32837)
* Se ha corregido un problema relacionado con el asunto del correo electrónico que no se había escapado correctamente.
* Se ha corregido un problema que impedía que los fragmentos se cargaran en la paleta izquierda del Diseñador de correo electrónico.
* Se ha corregido un problema que impedía que los fragmentos creados durante la edición de contenido de correo electrónico se mostraran en la paleta izquierda del Diseñador de correo electrónico al actualizar la lista de fragmentos.
* Se han corregido varios problemas que se producían al utilizar contenido dinámico en un mensaje de correo electrónico.
* Se ha corregido un problema que se producía con el selector de color al intentar definir un color con valores de RGB.
* Se ha corregido un problema que impedía que la página espejo respondiera al recibir el correo electrónico en un móvil.

**Mejoras de mensajería transaccional**

Se han añadido varias mejoras al canal de mensajería transaccional para optimizar el funcionamiento y el rendimiento.

* La duración del mensaje transaccional se ha ampliado para garantizar que todos los mensajes se envíen antes de que caduquen, especialmente cuando se realizan reintentos.
* El rendimiento de la mensajería transaccional se ha aumentado mediante la distribución de la carga en diferentes subprocesos de envío.
* El proceso de mensajería transaccional se ha optimizado para poder iniciar en paralelo múltiples análisis del mismo mensaje.
* Se ha corregido un problema que podría provocar un rendimiento y una latencia incoherentes en las notificaciones push transaccionales.
* Se ha corregido un problema que mostraba una audiencia objetivo incorrecta para los envíos de ejecución de mensajes transaccionales.
* Se ha corregido un problema que se producía al importar un paquete con una configuración de evento y el mensaje transaccional asociado. Para obtener más información, consulte [documentación detallada](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* Se ha corregido un problema que eliminaba los datos de recopilación de los perfiles de prueba creados para un mensaje transaccional que contenía listas de productos.

**Otros cambios**

* Se ha añadido una nueva opción a la cuenta externa SMS. Permite limitar el número máximo de procesos de MTA que envían SMS para controlar mejor el número de conexiones paralelas. Para obtener más información, consulte la [Configuración y protocolo del conector SMS](https://helpx.adobe.com/es/campaign/kb/sms-connector-protocol-and-settings.html) nota técnica.
* Al publicar un recurso con extensión de API, si la API ya se ha publicado, ahora se actualiza automáticamente cada vez que se vuelve a publicar. Anteriormente, esta acción era manual y, si no se actualizaba la API, se podía romper el perfil o el recurso de servicio de esta API. Para obtener más información, consulte [documentación detallada](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* La dimensión Código postal se ha eliminado del sistema de informes dinámico. Se recomienda utilizar las dimensiones Ciudad, País y Estado en su lugar.
* Se ha eliminado el déclencheur de evento de ciclo vital &quot;Primer inicio&quot; para los mensajes en la aplicación.
* Al exportar un paquete con grupos de seguridad, ahora contiene las funciones asignadas a cada grupo. (CAMP-32960)
* En la actividad Cargar archivo, una nueva opción le permite comprobar que las columnas del archivo que está cargando coinciden con la definición de la columna. Para obtener más información, consulte la [documentación detallada](../../automating/using/load-file.md). (CAMP-32229)
* Los flujos de trabajo ahora se pueden iniciar con una carga útil, lo que permite utilizar y compartir parámetros externos entre actividades dentro del flujo de trabajo. Para obtener más información, consulte la [documentación detallada](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 Y CAMP-29413)
* Las API de Campaign Standard ahora permiten actualizar las unidades geográficas y organizativas de los perfiles mediante una carga útil. Para obtener más información, consulte la [documentación detallada](../../api/using/get-started-apis.md).
* Se han aclarado los mensajes de error cuando no se puede acceder a un objeto de la base de datos.
* En la actividad Extraer archivo, se han actualizado las funcionalidades de Javascript al definir el nombre de un archivo que exportar. Ahora solo está disponible la función formatDate para su uso en el campo Output. Para obtener más información, consulte la [documentación detallada](../../automating/using/extract-file.md).
* Se ha mejorado la generación de ID de secuencia automática para los recursos personalizados. Las claves principales de los nuevos recursos personalizados ahora se encuentran en 64 bits de forma predeterminada.
* Se ha mejorado el modo de prueba de publicación de recursos personalizado. Ahora se muestra un mensaje de advertencia a los usuarios si la última publicación de recursos personalizados ha fallado y no está fija. Tras un error de publicación de recursos personalizados, puede volver a la última versión en funcionamiento. Para obtener más información, consulte la [documentación detallada](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Se ha añadido una nueva opción en la actividad Transferir archivo. Permite ordenar los archivos cuando se utiliza la acción File download, en modo SFTP. Para obtener más información, consulte la [documentación detallada](../../automating/using/transfer-file.md). (CAMP-33109)

**Parches**

* Se ha corregido un problema que podría provocar una fuga de memoria al MTA cuando se recargaba la configuración de SMS.
* Se ha corregido un problema que podía impedir la publicación de actualizaciones de la base de datos en modo de reparación.
* Se ha corregido un problema que provocaba discrepancias entre los informes de Adobe Analytics y los informes dinámicos de Adobe Campaign. (CAMP-25393)
* Se ha corregido un error que hacía que fallara el flujo de trabajo de uso compartido de informes.
* Se ha corregido un error que impedía a los usuarios enviar mensajes en la aplicación con solo la URL de medios.
* Se ha corregido un problema que mostraba una aplicación móvil incluso si su certificado no se había cargado en la instancia.
* Se ha corregido un error que impedía que los campos de personalización funcionaran al usar el **Segmentar a todos los usuarios de una aplicación móvil** plantilla.
* Se han aprovisionado nuevas instancias de Campaign Standard. (CAMP-32635 Y CAMP-32344)
* Se ha corregido un error que impedía personalizar la fórmula de fecha en un flujo de trabajo. (CAMP-30336)
* Se ha corregido un problema que se producía al definir una fórmula de fecha personalizada que podía impedir que los campos &quot;Datos adicionales&quot; y &quot;Código de segmento&quot; estuvieran disponibles en la lista desplegable. (CAMP-32383)
* Se ha corregido un problema que podía impedir que las actividades &quot;Transferir archivo&quot; y &quot;Extraer archivo&quot; encontraran los rechazos de archivos si estaban cifrados. (CAMP-32377)
* Se ha corregido un problema en las API que podía impedir que el filtro lineCount procesara el recuento total exacto. (CAMP-31424)
* Se ha corregido un problema en las páginas de aterrizaje que podía impedir que los campos de entrada mostraran el valor actualizado una vez modificado. (CAMP-31401)
* Se ha corregido un problema que podría provocar que una actividad de señal se active inesperadamente.
* Se ha corregido un problema que podía impedir que se mostrara la vista previa del correo electrónico cuando la audiencia estaba vacía.
* Se ha corregido un problema en la actividad &quot;Extraer archivo&quot; que podía generar un archivo mientras se activaba la opción &quot;No generar un archivo si la transición entrante está vacía&quot;.
* Se ha corregido un problema que provocaba que el flujo de trabajo de la Capacidad de entrega se desactivara si no terminaba correctamente.
* Se ha corregido un problema que podía impedir que los usuarios guardaran o programaran informes. (CAMP-31133)

## Versión 19.1.3: marzo de 2019 {#release-19-1-3---march-2019}

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que impedía modificar una plantilla después de guardarla.
* Se han corregido varios problemas al utilizar una plantilla creada anteriormente en un correo electrónico.
* Se ha corregido un problema que impedía que los componentes se ocultaran en plantillas importadas.

**Otras mejoras**

* Se ha corregido un error al ver las reglas de tipología. (CAMP-32059 Y CAMP-31849)
* Se ha corregido un problema que impedía que se editaran las reglas de tipología. (CAMP-31750)
* Se ha corregido un problema con el proceso de inMail que podía detenerse inesperadamente. (CAMP-31238)

## Versión 19.1: febrero de 2019 {#release-19-1---february-2019}

**Novedades**

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Mejoras en los informes de canal push<br /> </td> 
   <td> <p>Se han añadido varias mejoras a los informes de canal push para que pueda medir la participación del usuario de forma más intuitiva. Con esta versión, ampliamos la lista de métricas de canales push a tres métricas diferentes: Impresiones, Clics, Aperturas (Apertura de aplicación) para ayudarle a medir y analizar la interacción de los usuarios con notificaciones push de forma más eficaz. Junto con esto, también estamos estandarizando la definición e implementación de estas métricas. El informe integrado de notificaciones push también se ha mejorado con visualizaciones y métricas de uso común.</p><p> Para obtener más información, consulte la <a href="../../reporting/using/push-notification-report.md">documentación detallada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Integración de Launch para aplicaciones móviles<br /> </td> 
   <td> <p>Esta versión contiene la integración de Adobe Campaign con las versiones GA de las extensiones Android y iOS para Adobe Campaign Standard en Adobe Experience Platform Launch y los SDK móviles. Estas extensiones admiten la mensajería push, la mensajería en la aplicación y las actualizaciones de perfil de aplicaciones móviles.</p><p> Para obtener más información, consulte la <a href="https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html">documentación detallada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mensajería en la aplicación móvil<br /> </td> 
   <td> <p>Esta versión contiene la versión GA del canal In-App en Campaign. Desde el punto de vista funcional, las adiciones más importantes a la versión Beta son los informes dinámicos para el canal In-App y el protocolo de enlace seguro entre el SDK móvil y el MCIAS (servicio de mensajería In-App de Marketing Cloud que sirve para las reglas In-App al SDK). Un protocolo de enlace seguro garantiza que los datos PII de los usuarios no caigan en manos malintencionadas, y permite mantener la privacidad de los usuarios en un dispositivo compartido al borrar la caché de mensajes cada vez que el usuario cierra la sesión.</p><p>Para obtener más información, consulte la <a href="../../channels/using/about-in-app-messaging.md">documentación detallada</a> y la dedicada <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">Tutorial en la aplicación</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mejoras del flujo de trabajo<br /> </td> 
   <td> <p>Se han añadido las siguientes funciones de flujo de trabajo:</p> 
    <ul> 
     <li> Ahora puede copiar y pegar actividades dentro de un flujo de trabajo o en otro flujo de trabajo de la misma instancia de Campaign. De este modo, puede duplicar fácilmente un flujo de trabajo completo o actividades específicas y conservar la configuración definida inicialmente. Para obtener más información, consulte la <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentación detallada</a>. (CAMP-20014) </li> 
     <li> Al usar el <strong>Cargar archivo</strong> actividad, ahora puede añadir una marca de tiempo al nombre del archivo que contiene los registros rechazados. Para obtener más información, consulte la <a href="../../automating/using/load-file.md#configuration">documentación detallada</a>. </li> 
     <li> <strong>Consulta</strong> y <strong>Segmentación</strong> las actividades ahora permiten habilitar una transición saliente en el caso de que las actividades no recuperen datos. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras de seguridad**

* El código del HTML de la página de aterrizaje generada se ha actualizado para evitar la indexación del motor de búsqueda.

**Mejoras en el diseñador de correo electrónico**

* Ya está disponible un conjunto de cuatro mejores plantillas de correo electrónico adaptables diseñadas por artistas de Behance.

  Para obtener más información, consulte la [documentación detallada](../../designing/using/using-reusable-content.md#content-templates).

* Nuestra nueva experiencia de incorporación le ayuda a iniciar la creación de correos electrónicos más rápido y le facilita el acceso a la documentación y a los tutoriales.

  Para obtener más información, consulte la [documentación detallada](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Ahora tiene la flexibilidad para configurar el número de columnas y el ancho según sus necesidades.

  Para obtener más información, consulte la [documentación detallada](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Al editar en la vista móvil, puede ocultar ciertos componentes solo en la visualización móvil para un uso eficaz del espacio.

  Para obtener más información, consulte la [documentación detallada](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Ahora puede añadir canales sociales personalizados a la plantilla de correo electrónico además de los que ya están disponibles.
* Se ha corregido un problema que impedía desplazarse hacia abajo en el menú de estructura al utilizar más de 18 estructuras. (CAMP-31173)
* Se ha corregido un problema que mostraba el preencabezado encima del contenido al reenviar un correo electrónico que contenía un preencabezado enviado con Adobe Campaign. (CAMP-30736)
* Se ha corregido un problema que impedía actualizar la línea de asunto al hacer clic en **AEM Actualizar contenido de** después de modificar el asunto en Adobe Experience Manager. (CAMP-29984)
* Se han corregido varios problemas que evitaban el uso de imágenes dinámicas desde Adobe Target.
* Se ha corregido un problema que impedía actualizar la vista previa al recuperar contenido en el momento de la preparación si el contenido se había importado previamente desde una dirección URL.
* El icono de YouTube se ha añadido a **Social** componente de contenido.
* El **Lista** Se ha añadido una vista para los componentes de contenido y los fragmentos mostrados en la paleta Diseñador de correo electrónico.

**Otras mejoras**

* Adobe Campaign ahora es totalmente compatible con FCM para las aplicaciones SDK V4 y SDK de AEP.
* Adobe Campaign admite notificaciones push en Wear OS de Android y watchOS de Apple.
* Los mensajes de advertencia y error que se pueden mostrar al navegar en la interfaz se han aclarado y simplificado.
* Ahora puede agregar a la lista de perfiles columnas relacionadas con la inclusión y la exclusión (campos &quot;Ya no contacte con...&quot;).
* La lista desplegable Zona horaria de la pantalla Creación de perfiles se ha movido de la sección Dirección a la sección superior de la interfaz.
* Ahora puede agregar separadores al configurar pantallas de recursos personalizadas, lo que le permite organizar los campos en categorías.

  Para obtener más información, consulte la [documentación detallada](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Otros cambios**

* Adobe Campaign y Adobe Experience Cloud dejarán de ofrecer asistencia para Microsoft Internet Explorer 11 a partir de la primavera de 2019 y para Campaign Standard 19.2. Cambie a Microsoft Edge u otro explorador compatible. Consulte [Funciones en desuso y eliminadas](../../rn/using/deprecated-features.md) página.
* El **Código de país** El campo del recurso de perfil se ha cambiado a **Código de país o región**.

**Parches**

* Se ha corregido un problema que impedía que se enviara el mensaje al agregar un perfil de prueba a un mensaje transaccional de correo electrónico. (CAMP-29854)
* Se ha corregido un problema que ralentizaba el envío de mensajes desde otros canales si el envío era bajo para un canal cuando el envío de mensajes desde todos los canales se activaba simultáneamente.
* Se ha corregido un problema que provocaba que el MTA empezara a enviar mensajes SMS cuando la conexión de cuenta externa aún no se había establecido.
* Se ha corregido un problema que se producía con la frecuencia de ejecución de la actividad del planificador y la hora de inicio. (CAMP-30745)
* Se ha corregido un problema que se podía producir con la generación de PKEY al utilizar recursos de perfil extendidos. (CAMP-30285)
* Se ha corregido un problema que se podía producir con las reglas de fatiga basadas en el día del calendario. (CAMP-30136)
* Se ha corregido un problema que se podía producir al intentar acceder a recursos personalizados con nombres que terminaban con &quot;Base&quot;. (CAMP-30109)
* Se ha corregido un problema que impedía usar una llamada al PATCH para suscribir un perfil a un servicio. (CAMP-29728)
* Se ha corregido un problema que podía dañar un flujo de trabajo al importar un archivo XML a través de la actividad Cargar archivo. (CAMP-29208 y CAMP-28205)
* Se ha corregido un problema que se producía al vincular recursos personalizados y que podía impedir que se generaran vínculos de cardinalidad inversa. (CAMP-30476)
* Se ha corregido un problema que impedía ampliar los registros de envío al utilizar solo el código de segmento.
* Se ha corregido un problema que podía duplicar filas al utilizar la actividad de transferencia de archivos en flujos de trabajo.
* Se ha corregido un problema que impedía que los informes programados se enviaran en el momento elegido.
* Se ha corregido un problema que provocaba discrepancias entre los KPI &quot;Para entregar&quot; y &quot;Enviado&quot; para una entrega en la aplicación en un flujo de trabajo.
* Se ha corregido un problema que impedía que el seguimiento funcionara para un mensaje en la aplicación creado con un HTML personalizado.
* Se ha corregido un problema que impedía guardar el contenido de la entrega en la aplicación al utilizarlo en un flujo de trabajo.
* Se ha corregido un problema que impedía que se mostraran aplicaciones móviles para los administradores.
* Se ha corregido un problema que ocasionaba que fallara el flujo de trabajo técnico Deliverability Update. (CAMP-26387)
* Se ha corregido un problema que provocaba discrepancias entre los perfiles segmentados al crear una entrega en la aplicación y los mostrados en el panel de entrega. (CAMP-28722)
* Se ha corregido un problema con la integración de Campaign y el servicio principal Assets que podía impedir la selección de un recurso compartido en un mensaje de correo electrónico.

## Versión 19.0: enero de 2019 {#release-19-0---january-2019}

**Novedades**

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Disponibilidad general del Diseñador de correo electrónico<br /> </td> 
   <td> <p>El nuevo e intuitivo diseñador de correo electrónico (anteriormente conocido como diseñador creativo) se ha trasladado a GA. Ahora admite todas las funciones del antiguo editor de contenido, entre ellas:</p> 
    <ul> 
     <li> El uso de <a href="../../integrating/using/adding-target-dynamic-content.md">imágenes dinámicas de Adobe Target</a> </li> 
     <li> La capacidad de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperar contenido de una URL automáticamente al momento de la preparación</a> </li> 
     <li> Totalmente compatible <a href="../../designing/using/using-reusable-content.md#content-templates">plantillas de contenido listas para usar</a>. </li> 
    </ul> 
    <p>Para obtener más información, consulte la <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">vídeo explicativo</a>. A continuación se enumeran las mejoras y correcciones.</p><p>Como consecuencia, el antiguo editor de contenido se considera ya obsoleto. Para obtener más información, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes">página</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listados de productos en correos electrónicos transaccionales<br /> </td> 
   <td> <p>Ahora puede hacer referencia a una o más colecciones de productos en un mensaje de correo electrónico transaccional. Por ejemplo, puede enviar automáticamente un correo electrónico de abandono de carrito que enumere todos los productos que había en el carrito del usuario, incluyéndose una imagen, un precio y un vínculo a cada uno de los productos.</p><p>Para obtener más información, consulte la <a href="../../designing/using/using-product-listings.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">videotutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Vista móvil en el Diseñador de correo electrónico<br /> </td> 
   <td> <p>Ahora puede cambiar a una vista móvil dedicada al editar el contenido del correo electrónico. Esto le permite ajustar el diseño interactivo de un correo electrónico editando por separado todas las opciones de estilo de la pantalla móvil, como la adaptación de los márgenes, un tamaño de fuente más pequeño, un color de fondo diferente, etc.</p><p> Para obtener más información, consulte la <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">documentación detallada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mejoras en la versión beta de Mensajería en la aplicación<br /> </td> 
   <td> <p>La función Mensajería en la aplicación beta se ha mejorado con las siguientes funciones:</p> 
    <ul> 
     <li> El canal beta de la aplicación es compatible con el RGPD </li> 
     <li> Integración con las API de Analytics para rellenar listas desplegables de Déclencheur </li> 
     <li> Aspecto intuitivo y descripción de las plantillas de envío </li> 
     <li> Mejoras en la interfaz de creación desde el punto de vista de uso </li> 
    </ul> <p>Para obtener más información, consulte la <a href="../../channels/using/about-in-app-messaging.md">documentación detallada</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Una nueva opción en la actividad Load data ahora permite aplicar una fase de procesamiento posterior al archivo que contiene los registros rechazados (por ejemplo, compresión en formato zip). (CAMP-24521)
* Una nueva opción en la actividad de actualización de datos ahora le permite configurar el tamaño máximo del lote de datos que se va a cargar. (CAMP-28400)
* Se ha mejorado la selección de estados de direcciones de los perfiles. Al seleccionar un país, la lista desplegable &quot;Estado&quot; ahora se actualiza automáticamente con los valores de estados relevantes. (CAMP-28874)
* Una nueva opción en la actividad Extraer archivo ahora impide generar un archivo si la transición entrante está vacía. Esto evita la creación y carga de archivos vacíos en los servidores SFTP.
* Se ha mejorado el informe Resumen de entrega.
* Se ha enriquecido la lista de países disponibles al definir la dirección de un perfil. (CAMP-26707)
* Ahora se muestra un mensaje de error al intentar importar un flujo de trabajo integrado.

**Diseñador de correos electrónicos**

* Se ha corregido un problema que habilitaba la capacidad de la unidad geográfica en una plantilla de correo electrónico o en un fragmento de contenido creado con el Diseñador de correo electrónico, aunque esta capacidad estuviera deshabilitada en Adobe Campaign, lo que hacía que la plantilla o el fragmento no estuviera disponible al intentar acceder a ella de nuevo. (CAMP-28174)
* Se ha corregido un problema que impedía guardar las condiciones de contenido dinámico al editar contenido con el Diseñador de correo electrónico. (CAMP-27905)
* Se ha corregido un problema que eliminaba la versión del HTML del contenido del correo electrónico después de editar la versión de texto sin formato de un mensaje y romper la sincronización del HTML en el Diseñador de correo electrónico. (CAMP-28507)
* Se ha corregido un problema que impedía que la interfaz del Diseñador de correo electrónico se abriera al utilizar Internet Explorer 11. (CAMP-28273)
* Se ha corregido un problema que distorsionaba la representación en Microsoft Outlook de la configuración de estilo aplicada a los botones con el Diseñador de correo electrónico.
* Se ha corregido un problema con el Diseñador de correo electrónico que hacía que se pudiera editar una dirección URL a partir de un fragmento de contenido utilizado en un correo electrónico, lo cual no se esperaba, ya que el fragmento está bloqueado de forma predeterminada.
* Se ha corregido un problema que impedía que el componente divisor del Diseñador de correo electrónico se mostrara en Microsoft Office.
* AEM Se ha corregido un problema que provocaba la congelación de una página en ciertos navegadores de Internet al ver un contenido sincronizado desde el uso del editor de contenido de correo electrónico heredado de, que se ha sincronizado desde el editor de contenido. (CAMP-29068)
* Se ha corregido un error que se producía al hacer clic en cualquier imagen de un correo electrónico al utilizar el editor de contenido de correo electrónico heredado. (CAMP-30424)
* Se ha corregido un problema que impedía que se mostraran los fragmentos recién creados al editar un correo electrónico con el Diseñador de correo electrónico. (CAMP-29928)
* Se ha corregido un problema que impedía que el texto del botón se mostrara correctamente en los correos electrónicos creados con el Diseñador de correo electrónico y recibidos con el cliente de correo web de Outlook.
* Ahora es posible crear mensajes transaccionales de perfil mediante el Diseñador de correo electrónico. (CAMP-28900)
* Se ha corregido un error en el Diseñador de correo electrónico que hacía que el contenido se pudiera editar al recuperar contenido de una dirección URL automáticamente durante la preparación, cuando debería estar bloqueado.

**Parches**

* Se ha corregido un problema que mostraba registros de envío incorrectos en creación de informes dinámica. (CAMP-23446)
* Se ha corregido un problema que podía afectar a los números del informe Resumen de devoluciones (CAMP-28703)
* Se ha corregido un problema con la integración de Campaign y el servicio principal Assets que podía impedir que se mostraran los recursos al seleccionar **[!UICONTROL Image shared from Adobe Experience Cloud]** en un correo electrónico (CAMP-28732).
* Se ha corregido un problema que impedía que se enviaran mensajes SMS que contuvieran el carácter &quot;one&quot; aunque la transliteración estuviera autorizada en la cuenta externa SMPP. (CAMP-29041)
* Se ha corregido un problema que podía mostrar registros duplicados al utilizar una actividad de Segmentación en flujos de trabajo. (CAMP-28743)
* Se ha corregido un problema que impedía eliminar una de las asignaciones de valores en una columna de una actividad de flujo de trabajo. (CAMP-28708)
* Se ha corregido un problema en la actividad Transferencia de archivos, al utilizar caracteres comodín con la opción &quot;Probar para ver si el archivo existe&quot;. (CAMP-28977)
* Se ha corregido un problema con la actividad Transferencia de archivos que se podía producir al actualizar la configuración de la cuenta externa. (CAMP-28894)
* Se ha corregido un problema con los filtros personalizados en el editor de consultas al utilizar la condición &quot;El correo electrónico no está vacío&quot;. (CAMP-28741)
* Se ha corregido un problema que se podía producir al exportar tablas de recursos personalizadas con más de 100 000 registros. (CAMP-28150)
* Se ha corregido un problema que impedía eliminar mensajes transaccionales vinculados a déclencheur. (CAMP-28385)
* Se han eliminado contraseñas que se mostraban en algunos registros SMS.
* Se ha corregido un problema que ocasionaba que fallaran las conexiones al simulador de SMPP debido a la contraseña vacía enviada por Adobe Campaign.
* Se ha corregido un problema que impedía enviar campañas cuando las conexiones SMS eran inestables.
* Se ha corregido un problema que mostraba los envíos eliminados en la creación de informes dinámica.
* Se ha corregido un problema que podía impedir la recuperación de datos adicionales de los registros de envío, los registros de seguimiento y las tablas de exclusión de registros al utilizar una actividad de enriquecimiento en un flujo de trabajo.
* Se ha corregido un problema con las solicitudes de eliminación de RGPD que se podía producir al utilizar un tipo de vínculo &quot;Vínculo de recopilación de cardinalidad N&quot; y la opción &quot;Eliminar el registro de destino implica eliminar registros y referencias por el vínculo&quot;.
* Se ha corregido un problema con el uso compartido de informes.
* Se ha corregido un problema que podría provocar problemas de rendimiento al enviar una notificación push.
* Se ha corregido un problema con los archivos de salida de correo directo que faltaban campos.
* Se ha corregido un problema que permitía a los usuarios modificar flujos de trabajo integrados.
* Se ha corregido un problema que se producía al crear una campaña basada en una plantilla de campaña, incluido un flujo de trabajo con una actividad de extracción configurada. (CAMP-29198)
* Se ha corregido un problema con la actividad File extraction que impedía usar la misma expresión para varios elementos. (CAMP-29182)
* Se ha corregido un problema, en el editor de consultas, con la condición de unión entre broadlog y registro de seguimiento para rtEvent. (CAMP-28780)
* Se ha corregido un problema que impedía guardar las modificaciones a la opción de página de aterrizaje &quot;Acción específica&quot;. (CAMP-29422)
* Se ha corregido un problema que impedía exportar la carga útil de un evento en un flujo de trabajo. (CAMP-29029)
* Se ha corregido un problema que impedía que los números SMS de la lista de bloqueados de la se excluyeran en un mensaje SMS. (CAMP-28898)
* Se ha corregido un problema que podía impedir que se notificara a los proveedores de SMPP en caso de error al procesar los mensajes entrantes. (CAMP-29804)
* Se ha corregido un problema que permitía que se eliminaran cuentas externas con envíos asociados. (CAMP-29738)
* El rendimiento de envío se ha mejorado y estabilizado para los mensajes SMS.
* Se ha corregido un problema que impedía que el carácter &quot;~&quot; se usara en un mensaje SMS. (CAMP-29172)
* Se ha corregido un problema en los envíos con la opción Send time optimization. (CAMP-29231)
