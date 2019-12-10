---
title: Notas de la versión
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
source-git-commit: 0ebe0ac4b9d9ba9c24e056cc7e2745e9f69e2004

---


# Notas de la versión{#release-notes}

Todas las versiones de 2019, con sus nuevas funciones y parches, se muestran en esta página. También se incluyen las actualizaciones del Panel de control.

Recursos adicionales:

* [Planificación de versiones de campaña](https://helpx.adobe.com/campaign/kb/acs-release-planning.html)
* [Últimas actualizaciones de documentación](../../rn/using/documentation-updates.md)
* [Funciones obsoletas y eliminadas](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)
* [Panel de control](https://helpx.adobe.com/campaign/kb/control-panel.html)
* Notas de la versión anteriores: [2018](../../rn/using/release-notes-2018.md), [2017](../../rn/using/release-notes-2017.md), [2015-2016](../../rn/using/release-notes-2015-2016.md)

## Versión 19.4: octubre de 2019 {#release-19-4---october-2019}

### What's new? {#what-s-new-5}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> California Consumer Privacy Act (CCPA)<br /> </td> 
   <td> <p>CCPA es la nueva ley de privacidad del Estado de California que armoniza y moderniza los requerimientos de protección de datos que entrarán en vigencia el 1 de enero de 2020. CCPA se aplica a los clientes de Adobe Campaign que tienen datos para los sujetos de datos que residen en California.</p>
   <p>Además de las funciones de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), aprovechamos esta oportunidad para incluir funciones adicionales que le ayudarán a facilitar su preparación para el CCPA:</p>
   <ul>
    <li>Derecho de acceso y derecho de eliminación: estamos aprovechando las capacidades agregadas para el RGPD. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#righttoaccess">Más información</a> </li>
    <li><p>Al crear una solicitud de privacidad, se ha agregado el tipo de regulación (GDPR o CCPA) en el servicio principal de privacidad. Este método es el que debe utilizar para todas las solicitudes de acceso y eliminación. El uso de la API de campaña y la interfaz para acceder y eliminar solicitudes está en desuso.  Consulte el artículo <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">Funciones</a>obsoletas y eliminadas.</p></li>
    <li>Se ha agregado un campo de exclusión <strong>de</strong> CCPA al recurso Perfiles para permitir a los usuarios de Adobe Campaign realizar un seguimiento de si un cliente ha optado por la venta de información personal. <a href="https://helpx.adobe.com/content/help/en/campaign/kb/acs-privacy.html#ccpa">Más información</a>.</li>
  </ul>
    <p>Consulte el vídeo de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html">procedimientos</a>.</p>
</td> 
  </tr> 
  <tr> 
   <td> Integración de Microsoft Dynamics 365 (GA)<br /> </td> 
   <td> 
    <p>Ya está disponible la integración entre Adobe Campaign Standard y Microsoft Dynamics 365. Podrá transferir los registros de contacto y de entidad personalizada de Dynamics 365 a Campaign y obtener los datos de eventos de correo electrónico de Campaign a Dynamics 365 para mejorar la alineación de ventas y marketing.</p>
    <p>Consulte la documentación <a href="https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html"></a> detallada para configurar esta integración y ver el vídeo de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/integrating/microsoft-dynamics365-connector/introduction.html">procedimientos</a>.</p>
  </td>
  </tr> 
 </tbody> 
</table>

### Mejoras {#improvements-3}

* La ventana emergente de consentimiento para los informes dinámicos se ha actualizado para incluir la integración de Adobe Campaign Standard y Microsoft Dynamics 365. Al aceptar los términos, los datos de perfil se incluirán al utilizar la integración de Adobe Campaign Standard/Microsoft Dynamics 365 y los informes dinámicos. [Más](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement) información (CAMP-29766)
* Se ha corregido un problema que mostraba fechas de contacto incorrectas al recibir alertas de entrega.
* Cuando se envía un evento de mensaje transaccional con un parámetro de contexto desconocido, ahora Campaign devuelve un mensaje de error "400" en lugar de "500". (CAMP-28632)
* Se ha agregado un nuevo segmento de prueba **de** exclusión en los informes dinámicos. Este segmento ahora está seleccionado de forma predeterminada para filtrar los informes. [Más información](../../reporting/using/list-of-components-.md#segments)
* La opción de caducidad **del** mensaje se ha agregado a la notificación push. Permite especificar una fecha de caducidad en la que Apple (APNS) o Android (FCM) dejarán de enviar el mensaje. [Más información](../../channels/using/customizing-a-push-notification.md#add-expiration-date)
* Se han realizado mejoras en la actividad de archivos **de** carga: los registros de flujo de trabajo se han aclarado y detallado sobre el error que se produce cuando un archivo no se carga. La transición de salida generada al activar la opción **Mantener los rechazados en un archivo** ha pasado a denominarse **Rechazados**. [Más información](../../automating/using/load-file.md#load-files)
* Se han agregado registros relacionados multilingües a los registros de envío para comprender mejor los errores de envío debido a la ausencia de idiomas en los archivos CSV cargados.

### Mejoras de seguridad {#security-enhancements-3}

* Se corrigió un problema que se producía al eliminar la información de un perfil en cuarentena mediante una solicitud de privacidad, el cual eliminaba todos los datos excepto la dirección de correo electrónico de la lista de cuarentena.
* Se ha mejorado la seguridad para la protección contra inyecciones en los encabezados de correo electrónico.
* Se ha mejorado la seguridad para la protección contra ataques SSRF donde se pueden utilizar expresiones xtk (correo electrónico HTML, contenido de texto y asunto, SMS y contenido de notificaciones push).

### Mejoras en el Diseñador de correo electrónico {#email-designer-enhancements-4}

* Al editar un vínculo con el diseñador de correo electrónico, ahora puede utilizar la opción **Subrayar vínculo** . Además, se ha agregado una propiedad **Target** con el valor predeterminado **Ninguno**. [Más información](../../designing/using/styles.md#about-styling-links)
* Se ha corregido un problema de color en los vínculos de los componentes de texto en el cuerpo de un correo electrónico. (CAMP-37330)
* Se ha corregido un problema que impedía que los vínculos asociados se eliminaran al eliminar una imagen. (CAMP-37234)
* Se ha corregido un problema que impedía guardar las modificaciones en la configuración de **pedido** de contenido dinámico en una condición. (CAMP-36883)
* Se corrigió un problema al buscar páginas de aterrizaje. La búsqueda se ha ampliado de los 50 primeros creados a toda la base de datos. (CAMP-36839)
* Se ha corregido un problema al guardar las modificaciones en el remitente de correo electrónico en el **formulario Desde: Campo de nombre** . (CAMP-36606)
* La advertencia de compatibilidad de componentes de carrusel se ha modificado para reflejar los clientes de correo electrónico admitidos.
* Se ha corregido un problema de visualización en dispositivos móviles. El atributo height ahora siempre se establece en "height: auto" al agregar o cargar una imagen nueva en un correo electrónico. (CAMP-35497)
* Se ha corregido un problema que dejaba etiquetas meta y estilo en el HTML al eliminar un fragmento de un componente de estructura. (CAMP-35390)
* Se ha corregido un problema con los fragmentos al actualizar contenido reutilizable. (CAMP-35186)
* Se ha corregido un problema al mostrar contenido condicional solo móvil en correos electrónicos. (CAMP-35155)
* Se ha corregido un problema que mostraba al azar espacios sin saltos de ancho cero. (CAMP-35116)
* Se ha corregido un problema con la posición de los botones en el cuadro de diálogo **Guardar como fragmento** .
* Se ha corregido un problema de vista previa al agregar una etiqueta HTML en un título de imagen y texto alternativo.
* Se corrigió un problema al editar, en el diseñador de correo electrónico, los vínculos creados en correos electrónicos del editor heredado.
* Se ha corregido un problema que dejaba etiquetas de estilo duplicadas en el contenido.
* Se ha corregido un problema con el formato de fecha al insertar un campo de personalización en un correo electrónico.
* Se ha corregido un problema que se producía al cambiar del modo HTML al texto sin formato.
* Se ha corregido un problema que se producía al hacer clic en la opción de bloqueo y desbloqueo, que añadía valores de margen en el panel de propiedades de estilo en línea.
* Se ha corregido un problema con el tamaño de la vista previa móvil para mejorar la representación.
* Se ha corregido un problema con el tamaño de los botones en plantillas y fragmentos.
* Se ha corregido un problema con el tamaño de las imágenes al insertarlas en un componente de botón.

### Otros cambios {#other-changes-3}

* El intervalo de tiempo predeterminado para el cual se muestran los datos en las páginas KPI de entrega y en la página Informes dinámicos se ha alineado para evitar discrepancias en los resultados de los informes. (CAMP-35148)
* Se agregó un mensaje de error en los registros cuando caducó el certificado de la aplicación.
* La vista previa del cálculo de carga útil ahora incluye el tamaño de campo personalizado para evitar errores de notificación push. (CAMP-35303)
* El nombre del archivo **** Rechaza de la actividad del archivo **** Cargar ahora se puede personalizar del mismo modo que en la actividad de exportación **de** archivos.
* Ahora se puede acceder a todas las entidades personalizadas que no están vinculadas a ninguna entidad lista para usar a través de la API.
* Se ha mejorado el rendimiento de la base de datos en recursos de gran tamaño.
* Se han aclarado las descripciones de algunos errores que se producen al enviar mensajes SMS. (CAMP-36558)
* Ahora aparece un mensaje de error al ejecutar una actividad de **Programador** de un flujo de trabajo que está conectada a sí mismo, ya sea directamente o a través de varias actividades, ya que esto podría provocar que el servidor de flujo de trabajo de la instancia se quedara atascado.
* Se han realizado mejoras para ayudar a solucionar los problemas de los mensajes transaccionales: el vínculo "Datos" ha pasado a llamarse "Últimos eventos transaccionales" en la pantalla de configuración de eventos, ahora enumera los eventos recibidos ordenados en orden descendente. Además, se ha creado un nuevo estado de evento de transacción: "targetingFailed". Cuando el módulo de mensajería transaccional no puede enriquecer un vínculo que se utiliza para la segmentación de mensajes, el evento transaccional estará ahora en este nuevo estado (en lugar del estado "RoutingFailed").
* Se han realizado mejoras en la interfaz al restringir el acceso de la página de aterrizaje a unidades geográficas o organizativas específicas. El propósito es advertir que la página de aterrizaje puede estar sujeta a condiciones de visibilidad: ahora es obligatoria la selección de una unidad geográfica y organizativa al crear una página de aterrizaje. Ahora se muestra una pancarta con información relacionada una vez seleccionada una unidad. Se ha aclarado el mensaje de error que se muestra al probar la página de aterrizaje.
* En las API de Campaign Standard, las claves personalizadas no se pueden modificar con una operación de PARCH si el valor clave es diferente de la clave de origen o si está utilizando su propia clave comercial como URI en lugar de la proporcionada por Adobe.
* El idioma "Albanés - Macedonia" ha sido agregado a la lista desplegable de idiomas preferidos. (CAMP-35396)

### Parches {#patches-4}

* Se ha corregido un problema que impedía que los informes programados se ordenaran o buscaran.
* Se ha corregido un problema con las reglas de activadores que hacía que las reglas Y y O se mezclaran.
* Se ha corregido un problema que mostraba la propiedad Móvil como Eliminado en Inicio. (CAMP-35382)
* Se ha corregido un problema que impedía que las propiedades móviles de Adobe Launch se sincronizaran en Adobe Campaign. (CAMP-35411, CAMP-35089, CAMP-35014, CAMP-35487)
* Se corrigió un problema en el cual los mensajes push transaccionales fallaban cuando los eventos se enriquecieron con datos de perfil. (CAMP-34385)
* Se ha corregido un problema con las propiedades móviles que no se sincronizaban en varios entornos. (CAMP-37060)
* Se ha corregido un problema al seleccionar, en una notificación push, una plantilla con una fórmula de fecha de contacto. (CAMP-35300)
* Se ha corregido un problema que podía provocar el bloqueo del servicio de envío de mensajes. (CAMP-35287)
* Se ha corregido un problema con los correos directos recurrentes que se definían todos con la fecha del primer evento. (CAMP-35139)
* Se ha corregido un problema con los recursos personalizados de **perfiles** recién ampliados que no estaban disponibles para consultas. (CAMP-35119)
* Se corrigió el modo de estructura **de base de datos de** Reparación para instancias con la configuración de uso compartido activada. (CAMP-35118)
* Se ha corregido un problema que provocaba un error de registro SQL al agregar datos agregados en los logs. (CAMP-35034)
* Se ha corregido un problema con las transiciones al crear una actividad **de segmentación** . (CAMP-35033)
* Se ha corregido un problema en la actividad de **consulta** que impedía que la función **crypt_aescbcDecrypt** descifrara la función **encrypt_aescbcEncrypt** . (CAMP-34952)
* Se ha corregido un problema que podía impedir que los registros **de** seguimiento se mostraran en las entregas. (CAMP-34855)
* Se ha corregido un problema que, al usar una fórmula de fecha personalizada de optimización **de tiempo de** envío, impedía que se enviaran notificaciones push debido a errores con los datos adicionales del flujo de trabajo. (CAMP-30336)
* Se ha corregido un problema que podía impedir la publicación de recursos personalizados. (CAMP-37425)
* Se ha corregido un problema que impedía a los usuarios administradores modificar los paquetes de importación.  (CAMP-37176)
* Se ha corregido un problema en los flujos de trabajo que impedía que se enviaran pruebas si la actividad de entrega estaba conectada a una actividad de audiencia **de** lectura vacía. (CAMP-37164)
* Se ha corregido un problema que impedía importar recursos personalizados en un nuevo entorno. (CAMP-36506)
* Se ha corregido un problema en los informes de clics interactivos que podía hacer que los porcentajes se ocultaran en las imágenes (CAMP-36407)
* Se ha corregido un problema que se producía al intentar exportar un campo de descripción de entrega. (CAMP-35467)
* Se ha corregido un problema que podía dejar el estado de un envío como "Iniciar pendiente" aunque el envío hubiera finalizado. (CAMP-35355)
* Se ha corregido un problema que impedía que se mostraran los registros de flujo de trabajo después de habilitarlos y, a continuación, se desactivaran los registros SQL.

## Actualización del Panel de control - Agosto de 2019 {#controlpanel-update---august-2019}

### What's new? {#what-s-new-4}

Hemos agregado nuevas funciones para que los usuarios administradores reciban notificaciones antes de que caduquen los certificados SSL para sus dominios. Para obtener más información, consulte la documentación [](https://helpx.adobe.com/campaign/kb/control-panel-subdomains-certificates.html)detallada.

Además, los usuarios administradores ahora pueden eliminar las claves SSH agregadas para acceder a los servidores SFTP.

Tenga en cuenta que el Panel de control solo está disponible para clientes alojados en AWS. Estas actualizaciones estarán disponibles el 26 de agosto.

## Versión 19.3: julio de 2019 {#release-19-3---july-2019}

### What's new? {#what-s-new-3}

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
   <td> <p>Para una personalización más profunda, la actividad de API externa le permite incorporar datos de sistemas externos a un flujo de trabajo mediante una llamada de API de REST. Los extremos REST pueden ser un sistema de administración de clientes, Adobe I/O Runtime o Adobe Experience Cloud REST (por ejemplo, plataforma de datos, Target, Analytics, Campaign).</p><p>Esta capacidad está actualmente en versión beta pública.</p><p>Para obtener más información, consulte la documentación <a href="../../automating/using/external-api.md"></a> detallada y el vídeo de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html">procedimientos</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Informe sobre el segmento de flujo de trabajo<br /> </td> 
   <td> <p>Esta función permite a los especialistas en marketing desglosar el rendimiento de la entrega por código de segmento. Al crear un flujo de trabajo y utilizar una actividad de segmentación para asignar segmentos a la población de envío, estos segmentos ahora pueden ir al mismo envío. Esto le permite mostrar las estadísticas de aperturas/clics en base a varios segmentos dentro de una sola entrega.</p><p>Para obtener más información, consulte la documentación <a href="../../reporting/using/creating-a-report-workflow-segment.md"></a> detallada y el vídeo de <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/reporting/report-on-workflow-segments.html">procedimientos</a>.</p></td>
  </tr> 
 </tbody> 
</table>

### Mejoras de seguridad {#security-enhancements-2}

* Se ha corregido un problema de seguridad para evitar ataques de denegación de servicio (DoS) en solicitudes no válidas para obtener imágenes. (CAMP-33454)

### Mejoras en el Diseñador de correo electrónico {#email-designer-enhancements-3}

* Se ha corregido un problema que agregaba etiquetas de estilo HTML adicionales a una plantilla HTML cada vez que se añadía un componente, lo que podía aumentar considerablemente el tamaño de la plantilla. (CAMP-34694)
* Se ha corregido un problema que podía impedir que algunas opciones de menú de la barra de herramientas superior derecha estuvieran disponibles. (CAMP-34577)
* Se ha corregido un problema que se producía cuando se insertaba el bloque de contenido de la URL de la página de reflejo en un contenido de correo electrónico. (CAMP-34779)
* Se ha corregido un problema que se producía al usar código JSPP en un correo electrónico, lo que dificultaba la edición del contenido. (CAMP-34574)
* Se ha corregido un problema que provocaba que las imágenes se truncaran en la parte superior cuando se les agregaba un hipervínculo. (CAMP-34382)
* Se corrigió un problema de visualización al usar el Diseñador de correo electrónico con Firefox. (CAMP-34364)
* Se han corregido varios problemas que se producían con el modo Avanzado al definir contenido dinámico en un correo electrónico. (CAMP-34351, CAMP-34333, CAMP-34331)
* Se han corregido varios problemas que se producían con el editor de reglas de contenido dinámico (CAMP-34304, CAMP-34303).
* Se ha corregido un problema que podía impedir que el campo Vínculo se mostrara en el panel Configuración del diseñador de correo electrónico (CAMP-33749).
* Se ha corregido un problema con el icono de YouTube que se superponía en los correos electrónicos enviados. (CAMP-33726)
* Se ha corregido un problema de seguridad que hacía que el contenido de la página reflejada fuera editable. (CAMP-33691)
* Se ha corregido un problema que rompía la salida HTML al usar el símbolo mayor que en el contenido dinámico. (CAMP-33688)
* Se ha corregido un problema que se producía al utilizar la opción Deshacer al editar texto en el Diseñador de correo electrónico. (CAMP-32565)
* Se ha corregido un problema que creaba etiquetas adicionales al deshacer estilos en lugar de eliminarlos. (CAMP-32359)
* Ahora puede definir si cada componente utilizado en un correo electrónico se mostrará solo en dispositivos de escritorio o solo en dispositivos móviles.
* Ahora puede definir la anchura y la altura de un componente de contenido de Social.
* Se ha corregido un problema que impedía que el contenido dinámico antiguo del código fuente se eliminara después de eliminar dicho contenido dinámico.
* Se ha corregido un problema que podía impedir que se actualizara el asunto de un correo electrónico después de modificarlo.
* Se ha corregido un problema que impedía que una estructura de columna n:n se seleccionara una vez colocada en el espacio de trabajo.
* Se ha corregido un problema que hacía que la miniatura del mensaje apareciera borrosa en el tablero de correo electrónico.
* Se ha corregido un problema que impedía que el fondo se mostrara correctamente en los correos electrónicos recibidos en Outlook.
* Se corrigieron algunos problemas de ordenación en la página principal de Email Designer.
* Se ha corregido un problema que se producía al duplicar variantes al usar contenido dinámico.
* Algunos campos no deseados se eliminaron del panel Configuración de Email Designer.

### Otras mejoras {#other-improvements-3}

* Gracias a la integración con los servicios de ubicación de la plataforma Adobe Experience Platform, Adobe Campaign ahora es compatible para enviar mensajes de marketing basados en la ubicación a los suscriptores de la aplicación móvil mediante el SDK de la plataforma de experiencia. Para obtener más información, consulte la documentación [](../../integrating/using/configuring-campaign-points-of-interest-data-integration.md)detallada.
* La función de informes se ha mejorado para mejorar la experiencia. Para utilizar esta función, debe aceptar el Acuerdo de uso de informes dinámicos. Para obtener más información sobre esto, consulte la documentación [](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement)detallada.
* En los flujos de trabajo, se ha agregado una nueva opción para obtener una vista previa de las diez ejecuciones siguientes de un flujo de trabajo. Para obtener más información sobre esto, consulte la documentación [](../../automating/using/scheduler.md)detallada.
* En la actividad Programador, una nueva opción le permite seleccionar un día específico de una semana específica para los envíos mensuales. Para obtener más información sobre esto, consulte la documentación [](../../automating/using/scheduler.md)detallada.
* Al crear entregas recurrentes sin período de agregación, el panel de envío le permite solicitar confirmación antes de enviar la entrega. Para obtener más información sobre esto, consulte la documentación [](../../sending/using/confirming-the-send.md)detallada.
* Ahora puede personalizar una etiqueta de entrega con variables de evento que se han declarado en la actividad de señal externa del flujo de trabajo. Para obtener más información sobre esto, consulte la documentación [](../../automating/using/calling-a-workflow-with-external-parameters.md)detallada.
* Se ha mejorado la consulta de eliminación del RGPD para mejorar el rendimiento. (CAMP-33504)
* La opción "ftp" se ha eliminado de la interfaz de configuración de cuenta externa. (CAMP-34472)
* Ahora puede activar y desactivar la opción de modo de prueba SMTP para cada mensaje de correo electrónico. Para obtener más información sobre esto, consulte la documentación [](../../administration/using/configuring-email-channel.md#smtp-test-mode)detallada. (CAMP-34602)

### Otros cambios {#other-changes-2}

* Se agregó una advertencia en la interfaz de propiedades de entrega. Especifica que los envíos se preparan en función de su período de agregación y, si desea llamar al flujo de trabajo varias veces al día, debe asegurarse de que no tengan ningún período. (CAMP-34393)
* Se ha agregado una advertencia en las pantallas de configuración de recursos personalizadas. Se recomienda usar un máximo de 30 caracteres para los ID de recursos personalizados. Esto también se aplica a campos de recursos personalizados, claves, índices y vínculos.
* Ahora aparece un mensaje al intentar eliminar un mensaje transaccional que utiliza una página de aterrizaje como mensaje de confirmación.
* Ahora aparece una advertencia en los registros de flujos de trabajo cuando una actividad se ha estado ejecutando durante más de 6 horas. Esto no se aplica a las actividades de notificación push, envío, señal, inicio, fin, tenedor y unión, programación y espera.
* Ahora aparece una advertencia en los registros de flujos de trabajo cuando se alcanza el número máximo de flujos de trabajo que se ejecutan simultáneamente.
* Los flujos de trabajo que han estado en pausa o en estado de error durante más de 7 días ahora se detienen para consumir menos espacio en disco. La tarea de limpieza se muestra en los registros del flujo de trabajo.
* Al utilizar una actividad de "Transferir archivo", ahora se registra un error si el tamaño del archivo supera el espacio disponible en el disco.
* La acción Redirigir a la URL de destino ya no se puede seleccionar para el botón secundario en los mensajes en la aplicación.

### Parches {#patches-3}

* Se ha corregido un problema que podía provocar errores en las solicitudes de acceso de RGPD.
* Se ha corregido un problema que podía hacer que se descartaran los activadores cuando se recibían varios activadores para un perfil único.
* Se ha corregido un problema que podía generar un mensaje de error de publicación de recursos personalizados erróneo después del inicio de sesión.
* Se ha corregido un problema que mostraba una página en blanco al crear o ampliar un recurso personalizado.
* Se ha corregido un problema que impedía que una audiencia con appSubscriptionrcp como dimensión de segmentación estuviera disponible para segmentación en una entrega móvil.
* Se ha corregido un error que impedía que las direcciones de correo electrónico de devolución en bruto se pusieran en cuarentena. (CAMP-24587)
* Se ha corregido un problema que se producía al agregar una regla de tipología y, a continuación, eliminarla antes de guardar la tipología. (CAMP-32789)
* Se ha corregido un problema que podía impedir que se mostrara el contenido de la página de aterrizaje al desactivar el contenido dinámico. (CAMP-32924)
* Se ha corregido un problema con los envíos recurrentes que se producía al utilizar la personalización en los atributos de una entrega maestra. (CAMP-32983)
* Se ha corregido un problema en los flujos de trabajo que impedía leer los resultados de una transición que contenía datos de mensajes SMS entrantes. (CAMP-33134)
* Se ha corregido un problema en los flujos de trabajo que se producía al combinar actividades de exclusión y de tenedor para crear audiencias. (CAMP-33401)
* Se ha corregido un problema que podía impedir que se mostrara el contenido de la página de reflejo y que se enviaran mensajes de prueba para envíos recurrentes. (CAMP-33413)
* Se ha corregido un problema que provocaba un error al usar una actividad de Unión entre perfiles y audiencias. Este problema se debía a una incompatibilidad de las claves de identificación en las transiciones de entrada. (CAMP-33713)
* Se ha corregido un problema en las actividades de prueba que impedía que la expresión "recCount" utilizara la sintaxis correcta al hacer doble clic en ella. (CAMP-33756)
* Se ha corregido un problema que podía generar un mensaje de error al abrir los registros del flujo de trabajo técnico de facturación. (CAMP-34313)
* Se ha corregido un problema en las páginas de aterrizaje que se producía al configurar campos de casilla de verificación con suscripciones. (CAMP-34369)
* Se ha corregido un problema que se producía al configurar una lista y agregarle el campo "icono". (CAMP-34585)
* Se ha corregido un problema que impedía usar los símbolos "|" y "%" como separadores de fecha y hora en Cargar actividades de flujo de trabajo de archivos. (CAMP-34706)
* Se ha corregido un problema que se producía al usar condiciones de visibilidad con casillas de verificación en páginas de aterrizaje. (CAMP-34802)
* Se ha corregido un problema en la actividad Enriquecimiento que impedía que se mostraran campos en la ficha "Datos adicionales" si la dimensión de filtrado estaba configurada en registros de seguimiento y la dimensión de destino en el perfil.
* Se ha corregido un problema que provocaba un mensaje de error al exportar un recurso "workflowTemplate".
* Se corrigió un problema al crear un nuevo perfil, que impedía que el campo "Código de país o región" se guardara si se seleccionaba en el cuadro de diálogo.
* Se han corregido varios problemas que se producían al utilizar la plantilla de importación de correo directo (updateQuarantinesDeliveryLogsDirectMail).
* Se ha corregido un problema relacionado con la integración de Recursos On Demand.
* Se ha corregido un problema que se producía al acercar la vista Línea de tiempo. (CAMP-33628)
* Se ha corregido un problema que impedía que las pruebas se enviaran instantáneamente para mensajes de correo electrónico con una fecha y hora programadas. (CAMP-33723)
* Se ha corregido un problema relacionado con la mensajería transaccional que generaba registros de errores cuando un usuario cerraba la sesión. (CAMP-31698)
* Se ha corregido un error que podía producirse en entornos específicos al programar un mensaje de correo electrónico.
* Se corrigió un problema que ocasionaba que fallara el flujo de trabajo de ejecución de envío de actualización.
* Se ha corregido un problema de seguridad que rompía el contenido del correo electrónico cuando el asunto contenía varias líneas.


## Versión 19.2.7: julio de 2019 {#release-19-2-7---july-2019}

### Mejoras {#improvements-2}

* Se ha mejorado la consulta de eliminación del RGPD para mejorar el rendimiento.
* Se ha corregido un problema que podía provocar bloqueos web tras la actualización a la versión 19.2. (CAMP-34862)
* Se ha corregido un problema que podía impedir que los usuarios que no eran administradores guardaran o programaran informes. (CAMP-31133)
* Se ha corregido un problema al usar "|" como separador de fechas en la actividad de flujo de trabajo de cargar archivo. (CAMP-34706)

## Versión 19.2.4: junio de 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* Se ha corregido un problema que impedía a los usuarios editar fragmentos cuando se utilizaban etiquetas de estilo vacías en el HTML. Esta es una corrección de seguimiento para CAMP-33778 en 19.2.3.

## Versión 19.2.3: junio de 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

Se ha introducido una serie de mejoras y correcciones para optimizar los fragmentos en la versión 19.2. Los fragmentos recién creados funcionarán sin problemas. Los fragmentos que se generaron anteriormente se han atenuado y deben migrarse al nuevo formato. Para ello, haga clic en cada fragmento y valide su migración al nuevo formato. Se recomienda probar algunos fragmentos antes de migrarlos todos.

* Se ha corregido un problema que impedía a los usuarios editar un fragmento después de desbloquearlo. Esto afectaba a los fragmentos existentes al actualizar a 19.2. (CAMP-33778)
* Se ha corregido un problema al usar contenido dinámico. Se agregaron espacios adicionales en el HTML.

### Otras mejoras {#other-improvements-2}

* Se ha corregido un problema que podía impedir que el envío de SMS se reanudara después de desconectar el conector de SMS.
* Se ha corregido un problema que podía cerrar las conexiones SMPP cuando TLS estaba habilitado.
* Se ha corregido un problema que podía cerrar las conexiones SMPP cuando TLS estaba habilitado.
* La opción "Launch_URL_Campaign" se ha agregado a Campaign para administrar las propiedades de las aplicaciones móviles creadas con el SDK de Adobe Experience Platform Mobile.
* Se ha corregido un error que provocaba que la opción de entorno de Simulador para pruebas se desactivara tras cargar el certificado de una propiedad móvil recién creada y salir de la página de propiedades de la aplicación móvil.
* Se ha corregido un problema que impedía enriquecer el contenido de un mensaje transaccional con información del recurso de servicio. (CAMP-33707)
* Se ha corregido un problema en las páginas de aterrizaje de lista negra que se producía al intentar cancelar la suscripción de perfiles de un servicio.

## Versión 19.2: mayo de 2019 {#release-19-2---may-2019}

### What's new? {#what-s-new-}

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
   <td> <p>Para ayudar a aumentar la eficacia de su trabajo como usuario administrador, puede supervisar fácilmente la capacidad y administrar la configuración de sus instancias (empezando con la administración de servidores SFTP).</p><p>Para obtener más información, consulte la documentación <a href="https://helpx.adobe.com/campaign/kb/control-panel.html"></a> detallada y el vídeo de <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">procedimientos</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Notificaciones locales<br /> </td> 
   <td> <p>Los mensajes de notificación local permiten informar a los usuarios cuando hay nuevos datos disponibles en sus aplicaciones móviles, incluso sin tener acceso a Internet o a la aplicación móvil que se ejecuta en primer plano. Las notificaciones locales se activan mediante una aplicación móvil en un momento determinado y en función de un evento.</p><p>Para obtener más información, consulte la documentación <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type"></a>detallada.</p></td> 
  </tr> 
  <tr> 
   <td> Mejora del flujo de trabajo: agregue una carga útil a la actividad de señal externa<br /> </td> 
   <td> <p>Inicie un flujo de trabajo con una carga útil cuando las condiciones definidas se cumplan correctamente desde otro flujo de trabajo o una llamada de API REST para integrarse con sus sistemas externos. Esto también incluye una nueva actividad de <strong>prueba</strong> en la que puede ejecutar pruebas con esta funcionalidad.</p><p>Para obtener más información, consulte la documentación <a href="../../automating/using/calling-a-workflow-with-external-parameters.md"></a> detallada y el vídeo de <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">procedimientos</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Mejora de las páginas de aterrizaje - Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveche el reCAPTCHA de Google para evitar el spam en las páginas de aterrizaje sin requerir ninguna acción por parte de sus clientes.</p><p>Para obtener más información, consulte la documentación <a href="../../channels/using/configuring-landing-page.md#setting-google-recaptcha"></a>detallada.</p></td> 
  </tr> 
 </tbody> 
</table>

### Mejoras de seguridad {#security-enhancements}

* Se ha corregido un posible problema de seguridad de secuestro de clics en el espacio de trabajo de informes.

### Mejoras en el Diseñador de correo electrónico {#email-designer-enhancements}

* Se ha corregido un problema que se producía al duplicar fragmentos e intentar utilizarlos en el Diseñador de correo electrónico. (CAMP-33193)
* Se ha corregido un problema que creaba espacios no deseados al usar elementos en línea en la interfaz de Email Designer. (CAMP-32163)
* Se ha corregido un problema que eliminaba algunos atributos de etiqueta HTML adicionales añadidos por el usuario después de guardar el contenido de correo electrónico en el Diseñador de correo electrónico. (CAMP-32162)
* Se ha corregido un problema que mostraba una etiqueta de Microsoft Office en el modo HTML de Designer de correo electrónico incluso después de eliminarla. (CAMP-32141)
* Si ha creado un correo electrónico con una versión anterior del Diseñador de correo electrónico, al abrir este contenido de correo electrónico, ahora se abre una ventana emergente que solicita al usuario que actualice a la versión más reciente. (CAMP-31529)
* Se ha corregido un problema que podía distorsionar imágenes de un correo electrónico creado con el Diseñador de correo electrónico cuando se enviaba a algunos clientes de mensajería. (CAMP-31407)
* Se ha corregido un problema que impedía que algunos elementos como listas o botones se mostraran correctamente en el modo de texto sin formato al crearlos en el modo HTML. (CAMP-32582, CAMP-32542)
* Se ha corregido un problema que impedía mostrar más de 50 unidades organizativas en una plantilla de contenido o propiedades de fragmento. (CAMP-32932)
* Se ha corregido un problema con el color de fondo de la ventanilla cuando se recibía un correo electrónico creado con el Diseñador de correo electrónico en Outlook. (CAMP-31402)
* Se ha corregido un problema que podía impedir que el contenido de correo electrónico creado con el Diseñador de correo electrónico respondiera al abrirse en Outlook. (CAMP-31400)
* Se ha corregido un problema que impedía que el contenido dinámico funcionara correctamente cuando se utilizaba en un asunto de correo electrónico. (CAMP-32837)
* Se ha corregido un problema relacionado con el asunto del correo electrónico que no se escapaba correctamente.
* Se ha corregido un problema que impedía que los fragmentos se cargaran en la paleta izquierda de Email Designer.
* Se ha corregido un problema que impedía que los fragmentos creados durante la edición de contenido de correo electrónico se mostraran en la paleta izquierda de Email Designer al actualizar la lista de fragmentos.
* Se han corregido varios problemas que se producían al usar contenido dinámico en un correo electrónico.
* Se ha corregido un problema que se producía con el selector de color al intentar definir un color mediante valores RGB.
* Se ha corregido un problema que impedía que la página reflejada respondiera al recibir el correo electrónico en un dispositivo móvil.

### Mejoras en la mensajería transaccional {#transactional-messaging-enhancements}

Se han añadido varias mejoras al canal de mensajería Transactional para optimizar el funcionamiento y el rendimiento.

* La duración del mensaje transaccional se ha ampliado para asegurarse de que todos los mensajes se envían antes de que caduquen, especialmente cuando se realizan reintentos.
* El rendimiento de la mensajería transaccional se ha incrementado mediante la distribución de la carga en diferentes subprocesos de envío.
* Se ha optimizado el proceso de mensajería transaccional para que pueda iniciarse en paralelo un análisis múltiple del mismo mensaje.
* Se ha corregido un problema que podía provocar un rendimiento y latencia incoherentes en las notificaciones push transaccionales.
* Se ha corregido un problema que mostraba una audiencia de destino incorrecta para las entregas de ejecución de mensajes transaccionales.
* Se ha corregido un problema que se producía al importar un paquete con una configuración de evento y el mensaje transaccional asociado. Para obtener más información sobre esto, consulte la documentación [](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages)detallada.
* Se ha corregido un problema que eliminaba los datos de recopilación de los perfiles de prueba creados para un mensaje transaccional que contenía listados de productos.

### Otros cambios {#other-changes}

* Se ha agregado una nueva opción a la cuenta externa de SMS. Permite limitar el número máximo de procesos MTA que envían SMS para controlar mejor el número de conexiones paralelas. Para obtener más información, consulte la nota técnica de protocolo y configuración [del conector](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) SMS.
* Al publicar un recurso con extensión API, si la API ya se ha publicado, ahora se actualiza automáticamente cada vez que se vuelve a publicar. Anteriormente, esta acción era manual y si no se actualizaba la API se podía romper el perfil o el recurso de servicio de esta API. Para obtener más información sobre esto, consulte la documentación [](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)detallada.
* La dimensión de código postal se ha eliminado de los informes dinámicos. En su lugar, se recomienda usar dimensiones de ciudad, país y estado.
* Se ha eliminado el activador del evento de ciclo de vida de "primer inicio" para los mensajes en la aplicación.
* Al exportar un paquete con grupos de seguridad, ahora contiene las funciones asignadas a cada grupo. (CAMP-32960)
* En la actividad Cargar archivo, una nueva opción le permite comprobar que las columnas del archivo que está cargando coinciden con la definición de la columna. Para obtener más información, consulte la documentación [](../../automating/using/load-file.md)detallada. (CAMP-32229)
* Ahora, los flujos de trabajo se pueden iniciar con una carga útil, lo que le permite utilizar y compartir parámetros externos entre actividades dentro del flujo de trabajo. Para obtener más información, consulte la documentación [](../../automating/using/calling-a-workflow-with-external-parameters.md)detallada. (CAMP-29412 y CAMP-29413)
* Las API de Campaign Standard ahora permiten actualizar las unidades geográficas y organizativas de los perfiles mediante una carga útil. Para obtener más información, consulte la documentación [](../../api/using/about-campaign-standard-apis.md)detallada.
* Los mensajes de error cuando no se puede acceder a un objeto de la base de datos se han aclarado para comprenderlos.
* En la actividad de archivos de extracción, las funciones de Javascript se han actualizado al definir el nombre de un archivo que se va a exportar. Ahora solo está disponible la función formatDate para su uso en el campo Salida. Para obtener más información, consulte la documentación [](../../automating/using/extract-file.md)detallada.
* Se ha mejorado la generación de ID de secuencia automática para los recursos personalizados. Las claves principales de los nuevos recursos personalizados están ahora en 64 bits de forma predeterminada.
* Se ha mejorado el modo de prueba de publicación de recursos personalizados. Ahora se muestra un mensaje de advertencia a los usuarios si falla la última publicación de recursos personalizados y no se corrige. Después de un error de publicación de recursos personalizados, puede revertir a la última versión de trabajo. Para obtener más información, consulte la documentación [](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource)detallada.
* Se agregó una nueva opción en la actividad Transferir archivo. Le permite ordenar los archivos al utilizar la acción de descarga de archivos, en modo SFTP. Para obtener más información, consulte la documentación [](../../automating/using/transfer-file.md)detallada. (CAMP-33109)

### Parches {#patches}

* Se ha corregido un problema que podía provocar una pérdida de memoria en el MTA cuando se recargaba la configuración de SMS.
* Se ha corregido un problema que podía impedir la publicación de actualizaciones de la base de datos en modo de reparación.
* Se ha corregido un problema que provocaba discrepancias entre los informes de Adobe Analytics y los informes dinámicos de Adobe Campaign. (CAMP-25393)
* Se corrigió un error que ocasionaba que fallara el flujo de trabajo de uso compartido de informes.
* Se ha corregido un error que impedía a los usuarios enviar mensajes en la aplicación solo con una URL de medios.
* Se ha corregido un problema que mostraba una aplicación móvil aunque su certificado no se hubiera cargado en la instancia.
* Se ha corregido un error que impedía que los campos de personalización funcionaran al usar **Target todos los usuarios de una plantilla de aplicación** móvil.
* Se aprovisionaron las nuevas instancias de Campaign Standard. (CAMP-32635 y CAMP-32344)
* Se ha corregido un error que impedía la personalización de la fórmula de fecha en un flujo de trabajo. (CAMP-30336)
* Se ha corregido un problema al definir una fórmula de fecha personalizada que podía impedir que los campos "Datos adicionales" y "Código de segmento" estuvieran disponibles en la lista desplegable. (CAMP-32383)
* Se ha corregido un problema que podía impedir que las actividades "Transferir archivo" y "Extraer archivo" encontraran los archivos rechazados si estaban cifrados. (CAMP-32377)
* Se ha corregido un problema en las API que podía impedir que el filtro lineCount procesara el recuento total exacto. (CAMP-31424)
* Se ha corregido un problema en las páginas de aterrizaje que impedía que los campos de entrada mostraran el valor actualizado una vez modificado. (CAMP-31401)
* Se ha corregido un problema que podía provocar que una actividad de señal se activara inesperadamente.
* Se ha corregido un problema que podía impedir que se mostrara la vista previa de correo electrónico cuando la audiencia estaba vacía.
* Se ha corregido un problema en la actividad "Extraer archivo" que podía generar un archivo mientras se activaba la opción "No generar un archivo si la transición de entrada está vacía".
* Se ha corregido un problema que provocaba que el flujo de trabajo de entregabilidad se desactivara si no finalizaba correctamente.
* Se ha corregido un problema que podía impedir que los usuarios guardaran o programaran informes. (CAMP-31133)

## Versión 19.1.3: marzo de 2019 {#release-19-1-3---march-2019}

### Mejoras en el Diseñador de correo electrónico {#email-designer-enhancements-1}

* Se ha corregido un problema que impedía que una plantilla se modificara después de guardarla.
* Se corrigieron varios problemas al usar una plantilla creada anteriormente en un correo electrónico.
* Se ha corregido un problema que impedía que los componentes se ocultaran en plantillas importadas.

### Otras mejoras {#other-improvements}

* Se corrigió un error al ver las reglas de tipología. (CAMP-32059 y CAMP-31849)
* Se ha corregido un problema que impedía que se editaran las reglas de tipología. (CAMP-31750)
* Se ha corregido un problema con el proceso de inMail que podía detenerse inesperadamente. (CAMP-31238)

## Versión 19.1: febrero de 2019 {#release-19-1---february-2019}

### What's new? {#what-s-new--1}

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
   <td> <p>Se han añadido varias mejoras a los informes de canal push para permitirle medir la participación del usuario de forma más intuitiva. Con esta versión, expandimos la lista de métricas de canal push a tres métricas diferentes: Impresiones, clics, aperturas (Apertura de la aplicación) para ayudarle a medir y analizar la interacción de los usuarios con las notificaciones push de forma más eficaz. Junto con esto, también estamos estandarizando la definición e implementación de estas métricas. El informe integrado de notificaciones Push también se ha mejorado con las visualizaciones y métricas más utilizadas.</p><p> Para obtener más información, consulte la documentación <a href="../../reporting/using/push-notification-report.md"></a>detallada.</p> </td> 
  </tr> 
  <tr> 
   <td> Iniciar la integración para aplicaciones móviles<br /> </td> 
   <td> <p>Esta versión contiene la integración de Adobe Campaign con las versiones de GA de las extensiones Android e iOS para Adobe Campaign Standard en Adobe Experience Platform Launch y los SDK para móviles. Estas extensiones admiten la mensajería push, la mensajería en la aplicación y las actualizaciones de perfil de la aplicación móvil.</p><p> Para obtener más información, consulte la documentación <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html"></a>detallada.</p> </td> 
  </tr> 
  <tr> 
   <td> Mensajería en la aplicación móvil<br /> </td> 
   <td> <p>Esta versión contiene la versión de GA del canal en la aplicación en Campaign. Desde un punto de vista funcional, las adiciones más notables a la versión beta son los informes dinámicos para el canal en la aplicación y el protocolo de enlace seguro entre el SDK móvil y MCIAS (servicio de mensajería en la aplicación de Marketing Cloud que sirve las reglas en la aplicación al SDK). El protocolo de enlace seguro garantiza que los datos de PII de los usuarios no caigan en manos malintencionadas, así como permite mantener la privacidad de los usuarios en un dispositivo compartido al eliminar la caché de mensajes cada vez que el usuario cierra la sesión.</p><p>Para obtener más información, consulte la documentación <a href="../../channels/using/about-in-app-messaging.md"></a> detallada y el tutorial <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">dedicado</a>en la aplicación.</p> </td> 
  </tr> 
  <tr> 
   <td> Mejoras en el flujo de trabajo<br /> </td> 
   <td> <p>Se han agregado las siguientes funciones de flujo de trabajo:</p> 
    <ul> 
     <li> Ahora puede copiar y pegar actividades dentro de un flujo de trabajo u otro flujo de trabajo desde la misma instancia de Campaign. De este modo, puede duplicar fácilmente un flujo de trabajo completo o actividades específicas y mantener la configuración definida inicialmente. Para obtener más información, consulte la documentación <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities"></a>detallada. (CAMP-2014) </li> 
     <li> Al utilizar la actividad <strong>Cargar archivo</strong> , ahora puede agregar una marca de hora al nombre del archivo que contiene los registros rechazados. Para obtener más información, consulte la documentación <a href="../../automating/using/load-file.md#configuration"></a>detallada. </li> 
     <li> <strong>Las actividades de consulta</strong> y <strong>segmentación</strong> ahora permiten activar una transición de salida si las actividades no recuperan datos. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Mejoras de seguridad {#security-enhancements-1}

* El código HTML de la página de aterrizaje generado se ha actualizado para evitar la indexación del motor de búsqueda.

### Mejoras en el Diseñador de correo electrónico {#email-designer-enhancements-2}

* Ya está disponible un conjunto de cuatro plantillas de correo electrónico adaptables de primera categoría diseñadas por artistas de Behance.

   Para obtener más información, consulte la documentación [](../../designing/using/using-reusable-content.md#content-templates)detallada.

* Nuestra nueva experiencia de integración le ayudará a iniciar la creación de correos electrónicos con mayor rapidez y le facilitará el acceso a la documentación y los tutoriales.

   Para obtener más información, consulte la documentación [](../../designing/using/overview.md#email-designer-home-page)detallada.

* Ahora tiene la flexibilidad de configurar el número de columnas y el ancho en función de sus necesidades.

   Para obtener más información, consulte la documentación [](../../designing/using/designing-from-scratch.md#defining-the-email-structure)detallada.

* Al editar en la vista móvil, puede ocultar determinados componentes solo en la pantalla móvil para un uso eficaz del espacio.

   Para obtener más información, consulte la documentación [](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)detallada.

* Ahora puede agregar canales sociales personalizados a la plantilla de correo electrónico además de los que ya están disponibles.
* Se ha corregido un problema que impedía desplazarse hacia abajo por el menú de estructura al usar más de 18 estructuras. (CAMP-31173)
* Se ha corregido un problema que mostraba el encabezado previo sobre el contenido al reenviar un correo electrónico que contenía un encabezado previo enviado con Adobe Campaign. (CAMP-30736)
* Se ha corregido un problema que impedía actualizar la línea de asunto al hacer clic en la opción **Actualizar contenido** de AEM después de modificar el asunto en Adobe Experience Manager. (CAMP-29984)
* Se han corregido varios problemas que evitaban el uso de imágenes dinámicas de Adobe Target.
* Se ha corregido un problema que impedía que la vista previa se actualizara al recuperar contenido en tiempo de preparación si el contenido se había importado previamente de una URL.
* El icono de YouTube se ha agregado al componente de contenido de **Social** .
* Se ha agregado la vista **Lista** para los componentes y fragmentos de contenido que se muestran en la paleta Diseñador de correo electrónico.

### Otras mejoras {#other-improvements-1}

* Adobe Campaign ahora es totalmente compatible con FCM para las aplicaciones SDK V4 y AEP.
* Adobe Campaign admite notificaciones push en Wear OS por Android, así como watchOS por Apple.
* Los mensajes de advertencia y error que se pueden mostrar al navegar en la interfaz se han aclarado y facilitado la comprensión.
* Ahora puede agregar a las columnas de la lista de perfiles relacionadas con los campos de inclusión y exclusión ("Ya no hay contacto...").
* La lista desplegable Huso horario de la pantalla de creación de perfiles se ha movido de la sección Dirección a la sección superior de la interfaz.
* Ahora puede agregar separadores al configurar pantallas de recursos personalizadas, lo que le permite organizar los campos en categorías.

   Para obtener más información, consulte la documentación [](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration)detallada.

### Otros cambios {#other-changes-1}

* Adobe Campaign y Adobe Experience Cloud dejarán de ofrecer compatibilidad con Microsoft Internet Explorer 11 a partir de la primavera de 2019 y con Campaign Standard 19.2. Cambie a Microsoft Edge u otro explorador compatible. Consulte [Página Funciones](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) obsoletas y eliminadas.
* Se ha cambiado el nombre del campo Código **de** país del recurso Perfil al código **** País/Región.

### Parches {#patches-1}

* Se ha corregido un problema que impedía que se enviara el mensaje al agregar un perfil de prueba a un mensaje transaccional de correo electrónico. (CAMP-29854)
* Se ha corregido un problema que ralentizaba el envío de mensajes desde otros canales si el envío era bajo para un canal cuando el envío de mensajes desde todos los canales se activaba simultáneamente.
* Se ha corregido un problema que hacía que MTA empezara a enviar mensajes SMS cuando la conexión de cuenta externa aún no estaba establecida.
* Se ha corregido un problema que se producía con la frecuencia de ejecución de la actividad Programador y la hora de inicio. (CAMP-30745)
* Se ha corregido un problema que se podía producir con la generación de PKEY al usar recursos de perfil extendidos. (CAMP-30285)
* Se ha corregido un problema que podía ocurrir con las reglas de fatiga basadas en días de calendario. (CAMP-30136)
* Se ha corregido un problema que se podía producir al intentar obtener acceso a los recursos personalizados con nombres que terminaran por "Base". (CAMP-30109)
* Se ha corregido un problema que impedía utilizar una llamada PATCH para suscribir un perfil a un servicio. (CAMP-29728)
* Se ha corregido un problema que podía dañar un flujo de trabajo al importar un archivo XML a través de la actividad Cargar archivo. (CAMP-29208 y CAMP-28205)
* Se ha corregido un problema al vincular recursos personalizados que podía impedir que se generaran vínculos de cardinalidad inversa. (CAMP-30476)
* Se ha corregido un problema que impedía ampliar los registros de entrega al usar solo el código de segmento.
* Se ha corregido un problema que podía duplicar filas al usar la actividad de transferencia de archivos en flujos de trabajo.
* Se ha corregido un problema que impedía que los informes programados se enviaran a la hora elegida.
* Se ha corregido un problema que provocaba discrepancias entre los KPI "Para entregar" y "Enviado" para una entrega en la aplicación en un flujo de trabajo.
* Se ha corregido un problema que impedía que el seguimiento funcionara para un mensaje en la aplicación creado con un HTML personalizado.
* Se ha corregido un problema que impedía que el contenido de entrega en la aplicación se guardara cuando se utilizaba en un flujo de trabajo.
* Se ha corregido un problema que impedía que las aplicaciones móviles se mostraran para los administradores.
* Se corrigió un problema que ocasionaba que fallara el flujo de trabajo técnico de la Actualización de entregabilidad. (CAMP-26387)
* Se ha corregido un problema que provocaba discrepancias entre los perfiles objetivo al crear una entrega en la aplicación y los que se mostraban en el panel de envío. (CAMP-28722)
* Se ha corregido un problema con la integración del servicio principal de campañas y recursos que impedía seleccionar un recurso compartido en un correo electrónico.

## Versión 19.0: enero de 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

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
   <td> Disponibilidad general de Email Designer<br /> </td> 
   <td> <p>El nuevo e intuitivo diseñador de correo electrónico (anteriormente conocido como Creative Designer) se ha trasladado a GA. Ahora admite todas las funciones del editor de contenido heredado, incluidas:</p> 
    <ul> 
     <li> El uso de imágenes <a href="../../integrating/using/adding-target-dynamic-content.md">dinámicas de Adobe Target</a> </li> 
     <li> Capacidad para <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">recuperar contenido de una URL automáticamente en tiempo de preparación</a> </li> 
     <li> Plantillas de contenido totalmente <a href="../../designing/using/using-reusable-content.md#content-templates">listas para usar y totalmente compatibles</a>. </li> 
    </ul> 
    <p>Para obtener más información, consulte la documentación <a href="../../designing/using/overview.md"></a> detallada y el vídeo de <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">procedimientos</a>. A continuación se enumeran las mejoras y correcciones.</p><p>Como consecuencia, el editor de contenido de correo electrónico heredado ya no se utiliza. Para obtener más información, consulte esta <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">página</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Listados de productos en correos electrónicos transaccionales<br /> </td> 
   <td> <p>Ahora puede hacer referencia a una o varias colecciones de productos en un mensaje de correo electrónico transaccional. Por ejemplo, puede enviar automáticamente un correo electrónico de abandono del carro de compras con una lista de todos los productos que estaban en el carro de compras del usuario con una imagen, un precio y un vínculo a cada producto.</p><p>Para obtener más información, consulte la documentación <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message"></a> detallada y el vídeo de <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">procedimientos</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Vista móvil en el Diseñador de correo electrónico<br /> </td> 
   <td> <p>Ahora puede cambiar a una vista móvil dedicada al editar el contenido del correo electrónico. Esto le permite ajustar el diseño interactivo de un correo electrónico editando por separado todas las opciones de estilo para la visualización móvil, como la adaptación de márgenes, el tamaño de fuente más pequeño, el color de fondo diferente, etc.</p><p> Para obtener más información, consulte la documentación <a href="../../designing/using/plain-text-html-modes.md#switching-to-mobile-view"></a>detallada.</p> </td> 
  </tr> 
  <tr> 
   <td> Mejoras en la versión beta de la mensajería en la aplicación<br /> </td> 
   <td> <p>La función Beta de mensajería en la aplicación se ha mejorado con las siguientes capacidades:</p> 
    <ul> 
     <li> El canal beta en la aplicación es compatible con GDPR </li> 
     <li> Integración con las API de Analytics para rellenar los menús desplegables Desencadenadores </li> 
     <li> Aspecto intuitivo y descripción de las plantillas de entrega </li> 
     <li> Mejoras en la interfaz de creación desde el punto de vista de la facilidad de uso </li> 
    </ul> <p>Para obtener más información, consulte la documentación <a href="../../channels/using/about-in-app-messaging.md"></a>detallada.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Mejoras {#improvements}

* Una nueva opción en la actividad Cargar datos ahora permite aplicar una etapa posterior al procesamiento al archivo que contiene los registros rechazados (por ejemplo, Compresión en formato zip). (CAMP-24521)
* Una nueva opción en la actividad Actualizar datos ahora permite configurar el tamaño máximo del lote para que se carguen los datos. (CAMP-28400)
* Se ha mejorado la selección del estado de dirección de los perfiles. Al seleccionar un país, la lista desplegable "Estado" ahora se actualiza automáticamente con los valores de estados relevantes. (CAMP-28874)
* Ahora, una nueva opción en la actividad de archivo de extracción impide que se genere un archivo si la transición de entrada está vacía. Esto evita la creación y carga de archivos vacíos en servidores SFTP.
* Se ha mejorado el informe de resumen de envío.
* Se ha enriquecido la lista de países disponibles al definir la dirección de un perfil. (CAMP-26707)
* Ahora se muestra un mensaje de error al intentar importar un flujo de trabajo integrado.

### Email Designer {#email-designer}

* Se ha corregido un problema que habilitaba la capacidad de unidad geográfica en una plantilla de correo electrónico o un fragmento de contenido creado con el Diseñador de correo electrónico, aunque esta capacidad estuviera deshabilitada en Adobe Campaign, lo que hacía que la plantilla o el fragmento no estuviera disponible al intentar acceder de nuevo. (CAMP-28174)
* Se ha corregido un problema que impedía guardar las condiciones de contenido dinámico al editar contenido con el Diseñador de correo electrónico. (CAMP-27905)
* Se ha corregido un problema que eliminaba la versión HTML del contenido del correo electrónico después de editar la versión de texto sin formato de un mensaje y de romper la sincronización HTML en el Diseñador de correo electrónico. (CAMP-28507)
* Se ha corregido un problema que impedía que se abriera la interfaz de Email Designer al utilizar Internet Explorer 11. (CAMP-28273)
* Se ha corregido un problema que distorsionaba el procesamiento de Microsoft Outlook de la configuración de estilo aplicada a los botones con el Diseñador de correo electrónico.
* Se corrigió un problema en el Diseñador de correo electrónico que hacía que una dirección URL editable a partir de un fragmento de contenido utilizado en un correo electrónico no se esperaba, ya que el fragmento está bloqueado de forma predeterminada.
* Se ha corregido un problema que impedía que el componente divisor de Email Designer se mostrara en Microsoft Office.
* Se ha corregido un problema que hacía que se bloqueara la página en determinados navegadores de Internet al ver un contenido sincronizado desde AEM con el editor de contenido de correo electrónico heredado. (CAMP-29068)
* Se corrigió un error que se producía al hacer clic en cualquier imagen de un correo electrónico al usar el editor de contenido de correo electrónico heredado. (CAMP-30424)
* Se ha corregido un problema que impedía que se mostraran los fragmentos recién creados al editar un correo electrónico con el Diseñador de correo electrónico. (CAMP-29928)
* Se ha corregido un problema que impedía que el texto del botón se mostrara correctamente en los correos electrónicos creados con el Diseñador de correo electrónico y recibidos con el cliente de correo web de Outlook.
* Ahora es posible crear mensajes transaccionales de perfil mediante el Diseñador de correo electrónico. (CAMP-28900)
* Se corrigió un error en el Diseñador de correo electrónico que hacía que el contenido se pudiera editar al recuperar contenido de una URL automáticamente en tiempo de preparación, mientras que debería bloquearse.

### Parches {#patches-2}

* Se ha corregido un problema que mostraba registros de entrega incorrectos en los informes dinámicos. (CAMP-23446)
* Se ha corregido un problema que podía afectar a los números del informe Resumen de devoluciones (CAMP-28703)
* Se ha corregido un problema con la integración del servicio principal de campañas y recursos que podía impedir que se mostraran recursos al seleccionarlos **[!UICONTROL Image shared from Adobe Experience Cloud]** en un mensaje de correo electrónico (CAMP-28732).
* Se ha corregido un problema que impedía que los mensajes SMS que contenían el carácter ‘uno’ se enviaran aunque la transliteración estuviera autorizada en la cuenta externa de SMPP. (CAMP-29041)
* Se ha corregido un problema que podía mostrar registros duplicados al usar una actividad de segmentación en flujos de trabajo. (CAMP-28743)
* Se ha corregido un problema que impedía eliminar una de las asignaciones de valores en una columna de una actividad de flujo de trabajo. (CAMP-28708)
* Se ha corregido un problema en la actividad de transferencia de archivos al usar caracteres comodín con la opción "Probar para ver si el archivo existe". (CAMP-28977)
* Se ha corregido un problema en la actividad de transferencia de archivos que se podía producir al actualizar la configuración de cuenta externa. (CAMP-28894)
* Se ha corregido un problema con los filtros personalizados en el editor de consultas al usar la condición "Correo electrónico no está vacío". (CAMP-28741)
* Se ha corregido un problema que se podía producir al exportar tablas de recursos personalizados con más de 100.000 registros. (CAMP-28150)
* Se ha corregido un problema que impedía eliminar mensajes transaccionales vinculados a activadores. (CAMP-28385)
* Se han eliminado las contraseñas que se mostraban de forma insegura en algunos registros de SMS.
* Se ha corregido un problema que provocaba que las conexiones al simulador SMPP fallaran debido a una contraseña vacía enviada por Adobe Campaign.
* Se ha corregido un problema que impedía enviar campañas cuando las conexiones SMS eran inestables.
* Se ha corregido un problema que mostraba entregas eliminadas en los informes dinámicos.
* Se ha corregido un problema que impedía recuperar datos adicionales de los registros de entrega, los registros de seguimiento y las tablas de registros de exclusión al usar una actividad de enriquecimiento en un flujo de trabajo.
* Se ha corregido un problema con las solicitudes de eliminación del RGPD que se producía al utilizar un tipo de vínculo "N de recopilación de cardinalidad" y la opción "Eliminar el registro de destino implica eliminar las referencias de registros por el vínculo".
* Se ha corregido un problema con el uso compartido de informes.
* Se ha corregido un problema que podía provocar problemas de rendimiento al enviar una notificación push.
* Se ha corregido un problema que hacía que faltaran campos en los archivos de salida de correo directo.
* Se ha corregido un problema que permitía a los usuarios modificar los flujos de trabajo integrados.
* Se ha corregido un problema que se producía al crear una campaña basada en una plantilla de campaña, incluido un flujo de trabajo con una actividad de extracción configurada. (CAMP-29198)
* Se ha corregido un problema con la actividad de extracción de archivos que impedía usar la misma expresión para varios elementos. (CAMP-29182)
* Se corrigió un problema en el editor de consultas con la condición de unión entre el registro de banda ancha y el registro de seguimiento para rtEvent. (CAMP-28780)
* Se ha corregido un problema que impedía que se guardaran las modificaciones de la opción de página de aterrizaje "Acción específica". (CAMP-29422)
* Se ha corregido un problema que impedía exportar la carga útil de un evento en un flujo de trabajo. (CAMP-29029)
* Se ha corregido un problema que impedía que los números SMS bloqueados se excluyeran en un mensaje SMS. (CAMP-28898)
* Se ha corregido un problema que podía impedir que se notificara a los proveedores de SMPP en caso de error al procesar los mensajes entrantes. (CAMP-29804)
* Se ha corregido un problema que permitía eliminar cuentas externas con entregas asociadas. (CAMP-29738)
* Se ha mejorado y estabilizado el rendimiento de envío de mensajes SMS.
* Se ha corregido un problema que impedía que el carácter "~" se usara en un mensaje SMS. (CAMP-29172)
* Se ha corregido un problema en los envíos con la opción de optimización de tiempo de envío. (CAMP-29231)

