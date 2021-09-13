---
title: Notas de la versión 2019
description: Esta página enumera todas las versiones de 2019 de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 6a53e6f5-9b69-4068-ab7d-10e22e266277
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '7589'
ht-degree: 9%

---

# Notas de la versión 2019{#release-notes-2019}

[Planificación de versiones](https://helpx.adobe.com/es/campaign/kb/acs-release-planning.html)  | Versiones de  [Panel de control de Campaign](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es)  |  [Actualizaciones de documentación](../../rn/using/documentation-updates.md)  |  [Últimas notas de la versión](../../rn/using/release-notes.md)  | Funciones  [obsoletas](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes)

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
   <p>Además de las funciones de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), aprovechamos esta oportunidad para incluir funciones adicionales que le ayudarán a prepararse para la CCPA:</p>
   <ul>
    <li>Derecho de acceso y derecho de eliminación: estamos aprovechando las capacidades agregadas para el RGPD. <a href="https://helpx.adobe.com/content/help/es/campaign/kb/acs-privacy.html#righttoaccess">Más información</a> </li>
    <li><p>Al crear una solicitud de privacidad, se ha agregado el tipo de regulación (RGPD o CCPA) en el servicio principal de privacidad. Este método es el que debe utilizar para todas las solicitudes de acceso y eliminación. El uso de la API y la interfaz de Campaign para las solicitudes de acceso y eliminación quedará obsoleto.  Consulte el artículo <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">Funciones obsoletas y eliminadas</a>.</p></li>
    <li>Se ha agregado un campo <strong>Exclusión de CCPA</strong> al recurso Perfiles para permitir a los usuarios de Adobe Campaign realizar un seguimiento sobre si un consumidor se ha excluido de la venta de Información personal. <a href="https://helpx.adobe.com/es/content/help/es-ES/campaign/kb/acs-privacy.html#ccpa">Más información</a>.</li>
  </ul>
    <p>Consulte el vídeo de <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">procedimiento</a>.</p>
</td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integración con Microsoft Dynamics 365 (GA)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> 
    <p>Ya está disponible la integración entre Adobe Campaign Standard y Microsoft Dynamics 365. Podrá transferir sus registros de contacto y de entidad personalizada de Dynamics 365 a Campaign y obtener los datos de evento de correo electrónico de Campaign a Dynamics 365 para mejorar la alineación de ventas y marketing.</p>
    <p>Consulte la <a href="../../integrating/using/d365-acs-get-started.md">documentación detallada</a> para configurar esta integración.</p>
  </td>
  </tr> 
 </tbody> 
</table>

**Mejoras**

* La ventana emergente de consentimiento para los informes dinámicos se ha actualizado para incluir la integración de Adobe Campaign Standard y Microsoft Dynamics 365. Al aceptar los términos, los datos de perfil se incluirán al utilizar la integración de Adobe Campaign Standard con Microsoft Dynamics 365 y los informes dinámicos. [Más información](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)  (CAMP-29766)
* Se ha corregido un problema que mostraba fechas de contacto incorrectas al recibir alertas de entrega.
* Cuando se envía un evento de mensaje transaccional con un parámetro de contexto desconocido, Campaign ahora devuelve un mensaje de error &quot;400&quot; en lugar de &quot;500&quot;. (CAMP-28632)
* Se ha añadido un nuevo segmento **Exclude proof** en los informes dinámicos. Este segmento ahora está seleccionado de forma predeterminada para filtrar los informes. [Más información](../../reporting/using/list-of-components-.md#segments)
* Se ha añadido la opción **Message expiration** a la notificación push. Le permite especificar una fecha de caducidad en la que Apple (APNS) o Android (FCM) ya no enviarán el mensaje. [Más información](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Se han realizado mejoras en la actividad **Load file**: los registros de flujo de trabajo se han simplificado para proporcionar información más clara y detallada sobre el error que se produce cuando un archivo no se puede cargar. Se ha cambiado el nombre de la transición saliente generada al activar la opción **Keep the rejects in a file** a **Rejects**. [Más información](../../automating/using/load-file.md)
* Se han agregado registros relacionados multilingües a los registros de envío para comprender mejor los errores de envío debido a que faltan idiomas en los archivos CSV cargados.

**Mejoras de seguridad**

* Se ha corregido un problema que se producía al eliminar la información de un perfil en cuarentena a través de una solicitud de privacidad, la cual eliminaba todos los datos excepto la dirección de correo electrónico de la lista de cuarentena.
* Se ha mejorado la seguridad para la protección contra inyecciones en encabezados de correo electrónico.
* Se ha mejorado la seguridad para la protección contra ataques SSRF donde se pueden utilizar expresiones xtk (HTML de correo electrónico, contenido de texto y asunto, contenido de SMS y notificaciones push).

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que impedía el seguimiento de los vínculos de baja, suscripción y página de aterrizaje al insertarlos en un correo electrónico. (CAMP-37809)
* Se ha corregido un problema que podía provocar errores al crear un nuevo correo electrónico y seleccionar una plantilla. (CAMP-38000)
* Al editar un vínculo con el Diseñador de correo electrónico, ahora puede utilizar la opción **Subrayado de enlace**. Además, se ha agregado una propiedad **Target** con el valor predeterminado establecido en **None**. [Más información](../../designing/using/styles.md#about-styling-links)
* Se ha corregido un problema de color en los vínculos de los componentes de texto del cuerpo de un correo electrónico. (CAMP-37330)
* Se ha corregido un problema que impedía que se eliminaran los vínculos asociados al eliminar una imagen. (CAMP-37234)
* Se ha corregido un problema que impedía guardar las modificaciones en la configuración **Order** del contenido dinámico en una condición. (CAMP-36883)
* Se ha corregido un problema que se producía al buscar páginas de aterrizaje. La búsqueda se ha ampliado de los 50 primeros creados a toda la base de datos. (CAMP-36839)
* Se ha corregido un problema al guardar modificaciones en el remitente del correo electrónico en el **Desde: Campo Name**. (CAMP-36606)
* La advertencia de compatibilidad con componentes de carrusel se ha modificado para reflejar los clientes de correo electrónico admitidos.
* Se ha corregido un problema de visualización en dispositivos móviles. El atributo height ahora siempre se establece en &quot;altura: auto&quot; al agregar o cargar una imagen nueva en un correo electrónico. (CAMP-35497)
* Se ha corregido un problema que dejaba etiquetas meta y de estilo en el HTML al eliminar un fragmento de un componente de estructura. (CAMP-35390)
* Se ha corregido un problema con los fragmentos al actualizar contenido reutilizable. (CAMP-35186)
* Se ha corregido un problema que se producía al mostrar solo contenido condicional móvil en correos electrónicos. (CAMP-35155)
* Se ha corregido un problema que mostraba aleatoriamente espacios de no separación de ancho cero. (CAMP-35116)
* Se ha corregido un problema con la posición de los botones en el cuadro de diálogo **Guardar como fragmento**.
* Se ha corregido un problema con la vista previa al agregar una etiqueta HTML en un título de imagen y texto alternativo.
* Se ha corregido un problema al editar, en el Diseñador de correo electrónico, vínculos creados en correos electrónicos del editor heredado.
* Se ha corregido un problema que dejaba etiquetas de estilo duplicadas en el contenido.
* Se ha corregido un problema con el formato de fecha al insertar un campo de personalización en un correo electrónico.
* Se ha corregido un problema que se producía al cambiar del modo HTML al texto sin formato.
* Se ha corregido un problema que se producía al hacer clic en la opción de bloqueo y desbloqueo que añadía valores de margen en el panel de propiedades de estilo en línea.
* Se ha corregido un problema con el tamaño de la vista previa para móviles para un mejor procesamiento.
* Se ha corregido un problema con el tamaño de los botones en las plantillas y los fragmentos.
* Se ha corregido un problema con el tamaño de las imágenes al insertarlas en un componente de botón.

**Otros cambios**

* El intervalo de tiempo predeterminado para el cual se muestran los datos en las páginas KPI de envío y en la página Informes dinámicos se ha alineado para evitar discrepancias en los resultados de los informes. (CAMP-35148)
* Se ha añadido un mensaje de error en los registros cuando caduca el certificado de la aplicación.
* La previsualización del cálculo de carga útil ahora incluye un tamaño de campo personalizado para evitar errores de notificaciones push. (CAMP-35303)
* El nombre del **Rejects file** en la actividad **Load file** ahora se puede personalizar del mismo modo que en la actividad **File export**.
* Ahora se puede acceder a todas las entidades personalizadas que no están vinculadas a ninguna entidad predeterminada a través de la API .
* Se ha mejorado el rendimiento de la base de datos en recursos de gran tamaño.
* Se han aclarado las descripciones de algunos errores que se producen al enviar mensajes SMS. (CAMP-36558)
* Ahora aparece un mensaje de error al ejecutar la actividad **Scheduler** de un flujo de trabajo conectada a sí misma, ya sea directamente o a través de varias actividades, ya que esto podría provocar que el servidor de flujo de trabajo de la instancia se bloquee.
* Se han realizado mejoras para ayudar a solucionar los problemas de la mensajería transaccional: se ha cambiado el nombre del vínculo &quot;Datos&quot; a &quot;Últimos eventos transaccionales&quot; en la pantalla de configuración de eventos, ahora enumera los eventos recibidos ordenados en orden descendente. Además, se ha creado un nuevo estado de evento transaccional: &quot;targetingFailed&quot;. Cuando el módulo de mensajería transaccional no enriquece un vínculo que se utiliza para la segmentación de mensajes, el evento transaccional ahora estará en este nuevo estado (en lugar del estado &quot;routingFailed&quot;).
* Se han realizado mejoras en la interfaz al restringir el acceso de la página de aterrizaje a unidades geográficas u organizativas específicas. El propósito es advertir que la página de aterrizaje puede estar sujeta a condiciones de visibilidad: ahora es obligatorio seleccionar una unidad geográfica y organizativa al crear una página de aterrizaje. Ahora aparece un banner con información relacionada una vez seleccionada una unidad. Se ha aclarado el mensaje de error que se muestra al probar la página de aterrizaje.
* En las API de Campaign Standard, las claves personalizadas no se pueden modificar mediante una operación de PATCH si el valor de clave es diferente de la clave de origen o si utiliza su propia clave comercial como URI en lugar de la proporcionada por Adobe.
* El idioma &quot;Albanés - Macedonia&quot; ha sido agregado a la lista desplegable de idiomas preferidos. (CAMP-35396)

**Parches**

* Se ha corregido un problema que impedía que los informes programados se ordenaran o buscaran.
* Se ha corregido un problema con las reglas de Déclencheur que provocaba que las reglas Y y O se mezclaran.
* Se ha corregido un problema que mostraba la propiedad Móvil como Eliminada en Launch. (CAMP-35382)
* Se ha corregido un problema que impedía que las propiedades móviles de Launch de Adobe se sincronizaran en Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Se ha corregido un problema en el cual los mensajes push transaccionales fallaban cuando los eventos se enriquecieron con datos de perfil. (CAMP-34385)
* Se ha corregido un problema con las propiedades móviles que no se sincronizaban en varios entornos. (CAMP-37060)
* Se ha corregido un problema al seleccionar, en una notificación push, una plantilla con una fórmula de fecha de contacto. (CAMP-35300)
* Se ha corregido un problema que podría provocar que el servicio de envío de mensajes se bloqueara. (CAMP-35287)
* Se ha corregido un problema con los correos directos recurrentes que se definían todos con la fecha del primer evento. (CAMP-35139)
* Se ha corregido un problema con los recursos personalizados **Profiles** recién ampliados que no estaban disponibles para consultas. (CAMP-35119)
* Se ha corregido el modo **Repair database structure** para instancias con la configuración de uso compartido activada. (CAMP-35118)
* Se ha corregido un problema que provocaba un error de registro SQL al agregar datos acumulados en registros generales. (CAMP-35034)
* Se ha corregido un problema con las transiciones al crear una actividad **Segmentación**. (CAMP-35033)
* Se ha corregido un problema en la actividad **Query** que impedía que la función **encryption_aescbcDecrypt** descifrara la función **encryption_aescbcEncrypt**. (CAMP-34952)
* Se ha corregido un problema que podía impedir que los **Registros de seguimiento** se mostraran en los envíos. (CAMP-34855)
* Se ha corregido un problema que se producía al utilizar una fórmula de fecha personalizada **Send time optimization** , lo que podía impedir que se enviaran notificaciones push debido a errores con los datos adicionales del flujo de trabajo. (CAMP-30336)
* Se ha corregido un problema que podía impedir la publicación de recursos personalizados. (CAMP-37425)
* Se ha corregido un problema que impedía a los usuarios administradores modificar paquetes de importación.  (CAMP-37176)
* Se ha corregido un problema en flujos de trabajo que impedía que se enviaran pruebas si la actividad de envío estaba conectada a una actividad **Read audience** vacía. (CAMP-37164)
* Se ha corregido un problema que impedía importar recursos personalizados en un nuevo entorno. (CAMP-36506)
* Se ha corregido un problema en los informes de clics activos que podía provocar que los porcentajes se ocultaran en imágenes (CAMP-36407)
* Se ha corregido un problema que se producía al intentar exportar un campo de descripción de la entrega. (CAMP-35467)
* Se ha corregido un problema que podía dejar el estado de una entrega como &quot;Start pending&quot; a pesar de que la entrega había finalizado. (CAMP-35355)
* Se ha corregido un problema que impedía que se mostraran los registros de flujo de trabajo después de activarlos y, a continuación, deshabilitar los registros SQL.

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
   <td> <p>Para una personalización más profunda, la actividad de API externa permite introducir datos de sistemas externos en un flujo de trabajo mediante una llamada a la API de REST. Los extremos de REST pueden ser un sistema de administración de clientes, un extremo de REST de Adobe I/O Runtime o Adobe Experience Cloud (por ejemplo, plataforma de datos, Target, Analytics o Campaign).</p><p>Esta funcionalidad está actualmente en versión beta pública.</p><p>Para obtener más información, consulte la <a href="../../automating/using/external-api.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">videotutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Informe sobre el segmento de flujo de trabajo<br /> </td> 
   <td> <p>Esta función permite a los especialistas en marketing desglosar el rendimiento de envío por código de segmento. Al crear un flujo de trabajo y utilizar una actividad de segmentación para asignar segmentos a la población de entrega, estos segmentos ahora pueden entrar en el mismo envío. Esto le permite mostrar las estadísticas de aperturas/clics basadas en varios segmentos dentro de un solo envío.</p><p>Para obtener más información, consulte la <a href="../../reporting/using/creating-a-report-workflow-segment.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">videotutorial</a>.</p></td>
  </tr> 
 </tbody> 
</table>

**Mejoras de seguridad**

* Se ha corregido un problema de seguridad para evitar ataques de denegación de servicio (DoS) en solicitudes no válidas para obtener imágenes. (CAMP-33454)

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que añadía etiquetas de estilo HTML adicionales a una plantilla HTML cada vez que se agregaba un componente, lo que podía aumentar considerablemente el tamaño de la plantilla. (CAMP-34694)
* Se ha corregido un problema que podía impedir que algunas opciones de menú de la barra de herramientas superior derecha estuvieran disponibles. (CAMP-34577)
* Se ha corregido un problema que se producía cuando el bloque de contenido de la URL de la página espejo se insertaba en un contenido de correo electrónico. (CAMP-34779)
* Se ha corregido un problema que se producía al usar código JSPP en un correo electrónico, lo que dificultaba la edición del contenido. (CAMP-34574)
* Se ha corregido un problema que provocaba que las imágenes se truncaran en la parte superior cuando se les agregaba un hipervínculo. (CAMP-34382)
* Se ha corregido un problema de visualización al usar el Diseñador de correo electrónico con Firefox. (CAMP-34364)
* Se han corregido varios problemas que se producían con el modo Avanzado al definir contenido dinámico en un correo electrónico. (CAMP-34351, CAMP-34333, CAMP-34331)
* Se han corregido varios problemas que se producían con el editor de reglas de contenido dinámico (CAMP-34304, CAMP-34303).
* Se ha corregido un problema que podía impedir que el campo Vínculo se mostrara en el panel Configuración del Diseñador de correo electrónico (CAMP-33749).
* Se ha corregido un problema con el icono de YouTube que se superaba de tamaño en los correos electrónicos enviados. (CAMP-33726)
* Se ha corregido un problema de seguridad que hacía que el contenido de la página espejo se pudiera editar. (CAMP-33691)
* Se ha corregido un problema que rompía la salida HTML al usar el símbolo bueno que en el contenido dinámico. (CAMP-33688)
* Se ha corregido un problema que se producía al utilizar la opción Deshacer al editar texto en el Diseñador de correo electrónico. (CAMP-32565)
* Se ha corregido un problema que creaba etiquetas adicionales al deshacer estilos en lugar de eliminarlos. (CAMP-32359)
* Ahora puede definir si cada componente utilizado en un correo electrónico se mostrará solo en dispositivos de escritorio o solo en dispositivos móviles.
* Ahora puede establecer la anchura y la altura de un componente de contenido de Social .
* Se ha corregido un problema que impedía que el contenido dinámico antiguo del código fuente se eliminara después de eliminar ese contenido dinámico.
* Se ha corregido un problema que podía impedir que se actualizara el asunto de un correo electrónico después de modificarlo.
* Se ha corregido un problema que impedía que se seleccionara una estructura de columna n:n una vez colocada en el espacio de trabajo.
* Se ha corregido un problema que hacía que la miniatura del mensaje apareciera borrosa en el panel de correo electrónico.
* Se ha corregido un problema que impedía que el fondo se mostrara correctamente en los correos electrónicos recibidos en Outlook.
* Se han corregido algunos problemas de ordenación en la página de inicio del Diseñador de correo electrónico.
* Se ha corregido un problema que se producía al duplicar variantes al usar contenido dinámico.
* Se eliminaron algunos campos no deseados del panel Configuración del Diseñador de correo electrónico .

**Otras mejoras**

* A través de la integración con Adobe Experience Platform Location Services, Adobe Campaign ahora es compatible para enviar mensajes de marketing basados en la ubicación a los suscriptores de la aplicación móvil mediante el SDK de Experience Platform. Para obtener más información, consulte la [documentación detallada](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md).
* La función de informes se ha mejorado para mejorar la experiencia. Para utilizar esta función, debe aceptar el Acuerdo de uso de informes dinámicos. Para obtener más información, consulte la [documentación detallada](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
* En los flujos de trabajo, se ha añadido una nueva opción para previsualizar las siguientes diez ejecuciones de un flujo de trabajo. Para obtener más información, consulte la [documentación detallada](../../automating/using/scheduler.md).
* En la actividad Planificador , una nueva opción le permite seleccionar un día específico de una semana específica para los envíos mensuales. Para obtener más información, consulte la [documentación detallada](../../automating/using/scheduler.md).
* Al crear envíos recurrentes sin periodo de acumulación, el panel de envío ahora le permite solicitar confirmación antes de realizar la entrega. Para obtener más información, consulte la [documentación detallada](../../sending/using/confirming-the-send.md).
* Ahora puede personalizar la etiqueta de una entrega con variables de evento que se han declarado en la actividad de señal externa del flujo de trabajo. Para obtener más información, consulte la [documentación detallada](../../automating/using/calling-a-workflow-with-external-parameters.md).
* La consulta de eliminación del RGPD se ha mejorado para un mejor rendimiento. (CAMP-33504)
* La opción &quot;ftp&quot; se ha eliminado de la interfaz de configuración de cuentas externas. (CAMP-34472)
* Ahora puede activar y desactivar la opción del modo de prueba SMTP para cada mensaje de correo electrónico. Para obtener más información, consulte la [documentación detallada](../../administration/using/configuring-email-channel.md#smtp-test-mode). (CAMP-34602)

**Otros cambios**

* Se ha añadido una advertencia en la interfaz de propiedades de entrega. Especifica que los envíos se preparan en función de su periodo de acumulación y, a continuación, para llamar al flujo de trabajo varias veces al día, debe asegurarse de que no tengan ningún periodo. (CAMP-34393)
* Se ha añadido una advertencia en las pantallas de configuración de recursos personalizadas. Se recomienda usar un máximo de 30 caracteres para los ID de recursos personalizados. Esto también se aplica a los campos de recursos personalizados, las claves, los índices y los enlaces.
* Ahora aparece un mensaje al intentar eliminar un mensaje transaccional que utiliza una página de aterrizaje como mensaje de confirmación.
* Ahora aparece una advertencia en los registros de flujos de trabajo cuando una actividad ha estado ejecutándose durante más de 6 horas. Esto no se aplica a las actividades de notificaciones push, entrega, señal, inicio, fin, ramificación , AND-Joint, Schedule y Wait .
* Ahora aparece una advertencia en los registros de flujos de trabajo cuando se alcanza el número máximo de flujos de trabajo que se ejecutan simultáneamente.
* Los flujos de trabajo que han estado en pausa o en estado de error durante más de 7 días ahora se detienen para consumir menos espacio en disco. La tarea de limpieza se muestra en los registros del flujo de trabajo.
* Al utilizar una actividad &quot;Transferir archivo&quot;, ahora se registra un error si el tamaño del archivo supera el espacio disponible en disco.
* La acción Redirigir a URL de destino ya no se puede seleccionar para el botón secundario de los mensajes en la aplicación.

**Parches**

* Se ha corregido un problema que podría provocar errores en las solicitudes de acceso de RGPD.
* Se ha corregido un problema que podía provocar que se descartaran déclencheur cuando se recibían varios déclencheur para un perfil único.
* Se ha corregido un problema que podría provocar un mensaje de error de publicación de recursos personalizados erróneo después del inicio de sesión.
* Se ha corregido un problema que mostraba una página en blanco al crear o ampliar un recurso personalizado.
* Se ha corregido un problema que impedía que una audiencia con appSubscriptionrcp como dimensión de segmentación estuviera disponible para segmentación en un envío móvil.
* Se ha corregido un error que impedía que las direcciones de correo electrónico de rechazos graves se pusieran en cuarentena. (CAMP-24587)
* Se ha corregido un problema que se producía al agregar una regla de tipología y luego eliminarla antes de guardar la tipología. (CAMP-32789)
* Se ha corregido un problema que podía impedir que se mostrara el contenido de la página de aterrizaje al deshabilitar el contenido dinámico. (CAMP-32924)
* Se ha corregido un problema con los envíos recurrentes que se producía al utilizar la personalización en los atributos de un envío principal. (CAMP-32983)
* Se ha corregido un problema en flujos de trabajo que impedía leer resultados de una transición que contenía datos de mensajes SMS entrantes. (CAMP-33134)
* Se ha corregido un problema con flujos de trabajo que se producía al combinar actividades de ramificación y exclusión para crear audiencias. (CAMP-33401)
* Se ha corregido un problema que podía impedir que se mostrara el contenido de la página espejo y que se enviaran mensajes de prueba para envíos recurrentes. (CAMP-33413)
* Se ha corregido un problema que provocaba un error al usar una actividad de unión entre perfiles y audiencias. Este problema se debía a una incompatibilidad de las claves de identificación en las transiciones de entrada. (CAMP-33713)
* Se ha corregido un problema en las actividades de prueba que impedía que la expresión &quot;recCount&quot; utilizara la sintaxis correcta al hacer doble clic en ella. (CAMP-33756)
* Se ha corregido un problema que podría provocar un mensaje de error al abrir los registros de flujo de trabajo técnico de facturación . (CAMP-34313)
* Se ha corregido un problema en las páginas de aterrizaje que se podía producir al configurar campos de casilla de verificación con suscripciones. (CAMP-34369)
* Se ha corregido un problema que se producía al configurar una lista y al agregarle el campo &quot;icono&quot;. (CAMP-34585)
* Se ha corregido un problema que impedía utilizar los símbolos &quot;|&quot; y &quot;%&quot; como separadores de fecha y hora en las actividades de flujo de trabajo de Cargar archivo . (CAMP-34706)
* Se ha corregido un problema que se producía al usar condiciones de visibilidad con casillas de verificación en páginas de aterrizaje. (CAMP-34802)
* Se ha corregido un problema en la actividad Enrichment que impedía que los campos se mostraran en la pestaña &quot;Additional data&quot;, si la dimensión de filtrado estaba configurada en registros de seguimiento y la dimensión de destino en perfil.
* Se ha corregido un problema que provocaba un mensaje de error al exportar un recurso &quot;workflowTemplate&quot;.
* Se ha corregido un problema al crear un nuevo perfil, que impedía guardar el campo &quot;Código de país/región&quot; si se seleccionaba del cuadro de diálogo.
* Se han corregido varios problemas que se producían al usar la plantilla de importación de correo postal (updateQuarantinesDeliveryLogsDirectMail).
* Se ha corregido un problema relacionado con la integración de Assets on Demand.
* Se ha corregido un problema que se producía al ampliar la vista Cronología. (CAMP-33628)
* Se ha corregido un problema que impedía que las pruebas se enviaran instantáneamente para mensajes de correo electrónico con una fecha y hora programadas. (CAMP-33723)
* Se ha corregido un problema relacionado con la mensajería transaccional que generaba registros de error cuando un usuario cerraba la sesión. (CAMP-31698)
* Se ha corregido un error que se podía producir en entornos específicos al programar un mensaje de correo electrónico.
* Se ha corregido un problema que provocaba que fallara el flujo de trabajo Update delivery execution .
* Se ha corregido un problema de seguridad que rompía el contenido del correo electrónico cuando el asunto contenía varias líneas.


## Versión 19.2.7: julio de 2019 {#release-19-2-7---july-2019}

**Mejoras**

* La consulta de eliminación del RGPD se ha mejorado para un mejor rendimiento.
* Se ha corregido un problema que podría provocar bloqueos web después de la actualización a la versión 19.2. (CAMP-34862)
* Se ha corregido un problema que podía impedir que los usuarios que no eran administradores guardaran o programaran informes. (CAMP-31133)
* Se ha corregido un problema que se producía al usar &quot;|&quot; como separador de fechas en la actividad de flujo de trabajo Cargar archivo . (CAMP-34706)

## Versión 19.2.4: junio de 2019 {#release-19-2-4---june-2019}

**Diseñador de correos electrónicos**

* Se ha corregido un problema que impedía a los usuarios editar fragmentos cuando se utilizaban etiquetas de estilo vacías en el HTML. Esta es una corrección de seguimiento para CAMP-33778 en 19.2.3.

## Versión 19.2.3: junio de 2019 {#release-19-2-3---june-2019}

**Diseñador de correos electrónicos**

Se ha introducido una serie de mejoras y correcciones para optimizar los fragmentos en la versión 19.2. Los fragmentos recién creados funcionarán sin problemas. Los fragmentos creados anteriormente han quedado atenuados y deben migrarse al nuevo formato. Para ello, haga clic en cada fragmento y valide su migración al nuevo formato. Se recomienda probar algunos fragmentos antes de migrarlos todos.

* Se ha corregido un problema que impedía a los usuarios editar un fragmento después de desbloquearlo. Esto afectaba a los fragmentos existentes al actualizar a la versión 19.2. (CAMP-33778)
* Se ha corregido un problema que se producía al usar contenido dinámico. Se agregaron espacios adicionales en el HTML.

**Otras mejoras**

* Se ha corregido un problema que podía impedir que el envío de SMS se reanudara tras la desconexión del conector SMS.
* Se ha corregido un problema que podía cerrar las conexiones SMPP cuando TLS estaba habilitado.
* Se ha corregido un problema que podía cerrar las conexiones SMPP cuando TLS estaba habilitado.
* Se ha añadido la opción &quot;Launch_URL_Campaign&quot; en Campaign para administrar las propiedades de las aplicaciones móviles creadas con el SDK de Adobe Experience Platform Mobile.
* Se ha corregido un error que provocaba que la opción de entorno de espacio aislado no estuviera marcada después de cargar el certificado de una propiedad móvil recién creada y salir de la página de propiedades de la aplicación móvil.
* Se ha corregido un problema que impedía enriquecer el contenido de un mensaje transaccional con información del recurso de servicio. (CAMP-33707)
* Se ha corregido un problema en las páginas de aterrizaje de  de lista de bloqueados que se producía al intentar cancelar la suscripción de perfiles de un servicio.

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
   <td> <p>Para aumentar la eficacia de su trabajo como usuario administrador, puede supervisar fácilmente la capacidad y administrar la configuración de sus instancias (empezando por la administración de servidores SFTP).</p><p>Para obtener más información, consulte la <a href="https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/control-panel/control-panel-overview.html?lang=es">videotutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notificaciones locales<br /> </td> 
   <td> <p>Los mensajes de notificación locales permiten informar a los usuarios de cuándo hay nuevos datos disponibles en sus aplicaciones móviles, incluso sin tener acceso a Internet o sin la aplicación móvil que se ejecuta en primer plano. Las notificaciones locales se activan mediante una aplicación móvil en un momento concreto y según un evento.</p><p>Para obtener más información, consulte la <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">documentación detallada</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Mejora del flujo de trabajo: Añada una carga útil a la actividad de señal externa<br /> </td> 
   <td> <p>Inicie un flujo de trabajo con una carga útil cuando las condiciones definidas se cumplan correctamente desde otro flujo de trabajo o una llamada a la API de REST para integrarse con los sistemas externos. Esto también incluye una nueva actividad <strong>test</strong> donde puede ejecutar pruebas en esta funcionalidad.</p><p>Para obtener más información, consulte la <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/execution-activities/external-signal-activity.html">videotutorial</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Mejora de las páginas de aterrizaje: Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveche Google reCAPTCHA para evitar el spam en las páginas de aterrizaje sin que sus clientes tengan que realizar ninguna acción.</p><p>Para obtener más información, consulte la <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha">documentación detallada</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

**Mejoras de seguridad**

* Se ha corregido un posible problema de seguridad de secuestro de clics en el espacio de trabajo de informes.

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que se producía al duplicar fragmentos e intentar utilizarlos en el Diseñador de correo electrónico. (CAMP-33193)
* Se ha corregido un problema que creaba espacios no deseados al usar elementos en línea en la interfaz del Diseñador de correo electrónico. (CAMP-32163)
* Se ha corregido un problema que eliminaba algunos atributos de etiqueta HTML adicionales añadidos por el usuario después de guardar contenido de correo electrónico en el Diseñador de correo electrónico. (CAMP-32162)
* Se ha corregido un problema que mostraba una etiqueta de Microsoft Office en el modo HTML del Diseñador de correo electrónico incluso después de quitarla. (CAMP-32141)
* Si ha creado un correo electrónico con una versión anterior del Diseñador de correo electrónico, al abrir este contenido de correo electrónico, una ventana emergente ahora solicita al usuario que actualice a la versión más reciente. (CAMP-31529)
* Se ha corregido un problema que podía distorsionar imágenes de un correo electrónico creado con el Diseñador de correo electrónico cuando se enviaba a algunos clientes de mensajería. (CAMP-31407)
* Se ha corregido un problema que impedía que algunos elementos, como listas o botones, se mostraran correctamente en modo de texto sin formato al crearlos en modo HTML. (CAMP-32582, CAMP-32542)
* Se ha corregido un problema que impedía mostrar más de 50 unidades organizativas en una plantilla de contenido o propiedades de fragmento. (CAMP-32932)
* Se ha corregido un problema con el color de fondo de la ventanilla móvil al recibir un correo electrónico creado con el Diseñador de correo electrónico en Outlook. (CAMP-31402)
* Se ha corregido un problema que podía impedir que el contenido del correo electrónico creado con el Diseñador de correo electrónico respondiera al abrirlo en Outlook. (CAMP-31400)
* Se ha corregido un problema que impedía que el contenido dinámico funcionara correctamente cuando se usaba en un asunto de correo electrónico. (CAMP-32837)
* Se ha corregido un problema relacionado con el asunto del correo electrónico que no se escapaba correctamente.
* Se ha corregido un problema que impedía que los fragmentos se cargaran en la paleta izquierda del Diseñador de correo electrónico.
* Se ha corregido un problema que impedía que los fragmentos creados durante la edición de contenido de correo electrónico se mostraran en la paleta izquierda del Diseñador de correo electrónico al actualizar la lista de fragmentos.
* Se han corregido varios problemas que se producían al usar contenido dinámico en un correo electrónico.
* Se ha corregido un problema que se producía con el selector de color al intentar definir un color mediante valores RGB.
* Se ha corregido un problema que impedía que la página espejo respondiera al recibir el correo electrónico en un móvil.

**Mejoras en la mensajería transaccional**

Se han añadido varias mejoras al canal de mensajería transaccional para optimizar el funcionamiento y el rendimiento.

* La duración del mensaje transaccional se ha ampliado para asegurarse de que todos los mensajes se envíen antes de que caduquen, especialmente cuando se realizan reintentos.
* El rendimiento de la mensajería transaccional se ha aumentado al distribuir la carga en diferentes subprocesos de envío.
* El proceso de mensajería transaccional se ha optimizado para poder iniciarse en análisis múltiples paralelos del mismo mensaje.
* Se ha corregido un problema que podría provocar un rendimiento y latencia incoherentes en las notificaciones push transaccionales.
* Se ha corregido un problema que mostraba una audiencia de destino incorrecta para las entregas de ejecución de mensajes transaccionales.
* Se ha corregido un problema que se producía al importar un paquete con una configuración de evento y el mensaje transaccional asociado. Para obtener más información, consulte la [documentación detallada](../../channels/using/getting-started-with-transactional-msg.md#exporting-and-importing-transactional-messages).
* Se ha corregido un problema que eliminaba los datos de recopilación de los perfiles de prueba creados para un mensaje transaccional que contenía listas de productos.

**Otros cambios**

* Se ha añadido una nueva opción a la cuenta externa de SMS. Permite limitar el número máximo de procesos MTA que envían SMS para controlar mejor el número de conexiones paralelas. Para obtener más información, consulte la nota técnica [SMS connector protocol and settings](https://helpx.adobe.com/es/campaign/kb/sms-connector-protocol-and-settings.html) .
* Al publicar un recurso con extensión de API, si la API ya se ha publicado, ahora se actualiza automáticamente cada vez que se vuelve a publicar. Anteriormente, esta acción era manual y, al no actualizar la API, se podía dañar el perfil o el recurso de servicio de esta API. Para obtener más información, consulte la [documentación detallada](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* La dimensión Código postal se ha eliminado de los informes dinámicos. En su lugar, se recomienda utilizar dimensiones de ciudad, país y estado.
* Se ha eliminado el déclencheur de evento &quot;Primer lanzamiento&quot; del ciclo vital para los mensajes en la aplicación.
* Al exportar un paquete con grupos de seguridad, ahora contiene las funciones asignadas a cada grupo. (CAMP-32960)
* En la actividad Cargar archivo , una nueva opción le permite comprobar que las columnas del archivo que está cargando coinciden con la definición de la columna. Para obtener más información, consulte la [documentación detallada](../../automating/using/load-file.md). (CAMP-32229)
* Ahora, los flujos de trabajo se pueden iniciar con una carga útil, lo que permite utilizar y compartir parámetros externos entre actividades dentro del flujo de trabajo. Para obtener más información, consulte la [documentación detallada](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP-29412 y CAMP-29413)
* Las API de Campaign Standard ahora permiten actualizar las unidades geográficas y organizativas de los perfiles mediante una carga útil. Para obtener más información, consulte la [documentación detallada](../../api/using/get-started-apis.md).
* Los mensajes de error cuando un objeto de la base de datos no es accesible se han aclarado para comprenderlo.
* En la actividad Extraer archivo , se han actualizado las capacidades de Javascript al definir el nombre de un archivo a exportar. Ahora solo está disponible la función formatDate para su uso en el campo Output . Para obtener más información, consulte la [documentación detallada](../../automating/using/extract-file.md).
* La generación de ID de secuencia automática se ha mejorado para los recursos personalizados. Las claves principales de los nuevos recursos personalizados ahora están en 64 bits de forma predeterminada.
* Se ha mejorado el modo de prueba de publicación de recursos personalizado. Ahora se muestra un mensaje de advertencia a los usuarios si la última publicación de recursos personalizados falla y no se corrige. Después de un error de publicación de recursos personalizados, puede volver a la última versión de trabajo. Para obtener más información, consulte la [documentación detallada](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Se ha añadido una nueva opción en la actividad Transferir archivo . Permite ordenar los archivos cuando se utiliza la acción File download , en modo SFTP. Para obtener más información, consulte la [documentación detallada](../../automating/using/transfer-file.md). (CAMP-33109)

**Parches**

* Se ha corregido un problema que podía provocar pérdidas de memoria en el MTA cuando se recargaba la configuración de SMS.
* Se ha corregido un problema que podía impedir la publicación de actualizaciones de la base de datos en modo de reparación.
* Se ha corregido un problema que provocaba discrepancias entre los informes de Adobe Analytics y los informes dinámicos de Adobe Campaign. (CAMP-25393)
* Se ha corregido un error que provocaba que fallara el flujo de trabajo de uso compartido de informes .
* Se ha corregido un error que impedía a los usuarios enviar mensajes en la aplicación solo con la URL de medios.
* Se ha corregido un problema que mostraba una aplicación móvil aunque su certificado no se hubiera cargado en la instancia.
* Se ha corregido un error que impedía que los campos de personalización funcionaran al usar la plantilla **Dirigirse a todos los usuarios de una aplicación móvil**.
* Se aprovisionaron nuevas instancias de Campaign Standard. (CAMP-32635 y CAMP-32344)
* Se ha corregido un error que impedía la personalización de la fórmula de fecha en un flujo de trabajo. (CAMP-30336)
* Se ha corregido un problema al definir una fórmula de fecha personalizada que podía impedir que los campos &quot;Datos adicionales&quot; y &quot;Código de segmento&quot; estuvieran disponibles en la lista desplegable. (CAMP-32383)
* Se ha corregido un problema que podía impedir que las actividades &quot;Transferir archivo&quot; y &quot;Extraer archivo&quot; encontraran los archivos rechazados si se cifraban. (CAMP-32377)
* Se ha corregido un problema en las API que podía impedir que el filtro lineCount procesara el recuento total exacto. (CAMP-31424)
* Se ha corregido un problema en las páginas de aterrizaje que podía impedir que los campos de entrada mostraran el valor actualizado una vez que se había modificado. (CAMP-31401)
* Se ha corregido un problema que podría provocar que una actividad de señal se active de forma inesperada.
* Se ha corregido un problema que podía impedir que se mostrara la vista previa del correo electrónico cuando la audiencia estaba vacía.
* Se ha corregido un problema en la actividad &quot;Extraer archivo&quot; que podía generar un archivo mientras se activaba la opción &quot;No generar un archivo si la transición entrante está vacía&quot;.
* Se ha corregido un problema que provocaba que el flujo de trabajo de entrega se desactivara si no finalizaba correctamente.
* Se ha corregido un problema que podía impedir que los usuarios guardaran o programaran informes. (CAMP-31133)

## Versión 19.1.3: marzo de 2019 {#release-19-1-3---march-2019}

**Mejoras en el diseñador de correo electrónico**

* Se ha corregido un problema que impedía modificar una plantilla después de guardarla.
* Se han corregido varios problemas al usar una plantilla creada anteriormente en un correo electrónico.
* Se ha corregido un problema que impedía que los componentes se ocultaran en plantillas importadas.

**Otras mejoras**

* Se ha corregido un error al ver las reglas de tipología. (CAMP-32059 y CAMP-31849)
* Se ha corregido un problema que impedía que se editaran las reglas de tipología. (CAMP-31750)
* Se ha corregido un problema con el proceso inMail que podía detenerse de forma inesperada. (CAMP-31238)

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
   <td> <p>Se han añadido varias mejoras a los informes de canal push para permitirle medir la participación del usuario de forma más intuitiva. Con esta versión, se amplía la lista de métricas de canal push a tres métricas diferentes: Impresiones, clics, aperturas (App Open) para ayudarle a medir y analizar la interacción de los usuarios con las notificaciones push de forma más eficaz. Además de esto, también estamos estandarizando la definición e implementación de estas métricas. El informe integrado de notificaciones push también se ha mejorado con visualizaciones y métricas de uso común.</p><p> Para obtener más información, consulte la <a href="../../reporting/using/push-notification-report.md">documentación detallada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Integración de Launch para aplicaciones móviles<br /> </td> 
   <td> <p>Esta versión contiene la integración de Adobe Campaign con las versiones GA de las extensiones Android e iOS para Adobe Campaign Standard en Adobe Experience Platform Launch y los SDK para móviles. Estas extensiones admiten la mensajería push, la mensajería en la aplicación y las actualizaciones de perfil de aplicaciones móviles.</p><p> Para obtener más información, consulte la <a href="https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html">documentación detallada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mensajería en la aplicación móvil<br /> </td> 
   <td> <p>Esta versión contiene la versión GA del canal In-App en Campaign. Desde el punto de vista funcional, las adiciones más importantes a la versión Beta son los informes dinámicos para el canal In-App y el protocolo de enlace seguro entre el SDK móvil y el MCIAS (Servicio de mensajería In-App de Marketing Cloud que sirve para las reglas del SDK). El protocolo de enlace seguro garantiza que los datos PII de los usuarios no caigan en manos malintencionadas, así como permite mantener la privacidad de los usuarios en un dispositivo compartido eliminando la caché de mensajes cada vez que el usuario cierra la sesión.</p><p>Para obtener más información, consulte la <a href="../../channels/using/about-in-app-messaging.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/communication-channels/mobile/in-app/in-app-message-overview.html">tutorial en la aplicación</a> dedicado.</p> </td> 
  </tr> 
  <tr> 
   <td> Mejoras en el flujo de trabajo<br /> </td> 
   <td> <p>Se han añadido las siguientes capacidades de flujo de trabajo:</p> 
    <ul> 
     <li> Ahora puede copiar y pegar actividades dentro de un flujo de trabajo u otro flujo de trabajo desde la misma instancia de Campaign. De este modo, puede duplicar fácilmente un flujo de trabajo completo o actividades específicas y conservar la configuración definida inicialmente. Para obtener más información, consulte la <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">documentación detallada</a>. (CAMP-20014) </li> 
     <li> Al utilizar la actividad <strong>Load file</strong>, ahora puede agregar una marca de tiempo al nombre del archivo que contiene los registros rechazados. Para obtener más información, consulte la <a href="../../automating/using/load-file.md#configuration">documentación detallada</a>. </li> 
     <li> <strong>Las actividades </strong> Consulta y  <strong></strong> Segmentación ahora permiten habilitar una transición saliente si las actividades no recuperan datos. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras de seguridad**

* El código HTML de la página de aterrizaje generado se ha actualizado para evitar la indexación del motor de búsqueda.

**Mejoras en el diseñador de correo electrónico**

* Ya está disponible un conjunto de cuatro plantillas de correo electrónico adaptables de primera categoría diseñadas por artistas de Behance.

   Para obtener más información, consulte la [documentación detallada](../../designing/using/using-reusable-content.md#content-templates).

* Nuestra nueva experiencia de incorporación le ayudará a iniciar la creación de correos electrónicos con mayor rapidez y le facilitará el acceso a la documentación y los tutoriales.

   Para obtener más información, consulte la [documentación detallada](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page).

* Ahora tiene la flexibilidad de configurar el número de columnas y el ancho según sus necesidades.

   Para obtener más información, consulte la [documentación detallada](../../designing/using/designing-from-scratch.md#defining-the-email-structure).

* Al editar en la vista móvil, puede ocultar ciertos componentes solo en la visualización móvil para un uso eficaz del espacio.

   Para obtener más información, consulte la [documentación detallada](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view).

* Ahora puede agregar canales sociales personalizados a la plantilla de correo electrónico, además de los que ya están disponibles.
* Se ha corregido un problema que impedía desplazarse hacia abajo en el menú de estructura al utilizar más de 18 estructuras. (CAMP-31173)
* Se ha corregido un problema que mostraba el encabezado previo sobre el contenido al reenviar un correo electrónico que contenía un encabezado previo enviado con Adobe Campaign. (CAMP-30736)
* Se ha corregido un problema que impedía actualizar la línea de asunto al hacer clic en la opción **Actualizar AEM contenido** después de modificar el asunto en Adobe Experience Manager. (CAMP-29984)
* Se han corregido varios problemas que evitaban el uso de imágenes dinámicas desde Adobe Target.
* Se ha corregido un problema que impedía actualizar la vista previa al recuperar contenido en el momento de la preparación si el contenido se había importado previamente de una dirección URL.
* El icono de YouTube se ha añadido al componente de contenido **Social**.
* Se ha añadido la vista **List** para los componentes de contenido y los fragmentos mostrados en la paleta Diseñador de correo electrónico.

**Otras mejoras**

* Adobe Campaign ahora es totalmente compatible con FCM para las aplicaciones SDK V4 y AEP SDK.
* Adobe Campaign admite notificaciones push para Wear OS de Android, así como watchOS de Apple.
* Los mensajes de advertencia y error que se pueden mostrar al navegar por la interfaz se han hecho más claros y fáciles de entender.
* Ahora puede agregar a las columnas de la lista de perfiles relacionadas con los campos de inclusión y exclusión (ya no se puede contactar con ...).
* La lista desplegable Zona horaria de la pantalla Creación de perfiles se ha movido de la sección Dirección a la sección superior de la interfaz.
* Ahora puede añadir separadores al configurar pantallas de recursos personalizadas, lo que le permite organizar los campos en categorías.

   Para obtener más información, consulte la [documentación detallada](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

**Otros cambios**

* Adobe Campaign y Adobe Experience Cloud dejarán de ser compatibles con Microsoft Internet Explorer 11 a partir de la primavera de 2019 y con la versión de Campaign Standard 19.2. Cambie a Microsoft Edge u otro explorador compatible. Consulte la página [Funciones obsoletas y eliminadas](../../rn/using/deprecated-features.md).
* Se ha cambiado el nombre del campo **Código de país** del recurso Perfil a **Código de país/región**.

**Parches**

* Se ha corregido un problema que impedía que se enviara el mensaje al agregar un perfil de prueba a un mensaje transaccional de correo electrónico. (CAMP-29854)
* Se ha corregido un problema que ralentizaba el envío de mensajes desde otros canales si el envío era bajo para un canal cuando el envío de mensajes desde todos los canales se activaba simultáneamente.
* Se ha corregido un problema que hacía que el MTA empezara a enviar mensajes SMS cuando la conexión de cuenta externa aún no estaba establecida.
* Se ha corregido un problema que se producía con la frecuencia de ejecución de la actividad Planificador y la hora de inicio. (CAMP-30745)
* Se ha corregido un problema que se podía producir con la generación de PKEY al utilizar recursos de perfil extendidos. (CAMP-30285)
* Se ha corregido un problema que podría producirse con las reglas de fatiga basadas en días del calendario. (CAMP-30136)
* Se ha corregido un problema que se podía producir al intentar acceder a recursos personalizados con nombres que terminaran con &quot;Base&quot;. (CAMP-30109)
* Se ha corregido un problema que impedía utilizar una llamada del PATCH para suscribir un perfil a un servicio. (CAMP-29728)
* Se ha corregido un problema que podía dañar un flujo de trabajo al importar un archivo XML a través de la actividad Cargar archivo . (CAMP-29208 y CAMP-28205)
* Se ha corregido un problema al vincular recursos personalizados que podía impedir que se generaran vínculos de cardinalidad inversa. (CAMP-30476)
* Se ha corregido un problema que impedía ampliar los registros de envío al usar solo código de segmento.
* Se ha corregido un problema que podía duplicar filas al utilizar la actividad de transferencia de archivos en flujos de trabajo.
* Se ha corregido un problema que impedía que los informes programados se enviaran a la hora elegida.
* Se ha corregido un problema que provocaba discrepancias entre los KPI &quot;To deliver&quot; y &quot;Sent&quot; para una entrega en la aplicación en un flujo de trabajo.
* Se ha corregido un problema que impedía que el seguimiento funcionara para un mensaje en la aplicación creado con un HTML personalizado.
* Se ha corregido un problema que impedía guardar el contenido de entrega en la aplicación al utilizarlo en un flujo de trabajo.
* Se ha corregido un problema que impedía que las aplicaciones móviles se mostraran para los administradores.
* Se ha corregido un problema que provocaba que fallara el flujo de trabajo técnico de Deliverability Update . (CAMP-26387)
* Se ha corregido un problema que provocaba discrepancias entre los perfiles segmentados al crear un envío en la aplicación y los que se mostraban en el panel de envío. (CAMP-28722)
* Se ha corregido un problema con la integración de Campaign y del servicio principal de recursos que podía impedir que se seleccionara un recurso compartido en un correo electrónico.

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
   <td> <p>El nuevo e intuitivo Email Designer (anteriormente conocido como Creative Designer) se ha trasladado a GA. Ahora es compatible con todas las funciones del antiguo editor de contenido, incluidas las siguientes:</p> 
    <ul> 
     <li> El uso de <a href="../../integrating/using/adding-target-dynamic-content.md">imágenes dinámicas de Adobe Target</a> </li> 
     <li> La capacidad de <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperar contenido de una URL automáticamente en tiempo de preparación</a> </li> 
     <li> <a href="../../designing/using/using-reusable-content.md#content-templates">plantillas de contenido predeterminadas</a> totalmente compatibles. </li> 
    </ul> 
    <p>Para obtener más información, consulte la <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/email-designer-overview.html">videotutorial</a>. A continuación se enumeran las mejoras y correcciones.</p><p>Como consecuencia, el antiguo editor de contenido de correo electrónico ya no se utiliza. Para obtener más información, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html">página</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listas de productos en correos electrónicos transaccionales<br /> </td> 
   <td> <p>Ahora puede hacer referencia a una o más colecciones de productos en un mensaje de correo electrónico transaccional. Por ejemplo, puede enviar automáticamente un correo electrónico de abandono del carro de compras que enumere todos los productos que había en el carro de compras del usuario, con una imagen, un precio y un vínculo a cada producto.</p><p>Para obtener más información, consulte la <a href="../../designing/using/using-product-listings.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/product-listings-in-transactional-email.html">videotutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Vista móvil en el Diseñador de correo electrónico<br /> </td> 
   <td> <p>Ahora puede cambiar a una vista móvil dedicada al editar contenido de correo electrónico. Esto le permite ajustar el diseño interactivo de un correo electrónico editando por separado todas las opciones de estilo para la visualización móvil, como la adaptación de márgenes, un tamaño de fuente más pequeño, colores de fondo diferentes, etc.</p><p> Para obtener más información, consulte la <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view">documentación detallada</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mejoras en la versión beta de la mensajería en la aplicación<br /> </td> 
   <td> <p>La función Mensajería en la aplicación beta se ha mejorado con las siguientes capacidades:</p> 
    <ul> 
     <li> El canal beta en la aplicación es compatible con el RGPD </li> 
     <li> Integración con las API de Analytics para rellenar listas desplegables de Déclencheur </li> 
     <li> Aspecto intuitivo y descripción de las plantillas de envío </li> 
     <li> Mejoras en la interfaz de creación desde el punto de vista de uso </li> 
    </ul> <p>Para obtener más información, consulte la <a href="../../channels/using/about-in-app-messaging.md">documentación detallada</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Ahora, una nueva opción de la actividad Load data permite aplicar una fase de posprocesamiento al archivo que contiene los registros rechazados (por ejemplo, compresión en formato zip). (CAMP-24521)
* Ahora, una nueva opción en la actividad Update data permite configurar el tamaño máximo del lote de datos que se va a cargar. (CAMP-28400)
* Se ha mejorado la selección de estado de dirección de los perfiles. Al seleccionar un país, la lista desplegable &quot;Estado&quot; ahora se actualiza automáticamente con los valores de estados relevantes. (CAMP-28874)
* Ahora, una nueva opción en la actividad Extraer archivo impide que se genere un archivo si la transición entrante está vacía. Esto evita la creación y carga de archivos vacíos en los servidores SFTP.
* Se ha mejorado el informe Resumen de entregas .
* Se ha enriquecido la lista de países disponibles al definir la dirección de un perfil. (CAMP-26707)
* Ahora aparece un mensaje de error al intentar importar un flujo de trabajo integrado.

**Diseñador de correos electrónicos**

* Se ha corregido un problema que habilitaba la capacidad de la unidad geográfica en una plantilla de correo electrónico o un fragmento de contenido creado con el Diseñador de correo electrónico, aunque esta capacidad estuviera deshabilitada en Adobe Campaign, por lo que la plantilla o el fragmento no estaba disponible al intentar acceder de nuevo. (CAMP-28174)
* Se ha corregido un problema que impedía guardar las condiciones de contenido dinámico al editar contenido con el Diseñador de correo electrónico. (CAMP-27905)
* Se ha corregido un problema que eliminaba la versión HTML del contenido del correo electrónico después de editar la versión de texto sin formato de un mensaje y de romper la sincronización HTML en el Diseñador de correo electrónico. (CAMP-28507)
* Se ha corregido un problema que impedía que se abriera la interfaz del Diseñador de correo electrónico al usar Internet Explorer 11. (CAMP-28273)
* Se ha corregido un problema que distorsionaba la renderización de Microsoft Outlook de la configuración de estilo aplicada a los botones con el Diseñador de correo electrónico.
* Se ha corregido un problema en el Diseñador de correo electrónico que hacía que se pudiera editar una dirección URL de un fragmento de contenido utilizado en un correo electrónico, lo cual no se esperaba, ya que el fragmento está bloqueado de forma predeterminada.
* Se ha corregido un problema que impedía que el componente divisor del Diseñador de correo electrónico se mostrara en Microsoft Office.
* Se ha corregido un problema que bloqueaba la página en determinados navegadores de Internet al ver contenido sincronizado de AEM con el editor de contenido de correo electrónico antiguo. (CAMP-29068)
* Se ha corregido un error que se producía al hacer clic en cualquier imagen de un correo electrónico al utilizar el editor de contenido de correo electrónico heredado. (CAMP-30424)
* Se ha corregido un problema que impedía que se mostraran los fragmentos recién creados al editar un correo electrónico con el Diseñador de correo electrónico. (CAMP-29928)
* Se ha corregido un problema que impedía que el texto del botón se mostrara correctamente en los correos electrónicos creados con el Diseñador de correo electrónico y recibidos con el cliente de correo web de Outlook.
* Ahora es posible crear mensajes transaccionales de perfil mediante el Diseñador de correo electrónico. (CAMP-28900)
* Se ha corregido un error en el Diseñador de correo electrónico que hacía que el contenido se pudiera editar al recuperar contenido de una URL automáticamente en el momento de la preparación, mientras que debería bloquearse.

**Parches**

* Se ha corregido un problema que mostraba registros de envío incorrectos en los informes dinámicos. (CAMP-23446)
* Se ha corregido un problema que podría afectar a los números del informe Resumen de devoluciones (CAMP-28703)
* Se ha corregido un problema con la integración de Campaign y del servicio principal de activos que podía impedir que se mostraran recursos al seleccionar **[!UICONTROL Image shared from Adobe Experience Cloud]** en un mensaje de correo electrónico (CAMP-28732).
* Se ha corregido un problema que impedía que se enviaran mensajes SMS que contenían el carácter &quot;oe&quot; aunque la transliteración estuviera autorizada en la cuenta externa de SMPP. (CAMP-29041)
* Se ha corregido un problema que podía mostrar registros duplicados al usar una actividad de segmentación en flujos de trabajo. (CAMP-28743)
* Se ha corregido un problema que impedía eliminar una de las asignaciones de valor en una columna de una actividad de flujo de trabajo. (CAMP-28708)
* Se ha corregido un problema en la actividad de transferencia de archivos, al utilizar caracteres comodín con la opción &quot;Comprobar si existe un archivo&quot;. (CAMP-28977)
* Se ha corregido un problema en la actividad Transferencia de archivos que se podía producir al actualizar la configuración de cuenta externa. (CAMP-28894)
* Se ha corregido un problema con los filtros personalizados en el editor de consultas al utilizar la condición &quot;El correo electrónico no está vacío&quot;. (CAMP-28741)
* Se ha corregido un problema que se podía producir al exportar tablas de recursos personalizadas con más de 100.000 registros. (CAMP-28150)
* Se ha corregido un problema que impedía eliminar mensajes transaccionales vinculados a déclencheur. (CAMP-28385)
* Se han eliminado contraseñas que se mostraban en algunos registros SMS.
* Se ha corregido un problema que provocaba que las conexiones al simulador SMPP fallaran debido a una contraseña vacía enviada por Adobe Campaign.
* Se ha corregido un problema que impedía enviar campañas cuando las conexiones SMS eran inestables.
* Se ha corregido un problema que mostraba los envíos eliminados en los informes dinámicos.
* Se ha corregido un problema que podía impedir la recuperación de datos adicionales de los registros de envío, los registros de seguimiento y las tablas de exclusión de registros al utilizar una actividad de Enriquecimiento en un flujo de trabajo.
* Se ha corregido un problema con las solicitudes de eliminación del RGPD que se podía producir al usar un tipo de vínculo &quot;N cardinality collection link&quot; y la opción &quot;Borrar el registro de destino implica eliminar las referencias de registros por el vínculo&quot;.
* Se ha corregido un problema con el uso compartido de informes.
* Se ha corregido un problema que podía provocar problemas de rendimiento al enviar una notificación push.
* Se ha corregido un problema por el que faltaban campos en los archivos de salida de correo postal.
* Se ha corregido un problema que permitía a los usuarios modificar los flujos de trabajo integrados.
* Se ha corregido un problema que se producía al crear una campaña basada en una plantilla de campaña, incluido un flujo de trabajo con una actividad de extracción configurada. (CAMP-29198)
* Se ha corregido un problema con la actividad de extracción de archivos que impedía utilizar la misma expresión para varios elementos. (CAMP-29182)
* Se ha corregido un problema, en el editor de consultas, con la condición de unión entre broadlog y el registro de seguimiento para rtEvent. (CAMP-28780)
* Se ha corregido un problema que impedía guardar las modificaciones de la opción de página de aterrizaje &quot;Acción específica&quot;. (CAMP-29422)
* Se ha corregido un problema que impedía exportar la carga útil de un evento en un flujo de trabajo. (CAMP-29029)
* Se ha corregido un problema que impedía que los números SMS de la  de lista de bloqueados se excluyeran en un mensaje SMS. (CAMP-28898)
* Se ha corregido un problema que podía impedir que se notificara a los proveedores de SMPP en caso de error al procesar los mensajes entrantes. (CAMP-29804)
* Se ha corregido un problema que permitía eliminar cuentas externas con entregas asociados. (CAMP-29738)
* El rendimiento del envío se ha mejorado y estabilizado para los mensajes SMS.
* Se ha corregido un problema que impedía que el carácter &quot;~&quot; se usara en un mensaje SMS. (CAMP-29172)
* Se ha corregido un problema en los envíos con la opción de optimización del tiempo de envío . (CAMP-29231)
