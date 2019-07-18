---
title: Notas de revisión 2015-2016
seo-title: Notas de revisión 2015-2016
description: Notas de revisión 2015-2016
seo-description: Esta página enumera todas las versiones de Adobe Campaign Standard 2015 y 2016.
page-status-flag: no activado nunca
uuid: d 5 a 0 f 6 cc -0 bed -46 cf -8 dff -1717 fb 624 f 8 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versiones estándar de campaña
discoiquuid: a 3 ce 6 b 80-1858-49 d 1-8880-3543181127 f 4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2015-2016{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard 2015-2016?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 16.11 - November 2016 {#release-16-11---november-2016}

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
   <td> Deliverability exclusion rules<br /> </td> 
   <td> Ahora se administra una lista de supresión global cifrada en la instancia de entrega para evitar quedar bloqueada debido a una actividad malintencionada, especialmente el uso de un reventado.<br /> Para cada envío de correo electrónico, dos reglas de tipología predeterminadas comparan las direcciones de correo electrónico del destinatario con las direcciones o los nombres de dominio prohibidos de esta lista. Si hay una coincidencia, ese destinatario se excluye de la población objetivo.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> General optimization<br /> </td> 
   <td> Esta actualización incluye numerosos cambios y parches que solucionan los problemas de nuestros clientes. The global platform performances have also been optimized. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### General {#general}

* Se han corregido varios problemas de seguridad.
* Se han corregido varios problemas relacionados con campos vacíos o campos duplicados en la API de REST.
* Ahora puede crear mensajes SMS y notificaciones push directamente desde la página principal de la aplicación.

#### Emails and SMS messages {#emails-and-sms-messages}

* Se ha corregido un problema que impedía a los usuarios cargar archivos comprimidos en el editor de contenido.
* Se ha corregido un problema que impedía abrir una prueba después de enviarla.
* Fixed an issue that led to an error message displaying when accessing the **[!UICONTROL Hot Clicks]** report on an A/B test email.
* Fixed an issue that prevented modifications made using the **[!UICONTROL Show source]** mode from being applied.
* Se ha corregido un problema que impedía importar archivos de modelo XML de línea de asunto predictivos.
* A new screen dedicated to importing data for the subject line trained model is now available in **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* Se ha corregido un problema que permitía a los usuarios no administradores editar las máscaras autorizadas en la pantalla de configuración de correo electrónico.

#### Push notifications {#push-notifications}

* Fixed an issue that prevented sending logs and event logs from being displayed for the recipients after sending a push notification using the **[!UICONTROL Send push on profiles]** template.
* Se ha corregido un problema que impedía crear nuevas aplicaciones móviles.

#### Workflows {#workflows}

* Fixed a performance issue that occured when using the **[!UICONTROL Subscription]** activity.
* Se ha corregido un problema que impedía que un flujo de trabajo funcionara cuando su nombre interno contenía un espacio.

#### Integrations {#integrations}

* Fixed an issue that could lead to an error being displayed when using the **Image shared from Adobe Marketing Cloud** option in an email.

#### Custom resources {#custom-resources}

* Se mejoró la vista previa de registro API entre dos publicaciones de campos de API ampliados.
* Se ha corregido un problema que impedía eliminar un recurso personalizado antes de publicarlo.
* Se ha corregido un problema que impedía que se ampliaran los perfiles y que las claves de identificador se establecieran con un campo dinámico.
* Se ha corregido un problema que se podía producir al agregar vínculos en un recurso personalizado.

## Release 16.10 - October 2016 {#release-16-10---october-2016}

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
   <td> Email predictive subject line<br /> </td> 
   <td> Al editar un correo electrónico, una nueva opción le permite probar diferentes líneas de asunto y obtener una estimación de su velocidad abierta antes de enviarla. Esto es posible mediante la capacitación de su propio modelo en función de los datos de entrega anteriores o mediante un modelo predefinido que es específico de su industria. Esta función está disponible para mensajes de correo electrónico y para bases de datos que contienen contenido en inglés solamente. <br /> Para obtener más información sobre cómo habilitar y utilizarlo, consulte la documentación <a href="../../designing/using/personalizing-the-subject-line-of-an-email.md#predictive-subject-line">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> SMS transactional messaging<br /> </td> 
   <td> El canal SMS se ha agregado a las capacidades de mensajes transaccionales de Adobe Campaign. Ahora se admiten dos canales para los mensajes transaccionales: correo electrónico y SMS.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Follow-up message for transactional messaging<br /> </td> 
   <td> Ahora es posible crear un flujo de trabajo dirigido a un evento. Esto significa que puede enviar un mensaje de seguimiento a los clientes que anteriormente recibieron un mensaje de transacción. Puede filtrar el objetivo según el tipo de evento, los registros de eventos y los registros de seguimiento. En el mensaje de seguimiento, podrá aprovechar el contenido del evento (carga útil). <br /> Para obtener más información, consulte la documentación <a href="../../channels/using/follow-up-messages.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extended Profile &amp; Services API<br /> </td> 
   <td> Ahora puede exponer campos ampliados en la API de perfil y servicios. El mecanismo de publicación permite a las API asignar los campos extendidos de los recursos personalizados de perfiles o servicios. For this to work, the <strong>Datamodel</strong> role has been added. Esta nueva función permite al usuario configurar un conjunto de administradores que tendrán acceso al modelo de datos.<br /> Para obtener más información, consulte la documentación <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### General {#general-1}

* Se han corregido varios problemas de seguridad.

#### Emails and SMS messages {#emails-and-sms-messages-1}

* The SMS external account configuration screen ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ) has been improved. Several parameters have been added in the **[!UICONTROL SMSC specifics]** section to support error codes in the "Text" field.

#### Push notifications {#push-notifications-1}

* Fixed an issue that prevented the predefined filters from being displayed when editing the audience of a push notification based on the **[!UICONTROL Send via push notification]** (mobileApp) template.
* The mobile application configuration screen ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) now displays a message to indicate that the iOS or Android platform has been successfully created.

#### Landing pages {#landing-pages}

* Se han corregido problemas que evitaban que se enviaran correos electrónicos de confirmación al enviar un formulario de página de aterrizaje.

#### Audiences and queries {#audiences-and-queries}

* Se han corregido varios problemas que se producían al seleccionar un perfil en el editor de consultas.

#### Transactional messages {#transactional-messages}

* Se ha corregido un error que impedía que se cancelara la publicación de una plantilla de transacción.
* Se ha corregido un problema que provocaba que los eventos se mostraran en la lista de eventos.

#### Integrations {#integrations-1}

* Se ha corregido un problema que impedía que una audiencia compartida se usara en una entrega después de actualizar dicha audiencia.
* Fixed an issue that prevented a shared asset ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** option) from being used in a landing page.
* Se han corregido problemas que se producían al editar una audiencia compartida importada desde Adobe Audience Manager.

## Release 16.9 - September 2016 {#release-16-9---september-2016}

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
   <td> Remarketing Triggers<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> En Adobe Marketing Cloud, usted define los distintos activadores, es decir, los comportamientos del cliente que desea monitorear, como todos los clientes que abandonaron el carro o el formulario, eliminaron un producto del carro o incluso los clientes cuya sesión caducó. Al crear un activador, se define la condición del activador y los datos que se enviarán en el evento (proceso de carga) a Adobe Campaign. <br /> En Adobe Campaign, se selecciona el activador que se creó anteriormente, se enriquecen los datos del evento con datos de datos y se define una plantilla de mensaje transaccional vinculada a dicho activador. Por ejemplo, cuando un cliente abandona el carro de compras, se envía un evento a Adobe Campaign que luego puede aprovechar este evento a través de un correo electrónico de remercadotecnia que se envía al cliente en un plazo de 15 minutos.<br /> Para obtener más información, consulte la documentación <a href="../../integrating/using/about-adobe-experience-cloud-triggers.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages: Pause / Unpublish<br /> </td> 
   <td> Ahora puede suspender la publicación de una plantilla de transacción mientras actualiza su contenido. Los mensajes correspondientes ya no se envían, pero se almacenan en la base de datos. Cuando se reanuda, se procesan los mensajes en cola y se envían si no han caducado.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication">detallada</a>.<br /> Ahora también puede cancelar la publicación de eventos y plantillas de transacción. Los mensajes correspondientes no se envían y no se almacenan en la base de datos.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multibranding<br /> </td> 
   <td> Los clientes con varias marcas ahora pueden administrarlos en la misma instancia. La personalización es una función administrada por el administrador de la instancia de Adobe Campaign que le permite configurar de forma centralizada todos los parámetros relacionados con una marca en Adobe Campaign. Esto incluye elementos como el logotipo a parámetros más técnicos como URL de seguimiento, análisis de Web, URL del servidor, nombre de dominio, etc.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/branding.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Responsive email design preview<br /> </td> 
   <td> Esta función le permite probar la capacidad de respuesta de su correo electrónico en diferentes tipos de dispositivos. In the email preview, a grid has been added to test your email on various screen sizes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications<br /> </td> 
   <td> Se ha agregado un nuevo canal para permitir a los especialistas en marketing enviar notificaciones push personalizadas y segmentadas en dispositivos móviles iOS y Android. Los mensajes pueden enviarse a través de una entrega única o mediante una actividad de flujo de trabajo. La compatibilidad con mensajes transaccionales estará disponible en versiones futuras. This channel leverages the Mobile core service’s SDK (available <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">here</a>).<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/about-push-notifications.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general-2}

* Esta versión incorpora nuevas funciones de filtrado y búsqueda en las listas de interfaz. Esta nueva característica está disponible, por ejemplo, en los registros (entrega, seguimiento), servicios (suscripción, historial de suscripción), audiencias y transiciones de flujo de trabajo.
* Se han corregido varios problemas de visualización relacionados con el número de touchpoints en un perfil de cliente.
* Se han corregido varios problemas de tipología.

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Se ha corregido un error que permitía editar pruebas erróneas. Ahora son de solo lectura.
* Se ha corregido un problema que hacía que un destinatario estuviera bloqueado cuando un SMS era demasiado largo o tenía problemas de codificación.

#### Custom resources {#custom-resources-1}

* Se ha corregido un error que impedía que se mostraran todos los resultados al utilizar los filtros avanzados de un recurso personalizado.

#### Transactional messages {#transactional-messages-1}

* Ahora se agrega automáticamente un prefijo al identificador de una nueva definición de evento.
* Se ha cambiado el icono que representa los mensajes transaccionales en la interfaz.

#### Integrations {#integrations-2}

* Fixed a display error that would occur when a high resolution image was inserted via the **Dynamic image from Adobe Target** option.
* Se ha corregido un error que permitía guardar una audiencia compartida aunque el ID de destino no estuviera establecido en la fuente de datos AMC.

## Release 16.7 - July 2016 {#release-16-7---july-2016}

### New capabilities {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Enriched transactional messages<br /> </td> 
   <td> Ahora puede vincular plantillas de transacciones con la base de datos de Adobe Campaign para recuperar información que le permita enriquecer el contenido de los mensajes transaccionales.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic URLs for images<br /> </td> 
   <td> Esta nueva funcionalidad permite personalizar una fuente de imágenes insertando bloques de contenido y texto dinámico para fines de seguimiento y personalización.<br /> A continuación, resulta posible aprovechar las funciones de los medios dinámicos de AEM Asset (S 7) introduciendo parámetros en las URL de imágenes. Por ejemplo, puede enviar un correo electrónico con imágenes personalizadas que indican "Hello Alexandre, obtenga las últimas noticias sobre próximos eventos en París!" o "Hola Frank, obtenga las últimas noticias sobre próximos eventos en Nueva York".<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/personalizing-urls.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with People Core Service<br /> </td> 
   <td> The Adobe Marketing Cloud <strong>Declared IDs</strong> are now covered by the integration between Adobe Campaign and People Core Service (Profiles &amp; Audiences).<br /> Esto significa que puede importar segmentos y exportar audiencias formadas por <strong>ID de visitante</strong>o <strong>ID declarados</strong>.<br /> Para obtener más información, consulte la documentación <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery logs<br /> </td> 
   <td> The MTA logs (delivery server) now display the complete history of each message, particularly all of the delivery attempts as well as the associated error statuses, and this has no impact on the application's performance.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### General {#general-3}

* Se ha corregido un error que podía hacer que se mostraran campos irrelevantes en lugar de campos que debían completarse. Esto sucedería después de que el operador de comparación se modificara varias veces al editar una condición en una consulta.
* Fixed the behavior of the option **[!UICONTROL The last X days/months/quarters/years]** when defining a relative filtering condition for a date field. El período calculado es ahora un período deslizante en relación con la fecha y hora del servidor y no basado en calendario.

#### Workflows {#workflows-1}

* Fixed an error that would return an incorrect list of values in the screen for selecting the targeting dimension in the properties of a **[!UICONTROL Query]** activity.
* Fixed an error that would force the **Exists** operator to be selected when adding an average or count aggregate on a collection element in a **[!UICONTROL Query]** activity.

#### Content editing {#content-editing}

* Se ha corregido un error que podía provocar problemas de visualización (diseño interactivo) al importar contenido HTML: los atributos de estilo ya no se vuelven a escribir cuando el contenido se abre por primera vez después de importarse.
* Se ha corregido un error de no bloqueo que se producía cuando se añadía una condición en una variante de contenido dinámico.
* Se ha corregido un error debido al agregado de una casilla en el contenido de una página de aterrizaje. La casilla no se puede utilizar.
* Se corrigió un error que se podía producir al eliminar texto en un bloque si el cursor se colocaba al principio del bloque en cuestión.

#### Transactional messages {#transactional-messages-2}

* Al integrar un sitio Web, ahora puede definir una fecha de caducidad para un evento determinado. Una vez pasada esta fecha, el mensaje correspondiente al evento ya no se puede enviar.

## Release 16.6 - June 2016 {#release-16-6---june-2016}

### New capabilities {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Profiles and Services API<br /> </td> 
   <td> The Adobe Campaign <span class="uicontrol">Profiles and Services</span> API is available in the <a href="https://www.adobe.io/products/campaign">adobe.io</a> portal. Esto permite actualizar, agregar y eliminar perfiles de Adobe Campaign, y para que estén suscritos o desmarcados de los servicios a través de llamadas REST.<br /> Para obtener más información, consulte la descripción <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">detallada de la API</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### General {#general-4}

* Ahora, las informaciones sobre herramientas están desactivadas en dispositivos móviles para garantizar que la información que se muestra en la pantalla sea fácil de leer.
* Se ha corregido un error que impedía que el usuario desplazara el contenido de ciertas zonas en la pantalla del ipad.
* Se han corregido varios errores de compatibilidad que se producían al editar contenido en Internet Explorer 11.
* Se ha corregido un error que podía impedir acceso a registros detallados cuando la importación de datos fallaba por primera vez.
* Se ha corregido un error que impedía guardar un filtro de intervalo.
* Se ha corregido un error que impedía que se mostraran elementos de un recurso al configurar la forma en que se mostraba una lista.
* Se corrigió un error en el explorador de consultas explorer. Los resultados devueltos por el campo de búsqueda se conservaron en el historial de búsqueda y se siguieron mostrando en cada nueva búsqueda.

#### Emails and SMS messages {#emails-and-sms-messages-3}

* Se ha corregido un error que impedía que la información vinculada a devoluciones se recuperara en registros de entrega.
* Se ha corregido un error que impedía acceso al contexto en un bloque de contenido dinámico de un mensaje de transacción.
* Se ha corregido un error que impedía que un vínculo de URL se defina en texto dinámico en contenido de correo electrónico.
* Se corrigió la visualización de la barra superior del asistente para creación de envíos.
* La clave principal de una entrega ya no se puede utilizar como campo de personalización.

#### Workflows {#workflows-2}

* Ahora, las transiciones entre dos actividades de un flujo de trabajo muestran el recuento de elementos calculado y transferidos de una actividad a otra.
* Incompatible fields are now hidden when additional data is added in a **[!UICONTROL Query]** activity.
* La ventana de definición agregada, que se muestra al agregar datos adicionales, se ha mejorado para ofrecer solamente opciones que son compatibles con los datos en uso (por ejemplo: el cálculo de un promedio solo es posible para los datos numéricos).
* Ahora solo un usuario con derechos de administración puede realizar o reanudar un flujo de trabajo técnico predeterminado.

#### Landing pages {#landing-pages-1}

* Se ha corregido un error que podía truncar las claves de codificación AES de 32 bits en las propiedades de una página de aterrizaje.
* Se ha corregido un error que impedía que el editor de consultas se mostrara correctamente al definir una condición de visibilidad o al agregar contenido dinámico a una página de aterrizaje.

#### Custom resources {#custom-resources-2}

* The **[!UICONTROL Switch to parameters]** option is now hidden when defining a filter related to a profile's subscriptions to a service.
* Se ha corregido un error que se podía producir cuando se configuraba un vínculo de tipo 0-1 desde un recurso personalizado.
* Fixed an error that, where relevant, could prevent the defined **Constant default value** from being edited when adding a **Date and time** type field in a custom resource.

## Release 16.5 - May 2016 {#release-16-5---may-2016}

### New capabilities {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Predefined filters<br /> </td> 
   <td> Los administradores ahora pueden crear filtros avanzados que aparecen en el editor de consultas en forma de reglas preconfiguradas. La selección de esos filtros permite a los usuarios desarrollar configuraciones complejas más fácilmente en una interfaz simplificada al definir una audiencia, por ejemplo.<br /> Para obtener más información, consulte la documentación <a href="../../developing/using/configuring-filter-definition.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Subscription Services<br /> </td> 
   <td> A new <span class="uicontrol">Subscription Services</span> activity offers the possibility of subscribing several profiles to a service or unsubscribing them from a service with in a single action.<br /> Esta actividad se puede utilizar después de haber realizado un objetivo o de importar un archivo con datos identificados.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/subscription-services.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: data enrichment<br /> </td> 
   <td> The <span class="uicontrol">Additional data</span> tab is now available in <span class="uicontrol">Query</span> type activities. Esta funcionalidad permite enriquecer los datos dirigidos a la consulta y transferir estos datos a las siguientes actividades de flujo de trabajo donde se puede aprovechar.<br /> Después de agregar datos adicionales, puede aplicar un nivel de filtro adicional a los datos de objetivo inicialmente creando condiciones basadas en los datos adicionales definidos.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/query.md#enriching-data">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Contextual help<br /> </td> 
   <td> Ahora está disponible una función de ayuda contextual en las distintas pantallas de Adobe Campaign. Esto significa que, en un solo clic, puede acceder directamente a la documentación sobre la funcionalidad que está utilizando. Para mostrar la ayuda contextual, haga clic en el icon in the upper-right corner of the screen, as shown in the example below.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-5}

* Varias interfaces Nuevas funciones que cumplen con los estándares de Marketing Cloud.
* Estandarización de los distintos tipos de listas desplegables.

#### Emails and SMS messages {#emails-and-sms-messages-4}

* Se ha corregido un error que impedía que se enviaran correos electrónicos si se había especificado la máscara de dirección de error.
* El protocolo TLS ahora es compatible con la entrega por correo electrónico. Una nueva columna en la administración MX permite definir el comportamiento de TLS para cada dominio.
* Se ha mejorado la interfaz de SMS.

#### Workflows {#workflows-3}

* Varias interfaces de flujo de trabajo Nuevas funciones.
* Se ha corregido un error que se producía al mostrar acciones rápidas.
* Fixed an error that could cause a workflow to fail when using a **[!UICONTROL Segmentation]** type activity containing a 1-N link.
* Se ha corregido un error que impedía que las transiciones de un flujo de trabajo se abrieran en un dispositivo híbrido.
* Se ha corregido un error que impedía que el botón de pausa se mostrara al iniciar un flujo de trabajo por primera vez.

#### Content editor {#content-editor}

* Ahora, el editor de contenido permite personalizar cualquier URL incluida en un correo electrónico o una página de aterrizaje. Refer to the [detailed documentation](../../designing/using/personalizing-urls.md).
* Se ha corregido un error que podía causar pérdida de imágenes cuando se añadían al asistente para creación de la entrega y su contenido se modificaba posteriormente.

#### Custom resources {#custom-resources-3}

* Se ha corregido un error que se producía al agregar un vínculo personalizado de 1 N en la pantalla de configuración de un recurso personalizado.
* Se ha mejorado la visualización de la barra de progreso al preparar y publicar recursos personalizados.
* Se ha corregido un error que se producía al mostrar la lista de vínculos de un recurso personalizado.

#### Transactional messages {#transactional-messages-3}

* Se ha optimizado la practicidad de la interfaz, así como el rendimiento y la solidez del motor de mensajes transaccionales.
* Ahora es posible suspender temporalmente la publicación de una plantilla de mensaje transaccional. For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* Se ha corregido un error que podía provocar que un bloque de contenido con una dimensión de objetivo incompatible se agregara a una plantilla de mensaje transaccional.
* Se ha corregido un error que impedía que la vista previa de la API se mostrara en una pantalla de configuración del evento.

#### Audiences and queries {#audiences-and-queries-1}

* Hay varios parches relacionados con el uso de fechas en el editor de consultas. Refer to the [detailed documentation](../../automating/using/editing-queries.md#creating-queries).

#### Administration {#administration}

* Se ha corregido un error relacionado con el nombre del grupo de seguridad "Usuarios estándar" que impedía que los usuarios iniciaran sesión.

## Release 16.3 - March 2016 {#release-16-3---march-2016}

### New capabilities {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Interface and navigation<br /> </td> 
   <td> La interfaz de Adobe Campaign se ha mejorado para facilitar la navegación y las operaciones.<br /> Ahora se desplaza desde la barra superior de la aplicación. The advanced menus are accessible by selecting the <strong>Adobe Campaign</strong> logo.<br /> Para obtener más información, consulte la documentación <a href="../../start/using/interface-description.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Save audience<br /> </td> 
   <td> A new option, <span class="uicontrol">Create then update an audience</span> , is now available in the <span class="uicontrol">Save audience</span> activity. Esta opción permite introducir manualmente una etiqueta de audiencia. Si la etiqueta ingresada corresponde a una audiencia existente, se actualizará. Si la audiencia no existe, se creará.<br /> Además, la audiencia se actualizará cada vez que se ejecute el flujo de trabajo (nuevamente).<br /> Siempre puede seleccionar el modo de actualización de audiencia: complete la audiencia con nuevos datos o sustituya la totalidad de los datos de audiencia en cada ejecución.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/save-audience.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Segmentation<br /> </td> 
   <td> The <span class="uicontrol">Segmentation</span> activity now allows the user to segment the data of a temporary resource. Por ejemplo: los datos de un archivo importado.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/segmentation.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-6}

* Se ha corregido un error de visualización que se producía al ordenar una lista: la flecha que indica el orden de una columna sólo se puede invertir para ciertos tipos de datos.
* Se ha corregido un error que limitaba el número de elementos mostrados en un menú desplegable cuando se añadía una regla en una consulta.

#### Emails and SMS messages {#emails-and-sms-messages-5}

* Se ha corregido un error que podía impedir el acceso al informe de procesamiento de correo electrónico.
* La etapa de envío de envío para un mensaje ahora devuelve un error si no se proporciona la dirección remitente.

#### Workflows {#workflows-4}

* Algunas opciones de formato de archivo eran visibles pero no se tenían en cuenta al extraer un archivo de formato CSV. Estas opciones ya no están visibles.
* Fixed an error caused when the **[!UICONTROL Delete the source files after transfer]** option was checked for a **[!UICONTROL SFTP]** type file transfer.
* Fixed an error that could prevent the counter and preview of **[!UICONTROL Query]** data from being displayed after refreshing the page.
* Se ha corregido un error debido al abrir ciertas transiciones en un flujo de trabajo, especialmente después de una actividad de entrega o una consulta en la que las dimensiones de objetivo y filtrado eran diferentes.
* Se ha corregido un error que impedía que un campo de personalización se insertara en una actividad de entrega de un flujo de trabajo si el flujo de trabajo no se guardaba tras agregar la actividad.
* Se ha corregido un error que impedía que se mostrara la dimensión de objetivo de transición saliente de una actividad de envío de correo electrónico.

#### Landing pages {#landing-pages-2}

* Se ha corregido un error que impedía que los campos de personalización funcionaran correctamente en un bloque de contenido localizable en una página de aterrizaje.

#### Custom resources {#custom-resources-4}

* Fixed an error that prevented a search on a custom resource from being carried out if the **[!UICONTROL Add search fields]** option of the resource screen definition was checked and if several fields were selected in the **[!UICONTROL Filter zone composition]** .

## Release 16.2 - February 2016 {#release-16-2---february-2016}

### New capabilities {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> A/B test for emails<br /> </td> 
   <td> Ahora puede realizar pruebas A/B en el contenido, asunto o nombre remitente de sus correos electrónicos. Esta nueva funcionalidad puede probar hasta tres variantes de un elemento.<br /> Al crear un correo electrónico desde una de las nuevas plantillas específicas de las pruebas A/B, un nuevo paso en el asistente para creación permite definir los parámetros de la prueba.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/designing-an-a-b-test-email.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Brand management<br /> </td> 
   <td> Ahora puede definir una o varias marcas para introducir de forma centralizada los parámetros que afectan a la identidad de una marca. Adobe Campaign permite crear estas marcas y vincularlas a plantillas de página de aterrizaje o entrega.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/branding.md#assigning-a-brand-to-an-email">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Incremental query<br /> </td> 
   <td> A new workflow activity, <span class="uicontrol">Incremental query</span> , allows you to carry out a query which, on every execution, targets only the new results. Los resultados de ejecuciones anteriores se excluyen automáticamente. Linked to a <span class="uicontrol">Scheduler</span> activity, you can define the execution frequency of the <span class="uicontrol">Incremental query</span> .<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/incremental-query.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> Se ha mejorado la solidez del usuario de la interfaz de mensajes transaccionales. All business process management linked to transactional messages is currently centralized in the <span class="uicontrol">Marketing plans</span> &gt; <span class="uicontrol">Transactional messages</span> menu. También se ha mejorado la configuración del evento. Los eventos ahora se administran independientemente de los recursos personalizados.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/about-transactional-messaging.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-7}

#### General {#general-7}

* Se han corregido varios errores de visualización en informes, listas y consultas.
* Se han corregido varios errores de compatibilidad y visualización en dispositivos móviles.

#### Emails and SMS messages {#emails-and-sms-messages-6}

* Se ha corregido un error que podía impedir que el botón utilizado para insertar campos de personalización se mostrara al crear un mensaje (correo electrónico o SMS).
* Se ha corregido un error que podía impedir que los mensajes SMS enviados mediante Mblox se transmitieran correctamente.

#### Audiences and queries {#audiences-and-queries-2}

* Se ha corregido un error de recuento que se podía producir al agregar una condición adicional en una consulta después de haber modificado la dimensión de filtrado.
* Se ha corregido un error que podía llevar a una paginación incorrecta al obtener una vista previa de los resultados de una consulta.

#### Content editing {#content-editing-1}

* Se ha corregido un error que impedía tener en cuenta correctamente la configuración de contenido dinámico al usar una enumeración personalizada.

#### Workflows {#workflows-5}

* Fixed an error that could prevent any action in a workflow from being carried out if there was an empty line in the **[!UICONTROL Fields to update]** tab of an **[!UICONTROL Update data]** activity.
* Se ha corregido un error que impedía importar datos que contenían información de unidades geográficas/organizativas.
* Fixed an error caused by adding a **[!UICONTROL Change axis]** type of **[!UICONTROL Exclusion]** rule.
* Fixed an error that could lead to an unwanted additional segment being created when manipulating an outbound transition of a **[!UICONTROL Segmentation]** activity.
* Se ha corregido un error ocasionado por la carga de un archivo en una plantilla de flujo de trabajo.
* Fixed an error that could prevent spaces from being used as column separators in a **[!UICONTROL Load file]** activity.

#### Custom resources {#custom-resources-5}

* Se ha corregido un error que impedía que se volviera a escribir el estado de un recurso personalizado tras importar un paquete, si el recurso se había publicado en el momento de la exportación.

#### Packages {#packages}

* Se ha corregido un error que impedía exportar un paquete que contenía un flujo de trabajo.
* Se ha corregido un error que podía impedir que se seleccionaran varios elementos del mismo recurso.

## Release 16.1 - January 2016 {#release-16-1---january-2016}

### New capabilities {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> The following email specific reports have been added: <span class="uicontrol">Complaints</span> , <span class="uicontrol">Opens</span> , and <span class="uicontrol">Unsubscriptions</span> .<br /> Se han mejorado los siguientes informes: <span class="uicontrol">Resumen</span> de entrega, <span class="uicontrol">resumen</span> de devoluciones, <span class="uicontrol">Rendimiento</span> de entrega e <span class="uicontrol">Indicadores</span> de seguimiento.<br /> Para obtener más información, consulte la documentación <a href="../../reporting/using/defining-the-report-period.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Query editing<br /> </td> 
   <td> The query editor has been improved and now allows you to scan the <strong>1-N</strong> type links.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/editing-queries.md#creating-queries">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content personalization<br /> </td> 
   <td> As for email or landing page editing, the input interface for content block display conditions has been improved.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: column definition when importing<br /> </td> 
   <td> The <span class="uicontrol">Load file</span> activity now allows you to configure the columns of an imported file in detail: expected data type, date and time format, processing to apply in case of an empty value or an error, and value remapping.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/load-file.md#column-format">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mapping of SMS encodings<br /> </td> 
   <td> Ahora es posible definir asignaciones de codificaciones de mensajes SMS personalizados para proveedores que no utilicen codificación estándar. Un administrador puede realizar la configuración de asignaciones personalizadas y definir el orden en el que se deben tener en cuenta.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/configuring-sms-channel.md#smsc-specifics">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-8}

#### General {#general-8}

* Compatibilidad mejorada con Internet Explorer y Chrome para dispositivos híbridos o táctiles.
* Se ha corregido un error que podía provocar la pérdida de todos los datos introducidos para un nuevo perfil de usuario/perfil/prueba si la dirección de correo electrónico indicada contenía errores de sintaxis.

#### Emails and SMS messages {#emails-and-sms-messages-7}

* Se ha corregido un error que podía impedir que la miniatura de contenido se generara en la pantalla de vista previa de correo electrónico.
* Se ha corregido un error que podía impedir que el contenido sin procesar de un mensaje (correo electrónico o SMS) se mostrara en la pantalla de vista previa del mensaje.

#### Audiences and queries {#audiences-and-queries-3}

* Fixed an error that could prevent a **Query** type audience from being created in the **Service** resource.
* Se ha corregido un error que podía evitar que la lista de funciones se mostrara correctamente al editar una condición de una consulta en modo avanzado.
* Fixed an error that could prevent a **Query** type audience from being created if it contained criteria based on collections.
* Se ha corregido un error que impedía que se crearan consultas que contenían filtros en los KPI de entrega.
* Se ha corregido un error que podía impedir la vista previa del contenido de una audiencia creada desde un flujo de trabajo.

#### Custom resources {#custom-resources-6}

* Se ha corregido un error que podía provocar un bloqueo del servidor si un recurso personalizado contenía un campo con un valor predeterminado dinámico.
* Fixed an error caused by moving, then deleting an element in the **[!UICONTROL Detail screen configuration]** section while defining screens of a custom resource.
* Fixed an error that occurred when a default value had been defined for an **integer** list that did not include **0** in its range of possible values.
* Se ha corregido un error que podía impedir que un elemento se agregara en la configuración de la pantalla de detalles de un recurso personalizado tras una reinicialización.

#### Workflows {#workflows-6}

* Se ha corregido un error que podía provocar que se mostraran registros de todas las actividades en un flujo de trabajo en lugar de mostrar únicamente los de la actividad seleccionada.
* Fixed an error in the **[!UICONTROL Scheduler]** activity. The **[!UICONTROL Day of the month]** option was not correctly taken into account and replaced by **[!UICONTROL Week day]** .
* Fixed an error that could prevent a **[!UICONTROL Scheduler]** activity from working correctly with the expiration mode set to **[!UICONTROL After a certain number of iterations]** .
* Fixed an error that occurred when exporting data using an **[!UICONTROL Extract file]** activity. El número de líneas presentes en el archivo de exportación era inferior al número de elementos exportados.
* Fixed an error that could prevent a file in a **[!UICONTROL Load file]** activity from being selected.
* Fixed an error that prevented fields that were to be updated in an **[!UICONTROL Update data]** activity from being deleted.
* Se ha corregido un error que impedía guardar las modificaciones realizadas en un flujo de trabajo tras haber abierto los registros de ejecución del flujo de trabajo.
* Fixed an error that caused a **[!UICONTROL Load file]** activity to be executed twice if it was configured to use the file from its inbound transition and this file had been loaded using a **[!UICONTROL Transfer file]** activity.
* Fixed an error that could prevent certain temporary entities from being correctly processed by an **Exclusion** activity.
* Fixed an error that could prevent a **[!UICONTROL Query]** activity from being executed correctly if the targeting dimension and the filtering dimension configured in the activity were different.
* Fixed an error concerning the automatic naming of outbound transitions added to a **[!UICONTROL Fork]** activity that could prevent the workflow from being saved.

#### Content editing {#content-editing-2}

* Se ha corregido un error que podía provocar que un icono o una barra de búsqueda se mostraran inesperadamente al editar contenido.

#### Landing pages {#landing-pages-3}

* Se ha corregido un error que impedía importar una página de aterrizaje mediante una importación de paquete.

#### Transactional messages {#transactional-messages-4}

* Ahora es posible especificar una dirección IP confiada en los parámetros de seguridad del operador Agent Center Push Agent.
* Se ha corregido un error que podía impedir que se creara un nuevo tipo de evento.

## Release 15.11 - November 2015 {#release-15-11---november-2015}

### New capabilities {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> Ahora puede enviar mensajes SMS con Adobe Campaign.<br /> Al igual que con los correos electrónicos, puede crear nuevos envíos SMS a partir de sus campañas y de la lista de actividades de marketing. También puede crear mensajes SMS recurrentes y de envío a partir de un flujo de trabajo.<br /> Estos envíos SMS se basan en plantillas que se pueden configurar desde la lista de plantillas de envío. Hay disponible una plantilla predeterminada.<br /> Estos envíos SMS utilizan el protocolo SMPP 3.4, utilizado por la mayoría de los enrutadores SMS.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/about-sms-messages.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploring transitions<br /> </td> 
   <td> Ahora puede explorar los datos y su estructura en la última transición de un flujo de trabajo. This allows you to check that the processes applied by each activity correspond to your needs.<br /> </td> 
  </tr> 
  <tr> 
   <td> File pre- and post-processing in workflows<br /> </td> 
   <td> You can now carry out additional processing on a data file when importing or exporting it via the <span class="uicontrol">Load file</span> and <span class="uicontrol">Extract file</span> activities.<br /> De forma predeterminada, puede descomprimir y compactar un archivo de formato GZIP en estas actividades.<br /> Para obtener más información, consulte la documentación sobre el archivo <a href="../../automating/using/load-file.md">Cargar</a> y <a href="../../automating/using/extract-file.md">Extraer</a> actividades de archivo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Deliverability reports<br /> </td> 
   <td> Ahora está disponible un informe de procesamiento de correo electrónico. Este informe permite ver las diferentes representaciones de un mensaje según la asistencia y el servicio de mensajes utilizado para leerlo.<br /> El resumen del informe también muestra la cantidad de mensajes recibidos, mensajes no deseados, mensajes no recibidos y mensajes que esperan la recepción.<br /> Para obtener más información, consulte la documentación <a href="../../sending/using/email-rendering.md#email-rendering-report-description">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Package Management<br /> </td> 
   <td> It is now possible to import and export images in packages.<br /> </td> 
  </tr> 
  <tr> 
   <td> Quick actions<br /> </td> 
   <td> Determinadas acciones aparecen cuando se pasa el ratón por encima o después de seleccionar un elemento en una lista o un flujo de trabajo. Algunas de estas acciones se muestran ahora como iconos alrededor de los elementos pertinentes para facilitar el acceso. These quick actions can be used to duplicate an element, delete it, show the detail, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-9}

#### General {#general-9}

* Se ha corregido un error que podía impedir el acceso a los parámetros generales de una instancia desde una cuenta de administrador.
* **Los datos flotantes** ahora se tienen en cuenta correctamente en los recursos personalizados.
* Se ha corregido un error de visualización en la lista de importaciones simplificadas ejecutadas que se producía cuando se había modificado el estado de la plantilla correspondiente.

#### Landing pages {#landing-pages-4}

* Se han corregido ciertos elementos de las plantillas de página de aterrizaje que se podían mostrar incorrectamente en francés en instancias de inglés.

#### Audiences {#audiences}

* Se ha corregido un error que podía impedir que las audiencias importadas de Adobe Marketing Cloud aparecieran en la lista de audiencias.
* Se ha corregido un error que podía forzar la distinción entre mayúsculas y minúsculas al definir una consulta.
* Se ha corregido un error que podía impedir que las audiencias se filtraran al definir una consulta.
* Se ha corregido un error que podía impedir que una acción se cancelara en una audiencia.

#### Workflows {#workflows-7}

* Fixed an error that could prevent the fields that were to be updated in an **[!UICONTROL Update data]** activity from manually being configured.
* Fixed an error that could cause the **[!UICONTROL Query]** activity to load infinitely when opened if the workflow had not been saved after having placed the activity in the diagram.
* Fixed an error that could cause the server to stop while counting or previewing an audience selected from a **[!UICONTROL Query]** in a workflow.
* Se ha corregido un error no crítico que podía aparecer cuando se abría una actividad en un flujo de trabajo.
* Fixed an error that prevented a **[!UICONTROL Scheduler]** activity from being configured to execute a workflow several times a day.
* Se ha corregido un error que podía provocar que los campos en los que no se pudiera realizar una consulta aparecieran en ciertas actividades de flujo de trabajo.
* Fixed an error that could prevent the user from locating the KPIs added from a **[!UICONTROL Query]** on deliveries in the outbound transition.
* Se ha corregido un error que podía impedir que se creara una audiencia de archivos después de importar un archivo en un flujo de trabajo.
* Fixed an error that could prevent data from being updated on profiles if the **location/address3** field of the resource was used.
* Se ha corregido un error que impedía que las colecciones heterogéneas de actividades se duplicaran en un flujo de trabajo.
* Se ha corregido un error que impedía que se mostrara SQL, lo que permitía diagnosticar errores para una entrega recurrente en un flujo de trabajo.

#### Content editor {#content-editor-1}

* Se corrigió un error que causaba que la búsqueda en el código fuente de una página de aterrizaje o correo electrónico fuera imposible.

#### Packages {#packages-1}

* Se han corregido varios errores que evitaban que ciertos tipos de elementos se exportaran en paquetes (particularmente páginas de aterrizaje o flujos de trabajo).
* Se ha corregido un error que causaba que se mostrase la etiqueta de importación del paquete anterior si se había modificado la etiqueta.
* Se ha corregido un error que podía hacer que se mostraran recursos incompatibles en la lista de recursos exportables.

## Release 15.10 - October 2015 {#release-15-10---october-2015-}

### New capabilities {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Deduplication activity<br /> </td> 
   <td> Ya hay disponible una nueva actividad dedicada a eliminar la duplicación de datos en los flujos de trabajo. Esta actividad le permite filtrar cualquier duplicado de sus objetivos según los criterios que haya elegido.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/deduplication.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Improved diagram<br /> </td> 
   <td> Desde el espacio de trabajo del flujo de trabajo, ahora puede utilizar varios métodos abreviados de teclado para seleccionar, abrir y eliminar actividades.<br /> La alineación de actividades también se ha mejorado y permite que un flujo de trabajo se organice mejor.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/workflow-interface.md#workspace">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> The date and time of the export is now automatically added to the labels of the files exported using an <span class="uicontrol">Extract file</span> activity. This way the files generated are unique.<br /> </td> 
  </tr> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> The name of the template from which a simplified import was carried out is now visible by default in the import list and in the detail of each import.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Improvement and extended possibilities for managing and defining links for custom resources.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-10}

#### Email {#email}

* Se ha corregido un error que impedía que un vínculo de cancelación de suscripción funcionara correctamente desde una página reflejada.
* Se ha corregido un error que podía impedir que una etiqueta de envío de correo electrónico se mostrara correctamente en la página de edición de correo electrónico.
* Fixed an error that could prevent an external **[!UICONTROL Routing]** account from being selected in a duplicated delivery template.

#### Audiences {#audiences-1}

* Se ha corregido un error producido durante un recuento de audiencias si se utilizaba un vínculo 1-N en la consulta.
* Se ha corregido un error que podía impedir que un perfil se pudiera seleccionar en una audiencia de destino de envío de correo electrónico.

#### Workflows {#workflows-8}

* Se ha corregido un error que podía provocar problemas de visualización al configurar una entrega por correo electrónico en un flujo de trabajo.
* Fixed an error that could prevent the **[!UICONTROL Load file]** activity from working correctly. Aparecerá un mensaje de error en blanco.
* Fixed an error that could prevent the **[!UICONTROL Transfer file]** activity from working correctly. Los derechos de acceso no siempre se tuvieron en cuenta correctamente.
* Fixed an error that could prevent a file from being exported if the workflow contained a **[!UICONTROL Recurring email]** .
* Se ha corregido un error que podía impedir que se creara una entrega por correo electrónico en un flujo de trabajo o impedir que el asunto y el contenido definido se tuvieran en cuenta.
* Fixed an error that could prevent a reconciliation key from being selected in an **[!UICONTROL Update data]** activity when configuring the workflow of a simplified import template.
* Se ha corregido un error que impedía guardar un flujo de trabajo tras haber eliminado una actividad.

#### Platform {#platform}

* Se ha corregido un error que podía evitar que se creara un nuevo elemento si un recurso personalizado contenía un vínculo al tipo de recurso de ese elemento.
* Se ha corregido un error que podía provocar un retraso de 15 minutos en ciertos registros.
* Fixed an error that could prevent the marketing activity list from being displayed when sorted by the **[!UICONTROL Date]** or **[!UICONTROL Indicators]** columns.

#### Landing pages {#landing-pages-5}

* Se ha corregido un error que se producía al seleccionar un perfil de prueba para obtener una vista previa de una página de aterrizaje.

#### Transactional messages {#transactional-messages-5}

* Se ha corregido un error que podía provocar que la aplicación se bloqueara después de eliminar un evento en un perfil de prueba.

#### Reports {#reports}

* Fixed an error that could cause incorrect data to be sent for the reports **[!UICONTROL deliveryThroughputReport]** and **[!UICONTROL deliveryTrackingReport]** .

#### Content editor {#content-editor-2}

* Se ha corregido un error de administración de etiquetas HTML que se producía al procesar bloques de contenido dinámico.

## Release 15.8 - August 2015 {#release-15-8---august-2015}

### New capabilities {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Simplified data import<br /> </td> 
   <td> Ahora puede importar datos de forma simplificada.<br /> Los usuarios simplemente seleccionan una plantilla predefinida por un administrador y cargan el archivo que contiene los datos que se van a importar. Un flujo de trabajo definido en la plantilla se ejecuta de forma transparente para el usuario, que puede acceder a los detalles del resultado de la importación como así también un registro de cualquier error.<br /> Los datos de estos archivos se pueden insertar en la base de datos o servir de medio para crear directamente una audiencia.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/about-data-import-and-export.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creating programs and campaigns<br /> </td> 
   <td> Ahora, las campañas y los programas se configuran para que el día que se crean se utilice automáticamente como fecha de inicio.<br /> La fecha de finalización se configura de acuerdo con la fecha de inicio, por ejemplo:<br /> 
    <ul> 
     <li> D +186 para programas </li> 
     <li> D +61 para campañas </li> 
    </ul> For more information, refer to the <a href="../../start/using/programs-and-campaigns.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> The list of tracked URLs is now read only.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional messages<br /> </td> 
   <td> Ahora puede administrar mensajes transaccionales personalizados para eventos como cambios de contraseña o confirmaciones después de crear una cuenta.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/about-transactional-messaging.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> Se han agregado varias funcionalidades como: ampliar un perfil de prueba, administración de estado y eliminar recursos.<br /> Para obtener más información, consulte la documentación <a href="../../developing/using/resource-statuses.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-11}

#### Display {#display}

* Se ha corregido un error que podía provocar que dos campos se yuxtaposed en el editor de consultas en Safari.

#### Content editor {#content-editor-3}

* Se ha corregido un error que impedía que se usaran los caracteres ' &lt;',' &amp;' y ' &gt;' en un asunto del mensaje de correo electrónico.

#### Email {#email-1}

* Se ha corregido un error que impedía que el usuario agregara texto después de texto dinámico.

#### Lists {#lists}

* Fixed an error that prevented the **Message** column in workflow execution logs from being exported correctly.

#### Profiles and audiences {#profiles-and-audiences}

* Se ha corregido un error que llevaba a una doble confirmación de cuándo se duplicaba o eliminaba un elemento. **Dispositivos híbridos con Internet Explorer 11 solamente**.

#### Workflows {#workflows-9}

* Se ha corregido un error que podía impedir que se enviaran correos electrónicos desde un flujo de trabajo.
* Fixed an error that could prevent a workflow from executing when the name of the rejection file was not specified in a **[!UICONTROL Load file]** activity.
* Fixed an error that could prevent a workflow from executing when the **[!UICONTROL Execution frequency]** of a **[!UICONTROL Schedule]** activity was set to **[!UICONTROL Daily]** .

#### Platform {#platform-1}

* Se ha corregido un error que impedía que se generaran miniaturas en un entorno equilibrado de carga.

## Release 15.7 - July 2015 {#release-15-7---july-2015}

### New capabilities {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exporting lists<br /> </td> 
   <td> Ahora puede exportar contenido de las listas a un archivo en formato CSV. This function is available in all screens with a <strong>List</strong> mode (for example: profile list).<br /> Los datos exportados son los datos de las columnas mostradas al exportar. Al editar la lista, puede seleccionar los datos que desee exportar.<br /> Para obtener más información sobre cómo utilizar esta funcionalidad, consulte la documentación <a href="../../automating/using/exporting-lists.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integration with Adobe Profiles &amp; Audiences<br /> </td> 
   <td> You can now share audiences between Adobe Campaign and your other Adobe Marketing Cloud solutions:<br /> 
    <ul> 
     <li> Export: when you save an audience composed of profiles in a workflow, a new <span class="uicontrol">Share in Adobe Marketing Cloud</span> option allows you to add profiles to an existing audience or to create a new audience. </li> 
     <li> Import: by creating a <strong>List</strong> type audience from the audience management screen, a new option allows you to identify it as an <span class="uicontrol">Adobe Marketing Cloud Audience</span> . A continuación, puede seleccionar una audiencia compartida existente para importarla a Adobe Campaign. </li> 
    </ul> For more information on configuring and using this functionality, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic content<br /> </td> 
   <td> Se ha mejorado la interfaz de contenido dinámico. Ahora, las flechas aparecen para permitir navegar entre los distintos contenidos dinámicos directamente en el cuerpo del correo electrónico.<br /> Para obtener más información sobre cómo utilizar esta funcionalidad, consulte la documentación <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor - Dynamic text<br /> </td> 
   <td> From the content editor of an email, you can now define dynamic text:<br /> 
    <ul> 
     <li> en un asunto de correo electrónico, </li> 
     <li> en modo HTML, </li> 
     <li> o en modo de texto. </li> 
    </ul> For more information on using this functionality, refer to the <a href="../../designing/using/defining-dynamic-text.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programs and campaigns - Reports<br /> </td> 
   <td> Se ha mejorado la interfaz y los gráficos de los informes.<br /> Para obtener más información sobre cómo utilizar esta funcionalidad, consulte la documentación <a href="../../reporting/using/defining-the-report-period.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-12}

#### Installation {#installation}

* Los nombres de instancias de Adobe Campaign están ahora limitados a 32 caracteres.

#### Workflows {#workflows-10}

* Se ha corregido un error que podía impedir el establecimiento de un recurso de «entrega» al editar una consulta en un flujo de trabajo.
* Se ha corregido un error que impedía que ciertos recursos vinculados se procesaran al editar una consulta en un flujo de trabajo.
* Fixed an error that could prevent a **Recurring delivery** activity from being modified if the workflow had already been executed.

#### Emails {#emails}

* Se ha corregido un error que impedía que se verificaran los errores de sintaxis JavaScript antes de enviar un mensaje de correo electrónico cuando se añadía un contenido dinámico a través del editor de expresiones.

#### Landing pages {#landing-pages-6}

* Se ha corregido un error que impedía que se editara una página de aterrizaje desde una tableta.

#### Assets Core Service {#assets-core-service}

* Al seleccionar un recurso compartido desde un correo electrónico o una página de aterrizaje que se esté editando, ahora se filtra la lista de recursos disponibles para Adobe Campaign.

## Release 15.6 - June 2015 {#release-15-6---june-2015}

### New capabilities {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Workflows: Reconciliation activity<br /> </td> 
   <td> A new <strong>Reconciliation</strong> activity links unidentified data (for example, after importing a file) with existing resources within a workflow.<br /> Esta actividad se utiliza principalmente para fines de administración de datos. It responds to two different use cases:<br /> 
    <ul> 
     <li> <strong>Adición de relaciones</strong>: La ficha <strong>Relaciones</strong> permite agregar vínculos entre datos de entrada y varias dimensiones de la base de datos de Adobe Campaign. </li> 
     <li> <strong>Identificación de datos</strong>: Una ficha <strong>Identificación</strong> permite asociar datos de entrada a columnas en una dimensión existente en la base de datos de Adobe Campaign. Cuando sale de la actividad, los datos se identifican como pertenecientes a la dimensión especificada. </li> 
    </ul> Refer to the <a href="../../automating/using/reconciliation.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Extract file activity<br /> </td> 
   <td> A new <strong>Extract file</strong> activity allows you to export data from the Adobe Campaign database in the form of an external file from a workflow. <br /> Limitación: actualmente no es posible utilizar nombres dinámicos para archivos de salida.<br /> Consulte la documentación <a href="../../automating/using/extract-file.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Scheduler activity<br /> </td> 
   <td> Improved widget that allows you to select the execution time of the <strong>Scheduler</strong> activity in a workflow.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: Transfer file activity<br /> </td> 
   <td> SFTP is now supported.<br /> </td> 
  </tr> 
  <tr> 
   <td> Custom resources<br /> </td> 
   <td> The <span class="uicontrol">Development</span> menu now allows users with admin rights to enrich the data templates provided by creating their own custom resources, such as purchase or product tables. <br /> Los recursos predeterminados también pueden ampliarse para agregar nuevos campos.<br /> Además, puede configurarse la navegación en las pantallas correspondientes a recursos personalizados nuevos o ampliados.<br /> Consulte la documentación <a href="../../developing/using/data-model-concepts.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> The <strong>Middle name</strong> and <strong>Title</strong> of the test profiles can now be selected when configuring the list of test profiles.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content editor: Dynamic content<br /> </td> 
   <td> Puede definir distintos contenidos que se mostrarán dinámicamente al usuario según las condiciones definidas mediante el editor de expresiones.<br /> Consulte la documentación <a href="../../designing/using/defining-dynamic-content-in-a-landing-page.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email<br /> </td> 
   <td> A <strong>Test profiles</strong> column is now available in an email's sending logs.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-13}

#### Lists {#lists-1}

* Al eliminar un elemento de una lista ahora se actualiza automáticamente la lista.
* Se ha corregido un error que impedía que se seleccionaran elementos de una lista que contenía sólo una columna.
* Se ha corregido un error que provocaba que se perdiesen los cambios aplicados a la visualización de una lista tras actualizar la página.
* Tanto el nombre central como el título de perfiles de prueba ahora se pueden mostrar en la lista de perfiles de prueba.
* Se ha corregido un error que se producía al seleccionar una casilla de verificación en una lista con Mozilla Firefox.

#### Audiences {#audiences-2}

* Fixed an error that prevented the **[!UICONTROL Add]** button from being used in the audience interface.

#### Emails {#emails-1}

* Se ha corregido un error de JavaScript que impedía que el botón de vista previa se usara dos veces seguidas al editar un mensaje de correo electrónico.
* Fixed an error that prevented the **[!UICONTROL Edit properties]** and **[!UICONTROL Show proofs]** buttons from being used on Microsoft Surface Pro3 tablets using Internet Explorer 11.
* Se ha corregido un error que podía evitar que se mostraran registros de correo electrónico.

#### Landing pages {#landing-pages-7}

* Fixed an error that prevented the **Brand logo** content block from being used when editing content in a landing page.
* Se ha corregido un error que impedía que las páginas de aterrizaje se mostraran en la lista de actividades de marketing si se especificaban fechas de validez para la página de aterrizaje.

#### Workflows {#workflows-11}

* Fixed an error that prevented limiting a segment in group mode from working correctly when configuring a **Segmentation** activity.
* Fixed an error that prevented a transition from being selected after having configured a **Segmentation** activity.
* Fixed an error that prevented a transition from being deleted after having configured a **Segmentation** activity.
* Fixed an error that prevented populations from being counted and previewed within a **Segmentation** activity.
* Se ha corregido un error que impedía que se eliminara de forma eficaz un mensaje de correo electrónico recurrente.
* Fixed an error that caused data from a deleted **Transfer file** activity to appear in a new **Transfer file** activity.
* Fixed an error that prevented an exclusion rule from being correctly taken into account within an **Exclusion** activity.
* Se ha corregido un error que se producía al eliminar una actividad de envío de correo electrónico en un flujo de trabajo. Los envíos correspondientes ahora también se eliminan de la lista de actividades de marketing.

#### Navigation {#navigation}

* Ahora puede utilizar la tecla de tabulación para navegar correctamente entre los campos de la misma página.

## Release 15.4 - April 2015 {#release-15-4---april-2015}

### New capabilities {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Package exports / Package imports<br /> </td> 
   <td> The <strong>Deployment</strong> menu now allows users with admin rights to exchange resources between different Adobe Campaign instances by exporting and importing packages.<br /> Consulte la documentación <a href="../../automating/using/managing-packages.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> All reports (except the <strong>Hot clicks</strong> report) can now be accessed from a program. These reports are:<br /> 
    <ul> 
     <li> Rendimiento de entrega del programa </li> 
     <li> Indicadores de seguimiento de programas </li> 
     <li> Desglose de programas por dominio </li> 
     <li> Programa no entregado y devoluciones </li> 
     <li> URL del programa y clics en flujos </li> 
    </ul> Estos informes pueden filtrarse durante un período determinado (por ejemplo, tres meses, seis meses, etc.). Los informes de campaña también pueden filtrarse.<br /> Consulte la documentación <a href="../../reporting/using/about-dynamic-reports.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Email delivery</strong> activity<br /> </td> 
   <td> The <strong>Email delivery</strong> activity in the workflows has been improved. Ahora puede encontrar correos electrónicos, correos electrónicos recurrentes e información detallada sobre ejecuciones de correo electrónico recurrentes desde la lista de actividades de marketing de aplicaciones.<br /> Consulte la documentación <a href="../../automating/using/email-delivery.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: <strong>Segmentation</strong> activity<br /> </td> 
   <td> The <strong>Segmentation</strong> activity is now available in the workflows. Esta actividad permite crear uno o varios segmentos y vincular un código de segmento a partir de una población calculada por actividades que se hayan colocado en el flujo de trabajo en el mismo flujo de trabajo. Desde esta actividad, los segmentos se pueden procesar en una sola transición o en varias transiciones múltiples. Ahora hay opciones para filtrar la población y limitar el tamaño de cada segmento para optimizar la personalización. Por ejemplo, puede seleccionar de forma aleatoria perfiles que correspondan a criterios específicos.<br /> Consulte la documentación <a href="../../automating/using/segmentation.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Assets Core Service</strong><br /> </td> 
   <td> You can now use shared resources via <strong>Assets Core Service</strong> in your email and landing page contents. Puede administrar los recursos compartidos directamente desde Adobe Marketing Cloud.<br /> Consulte la documentación <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integrations: <strong>Adobe Target</strong><br /> </td> 
   <td> You can now insert images that are dynamically computed by <strong>Adobe Target</strong> into your Adobe Campaign emails. Esto le permite ofrecer varias versiones del mismo mensaje de correo electrónico personalizando el contenido según los criterios definidos en los segmentos de Adobe Target.<br /> Consulte la documentación <a href="../../integrating/using/about-campaign-target-integration.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Digital Content Editor: <strong>Block selector</strong><br /> </td> 
   <td> Cuando se selecciona un bloque en el editor de contenido HTML, se muestra una ruta de navegación en la parte inferior de la zona de edición. Esto le permite desplazarse y seleccionar fácilmente distintos elementos.<br /> Consulte la documentación <a href="../../designing/using/managing-landing-page-structure-and-style.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.3 - March 2015 {#release-15-3---march-2015}

### New capabilities {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Functionality<br /> </th> 
   <th> Description<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reports<br /> </td> 
   <td> Ahora se puede acceder a los informes directamente desde un programa o una campaña. The <strong>Delivery summary</strong> report has been added at a program level.<br /> Consulte la documentación <a href="../../reporting/using/delivery-summary.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Update data<br /> </td> 
   <td> In the workflows, the available <strong>Update data</strong> activity has a new option, which allows you to automatically link inbound data fields with the fields of an application schema. Esto ayuda a facilitar el proceso de selección para actualizar los campos.<br /> Consulte la documentación <a href="../../automating/using/update-data.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email delivery<br /> </td> 
   <td> In workflows, the advanced options of the <strong>Email delivery</strong> activity can now be accessed via a specific button in the action bar. This button is only available if an <strong>Email delivery</strong> activity is selected. El principal beneficio es que permite agregar una transición saliente a la actividad y editar el nombre de la actividad tal como se muestra en el flujo de trabajo.<br /> Consulte la documentación <a href="../../automating/using/email-delivery.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-14}

#### General {#general-10}

* Se ha corregido un error que impedía que el destinatario se mostrara al crear una entrega.
* Se ha corregido un error que impedía que se usara una audiencia basada en una condición'Destinatarios que han abierto '.
* Se ha corregido un error que impedía eliminar un perfil vacío.
* Se ha corregido un error que se producía al obtener una vista previa de una entrega.
* Se ha corregido un error que impedía que se duplicara una actividad de marketing.
* Se corrigió un error que se producía al eliminar una campaña.

