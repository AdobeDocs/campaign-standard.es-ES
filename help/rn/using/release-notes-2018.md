---
title: Notas de la versión 2018
seo-title: Notas de la versión 2018
description: Notas de la versión 2018
seo-description: Esta página enumera todas las versiones de 2018 de Adobe Campaign Standard.
page-status-flag: nunca activado
uuid: 99f92a54-4b3d-48b9-b08d-e98b24e75f62
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: referencia
topic-tags: campaign-standard-releases
discoiquuid: e54f8305-7e32-4193-8e5a-b5d87b03038c
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 94c7649448aff859daaf2bbe9a4d17a5187ac71f

---


# Release Notes 2018{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard para 2018?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

Vea las últimas actualizaciones [de](../../rn/using/documentation-updates.md) documentación de Adobe Campaign Standard. Si busca una versión más reciente, consulte esta [página](../../rn/using/release-notes.md).

## Versión 18.9: septiembre de 2018 {#release-18-9---september-2018}

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
   <td> Mensajería en la aplicación (beta)<br /> </td> 
   <td> La mensajería en la aplicación le permite interactuar con mayor eficacia con los usuarios de aplicaciones móviles al proporcionar una interacción contextual y permitirle comunicarse con los usuarios que hayan optado por no recibir notificaciones push. Utilice la mensajería en la aplicación junto con las notificaciones push para crear una experiencia muy personalizada y relevante. Esto lleva a una mejor conversión y retención de los usuarios de la aplicación.<br /><a href="../../channels/using/about-in-app-messaging.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Adobe Launch para aplicaciones móviles (beta)<br /> </td> 
   <td> La integración de Adobe Launch con Adobe Campaign ahora simplifica y automatiza el proceso de activación de la propiedad de la aplicación móvil en Campaign mediante el SDK de Mobile V5.<br /><a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mejoras {#improvements}

* Adobe Campaign Standard ahora admite la versión 4 de la API de Amazon S3.

### Otros cambios {#other-changes}

* En los registros generales hay ahora una distinción entre el número máximo de conexiones y el número máximo de mensajes por hora. Cuando se alcanzan los límites, es posible saber por qué el rendimiento está limitado. Anteriormente, el mismo mensaje (“cuota alcanzada”) se aplica a ambos casos.
* Al configurar una aplicación móvil en Campaign, el usuario puede saber si el certificado de iOS y la clave del servidor de Android se han cargado correctamente y su fecha de caducidad.

   Para obtener más información sobre esto, consulte la documentación detallada sobre cómo configurar una aplicación móvil mediante [SDK V4](https://helpx.adobe.com/campaign/kb/configuring-app-sdkv4.html) y [SDK V5](https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html).

* Para dirigirse a usuarios de una aplicación móvil específica, seleccione una aplicación móvil al definir las propiedades de la campaña. Esta función es tanto para los canales de mensajería push como en la aplicación.

   Para obtener más información, consulte la [documentación detallada](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Al seleccionar un bloque de contenido mediante la interfaz de Creative Designer, ahora se cargan y muestran todos los bloques de contenido de la lista. (CAMP-27311)

   For more on this, refer to the [detailed documentation](../../designing/using/personalization.md#adding-a-content-block).

### Parches {#patches}

* Se ha corregido un problema que mostraba una discrepancia en el recuento de registros entre el tablero de correo electrónico y el informe de resumen de correo electrónico para los mensajes de correo electrónico transaccionales. (CAMP-28237)
* Se ha corregido un problema en los flujos de trabajo que podía mostrar un mensaje de error al importar un archivo mediante una actividad de transferencia de archivos. (CAMP-27435)
* Se corrigió un problema con las páginas de aterrizaje que contenían más de 25 servicios, que hacía que los servicios no se seleccionaran al azar en el formulario. (CAMP-26572)
* Se ha corregido un problema en los flujos de trabajo que impedía configurar cuentas externas con una URL SFTP al usar la actividad de transferencia de archivos. (CAMP-26475)
* Se ha corregido un problema que impedía actualizar el informe de resumen de servicios. (CAMP-26301)
* Se ha corregido un problema en los flujos de trabajo al usar una actividad de enriquecimiento que impedía que un campo personalizado mostrara la fecha correcta. (CAMP-26242)
* Se ha corregido un problema que impedía que las fechas de suscripción de servicio se actualizaran al importarlas mediante una importación de archivos.
* Se ha corregido un error con la actividad de carga de archivos que impedía que los flujos de trabajo importaran archivos (CAMP-27068).
* Se ha corregido un problema que mostraba el número incorrecto de suscripciones en los informes de resumen de servicio (CAMP-25587).
* Se ha corregido un problema de discrepancia de datos entre los informes de Adobe Analytics y Adobe Campaign. (CAMP-25393)
* Se ha corregido un problema que podía impedir que un usuario de acceso limitado iniciara sesión. (CAMP-27381)
* Se ha corregido un problema que podía impedir que se mostrara la lista de contenido de Adobe Experience Manager al editar un correo electrónico con Creative Designer. (CAMP-27181)
* Se ha corregido un problema que podía impedir que se abriera el Diseñador creativo y provocar un error. (CAMP-27304)
* Se ha corregido un problema que impedía que la función de arrastrar y soltar funcionara correctamente en Creative Designer al utilizar Internet Explorer 11.
* Se ha corregido un problema que provocaba que las imágenes cargadas desde una cámara y grabadas en modo vertical se mostraran en una posición rotada no deseada.
* Se ha corregido un problema que mostraba información de selección poco clara al utilizar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que impedía duplicar correctamente un elemento al utilizar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que hacía que los mensajes SMS se siguieran enviando a destinatarios bloqueados aunque se hubieran cancelado las suscripciones mediante una respuesta automática. (CAMP-27128)
* Se ha corregido un problema que impedía mostrar los errores que provocaban que fallara el flujo de trabajo de limpieza de **bases de datos** . (CAMP-26876)
* Se ha corregido un problema que podía impedir la eliminación de campos personalizados en una definición de notificación push. (CAMP-25588)

## Versión 18.7: julio de 2018 {#release-18-7---july-2018}

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
   <td> Indicador de alta prioridad para notificaciones push de Android<br /> </td> 
   <td> Indicador de alta prioridad para Android: permite enviar una notificación push con alta prioridad para las aplicaciones de Android, lo que provoca que el dispositivo de suspensión se active y ejecute un procesamiento limitado. Tenga en cuenta que la prioridad predeterminada es Normal, lo que puede retrasar la entrega del mensaje para guardar la batería. <br /><a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro de tipología para suscriptores de aplicaciones móviles<br /> </td> 
   <td> Suscripciones compatibles en el filtro de tipología: al especificar los criterios de filtrado para una regla de tipología, las suscripciones a la aplicación se pueden seleccionar como dimensiones de filtrado y destino, lo que permite filtrar atributos para usuarios con o sin un perfil. <br /><a href="../../administration/using/about-typology-rules.md#typology-rules"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importación automática de contenido desde una dirección URL durante la preparación de mensajes<br /> </td> 
   <td> Ahora es posible importar contenido de correo electrónico desde una dirección URL durante la fase de preparación. Para envíos recurrentes por correo electrónico, el contenido HTML más reciente se recupera cada vez que se prepara el mensaje, lo que garantiza que el contenido esté siempre actualizado en el momento en que se envía el correo electrónico. Esta función también le permite crear una entrega programada con contenido de una dirección URL aunque el contenido aún no esté listo.<br /><a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensaje de notificación de lanzamiento de campaña<br /> </td> 
   <td> Ahora aparece un mensaje emergente cuando un usuario inicia sesión después de actualizar la instancia a una nueva versión. El mensaje indica el número de versión e incluye un vínculo a las notas de la versión. Puede elegir ocultar el mensaje hasta la próxima versión. <br /> </td> 
  </tr> 
  <tr> 
   <td> Administración de usuarios<br /> </td> 
   <td> La capacidad de unidad geográfica ahora no está disponible para las nuevas instancias de Campaign Standard, ni para las instancias existentes sin crear unidades geográficas, a partir de la versión 18.7.<br /><a href="https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html"> Para obtener más información, consulte esta página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mejoras {#improvements-1}

* La integración de Adobe Campaign y Adobe Target ahora le permite aprovechar la función [Permisos](https://marketing.adobe.com/resources/help/en_US/target/target/properties-overview.html) de Target. Al incluir una imagen dinámica de Adobe Target en un mensaje de correo electrónico, ahora puede especificar una propiedad de Target (código at_property).
* Las solicitudes de acceso o eliminación de privacidad de GDPR tienen ahora en cuenta los recursos personalizados que tienen un vínculo de descarga al recurso de perfiles. Para los vínculos simples de cardinalidad 1 y los vínculos de recopilación de cardinalidad N, debe seleccionar "Eliminar/duplicar el registro de destino implica eliminar/duplicar los registros a los que hace referencia el vínculo" en el recurso personalizado. Para los vínculos simples de cardinalidad 0 o 1, seleccione "Eliminar o duplicar el registro implica eliminar o duplicar el registro de destino al que hace referencia el vínculo".

### Otros cambios {#other-changes-1}

* El tiempo de espera de uso compartido de informes se ha aumentado de uno a cuatro minutos para evitar cualquier error de tiempo de espera.
* Al editar el contenido de un correo electrónico, se abre el nuevo Diseñador creativo de forma predeterminada. Si lo desea, puede volver al editor de contenido predeterminado en cualquier momento después de guardar los cambios. For more on this, refer to the [detailed documentation](../../designing/using/overview.md).
* En Creative Designer, ahora se puede añadir un nuevo componente de contenido a un correo electrónico: el carrusel. For more on this, refer to the [detailed documentation](../../designing/using/designing-from-scratch.md#about-content-components).
* En un informe de clic en caliente de mensajes transaccionales, al hacer clic en el botón **Cambiar perfil** , ahora solo se muestran los perfiles de prueba vinculados al evento que definió para el mensaje transaccional.

### Parches {#patches-1}

* Se ha corregido un problema con el filtro de consulta byEmail que no devolvía ningún resultado. (CAMP-23420)
* Se ha corregido un problema que permitía a un usuario estándar acceder a determinadas funciones o pantallas restringidas a los administradores (extremos/rest/head/*, pantallas de mensajería transaccionales, perfiles y pantallas de importación de audiencias).
* Se ha corregido un problema que impedía que las solicitudes de eliminación de privacidad GDPR procesaran recursos personalizados si su nombre empezaba por un número.
* Se ha corregido un error que impedía que la actividad Guardar audiencia compartiera suscriptores de aplicaciones en Adobe Experience Cloud.
* Se ha corregido un problema con la actividad de transferencia de archivos que podía producirse cuando el nombre del archivo contenía espacios en blanco. (CAMP-25936)
* Se ha corregido un problema que se podía producir al usar el botón de reconexión después de que caduque una sesión. (CAMP-25560)
* Se ha corregido un problema que podía provocar exclusiones al enviar entregas con optimización de huso horario asociada a reglas de fatiga. (CAMP-25425)
* Se ha corregido un problema que, al usar la función GDPR de API, impedía eliminar datos con un vínculo de tipo 0-1.
* Se ha corregido un problema que podía generar un mensaje de error al cancelar la edición de una regla de tipología de fatiga.
* Se ha corregido un problema que se podía producir al previsualizar un contenido de entrega después de editarlo.
* Se ha corregido un problema que se podía producir al procesar archivos comprimidos CSV al utilizar la opción Descompresión.
* Se ha corregido un problema en el Diseñador creativo que provocaba que la fuente de color y el formato no fueran deseados al cambiar texto con estilo incorporado a un vínculo o al editarlo. (CAMP-26001)
* Se ha corregido un problema que impedía que el informe de clics interactivos mostrara los porcentajes de cada condición en las entregas que contenían contenido dinámico. Anteriormente, solo se mostraban los clics en la variante predeterminada.

## Versión 18.6: junio de 2018 {#release-18-6---june-2018}

### Mejoras {#improvements-2}

* La **[!UICONTROL History]** API se ha agregado a Adobe.IO. Permite acceder a información relacionada con el historial de marketing de un perfil: número de puntos de contacto, envíos enviados, URL de la página de reflejo, etc. For more on this, refer to the [dedicated use case](https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#how-to-retrieve-the-mirror-page-for-a-delivery-sent-to-a-profile) .
* El flujo de trabajo **[!UICONTROL Database cleanup]** técnico se ha optimizado para garantizar un mejor rendimiento para el backup de bases de datos.
* Creative Designer para correo electrónico ahora también está disponible en francés y alemán.

### Otros cambios {#other-changes-2}

* Se ha agregado un **[!UICONTROL Compute stats]** botón en la ventana **[!UICONTROL Deployment]** de envíos enviados. Le permite recuperar los KPI más recientes, por ejemplo si los resultados del envío tardan demasiado en actualizarse o no se han tenido en cuenta. Para obtener más información, consulte [esta sección](../../sending/using/confirming-the-send.md).
* En el flujo de trabajo técnico de **actualización para la entrega** lista para usar, los administradores funcionales ahora pueden definir el número de errores consecutivos que se deben ignorar en la actividad de JavaScript de reglas **de** actualización. De forma predeterminada, el valor del campo se establece en 0, lo que significa que se omitirán todos los errores.
* Se ha optimizado el SQL generado al administrar las condiciones de restricción de acceso a la unidad.
* La **[!UICONTROL Update]** actividad ahora le permite agregar, actualizar o eliminar datos relacionados con suscripciones (tabla nms:appSubscriptionRcp).
* El flujo de trabajo **[!UICONTROL Update delivery execution]** técnico se ha dividido en dos flujos de trabajo para optimizar el rendimiento: - **[!UICONTROL Update delivery execution]**: actualiza el seguimiento del envío. Se inicia cada 10 minutos de forma predeterminada. **[!UICONTROL Update delivery indicators]**:: actualiza los KPI del envío, se inicia cada hora de forma predeterminada. For more on technical workflows, refer to this [section](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Cuando una entrega envía mensajes, el estado de la sección **[!UICONTROL Deployment]** ahora puede tener dos valores: **[!UICONTROL Sending]**: los mensajes se están enviando. **[!UICONTROL Sending (retry)]**:: se está procesando una pasada de reintento.
* Los usuarios con la **[!UICONTROL Delivery preparation]** función ahora pueden enviar pruebas. (CAMP-24313)
* La opción **Habilitar TLS sobre SMPP** se ha agregado al enrutamiento **SMS a través de la cuenta externa de SMPP** . Consulte esta [sección](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing)para obtener más información.

### Parches {#patches-2}

* Se ha corregido un problema que podía impedir que se enviaran correos electrónicos al incluir una imagen dinámica de Adobe Target (CAMP-24848).
* Se ha corregido un problema con los flujos de trabajo **[!UICONTROL Privacy Access/Delete Request]** técnicos, que no se completaban si se producía algún error en las solicitudes.
* Se ha corregido un problema que impedía que el servicio de Privacy Core recibiera actualizaciones del estado de la solicitud desde Campaign.
* Se ha corregido un problema que impedía que el flujo de trabajo técnico **[!UICONTROL Import shared audience]** funcionara correctamente (CAMP -25465).
* Se ha corregido un problema que impedía que las solicitudes de privacidad de campaña se marcaran como finalizadas en Core Privacy Service.
* Se ha corregido un problema que podía impedir que ciertos usuarios iniciaran sesión en Campaign Standard mediante autenticación IMS cuando el ID de Adobe era demasiado largo. (CAMP-24095)
* Se ha corregido un problema en Creative Designer que podía producirse al eliminar módulos de contenido. (CAMP-25242)
* Se ha corregido un problema que se producía al usar reglas de fatiga de notificaciones push para suscriptores sin perfil en la base de datos. (CAMP-25344)
* Se ha corregido un problema que podía mostrar un mensaje de error al acceder a los registros de exclusión de entregas. (CAMP-24724)
* Se ha corregido un problema que impedía que las pruebas se prepararan en instancias con registros de envío extendidos.
* Se han corregido dos problemas que podían producirse al publicar recursos personalizados con la **[!UICONTROL Sending log]** extensión activada.
* Se ha corregido un problema que podía ocurrir con la duración de la entrega que no se tenía en cuenta en los envíos recurrentes.
* Se ha corregido un problema que se podía producir al ordenar datos en el **[!UICONTROL Client data]** menú, para recursos personalizados con más de 100.000 registros. (CAMP-24308)
* Se ha corregido un problema con las dimensiones de perfil personalizadas que no se tenían en cuenta al usar la función de búsqueda en los informes dinámicos.
* Se ha corregido un problema con la visualización de datos internacionales para los niveles de cuenta en los informes dinámicos.
* Ahora es posible crear un servicio sin un mensaje de confirmación de suscripción o cancelación de suscripción.

## Versión 18.5: mayo de 2018 {#release-18-5---may-2018}

### What's new? {#what-s-new--2}

<table> 
 <thead> 
  <tr> 
   <th> Funcionalidad<br /> </th> 
   <th> Descripción<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> RGPD: Integración de servicios principales<br /> </td> 
   <td> Privacy Core Service Integration le permite automatizar sus solicitudes GDPR en un contexto de varias soluciones a través de una sola llamada de API JSON. <br /> Las solicitudes de RGPD insertadas desde el servicio principal de privacidad a todas las soluciones de Experience Cloud ahora son gestionadas automáticamente por Campaign. <br /><a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mejoras de inserción: comentarios de entrega detallados<br /> </td> 
   <td> Adobe Campaign ahora ofrece la posibilidad de recibir comentarios detallados (enviar registros y registros de exclusión) sobre los mensajes push de los proveedores (APNS/GCM) a través de MCPNS.<br /><a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extensión de registros de envío<br /> </td> 
   <td> La extensión de los registros de entrega permite ampliar los registros de envío con datos de perfil y código de segmento procedentes de flujos de trabajo. Esta información se puede utilizar en informes dinámicos y permite mantener una instantánea de cierta información en el momento de envío de un envío.<br /> Hay dos casos de uso más:<br /> 
    <ul> 
     <li> Exporte los diarios ampliados con datos "congelados": Como especialista en mercadotecnia, me gustaría exportar todos los perfiles donde el código de segmento sea igual a "A" (proveniente del motor de flujo de trabajo). </li> 
     <li> Segmentación de datos "congelados": Como especialista en mercadotecnia, me gustaría <strong>redirigir</strong> todos los perfiles que hayan ganado 1000 puntos de lealtad desde el último envío o donde el código de segmento sea igual a "A". </li> 
    </ul> Para obtener más información, consulte la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Informes dinámicos con datos de perfil personalizados<br /> </td> 
   <td> Esta función le permite crear y administrar informes basados en datos de perfil personalizados creados durante la extensión de recursos de perfil. Puede desglosar los informes por atributos de perfil, como programa de lealtad, canal preferido, etc.<br /><a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Mejoras {#improvements-3}

* Se ha mejorado el uso general de memoria y CPU de la aplicación

### Otros cambios {#other-changes-3}

* La actividad de flujo de trabajo Leer audiencia ahora puede leer audiencias de Experience Cloud. Anteriormente, esta actividad solo podía leer audiencias de consulta y lista. Consulte la documentación [detallada](../../automating/using/read-audience.md). (CAMP-23623)
* El identificador de la fuente de datos compartida predeterminada está ahora en modo de solo lectura y ya no se puede cambiar. Cambiar este identificador podría provocar algunos problemas al compartir audiencias con Experience Cloud.
* La importación de audiencias desde el Gestor de colaboradores ahora funciona con archivos divididos. Anteriormente, el último archivo del segmento se importó mediante el flujo de trabajo técnico Importar audiencia compartida.
* Las cuentas externas de AWS S3 ahora admiten regiones y el mecanismo de autenticación de la versión 4. Consulte la documentación [detallada](../../administration/using/external-accounts.md).
* La ventana de selección de recursos ahora debe cargarse más rápido y permitir seleccionar un recurso y salir de la ventana sin ningún problema.
* Las propiedades y la estructura de los flujos de trabajo técnicos ahora pueden ser modificadas por usuarios con derechos de administración y pertenecientes a las unidades organizativas y geográficas "Todos".
* Se han realizado mejoras en la interfaz de actividad de segmentación al crear nuevos segmentos: La ficha Limitación ahora aparece directamente después de agregar una limitación. Los nombres de los nuevos segmentos ahora se incrementan ("Segmento 1", "Segmento 2", etc.).
* Se agrega un campo "nextProcessingDate" al recurso Flujo de trabajo. Este campo solo está visible a través de las llamadas de la API de REST, y le permite visualizar flujos de trabajo en las próximas fechas de procesamiento.
* El campo "sourceId" ahora está expuesto en el recurso de registros de seguimiento (nms:trackingLog).
* Los valores "Total de aperturas" y "Total de clics" ahora se pueden exportar en un archivo plano a través de un flujo de trabajo. (CAMP-24186)
* "Inglés - Danmark" ya está disponible en la lista de idiomas preferidos en los perfiles. (CAMP-23728)
* Al utilizar una actividad de segmentación con un vínculo Datos adicionales (targetData), ahora un mensaje le informa de que los datos no están disponibles fuera del flujo de trabajo. Este mensaje se muestra al hacer clic en el botón Recuento o Vista previa de la actividad Segmentación. (CAMP-23651)
* Se han realizado mejoras para optimizar el espacio en disco utilizado por los flujos de trabajo: (CAMP-21979): Los archivos procesados por la actividad "Cargar archivo" ahora se eliminan de forma predeterminada. Una opción permite mantenerlos para necesidades específicas. Cuando se elimina un flujo de trabajo, su carpeta dedicada se suprime automáticamente del directorio del servidor.

### Parches {#patches-3}

* Se corrigió un problema en el cual algunos eventos de informes sin procesar no tenían eventos de seguimiento asociados porque el campo eventDate no se rellenaba correctamente.
* Se ha corregido un problema que impedía que se mostraran campos personalizados en la ventana de vista previa de una entrega de notificación push.
* Se ha corregido un problema que impedía que el texto ajustara el cuerpo del mensaje de una notificación push en la ventana de vista previa.
* Se ha corregido un problema que se producía al enviar una entrega de recuperación desde un flujo de trabajo cuando el destino principal estaba vacío.
* Se ha corregido un problema que impedía acceder a una asignación de destino si estaba vinculada a un esquema inexistente.
* Se ha corregido un problema que podía producirse al importar un archivo zip mediante una actividad de carga de archivos. (CAMP-24309)
* Se ha corregido un problema que provocaba un error PostgreSQL al enviar una entrega recurrente. (CAMP-23613)
* Se ha corregido un problema que mostraba un mensaje de error al enviar una solicitud de API REST con un atributo JSON vacío. (CAMP-23506)
* Se corrigió un problema en los perfiles que definía en mayúsculas los caracteres que siguen al carácter "ß". (CAMP-23136)
* Se ha corregido un problema que se producía al enviar entregas utilizadas con la condición de elegibilidad de personalización o de bloque de contenido dinámico al usar atributos de un esquema de perfil vinculado. (CAMP-22751)
* Se ha corregido un problema que impedía eliminar servicios. (CAMP-22050)
* Se ha corregido un problema que impedía cambiar los valores País o Estado en un perfil de prueba. (CAMP-20426)
* Se ha corregido un problema que podía impedir que se cargara Creative Designer. (CAMP-24573)
* Se ha corregido un problema que eliminaba los caracteres añadidos tras los campos de personalización en el asunto del correo electrónico. (CAMP-24113)

## Versión 18.4: abril de 2018 {#release-18-4---april-2018}

### Parches {#patches-4}

#### Plataforma {#platform}

* Se ha corregido un error que podía impedir el procesamiento correcto de solicitudes de acceso o eliminación de RGPD. Este comportamiento se ha observado en algunos casos excepcionales en los que los datos extraídos contenían uno de los siguientes caracteres: &amp; &lt; &gt; " '.

#### Correos electrónicos, mensajes SMS y correo directo {#emails--sms-messages-and-direct-mail}

* Se ha corregido un problema que podía hacer que los KPI se sobrescribieran con valores incorrectos si la sincronización de diarios extendidos tardaba más de una hora.

#### Workflows {#workflows}

* Se ha mejorado la administración de memoria y el rendimiento optimizado en los flujos de trabajo.

#### Informes {#reporting}

* El flujo de trabajo de uso compartido de KPI ahora recupera los valores de entrega de los últimos 2 meses en lugar de los últimos 6 meses. Se ha corregido un problema con la cuenta externa de uso compartido de KPI que mostraba fechas truncadas.
* Se ha corregido un problema que podía hacer que algunos mensajes no se tuvieran en cuenta en **Enviados**, **Entregados** y **** Devoluciones.
* Se corrigió un error que se producía cuando el intervalo de tiempo seleccionado en el informe **Resumen de** envío era demasiado largo.

#### Recursos personalizados {#custom-resources}

* Se corrigió un error que ocasionaba que fallara la preparación de recursos personalizados.

## Versión 18.3: marzo de 2018 {#release-18-3---march-2018}

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
   <td> Reglamento General de Protección de Datos.<br /> </td> 
   <td> El Reglamento General de Protección de Datos (RGPD) es la nueva normativa sobre privacidad de la Unión Europea que unifica y moderniza los requisitos de protección de datos y entrará en vigencia el 25 de mayo de 2018. El RGPD se aplica a los clientes de Adobe Campaign que albergan datos de sujetos de datos que residan en la UE.<br /> Además de las funcionalidades de privacidad disponibles en Adobe Campaign (incluida la administración de consentimiento, configuración de retención de datos y funciones de usuario), estamos tomando esta oportunidad en nuestro rol como procesador de datos para incluir funcionalidades adicionales, para ayudar a facilitar su preparación como controlador de datos para ciertas solicitudes de RGPD:<br /> 
    <ul> 
     <li> Derecho de acceso: permite que el sujeto de datos reciba una copia de sus datos personales recopilados por los controladores de datos, incluso los datos almacenados en Adobe Campaign. </li> 
     <li> Derecho a borrado: autoriza al sujeto de datos a que sus datos personales recopilados por los controladores de datos se borren, lo que incluye datos almacenados en Adobe Campaign. </li> 
    </ul> Para obtener más información, consulte la <a href="https://docs.campaign.adobe.com/doc/standard/getting_started/en/ACS_GDPR.html">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer para correo electrónico (Beta)<br /> </td> 
   <td> El nuevo diseño creativo de Adobe Campaign ofrece una experiencia de creación totalmente integrada en Campaign, lo que permite crear de forma rápida y sencilla correos electrónicos cautivadores personalizados e individuales sin necesidad de escribir una sola línea de código. Gracias a su potente interfaz de arrastrar y soltar, Creative Designer ayuda a escalar la creación de correo electrónico tanto si los usuarios comienzan en una pizarra en blanco como si aprovechan los fragmentos de contenido o las plantillas existentes. <br /> Las funciones clave incluyen:<br /> 
    <ul> 
     <li> Diseñe y cree mensajes de correo electrónico totalmente personalizados y adaptables mediante una interfaz de arrastrar y soltar, aumentada por integraciones nativas de Creative Cloud </li> 
     <li> Crear y guardar una plantilla de contenido de correo electrónico y aprovechar las plantillas guardadas para ayudar a escalar la creación de correo electrónico </li> 
     <li> Cree y guarde fragmentos de contenido (como encabezado, pie de página, artículo, etc.) para optimizar la creación de contenido y garantizar la coherencia de la marca </li> 
     <li> Cambie sin problemas entre la creación en la interfaz de arrastrar y soltar y la edición directa de HTML de un correo electrónico haciendo clic en un botón </li> 
    </ul> Creative Designer para correo electrónico solo está disponible en inglés.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/overview.md"></a> detallada y vea este <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregas push multilingües<br /> </td> 
   <td> La misma interfaz multilingüe simple, que ya existe en los canales de correo electrónico y SMS, se ha agregado al canal Push para ayudarle a captar clientes sin importar su idioma preferido.<br /> Esta capacidad ofrece una solución escalable y automática para los clientes que administran campañas push en varias regiones y desean dirigirse a los usuarios en su idioma preferido. Le permite cargar todas las variantes lingüísticas a través de una hoja de cálculo con plantilla en una única entrega push, con un solo clic. A continuación, Adobe Campaign realiza una segmentación automática basada en las preferencias de idioma de los usuarios, lo que ayuda a reducir las redundancias simplificando los flujos de trabajo y los informes.<br /><a href="../../channels/using/creating-a-multilingual-push-notification.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso de recursos personalizados en la mensajería transaccional<br /> </td> 
   <td> Además de los campos predeterminados, la mensajería transaccional ahora permite utilizar recursos personalizados para enriquecer el contenido de los mensajes.<br /> Por ejemplo:<br /> 
    <ul> 
     <li> Aproveche los campos personalizados como criterios de reconciliación para que un mensaje transaccional coincida con un perfil </li> 
     <li> Aproveche perfiles completos, servicios y datos vinculados para personalizar aún más los mensajes transaccionales </li> 
    </ul> Para obtener más información, consulte la <a href="../../administration/using/configuring-transactional-messaging.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-5}

#### Plataforma {#platform-1}

* Se ha corregido un problema que impedía exportar más de 5000 registros de una lista.
* Se corrigió un problema al exportar datos a archivos con nombres con campos de personalización.

#### Correos electrónicos, mensajes SMS y correo directo {#emails--sms-messages-and-direct-mail-1}

* Se ha corregido un problema que provocaba que el SMS de varias partes se truncara porque el tamaño de las partes se calculaba en caracteres en lugar de en bytes.
* Se ha agregado una opción que permite actualizar los KPI **[!UICONTROL Delivered]** o **[!UICONTROL Bounces + Errors]** KPI en tiempo real después de enviar el envío. Se vuelven a calcular directamente desde el SR (Informe de estado) recibido del proveedor.
* Se ha corregido un problema con la utilidad de calendario en el programador de envíos.
* Se corrigió un problema de visualización al abrir un destino por segunda vez en un envío.
* Se ha corregido un problema que provocaba un mensaje de error que solicitaba una fecha de inicio al crear una plantilla de correo electrónico con una fecha de envío retrasada.
* Se ha corregido un problema que podía provocar problemas de representación de imágenes al editar el contenido de una publicación.
* Se ha corregido un problema con las pruebas al duplicar una campaña.
* Se ha corregido un problema que provocaba un mensaje de error al acceder a una plantilla de campaña a través de la barra de navegación, después de agregar una entrega al flujo de trabajo.
* Se ha corregido un problema que podía impedir que el ganador de un correo electrónico de prueba A/B se seleccionara automáticamente, lo que provocaba que no se enviara el correo electrónico. Este comportamiento podría producirse si el envío estaba en **[!UICONTROL retryInProgress]** estado.
* Se ha corregido un problema que podía provocar que apareciera un mensaje de error al volver a abrir los parámetros de un correo electrónico de prueba A/B.

#### Audiencias y consultas {#audiences-e-queries}

* Se ha corregido un problema que impedía acceder a los datos y configurar consultas para destinatarios replicados de Adobe Campaign Classic a Standard.
* Se ha corregido un problema que se producía al usar un campo de tipo de filtro en el editor de consultas, después de usar los botones **Recuento** o **Vista previa** .

#### Workflows {#workflows-1}

* El flujo de trabajo de **facturación** se ha optimizado para mejorar el retraso en la preparación de la entrega.
* Se ha corregido un problema que impedía que los datos de población se mostraran en una transición de salida al usar una actividad de entrega recurrente.
* Se ha corregido un problema que impedía que los registros rechazados se mostraran en una transición después de una actividad de **actualización de datos** .
* Se ha corregido un problema que podía provocar un error en el flujo de trabajo técnico de **liberabilidadActualizar** .

#### Integraciones {#integrations}

* Se ha corregido un problema que impedía que los caracteres internacionales se enviaran correctamente a Adobe Analytics.
* Los recursos ahora deben cargarse más rápido al intentar insertar una imagen de la biblioteca de recursos de Experience Cloud en un mensaje.
* Se ha corregido un problema que podía impedir que la ventana de selección de recursos se cerrara en algunos casos.
* Desde un detalle de fuente de datos, ahora puede acceder directamente a su flujo de trabajo relacionado para comprobar el estado del flujo de trabajo.
* Ahora puede actualizar el esquema Triggers directamente al definir o editar un evento desencadenador. Con este cambio, ya no tendrá que cancelar la publicación del activador y crear otro.

#### Mensajes transaccionales {#transactional-messages}

* Se corrigió un error con la plantilla de mensaje transaccional cuando se amplió el recurso de entrega.
* Ahora es posible eliminar mensajes transaccionales.

## Versión 18.2: febrero de 2018 {#release-18-2---february-2018}

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
   <td> Suscripción: suscripción o cancelación de la suscripción de una lista de perfiles a varios servicios<br /> </td> 
   <td> La actividad de flujo de trabajo de servicios <strong>de</strong> suscripción ahora le permite suscribirse o cancelar la suscripción de una lista de perfiles a varios servicios. En el flujo de trabajo, importe un archivo que contenga los perfiles y, para cada perfil, el tipo de operación y el servicio. La actividad Servicios <strong>de</strong> suscripción podrá utilizar esta información y gestionar dinámicamente todas las suscripciones y cancelaciones de perfiles a la vez.<br /><a href="../../automating/using/subscription-services.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Actividad de enriquecimiento: enriquecer datos en base a transiciones anteriores<br /> </td> 
   <td> La nueva actividad <span class="uicontrol">de flujo de trabajo Enriquecimiento</span> le permite aprovechar las transiciones de entrada y completar la transición de salida con datos adicionales. Si segmenta perfiles, la actividad de enriquecimiento le permite enriquecer la información de perfiles con datos adicionales que no se almacenan en la base de datos (por ejemplo, procedentes de un archivo importado).<br /><a href="../../automating/using/enrichment.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-6}

#### Plataforma {#platform-2}

* La barra superior de la interfaz de Adobe Campaign se ha actualizado con el nuevo menú de Experience Cloud.
* Se ha corregido un problema que impedía que el vínculo a se mostrara **[!UICONTROL Offers]** en la lista desplegable de soluciones.

#### Correos electrónicos, mensajes SMS y correo directo {#emails--sms-messages-and-direct-mail-2}

* Se ha mejorado la fase de preparación de la ejecución para mejorar el rendimiento.
* Se corrigieron varios problemas que podrían hacer que los registros de seguimiento se dañaran en algunas situaciones específicas.
* Se ha corregido un problema de actualización de la fecha de contacto que se producía cuando se cambiaba la fecha de contacto entre la preparación de la entrega y la confirmación. Ahora, cuando cambie la fecha de contacto después de la preparación, deberá volver a preparar la entrega antes de poder confirmar el envío. Consulte la documentación [detallada](../../sending/using/preparing-the-send.md).

#### Notificaciones push {#push-notifications}

* Se ha corregido un error que impedía que algunos campos de personalización funcionaran en las notificaciones push de iOS.
* Se corrigió un error que mostraba las tasas de clic y de apertura como 0% en el tablero de notificaciones push.

#### Informes {#reports}

* Se corrigió un error que mostraba la lista de informes como vacía en algunos exploradores.
* Se ha corregido un error que se producía en el flujo de trabajo **[!UICONTROL Report sharing]** técnico justo antes de que se alcanzara el límite de caducidad.

#### Workflows {#workflows-2}

* Se ha corregido un problema que impedía que las actividades fueran accesibles después de arrastrarlas y soltarlas.
* Se ha corregido un problema que podía hacer que el orden de las transiciones de salida de una **[!UICONTROL Segmentation]** actividad cambiara en algunas situaciones.
* Se corrigió un error que se producía al leer una audiencia que contenía un campo de tipo de enumeración y que anteriormente se había guardado desde un flujo de trabajo
* Se ha corregido un problema que provocaba que la **[!UICONTROL Request confirmation before sending messages]** opción permaneciera marcada incluso después de desactivarla al definir las propiedades de programación de una entrega creada en un flujo de trabajo.
* La eliminación automática de filas duplicadas (cláusula DISTINCT) ahora se puede desactivar en **[!UICONTROL Query]** las actividades, mediante una nueva opción ubicada en la **[!UICONTROL Additional data]** ficha. Se recomienda desactivar esta opción cuando se definan muchos (más de 100) elementos adicionales por motivos de rendimiento.

#### Integraciones {#integrations-1}

* Se han realizado algunas mejoras en la pantalla de configuración **[!UICONTROL Data sources]** .

### Problemas conocidos {#known-issues}

Se recomienda no utilizar Internet Explorer versión 11 debido a posibles problemas de visualización.

Pueden producirse algunos problemas al utilizar vínculos de ayuda contextuales desde la interfaz de Campaign. Se corregirán en 18.3.

## Versión 18.1: enero de 2018 {#release-18-1---january-2018}

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
   <td> Informes para la administración de fatiga<br /> </td> 
   <td> Reporting for Fatigue Management es un informe dedicado y configurable que muestra el impacto que las reglas de fatiga tienen en las entregas a través de los canales de correo electrónico, push, SMS y correo directo dentro de un intervalo de fechas especificado antes de enviarlas. Con la perspectiva adicional de poder ver rápidamente todas las campañas en conflicto en una sola vista, los especialistas en mercadotecnia pueden planificar las campañas de mercadotecnia de acuerdo con la definición de las reglas de fatiga de manera más eficaz y dar prioridad a las comunicaciones.<br /><a href="../../administration/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso compartido de informes<br /> </td> 
   <td> El uso compartido de informes le permite compartir sus informes con usuarios de Adobe Campaign como datos adjuntos de correo electrónico, incluso de forma periódica y automatizada. Los usuarios que reciben informes recurrentes pueden cancelar la suscripción a estas comunicaciones mediante un vínculo específico en cada correo electrónico.<br /><a href="../../reporting/using/reporting-interface.md#share-tab"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Nuevas capacidades push<br /> </td> 
   <td> Vista previa de mensajes push: previsualice las notificaciones push en dispositivos iOS y Android desde el editor de contenido de notificaciones push para ver exactamente lo que verán los destinatarios antes de probar o ejecutar la entrega.<br /><a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification"> Para obtener más información, consulte la documentación detallada</a>.<br /> Contenido disponible: cuando las aplicaciones no se abren durante períodos de tiempo más largos, sus datos pueden quedar obsoletos. Esto hace que los datos deban actualizarse o reemplazarse en el momento en que un usuario finalmente abre la aplicación, lo que puede provocar retrasos en el uso de la aplicación. Con la compatibilidad añadida de Contenido disponible, los usuarios de Adobe Campaign pueden activar su aplicación para actualizar sus datos en segundo plano al enviar una notificación push, lo que permite una mayor coherencia y control sobre la experiencia en la aplicación de un usuario.<br /> Contenido mutable: con la compatibilidad añadida de Contenido mutable, los usuarios de Adobe Campaign ahora pueden aprovechar las extensiones de sus aplicaciones móviles para modificar aún más el contenido o la presentación de las notificaciones push entrantes enviadas desde Adobe Campaign. Por ejemplo, los usuarios pueden aprovechar el contenido mutable para: <br /> 
    <ul> 
     <li> descifrar datos que se entregaron en formato cifrado </li> 
     <li> descargar imágenes u otros archivos multimedia y agregarlos como datos adjuntos a una notificación </li> 
     <li> cambiar el texto del cuerpo o del título de una notificación </li> 
     <li> agregar un identificador de subproceso a una notificación </li> 
    </ul> Para obtener más información sobre el contenido disponible y el contenido mutable, consulte la documentación <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios"></a>detallada.<br /><strong> </strong>Advertencia: estas actualizaciones de las notificaciones push requieren que los clientes actualicen sus aplicaciones móviles. Refer to <a href="https://helpx.adobe.com/campaign/kb/understanding-campaign-standard-push-notifications-payload-struc.html">this technote</a> for more information.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregas optimizadas para zonas horarias<br /> </td> 
   <td> Programe las notificaciones recurrentes por correo electrónico, SMS y push para que se entreguen en un día y hora específicos en el huso horario de cada destinatario, lo que garantiza que los mensajes se entreguen en el momento adecuado sin necesidad de configurar varias entregas. <br /><a href="../../automating/using/scheduler.md"> Para obtener más información, consulte la documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Activación de actividad de señal de API<br /> </td> 
   <td> Ahora es posible activar una actividad de señal para los flujos de trabajo directamente desde la API de Adobe Campaign Standard.<br /><a class="anchorLink" href="https://final-docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html#triggering-a-signal-activity" target="_blank"> Para obtener más información, consulte la documentación detallada</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-7}

#### Plataforma {#platform-3}

* La búsqueda de perfiles se ha optimizado para mejorar el rendimiento.
* El identificador interno de los grupos de seguridad predeterminados está ahora en modo de solo lectura para los usuarios estándar.

#### Correos electrónicos, mensajes SMS y correo directo {#emails--sms-messages-and-direct-mail-3}

* Se ha corregido un problema de visualización que se producía al insertar emojis en el contenido de los envíos.
* Se ha corregido un problema que permitía al usuario acceder a los registros de envío cuando la entrega aún estaba en edición.
* La **[!UICONTROL Scheduler]** actividad ahora le permite enviar los envíos en función del huso horario del destinatario.
* SMS: La opción **[!UICONTROL Store incoming MO]** de la base de datos se ha agregado a cuentas externas. Cuando se selecciona, todos los SMS entrantes se almacenan **en la tabla de SMS** .
* SMS: Los servicios ahora se adjuntan a un evento en lugar de a una plantilla de transacción.
* SMS: El tiempo de espera de conexión SMTP predeterminado se ha reducido a 30 segundos.

#### Notificaciones push {#push-notifications-1}

* Se ha corregido un error que impedía que se detuvieran las entregas de notificaciones push.
* Se ha agregado una opción en las opciones avanzadas de notificación push para activar la aplicación con una notificación push.
* Se ha agregado un botón de pausa para el vídeo de vista previa de notificaciones Push.
* La vista previa de la notificación push ya está disponible para distintos dispositivos como iPhone, Android y tablets.

   todos los canales

#### Informes {#reports-1}

* Se corrigió un error que mostraba tasas superiores al 100%.
* Se ha corregido un problema que impedía a los usuarios descargar informes en CSV.
* Se agregó un nuevo **[!UICONTROL Report]** elemento en la página principal.

#### Workflows {#workflows-3}

* Se ha corregido un problema que provocaba un mensaje de error al usar datos adicionales en una consulta y agregar alias que contenían espacios. Los caracteres no alfanuméricos ahora se reemplazan por "_".
* Se corrigió un problema en el cual los KPI de cálculo del flujo de trabajo técnico se podían detener de forma predeterminada en algunos casos.

#### Perfiles y audiencias {#profiles-and-audiences}

* Se corrigió un error que se producía al agregar varios filtros en una consulta de audiencia.
* Se ha corregido un problema de visualización que se producía al cambiar la imagen de un perfil.
* Se agregó una información de objeto que muestra el número de resultado exacto después de contar la población de una consulta.
* Se ha corregido un problema que podía impedir que un usuario seleccionara una audiencia o cerrara la ventana del selector de audiencias.
* Se ha actualizado la lista de funciones disponibles en el editor de expresiones. Se han eliminado **las funciones FormatCurrency** y **ConvertCurrency** .

