---
title: Notas de la versión
seo-title: Notas de la versión
description: Notas de la versión
seo-description: Esta página enumera todas las versiones recientes de Adobe Campaign Standard.
page-status-flag: no activado nunca
uuid: 1 cf 2 e 40 c-beca -43 db -8261-a 1820 ee 86 ad 3
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versiones estándar de campaña
discoiquuid: 5 c 7 bfb 74-4002-4 ffe -87 e 8-bddb 41 d 34 b 41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 830292bd6f5bbd143ad0c674aaac67b67abc5665

---


# Release Notes{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido. Consult the [Release Planning](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) to find out when the next release will happen.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a previous release, consult these pages: [2018 Release Notes](../../rn/using/release-notes-2018.md), [2017 Release Notes](../../rn/using/release-notes-2017.md), [2015-2016 Release Notes](../../rn/using/release-notes-2015-2016.md). Also consult the list of [Deprecated and Removed Features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html).

## Release 19.2.7 - July 2019 {#release-19-2-7---july-2019}

### Improvements {#improvements-2}

* La consulta de eliminación del RGPD se ha mejorado para mejorar el rendimiento.
* Se ha corregido un problema que podía provocar bloqueos Web después de la actualización 19.2. (CAMP -34862)
* Se ha corregido un problema que impedía a los usuarios que no fueran administradores guardar o programar informes. (CAMP -31133)
* Se corrigió un problema al utilizar "|" como separador de fechas en la actividad de flujo de trabajo de archivo de carga. (CAMP -34706)

## Release 19.2.4 - June 2019 {#release-19-2-4---june-2019}

### Email Designer {#email-designer-2}

* Se ha corregido un problema que impedía a los usuarios editar fragmentos cuando se utilizaban etiquetas de estilo vacías en HTML. Esta es una corrección de seguimiento para CAMP -33778 en 19.2.3.

## Release 19.2.3 - June 2019 {#release-19-2-3---june-2019}

### Email Designer {#email-designer-1}

Se ha introducido una serie de mejoras y correcciones para optimizar los fragmentos en la versión 19.2. Los fragmentos recién creados funcionarán perfectamente. Los fragmentos creados anteriormente se han atenuado y deben migrarse al nuevo formato. Para ello, haga clic en cada fragmento y valide su migración al nuevo formato. Le recomendamos que pruebe algunos fragmentos antes de migrarlos todos.

* Se ha corregido un problema que impedía que los usuarios editasen un fragmento después de desbloquearlo. Esto afectaba a los fragmentos existentes al actualizar a 19.2. (CAMP -33778)
* Se ha corregido un problema al utilizar contenido dinámico. Se agregaron espacios adicionales en el HTML.

### Other improvements {#other-improvements-2}

* Se ha corregido un problema que podía impedir que el envío SMS se reanudara tras una desconexión del conector SMS.
* Se ha corregido un problema que podía cerrar conexiones SMPP cuando se activaba TLS.
* Se ha corregido un problema que podía cerrar conexiones SMPP cuando se activaba TLS.
* La opción «Launch_ URL_ Campaign» se ha agregado en Campaign para administrar las propiedades de las aplicaciones móviles creadas con Adobe Experience Platform Mobile SDK.
* Se ha corregido un error que provocaba que se desactivara la opción del entorno Simulador para pruebas después de cargar el certificado de una propiedad móvil recién creada y salir de la página de propiedad de la aplicación móvil.
* Se ha corregido un problema que impedía enriquecer un contenido de mensaje transaccional con información del recurso de Servicio. (CAMP -33707)
* Se corrigió un problema en las páginas de aterrizaje Blacklist que se producía al intentar cancelar la suscripción de perfiles de un servicio.

## Release 19.2 - May 2019 {#release-19-2---may-2019}

### What's new? {#what-s-new-}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Control Panel<br /> </td> 
   <td> <p>Para ayudar a aumentar la eficacia de su trabajo como usuario administrador, puede supervisar fácilmente la capacidad y administrar la configuración de las instancias (empezando por la administración de servidores SFTP).</p><p>For more information, refer to the <a href="https://helpx.adobe.com/campaign/kb/control-panel.html">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-control-panel-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Local notifications<br /> </td> 
   <td> <p>Los mensajes de notificación local permiten informar a los usuarios cuando los nuevos datos están disponibles en sus aplicaciones móviles, incluso sin tener acceso a Internet o a la aplicación móvil que se ejecuta en primer plano. Las notificaciones locales se activan mediante una aplicación móvil en un momento concreto y según un evento.</p><p>For more information, refer to the <a href="../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type">detailed documentation</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Workflow enhancement - Add a payload to external signal activity<br /> </td> 
   <td> <p>Inicie un flujo de trabajo con una carga útil cuando las condiciones definidas se cumplan correctamente con otro flujo de trabajo o una llamada de API REST para integrarlos con los sistemas externos. This also includes a new <strong>test</strong> activity where you can run tests on this functionality.</p><p>For more information, refer to the <a href="../../automating/using/calling-a-workflow-with-external-parameters.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-external-signal-activity-feature-video-use.html">how-to video</a>.</p></td> 
  </tr> 
  <tr> 
   <td> Landing Pages enhancement - Google reCAPTCHA<br /> </td> 
   <td> <p>Aproveche Google recaptcha para evitar el correo deseado en las páginas de aterrizaje sin requerir ninguna acción de sus clientes.</p><p>For more information, refer to the <a href="../../channels/using/designing-a-landing-page.md#setting-google-recaptcha">detailed documentation</a>.</p></td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements}

* Se ha corregido un posible problema de seguridad de clickjacking en el área de trabajo de informes.

### Email Designer enhancements {#email-designer-enhancements}

* Se ha corregido un problema que se producía al duplicar fragmentos e intentar usarlos en el correo electrónico de Designer. (CAMP -33193)
* Se ha corregido un problema que creaba espacios no deseados al utilizar elementos en línea en la interfaz de Email Designer. (CAMP -32163)
* Se ha corregido un problema que eliminaba algunos atributos de etiqueta HTML adicionales agregados por el usuario después de guardar contenido de correo electrónico en el correo electrónico de Designer. (CAMP -32162)
* Se ha corregido un problema que mostraba una etiqueta de Microsoft Office en el modo HTML de Designer Designer incluso después de eliminarla. (CAMP -32141)
* Si ha creado un correo electrónico con una versión anterior de Designer Designer, al abrir este contenido de correo electrónico, ahora aparecerá una ventana emergente que solicita al usuario que actualice a la versión más reciente. (CAMP -31529)
* Se ha corregido un problema que podía distorsionar imágenes de un correo electrónico creado con el correo electrónico de Designer cuando se entregaban a algunos clientes. (CAMP -31407)
* Se ha corregido un problema que impedía que algunos elementos, como listas o botones, se mostraran correctamente en modo de texto normal cuando se creaban en modo HTML. (CAMP -32582, CAMP -32542)
* Se ha corregido un problema que impedía mostrar más de 50 unidades de organización en una plantilla de contenido o propiedades de fragmento. (CAMP -32932)
* Se ha corregido un problema con el color de fondo de la ventanilla móvil al recibir un correo electrónico creado con el correo electrónico de Designer en Outlook. (CAMP -31402)
* Se ha corregido un problema que impedía que el contenido de correo electrónico creado con el correo electrónico de Designer se adaptara al abrirlo en Outlook. (CAMP -31400)
* Se ha corregido un problema que impedía que el contenido dinámico funcionara correctamente cuando se utilizaba en un asunto de correo electrónico. (CAMP -32837)
* Se ha corregido un problema relacionado con el asunto del mensaje de correo electrónico que no era adecuado.
* Se ha corregido un problema que impedía que los fragmentos se cargaran en la paleta izquierda de Designer Designer.
* Se ha corregido un problema que impedía que los fragmentos creados durante la edición de contenido de correo electrónico se mostraran en la paleta izquierda de Designer Designer al actualizar la lista de fragmentos.
* Se han corregido varios problemas que se producían al utilizar contenido dinámico en un mensaje de correo electrónico.
* Se ha corregido un problema que se producía con el selector de color al intentar definir un color con valores RGB.
* Se ha corregido un problema que impedía que la página reflejada respondiera al recibir el correo electrónico en un dispositivo móvil.

### Transactional Messaging enhancements {#transactional-messaging-enhancements}

Se han agregado varias mejoras al canal de mensajes Transaccionales para optimizar la operación y el rendimiento.

* La duración del mensaje transaccional se ha ampliado para garantizar que todos los mensajes se envíen antes de que caduquen, especialmente cuando se realizan reintentos.
* El rendimiento de los mensajes transaccionales ha aumentado distribuyendo la carga en diferentes procesos de envío.
* El proceso de mensajes transaccionales se ha optimizado para poder comenzar en paralelo múltiples análisis del mismo mensaje.
* Se ha corregido un problema que podía provocar un rendimiento y latencia incoherentes para las notificaciones push transaccionales.
* Se ha corregido un problema que mostraba una audiencia de destino incorrecta para entregas de ejecución de mensajes transaccionales.
* Se ha corregido un problema que se producía al importar un paquete con una configuración de evento y el mensaje de transacción asociado. For more on this, refer to the [detailed documentation](../../channels/using/about-transactional-messaging.md#exporting-and-importing-transactional-messages).
* Se ha corregido un problema que eliminaba los datos de la colección de los perfiles de prueba creados para un mensaje de transacción que contenía listados de productos.

### Other changes {#other-changes}

* Se ha agregado una nueva opción a la cuenta externa SMS. Permite limitar el número máximo de procesos de llamada a acción que envían SMS para controlar mejor el número de conexiones paralelas. For more information, refer to the [SMS connector protocol and settings](https://helpx.adobe.com/campaign/kb/sms-connector-protocol-and-settings.html) technote.
* Al publicar un recurso con la extensión de API, si la API ya se ha publicado, ahora se actualiza automáticamente cada vez que se vuelve a publicar. Anteriormente, esta acción era manual y no actualizaba la API podía alterar el perfil de servicio o de servicio de esta API. For more on this, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension).
* Se ha eliminado la dimensión Código postal de los informes dinámicos. Se recomienda utilizar las dimensiones Ciudad, País, Estado en su lugar.
* Se ha eliminado el activador del evento «Primer lanzamiento» de ciclo vital para mensajes en la aplicación.
* Al exportar un paquete con grupos de seguridad, ahora contiene las funciones asignadas a cada grupo. (CAMP -32960)
* En la actividad Cargar archivo, una nueva opción le permite comprobar que las columnas del archivo que está cargando coinciden con la definición de columna. For more information, refer to the [detailed documentation](../../automating/using/load-file.md). (CAMP -32229)
* Los flujos de trabajo ahora se pueden iniciar con una carga útil, permitiéndole utilizar y compartir parámetros externos entre actividades dentro del flujo de trabajo. For more information, refer to the [detailed documentation](../../automating/using/calling-a-workflow-with-external-parameters.md). (CAMP -29412 &amp; CAMP -29413)
* Las API de Campaign Standard ahora permiten actualizar las unidades geográficas y organizativas de los perfiles mediante una carga útil. For more information, refer to the [detailed documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).
* Se han aclarado los mensajes de error cuando no se puede acceder a un objeto de la base de datos.
* En la actividad de extracción de archivos, las capacidades de Javascript se han actualizado al definir el nombre de un archivo que exportar. Solo la función formatdate está ahora disponible para su uso en el campo Salida. For more information, refer to the [detailed documentation](../../automating/using/extract-file.md).
* La generación automática de ID de secuencia automática se ha mejorado para los recursos personalizados. De forma predeterminada, las claves principales para los nuevos recursos personalizados tienen 64 bits.
* Se ha mejorado el modo de prueba de publicación de recursos personalizados. Ahora se muestra un mensaje de advertencia a los usuarios si se ha producido un error en la publicación del último recurso personalizado y no se ha corregido. Después de un error en la publicación de recursos personalizados, puede volver a la última versión de trabajo. For more information, refer to the [detailed documentation](../../developing/using/updating-the-database-structure.md#publishing-a-custom-resource).
* Se ha agregado una nueva opción en la actividad de transferencia de archivos. Permite ordenar los archivos al utilizar la acción de descarga de archivos en el modo SFTP. For more information, refer to the [detailed documentation](../../automating/using/transfer-file.md). (CAMP -33109)

### Patches {#patches}

* Se ha corregido un problema que podía provocar la fuga de memoria a MTA cuando se volvían a cargar los ajustes SMS.
* Se ha corregido un problema que podía impedir las actualizaciones de la base de datos de publicación en modo de reparación.
* Se ha corregido un problema que causaba discrepancia entre Informes de Adobe Analytics y Informes dinámicos de Adobe Campaign. (CAMP -25393)
* Se ha corregido un error que provocaba errores en el flujo de trabajo de Compartir informes.
* Se ha corregido un error que impedía que los usuarios enviaran mensajes en la aplicación con Solo Media URL.
* Se ha corregido un problema que mostraba una aplicación móvil aunque no se cargara su certificado en la instancia.
* Fixed an error that prevented personalization fields from working when using the **Target all users of a Mobile app** template.
* Se aprovisionaron las instancias de Nueva campaña Standard. (CAMP -32635 &amp; CAMP -32344)
* Se ha corregido un error que impedía personalizar la fórmula de fecha en un flujo de trabajo. (CAMP -30336)
* Se ha corregido un problema que se producía al definir una fórmula de fecha personalizada que impedía que los campos "Datos adicionales" y "Código de segmento" estuvieran disponibles en la lista desplegable. (CAMP -32383)
* Se ha corregido un problema que impedía que las actividades de «Transferencia de archivos» y «Extracción de archivos» se desactivaran si se codificaban. (CAMP -32377)
* Se ha corregido un problema en las API que podía evitar que el filtro linecount procesara el recuento total exacto. (CAMP -31424)
* Se ha corregido un problema en las páginas de aterrizaje que impedía que los campos de entrada mostraran el valor actualizado una vez que se había modificado. (CAMP -31401)
* Se ha corregido un problema que podía llevar a una actividad de señal a activarse inesperadamente.
* Se ha corregido un problema que impedía que se mostrara la vista previa de correo electrónico cuando la audiencia estaba vacía.
* Se ha corregido un problema en la actividad «Extraer archivo» que podía generar un archivo mientras que «No generar un archivo si la transición de entrada está vacía» estaba activada.
* Se ha corregido un problema que provocaba que el flujo de trabajo de Deliverability desactivara si no se terminaba correctamente.
* Se ha corregido un problema que impedía a los usuarios guardar o programar informes. (CAMP -31133)

## Release 19.1.3 - March 2019 {#release-19-1-3---march-2019}

### Email Designer enhancements {#email-designer-enhancements-1}

* Se ha corregido un problema que impedía modificar una plantilla después de guardarla.
* Se han corregido varios problemas al usar una plantilla creada previamente en un mensaje de correo electrónico.
* Se ha corregido un problema que impedía que los componentes se ocultaran en plantillas importadas.

### Other improvements {#other-improvements}

* Se ha corregido un error al ver reglas de tipología. (CAMP -32059 &amp; CAMP -31849)
* Se ha corregido un problema que impedía editar reglas de tipología. (CAMP -31750)
* Se ha corregido un problema con el proceso de inmail que podía detenerse inesperadamente. (CAMP -31238)

## Release 19.1 - February 2019 {#release-19-1---february-2019}

### What's new? {#what-s-new--1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Push channel Reporting improvements<br /> </td> 
   <td> <p>Se han agregado varias mejoras a los informes de canal Push para permitirle medir la participación de los usuarios de forma más intuitiva. Con esta versión, ampliamos la lista de métricas de canal push a tres métricas diferentes: Impresiones, Clics, Aperturas (Apertura de la aplicación) para ayudarle a medir y analizar la interacción de los usuarios con las notificaciones Push de forma más eficaz. Además de esto, estandarizamos la definición y la implementación de estas métricas. El informe integrado de notificaciones Push también se ha mejorado con las visualizaciones y métricas utilizadas con más frecuencia.</p><p> For more information, refer to the <a href="../../reporting/using/push-notification-report.md">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Launch integration for Mobile App<br /> </td> 
   <td> <p>Esta versión contiene la integración de Adobe Campaign con las versiones GA de las extensiones de Android y iOS para Adobe Campaign Standard en Adobe Experience Platform Launch y SDK de Mobile. Estas extensiones admiten mensajería push, mensajería en la aplicación y actualizaciones de perfiles de aplicaciones móviles.</p><p> For more information, refer to the <a href="../../administration/using/about-typology-rules.md#typology-rules">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile In-App Messaging<br /> </td> 
   <td> <p>Esta versión contiene la versión GA del canal In-App en Campaign. Desde un punto de vista funcional, las adiciones más importantes a la versión Beta son los informes dinámicos para el canal en la aplicación y el enlace seguro entre el SDK móvil y MCIAS (servicio de mensajería en la aplicación de Marketing Cloud que sirve las reglas dentro de la aplicación al SDK). El protocolo de enlace seguro garantiza que los datos PII de los usuarios no caigan en manos malintencionadas, así como mantener la privacidad de los usuarios en un dispositivo compartido borrando la caché del mensaje cada vez que el usuario cierra sesión.</p><p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a> and the dedicated <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-in-app-message-tutorial.html">In-App tutorial</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Workflow enhancements<br /> </td> 
   <td> <p>Se han añadido las siguientes capacidades de flujo de trabajo:</p> 
    <ul> 
     <li> Ahora puede copiar y pegar actividades dentro de un flujo de trabajo u otro flujo de trabajo desde la misma instancia de Campaña. De esta forma, puede duplicar fácilmente un flujo de trabajo completo o actividades específicas y conservar la configuración definida inicialmente. For more information, refer to the <a href="../../automating/using/workflow-interface.md#duplicating-workflow-activities">detailed documentation</a>. (CAMP -20014) </li> 
     <li> When using the <strong>Load file</strong> activity, you can now add a timestamp to the name of the file containing the rejected records. For more information, refer to the <a href="../../automating/using/load-file.md#configuration">detailed documentation</a>. </li> 
     <li> <strong>Las actividades de consulta</strong> y <strong>segmentación</strong> ahora permiten habilitar una transición saliente si las actividades no recuperan datos. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Security enhancements {#security-enhancements-1}

* El código HTML de la página de aterrizaje generada se ha actualizado para evitar la indexación de motores de búsqueda.

### Email Designer enhancements {#email-designer-enhancements-2}

* Ya está disponible un conjunto de cuatro plantillas de correo electrónico interactivas de mejor calidad diseñadas por artistas de Behance.

   For more information, refer to the [detailed documentation](../../start/using/about-templates.md#content-templates).

* Nuestra nueva experiencia de integración le ayudará a empezar a crear por correo electrónico más rápido y le facilitará el acceso a la documentación y a los tutoriales.

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#email-designer-home-page).

* Ahora tiene la flexibilidad de configurar el número de columnas y anchura según sus necesidades.

   For more information, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#editing-the-email-structure).

* Al editar en la vista móvil, puede ocultar ciertos componentes solo en la visualización móvil para un uso efectivo del espacio.

   For more information, refer to the [detailed documentation](../../designing/using/about-email-content-design.md#switching-to-mobile-view).

* Ahora puede agregar canales sociales personalizados a la plantilla de correo electrónico sobre los que ya están disponibles.
* Se ha corregido un problema que impedía desplazarse hacia abajo en el menú de estructura al utilizar más de 18 estructuras. (CAMP -31173)
* Se ha corregido un problema que mostraba el encabezado sobre el contenido al reenviar un mensaje de correo electrónico que contenía un encabezado enviado con Adobe Campaign. (CAMP -30736)
* Fixed an issue that prevented the subject line from being updated when clicking the **Refresh AEM content** option after modifying the subject in Adobe Experience Manager. (CAMP -29984)
* Se han corregido varios problemas que impedía el uso de imágenes dinámicas de Adobe Target.
* Se ha corregido un problema que impedía que la vista previa se actualizara al recuperar contenido al momento de la preparación si el contenido había sido importado previamente desde una URL.
* The YouTube icon has been added to the **Social** content component.
* The **List** view has been added for content components and fragments displayed in the Email Designer palette.

### Other improvements {#other-improvements-1}

* Adobe Campaign es compatible con FCM tanto para las aplicaciones SDK V 4 de SDK como para AEP SDK.
* Adobe Campaign admite notificaciones push en Wear OS por Android, así como watchos por Apple.
* Los mensajes de advertencia y error que pueden mostrarse al navegar en la interfaz se han aclarado y simplificado.
* Ahora puede agregar a las columnas de lista de perfiles relacionadas con la inclusión y la exclusión ("Ya no se contactan…" los campos).
* La lista desplegable Huso horario de la pantalla de creación Perfil se ha movido de la sección Dirección a la parte superior de la interfaz.
* Ahora puede añadir separadores al configurar pantallas de recursos personalizados, lo que le permite organizar los campos en categorías.

   For more information, refer to the [detailed documentation](../../developing/using/configuring-the-screen-definition.md#defining-the-detail-screen-configuration).

### Other changes {#other-changes-1}

* Adobe Campaign y Adobe Experience Cloud dejarán de ofrecer asistencia para Microsoft Internet Explorer 11 comenzando la primavera de 2019 y la versión de Campaign Standard 19.2. Cambie a Microsoft Edge u otro explorador compatible. See [Deprecated and removed features](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html) page.
* The **Country code** field from the Profile resource has been renamed to **Country/Region code**.

### Patches {#patches-1}

* Se ha corregido un problema que impedía que el mensaje se enviara al agregar un perfil de prueba a un mensaje transaccional de correo electrónico. (CAMP -29854)
* Se ha corregido un problema que ralentizaba el envío de mensajes de otros canales si el envío era escaso para un canal cuando el envío de mensajes desde todos los canales se activaba simultáneamente.
* Se ha corregido un problema que provocaba que el MTA comenzara a enviar mensajes SMS cuando todavía no se había establecido la conexión de cuenta externa.
* Se ha corregido un problema que se producía con la frecuencia de ejecución de actividad Programador y la hora de inicio. (CAMP -30745)
* Se ha corregido un problema que se podía producir con la generación de PKEY al utilizar recursos de perfil extendidos. (CAMP -30285)
* Se corrigió un problema que se podía producir con reglas de Fatiga basadas en el día del calendario. (CAMP -30136)
* Se ha corregido un problema que se podía producir al intentar acceder a recursos personalizados con nombres que terminaban con "Base". (CAMP -30109)
* Se ha corregido un problema que impedía utilizar una llamada PATCH para suscribirse a un servicio. (CAMP -29728)
* Se ha corregido un problema que podía dañar un flujo de trabajo al importar un archivo XML a través de la actividad Cargar archivo. (CAMP -29208 y CAMP -28205)
* Se corrigió un problema al vincular recursos personalizados que podían impedir que se generaran vínculos de cardinalidad inversa. (CAMP -30476)
* Se ha corregido un problema que impedía ampliar los registros de entrega al utilizar únicamente el código de segmento.
* Se ha corregido un problema que podía duplicar filas al utilizar la actividad de transferencia de archivos en flujos de trabajo.
* Se ha corregido un problema que impedía que los informes programados se enviaran en el momento elegido.
* Se ha corregido un problema que provocaba discrepancias entre los KPI «Enviados» y «Enviados» para una entrega desde la propia aplicación en un flujo de trabajo.
* Se ha corregido un problema que impedía que el seguimiento funcionara para un mensaje en la aplicación creado con un HTML personalizado.
* Se ha corregido un problema que impedía guardar contenido de entrega en la aplicación cuando se utilizaba en un flujo de trabajo.
* Se ha corregido un problema que impedía que se mostraran aplicaciones móviles para administradores.
* Se ha corregido un problema que provocaba que fallara el flujo de trabajo técnico Actualización de la capacidad de entrega. (CAMP -26387)
* Se ha corregido un problema que provocaba discrepancias entre los perfiles dirigidos al crear una entrega en la aplicación y los que se mostraban en el panel de entrega. (CAMP -28722)
* Se ha corregido un problema con la integración de los servicios principales de campañas y recursos que impedía seleccionar un recurso compartido en un mensaje de correo electrónico.

## Release 19.0 - January 2019 {#release-19-0---january-2019}

### What's new? {#what-s-new--2}

<table> 
 <colgroup><col style="width: 30%"><col style="width: 70%"></colgroup>
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Email Designer General Availability<br /> </td> 
   <td> <p>El nuevo intuitivo correo electrónico Designer (anteriormente conocido como Creative Designer) se ha trasladado a GA. Ahora admite todas las funciones del editor de contenido heredado, incluyendo:</p> 
    <ul> 
     <li> The use of <a href="../../integrating/using/adding-target-dynamic-content.md">dynamic images from Adobe Target</a> </li> 
     <li> The ability to <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">retrieve content from a URL automatically at preparation time</a> </li> 
     <li> Fully compliant <a href="../../start/using/about-templates.md#content-templates">out-of-the box content templates</a>. </li> 
    </ul> 
    <p>For more information, refer to the <a href="../../designing/using/about-email-content-design.md">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-email-designer-tutorial.html">how-to video</a>. A continuación se enumeran las mejoras y correcciones.</p><p>Como consecuencia, el editor de contenido de correo electrónico heredado ya está obsoleto. For more information, refer to this <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">page</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Product Listings in Transactional Emails<br /> </td> 
   <td> <p>Ahora puede hacer referencia a una o varias colecciones de productos en un mensaje de correo electrónico de transacción. Por ejemplo: puede enviar automáticamente un correo electrónico de abandono del carro de compras con todos los productos que estaban en el carro de compras del usuario con una imagen, un precio y un vínculo a cada producto.</p><p>For more information, refer to the <a href="../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message">detailed documentation</a> and the <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-product-listings-in-transactional-emails-feature-video-setup.html">how-to video</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> Mobile View in the Email Designer<br /> </td> 
   <td> <p>Ahora puede cambiar a una vista móvil dedicada al editar contenido de correo electrónico. Esto le permite perfeccionar el diseño interactivo de un mensaje de correo electrónico editando por separado todas las opciones de estilo para la visualización móvil, como la adaptación de márgenes, el tamaño de fuente más pequeño, el color de fondo diferente, etc.</p><p> For more information, refer to the <a href="../../designing/using/about-email-content-design.md#switching-to-mobile-view">detailed documentation</a>.</p> </td> 
  </tr> 
  <tr> 
   <td> In-App Messaging Beta Improvements<br /> </td> 
   <td> <p>La función beta de mensajería en la aplicación se ha mejorado con las siguientes capacidades:</p> 
    <ul> 
     <li> El canal beta de la aplicación es compatible con el RGPD </li> 
     <li> Integración con las API de Analytics para rellenar los menús desplegables Activadores </li> 
     <li> Aspecto intuitivo y descripción de plantillas de envío </li> 
     <li> Mejoras en la interfaz de creación desde el punto de vista de uso </li> 
    </ul> <p>For more information, refer to the <a href="../../channels/using/about-in-app-messaging.md">detailed documentation</a>.</p> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* Una nueva opción de la actividad Cargar datos ahora permite aplicar una etapa posterior al procesamiento al archivo que contiene los registros rechazados (por ejemplo: Compresión de formato Zip). (CAMP -24521)
* Ahora, una nueva opción de la actividad Actualizar datos permite configurar el tamaño máximo de lote para la carga de los datos. (CAMP -28400)
* Se ha mejorado la selección de estado de la dirección de los perfiles. Al seleccionar un país, la lista desplegable "Estado" se actualiza automáticamente con valores de estados relevantes. (CAMP -28874)
* Ahora, una nueva opción de la actividad de extracción de archivos impide generar un archivo si la transición de entrada está vacía. Esto evita la creación y carga de archivos vacíos en servidores SFTP.
* Se ha mejorado el informe de resumen de envío.
* La lista de países disponibles al definir la dirección de un perfil se ha enriquecido. (CAMP -26707)
* Ahora aparece un mensaje de error al intentar importar un flujo de trabajo integrado.

### Email Designer {#email-designer}

* Se ha corregido un problema que habilitaba la capacidad de unidad geográfica en una plantilla de correo electrónico o un fragmento de contenido creado con el correo electrónico de Designer, aunque esta capacidad estuviera desactivada en Adobe Campaign, lo que hacía que la plantilla o el fragmento no estuvieran disponibles al intentar volver a acceder. (CAMP -28174)
* Se ha corregido un problema que impedía guardar las condiciones de contenido dinámico al editar contenido con el Correo electrónico de Designer. (CAMP -27905)
* Se ha corregido un problema que eliminaba la versión HTML del contenido de correo electrónico tras editar la versión de texto sin formato de un mensaje y dividir la sincronización HTML en el correo electrónico de Designer. (CAMP -28507)
* Se ha corregido un problema que impedía que la interfaz de Email Designer se abra al utilizar Internet Explorer 11. (CAMP -28273)
* Se ha corregido un problema que distorsionaba el procesamiento de estilos de estilo de Microsoft Outlook aplicado a botones con el correo electrónico de Designer.
* Se ha corregido un problema en el mensaje de correo electrónico de Designer que hacía editable una URL desde un fragmento de contenido utilizado en un mensaje de correo electrónico, lo que no era posible cuando el fragmento estaba bloqueado de forma predeterminada.
* Se ha corregido un problema que impedía que el componente divisor de Email Designer se mostrara en Microsoft Office.
* Se ha corregido un problema que provocaba un bloqueo de página en determinados exploradores de Internet al ver un contenido sincronizado desde AEM mediante el editor de contenido de correo electrónico heredado. (CAMP -29068)
* Se ha corregido un error que se producía al hacer clic en cualquier imagen de un mensaje de correo electrónico al utilizar el editor de contenido de correo electrónico heredado. (CAMP -30424)
* Se ha corregido un problema que impedía que se mostraran los fragmentos recién creados al editar un correo electrónico con el correo electrónico de Designer. (CAMP -29928)
* Se ha corregido un problema que impedía que el texto del botón se mostrara correctamente en correos electrónicos creados con el Designer de correo electrónico y se recibiera mediante el cliente de correo web de Outlook.
* Ahora es posible crear mensajes transaccionales de perfil mediante el correo electrónico de Designer. (CAMP -28900)
* Se ha corregido un error en Designer Designer que provocaba que el contenido se editara al recuperar contenido de una URL automáticamente al momento de la preparación, mientras que debería bloquearse.

### Patches {#patches-2}

* Se ha corregido un problema que mostraba registros de entrega incorrectos en Informes dinámicos. (CAMP -23446)
* Se ha corregido un problema que podía afectar a los números del informe Resumen de devoluciones (CAMP -28703)
* Fixed an issue with the Campaign and Assets Core Service integration which could prevent assets from being displayed when selecting **[!UICONTROL Image shared from Adobe Experience Cloud]** in an email (CAMP-28732).
* Se ha corregido un problema que impedía que los mensajes SMS que contenían el carácter «off» se enviaran aunque la transliteración estuviera autorizada en la cuenta externa SMPP. (CAMP -29041)
* Se ha corregido un problema que podía mostrar registros duplicados al usar una actividad de segmentación en flujos de trabajo. (CAMP -28743)
* Se ha corregido un problema que impedía eliminar una de las asignaciones de valores en una columna en una actividad de flujo de trabajo. (CAMP -28708)
* Se ha corregido un problema en la actividad de transferencia de archivos, al utilizar comodines con la opción «Probar si existe el archivo». (CAMP -28977)
* Se corrigió un problema en la actividad de Transferencia de archivos que se podía producir al actualizar la configuración de cuenta externa. (CAMP -28894)
* Se ha corregido un problema con los filtros personalizados en el editor de consultas al utilizar la condición «Correo electrónico no está vacía». (CAMP -28741)
* Se ha corregido un problema que se podía producir al exportar tablas de recursos personalizados con más de 100 k registros. (CAMP -28150)
* Se ha corregido un problema que impedía eliminar mensajes transaccionales vinculados a activadores. (CAMP -28385)
* Se eliminaron las contraseñas que se mostraban incorrectamente en algunos registros SMS.
* Se ha corregido un problema que provocaba que las conexiones al simulador SMPP fallaran debido a la contraseña vacía enviada por Adobe Campaign.
* Se ha corregido un problema que impedía enviar campañas cuando las conexiones SMS estaban inestables.
* Se ha corregido un problema que mostraba entregas eliminadas en informes dinámicos.
* Se ha corregido un problema que impedía recuperar datos adicionales de registros de entrega, registros de seguimiento y tablas de registros de exclusión al usar una actividad de enriquecimiento en un flujo de trabajo.
* Se corrigió un problema con el RGPD que eliminaba las solicitudes que se podían producir al usar un tipo de vínculo "N cardinalidad de vínculo de recopilación" y que la opción "Eliminar el registro de destino implica eliminar referencias de registros por el vínculo".
* Se ha corregido un problema con el uso compartido de informes.
* Se ha corregido un problema que podía producir problemas de rendimiento al enviar una notificación Push.
* Se ha corregido un problema con los archivos de salida de correo directo que faltan campos.
* Se ha corregido un problema que permitía a los usuarios modificar flujos de trabajo integrados.
* Se ha corregido un problema al crear una campaña basada en una plantilla de campaña, que incluía un flujo de trabajo con una actividad de extracción configurada. (CAMP -29198)
* Se ha corregido un problema con la actividad de extracción de archivos que impedía utilizar la misma expresión para varios elementos. (CAMP -29182)
* Se ha corregido un problema, en el editor de consultas, con la condición de unión entre el registro broadlog y el registro de seguimiento de rtevent. (CAMP -28780)
* Se ha corregido un problema que impedía guardar las modificaciones en la opción de página de aterrizaje «Acción específica». (CAMP -29422)
* Se ha corregido un problema que impedía exportar la carga útil de un evento en un flujo de trabajo. (CAMP -29029)
* Se ha corregido un problema que impedía excluir números SMS bloqueados en un mensaje SMS. (CAMP -28898)
* Se ha corregido un problema que impedía que los proveedores SMPP se notificaran en caso de error al procesar mensajes entrantes. (CAMP -29804)
* Se ha corregido un problema que permitía eliminar cuentas externas con entregas asociadas. (CAMP -29738)
* El proceso de envío se ha mejorado y estabilizado para los mensajes SMS.
* Se ha corregido un problema que impedía que el carácter " ~" se usara en un mensaje SMS. (CAMP -29172)
* Se ha corregido un problema en los envíos con la opción de optimización de tiempo de envío. (CAMP -29231)

