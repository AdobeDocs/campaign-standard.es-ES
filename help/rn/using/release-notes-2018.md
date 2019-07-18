---
title: Notas de revisión 2018
seo-title: Notas de revisión 2018
description: Notas de revisión 2018
seo-description: Esta página enumera todas las versiones de Adobe Campaign Standard 2018.
page-status-flag: no activado nunca
uuid: 99 f 92 a 54-4 b 3 d -48 b 9-b 08 d-e 98 b 24 e 75 f 62
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versiones estándar de campaña
discoiquuid: e 54 f 8305-7 e 32-4193-8 e 5 a-b 5 d 87 b 03038 c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6a877d878f01fa1e541dc20b8b0941602113d15b

---


# Release Notes 2018{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard en 2018?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 18.9 - September 2018 {#release-18-9---september-2018}

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
   <td> In-App messaging (beta)<br /> </td> 
   <td> La mensajería en la aplicación le permite interactuar con usuarios de aplicaciones móviles de forma más eficaz proporcionando interacción contextual y permitiendo a los usuarios que hayan excluido las notificaciones Push. Utilice la mensajería en la aplicación junto con las notificaciones Push para crear una experiencia relevante y altamente personalizada. Esto lleva a una mejor conversión y retención de los usuarios de la aplicación.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/about-in-app-messaging.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Launch integration for mobile apps (beta)<br /> </td> 
   <td> La integración de Adobe Launch con Adobe Campaign ahora simplifica y automatiza el proceso de activación de la propiedad de la aplicación móvil en Campaign con el SDK de Mobile V 5.<br /> Para obtener más información, consulte la documentación <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements}

* Adobe Campaign Standard ahora admite la versión 4 de la API de Amazon S 3.

### Other changes {#other-changes}

* En los gráficos Broadlogs, ahora existe una distinción entre el número máximo de conexiones y el número máximo de mensajes por hora. Cuando se alcanzan los límites, es posible saber por qué el rendimiento es limitado. Anteriormente, el mismo mensaje (' cuota cumplida ') se aplicaba a ambos casos.
* Al configurar una aplicación móvil en Campaign, el usuario puede saber si el certificado iOS y la clave del servidor Android se han cargado correctamente y su fecha de caducidad.

   For more on this, refer to the detailed documentation on how to configure a mobile application using [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) and [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* Diríjase a usuarios de una aplicación móvil específica seleccionando una aplicación móvil mientras define las propiedades de campaña. Esta función es tanto para los canales Push como para la mensajería en la aplicación.

   For more information, refer to the [detailed documentation](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Al seleccionar un bloque de contenido con la interfaz de Creative Designer, ahora se cargan y muestran todos los bloques de contenido de la lista. (CAMP -27311)

   For more on this, refer to the [detailed documentation](../../designing/using/adding-a-content-block.md).

### Patches {#patches}

* Se ha corregido un problema que mostraba una discrepancia en los recuentos de registros entre el panel de correo electrónico y el informe de resumen de correo electrónico para los correos electrónicos transaccionales. (CAMP -28237
* Se ha corregido un problema en los flujos de trabajo que podía mostrar un mensaje de error al importar un archivo mediante una actividad de transferencia de archivos. (CAMP -27435)
* Se ha corregido un problema con las páginas de aterrizaje que contenían más de 25 servicios, que hacía que los servicios se anularan de forma aleatoria en el formulario. (CAMP -26572)
* Se ha corregido un problema en los flujos de trabajo que impedía configurar cuentas externas con una URL de SFTP al utilizar la actividad de transferencia de archivos. (CAMP -26475)
* Se ha corregido un problema que impedía que se actualizara el informe de resumen de servicios. (CAMP -26301)
* Se ha corregido un problema en los flujos de trabajo al usar una actividad de enriquecimiento que impedía que un campo personalizado mostrara la fecha correcta. (CAMP -26242)
* Se ha corregido un problema que impedía que se actualizaran las fechas de suscripción al servicio al importarlas mediante una importación de archivo.
* Se ha corregido un error con la actividad de carga de archivos que impedía que los flujos de trabajo importaran archivos (CAMP -27068).
* Se ha corregido un problema que mostraba el número incorrecto de suscripciones en los informes de resumen de Servicio (CAMP -25587).
* Se ha corregido un problema de discrepancia de datos entre los informes de Adobe Analytics y Adobe Campaign. (CAMP -25393)
* Se ha corregido un problema que impedía que un usuario de acceso limitado iniciara sesión. (CAMP -27381)
* Se ha corregido un problema que impedía que se mostrara la lista de contenido de Adobe Experience Manager al editar un correo electrónico con Creative Designer. (CAMP -27181)
* Se ha corregido un problema que podía impedir que se abriera Creative Designer, lo que provocaba un error. (CAMP -27304)
* Se ha corregido un problema que impedía que la función de arrastrar y soltar funcionara correctamente en Creative Designer al utilizar Internet Explorer 11.
* Se ha corregido un problema que provocaba que las imágenes cargadas desde una cámara y toma en modo vertical se mostraran en una posición girada no deseada.
* Se ha corregido un problema que mostraba información de selección no clara al utilizar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que impedía duplicar correctamente un elemento al utilizar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que seguía enviando mensajes SMS a destinatarios bloqueados, aunque se habían cancelado la suscripción a través de una respuesta automática. (CAMP -27128)
* Fixed an issue that prevented displaying the errors that caused the **Database Cleanup** workflow to fail. (CAMP -26876)
* Se ha corregido un problema que impedía eliminar campos personalizados en una definición de notificación push. (CAMP -25588)

## Release 18.7 - July 2018 {#release-18-7---july-2018}

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
   <td> High priority flag for Android push notifications<br /> </td> 
   <td> Indicador de prioridad alta para Android: habilita la entrega de una notificación Push con alta prioridad para las aplicaciones de Android, lo que hace que el dispositivo dormir se despierta y ejecute un procesamiento limitado. Tenga en cuenta que la prioridad predeterminada es Normal, lo que podría retrasar la entrega del mensaje para guardar la batería. <br /> Para obtener más información, consulte la documentación <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Typology filter for mobile app subscribers<br /> </td> 
   <td> Suscripciones de compatibilidad en el filtro de tipología: Al especificar los criterios de filtro para una regla de tipología, se pueden seleccionar suscripciones de aplicación como dimensiones de filtrado y destino, lo que permite filtrar atributos para los usuarios con o sin perfil. <br /> Para obtener más información, consulte la documentación <a href="../../administration/using/about-typology-rules.md#typology-rules">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Automated content import from a URL during message preparation<br /> </td> 
   <td> Ahora es posible importar contenido de correo electrónico desde una dirección URL durante la fase de preparación. Para envíos recurrentes de correo electrónico, el contenido HTML más reciente se recupera cada vez que el mensaje está preparado para garantizar que el contenido esté siempre actualizado al momento de enviarse el correo electrónico. Esta función también permite crear una entrega programada con contenido desde una URL aunque el contenido aún no esté listo.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/importing-content-from-a-url.md#retrieving-content-from-a-url-automatically-at-preparation-time">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Campaign release notification message<br /> </td> 
   <td> Ahora aparece un mensaje emergente cuando un usuario inicia sesión después de actualizar la instancia a una nueva versión. El mensaje indica el número de versión e incluye un vínculo a las notas de la versión. You can choose to hide the message until the next release. <br /> </td> 
  </tr> 
  <tr> 
   <td> User management<br /> </td> 
   <td> La capacidad de unidad geográfica no está disponible para las nuevas instancias de Campaign Standard, al igual que las instancias existentes sin unidades geográficas creadas, comenzando la versión 18.7.<br /> Para obtener más información, consulte esta <a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html">página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-1}

* The Adobe Campaign and Adobe Target integration now allows you to leverage Target’s [Permissions](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) feature. Al incluir una imagen dinámica de Adobe Target en un correo electrónico, ahora puede especificar una propiedad de Target (código de at_ property).
* Los recursos personalizados que tienen un vínculo owncopy al recurso de perfiles ahora son tomados en cuenta por el acceso de la privacidad GDPR o las solicitudes. Para 1 de los vínculos sencillos y de la colección N cardinalidad, es necesario seleccionar "Eliminar/duplicar el registro de destino implica eliminar o duplicar los registros a los que hace referencia el vínculo" en el recurso personalizado. Para vínculos simples 0 o 1 cardinalidad, seleccione "Eliminar/duplicar el registro implica eliminar o duplicar el registro de destino al que hace referencia el vínculo".

### Other changes {#other-changes-1}

* El tiempo de espera de uso compartido de informes ha aumentado de uno a cuatro minutos para evitar cualquier error de tiempo de espera.
* Al editar el contenido de un correo electrónico, se abre de forma predeterminada el nuevo Creative Designer. Si lo desea, puede volver al editor de contenido predeterminado en cualquier momento después de guardar los cambios. For more on this, refer to the [detailed documentation](../../designing/using/about-email-content-design.md).
* En Creative Designer, ahora se puede añadir un nuevo componente de contenido a un mensaje de correo electrónico: el carrusel. For more on this, refer to the [detailed documentation](../../designing/using/defining-the-email-structure.md#about-content-components).
* In a transactional message hot click report, when you click the **Change profile** button, now only the test profiles linked to the event that you defined for your transactional message are listed.

### Patches {#patches-1}

* Se ha corregido un problema con el filtro de consulta byemail que no devolvía ningún resultado. (CAMP -23420)
* Se ha corregido un problema que permitía a un usuario estándar acceder a determinadas funciones o pantallas restringidas a administradores (/puntos finales/encabezado/*, pantallas de mensajes transaccionales, perfiles y audiencias importadas).
* Se ha corregido un problema que impedía que la privacidad GDPR se eliminara de los recursos personalizados si su nombre empezaba por un número.
* Se ha corregido un error que impedía que la actividad Guardar audiencia compartiera los suscriptores de la aplicación en Adobe Experience Cloud.
* Se ha corregido un problema con la actividad de Transferencia de archivos que podía producirse cuando el nombre del archivo contenía espacios en blanco. (CAMP -25936)
* Se corrigió un problema que se podía producir al utilizar el botón de reconexión después de que caduca una sesión. (CAMP -25560)
* Se ha corregido un problema que podía llevar a exclusiones al enviar entregas con la optimización de zona horaria asociada a reglas de fatiga. (CAMP -25425)
* Se ha corregido un problema que se producía al usar la función GDPR de API, que impedía eliminar datos con un vínculo de tipo 0-1.
* Se ha corregido un problema que podía provocar un mensaje de error al cancelar la edición de una regla de tipología de fatiga.
* Se ha corregido un problema que se podía producir al obtener una vista previa de un contenido de entrega después de editarlo.
* Se ha corregido un problema que se podía producir al procesar archivos zip CSV al utilizar la opción Descompresión.
* Se ha corregido un problema en Creative Designer que provocaba un formato y fuente de color no deseados al cambiar texto con estilo incrustado a un vínculo o al editar dicho vínculo. (CAMP -26001)
* Se ha corregido un problema que impedía que el informe de clics dinámicos mostrase los porcentajes de cada condición en entregas que contenían contenido dinámico. Anteriormente, solo se mostraban los clics en la variante predeterminada.

## Release 18.6 - June 2018 {#release-18-6---june-2018}

### Improvements {#improvements-2}

* **[!UICONTROL History]** La API se ha agregado a Adobe. IO. Permite acceder a información relacionada con el historial de marketing de un perfil: número de touchpoints, envíos enviados, URL de página reflejada, etc. For more on this, refer to the [dedicated use case](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) .
* The **[!UICONTROL Database cleanup]** technical workflow has been optimized in order to ensure better performance for database backup.
* Ahora, Creative Designer para correo electrónico también está disponible en francés y alemán.

### Other changes {#other-changes-2}

* A **[!UICONTROL Compute stats]** button has been added in the **[!UICONTROL Deployment]** window of sent deliveries. Permite recuperar los KPI más recientes, por ejemplo, si los resultados del envío tardan demasiado en actualizarse o no se han tenido en cuenta. For more on this, refer to this [section](../../sending/using/confirming-the-send.md).
* In the **Update for deliverability** out-of-the-box technical workflow, functional administrators can now define the number of consecutive errors to ignore in the **Update rules** javascript activity. De forma predeterminada, el valor del campo se define como 0, lo que significa que se ignorarán todos los errores.
* Se ha optimizado el SQL generado al administrar las condiciones de restricción de acceso a unidades.
* The **[!UICONTROL Update]** activity now allows you to add, update or delete data related to subscriptions (nms:appSubscriptionRcp table).
* The **[!UICONTROL Update delivery execution]** technical workflow has been divided into two workflows in order to optimize performance: - **[!UICONTROL Update delivery execution]**: updates the delivery's tracking. Se inicia cada 10 minutos de forma predeterminada. **[!UICONTROL Update delivery indicators]**: actualiza los KPI de la entrega, se inicia cada hora de forma predeterminada. For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* When a delivery is sending messages, the status in the **[!UICONTROL Deployment]** section can now have two values: **[!UICONTROL Sending]**: the messages are being sent. **[!UICONTROL Sending (retry)]**: se está realizando un paso de reintento.
* Users with the **[!UICONTROL Delivery preparation]** role are now able to send proofs. (CAMP -24313)
* The **Enable TLS over SMPP** option has been added to the **SMS routing via SMPP** external account. For more on this refer to this [section](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing).

### Patches {#patches-2}

* Se ha corregido un problema que impedía que se enviaran correos electrónicos al incluir una imagen dinámica desde Adobe Target (CAMP -24848).
* Fixed an issue with the **[!UICONTROL Privacy Access/Delete Request]** technical workflows, which did not complete if any of the requests failed.
* Se ha corregido un problema que impedía que el servicio de Privacidad Core reciba actualizaciones de estado de solicitud desde Campaign.
* Se ha corregido un problema que impedía que el flujo de trabajo técnico **[!UICONTROL Import shared audience]** funcionara correctamente (CAMP -25465).
* Se ha corregido un problema que impedía que las solicitudes de privacidad de campaña se marcaran como finalizaban en el servicio de privacidad principal.
* Se ha corregido un problema que impedía que determinados usuarios iniciaran sesión en Campaign Standard a través de la autenticación IMS cuando el ID de Adobe era demasiado largo. (CAMP -24095)
* Se ha corregido un problema en Creative Designer que podía producirse al eliminar módulos de contenido. (CAMP -25242)
* Se ha corregido un problema al usar reglas de fatiga de notificaciones push para suscriptores sin perfil en la base de datos. (CAMP -25344)
* Se ha corregido un problema que podía mostrar un mensaje de error al acceder a registros de exclusión de entregas. (CAMP -24724)
* Se ha corregido un problema que impedía que las pruebas se preparasen en instancias con registros de envío extendidos.
* Fixed two issues that could occur when publishing custom resources with the **[!UICONTROL Sending log]** extension activated.
* Se ha corregido un problema que podía ocurrir con la duración de la entrega no tener en cuenta en entregas recurrentes.
* Fixed an issue that could occur when sorting data in the **[!UICONTROL Client data]** menu, for custom resources with more than 100K records. (CAMP -24308)
* Se ha corregido un problema con dimensiones de perfil personalizadas que no se tenían en cuenta al usar la función de búsqueda en informes dinámicos.
* Se ha corregido un problema con la visualización de datos internacionales para niveles de cuenta en informes dinámicos.
* Ahora es posible crear un servicio sin un mensaje de confirmación de suscripción o cancelación de suscripción.

## Release 18.5 - May 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> GDPR: Core Service Integration<br /> </td> 
   <td> La integración de servicios principales de privacidad permite automatizar las solicitudes RGPD en un contexto de varias soluciones a través de una sola llamada de JSON. <br /> Las solicitudes RGPD insertadas desde el servicio principal de privacidad a todas las soluciones de Experience Cloud ahora son gestionadas automáticamente por Campaign. <br /> Para obtener más información, consulte la documentación <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push improvements - detailed delivery feedback<br /> </td> 
   <td> Ahora, Adobe Campaign ofrece la posibilidad de recibir comentarios detallados (registros de exclusión de registros de inicio de registros) en los mensajes push de los proveedores (APNS/GCM) a través de MCPNS.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs extension<br /> </td> 
   <td> La extensión de registros de entrega permite ampliar los registros de registros con datos de perfil y código de segmento proveniente de flujos de trabajo. Esta información se puede utilizar en Informes dinámicos y permite guardar una instantánea de cierta información al enviar una entrega.<br /> Existen 2 casos de uso más:<br /> 
    <ul> 
     <li> Exporte los gráficos extendidos con datos "congelados": Como especialista en mercadotecnia, me gustaría exportar todos los perfiles donde el código de segmento es igual a "A" (procedente del motor de flujo de trabajo). </li> 
     <li> Segmentation on "frozen" data: As a marketer, I would like to <strong>retarget</strong> all profiles who have won 1000 loyalty points since the last sending or where segment code was equal to "A". </li> 
    </ul> For more information, refer to the <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic reporting with Custom profile data<br /> </td> 
   <td> Esta función permite crear y administrar informes basados en datos de perfil personalizados creados durante la extensión de recursos de perfil. Puede desglosar informes por atributos de perfil como el programa de fidelidad, el canal preferido, etc.<br /> Para obtener más información, consulte la documentación <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Improvements {#improvements-3}

* Se ha mejorado la memoria general y el uso de CPU de la aplicación

### Other changes {#other-changes-3}

* La actividad del flujo de trabajo Leer audiencia ahora puede leer audiencias de Experience Cloud. Anteriormente, esta actividad solo podía leer las audiencias Consulta y Lista. Refer to the [detailed documentation](../../automating/using/read-audience.md). (CAMP -23623)
* El identificador de la fuente de datos compartida predeterminada está ahora en modo de solo lectura y ya no se puede cambiar. Cambiar este identificador podría dar lugar a algunos problemas al compartir audiencias con Experience Cloud.
* La importación de audiencias desde Audience Manager funciona ahora con archivos divididos. Anteriormente, solo el flujo de trabajo técnico importsharedaudience importaba el último archivo del segmento.
* Las cuentas externas de AWS S 3 ahora admiten regiones y el mecanismo de autenticación de la versión 4. Refer to the [detailed documentation](../../administration/using/external-accounts.md).
* La ventana de selección de recursos ahora debe cargarse más rápidamente y permitir seleccionar un recurso, luego salir de la ventana sin ningún problema.
* Los usuarios con derechos de administración pueden modificar las propiedades y estructura de los flujos de trabajo técnicos, y pertenecen a las unidades orgánicas y geográficas "Todas".
* Se han realizado mejoras en la interfaz de actividad de segmentación al crear nuevos segmentos: La ficha Limitación aparece ahora directamente después de agregar una limitación. Ahora se incrementan los nombres de los nuevos segmentos ("Segmento 1", "Segmento 2", etc.).
* Se agrega un campo "nextprocessingdate" al recurso Workflow. Este campo solo es visible a través de llamadas de API REST, ya que permite visualizar flujos de trabajo siguientes fechas de procesamiento.
* El campo "sourceid" ahora se expone en el recurso de registros de seguimiento (nms: Trackinglog).
* Ahora, los valores "Total de aperturas" y "Totales de clics" se pueden exportar en un archivo plano a través de un flujo de trabajo. (CAMP -24186)
* " Inglés - Danmark "está ahora disponible en la lista de idiomas Preferido en perfiles. (CAMP -23728)
* Al utilizar una actividad de segmentación con un vínculo de datos adicionales (targetdata), ahora un mensaje informa de que los datos no están disponibles fuera del flujo de trabajo. Este mensaje aparece al hacer clic en el botón Recuento o Vista previa desde la actividad Segmentación. (CAMP -23651)
* Se han realizado mejoras para optimizar el espacio en disco utilizado por los flujos de trabajo: (CAMP -21979): Los archivos procesados por la actividad «Cargar archivo» ahora se eliminan de forma predeterminada. Una opción le permite mantenerlos para necesidades específicas. Cuando se elimina un flujo de trabajo, su carpeta dedicada se elimina automáticamente del directorio del servidor.

### Patches {#patches-3}

* Se corrigió un problema en el cual algunos eventos de informes sin procesar no tenían eventos de seguimiento asociados porque el campo eventdate no se rellenaba correctamente.
* Se ha corregido un problema que impedía que se mostraran campos personalizados en la ventana de vista previa de un envío de notificaciones Push.
* Se ha corregido un problema que impedía que el texto rodeara el cuerpo del mensaje de una notificación push en la ventana de vista previa.
* Se ha corregido un problema al enviar una entrega de rectángulo desde un flujo de trabajo cuando el destino principal estaba vacío.
* Se ha corregido un problema que impedía acceder a una asignación de objetivo si está vinculada a un esquema no existente.
* Se corrigió un problema que se podía producir al importar un archivo zip a través de una actividad de carga de archivo. (CAMP -24309)
* Se ha corregido un problema que provocaba un error postgresql al enviar un envío recurrente. (CAMP -23613)
* Se ha corregido un problema que mostraba un mensaje de error al enviar una solicitud de REST de REST con un atributo JSON vacío. (CAMP -23506)
* Se ha corregido un problema en los perfiles que configuraban en mayúsculas los caracteres que siguen al carácter "ß". (CAMP -23136)
* Se ha corregido un problema al enviar entregas utilizadas con la condición de elegibilidad de un bloque de contenido dinámico o personalizado al utilizar atributos de un esquema vinculado del perfil. (CAMP -22751)
* Se ha corregido un problema que impedía eliminar servicios. (CAMP -22050)
* Se ha corregido un problema que impedía cambiar los valores de País o Estado en un perfil de Prueba. (CAMP -20426)
* Se ha corregido un problema que podía impedir que se cargara Creative Designer. (CAMP -24573)
* Se ha corregido un problema que eliminaba caracteres agregados después de campos de personalización en el asunto del mensaje de correo electrónico. (CAMP -24113)

## Release 18.4 - April 2018 {#release-18-4---april-2018}

### Patches {#patches-4}

#### Platform {#platform}

* Se ha corregido un error que impedía procesar correctamente el acceso al RGPD o eliminar solicitudes. Este comportamiento se ha observado en algunos casos en los que los datos extraídos contenían uno de los siguientes caracteres: &amp; &lt; &gt; "'.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* Se ha corregido un problema que podía provocar que los KPI se sobrescribían con valores incorrectos si la sincronización de Broadlog tardaba más de una hora.

#### Workflows {#workflows}

* Se ha mejorado la administración de memoria y el rendimiento optimizado en los flujos de trabajo.

#### Reporting {#reporting}

* El flujo de trabajo de compartir KPI ahora recupera los valores de entrega de los últimos 2 meses en lugar de los últimos 6 meses. Se ha corregido un problema con el uso compartido de KPI de cuentas externas que mostraban fechas truncadas.
* Fixed an issue which could lead to certain messages not being taken into account in **Sent**, **Delivered** and **Bounce** metrics.
* Fixed an error which occurred when the chosen time range in the **Delivery Summary Report** was too long.

#### Custom resources {#custom-resources}

* Se ha corregido un error que provocaba errores en la preparación de recursos personalizados.

## Release 18.3 - March 2018 {#release-18-3---march-2018}

### New capabilities {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> EU General Data Protection Regulation (GDPR)<br /> </td> 
   <td> El RGPD es la nueva ley de privacidad de la Unión Europea que armoniza y moderniza los requisitos de protección de datos a partir del 25 de mayo de 2018. El RGPD se aplica a los clientes de Adobe Campaign que contienen datos para los sujetos de datos que residen en la UE.<br /> Además de las capacidades de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), estamos tomando esta oportunidad en nuestro rol como procesador de datos para incluir capacidades adicionales, para facilitar su preparación como controlador de datos para ciertas solicitudes RGPD:<br /> 
    <ul> 
     <li> Derecho a acceso: permite que los datos reciban una copia de sus datos personales capturados por Controladores de datos, incluyendo potencialmente datos almacenados en Adobe Campaign. </li> 
     <li> Derecho a eliminar: da derecho al sujeto de datos a que los controladores de datos borren sus datos personales, incluso los datos almacenados en Adobe Campaign. </li> 
    </ul> For more information, refer to the <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer for Email (Beta)<br /> </td> 
   <td> El nuevo Creative Designer de Adobe Campaign ofrece una experiencia de creación completamente integrada en Campaign, lo que permite la creación visual rápida y sin esfuerzo de mensajes de correo electrónico personalizados y personalizados sin necesidad de crear secuencias de comandos con una sola línea de código. A través de la poderosa interfaz de arrastrar y soltar, Creative Designer ayuda a escalar la creación de correo electrónico, ya sea que los usuarios comiencen a partir de una pizarra en blanco o aproveche los fragmentos o plantillas de contenido existentes. <br /> Las funciones clave incluyen:<br /> 
    <ul> 
     <li> Diseñe y cree correos electrónicos totalmente personalizados y adaptables a través de una interfaz de arrastrar y soltar, ampliada por integraciones nativas de Creative Cloud </li> 
     <li> Cree y guarde una plantilla de contenido de correo electrónico y aproveche las plantillas guardadas para ayudar a escalar la creación de correo electrónico </li> 
     <li> Cree y guarde fragmentos de contenido (como encabezado, pie de página, artículo, etc.) para racionalizar la creación de contenido y garantizar la coherencia de la marca </li> 
     <li> Cambiar sin problemas la creación en la interfaz de arrastrar y soltar y editar directamente HTML de un mensaje de correo electrónico al hacer clic en un botón </li> 
    </ul> Creative Designer para correo electrónico solo está disponible en inglés.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/about-email-content-design.md#about-the-email-designer">detallada</a> y vea este <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multilingual Push Deliveries<br /> </td> 
   <td> La misma interfaz multilingüe simple, que ya existe en los canales Correo electrónico y SMS, se ha agregado al canal Push ayuda a captar a los clientes sin importar su idioma preferido.<br /> Esta capacidad ofrece una solución escalable y automática para clientes que administran campañas Push que abarcan varias regiones y desean dirigir a los usuarios en su idioma preferido. Permite cargar todas las variantes lingüísticas a través de una hoja de cálculo con plantillas a una sola entrega Push, con un solo clic. A continuación, Adobe Campaign realiza una segmentación automática según la preferencia de idioma de los usuarios, lo que ayuda a reducir las redundancias simplifican los flujos de trabajo y los informes.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/creating-a-multilingual-push-notification.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Use of Custom Resources in Transactional Messaging<br /> </td> 
   <td> Además de los campos predeterminados, los mensajes transaccionales ahora permiten utilizar recursos personalizados para enriquecer el contenido de los mensajes.<br /> Por ejemplo:<br /> 
    <ul> 
     <li> Aproveche los campos personalizados como criterio de reconciliación para coincidir con un mensaje de transacción a un perfil </li> 
     <li> Aproveche los perfiles completos, los servicios y los datos vinculados para personalizar más los mensajes transaccionales </li> 
    </ul> For more information, refer to the <a href="../../administration/using/configuring-transactional-messaging.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### Platform {#platform-1}

* Se ha corregido un problema que impedía exportar más de 5000 registros de una lista.
* Se ha corregido un problema que se producía al exportar datos a los archivos con campos de personalización.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* Se ha corregido un problema que provocaba que el SMS de varias partes se truncara porque el tamaño de las partes se calculaba en caracteres en lugar de bytes.
* Added an option which allows the **[!UICONTROL Delivered]** or **[!UICONTROL Bounces + Errors]** KPIs to be updated in real time after sending your delivery. Se recalculan directamente desde la SR (Informe de estado) recibida del proveedor.
* Se ha corregido un problema con la utilidad Calendario en el programador de envío.
* Se ha corregido un problema de visualización al abrir un objetivo por segunda vez en una entrega enviada.
* Se ha corregido un problema que provocaba un mensaje de error que solicitaba una fecha de inicio al crear una plantilla de correo electrónico con una fecha de envío retrasada.
* Se ha corregido un problema que podía provocar problemas de procesamiento de imágenes al editar el contenido de una entrega.
* Se ha corregido un problema con las pruebas al duplicar una campaña.
* Se ha corregido un problema que provocaba un mensaje de error al acceder a una plantilla de campaña a través de la barra de navegación, después de agregar una entrega al flujo de trabajo.
* Se ha corregido un problema que podía impedir que se seleccionara automáticamente el ganador de un correo electrónico de prueba A/B, lo que provocaba que no se enviara el correo electrónico. This behavior could occur if the delivery was in **[!UICONTROL retryInProgress]** state.
* Se ha corregido un problema que podía provocar que apareciera un mensaje de error al volver a abrir los parámetros de un correo electrónico de prueba A/B.

#### Audiences &amp; queries {#audiences-e-queries}

* Se ha corregido un problema que impedía acceder a datos y configurar consultas de destinatarios replicados de Adobe Campaign Classic a Standard.
* Fixed an issue that occurred when using a filter type field in the query editor, after using the **Count** or **Preview** buttons.

#### Workflows {#workflows-1}

* The **Billing** workflow has been optimized to improve the delivery preparation delay.
* Se ha corregido un problema que impedía que los datos de población se mostraran en una transición saliente al utilizar una actividad de envío recurrente.
* Fixed an issue that prevented reject records from being displayed in a transition after an **Update data** activity.
* Fixed an issue which could cause the **deliverabilityUpdate** technical workflow to fail.

#### Integrations {#integrations}

* Se ha corregido un problema que impedía que los caracteres internacionales se enviaran correctamente a Adobe Analytics.
* Los recursos ahora deben cargarse más rápido al intentar insertar una imagen de la biblioteca de recursos de Experience Cloud en un mensaje.
* Se ha corregido un problema que impedía que la ventana de selección de recursos se cerrara en algunos casos.
* Desde un detalle de fuente de datos, ahora puede acceder directamente a su flujo de trabajo relacionado para comprobar el estado del flujo de trabajo.
* Ahora puede actualizar el esquema Activadores directamente al definir o editar un evento desencadenador. Con este cambio, ya no tendrá que cancelar la publicación y crear otra.

#### Transactional messages {#transactional-messages}

* Se ha corregido un error con la plantilla de mensaje transaccional cuando se extendía el recurso de entrega.
* Ahora es posible eliminar mensajes transaccionales.

## Release 18.2 - February 2018 {#release-18-2---february-2018}

### New capabilities {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Subscription - subscribe or unsubscribe a list of profiles to multiple services<br /> </td> 
   <td> The <strong>Subscription Services</strong> workflow activity now allows you to subscribe or unsubscribe a list of profiles to multiple services. En el flujo de trabajo, importe un archivo que contenga los perfiles y, para cada perfil, el tipo de operación y el servicio. The <strong>Subscription Services</strong> activity will be able to use this information and handle dynamically all your profiles subscriptions and unsubscriptions at once.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/subscription-services.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Enrichment activity - enrich data based on previous transitions<br /> </td> 
   <td> The new <span class="uicontrol">Enrichment</span> workflow activity allows you to leverage the inbound transitions and complete the output transition with additional data. Si segmenta perfiles, la actividad de enriquecimiento le permite enriquecer la información de los perfiles con datos adicionales que no se almacenan en la base de datos (por ejemplo, de un archivo importado).<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/enrichment.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### Platform {#platform-2}

* La barra superior de la interfaz de Adobe Campaign se ha actualizado con el nuevo menú Experience Cloud.
* Fixed an issue which prevented the link to **[!UICONTROL Offers]** from being displayed in the solution dropdown list.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* La fase de preparación de la entrega se ha mejorado para mejorar el rendimiento.
* Se han corregido varios problemas que podrían dañar los registros de seguimiento en algunas situaciones de nicho.
* Se ha corregido un problema de actualización de fecha de contacto que se producía cuando se cambiaba la fecha de contacto entre la preparación y la confirmación de la entrega. Ahora, cuando cambie la fecha de contacto después de la preparación, debe volver a preparar la entrega antes de poder confirmar el envío. See the [detailed documentation](../../sending/using/preparing-the-send.md).

#### Push notifications {#push-notifications}

* Se ha corregido un error que impedía que algunos campos de personalización funcionaran en notificaciones push de iOS.
* Se ha corregido un error que mostraba las tasas de clics y abiertas como 0% en el panel de notificaciones Push.

#### Reports {#reports}

* Se ha corregido un error que mostraba la lista de informes como vacía en algunos exploradores.
* Fixed an error that occurred in the **[!UICONTROL Report sharing]** technical workflow just before its expiration limit was reached.

#### Workflows {#workflows-2}

* Se ha corregido un problema que impedía a las actividades ser accesibles después de arrastrarlas y soltarlas.
* Fixed an issue that could cause the order of output transitions of a **[!UICONTROL Segmentation]** activity to change in some situations.
* Se ha corregido un error que se producía al leer una audiencia que contenía un campo de tipo de enumeración y que anteriormente se había guardado desde un flujo de trabajo.
* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain checked even after unchecking it when defining the scheduling properties of a delivery created in a workflow.
* Automatic removal of duplicate rows (DISTINCT clause) can now be disabled in **[!UICONTROL Query]** activities, via a new option located in the **[!UICONTROL Additional data]** tab. Se recomienda desactivar esta opción al definir muchos (más de 100) elementos adicionales, por motivos de rendimiento.

#### Integrations {#integrations-1}

* Some improvements were made to the **[!UICONTROL Data sources]** configuration screen.

### Known issues {#known-issues}

Recomendamos no utilizar Internet Explorer versión 11 debido a posibles problemas de visualización.

Pueden producirse algunos problemas al utilizar vínculos de ayuda contextuales desde la interfaz de Campaña. Se solucionarán en 18.3.

## Release 18.1 - January 2018 {#release-18-1---january-2018}

### New capabilities {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reporting for Fatigue Management<br /> </td> 
   <td> Informar para administración de fatiga es un informe dedicado y configurable que muestra el impacto que las reglas de fatiga tienen en las entregas entre los canales Correo electrónico, Push, SMS y Correo directo dentro de un intervalo de fechas especificado antes de enviar. Con la perspectiva agregada de poder ver rápidamente todas las campañas en conflicto en una sola vista, los especialistas en mercadotecnia pueden planificar las campañas de mercadotecnia de acuerdo con el establecimiento de reglas de fatiga de forma más eficaz y priorizar las comunicaciones.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Report sharing<br /> </td> 
   <td> Compartir informes permite compartir los informes con los usuarios de Adobe Campaign como un adjunto de correo electrónico, incluso de forma automática y automática. Los usuarios que reciben informes recurrentes pueden cancelar la suscripción de estas comunicaciones a través de un vínculo dedicado en cada correo electrónico.<br /> Para obtener más información, consulte la documentación <a href="../../reporting/using/reporting-interface.md#share-tab">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push New capabilities<br /> </td> 
   <td> Vista previa del mensaje push: Obtenga una vista previa de las notificaciones push en dispositivos iOS y Android desde el editor de contenido de notificaciones push para ver exactamente lo que verán los destinatarios antes de probar o ejecutar la entrega.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">detallada</a>.<br /> Contenido disponible: cuando las aplicaciones no se abren durante más tiempo, sus datos pueden quedar obsoletos. Esto hace que los datos deban actualizarse o sustituirse en el momento en que un usuario finalmente abre la aplicación, lo que puede provocar retrasos en el uso de la aplicación. Con la compatibilidad añadida de Contenido disponible, los usuarios de Adobe Campaign pueden despertar su aplicación para actualizar sus datos en segundo plano al enviar una notificación Push, lo que permite mayor coherencia y control sobre la experiencia de un usuario en la aplicación.<br /> Contenido mutable: con la compatibilidad añadida del contenido mutable, los usuarios de Adobe Campaign ahora pueden aprovechar sus extensiones de aplicación móvil para modificar aún más el contenido o la presentación de las notificaciones push entrantes enviadas desde Adobe Campaign. For example, users can leverage Mutable Content to: <br /> 
    <ul> 
     <li> descifrar datos que se entregaron en un formato cifrado </li> 
     <li> descargar imágenes u otros archivos multimedia y agregarlos como archivos adjuntos a una notificación </li> 
     <li> cambiar el cuerpo o el texto del título de una notificación </li> 
     <li> agregar un identificador de subproceso a una notificación </li> 
    </ul> For more information on Content Available and Mutable Content, refer to the <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">detailed documentation</a>.<br /><strong>Advertencia:</strong> Estas actualizaciones en las notificaciones push requieren que los clientes actualicen sus aplicaciones móviles. Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Time-zone optimized deliveries<br /> </td> 
   <td> Programe las notificaciones recurrentes de correo electrónico, SMS y push para que se entreguen en un día y hora específicos en cada zona horaria de los destinatarios, garantizando que los mensajes se entreguen en el momento adecuado sin configurar varias entregas. <br /> Para obtener más información, consulte la documentación <a href="../../automating/using/scheduler.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API Signal activity triggering<br /> </td> 
   <td> Ahora es posible activar una actividad de señal para sus flujos de trabajo directamente desde la API de Adobe Campaign Standard.<br /> Para obtener más información, consulte la documentación <a class="anchorLink" href="https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank">detallada</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### Platform {#platform-3}

* La búsqueda de perfiles se ha optimizado para mejorar el rendimiento.
* El identificador interno de los grupos de seguridad predeterminados está ahora en modo de solo lectura para usuarios estándar.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-3}

* Se ha corregido un problema de visualización que se producía al insertar emojis en el contenido de los envíos.
* Se ha corregido un problema que permitía al usuario acceder al registro cuando el envío todavía estaba en edición.
* The **[!UICONTROL Scheduler]** activity now allows you to send your deliveries depending on the recipient's time zone.
* SMS: The option **[!UICONTROL Store incoming MO]** in the database has been added to external accounts. When checked, all incoming SMS will be stored into the **inSMS** table.
* SMS: Los servicios ahora se adjuntan a un evento en lugar de una plantilla de transacción.
* SMS: El tiempo de espera de conexión SMTP predeterminado se ha reducido a 30 segundos.

#### Push notifications {#push-notifications-1}

* Se ha corregido un error que impedía que las entregas de notificaciones Push se detengan.
* Se ha agregado una opción en las opciones avanzadas de notificación Push para despertar la aplicación con una notificación Push.
* Se ha agregado un botón de pausa para el vídeo de vista previa de notificaciones push.
* La vista previa de notificaciones push está ahora disponible para distintos dispositivos, como iphone, Android y tablets.

   todos los canales

#### Reports {#reports-1}

* Se ha corregido un error que mostraba tasas superiores al 100%.
* Se ha corregido un problema que impedía a los usuarios descargar informes en CSV.
* Added a new **[!UICONTROL Report]** item in the homepage.

#### Workflows {#workflows-3}

* Se ha corregido un problema que provocaba un mensaje de error al utilizar datos adicionales en una consulta y añadir alias que contenían espacios. Los caracteres no alfanuméricos ahora son reemplazados por "_".
* Se ha corregido un problema por el que el flujo de trabajo técnico que calculaba los KPI podía detenerse de forma predeterminada en algunos casos.

#### Profiles and audiences {#profiles-and-audiences}

* Se ha corregido un error que se producía al agregar varios filtros en la consulta de una audiencia.
* Se ha corregido un problema de visualización que se producía al cambiar la imagen de un perfil.
* Se ha agregado una información de objeto con el número exacto de resultado después de contar la población de una consulta.
* Se ha corregido un problema que podía impedir que un usuario seleccionara una audiencia o cerrara la ventana del selector de audiencias.
* Se ha actualizado la lista de funciones disponibles en el editor de expresiones. The **FormatCurrency** and **ConvertCurrency** functions have been removed.

