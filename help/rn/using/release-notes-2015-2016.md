---
title: Notas de la versión 2015-2016
seo-title: Notas de la versión 2015-2016
description: Notas de la versión 2015-2016
seo-description: Esta página enumera todas las versiones de 2015 y 2016 de Adobe Campaign Standard.
page-status-flag: nunca activado
uuid: d5a0f6cc-0bed-46cf-8dff-1717fb624f8f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: referencia
topic-tags: campaign-standard-releases
discoiquuid: a3ce6b80-1858-49d1-8880-3543181127f4
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 159c33639ab7b53558dac2ce183c3801c15ccb0f

---


# Release Notes 2015-2016{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard para 2015-2016?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

Vea las últimas actualizaciones [de](../../rn/using/documentation-updates.md) documentación de Adobe Campaign Standard. Si busca una versión más reciente, consulte esta [página](../../rn/using/release-notes.md).

## Versión 16.11: noviembre de 2016 {#release-16-11---november-2016}

### Nuevas capacidades {#new-capabilities}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Reglas de exclusión de la entrega<br /> </td> 
   <td> Ahora se administra una lista de supresión global cifrada en la instancia de entregabilidad para evitar ser bloqueada debido a una actividad maliciosa, especialmente el uso de Spamtrampa.<br /> Para cada envío de correo electrónico, dos reglas de tipología predeterminadas comparan las direcciones de correo electrónico del destinatario con las direcciones o nombres de dominio prohibidos que contiene esta lista. Si hay una coincidencia, ese destinatario se excluye de la población objetivo.<br /><a href="../../administration/using/filtering-rules.md#default-deliverability-exclusion-rules"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Optimización general<br /> </td> 
   <td> Esta actualización incluye numerosos cambios y parches que corrigen problemas encontrados por nuestros clientes. También se han optimizado los resultados de la plataforma global. <br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches}

#### General {#general}

* Se han corregido varios problemas de seguridad.
* Se corrigieron varios problemas relacionados con campos vacíos o campos duplicados en la API de REST.
* Ahora puede crear mensajes SMS y notificaciones push directamente desde la página principal de la aplicación.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages}

* Se ha corregido un problema que impedía a los usuarios cargar archivos zip en el editor de contenido.
* Se ha corregido un problema que impedía abrir una prueba después de enviarla.
* Se ha corregido un problema que provocaba que se mostrara un mensaje de error al acceder al informe en un correo electrónico de prueba A/B. **[!UICONTROL Hot Clicks]**
* Se ha corregido un problema que impedía que se aplicaran las modificaciones realizadas con el **[!UICONTROL Show source]** modo.
* Se ha corregido un problema que podía impedir la importación de archivos de modelo XML de línea de asunto predictiva.
* Ya está disponible una nueva pantalla dedicada a la importación de datos para el modelo de línea de asunto entrenado en **[!UICONTROL Administration > Channels > Emails > Predictive Subject Line]** .
* Se ha corregido un problema que permitía a los usuarios no administradores editar las máscaras autorizadas en la pantalla de configuración de correo electrónico.

#### Notificaciones push {#push-notifications}

* Se ha corregido un problema que impedía que se mostraran registros de envío y registros de eventos para los destinatarios después de enviar una notificación push mediante la **[!UICONTROL Send push on profiles]** plantilla.
* Se ha corregido un problema que podía impedir que se crearan nuevas aplicaciones móviles.

#### Workflows {#workflows}

* Se ha corregido un problema de rendimiento que se producía al usar la **[!UICONTROL Subscription]** actividad.
* Se ha corregido un problema que impedía que un flujo de trabajo funcionara cuando su nombre interno contenía un espacio.

#### Integraciones {#integrations}

* Se ha corregido un problema que podía provocar que se mostrara un error al usar la opción **Imagen compartida desde Adobe Marketing Cloud** en un correo electrónico.

#### Recursos personalizados {#custom-resources}

* Las API mejoradas previsualizan el registro entre dos publicaciones de campos API extendidos.
* Se ha corregido un problema que impedía que un recurso personalizado se eliminara antes de publicarse.
* Se ha corregido un problema que impedía que se extendieran los perfiles y que las claves de identificador se establecieran con un campo dinámico.
* Se ha corregido un problema que se podía producir al agregar vínculos en un recurso personalizado.

## Versión 16.10: octubre de 2016 {#release-16-10---october-2016}

### Nuevas capacidades {#new-capabilities-1}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Línea de asunto predictiva de correo electrónico<br /> </td> 
   <td> Al editar un mensaje de correo electrónico, una nueva opción le permite probar distintas líneas de asunto y obtener una estimación de su tasa de apertura antes de enviarlo. Esto es posible formando su propio modelo en función de los datos de entrega anteriores o utilizando un modelo predefinido específico de su sector. Esta función está disponible para los mensajes de correo electrónico y para las bases de datos que solo contienen contenido en inglés. <br /> Para obtener más información sobre cómo habilitarla y utilizarla, consulte la documentación <a href="../../designing/using/subject-line.md#predictive-subject-line"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensajes transaccionales SMS<br /> </td> 
   <td> El canal SMS se ha agregado a las capacidades de mensajería transaccional de Adobe Campaign. Ahora se admiten dos canales para los mensajes transaccionales: correo electrónico y SMS.<br /><a href="../../administration/using/configuring-transactional-messaging.md#creating-an-event"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensaje de seguimiento para mensajes transaccionales<br /> </td> 
   <td> Ahora es posible crear un flujo de trabajo dirigido a un evento. Esto significa que puede enviar un mensaje de seguimiento a los clientes que ya han recibido un mensaje transaccional. Puede filtrar el objetivo según el tipo de evento, los logs de eventos y los registros de seguimiento. En el mensaje de seguimiento, podrá aprovechar el contenido del evento (carga útil). <br /><a href="../../channels/using/follow-up-messages.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de perfiles y servicios extendidos<br /> </td> 
   <td> Ahora puede exponer campos extendidos en la API de perfil y servicios. El mecanismo de publicación permite a las API asignar los campos extendidos de los recursos personalizados de Profiles o Services. Para que esto funcione, se ha agregado la función <strong>Datamodel</strong> . Esta nueva función permite al usuario configurar un conjunto de administradores que tendrán acceso al modelo de datos.<br /><a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-1}

#### General {#general-1}

* Se han corregido varios problemas de seguridad.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-1}

* Se ha mejorado la pantalla de configuración de la cuenta externa de SMS ( **[!UICONTROL Administration > Channels > SMS > SMS accounts]** ). Se han agregado varios parámetros en la sección para admitir códigos de error en el campo "Texto". **[!UICONTROL SMSC specifics]**

#### Notificaciones push {#push-notifications-1}

* Se ha corregido un problema que impedía que se mostraran los filtros predefinidos al editar la audiencia de una notificación push basada en la plantilla **[!UICONTROL Send via push notification]** (mobileApp).
* La pantalla de configuración de la aplicación móvil ( **[!UICONTROL Administration > Channels > Push Notification > Mobile applications]** ) ahora muestra un mensaje para indicar que la plataforma iOS o Android se ha creado correctamente.

#### Páginas de destino {#landing-pages}

* Se han corregido problemas que evitaban que se enviaran correos electrónicos de confirmación al enviar un formulario de página de aterrizaje.

#### Audiencias y consultas {#audiences-and-queries}

* Se han corregido varios problemas que se producían al seleccionar un perfil en el editor de consultas.

#### Mensajes transaccionales {#transactional-messages}

* Se corrigió un error que impedía que se cancelara la publicación de una plantilla transaccional.
* Se ha corregido un problema que provocaba que los eventos se mostraran en la lista de eventos.

#### Integraciones {#integrations-1}

* Se ha corregido un problema que impedía que una audiencia compartida se usara en una entrega después de que se actualizara dicha audiencia.
* Se ha corregido un problema que impedía que un recurso compartido ( **[!UICONTROL Image shared from Adobe Marketing Cloud]** opción) se utilizara en una página de aterrizaje.
* Se han corregido problemas que se producían al editar una audiencia compartida importada desde Adobe Audience Manager.

## Versión 16.9: septiembre de 2016 {#release-16-9---september-2016}

### Nuevas capacidades {#new-capabilities-2}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Activadores de remercadotecnia<br /> </td> 
   <td> Integration between the core service <span class="uicontrol">Triggers</span> and Adobe Campaign allows you to send personalized emails to your customers as a reaction to specific behaviors that are tracked on your website by Adobe Analytics (within 15 minutes).<br /> En Adobe Marketing Cloud, se definen los distintos activadores, es decir, los comportamientos del cliente que se desea supervisar, como todos los clientes que abandonaron el carro de compras o el formulario, que quitaron un producto del carro de compras o incluso los clientes cuya sesión expiró. Al crear un activador, se define la condición del activador y los datos que se enviarán en el evento (carga) a Adobe Campaign. <br /> En Adobe Campaign, se selecciona el activador que se creó anteriormente, se enriquecen los datos del evento con datos de datamart y se define una plantilla de mensaje transaccional vinculada a ese activador. Por ejemplo, cuando un cliente abandona el carro de compras, se envía un evento a Adobe Campaign que puede aprovechar este evento mediante un correo electrónico de remercadotecnia que se envía al cliente en un plazo de 15 minutos.<br /><a href="../../integrating/using/about-adobe-experience-cloud-triggers.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensajes transaccionales: Pausar / Cancelar la publicación<br /> </td> 
   <td> Ahora puede suspender la publicación de una plantilla transaccional mientras actualiza su contenido. Los mensajes correspondientes ya no se envían, pero se almacenan en la base de datos. Al reanudar, los mensajes en cola se procesan y se envían si no han caducado.<br /><a href="../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication"> Para obtener más información, consulte la documentación detallada</a>.<br /> Ahora también puede cancelar la publicación de eventos y plantillas transaccionales. Los mensajes correspondientes ya no se envían y no se almacenan en la base de datos.<br /><a href="../../channels/using/event-transactional-messages.md#unpublishing-a-transactional-message"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Multimarca<br /> </td> 
   <td> Los clientes con varias marcas ahora pueden administrarlas en la misma instancia. La promoción de marca es una función administrada por el administrador de la instancia de Adobe Campaign que le permite configurar de forma centralizada todos los parámetros relacionados con una marca dentro de Adobe Campaign. Esto incluye aspectos como el logotipo para parámetros más técnicos como URL de seguimiento, análisis web, URL del servidor, nombre de dominio, etc.<br /><a href="../../administration/using/branding.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Vista previa del diseño de correo electrónico adaptable<br /> </td> 
   <td> Esta función le permite probar la capacidad de respuesta del correo electrónico en diferentes tipos de dispositivos. En la vista previa del correo electrónico, se ha agregado una cuadrícula para probar el correo electrónico en varios tamaños de pantalla.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push<br /> </td> 
   <td> Se ha agregado un nuevo canal para permitir a los especialistas en marketing enviar notificaciones push personalizadas y segmentadas en dispositivos móviles iOS y Android. Los mensajes se pueden enviar a través de una única entrega o mediante una actividad de flujo de trabajo. La compatibilidad con los mensajes transaccionales estará disponible en versiones futuras. Este canal aprovecha el SDK del servicio principal de Mobile (disponible <a href="https://marketing.adobe.com/developer/gallery/marketing-cloud-mobile-libraries">aquí</a>).<br /><a href="../../channels/using/about-push-notifications.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-2}

#### General {#general-2}

* Esta versión incorpora nuevas funciones de filtrado y búsqueda en las listas de interfaz. Esta nueva función está disponible, por ejemplo, en los registros (entrega, seguimiento), servicios (suscripción, historial de suscripciones), audiencias y transiciones de flujo de trabajo.
* Se han corregido varios problemas de visualización relacionados con el número de puntos de contacto en un perfil de cliente.
* Se han corregido varios problemas de tipología.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-2}

* Se ha corregido un error que permitía editar pruebas erróneas. Ahora son de sólo lectura.
* Se ha corregido un problema que provocaba que un destinatario se bloqueara cuando un SMS era demasiado largo o tenía problemas de codificación.

#### Recursos personalizados {#custom-resources-1}

* Se ha corregido un error que impedía que se mostraran todos los resultados al utilizar los filtros avanzados de un recurso personalizado.

#### Mensajes transaccionales {#transactional-messages-1}

* Ahora se agrega automáticamente un prefijo al identificador de una nueva definición de evento.
* Se ha cambiado el icono que representa los mensajes transaccionales en la interfaz.

#### Integraciones {#integrations-2}

* Se corrigió un error de visualización que se producía cuando se insertaba una imagen de alta resolución mediante la opción Imagen **dinámica de Adobe Target** .
* Se ha corregido un error que permitía guardar una audiencia compartida aunque el ID de destino no se hubiera establecido en la fuente de datos de AMC.

## Versión 16.7: julio de 2016 {#release-16-7---july-2016}

### Nuevas capacidades {#new-capabilities-3}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Mensajes transaccionales enriquecidos<br /> </td> 
   <td> Ahora puede vincular plantillas transaccionales con la base de datos de Adobe Campaign para recuperar información que le permita enriquecer el contenido de los mensajes transaccionales.<br /><a href="../../administration/using/configuring-transactional-messaging.md#enriching-the-transactional-message-content"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direcciones URL dinámicas para imágenes<br /> </td> 
   <td> Esta nueva funcionalidad le permite personalizar una fuente de imágenes mediante la inserción de bloques de contenido y texto dinámico para fines de seguimiento y personalización.<br /> A continuación, es posible, entre otras cosas, aprovechar las funcionalidades de los medios dinámicos de AEM Asset (S7) introduciendo parámetros en las direcciones URL de las imágenes. Por ejemplo, puede enviar un correo electrónico con imágenes personalizadas que indiquen "Hola Alexandre, ¡obtenga las últimas noticias sobre los próximos eventos en París!" o "Hola Frank, ¡obtenga las últimas noticias sobre los próximos eventos en Nueva York!".<br /><a href="../../designing/using/personalization.md#personalizing-urls"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración con el servicio principal Personas<br /> </td> 
   <td> Los ID <strong>declarados</strong> de Adobe Marketing Cloud ahora están cubiertos por la integración entre Adobe Campaign y el servicio principal Personas (perfiles y audiencias).<br /><strong> Esto significa que puede importar segmentos y exportar audiencias compuestas por </strong>ID de visitante o<strong>ID </strong>declarados<br />de visitante.Para obtener más información, consulte la documentación <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Registros de envío<br /> </td> 
   <td> Los registros de MTA (servidor de entrega) ahora muestran el historial completo de cada mensaje, en particular todos los intentos de entrega, así como los estados de error asociados, y esto no afecta al rendimiento de la aplicación.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-3}

#### General {#general-3}

* Se ha corregido un error que podía hacer que se mostraran campos irrelevantes en lugar de campos que debían completarse. Esto sucedería después de que el operador de comparación se modificara varias veces al editar una condición en una consulta.
* Se corrigió el comportamiento de la opción **[!UICONTROL The last X days/months/quarters/years]** al definir una condición de filtrado relativa para un campo de fecha. El período calculado es ahora un período deslizante en relación con la fecha y la hora del servidor y no basado en el calendario.

#### Workflows {#workflows-1}

* Se corrigió un error que devolvía una lista incorrecta de valores en la pantalla para seleccionar la dimensión de objetivo en las propiedades de una **[!UICONTROL Query]** actividad.
* Se corrigió un error que obligaba al operador **Existe** a seleccionarse al agregar un promedio o recuento de agregado en un elemento de recopilación en una **[!UICONTROL Query]** actividad.

#### Edición de contenido {#content-editing}

* Se ha corregido un error que podía provocar problemas de visualización (diseño interactivo) al importar contenido HTML: los atributos de estilo ya no se vuelven a escribir cuando el contenido se abre por primera vez después de importarse.
* Se corrigió un error de no bloqueo que se producía cuando se agregaba una condición en una variante de contenido dinámico.
* Se corrigió un error que se producía al agregar una casilla de verificación en el contenido de una página de aterrizaje. La casilla de verificación no se podía utilizar.
* Se ha corregido un error que se podía producir al eliminar texto de un bloque si el cursor se colocaba al principio del bloque en cuestión.

#### Mensajes transaccionales {#transactional-messages-2}

* Al integrar un sitio web, ahora puede definir una fecha de caducidad para cualquier evento determinado. Una vez pasada esta fecha, ya no se puede enviar el mensaje correspondiente al evento.

## Versión 16.6: junio de 2016 {#release-16-6---june-2016}

### Nuevas capacidades {#new-capabilities-4}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> API de perfiles y servicios<br /> </td> 
   <td> La API de <span class="uicontrol">perfiles y servicios</span> de Adobe Campaign está disponible en el portal <a href="https://www.adobe.io/products/campaign">adobe.io</a> . Esto permite actualizar, añadir y eliminar perfiles de Adobe Campaign, así como suscribirse o cancelar la suscripción a los servicios mediante llamadas REST.<br /> Para obtener más información, consulte la descripción <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">detallada de la API</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-4}

#### General {#general-4}

* Ahora, la información sobre herramientas está desactivada en los dispositivos móviles para garantizar que la información mostrada en la pantalla sea fácil de leer.
* Se ha corregido un error que impedía al usuario desplazarse por el contenido de determinadas zonas en la pantalla del iPad.
* Se corrigieron varios errores de compatibilidad encontrados al editar contenido en Internet Explorer 11.
* Se ha corregido un error que podía impedir el acceso a registros detallados cuando la importación de datos fallaba por primera vez.
* Se ha corregido un error que podía impedir que se guardara un filtro de rango.
* Se ha corregido un error que impedía que se mostraran elementos de un recurso al configurar la forma en que se muestra una lista.
* Se corrigió un error en el explorador del editor de consultas. Los resultados devueltos por el campo de búsqueda se guardaban en el historial de búsqueda y se seguían mostrando en cada nueva búsqueda.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-3}

* Se ha corregido un error que impedía que la información vinculada a devoluciones se recuperara en los registros de entrega.
* Se corrigió un error que impedía el acceso al contexto en un bloque de contenido dinámico de un mensaje transaccional.
* Se ha corregido un error que impedía que un vínculo URL se definiera en texto dinámico en el contenido de un correo electrónico.
* Se corrigió la visualización de la barra superior del asistente para la creación de envíos.
* La clave principal de una entrega ya no se puede usar como campo de personalización.

#### Workflows {#workflows-2}

* Las transiciones entre dos actividades de un flujo de trabajo ahora muestran el recuento de elementos computados y transferidos de una actividad a otra.
* Los campos incompatibles ahora se ocultan cuando se agregan datos adicionales a una **[!UICONTROL Query]** actividad.
* La ventana de definición agregada, que se muestra al agregar datos adicionales, se ha mejorado para ofrecer únicamente opciones compatibles con los datos en uso (por ejemplo: solo es posible calcular una media para datos numéricos).
* Ahora, el inicio o reinicio de un flujo de trabajo técnico integrado solo puede realizarlo un usuario con derechos de administración.

#### Páginas de destino {#landing-pages-1}

* Se ha corregido un error que podía truncar las claves de codificación AES de 32 bits en las propiedades de una página de aterrizaje.
* Se ha corregido un error que impedía que el editor de consultas se mostrara correctamente al definir una condición de visibilidad o al agregar contenido dinámico a una página de aterrizaje.

#### Recursos personalizados {#custom-resources-2}

* La **[!UICONTROL Switch to parameters]** opción ahora está oculta al definir un filtro relacionado con las suscripciones de un perfil a un servicio.
* Se corrigió un error que se podía producir cuando se configuraba un vínculo de tipo 0-1 desde un recurso personalizado.
* Se corrigió un error que, cuando era pertinente, podía impedir que se editara el valor **predeterminado de** Constante definido al agregar un campo de tipo **Fecha y hora** en un recurso personalizado.

## Versión 16.5: mayo de 2016 {#release-16-5---may-2016}

### Nuevas capacidades {#new-capabilities-5}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Filtros predefinidos<br /> </td> 
   <td> Los administradores ahora pueden crear filtros avanzados que aparecen en el editor de consultas en forma de reglas preconfiguradas. La selección de estos filtros permite a los usuarios desarrollar configuraciones complejas más fácilmente en una interfaz simplificada al definir una audiencia, por ejemplo.<br /><a href="../../developing/using/configuring-filter-definition.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo:Servicios de suscripción<br /> </td> 
   <td> Una nueva actividad de Servicios <span class="uicontrol">de</span> suscripción ofrece la posibilidad de suscribir varios perfiles a un servicio o de cancelarlos de un servicio con una sola acción.<br /> Esta actividad se puede utilizar después de haber realizado un objetivo o de haber importado un archivo con datos identificados.<br /><a href="../../automating/using/subscription-services.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: enriquecimiento de datos<br /> </td> 
   <td> La ficha Datos <span class="uicontrol"></span> adicionales ahora está disponible en actividades de tipo <span class="uicontrol">Consulta</span> . Esta funcionalidad le permite enriquecer los datos dirigidos por la consulta y transferirlos a las siguientes actividades de flujo de trabajo donde se pueden aprovechar.<br /> Después de agregar datos adicionales, puede aplicar un nivel de filtro adicional a los datos objetivo inicial creando condiciones basadas en los datos adicionales definidos.<br /><a href="../../automating/using/query.md#enriching-data"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Ayuda contextual<br /> </td> 
   <td> Ahora hay una función de ayuda contextual disponible en las distintas pantallas de Adobe Campaign. Esto significa que, con un solo clic, puede acceder directamente a la documentación sobre la funcionalidad que está utilizando actualmente. Para mostrar la ayuda contextual, haga clic en el botón '?' en la esquina superior derecha de la pantalla, como se muestra en el ejemplo siguiente.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-5}

#### General {#general-5}

* Diversas interfaces Nuevas funciones que cumplen los estándares de Marketing Cloud.
* Estandarización de los distintos tipos de listas desplegables.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-4}

* Se ha corregido un error que impedía que se enviaran correos electrónicos si se especificaba la máscara de dirección de error.
* El protocolo TLS ahora se admite para la entrega por correo electrónico. Una nueva columna en la administración MX permite definir el comportamiento TLS deseado para cada dominio.
* Se ha mejorado la interfaz de SMS.

#### Workflows {#workflows-3}

* Diversas interfaces de flujo de trabajo Nuevas funciones.
* Se corrigió un error que se producía al mostrar acciones rápidas.
* Se ha corregido un error que podía hacer que un flujo de trabajo fallara al usar una actividad de **[!UICONTROL Segmentation]** tipo que contenía un vínculo 1-N.
* Se ha corregido un error que impedía que las transiciones de un flujo de trabajo se abrieran en un dispositivo híbrido.
* Se ha corregido un error que impedía que se mostrara el botón de pausa al iniciar un flujo de trabajo por primera vez.

#### Editor de contenido {#content-editor}

* El editor de contenido ahora permite personalizar cualquier dirección URL contenida en un correo electrónico o una página de aterrizaje. Consulte la documentación [detallada](../../designing/using/personalization.md#personalizing-urls).
* Se ha corregido un error que podía hacer que las imágenes se perdieran al agregarlas al asistente de creación de la entrega y al modificar su contenido posteriormente.

#### Recursos personalizados {#custom-resources-3}

* Se corrigió un error que se producía al agregar un vínculo personalizado de tipo 1-N en la pantalla de configuración de un recurso personalizado.
* Se ha mejorado la visualización de la barra de progreso al preparar y publicar recursos personalizados.
* Se corrigió un error que se producía al mostrar la lista de vínculos de un recurso personalizado.

#### Mensajes transaccionales {#transactional-messages-3}

* Se ha optimizado la facilidad de uso de la interfaz, así como el rendimiento y la solidez del motor de mensajes transaccionales.
* Ahora es posible suspender temporalmente la publicación de una plantilla de mensaje transaccional. For more on this, refer to the [detailed documentation](../../channels/using/event-transactional-messages.md#suspending-a-transactional-message-publication).
* Se ha corregido un error que podía hacer que se agregara un bloque de contenido con una dimensión de objetivo incompatible a una plantilla de mensaje transaccional.
* Se ha corregido un error que impedía que la vista previa de la API se mostrara en una pantalla de configuración de eventos.

#### Audiencias y consultas {#audiences-and-queries-1}

* Varios parches con respecto al uso de fechas en el editor de consultas. Consulte la documentación [detallada](../../automating/using/editing-queries.md#creating-queries).

#### Administración {#administration}

* Se corrigió un error con respecto al nombre del grupo de seguridad "Usuarios estándar" que impedía que los usuarios iniciaran sesión.

## Versión 16.3: marzo de 2016 {#release-16-3---march-2016}

### Nuevas capacidades {#new-capabilities-6}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Interfaz y navegación<br /> </td> 
   <td> La interfaz de Adobe Campaign se ha mejorado para que la navegación y las operaciones sean sencillas e intuitivas.<br /> Ahora puede desplazarse desde la barra superior de la aplicación. Se puede acceder a los menús avanzados seleccionando el logotipo de <strong>Adobe Campaign</strong> .<br /><a href="../../start/using/interface-description.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo:Guardar audiencia<br /> </td> 
   <td> Ahora hay una nueva opción, <span class="uicontrol">Crear y actualizar una audiencia</span> , disponible en la actividad <span class="uicontrol">Guardar audiencia</span> . Esta opción le permite introducir manualmente una etiqueta de audiencia. Si la etiqueta especificada corresponde a una audiencia existente, se actualizará. Si la audiencia no existe, se creará.<br /> Además, la audiencia se actualizará cada vez que se ejecute el flujo de trabajo (de nuevo).<br /> Siempre puede seleccionar el modo de actualización de audiencia: complete la audiencia con nuevos datos o reemplace todos los datos de audiencia en cada ejecución.<br /><a href="../../automating/using/save-audience.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo:Segmentación<br /> </td> 
   <td> La actividad <span class="uicontrol">Segmentación</span> ahora permite al usuario segmentar los datos de un recurso temporal.  Por ejemplo: los datos de un archivo importado.<br /><a href="../../automating/using/segmentation.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-6}

#### General {#general-6}

* Se corrigió un error de visualización que se producía al ordenar una lista: la flecha que indica el orden de una columna sólo se puede invertir para determinados tipos de datos.
* Se corrigió un error que limitaba el número de elementos mostrados en un menú desplegable cuando se agregaba una regla a una consulta.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-5}

* Se ha corregido un error que podía impedir el acceso al informe de procesamiento de correo electrónico.
* La etapa de preparación del envío de un mensaje ahora devuelve un error si no se proporciona la dirección del remitente.

#### Workflows {#workflows-4}

* Algunas opciones de formato de archivo eran visibles pero no se tenían en cuenta al extraer un archivo con formato CSV. Estas opciones ya no están visibles.
* Se corrigió un error que se producía cuando se comprobaba la **[!UICONTROL Delete the source files after transfer]** opción para la transferencia de un **[!UICONTROL SFTP]** tipo de archivo.
* Se corrigió un error que podía evitar que el contador y la vista previa de los datos se mostraran después de actualizar la página. **[!UICONTROL Query]**
* Se corrigió un error que se producía al abrir ciertas transiciones en un flujo de trabajo, especialmente después de una actividad de entrega o de una consulta en la que las dimensiones de filtrado y objetivo eran diferentes.
* Se ha corregido un error que impedía que un campo de personalización se insertara en una actividad de entrega de un flujo de trabajo si el flujo de trabajo no se guardaba después de agregar la actividad.
* Se ha corregido un error que impedía que se mostrara la dimensión de segmentación de transición de salida de una actividad de envío de correo electrónico.

#### Páginas de destino {#landing-pages-2}

* Se ha corregido un error que impedía que los campos de personalización funcionaran correctamente en un bloque de contenido localizable en una página de aterrizaje.

#### Recursos personalizados {#custom-resources-4}

* Se corrigió un error que impedía realizar una búsqueda en un recurso personalizado si se seleccionaba la **[!UICONTROL Add search fields]** opción de la definición de la pantalla de recursos y si se seleccionaban varios campos en la **[!UICONTROL Filter zone composition]** .

## Versión 16.2: febrero de 2016 {#release-16-2---february-2016}

### Nuevas capacidades {#new-capabilities-7}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Prueba A/B para correos electrónicos<br /> </td> 
   <td> Ahora puede realizar pruebas A/B sobre el contenido, el asunto o el nombre del remitente de sus correos electrónicos. Esta nueva funcionalidad puede probar hasta tres variantes de un elemento.<br /> Al crear un correo electrónico a partir de una de las nuevas plantillas específicas de las pruebas A/B, un nuevo paso en el asistente de creación le permite definir los parámetros de la prueba.<br /><a href="../../channels/using/designing-an-a-b-test-email.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Administración de marcas<br /> </td> 
   <td> Ahora puede definir una o varias marcas para introducir de forma centralizada los parámetros que afectan a la identidad de una marca. Adobe Campaign permite crear estas marcas y vincularlas a las plantillas de página de aterrizaje o de entrega.<br /><a href="../../administration/using/branding.md#assigning-a-brand-to-an-email"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo:Consulta incremental<br /> </td> 
   <td> Una nueva actividad de flujo de trabajo, la consulta <span class="uicontrol"></span> incremental, le permite realizar una consulta que, en cada ejecución, segmenta únicamente los nuevos resultados. Los resultados de ejecuciones anteriores se excluyen automáticamente. Vinculada a una actividad de <span class="uicontrol">Programador</span> , puede definir la frecuencia de ejecución de la consulta <span class="uicontrol"></span> incremental.<br /><a href="../../automating/using/incremental-query.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensajes transaccionales<br /> </td> 
   <td> Se ha mejorado la facilidad de uso de la interfaz de mensajes transaccionales. Toda la administración de procesos comerciales vinculada a mensajes transaccionales está actualmente centralizada en el menú Planes <span class="uicontrol">de</span> marketing &gt; Mensajes <span class="uicontrol"></span> transaccionales. También se ha mejorado la configuración de eventos. Los eventos ahora se administran de forma independiente de los recursos personalizados.<br /><a href="../../channels/using/about-transactional-messaging.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-7}

#### General {#general-7}

* Se corrigieron varios errores de visualización en informes, listas y consultas.
* Se han corregido varios errores de compatibilidad y visualización en dispositivos móviles.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-6}

* Se ha corregido un error que podía impedir que se mostrara el botón utilizado para insertar campos de personalización al crear un mensaje (correo electrónico o SMS).
* Se ha corregido un error que podía impedir que los mensajes SMS enviados a través de Mblox se transmitieran correctamente.

#### Audiencias y consultas {#audiences-and-queries-2}

* Se corrigió un error de recuento que podía producirse al agregar una condición adicional en una consulta, después de haber modificado la dimensión de filtrado.
* Se ha corregido un error que podía provocar una paginación incorrecta al obtener una vista previa de los resultados de una consulta.

#### Edición de contenido {#content-editing-1}

* Se ha corregido un error que podía impedir que la configuración de contenido dinámico se tuviera correctamente en cuenta al usar una enumeración personalizada.

#### Workflows {#workflows-5}

* Se ha corregido un error que podía impedir que se realizara cualquier acción en un flujo de trabajo si había una línea vacía en la **[!UICONTROL Fields to update]** ficha de una **[!UICONTROL Update data]** actividad.
* Se ha corregido un error que impedía que se importaran datos que contenían información geográfica/de unidad organizativa.
* Se corrigió un error que se producía al agregar un **[!UICONTROL Change axis]** tipo de **[!UICONTROL Exclusion]** regla.
* Se ha corregido un error que podía hacer que se creara un segmento adicional no deseado al manipular una transición de salida de una **[!UICONTROL Segmentation]** actividad.
* Se ha corregido un error que se producía al cargar un archivo en una plantilla de flujo de trabajo.
* Se ha corregido un error que podía impedir que los espacios se usaran como separadores de columnas en una **[!UICONTROL Load file]** actividad.

#### Recursos personalizados {#custom-resources-5}

* Se corrigió un error que impedía que se volviera a redactar el estado de un recurso personalizado después de importar un paquete, si el recurso se había publicado en el momento de la exportación.

#### Paquetes {#packages}

* Se ha corregido un error que impedía exportar un paquete que contenía un flujo de trabajo.
* Se ha corregido un error que podía impedir que se seleccionaran varios elementos del mismo recurso.

## Versión 16.1: enero de 2016 {#release-16-1---january-2016}

### Nuevas capacidades {#new-capabilities-8}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Informes<br /> </td> 
   <td> Se han agregado los siguientes informes específicos de correo electrónico: <span class="uicontrol">Quejas</span> , <span class="uicontrol">aperturas</span> y <span class="uicontrol">cancelaciones</span> .<br /> Se han mejorado los siguientes informes: Resumen <span class="uicontrol"></span> de envío, resumen <span class="uicontrol">de</span> devolución, rendimiento <span class="uicontrol">de</span> entrega e indicadores <span class="uicontrol">de seguimiento</span> .<br /><a href="../../reporting/using/defining-the-report-period.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Edición de consultas<br /> </td> 
   <td> El editor de consultas se ha mejorado y ahora permite analizar los vínculos de tipo <strong>1-N</strong> .<br /><a href="../../automating/using/editing-queries.md#creating-queries"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Personalización del contenido<br /> </td> 
   <td> En cuanto a la edición de páginas de aterrizaje o correo electrónico, se ha mejorado la interfaz de entrada para las condiciones de visualización de bloques de contenido.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: definición de columna al importar<br /> </td> 
   <td> La actividad <span class="uicontrol">Cargar archivo</span> ahora permite configurar las columnas de un archivo importado en detalle: tipo de datos esperado, formato de fecha y hora, procesamiento que se aplicará en caso de un valor vacío o un error, y reasignación de valores.<br /><a href="../../automating/using/load-file.md#column-format"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Asignación de codificaciones de SMS<br /> </td> 
   <td> Ahora es posible definir asignaciones de codificaciones de mensajes SMS personalizados para proveedores que no utilizan codificación estándar. Un administrador puede realizar la configuración de asignaciones personalizadas y definir el orden en el que deben tenerse en cuenta.<br /><a href="../../administration/using/configuring-sms-channel.md#smsc-specifics"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-8}

#### General {#general-8}

* Compatibilidad mejorada con Internet Explorer y Chrome para dispositivos híbridos/de pantalla táctil.
* Se ha corregido un error que podía provocar la pérdida de todos los datos introducidos para un nuevo perfil de usuario/perfil/prueba si la dirección de correo electrónico indicada contenía errores de sintaxis.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-7}

* Se ha corregido un error que podía impedir que la miniatura de contenido se generara en la pantalla de vista previa del correo electrónico.
* Se ha corregido un error que podía impedir que el contenido sin procesar de un mensaje (correo electrónico o SMS) se mostrara en la pantalla de vista previa del mensaje.

#### Audiencias y consultas {#audiences-and-queries-3}

* Se ha corregido un error que podía impedir que se creara una audiencia de tipo **Consulta** en el recurso **Servicio** .
* Se ha corregido un error que podía impedir que la lista de funciones se mostrara correctamente al editar una condición de una consulta en modo avanzado.
* Se ha corregido un error que podía impedir que se creara una audiencia de tipo **Consulta** si contenía criterios basados en colecciones.
* Se ha corregido un error que podía impedir que se crearan consultas que contenían filtros en KPI de entrega.
* Se ha corregido un error que podía impedir que se previsualizara el contenido de una audiencia creada a partir de un flujo de trabajo.

#### Recursos personalizados {#custom-resources-6}

* Se ha corregido un error que podía provocar un bloqueo del servidor si un recurso personalizado contenía un campo con un valor predeterminado dinámico.
* Se corrigió un error que se producía al mover y, a continuación, eliminar un elemento de la **[!UICONTROL Detail screen configuration]** sección al definir las pantallas de un recurso personalizado.
* Se corrigió un error que se producía cuando se había definido un valor predeterminado para una lista de **enteros** que no incluía **0** en su rango de valores posibles.
* Se ha corregido un error que podía impedir que se agregara un elemento en la configuración de la pantalla de detalles de un recurso personalizado después de una reinicialización.

#### Workflows {#workflows-6}

* Se ha corregido un error que podía hacer que se mostraran registros de todas las actividades de un flujo de trabajo en lugar de mostrar solo los de la actividad seleccionada.
* Se corrigió un error en la **[!UICONTROL Scheduler]** actividad. La **[!UICONTROL Day of the month]** opción no se tuvo correctamente en cuenta y se sustituyó por **[!UICONTROL Week day]** .
* Se ha corregido un error que podía impedir que una **[!UICONTROL Scheduler]** actividad funcionara correctamente con el modo de caducidad establecido en **[!UICONTROL After a certain number of iterations]** .
* Se corrigió un error que se producía al exportar datos mediante una **[!UICONTROL Extract file]** actividad. El número de líneas presentes en el archivo de exportación era inferior al número de elementos exportados.
* Se ha corregido un error que podía impedir que se seleccionara un archivo de una **[!UICONTROL Load file]** actividad.
* Se corrigió un error que impedía que se eliminaran los campos que se actualizaban en una **[!UICONTROL Update data]** actividad.
* Se ha corregido un error que impedía guardar las modificaciones realizadas en un flujo de trabajo después de abrir los registros de ejecución del flujo de trabajo.
* Se ha corregido un error que hacía que una **[!UICONTROL Load file]** actividad se ejecutara dos veces si se había configurado para usar el archivo desde su transición de entrada y este archivo se había cargado con una **[!UICONTROL Transfer file]** actividad.
* Se ha corregido un error que podía impedir que determinadas entidades temporales se procesaran correctamente mediante una actividad de **exclusión** .
* Se ha corregido un error que podía impedir que una **[!UICONTROL Query]** actividad se ejecutara correctamente si la dimensión de objetivo y la dimensión de filtrado configuradas en la actividad eran diferentes.
* Se ha corregido un error que hacía que la asignación automática de nombres a las transiciones de salida agregada a una **[!UICONTROL Fork]** actividad impidiera guardar el flujo de trabajo.

#### Edición de contenido {#content-editing-2}

* Se ha corregido un error que podía hacer que se mostrara indeseablemente un icono o una barra de búsqueda al editar contenido.

#### Páginas de destino {#landing-pages-3}

* Se ha corregido un error que impedía importar una página de aterrizaje mediante una importación de paquete.

#### Mensajes transaccionales {#transactional-messages-4}

* Ahora es posible especificar una dirección IP de confianza en los parámetros de seguridad del operador de agente push de centro de mensajes.
* Se ha corregido un error que podía impedir que se creara un nuevo tipo de evento.

## Versión 15.11: noviembre de 2015 {#release-15-11---november-2015}

### Nuevas capacidades {#new-capabilities-9}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> SMS Channel<br /> </td> 
   <td> Ahora puede enviar mensajes SMS con Adobe Campaign.<br /> Al igual que en el caso de los mensajes de correo electrónico, puede crear nuevos envíos de SMS a partir de sus campañas y de la lista de actividades de marketing. También puede crear mensajes SMS recurrentes y de envío único a partir de un flujo de trabajo.<br /> Estos envíos SMS se basan en plantillas que se pueden configurar en la lista de plantillas de envío. Hay disponible una plantilla predeterminada.<br /> Estos envíos SMS utilizan el protocolo SMPP 3.4, utilizado por la mayoría de los routers SMS.<br /><a href="../../channels/using/about-sms-messages.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Exploración de transiciones<br /> </td> 
   <td> Ahora puede explorar los datos y su estructura en la última transición de un flujo de trabajo. Esto le permite comprobar que los procesos aplicados por cada actividad se corresponden con sus necesidades.<br /> </td> 
  </tr> 
  <tr> 
   <td> Procesamiento previo y posterior de archivos en flujos de trabajo<br /> </td> 
   <td> Ahora puede realizar un procesamiento adicional en un archivo de datos al importarlo o exportarlo mediante las actividades <span class="uicontrol">Cargar archivo</span> y <span class="uicontrol">Extraer archivo</span> .<br /> De forma predeterminada, puede descomprimir y comprimir un archivo con formato GZIP en estas actividades.<br /> Para obtener más información, consulte la documentación sobre las actividades del archivo <a href="../../automating/using/load-file.md"></a> Cargar y <a href="../../automating/using/extract-file.md">Extraer</a> .<br /> </td> 
  </tr> 
  <tr> 
   <td> Informes de capacidad de entrega<br /> </td> 
   <td> Ya hay disponible un informe de procesamiento por correo electrónico. Este informe permite ver las diferentes representaciones de un mensaje según el servicio de soporte y de mensajes utilizado para leerlo.<br /> El resumen del informe también presenta el número de mensajes recibidos, mensajes no deseados, mensajes no recibidos y mensajes que esperan ser recibidos.<br /><a href="../../sending/using/email-rendering.md#email-rendering-report-description"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Administración de paquetes<br /> </td> 
   <td> Ahora es posible importar y exportar imágenes en paquetes.<br /> </td> 
  </tr> 
  <tr> 
   <td> Acciones rápidas<br /> </td> 
   <td> Algunas acciones aparecen al pasar el ratón sobre un elemento de una lista o un flujo de trabajo o después de seleccionarlo. Algunas de estas acciones ahora se muestran como iconos alrededor de los elementos correspondientes para facilitar el acceso. Estas acciones rápidas se pueden utilizar para duplicar un elemento, eliminarlo, mostrar los detalles, etc.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-9}

#### General {#general-9}

* Se ha corregido un error que podía impedir el acceso a los parámetros generales de una instancia desde una cuenta de administrador.
* **Los datos flotantes** ahora se tienen correctamente en cuenta en los recursos personalizados.
* Se corrigió un error de visualización en la lista de importaciones simplificadas ejecutadas que se producía cuando se había modificado el estado de la plantilla correspondiente.

#### Páginas de destino {#landing-pages-4}

* Se corrigieron ciertos elementos de las plantillas de página de aterrizaje que podían mostrarse incorrectamente en francés en instancias en inglés.

#### Audiences {#audiences}

* Se ha corregido un error que podía impedir que las audiencias importadas de Adobe Marketing Cloud aparecieran en la lista de audiencias.
* Se corrigió un error que podía forzar la distinción entre mayúsculas y minúsculas al definir una consulta.
* Se ha corregido un error que podía impedir que las audiencias se filtraran al definir una consulta.
* Se ha corregido un error que podía impedir que una acción se cancelara en una audiencia.

#### Workflows {#workflows-7}

* Se ha corregido un error que podía impedir que los campos que se actualizarían en una **[!UICONTROL Update data]** actividad se configuraran manualmente.
* Se ha corregido un error que podía hacer que la actividad se cargara infinitamente al abrirse si el flujo de trabajo no se había guardado después de colocar la actividad en el diagrama. **[!UICONTROL Query]**
* Se ha corregido un error que podía hacer que el servidor se detuviera al contar o previsualizar una audiencia seleccionada de un **[!UICONTROL Query]** flujo de trabajo.
* Se ha corregido un error no crítico que podía aparecer al abrir una actividad en un flujo de trabajo.
* Se corrigió un error que impedía que una **[!UICONTROL Scheduler]** actividad se configurara para ejecutar un flujo de trabajo varias veces al día.
* Se ha corregido un error que podía hacer que aparecieran campos en los que no se puede realizar una consulta en determinadas actividades de flujo de trabajo.
* Se ha corregido un error que podía impedir que el usuario localizara los KPI agregados de un **[!UICONTROL Query]** envío en la transición de salida.
* Se ha corregido un error que podía impedir que se creara una audiencia de archivo después de importar un archivo en un flujo de trabajo.
* Se ha corregido un error que podía impedir que los datos se actualizaran en perfiles si se utilizaba el campo **location/address3** del recurso.
* Se ha corregido un error que impedía que las colecciones heterogéneas de actividades se duplicaran en un flujo de trabajo.
* Se ha corregido un error que impedía que se mostrara el SQL, lo que permitía diagnosticar errores para una entrega recurrente en un flujo de trabajo.

#### Editor de contenido {#content-editor-1}

* Se corrigió un error que hacía imposible la búsqueda en el código fuente de una página de aterrizaje o correo electrónico.

#### Paquetes {#packages-1}

* Se corrigieron varios errores que podían impedir que ciertos tipos de elementos se exportaran en paquetes (especialmente páginas de aterrizaje, flujos de trabajo).
* Se corrigió un error que ocasionaba que se mostrara la etiqueta de importación del paquete anterior si se había modificado la etiqueta.
* Se ha corregido un error que podía hacer que se mostraran recursos incompatibles en la lista de recursos exportables.

## Versión 15.10: octubre de 2015 {#release-15-10---october-2015-}

### Nuevas capacidades {#new-capabilities-10}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Flujos de trabajo: Actividad de desduplicación<br /> </td> 
   <td> Ahora hay disponible una nueva actividad dedicada a la eliminación de duplicaciones en los flujos de trabajo. Esta actividad le permite filtrar cualquier duplicado de los objetivos según los criterios que haya seleccionado.<br /><a href="../../automating/using/deduplication.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: Diagrama mejorado<br /> </td> 
   <td> Desde el espacio de trabajo del flujo de trabajo, ahora puede utilizar varios métodos abreviados de teclado para seleccionar, abrir y eliminar actividades.<br /> La alineación de actividades también se ha mejorado y permite organizar mejor el flujo de trabajo visualmente.<br /><a href="../../automating/using/workflow-interface.md#workspace"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: Extraer actividad de archivo<br /> </td> 
   <td> La fecha y la hora de exportación ahora se agregan automáticamente a las etiquetas de los archivos exportados mediante una actividad de archivo <span class="uicontrol"></span> Extraer. De este modo, los archivos generados son únicos.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importación de datos simplificada<br /> </td> 
   <td> El nombre de la plantilla desde la que se ha realizado una importación simplificada ahora está visible de forma predeterminada en la lista de importación y en los detalles de cada importación.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos personalizados<br /> </td> 
   <td> Mejoras y posibilidades ampliadas para administrar y definir vínculos para recursos personalizados.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-10}

#### Correo electrónico {#email}

* Se ha corregido un error que impedía que un vínculo de cancelación de suscripción de servicio funcionara correctamente desde una página reflejada.
* Se ha corregido un error que podía impedir que una etiqueta de envío de correo electrónico se mostrara correctamente en la página de edición de correo electrónico.
* Se ha corregido un error que podía impedir que se seleccionara una cuenta externa **[!UICONTROL Routing]** en una plantilla de envío duplicada.

#### Audiences {#audiences-1}

* Se corrigió un error que se producía durante un recuento de audiencias si se utilizaba un vínculo 1-N en la consulta.
* Se ha corregido un error que podía impedir que se seleccionara un perfil en la audiencia de destino de una entrega de correo electrónico.

#### Workflows {#workflows-8}

* Se ha corregido un error que podía provocar problemas de visualización al configurar un envío de correo electrónico en un flujo de trabajo.
* Se ha corregido un error que podía impedir que la **[!UICONTROL Load file]** actividad funcionara correctamente. Entonces aparecerá un mensaje de error en blanco.
* Se ha corregido un error que podía impedir que la **[!UICONTROL Transfer file]** actividad funcionara correctamente. Los derechos de acceso no siempre se tuvieron en cuenta correctamente.
* Se ha corregido un error que podía impedir que se exportara un archivo si el flujo de trabajo contenía un **[!UICONTROL Recurring email]** .
* Se ha corregido un error que podía impedir que se creara un envío de correo electrónico en un flujo de trabajo o que se tuviera en cuenta el asunto y el contenido definido.
* Se ha corregido un error que podía impedir que se seleccionara una clave de reconciliación en una **[!UICONTROL Update data]** actividad al configurar el flujo de trabajo de una plantilla de importación simplificada.
* Se ha corregido un error que podía impedir que se guardara un flujo de trabajo después de eliminar una actividad.

#### Plataforma {#platform}

* Se ha corregido un error que podía impedir que se creara un nuevo elemento si un recurso personalizado contenía un vínculo al tipo de recurso de ese elemento.
* Se ha corregido un error que podía provocar un retraso de 15 minutos en la escritura de determinados registros.
* Se ha corregido un error que podía impedir que se mostrara la lista de actividades de marketing al ordenarla por las **[!UICONTROL Date]** columnas o **[!UICONTROL Indicators]** .

#### Páginas de destino {#landing-pages-5}

* Se corrigió un error que se producía al seleccionar un perfil de prueba para obtener una vista previa de una página de aterrizaje.

#### Mensajes transaccionales {#transactional-messages-5}

* Se ha corregido un error que podía hacer que la aplicación se bloqueara después de eliminar un evento en un perfil de prueba.

#### Informes {#reports}

* Se ha corregido un error que podía hacer que se enviaran datos incorrectos para los informes **[!UICONTROL deliveryThroughputReport]** y **[!UICONTROL deliveryTrackingReport]** .

#### Editor de contenido {#content-editor-2}

* Se ha corregido un error de administración de etiquetas HTML que se producía al procesar bloques de contenido dinámico.

## Versión 15.8: agosto de 2015 {#release-15-8---august-2015}

### Nuevas capacidades {#new-capabilities-11}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Importación de datos simplificada<br /> </td> 
   <td> Ahora puede importar datos de forma simplificada.<br /> Los usuarios simplemente seleccionan una plantilla predefinida por un administrador y cargan el archivo que contiene los datos que se van a importar. Un flujo de trabajo definido en la plantilla se ejecuta de forma transparente para el usuario, que puede acceder a los detalles del resultado de la importación, así como a un registro de cualquier error.<br /> Los datos de estos archivos pueden insertarse en la base de datos o servir para crear una audiencia directamente.<br /><a href="../../automating/using/about-data-import-and-export.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creación de programas y campañas<br /> </td> 
   <td> Ahora, las campañas y los programas se configuran de modo que el día en que se crean se utilicen automáticamente como fecha de inicio.<br /> La fecha de finalización se configura según la fecha de inicio, como:<br /> 
    <ul> 
     <li> D+186 para programas </li> 
     <li> D+61 para campañas </li> 
    </ul> Para obtener más información, consulte la <a href="../../start/using/programs-and-campaigns.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Correo electrónico<br /> </td> 
   <td> La lista de direcciones URL rastreadas ahora es de solo lectura.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensajes transaccionales<br /> </td> 
   <td> Ahora puede administrar mensajes transaccionales personalizados para eventos como cambios de contraseña o confirmaciones después de crear una cuenta.<br /><a href="../../channels/using/about-transactional-messaging.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos personalizados<br /> </td> 
   <td> Se agregaron varias funcionalidades, como: ampliar un perfil de prueba, administración de estado y eliminación de recursos.<br /><a href="../../developing/using/resource-statuses.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-11}

#### Mostrar {#display}

* Se corrigió un error que podría llevar a que dos campos se yuxtaponen en el editor de consultas en Safari.

#### Editor de contenido {#content-editor-3}

* Se ha corregido un error que impedía que los caracteres '&lt;', '&amp;' y '&gt;' se usaran en un asunto de correo electrónico.

#### Correo electrónico {#email-1}

* Se ha corregido un error que impedía al usuario agregar texto después de texto dinámico.

#### Listas {#lists}

* Se ha corregido un error que impedía que la columna **Mensaje** de los registros de ejecución del flujo de trabajo se exportara correctamente.

#### Perfiles y audiencias {#profiles-and-audiences}

* Se ha corregido un error que provocaba una doble confirmación de cuándo se duplicaba o eliminaba un elemento. **Dispositivos híbridos que solo** usan Internet Explorer 11.

#### Workflows {#workflows-9}

* Se ha corregido un error que podía impedir que se enviaran correos electrónicos desde un flujo de trabajo.
* Se ha corregido un error que podía impedir que se ejecutara un flujo de trabajo cuando no se especificaba el nombre del archivo de rechazo en una **[!UICONTROL Load file]** actividad.
* Se ha corregido un error que podía impedir que se ejecutara un flujo de trabajo cuando el contenido **[!UICONTROL Execution frequency]** de una **[!UICONTROL Schedule]** actividad se establecía en **[!UICONTROL Daily]** .

#### Plataforma {#platform-1}

* Se ha corregido un error que impedía que las miniaturas se generaran en un entorno de equilibrio de carga.

## Versión 15.7: julio de 2015 {#release-15-7---july-2015}

### Nuevas capacidades {#new-capabilities-12}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exportación de listas<br /> </td> 
   <td> Ahora puede exportar contenido de sus listas a un archivo en formato CSV. Esta función está disponible en todas las pantallas con un modo <strong>Lista</strong> (por ejemplo: lista de perfiles).<br /> Los datos exportados son los datos de las columnas que se muestran al exportar. Al editar la lista, puede seleccionar los datos que desea exportar.<br /> Para obtener más información sobre el uso de esta funcionalidad, consulte la documentación <a href="../../automating/using/exporting-lists.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración con Profiles &amp; Audiences de Adobe<br /> </td> 
   <td> Ahora puede compartir audiencias entre Adobe Campaign y otras soluciones de Adobe Marketing Cloud:<br /> 
    <ul> 
     <li> Exportar: al guardar una audiencia compuesta de perfiles en un flujo de trabajo, una nueva opción <span class="uicontrol">Compartir en Adobe Marketing Cloud</span> le permite agregar perfiles a una audiencia existente o crear una nueva audiencia. </li> 
     <li> Importar: al crear una audiencia de tipo <strong>Lista</strong> desde la pantalla de gestión de público, una nueva opción le permite identificarla como audiencia <span class="uicontrol">de</span> Adobe Marketing Cloud. A continuación, puede seleccionar una audiencia compartida existente para importarla a Adobe Campaign. </li> 
    </ul> Para obtener más información sobre cómo configurar y utilizar esta funcionalidad, consulte la documentación <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de contenido digital: contenido dinámico<br /> </td> 
   <td> Se ha mejorado la interfaz de contenido dinámico. Ahora, las flechas permiten desplazarse entre los distintos contenidos dinámicos, directamente en el cuerpo del correo electrónico.<br /> Para obtener más información sobre el uso de esta funcionalidad, consulte la documentación <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de contenido digital: texto dinámico<br /> </td> 
   <td> Desde el editor de contenido de un correo electrónico, ahora puede definir texto dinámico:<br /> 
    <ul> 
     <li> en un asunto de correo electrónico, </li> 
     <li> en modo HTML, </li> 
     <li> o en el modo Texto. </li> 
    </ul>  Para obtener más información sobre el uso de esta funcionalidad, consulte la documentación <a href="../../channels/using/defining-dynamic-text.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Programas y campañas - Informes<br /> </td> 
   <td> Se han mejorado la interfaz y los gráficos de los informes.<br /> Para obtener más información sobre el uso de esta funcionalidad, consulte la documentación <a href="../../reporting/using/defining-the-report-period.md"></a>detallada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-12}

#### Instalación {#installation}

* Los nombres de instancia de Adobe Campaign ahora están limitados a 32 caracteres.

#### Workflows {#workflows-10}

* Se ha corregido un error que podía impedir la segmentación de un recurso de "entrega" al editar una consulta en un flujo de trabajo.
* Se ha corregido un error que podía impedir que ciertos recursos vinculados se procesaran al editar una consulta en un flujo de trabajo.
* Se ha corregido un error que podía impedir que se modificara una actividad de entrega **** recurrente si el flujo de trabajo ya se había ejecutado.

#### Correos electrónicos {#emails}

* Se ha corregido un error que impedía comprobar los errores de sintaxis de JavaScript antes de enviar un correo electrónico cuando se agregaba contenido dinámico mediante el editor de expresiones.

#### Páginas de destino {#landing-pages-6}

* Se corrigió un error que impedía que una página de aterrizaje se editara desde una tablet.

#### Assets Core Service {#assets-core-service}

* Al seleccionar un recurso compartido desde un correo electrónico o una página de aterrizaje que se está editando, la lista de recursos disponibles ahora se filtra para Adobe Campaign.

## Versión 15.6: junio de 2015 {#release-15-6---june-2015}

### Nuevas capacidades {#new-capabilities-13}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Flujos de trabajo: Actividad de reconciliación<br /> </td> 
   <td> Una nueva actividad <strong>Reconciliación</strong> vincula datos no identificados (por ejemplo, después de importar un archivo) con recursos existentes dentro de un flujo de trabajo.<br /> Esta actividad se utiliza esencialmente con fines de administración de datos. Responde a dos casos de uso diferentes:<br /> 
    <ul> 
     <li> <strong>Adición de relaciones</strong>: una ficha <strong>Relaciones</strong> permite agregar vínculos entre los datos entrantes y varias otras dimensiones de la base de datos de Adobe Campaign. </li> 
     <li> <strong>Identificación</strong>de datos: una ficha <strong>Identificación</strong> permite simplemente asociar datos entrantes a columnas de una dimensión existente en la base de datos de Adobe Campaign. Cuando sale de la actividad, los datos se identifican como pertenecientes a la dimensión especificada. </li> 
    </ul> Consulte la documentación <a href="../../automating/using/reconciliation.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: Extraer actividad de archivo<br /> </td> 
   <td> Una nueva actividad de archivo <strong></strong> Extraer permite exportar datos de la base de datos de Adobe Campaign en forma de archivo externo desde un flujo de trabajo. <br /> Limitación: actualmente no es posible utilizar nombres dinámicos para los archivos de salida.<br /> Consulte la documentación <a href="../../automating/using/extract-file.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo:Actividad del programador<br /> </td> 
   <td> Se ha mejorado la utilidad que permite seleccionar el tiempo de ejecución de la actividad <strong>Programador</strong> en un flujo de trabajo.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: Transferir actividad de archivo<br /> </td> 
   <td> Ahora se admite SFTP.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recursos personalizados<br /> </td> 
   <td> El menú <span class="uicontrol">Desarrollo</span> ahora permite a los usuarios con derechos de administrador enriquecer las plantillas de datos que se proporcionan creando sus propios recursos personalizados, como tablas de productos o de compras. <br /> Los recursos listos para usar también se pueden ampliar para agregarles nuevos campos.<br /> Además, se puede configurar la navegación en las pantallas correspondientes a los recursos personalizados nuevos o extendidos.<br /> Consulte la documentación <a href="../../developing/using/data-model-concepts.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Test profiles<br /> </td> 
   <td> El nombre <strong></strong> medio y el <strong>título</strong> de los perfiles de prueba ahora se pueden seleccionar al configurar la lista de perfiles de prueba.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de contenido: Contenido dinámico<br /> </td> 
   <td> Puede definir diferentes contenidos que se mostrarán dinámicamente al usuario según las condiciones definidas mediante el editor de expresiones.<br /> Consulte la documentación <a href="../../designing/using/personalization.md#defining-dynamic-content-in-an-email">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Correo electrónico<br /> </td> 
   <td> Ahora hay disponible una columna de perfiles <strong>de</strong> prueba en los registros de envío de un correo electrónico.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-13}

#### Listas {#lists-1}

* Al eliminar un elemento de una lista ahora se actualiza automáticamente.
* Se ha corregido un error que impedía que se seleccionaran elementos de una lista que solo contenía una columna.
* Se corrigió un error que ocasionaba que los cambios aplicados a la visualización de una lista se perdieran después de actualizar la página.
* El nombre medio y el título de los perfiles de prueba ahora se pueden mostrar en la lista de perfiles de prueba.
* Se corrigió un error que se producía al seleccionar una casilla de verificación en una lista con Mozilla Firefox.

#### Audiences {#audiences-2}

* Se ha corregido un error que impedía que el **[!UICONTROL Add]** botón se utilizara en la interfaz de audiencia.

#### Correos electrónicos {#emails-1}

* Se ha corregido un error de JavaScript que impedía que el botón de vista previa se utilizara dos veces seguidas al editar un correo electrónico.
* Se ha corregido un error que impedía que los botones **[!UICONTROL Edit properties]** y **[!UICONTROL Show proofs]** se usaran en tablets de Microsoft Surface Pro3 con Internet Explorer 11.
* Se ha corregido un error que podía impedir que se mostraran los registros de envío de un correo electrónico.

#### Páginas de destino {#landing-pages-7}

* Se ha corregido un error que impedía que el bloque de contenido del logotipo **de** marca se utilizara al editar contenido en una página de aterrizaje.
* Se corrigió un error que impedía que las páginas de aterrizaje se mostraran en la lista de actividades de marketing si se especificaban fechas de validez para la página de aterrizaje.

#### Workflows {#workflows-11}

* Se ha corregido un error que impedía que la limitación de un segmento en modo de grupo funcionara correctamente al configurar una actividad de **segmentación** .
* Se ha corregido un error que impedía que se seleccionara una transición después de haber configurado una actividad de **segmentación** .
* Se ha corregido un error que impedía que se eliminara una transición después de haber configurado una actividad **de segmentación** .
* Se ha corregido un error que impedía que se contaran y previsualizaran las poblaciones dentro de una actividad **de segmentación** .
* Se ha corregido un error que impedía que un correo electrónico recurrente se eliminara de forma efectiva.
* Se corrigió un error que ocasionaba que los datos de una actividad de archivo **de** transferencia eliminada aparecieran en una nueva actividad de archivo **de** transferencia.
* Se corrigió un error que impedía que una regla de exclusión se tuviera en cuenta correctamente en una actividad de **exclusión** .
* Se ha corregido un error que se producía al eliminar una actividad de envío de correo electrónico en un flujo de trabajo. Las entregas correspondientes ahora también se eliminan de la lista de actividades de marketing.

#### Navegación {#navigation}

* Ahora puede utilizar la tecla de tabulación para desplazarse correctamente entre los campos de la misma página.

## Versión 15.4: abril de 2015 {#release-15-4---april-2015}

### Nuevas capacidades {#new-capabilities-14}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Exportaciones de paquetes/Importaciones de paquetes<br /> </td> 
   <td> El menú <strong>Implementación</strong> ahora permite a los usuarios con derechos de administrador intercambiar recursos entre distintas instancias de Adobe Campaign mediante la exportación e importación de paquetes.<br /> Consulte la documentación <a href="../../automating/using/managing-packages.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Informes<br /> </td> 
   <td> Ahora se puede acceder a todos los informes (excepto al <strong>informe de clics</strong> interactivos) desde un programa. Estos informes son:<br /> 
    <ul> 
     <li> Rendimiento de la entrega de programas </li> 
     <li> Indicadores de seguimiento de programas </li> 
     <li> Desglose de programa por dominio </li> 
     <li> Programas no entregables y devoluciones </li> 
     <li> Direcciones URL del programa y flujos de clics </li> 
    </ul> Estos informes pueden filtrarse durante un período determinado (por ejemplo, tres meses, seis meses, etc.). Los informes de campaña también se pueden filtrar.<br /> Consulte la documentación <a href="../../reporting/using/about-dynamic-reports.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: Actividad <strong>de envío</strong> por correo electrónico<br /> </td> 
   <td> Se ha mejorado la actividad de envío <strong>de</strong> correo electrónico en los flujos de trabajo. Ahora puede encontrar correos electrónicos, correos electrónicos recurrentes e información detallada sobre ejecuciones recurrentes por correo electrónico en la lista de actividades de marketing de la aplicación.<br /> Consulte la documentación <a href="../../automating/using/email-delivery.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: Actividad <strong>de segmentación</strong><br /> </td> 
   <td> La actividad de <strong>segmentación</strong> ya está disponible en los flujos de trabajo. Esta actividad le permite crear uno o varios segmentos y vincular un código de segmento a ellos desde una población calculada por actividades ubicadas en el mismo flujo de trabajo. Desde esta actividad, los segmentos se pueden procesar en una sola transición o en diferentes transiciones. Ahora hay opciones para filtrar la población y limitar el tamaño de cada segmento para optimizar la personalización. Por ejemplo, puede seleccionar al azar perfiles que se correspondan con criterios específicos.<br /> Consulte la documentación <a href="../../automating/using/segmentation.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integraciones: Servicio principal de <strong>Assets</strong><br /> </td> 
   <td> Ahora puede utilizar recursos compartidos mediante <strong>Assets Core Service</strong> en el contenido de su página de aterrizaje y correo electrónico. Puede administrar los recursos compartidos directamente desde Adobe Marketing Cloud.<br /> Consulte la documentación <a href="../../integrating/using/working-with-campaign-and-assets-core-service.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integraciones: <strong>Adobe Target</strong><br /> </td> 
   <td> Ahora puede insertar imágenes calculadas dinámicamente por <strong>Adobe Target</strong> en los correos electrónicos de Adobe Campaign. Esto le permite ofrecer varias versiones del mismo correo electrónico personalizando el contenido según los criterios definidos en los segmentos de Adobe Target.<br /> Consulte la documentación <a href="../../integrating/using/about-campaign-target-integration.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Editor de contenido digital: Selector <strong>de bloques</strong><br /> </td> 
   <td> Cuando se selecciona un bloque en el editor de contenido HTML, se muestra una ruta de exploración en la parte inferior de la zona de edición. Esto le permite desplazarse fácilmente y seleccionar diferentes elementos.<br /> Consulte la documentación <a href="../../channels/using/designing-a-landing-page.md#managing-landing-page-structure-and-style">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Versión 15.3: marzo de 2015 {#release-15-3---march-2015}

### Nuevas capacidades {#new-capabilities-15}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> Informes<br /> </td> 
   <td> Ahora se puede acceder a los informes directamente desde un programa o una campaña. El informe <strong>de resumen</strong> de la ejecución se ha agregado a nivel de programa.<br /> Consulte la documentación <a href="../../reporting/using/delivery-summary.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Actualización de datos<br /> </td> 
   <td> En los flujos de trabajo, la actividad de datos <strong></strong> Actualizar disponible tiene una nueva opción, que le permite vincular automáticamente los campos de datos entrantes con los campos de un esquema de aplicación. Esto ayuda a facilitar el proceso de selección para actualizar los campos.<br /> Consulte la documentación <a href="../../automating/using/update-data.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Envío de correo electrónico<br /> </td> 
   <td> En los flujos de trabajo, ahora se puede acceder a las opciones avanzadas de la actividad de envío <strong>por correo</strong> electrónico a través de un botón específico en la barra de acciones. Este botón solo está disponible si se selecciona una actividad de envío <strong>de</strong> correo electrónico. La principal ventaja es que le permite agregar una transición saliente a la actividad y editar el nombre de la actividad tal como se muestra en el flujo de trabajo.<br /> Consulte la documentación <a href="../../automating/using/email-delivery.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-14}

#### General {#general-10}

* Se ha corregido un error que impedía que se mostrara el destinatario al crear una entrega.
* Se ha corregido un error que impedía que se usara una audiencia basada en la condición 'Destinatarios que han abierto'.
* Se ha corregido un error que impedía que se eliminara un perfil vacío.
* Se corrigió un error que se producía al obtener la vista previa de un envío.
* Se ha corregido un error que impedía que se duplicara una actividad de marketing.
* Se corrigió un error que se producía al eliminar una campaña.

