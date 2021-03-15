---
solution: Campaign Standard
product: campaign
title: Notas de la versión 2018
description: Esta página enumera todas las versiones de 2018 de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Información general
role: Profesional empresarial
level: Principiante
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '5406'
ht-degree: 10%

---


# Notas de la versión 2018{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard para 2018?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

Vea las [actualizaciones de documentación](../../rn/using/documentation-updates.md) más recientes para Adobe Campaign Standard. Si está buscando una versión más reciente, consulte esta [página](../../rn/using/release-notes.md).

## Versión 18.9: septiembre de 2018 {#release-18-9---september-2018}

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
   <td> Mensajería en la aplicación (beta)<br /> </td> 
   <td> La mensajería en la aplicación permite atraer a los usuarios de aplicaciones móviles de forma más eficaz ya que proporciona interacción contextual y permite llegar a usuarios que pueden haber salido de notificaciones push. Utilice la mensajería en la aplicación junto con las notificaciones push para crear una experiencia altamente personalizada y relevante. Esto lleva a una mejor conversión y retención de los usuarios de la aplicación.<br /> Para obtener más información, consulte la <a href="../../channels/using/about-in-app-messaging.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Adobe Launch para aplicaciones móviles (beta)<br /> </td> 
   <td> La integración de Adobe Launch con Adobe Campaign ahora simplifica y automatiza el proceso de activación de la propiedad de la aplicación móvil en Campaign mediante el SDK V5 para móviles.<br /> Para obtener más información, consulte la <a href="https://helpx.adobe.com/campaign/kb/configuring-app-sdk.html">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Adobe Campaign Standard ahora es compatible con la versión 4 de la API de Amazon S3.

**Otros cambios**

* En los registros generales hay ahora una distinción entre el número máximo de conexiones y el número máximo de mensajes por hora. Cuando se alcanzan los límites, es posible saber por qué el rendimiento está limitado. Anteriormente, el mismo mensaje (“cuota alcanzada”) se aplica a ambos casos.
* Al configurar una aplicación móvil en Campaign, el usuario ahora puede saber si el certificado de iOS y la clave de servidor de Android se han cargado correctamente y su fecha de caducidad.

   Para obtener más información, consulte la documentación detallada sobre cómo configurar una aplicación móvil mediante [SDK V4](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html) y [SDK V5](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html).

* Para dirigirse a usuarios de una aplicación móvil específica, seleccione una aplicación móvil al definir las propiedades de la campaña. Esta función es para canales de mensajería push y en la aplicación.

   Para obtener más información, consulte la [documentación detallada](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Al seleccionar un bloque de contenido mediante la interfaz de Creative Designer, ahora se cargan y muestran todos los bloques de contenido de la lista. (CAMP-27311)

   Para obtener más información, consulte la [documentación detallada](../../designing/using/personalization.md#adding-a-content-block).

**Parches**

* Se ha corregido un problema que mostraba una discrepancia en el recuento de registros entre el panel de correo electrónico y el informe de resumen de correo electrónico para los correos electrónicos transaccionales. (CAMP-28237
* Se ha corregido un problema con flujos de trabajo que podía mostrar un mensaje de error al importar un archivo a través de una actividad de transferencia de archivos . (CAMP-27435)
* Se ha corregido un problema con las páginas de aterrizaje que contenían más de 25 servicios, que provocaba que se anulara la selección aleatoria de los servicios en el formulario. (CAMP-26572)
* Se ha corregido un problema en flujos de trabajo que impedía configurar cuentas externas con una URL SFTP al utilizar la actividad de transferencia de archivos. (CAMP-26475)
* Se ha corregido un problema que impedía actualizar el informe de resumen de servicios. (CAMP-26301)
* Se ha corregido un problema en los flujos de trabajo al utilizar una actividad de Enriquecimiento que impedía que un campo personalizado mostrara la fecha correcta. (CAMP-26242)
* Se ha corregido un problema que impedía que las fechas de suscripción del servicio se actualizaran al importarse mediante una importación de archivos.
* Se ha corregido un error con la actividad de carga de archivo que impedía que los flujos de trabajo importaran archivos (CAMP-27068).
* Se ha corregido un problema que mostraba el número incorrecto de suscripciones en los informes de resumen del servicio (CAMP-25587).
* Se ha corregido un problema de discrepancia de datos entre los informes de Adobe Analytics y Adobe Campaign. (CAMP-25393)
* Se ha corregido un problema que podía impedir que un usuario con acceso limitado iniciara sesión. (CAMP-27381)
* Se ha corregido un problema que podía impedir que se mostrara la lista de contenido de Adobe Experience Manager al editar un correo electrónico con Creative Designer. (CAMP-27181)
* Se ha corregido un problema que podía impedir que se abriera el Creative Designer, lo que provocaba un error. (CAMP-27304)
* Se ha corregido un problema que impedía que la función de arrastrar y soltar funcionara correctamente en Creative Designer al utilizar Internet Explorer 11.
* Se ha corregido un problema que provocaba que las imágenes cargadas desde una cámara y grabadas en modo vertical se mostraran en una posición girada no deseada.
* Se ha corregido un problema que mostraba información de selección poco clara al usar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que impedía duplicar correctamente un elemento al usar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que seguía enviando mensajes SMS a los destinatarios en la  de lista de bloqueados, aunque se habían dado de baja de la suscripción mediante una respuesta automática. (CAMP-27128)
* Se ha corregido un problema que impedía mostrar los errores que provocaban que fallara el flujo de trabajo **Database Cleanup**. (CAMP-26876)
* Se ha corregido un problema que podía impedir la eliminación de campos personalizados en una definición de notificación push. (CAMP-25588)

## Versión 18.7: julio de 2018 {#release-18-7---july-2018}

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
   <td> Indicador de alta prioridad para notificaciones push de Android<br /> </td> 
   <td> Indicador de alta prioridad para Android : Habilite la entrega de una notificación push con alta prioridad para las aplicaciones Android, lo que hace que el dispositivo de suspensión se active y ejecute un procesamiento limitado. Tenga en cuenta que la prioridad predeterminada es Normal, lo que puede retrasar el envío del mensaje para guardar la batería. <br /> Para obtener más información, consulte la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro de tipología para suscriptores de aplicaciones móviles<br /> </td> 
   <td> Compatibilidad con suscripciones en el filtro de tipología : al especificar los criterios de filtrado para una regla de tipología, las suscripciones a la aplicación se pueden seleccionar como dimensiones de filtrado y segmentación, lo que proporciona la capacidad de filtrar atributos para usuarios con o sin un perfil. <br /> Para obtener más información, consulte la <a href="../../sending/using/about-typology-rules.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importación automática de contenido desde una dirección URL durante la preparación del mensaje<br /> </td> 
   <td> Ahora es posible importar contenido de correo electrónico desde una URL durante la fase de preparación. En el caso de las entregas de correo electrónico recurrentes, el contenido HTML más reciente se recupera cada vez que se prepara el mensaje, lo que garantiza que el contenido esté siempre actualizado en el momento en que se envía el correo electrónico. Esta función también permite crear un envío programado con contenido de una dirección URL aunque el contenido no esté listo.<br /> Para obtener más información, consulte la <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensaje de notificación de la versión de la campaña<br /> </td> 
   <td> Ahora aparece un mensaje emergente cuando un usuario inicia sesión después de actualizar la instancia a una nueva versión. El mensaje indica el número de versión e incluye un vínculo a las notas de la versión. Puede elegir ocultar el mensaje hasta la próxima versión. <br /> </td> 
  </tr> 
  <tr> 
   <td> Administración de usuarios<br /> </td> 
   <td> La capacidad de la unidad geográfica ya no está disponible para las nuevas instancias de Campaign Standard, ni para las instancias existentes sin crear unidades geográficas, a partir de la versión 18.7.<br /><a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes"> Para obtener más información, consulte esta página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* La integración de Adobe Campaign y Adobe Target ahora le permite aprovechar la función [Permissions](https://docs.adobe.com/content/help/es-ES/target/using/administer/manage-users/enterprise/properties-overview.html) de Target. Al incluir una imagen dinámica de Adobe Target en un mensaje de correo electrónico, ahora puede especificar una propiedad de destino (código at_property).
* Las solicitudes de acceso o eliminación de la privacidad del RGPD ahora tienen en cuenta los recursos personalizados que tienen un vínculo de descarga al recurso de perfiles. Para los vínculos simples de cardinalidad 1 y los vínculos de recopilación de cardinalidad N, debe seleccionar &quot;Eliminar/duplicar el registro de destino implica eliminar/duplicar los registros a los que hace referencia el vínculo&quot; en el recurso personalizado. Para vínculos simples de cardinalidad 0 o 1, seleccione &quot;Eliminar/Duplicar el registro implica eliminar/duplicar el registro de destino al que hace referencia el vínculo&quot;.

**Otros cambios**

* El tiempo de espera para el uso compartido de informes ha aumentado de uno a cuatro minutos para evitar cualquier error de tiempo de espera.
* Al editar el contenido de un correo electrónico, el nuevo Creative Designer se abre de forma predeterminada. Si lo desea, puede volver al editor de contenido predeterminado en cualquier momento después de guardar los cambios. Para obtener más información, consulte la [documentación detallada](../../designing/using/designing-content-in-adobe-campaign.md).
* En Creative Designer, ahora se puede añadir un nuevo componente de contenido en un correo electrónico: el carrusel. Para obtener más información, consulte la [documentación detallada](../../designing/using/designing-from-scratch.md#about-content-components).
* En un informe de clic activo de un mensaje transaccional, al hacer clic en el botón **Change profile**, ahora solo se enumeran los perfiles de prueba vinculados al evento que ha definido para el mensaje transaccional.

**Parches**

* Se ha corregido un problema con el filtro de consulta byEmail que no devolvía ningún resultado. (CAMP-23420)
* Se ha corregido un problema que permitía a un usuario estándar acceder a determinadas funciones o pantallas restringidas a administradores (/rest/head/* extremos, pantallas de mensajería transaccional, perfiles y pantallas de importación de audiencias).
* Se ha corregido un problema que impedía que las solicitudes de eliminación de privacidad de RGPD procesaran recursos personalizados si su nombre empezaba por un número.
* Se ha corregido un error que impedía que la actividad Guardar audiencia compartiera suscriptores de la aplicación en Adobe Experience Cloud.
* Se ha corregido un problema con la actividad de transferencia de archivos que se podía producir cuando el nombre del archivo contenía espacios en blanco. (CAMP-25936)
* Se ha corregido un problema que se podía producir al utilizar el botón de reconexión después de que caduque una sesión. (CAMP-25560)
* Se ha corregido un problema que podría provocar exclusiones al enviar entregas con optimización de zona horaria asociada a reglas de fatiga. (CAMP-25425)
* Se ha corregido un problema que se producía al utilizar la función del RGPD de la API y que podía impedir la eliminación de datos con un vínculo de tipo 0-1.
* Se ha corregido un problema que podría provocar un mensaje de error al cancelar la edición de una regla de tipología de fatiga.
* Se ha corregido un problema que se podía producir al obtener una vista previa del contenido de una entrega después de editarlo.
* Se ha corregido un problema que se podía producir al procesar archivos zip CSV mientras se usaba la opción de descompresión .
* Se ha corregido un problema en el Diseñador creativo que daba como resultado fuentes de color y formatos no deseados al cambiar texto con estilo incorporado a un vínculo o al editarlo. (CAMP-26001)
* Se ha corregido un problema que impedía que el informe de clics activos mostrara los porcentajes de cada condición en los envíos que contenían contenido dinámico. Anteriormente, solo se mostraban los clics en la variante predeterminada.

## Versión 18.6: junio de 2018 {#release-18-6---june-2018}

**Mejoras**

* La API **[!UICONTROL History]** se ha agregado a Adobe.IO. Permite acceder a información relacionada con el historial de marketing de un perfil: número de puntos de contacto, envíos enviados, URL de página espejo, etc. Para obtener más información, consulte el [caso de uso dedicado](../../api/using/interacting-with-marketing-history.md) .
* El flujo de trabajo técnico **[!UICONTROL Database cleanup]** se ha optimizado para garantizar un mejor rendimiento para la copia de seguridad de la base de datos.
* Creative Designer para correo electrónico ahora también está disponible en francés y alemán.

**Otros cambios**

* Se ha añadido un botón **[!UICONTROL Compute stats]** en la ventana **[!UICONTROL Deployment]** de los envíos enviados. Le permite recuperar los KPI más recientes, por ejemplo, si los resultados de la entrega tardan demasiado en actualizarse o no se han tenido en cuenta. Para obtener más información, consulte [esta sección](../../sending/using/confirming-the-send.md).
* En el flujo de trabajo técnico predeterminado **Update for deliverability** , los administradores funcionales ahora pueden definir el número de errores consecutivos que se deben ignorar en la actividad de javascript **Update rules** . De forma predeterminada, el valor del campo se establece en 0, lo que significa que se ignorarán todos los errores.
* Se ha optimizado el SQL generado al administrar las condiciones de restricción de acceso a la unidad.
* La actividad **[!UICONTROL Update]** ahora le permite añadir, actualizar o eliminar datos relacionados con suscripciones (tabla nms:appSubscriptionRcp ).
* El flujo de trabajo técnico **[!UICONTROL Update delivery execution]** se ha dividido en dos flujos de trabajo para optimizar el rendimiento: - **[!UICONTROL Update delivery execution]**: actualiza el seguimiento de la entrega. Se inicia cada 10 minutos de forma predeterminada. **[!UICONTROL Update delivery indicators]**: actualiza los KPI del envío, se inicia cada hora de forma predeterminada. Para obtener más información sobre los flujos de trabajo técnicos, consulte esta [sección](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Cuando un envío envía mensajes, el estado de la sección **[!UICONTROL Deployment]** ahora puede tener dos valores: **[!UICONTROL Sending]**: los mensajes se están enviando. **[!UICONTROL Sending (retry)]**: se está enviando un paso de reintento.
* Los usuarios con la función **[!UICONTROL Delivery preparation]** ahora pueden enviar pruebas. (CAMP-24313)
* La opción **Enable TLS over SMPP** se ha agregado al enrutamiento **SMS a través de la cuenta externa SMPP**. Consulte esta [sección](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) para obtener más información.

**Parches**

* Se ha corregido un problema que podía impedir que se enviaran correos electrónicos al incluir una imagen dinámica de Adobe Target (CAMP-24848).
* Se ha corregido un problema con los flujos de trabajo técnicos **[!UICONTROL Privacy Access/Delete Request]**, que no se completaban si fallaba alguna de las solicitudes.
* Se ha corregido un problema que impedía que el servicio principal de privacidad recibiera actualizaciones de estado de solicitud de Campaign.
* Se ha corregido un problema que impedía que el flujo de trabajo técnico **[!UICONTROL Import shared audience]** funcionara correctamente (CAMP -25465).
* Se ha corregido un problema que impedía que las solicitudes de privacidad de Campaign se marcaran como completadas en el Privacy Service principal.
* Se ha corregido un problema que podía impedir que ciertos usuarios iniciaran sesión en el Campaign Standard mediante la autenticación IMS cuando el Adobe ID era demasiado largo. (CAMP-24095)
* Se ha corregido un problema en Creative Designer que se podía producir al quitar módulos de contenido. (CAMP-25242)
* Se ha corregido un problema que se producía al usar reglas de fatiga de notificaciones push para suscriptores sin perfil en la base de datos. (CAMP-25344)
* Se ha corregido un problema que podía mostrar un mensaje de error al acceder a los registros de exclusión de entregas. (CAMP-24724)
* Se ha corregido un problema que impedía que las pruebas se prepararan en instancias con registros de envío extendidos.
* Se han corregido dos problemas que podían producirse al publicar recursos personalizados con la extensión **[!UICONTROL Sending log]** activada.
* Se ha corregido un problema que se podía producir cuando la duración de la entrega no se tenía en cuenta en los envíos recurrentes.
* Se ha corregido un problema que se podía producir al ordenar datos en el menú **[!UICONTROL Client data]** para recursos personalizados con más de 100.000 registros. (CAMP-24308)
* Se ha corregido un problema con las dimensiones de perfil personalizadas que no se tenían en cuenta al usar la función de búsqueda en los informes dinámicos.
* Se ha corregido un problema con la visualización de datos internacionales para niveles de cuenta en informes dinámicos.
* Ahora es posible crear un servicio sin un mensaje de confirmación de suscripción o baja.

## Versión 18.5: mayo de 2018 {#release-18-5---may-2018}

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
   <td> RGPD: Integración de servicios principales<br /> </td> 
   <td> La integración del servicio principal de privacidad le permite automatizar sus solicitudes de RGPD en un contexto de varias soluciones a través de una sola llamada de API JSON. <br /> Las solicitudes de RGPD insertadas desde el Servicio principal de privacidad a todas las soluciones de Experience Cloud ahora son gestionadas automáticamente por Campaign. <br /> Para obtener más información, consulte la <a href="https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=es">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mejoras de push: comentarios de entrega detallados<br /> </td> 
   <td> Adobe Campaign ahora proporciona la capacidad de recibir comentarios detallados (envío de registros y registros de exclusión) sobre los mensajes push de los proveedores (APNS/GCM) a través de MCPNS.<br /> Para obtener más información, consulte la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extensión de registros de envío<br /> </td> 
   <td> La extensión de registros de envío permite ampliar los registros de envío con datos de perfil y código de segmento procedentes de flujos de trabajo. Esta información se puede utilizar en informes dinámicos y permite mantener una instantánea de cierta información en el momento de la entrega.<br /> Hay dos casos de uso más:<br /> 
    <ul> 
     <li> Exportar registros generales ampliados con datos "congelados": Como especialista en marketing, me gustaría exportar todos los perfiles donde el código de segmento es igual a "A" (proveniente del motor de flujo de trabajo). </li> 
     <li> Segmentación en datos "congelados": Como especialista en marketing, me gustaría <strong>redirigir</strong> todos los perfiles que han ganado 1000 puntos de lealtad desde el último envío o donde el código de segmento era igual a "A". </li> 
    </ul> Para obtener más información, consulte la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creación de informes dinámicos con datos de perfil personalizados<br /> </td> 
   <td> Esta función le permite crear y administrar informes basados en datos de perfil personalizados creados durante la extensión de recurso de perfil. Los informes se pueden desglosar por atributos de perfil, como programa de fidelidad, canal preferido, etc.<br /> Para obtener más información, consulte la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Se ha mejorado el uso general de la memoria y la CPU de la aplicación

**Otros cambios**

* La actividad de flujo de trabajo Leer audiencia ahora puede leer audiencias de Experience Cloud. Anteriormente, esta actividad solo podía leer las audiencias Consulta y Lista . Consulte la [documentación detallada](../../automating/using/read-audience.md). (CAMP-23623)
* El identificador de la fuente de datos compartida predeterminada ahora está en modo de solo lectura y ya no se puede cambiar. Cambiar este identificador podría provocar algunos problemas al compartir audiencias con el Experience Cloud.
* La importación de audiencias desde el Gestor de colaboradores ahora funciona con archivos divididos. Anteriormente, el último archivo del segmento se importó mediante el flujo de trabajo técnico Importar audiencia compartida.
* Las cuentas externas de AWS S3 ahora admiten regiones y el mecanismo de autenticación de la versión 4. Consulte la [documentación detallada](../../administration/using/external-accounts.md).
* La ventana de selección de recursos ahora debe cargarse más rápido y permitir la selección de un recurso y salir de la ventana sin ningún problema.
* Ahora, los usuarios con derechos de administración y pertenecientes a las unidades organizativas y geográficas &quot;Todos&quot; pueden modificar las propiedades y estructura de los flujos de trabajo técnicos.
* Se han realizado mejoras en la interfaz de actividad de segmentación al crear nuevos segmentos: La pestaña Limitación ahora aparece directamente después de añadir una limitación. Los nombres de los nuevos segmentos ahora se incrementan (&quot;Segmento 1&quot;, &quot;Segmento 2&quot;, etc.).
* Se agrega un campo &quot;nextProcessingDate&quot; al recurso Flujo de trabajo. Este campo solo está visible a través de llamadas a la API de REST y le permite visualizar los flujos de trabajo en las próximas fechas de procesamiento.
* El campo &quot;sourceId&quot; ahora se expone en el recurso de registros de seguimiento (nms:trackingLog).
* Los valores &quot;Total opens&quot; y &quot;Total clicks&quot; ahora se pueden exportar en un archivo plano a través de un flujo de trabajo. (CAMP-24186)
* &quot;English - Danmark&quot; ya está disponible en la lista de idiomas preferidos en los perfiles. (CAMP-23728)
* Al utilizar una actividad de segmentación con un vínculo Additional data (targetData) , ahora un mensaje le informa de que los datos no están disponibles fuera del flujo de trabajo. Este mensaje se muestra al hacer clic en el botón Recuento o Vista previa de la actividad Segmentación . (CAMP-23651)
* Se han realizado mejoras para optimizar el espacio en disco utilizado por los flujos de trabajo: (CAMP-21979): Los archivos procesados por la actividad Cargar archivo ahora se eliminan de forma predeterminada. Una opción permite mantenerlos para necesidades específicas. Cuando se elimina un flujo de trabajo, su carpeta dedicada se suprime automáticamente del directorio del servidor.

**Parches**

* Se ha corregido un problema en el cual algunos eventos de informes sin procesar no tenían eventos de seguimiento asociados porque el campo eventDate no se rellenaba correctamente.
* Se ha corregido un problema que impedía que se mostraran campos personalizados en la ventana de vista previa de una entrega de notificaciones push.
* Se ha corregido un problema que impedía que el texto ajustara el cuerpo del mensaje de una notificación push en la ventana de vista previa.
* Se ha corregido un problema que se producía al enviar una entrega de recepción desde un flujo de trabajo cuando el destinatario principal estaba vacío.
* Se ha corregido un problema que impedía acceder a una asignación de destino si estaba vinculada a un esquema inexistente.
* Se ha corregido un problema que se podía producir al importar un archivo zip mediante una actividad de carga de archivo . (CAMP-24309)
* Se ha corregido un problema que provocaba un error PostgreSQL al realizar un envío recurrente. (CAMP-23613)
* Se ha corregido un problema que mostraba un mensaje de error al enviar una solicitud de API de REST con un atributo JSON vacío. (CAMP-23506)
* Se ha corregido un problema en los perfiles que definían en mayúsculas los caracteres que seguían al carácter &quot;ß&quot;. (CAMP-23136)
* Se ha corregido un problema que se producía al enviar envíos utilizados con la condición de elegibilidad de la personalización o del bloque de contenido dinámico al utilizar atributos de un esquema de perfil vinculado. (CAMP-22751)
* Se ha corregido un problema que impedía eliminar servicios. (CAMP-22050)
* Se ha corregido un problema que impedía cambiar los valores de País o Estado en un perfil de prueba. (CAMP-20426)
* Se ha corregido un problema que podía impedir que se cargara Creative Designer. (CAMP-24573)
* Se ha corregido un problema que eliminaba los caracteres añadidos después de los campos de personalización en el asunto del correo electrónico. (CAMP-24113)

## Versión 18.4: abril de 2018 {#release-18-4---april-2018}

**Parches**

_Plataforma_

* Se ha corregido un error que podía impedir que se procesaran correctamente las solicitudes de acceso o eliminación del RGPD. Este comportamiento se ha observado en algunos casos excepcionales en los que los datos extraídos contenían uno de los siguientes caracteres: &amp; &lt; > &quot; &#39;.

_Correos electrónicos, mensajes SMS y correo postal_

* Se ha corregido un problema que podía provocar que los KPI se sobrescribieran con valores incorrectos si la sincronización de broadlog tardaba más de una hora.

_Flujos de trabajo_

* Se ha mejorado la administración de memoria y el rendimiento optimizado en los flujos de trabajo.

_Creación de informes_

* El flujo de trabajo de uso compartido de KPI ahora recupera los valores de entrega de los últimos 2 meses en lugar de los últimos 6 meses. Se ha corregido un problema con la cuenta externa de uso compartido de KPI que mostraba fechas truncadas.
* Se ha corregido un problema que podría provocar que algunos mensajes no se tengan en cuenta en las métricas **Enviado**, **Entregado** y **Devolución**.
* Se ha corregido un error que se producía cuando el intervalo de tiempo elegido en el **Informe Resumen de envíos** era demasiado largo.

_Recursos personalizados_

* Se ha corregido un error que provocaba que fallara la preparación de recursos personalizados.

## Versión 18.3: marzo de 2018 {#release-18-3---march-2018}

**Nuevas funciones**

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
   <td> El nuevo Creative Designer de Adobe Campaign ofrece una experiencia de creación totalmente integrada en Campaign, lo que permite la creación visual rápida y sencilla de correos electrónicos personalizados cautivadores e individuales sin necesidad de crear una única línea de código. Gracias a su potente interfaz de arrastrar y soltar, Creative Designer ayuda a escalar la creación de correos electrónicos si los usuarios comienzan desde una pizarra en blanco o aprovechan los fragmentos de contenido o las plantillas existentes. <br /> Las funciones clave incluyen:<br /> 
    <ul> 
     <li> Diseñe y cree correos electrónicos interactivos y totalmente personalizados mediante una interfaz de arrastrar y soltar, aumentada por las integraciones nativas de Creative Cloud </li> 
     <li> Cree y guarde una plantilla de contenido de correo electrónico y aproveche las plantillas guardadas para ayudar a escalar la creación de correo electrónico </li> 
     <li> Crear y guardar fragmentos de contenido (como un encabezado, un pie de página, un artículo, etc.) para optimizar la creación de contenido y garantizar la coherencia de la marca </li> 
     <li> Cambie sin problemas entre crear en la interfaz de arrastrar y soltar y editar directamente el HTML de un correo electrónico haciendo clic en un botón </li> 
    </ul> Creative Designer para correo electrónico solo está disponible en inglés.<br /> Para obtener más información, consulte la  <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentación </a> detallada y vea este  <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregas push multilingües<br /> </td> 
   <td> La misma interfaz multilingüe sencilla, que ya existe en los canales de correo electrónico y SMS, se ha añadido al canal push para ayudarle a atraer clientes independientemente de su idioma preferido.<br /> Esta capacidad ofrece una solución escalable y automática para los clientes que administran campañas push en varias regiones y desean dirigirse a los usuarios en su idioma preferido. Permite cargar todas las variantes lingüísticas a través de una hoja de cálculo con plantilla en una única entrega push con un solo clic. A continuación, Adobe Campaign realiza una segmentación automática basada en las preferencias de idioma de los usuarios, lo que ayuda a reducir las redundancias simplificando los flujos de trabajo y los informes.<br /> Para obtener más información, consulte la <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso de recursos personalizados en la mensajería transaccional<br /> </td> 
   <td> Además de los campos predeterminados, la mensajería transaccional ahora le permite utilizar recursos personalizados para enriquecer el contenido de sus mensajes.<br /> Por ejemplo:<br /> 
    <ul> 
     <li> Aproveche los campos personalizados como criterios de reconciliación para que coincidan con un mensaje transaccional en un perfil </li> 
     <li> Aproveche los perfiles completos, los servicios y los datos vinculados para personalizar aún más los mensajes transaccionales. </li> 
    </ul> Para obtener más información, consulte la <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Se ha corregido un problema que impedía exportar más de 5000 registros de una lista.
* Se ha corregido un problema que se producía al exportar datos a archivos con nombre de campos de personalización.

_Correos electrónicos, mensajes SMS y correo postal_

* Se ha corregido un problema que provocaba que los SMS de varias partes se truncaran porque el tamaño de las partes se calculaba en caracteres en lugar de en bytes.
* Se ha agregado una opción que permite actualizar los KPI **[!UICONTROL Delivered]** o **[!UICONTROL Bounces + Errors]** en tiempo real después de realizar el envío. Se vuelven a calcular directamente desde el SR (Informe de estado) recibido del proveedor.
* Se ha corregido un problema con la utilidad de calendario en el programador de envíos.
* Se ha corregido un problema de visualización al abrir un destino por segunda vez en una entrega enviada.
* Se ha corregido un problema que provocaba un mensaje de error que solicitaba una fecha de inicio al crear una plantilla de correo electrónico con una fecha de envío retrasada.
* Se ha corregido un problema que podría provocar problemas de procesamiento de imágenes al editar el contenido de una entrega.
* Se ha corregido un problema con las pruebas al duplicar una campaña.
* Se ha corregido un problema que provocaba un mensaje de error al acceder a una plantilla de campaña a través de la barra de navegación, después de añadir una entrega al flujo de trabajo.
* Se ha corregido un problema que podía impedir que se seleccionara automáticamente el ganador de un correo electrónico de prueba A/B, lo que provocaba que no se enviara el correo electrónico. Este comportamiento podría producirse si el envío está en estado **[!UICONTROL retryInProgress]**.
* Se ha corregido un problema que podía provocar que apareciera un mensaje de error al volver a abrir los parámetros de un correo electrónico de prueba A/B.

_Audiencias y consultas_

* Se ha corregido un problema que impedía acceder a datos y configurar consultas para destinatarios duplicados de Adobe Campaign Classic a Standard.
* Se ha corregido un problema que se producía al utilizar un campo de tipo filtro en el editor de consultas, después de utilizar los botones **Count** o **Preview**.

_Flujos de trabajo_

* El flujo de trabajo **Facturación** se ha optimizado para mejorar el retraso en la preparación del envío.
* Se ha corregido un problema que impedía que los datos de población se mostraran en una transición saliente al utilizar una actividad de envío recurrente.
* Se ha corregido un problema que impedía que se mostraran registros rechazados en una transición después de una actividad **Update data**.
* Se ha corregido un problema que podría provocar errores en el flujo de trabajo técnico **deliverabilityUpdate**.

_Integraciones_

* Se ha corregido un problema que impedía que los caracteres internacionales se enviaran correctamente a Adobe Analytics.
* Los recursos ahora deben cargarse más rápido al intentar insertar una imagen desde la biblioteca de recursos del Experience Cloud en un mensaje.
* Se ha corregido un problema que podía impedir que la ventana de selección de recursos se cerrara en algunos casos.
* Desde un detalle de fuente de datos, ahora puede acceder directamente a su flujo de trabajo relacionado para comprobar el estado del flujo de trabajo.
* Ahora puede actualizar el esquema de Déclencheur directamente al definir o editar un evento de déclencheur. Con este cambio, ya no tiene que cancelar la publicación del déclencheur y crear otro.

_Mensajes transaccionales_

* Se ha corregido un error con la plantilla de mensaje transaccional cuando se ampliaba el recurso de entrega.
* Ahora es posible eliminar mensajes transaccionales.

## Versión 18.2: febrero de 2018 {#release-18-2---february-2018}

**Nuevas funciones**

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
   <td> La actividad de flujo de trabajo <strong>Subscription Services</strong> ahora le permite suscribirse o cancelar la suscripción de una lista de perfiles a varios servicios. En el flujo de trabajo, importe un archivo que contenga los perfiles y, para cada perfil, el tipo de operación y el servicio. La actividad <strong>Subscription Services</strong> podrá utilizar esta información y gestionar dinámicamente todas sus suscripciones y cancelaciones de suscripción de perfiles a la vez.<br /> Para obtener más información, consulte la <a href="../../automating/using/subscription-services.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Actividad de enriquecimiento: enriquecer datos basados en transiciones anteriores<br /> </td> 
   <td> La nueva actividad de flujo de trabajo <span class="uicontrol">Enrichment</span> permite aprovechar las transiciones de entrada y completar la transición de salida con datos adicionales. Si segmenta perfiles, la actividad de enriquecimiento le permite enriquecer la información de perfiles con datos adicionales que no se almacenan en la base de datos (procedentes de un archivo importado, por ejemplo).<br /> Para obtener más información, consulte la <a href="../../automating/using/enrichment.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* La barra superior de la interfaz de Adobe Campaign se ha actualizado con el nuevo menú Experience Cloud.
* Se ha corregido un problema que impedía que el vínculo a **[!UICONTROL Offers]** se mostrara en la lista desplegable de soluciones.

_Correos electrónicos, mensajes SMS y correo postal_

* La fase de preparación de la entrega se ha mejorado para mejorar el rendimiento.
* Se han corregido varios problemas que podían provocar que los registros de seguimiento se dañaran en algunas situaciones específicas.
* Se ha corregido un problema de actualización de fecha de contacto que se producía cuando se cambiaba la fecha de contacto entre la preparación de la entrega y la confirmación. Ahora, al cambiar la fecha de contacto después de la preparación, debe volver a preparar la entrega antes de poder confirmarlo. Consulte la [documentación detallada](../../sending/using/preparing-the-send.md).

_Notificaciones push_

* Se ha corregido un error que impedía que algunos campos de personalización funcionaran en las notificaciones push de iOS.
* Se ha corregido un error que mostraba las tasas de clic y apertura como 0 % en el panel de notificaciones push.

_Informes_

* Se ha corregido un error que mostraba la lista de informes como vacía en algunos exploradores.
* Se ha corregido un error que se producía en el flujo de trabajo técnico **[!UICONTROL Report sharing]** justo antes de alcanzar su límite de caducidad.

_Flujos de trabajo_

* Se ha corregido un problema que impedía el acceso a las actividades después de arrastrarlas y soltarlas.
* Se ha corregido un problema que podría provocar que el orden de las transiciones de salida de una actividad **[!UICONTROL Segmentation]** cambie en algunas situaciones.
* Se ha corregido un error que se producía al leer una audiencia que contenía un campo de tipo de lista desglosada y que anteriormente se había guardado desde un flujo de trabajo
* Se ha corregido un problema que provocaba que la opción **[!UICONTROL Request confirmation before sending messages]** permaneciera activada incluso después de desmarcarla al definir las propiedades de programación de un envío creado en un flujo de trabajo.
* La eliminación automática de filas duplicadas (cláusula DISTINCT) ahora se puede deshabilitar en actividades **[!UICONTROL Query]** a través de una nueva opción ubicada en la pestaña **[!UICONTROL Additional data]**. Se recomienda desactivar esta opción al definir muchos (más de 100) elementos adicionales por motivos de rendimiento.

_Integraciones_

* Se han realizado algunas mejoras en la pantalla de configuración **[!UICONTROL Data sources]**.

_Problemas conocidos_

Se recomienda no utilizar Internet Explorer versión 11 debido a posibles problemas de visualización.

Pueden producirse algunos problemas al utilizar vínculos de ayuda contextuales desde la interfaz de Campaign. Se corregirán en la versión 18.3.

## Versión 18.1: enero de 2018 {#release-18-1---january-2018}

**Nuevas funciones**

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
   <td> Informes para administración de fatiga es un informe dedicado y configurable que muestra el impacto que las reglas de fatiga tienen en los envíos de los canales Correo electrónico, Push, SMS y Correo postal dentro de un intervalo de fechas especificado antes del envío. Con la perspectiva añadida de poder ver rápidamente todas las campañas en conflicto en una sola vista, los especialistas en marketing pueden planificar las campañas de marketing de forma que establezcan las reglas de fatiga de forma más eficaz y prioricen las comunicaciones.<br /> Para obtener más información, consulte la <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso compartido de informes<br /> </td> 
   <td> Uso compartido de informes le permite compartir sus informes con los usuarios de Adobe Campaign como datos adjuntos de correo electrónico, incluso de forma recurrente y automatizada. Los usuarios que reciben informes recurrentes pueden cancelar la suscripción a estas comunicaciones a través de un vínculo específico en cada correo electrónico.<br /> Para obtener más información, consulte la <a href="../../reporting/using/reporting-interface.md#share-tab">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Insertar nuevas funciones<br /> </td> 
   <td> Vista previa de mensajes push : revise las notificaciones con el editor de contenido de notificaciones push (iOS y Android) para ver exactamente lo que verán los destinatarios antes de probar o ejecutar el envío.<br /> Para obtener más información, consulte la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentación detallada</a>.<br /> Contenido disponible : cuando una aplicación no se abre en mucho tiempo, sus datos pueden quedar obsoletos. Esto hace que los datos deban actualizarse o reemplazarse en el momento en que un usuario finalmente abre la aplicación, lo que puede provocar retrasos en el uso de la aplicación. Con la compatibilidad añadida de Contenido disponible, los usuarios de Adobe Campaign pueden despertar su aplicación para actualizar sus datos en segundo plano al enviar una notificación push, lo que permite una buena coherencia y control sobre la experiencia en la aplicación de un usuario.<br /> Contenido mutable : con la ayuda de Contenido mutable, ahora los usuarios de Adobe Campaign pueden aprovechar las extensiones de su aplicación móvil para modificar aún más el contenido o la presentación de las notificaciones push entrantes enviadas desde Adobe Campaign. Por ejemplo, los usuarios pueden aprovechar el contenido mutable para: <br /> 
    <ul> 
     <li> descifrar datos que se entregaron en formato cifrado </li> 
     <li> descargar imágenes u otros archivos multimedia y añadirlos como archivos adjuntos a una notificación </li> 
     <li> cambiar el texto del cuerpo o del título de una notificación </li> 
     <li> añadir un identificador de subproceso a una notificación </li> 
    </ul> Para obtener más información sobre el contenido disponible y el contenido mutable, consulte la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentación detallada</a>.<br /> <strong>Advertencia:</strong> estas actualizaciones de las notificaciones push requieren que los clientes actualicen sus aplicaciones móviles. Consulte <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard/using/communication-channels/push-notifications/push-payload.translate.html">esta nota técnica</a> para obtener más información.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregas optimizadas para zonas horarias<br /> </td> 
   <td> Programe notificaciones recurrentes por correo electrónico, SMS y push para que se envíen en un día/hora específico en el huso horario de cada destinatario, lo que garantiza que los mensajes se envíen en el momento adecuado sin configurar varios envíos. <br /> Para obtener más información, consulte la <a href="../../automating/using/scheduler.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Activación de actividad de señal de API<br /> </td> 
   <td> Ahora es posible déclencheur de una actividad de señal para sus flujos de trabajo directamente desde la API de Adobe Campaign Standard.<br /> Para obtener más información, consulte la <a href="/help/api/using/triggering-a-signal-activity.md">documentación detallada</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* La búsqueda de perfiles se ha optimizado para mejorar el rendimiento.
* El identificador interno de los grupos de seguridad predeterminados ahora está en modo de solo lectura para los usuarios estándar.

_Correos electrónicos, mensajes SMS y correo postal_

* Se ha corregido un problema de visualización que se producía al insertar emojis en el contenido de los envíos.
* Se ha corregido un problema que permitía al usuario acceder a los registros de envío cuando el envío seguía en edición.
* La actividad **[!UICONTROL Scheduler]** ahora le permite realizar sus envíos en función del huso horario del destinatario.
* SMS: La opción **[!UICONTROL Store incoming MO]** de la base de datos se ha agregado a cuentas externas. Cuando se selecciona, todos los SMS entrantes se almacenan en la tabla **inSMS**.
* SMS: Los servicios ahora se adjuntan a un evento en lugar de a una plantilla transaccional.
* SMS: El tiempo de espera de conexión SMTP predeterminado se ha reducido a 30 segundos.

_Notificaciones push_

* Se ha corregido un error que impedía que se detuvieran los envíos de notificaciones push.
* Se ha añadido una opción en las opciones avanzadas de las notificaciones push para activar la aplicación con una notificación push.
* Se ha agregado un botón de pausa para el vídeo de vista previa de notificaciones push.
* La vista previa de notificaciones push ya está disponible para distintos dispositivos, como iPhone, Android y tabletas.

_Informes_

* Se ha corregido un error que mostraba tasas superiores al 100%.
* Se ha corregido un problema que impedía a los usuarios descargar informes en CSV.
* Se ha agregado un nuevo elemento **[!UICONTROL Report]** en la página principal.

_Flujos de trabajo_

* Se ha corregido un problema que provocaba un mensaje de error al utilizar datos adicionales en una consulta y al agregar alias que contenían espacios. Los caracteres no alfanuméricos ahora se sustituyen por &quot;_&quot;.
* Se ha corregido un problema en el cual el flujo de trabajo técnico que calculaba los KPI se podía detener de forma predeterminada en algunos casos.

_Perfiles y audiencias_

* Se ha corregido un error que se producía al agregar varios filtros en la consulta de una audiencia.
* Se ha corregido un problema de visualización que se producía al cambiar la imagen de un perfil.
* Se ha añadido una información sobre herramientas que muestra el número de resultado exacto después de contar la población de una consulta.
* Se ha corregido un problema que podía impedir que un usuario seleccionara una audiencia o cerrara la ventana del selector de audiencias.
* Se ha actualizado la lista de funciones disponibles en el editor de expresiones. Se han eliminado las funciones **FormatCurrency** y **ConvertCurrency**.

