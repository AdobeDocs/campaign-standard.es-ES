---
title: Notas de la versión 2018
description: Esta página enumera todas las versiones de 2018 de Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 17521357-14ae-4751-bd7c-aeabbcf71d07
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '5355'
ht-degree: 9%

---

# Notas de la versión 2018{#release-notes}

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
   <td> La mensajería en aplicación permite atraer a los usuarios de aplicaciones móviles de forma más eficaz ya que proporciona interacción contextual y permite llegar a usuarios que pueden haber salido de notificaciones push. Utilice la mensajería en la aplicación junto con notificaciones push para crear una experiencia relevante y personalizada. Esto mejora la conversión y retención de los usuarios de la aplicación.<br /> Para obtener más información, consulte la <a href="../../channels/using/about-in-app-messaging.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Adobe Launch para aplicaciones móviles (versión beta)<br /> </td> 
   <td> La integración de Adobe Launch con Adobe Campaign ahora simplifica y automatiza el proceso de activación de la propiedad de la aplicación móvil en Campaign mediante el SDK V5 para móviles.<br /> Para obtener más información, consulte la <a href="https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Adobe Campaign Standard ahora es compatible con la versión 4 de la API de Amazon S3.

**Otros cambios**

* En los registros generales hay ahora una distinción entre el número máximo de conexiones y el número máximo de mensajes por hora. Cuando se alcanzan los límites, es posible saber por qué el rendimiento está limitado. Anteriormente, el mismo mensaje (“cuota alcanzada”) se aplica a ambos casos.
* Al configurar una aplicación móvil en Campaign, el usuario ahora puede saber si el certificado de iOS y la clave del servidor de Android se han cargado correctamente y su fecha de caducidad.

  Para obtener más información, consulte la documentación detallada sobre cómo configurar una aplicación móvil mediante [SDK V4](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html) y [SDK V5](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html).

* Dirija la actividad a usuarios en una aplicación móvil específica seleccionando una aplicación móvil mientras define las propiedades de la campaña. Esta función es para canales de mensajería push y en la aplicación.

  Para obtener más información, consulte la [documentación detallada](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification).

* Al seleccionar un bloque de contenido mediante la interfaz de Creative Designer, todos los bloques de contenido de la lista ahora se cargan y muestran. (CAMP-27311)

  Para obtener más información, consulte [documentación detallada](../../designing/using/personalization.md#adding-a-content-block).

**Parches**

* Se ha corregido un problema que mostraba una discrepancia en los recuentos de registros entre el panel de correo electrónico y el informe de resumen de correo electrónico de los correos electrónicos transaccionales. (CAMP-28237
* Se ha corregido un problema en los flujos de trabajo que podía mostrar un mensaje de error al importar un archivo a través de una actividad de transferencia de archivos. (CAMP-27435)
* Se ha corregido un problema con las páginas de aterrizaje que contenían más de 25 servicios, que provocaba que los servicios se desseleccionaran aleatoriamente en el formulario. (CAMP-26572)
* Se ha corregido un problema en los flujos de trabajo que impedía configurar cuentas externas con una URL SFTP al utilizar la actividad de transferencia de archivos. (CAMP-26475)
* Se ha corregido un problema que impedía actualizar el informe de resumen de servicios. (CAMP-26301)
* Se ha corregido un problema en los flujos de trabajo al utilizar una actividad de Enriquecimiento, que impedía que un campo personalizado mostrara la fecha correcta. (CAMP-26242)
* Se ha corregido un problema que impedía que las fechas de suscripción del servicio se actualizaran al importarse a través de una importación de archivos.
* Se ha corregido un error con la actividad de carga de archivo que impedía que los flujos de trabajo importaran archivos (CAMP -27068).
* Se ha corregido un problema que mostraba un número incorrecto de suscripciones en los informes de resumen del servicio (CAMP -25587).
* Se ha corregido un problema de discrepancia de datos entre los informes de Adobe Analytics y Adobe Campaign. (CAMP-25393)
* Se ha corregido un problema que podía impedir que un usuario con acceso limitado iniciara sesión. (CAMP-27381)
* Se ha corregido un problema que podía impedir que se mostrara la lista de contenido de Adobe Experience Manager al editar un correo electrónico con Creative Designer. (CAMP-27181)
* Se ha corregido un problema que podía impedir que se abriera Creative Designer y que provocaba un error. (CAMP-27304)
* Se ha corregido un problema que impedía que la operación de arrastrar y soltar funcionara correctamente en el Creative Designer al utilizar Internet Explorer 11.
* Se ha corregido un problema que provocaba que las imágenes cargadas desde una cámara y grabadas en modo vertical se mostraran en una posición girada no deseada.
* Se ha corregido un problema que mostraba información de selección no clara al utilizar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que impedía duplicar correctamente un elemento al utilizar la interfaz del editor de consultas en Creative Designer.
* Se ha corregido un problema que seguía enviando mensajes SMS a los destinatarios en la lista de bloqueados de la, aunque se hubieran dado de baja mediante una respuesta automática. (CAMP-27128)
* Se ha corregido un problema que impedía mostrar los errores que causaban el error **Database Cleanup** flujo de trabajo fallido. (CAMP-26876)
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
   <td> Indicador de alta prioridad para Android: habilite la entrega de una notificación push con alta prioridad para aplicaciones Android, lo que hace que el dispositivo en suspensión se despierte y ejecute un procesamiento limitado. Tenga en cuenta que la prioridad predeterminada es Normal, lo que puede retrasar la entrega del mensaje para ahorrar batería. <br /> Para obtener más información, consulte la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Filtro de tipología para suscriptores de aplicaciones móviles<br /> </td> 
   <td> Suscripciones de soporte en el filtro de tipología: al especificar los criterios de filtrado para una regla de tipología, las suscripciones de aplicación se pueden seleccionar como dimensiones de filtrado y segmentación, lo que permite filtrar los atributos de los usuarios con o sin perfil. <br /> Para obtener más información, consulte la <a href="../../sending/using/about-typology-rules.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Importación automática de contenido desde una dirección URL durante la preparación del mensaje<br /> </td> 
   <td> Ahora es posible importar contenido de correo electrónico desde una dirección URL durante la fase de preparación. Para las entregas de correo electrónico recurrentes, se recupera el contenido de HTML más reciente cada vez que se prepara el mensaje, lo que garantiza que el contenido siempre esté actualizado en el momento en que se envía el correo electrónico. Esta función también permite crear una entrega programada con contenido de una dirección URL aunque el contenido aún no esté listo.<br /> Para obtener más información, consulte la <a href="../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mensaje de notificación de lanzamiento de Campaign<br /> </td> 
   <td> Ahora aparece un mensaje emergente cuando un usuario inicia sesión después de actualizar la instancia a una nueva versión. El mensaje indica el número de versión e incluye un vínculo a las notas de la versión. Puede optar por ocultar el mensaje hasta la próxima versión. <br /> </td> 
  </tr> 
  <tr> 
   <td> Administración de usuarios<br /> </td> 
   <td> La capacidad de unidad geográfica ya no está disponible para las nuevas instancias de Campaign Standard, así como para las instancias existentes sin crear unidades geográficas, a partir de la versión 18.7.<br /> Para obtener más información, consulte esta <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/deprecated-features.html?lang=es#release-notes">página</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* La integración de Adobe Campaign y Adobe Target ahora le permite aprovechar las ventajas de Target [Permisos](https://experienceleague.adobe.com/docs/target/using/administer/manage-users/enterprise/properties-overview.html?lang=es) función. Al incluir una imagen dinámica de Adobe Target en un mensaje de correo electrónico, ahora puede especificar una Target Property (código at_property).
* Las solicitudes de acceso o eliminación de la privacidad del RGPD ahora tienen en cuenta los recursos personalizados que tienen un vínculo de copia propia al recurso de perfiles. Para los vínculos simples de cardinalidad 1 y los vínculos de colección de cardinalidad N, debe seleccionar &quot;Eliminar/duplicar el registro de destino implica eliminar/duplicar los registros a los que hace referencia el vínculo&quot; en el recurso personalizado. Para vínculos simples de cardinalidad 0 o 1, seleccione &quot;Eliminar/duplicar el registro implica eliminar/duplicar el registro de destino al que hace referencia el vínculo&quot;.

**Otros cambios**

* El tiempo de espera para compartir informes ha aumentado de uno a cuatro minutos para evitar errores de tiempo de espera.
* Al editar el contenido de un correo electrónico, el nuevo Creative Designer se abre de forma predeterminada. Si lo desea, puede volver al editor de contenido predeterminado en cualquier momento después de guardar los cambios. Para obtener más información, consulte [documentación detallada](../../designing/using/designing-content-in-adobe-campaign.md).
* En el Creative Designer, ahora se puede añadir un nuevo componente de contenido a un correo electrónico: el carrusel. Para obtener más información, consulte [documentación detallada](../../designing/using/designing-from-scratch.md#about-content-components).
* En un informe de clic activo de mensaje transaccional, al hacer clic en el **Cambiar perfil** , ahora solo se muestran los perfiles de prueba vinculados al evento definido para el mensaje transaccional.

**Parches**

* Se ha corregido un problema con el filtro de consulta byEmail que no devolvía ningún resultado. (CAMP-23420)
* Se ha corregido un problema que permitía a un usuario estándar acceder a determinadas funciones o pantallas restringidas a los administradores (/rest/head/&#42; extremos, pantallas de mensajería transaccional, perfiles y audiencias (pantallas de importación).
* Se ha corregido un problema que impedía que las solicitudes de eliminación de la privacidad del RGPD procesaran recursos personalizados si su nombre empezaba por un número.
* Se ha corregido un error que impedía que la actividad Guardar audiencia compartiera suscriptores de aplicaciones en Adobe Experience Cloud.
* Se ha corregido un problema con la actividad Transferencia de archivos que se podía producir cuando el nombre del archivo contenía espacios en blanco. (CAMP-25936)
* Se ha corregido un problema que se podía producir al utilizar el botón de reconexión después de que caduque una sesión. (CAMP-25560)
* Se ha corregido un problema que podría provocar exclusiones al realizar envíos con optimización de zona horaria asociada a reglas de fatiga. (CAMP-25425)
* Se ha corregido un problema que se producía al usar la función RGPD de API, y que podía impedir la eliminación de datos con un vínculo de tipo 0-1.
* Se ha corregido un problema que podía provocar un mensaje de error al cancelar la edición de una regla de tipología de fatiga.
* Se ha corregido un problema que se podía producir al obtener una vista previa del contenido de una entrega después de editarlo.
* Se ha corregido un problema que se podía producir al procesar archivos zip CSV mientras se utilizaba la opción de descompresión.
* Se ha corregido un problema con Creative Designer que provocaba fuentes de color y formato no deseados al cambiar texto con estilo integrado a un vínculo o al editar ese vínculo. (CAMP-26001)
* Se ha corregido un problema que impedía que el informe de clic activo mostrara los porcentajes de cada condición en las entregas que contenían contenido dinámico. Anteriormente, solo se mostraban los clics en la variante predeterminada.

## Versión 18.6: junio de 2018 {#release-18-6---june-2018}

**Mejoras**

* El **[!UICONTROL History]** La API se ha añadido a Adobe.IO. Permite acceder a información relacionada con el historial de marketing de un perfil: número de puntos de contacto, envíos enviados, URL de página espejo, etc. Para obtener más información, consulte [caso de uso específico](../../api/using/interacting-with-marketing-history.md) .
* El **[!UICONTROL Database cleanup]** El flujo de trabajo técnico de se ha optimizado para garantizar un mejor rendimiento del backup de la base de datos.
* El diseñador creativo para correo electrónico ahora también está disponible en francés y alemán.

**Otros cambios**

* A **[!UICONTROL Compute stats]** se ha añadido el botón en el **[!UICONTROL Deployment]** ventana de envíos enviados. Permite recuperar los KPI más recientes, por ejemplo, si los resultados del envío tardan demasiado en actualizarse o no se han tenido en cuenta. Para obtener más información, consulte [esta sección](../../sending/using/confirming-the-send.md).
* En el **Actualización para la entrega** flujo de trabajo técnico predeterminado, los administradores funcionales ahora pueden definir el número de errores consecutivos que se deben ignorar en la **Actualizar reglas** actividad de javascript. De forma predeterminada, el valor del campo se establece en 0, lo que significa que se omitirán todos los errores.
* Se ha optimizado el SQL generado al administrar las condiciones de restricción de acceso a la unidad.
* El **[!UICONTROL Update]** La actividad ahora permite añadir, actualizar o eliminar datos relacionados con suscripciones (tabla nms:appSubscriptionRcp).
* El **[!UICONTROL Update delivery execution]** flujo de trabajo técnico se ha dividido en dos flujos de trabajo para optimizar el rendimiento: **[!UICONTROL Update delivery execution]**: actualiza el seguimiento de la entrega. De forma predeterminada, se inicia cada 10 minutos. **[!UICONTROL Update delivery indicators]**: actualiza los KPI de la entrega, se inicia cada hora de forma predeterminada. Para obtener más información sobre flujos de trabajo técnicos, consulte [sección](../../administration/using/technical-workflows.md#list-of-technical-workflows).
* Cuando una entrega envía mensajes, el estado en la variable **[!UICONTROL Deployment]** La sección ahora puede tener dos valores: **[!UICONTROL Sending]**: los mensajes se están enviando. **[!UICONTROL Sending (retry)]**: se está realizando un reintento.
* Usuarios con **[!UICONTROL Delivery preparation]** Las funciones de ahora pueden enviar pruebas. (CAMP-24313)
* El **Habilitar TLS en SMPP** se ha añadido a la opción **Enrutamiento de SMS mediante SMPP** cuenta externa. Consulte esta [sección](../../administration/using/configuring-sms-channel.md#defining-an-sms-routing) para obtener más información.

**Parches**

* Se ha corregido un problema que podía impedir que se enviaran correos electrónicos al incluir una imagen dinámica de Adobe Target (CAMP-24848).
* Se ha corregido un problema con **[!UICONTROL Privacy Access/Delete Request]** flujos de trabajo técnicos, que no se completaron si falló alguna de las solicitudes.
* Se ha corregido un problema que impedía que el servicio principal de privacidad recibiera actualizaciones de estado de solicitud de Campaign.
* Se ha corregido un problema que impedía que el flujo de trabajo técnico **[!UICONTROL Import shared audience]** funcionara correctamente (CAMP -25465).
* Se ha corregido un problema que impedía que las solicitudes de privacidad de Campaign se marcaran como completadas en el Privacy Service principal.
* Se ha corregido un problema que podía impedir que algunos usuarios iniciaran sesión en el Campaign Standard a través de la autenticación IMS cuando el Adobe ID era demasiado largo. (CAMP-24095)
* Se ha corregido un problema con Creative Designer que se podía producir al eliminar módulos de contenido. (CAMP-25242)
* Se ha corregido un problema que se producía al utilizar reglas de fatiga de notificaciones push para suscriptores sin perfil en la base de datos. (CAMP-25344)
* Se ha corregido un problema que podía mostrar un mensaje de error al acceder a los registros de exclusión de envíos. (CAMP-24724)
* Se ha corregido un problema que impedía que se prepararan pruebas en instancias con registros de envío extendidos.
* Se han corregido dos problemas que podían producirse al publicar recursos personalizados con **[!UICONTROL Sending log]** extensión activada.
* Se ha corregido un problema que se podía producir con la duración de la entrega que no se tenía en cuenta en las entregas recurrentes.
* Se ha corregido un problema que se podía producir al ordenar los datos en la variable **[!UICONTROL Client data]** para recursos personalizados con más de 100.000 registros. (CAMP-24308)
* Se ha corregido un problema con las dimensiones de perfil personalizadas que no se tenían en cuenta al usar la función de búsqueda en los informes dinámicos.
* Se ha corregido un problema con la visualización de datos internacionales para los niveles de cuenta en los informes dinámicos.
* Ahora es posible crear un servicio sin un mensaje de confirmación de suscripción o de baja.

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
   <td> La integración de Privacy Core Service le permite automatizar sus solicitudes de RGPD en un contexto de varias soluciones a través de una sola llamada de API JSON. <br /> Las solicitudes de RGPD enviadas desde el Servicio principal de privacidad a todas las soluciones de Experience Cloud ahora se gestionan automáticamente mediante Campaign. <br /> Para obtener más información, consulte la <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mejoras de push: comentarios detallados sobre la entrega<br /> </td> 
   <td> Adobe Campaign ahora permite recibir comentarios detallados (envío de registros y registros de exclusión) sobre los mensajes push de los proveedores (APNS/GCM) a través de MCPNS.<br /> Para obtener más información, consulte la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Extensión de registros de envío<br /> </td> 
   <td> La extensión de registros de envío permite ampliar los registros de envío con datos de perfil y código de segmento procedentes de flujos de trabajo. Esta información se puede utilizar en los informes dinámicos y permite mantener una instantánea de cierta información en el momento de la entrega de un envío.<br /> Hay dos casos de uso más:<br /> 
    <ul> 
     <li> Exportar registros extendidos con datos "congelados": como experto en marketing, me gustaría exportar todos los perfiles con un código de segmento igual a "A" (proveniente del motor de flujo de trabajo). </li> 
     <li> Segmentación de datos "congelados": como experto en marketing, me gustaría <strong>redestinar</strong> todos los perfiles que hayan ganado 1000 puntos de lealtad desde el último envío o cuyo código de segmento sea igual a "A". </li> 
    </ul> Para obtener más información, consulte la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creación de informes dinámicos con datos de perfil personalizados<br /> </td> 
   <td> Esta función le permite crear y administrar informes basados en datos de perfil personalizados creados durante la extensión de recursos de perfil. Puede desglosar informes por atributo de perfil, como programa de fidelidad, canal preferido, etc.<br /> Para obtener más información, consulte la <a href="../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Se ha mejorado el uso general de memoria y CPU de la aplicación

**Otros cambios**

* La actividad de flujo de trabajo Leer audiencia ahora puede leer audiencias de Experience Cloud. Anteriormente, esta actividad solo podía leer audiencias de Consulta y Lista. Consulte la [documentación detallada](../../automating/using/read-audience.md). (CAMP-23623)
* El identificador de la fuente de datos compartida predeterminada ahora está en modo de solo lectura y ya no se puede cambiar. Si se cambia este identificador, podrían producirse algunos problemas al compartir audiencias con el Experience Cloud.
* La importación de audiencias desde el Gestor de colaboradores ahora funciona con archivos divididos. Anteriormente, el último archivo del segmento se importó mediante el flujo de trabajo técnico Importar audiencia compartida.
* Las cuentas externas de AWS S3 ahora admiten regiones y el mecanismo de autenticación de la versión 4. Consulte la [documentación detallada](../../administration/using/external-accounts.md).
* La ventana de Selección de recursos ahora debe cargarse más rápido, permitir la selección de un recurso y salir de la ventana sin ningún problema.
* Las propiedades y la estructura de los flujos de trabajo técnicos ahora pueden modificarlas los usuarios con derechos de administración y pertenecientes a las unidades organizativas y geográficas &quot;Todos&quot;.
* Se han realizado mejoras en la interfaz de actividad de Segmentación al crear nuevos segmentos: La pestaña Limitación ahora aparece directamente después de añadir una limitación. Los nombres de los nuevos segmentos ahora se incrementan (&quot;Segmento 1&quot;, &quot;Segmento 2&quot;, etc.).
* Se agrega un campo &quot;nextProcessingDate&quot; al recurso de flujo de trabajo. Este campo solo está visible a través de llamadas a la API de REST y le permite visualizar los flujos de trabajo en las próximas fechas de procesamiento.
* El campo &quot;sourceId&quot; ahora se expone en el recurso de registros de seguimiento (nms:trackingLog).
* Los valores &quot;Total opens&quot; y &quot;Total clicks&quot; ahora se pueden exportar en un archivo plano a través de un flujo de trabajo. (CAMP-24186)
* &quot;Inglés - Danmark&quot; ya está disponible en la lista Idiomas preferidos en los perfiles. (CAMP-23728)
* Al utilizar una actividad de Segmentación con un vínculo de Datos adicionales (targetData), un mensaje ahora le informa de que los datos no están disponibles fuera del flujo de trabajo. Este mensaje se muestra al hacer clic en el botón Recuento o Vista previa de la actividad Segmentación. (CAMP-23651)
* Se han realizado mejoras para optimizar el espacio en disco utilizado por los flujos de trabajo: (CAMP-21979): Los archivos procesados por la actividad &quot;Cargar archivo&quot; ahora se eliminan de forma predeterminada. Una opción le permite conservarlos para necesidades específicas. Cuando se elimina un flujo de trabajo, su carpeta dedicada se suprime automáticamente del directorio del servidor.

**Parches**

* Se ha corregido un problema por el cual algunos eventos de informes sin procesar no tenían eventos de seguimiento asociados porque el campo eventDate no se rellenaba correctamente.
* Se ha corregido un problema que impedía que se mostraran campos personalizados en la ventana de vista previa de una entrega de notificaciones push.
* Se ha corregido un problema que impedía que el texto ajustara el cuerpo del mensaje de una notificación push en la ventana de vista previa.
* Se ha corregido un problema que se producía al realizar un envío recurrente desde un flujo de trabajo cuando el destinatario principal está vacío.
* Se ha corregido un problema que impedía acceder a una asignación de destino si estaba vinculada a un esquema inexistente.
* Se ha corregido un problema que se podía producir al importar un archivo zip a través de una actividad de carga de archivo. (CAMP-24309)
* Se ha corregido un problema que provocaba un error de PostgreSQL al realizar un envío recurrente. (CAMP-23613)
* Se ha corregido un problema que mostraba un mensaje de error al enviar una solicitud de API de REST con un atributo JSON vacío. (CAMP-23506)
* Se ha corregido un problema en los perfiles que establecían en mayúsculas los caracteres que siguen al carácter &quot;ß&quot;. (CAMP-23136)
* Se ha corregido un problema que se producía al enviar envíos utilizados con la condición de idoneidad del bloque de contenido dinámico o de personalización mientras se utilizaban atributos de un esquema de perfil vinculado. (CAMP-22751)
* Se ha corregido un problema que impedía eliminar servicios de. (CAMP-22050)
* Se ha corregido un problema que impedía cambiar los valores de País o Estado en un perfil de Prueba. (CAMP-20426)
* Se ha corregido un problema que podía impedir que Creative Designer se cargara. (CAMP-24573)
* Se ha corregido un problema que eliminaba los caracteres añadidos después de los campos de personalización en el asunto del correo electrónico. (CAMP-24113)

## Versión 18.4: abril de 2018 {#release-18-4---april-2018}

**Parches**

_Plataforma_

* Se ha corregido un error que podía impedir que se procesaran correctamente las solicitudes de eliminación o acceso de RGPD. Este comportamiento se ha observado en algunos casos excepcionales en los que los datos extraídos contenían uno de los siguientes caracteres: &amp; &lt; > &quot; &#39;.

_Correos electrónicos, mensajes SMS y correo directo_

* Se ha corregido un problema que podía provocar que los KPI se sobrescriban con valores incorrectos si la sincronización del registro de banda ancha tardaba más de una hora.

_Flujos de trabajo_

* Administración de memoria mejorada y rendimiento optimizado en flujos de trabajo.

_Creación de informes_

* El flujo de trabajo de uso compartido de KPI ahora recupera los valores de envío de los últimos 2 meses en lugar de los últimos 6 meses. Se ha corregido un problema con la cuenta externa de uso compartido de KPI que mostraba fechas truncadas.
* Se ha corregido un problema que podría provocar que algunos mensajes no se tengan en cuenta en **Enviado**, **Entregado** y **Devolución** métricas.
* Se ha corregido un error que se producía cuando el intervalo de tiempo elegido en la variable **Informe de resumen de envío** era demasiado largo.

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
     <li> Derecho de acceso: permite que el sujeto de datos reciba una copia de sus datos personales capturados por los controladores de datos, incluso los datos almacenados en Adobe Campaign. </li> 
     <li> Derecho a eliminación: autoriza al sujeto de datos a que sus datos personales recopilados por los controladores de datos se borren, lo que incluye datos almacenados en Adobe Campaign. </li> 
    </ul> Para obtener más información, consulte la <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/getting-started/privacy/privacy.html">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creative Designer para correo electrónico (Beta)<br /> </td> 
   <td> El nuevo diseñador creativo de Adobe Campaign ofrece una experiencia de creación totalmente integrada en Campaign, lo que permite la creación visual rápida y sencilla de correos electrónicos personalizados y cautivadores sin necesidad de crear una sola línea de código. A través de su potente interfaz de arrastrar y soltar, Creative Designer ayuda a escalar la creación de correos electrónicos tanto si los usuarios comienzan desde una pizarra en blanco como si aprovechan los fragmentos de contenido o las plantillas existentes. <br /> Las funciones clave incluyen las siguientes:<br /> 
    <ul> 
     <li> Diseñe y cree correos electrónicos adaptables y totalmente personalizados con una interfaz de arrastrar y soltar, aumentada por integraciones de Creative Cloud nativos </li> 
     <li> Cree y guarde una plantilla de contenido de correo electrónico, y aproveche las plantillas guardadas para escalar la creación de correo electrónico </li> 
     <li> Crear y guardar fragmentos de contenido (como un encabezado, pie de página, artículo, etc.) para optimizar la creación de contenido y garantizar la coherencia de la marca </li> 
     <li> Cambie fácilmente entre crear en la interfaz de arrastrar y soltar y editar directamente el HTML de un correo electrónico haciendo clic en un botón </li> 
    </ul> Creative Designer para correo electrónico solo está disponible en inglés.<br /> Para obtener más información, consulte la <a href="../../designing/using/designing-content-in-adobe-campaign.md">documentación detallada</a> y mira esto <a href="https://www.youtube.com/watch?time_continue=1&amp;v=5S_6A4fsfms">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregas push multilingües<br /> </td> 
   <td> La misma interfaz multilingüe simple, que ya existe en los canales de correo electrónico y SMS, se ha agregado al canal push para ayudarle a atraer clientes independientemente del idioma que prefieran.<br /> Esta capacidad ofrece una solución escalable y automática para los clientes que administran campañas push en varias regiones y desean dirigirse a los usuarios en su idioma preferido. Permite cargar todas las variantes lingüísticas a través de una hoja de cálculo con plantilla en una sola entrega push con un solo clic. A continuación, Adobe Campaign realiza una segmentación automática basada en las preferencias de idioma de los usuarios, lo que ayuda a reducir las redundancias simplificando los flujos de trabajo y los informes.<br /> Para obtener más información, consulte la <a href="../../channels/using/creating-a-multilingual-push-notification.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso de recursos personalizados en la mensajería transaccional<br /> </td> 
   <td> Además de los campos predeterminados, la mensajería transaccional ahora le permite utilizar recursos personalizados para enriquecer el contenido de sus mensajes.<br /> Por ejemplo:<br /> 
    <ul> 
     <li> Aproveche los campos personalizados como criterios de reconciliación para hacer coincidir un mensaje transaccional con un perfil </li> 
     <li> Aproveche perfiles completos, servicios y datos vinculados para personalizar aún más los mensajes transaccionales </li> 
    </ul> Para obtener más información, consulte la <a href="../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Se ha corregido un problema que impedía exportar más de 5000 registros de una lista.
* Se ha corregido un problema que se producía al exportar datos a archivos llamados con campos de personalización.

_Correos electrónicos, mensajes SMS y correo directo_

* Se ha corregido un problema que provocaba que SMS de varias partes se truncara porque el tamaño de las partes se calculaba en caracteres en lugar de bytes.
* Se ha añadido una opción que permite **[!UICONTROL Delivered]** o **[!UICONTROL Bounces + Errors]** Los KPI se deben actualizar en tiempo real después de realizar el envío. Se vuelven a calcular directamente desde el SR (Informe de estado) recibido del proveedor.
* Se ha corregido un problema con el widget de calendario en el programador de envíos.
* Se ha corregido un problema con la visualización al abrir un destinatario por segunda vez en una entrega enviada.
* Se ha corregido un problema que provocaba un mensaje de error que solicitaba una fecha de inicio, al crear una plantilla de correo electrónico con una fecha de envío retrasada.
* Se ha corregido un problema que podría provocar problemas de procesamiento de imágenes al editar el contenido de una entrega.
* Se ha corregido un problema con las pruebas al duplicar una campaña.
* Se ha corregido un problema que provocaba un mensaje de error al acceder a una plantilla de campaña a través de la barra de navegación, después de añadir una entrega al flujo de trabajo.
* Se ha corregido un problema que podía impedir que el ganador de un correo electrónico de prueba A/B se seleccionara automáticamente, lo que provocaba que el correo electrónico no se enviara. Este comportamiento se podía producir si el envío estaba en **[!UICONTROL retryInProgress]** estado.
* Se ha corregido un problema que podría provocar la aparición de un mensaje de error al volver a abrir los parámetros de un correo electrónico de prueba A/B.

_Audiencias y consultas_

* Se ha corregido un problema que impedía acceder a los datos y configurar consultas para destinatarios duplicados de Adobe Campaign Classic a Standard.
* Se ha corregido un problema que se producía al utilizar un campo de tipo de filtro en el editor de consultas, después de usar el **Recuento** o **Previsualizar** botones.

_Flujos de trabajo_

* El **Factura** El flujo de trabajo de se ha optimizado para mejorar el retraso de preparación de envíos.
* Se ha corregido un problema que impedía que los datos de población se mostraran en una transición saliente al utilizar una actividad de entrega recurrente.
* Se ha corregido un problema que impedía que los registros rechazados se mostraran en una transición después de un **Actualización de datos** actividad.
* Se ha corregido un problema que podría provocar que **deliverabilityUpdate** flujo de trabajo técnico fallido.

_Integraciones_

* Se ha corregido un problema que impedía que los caracteres internacionales se enviaran correctamente a Adobe Analytics.
* Los recursos deberían cargarse más rápido al intentar insertar una imagen de la biblioteca de recursos del Experience Cloud en un mensaje.
* Se ha corregido un problema que podía impedir que se cerrara la ventana de selección de recursos en algunos casos.
* Desde los detalles de una fuente de datos, ahora puede acceder directamente a su flujo de trabajo relacionado para comprobar el estado del flujo de trabajo.
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
   <td> El <strong>Servicios de suscripción</strong> la actividad de flujo de trabajo ahora permite suscribir o cancelar la suscripción de una lista de perfiles a varios servicios. En el flujo de trabajo, importe un archivo que contenga los perfiles y, para cada perfil, el tipo de operación y el servicio. El <strong>Servicios de suscripción</strong> La actividad podrá utilizar esta información y gestionar dinámicamente todas las suscripciones y bajas de perfiles a la vez.<br /> Para obtener más información, consulte la <a href="../../automating/using/subscription-services.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Actividad de enriquecimiento: enriquecer datos basados en transiciones anteriores<br /> </td> 
   <td> El nuevo <span class="uicontrol">Enriquecimiento</span> la actividad de flujo de trabajo permite aprovechar las transiciones de entrada y completar la transición de salida con datos adicionales. Si se dirigen a perfiles, la actividad de enriquecimiento permite enriquecer la información de los perfiles con datos adicionales que no se almacenan en la base de datos (procedentes de un archivo importado, por ejemplo).<br /> Para obtener más información, consulte la <a href="../../automating/using/enrichment.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* La barra superior de la interfaz de Adobe Campaign se ha actualizado con el nuevo menú del Experience Cloud.
* Se ha corregido un problema que impedía el vínculo a **[!UICONTROL Offers]** de mostrarse en la lista desplegable de soluciones.

_Correos electrónicos, mensajes SMS y correo directo_

* Se ha mejorado la fase de preparación de entregas para mejorar el rendimiento.
* Se han corregido varios problemas que podían provocar que los registros de seguimiento se dañaran en algunas situaciones de nicho.
* Se ha corregido un problema con la actualización de la fecha de contacto que se producía cuando la fecha de contacto se cambiaba entre la preparación de la entrega y la confirmación. Ahora, cuando cambie la fecha de contacto después de la preparación, debe volver a preparar la entrega antes de poder confirmar el envío. Consulte la [documentación detallada](../../sending/using/preparing-the-send.md).

_Notificaciones push_

* Se ha corregido un error que impedía que algunos campos de personalización funcionaran en las notificaciones push de iOS.
* Se ha corregido un error que mostraba las tasas de clics y aperturas como 0 % en el panel de notificaciones push.

_Informes_

* Se ha corregido un error que mostraba la lista de informes como vacía en algunos exploradores.
* Se ha corregido un error que se producía en **[!UICONTROL Report sharing]** flujo de trabajo técnico justo antes de alcanzar su límite de caducidad.

_Flujos de trabajo_

* Se ha corregido un problema que impedía que las actividades fueran accesibles después de arrastrarlas y soltarlas.
* Se ha corregido un problema que podría provocar el orden de transiciones de salida de un **[!UICONTROL Segmentation]** actividad para cambiar en algunas situaciones.
* Se ha corregido un error que se producía al leer una audiencia que contenía un campo de tipo de lista desglosada y que se había guardado anteriormente desde un flujo de trabajo
* Se ha corregido un problema que provocaba lo siguiente **[!UICONTROL Request confirmation before sending messages]** opción para permanecer activada incluso después de desmarcar al definir las propiedades de programación de una entrega creada en un flujo de trabajo.
* La eliminación automática de filas duplicadas (cláusula DISTINCT) ahora se puede deshabilitar en **[!UICONTROL Query]** mediante una nueva opción ubicada en la variable **[!UICONTROL Additional data]** pestaña. Se recomienda desactivar esta opción al definir muchos elementos adicionales (más de 100), por motivos de rendimiento.

_Integraciones_

* Se han realizado algunas mejoras en el **[!UICONTROL Data sources]** pantalla de configuración.

_Problemas conocidos_

Se recomienda no utilizar Internet Explorer versión 11 debido a posibles problemas de visualización.

Pueden producirse algunos problemas al utilizar vínculos de ayuda contextual desde la interfaz de Campaign. Se corregirán en la versión 18.3.

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
   <td> Creación de informes para Administración de fatiga<br /> </td> 
   <td> Informes para la administración de la fatiga es un informe dedicado y configurable que muestra el impacto que las reglas de fatiga tienen en las entregas en los canales de correo electrónico, push, SMS y correo directo dentro de un intervalo de fechas especificado antes de la entrega. Con la perspectiva añadida de poder ver rápidamente todas las campañas en conflicto en una sola vista, los especialistas en marketing pueden planificar campañas de marketing según las reglas de fatiga de forma más eficaz y priorizar las comunicaciones.<br /> Para obtener más información, consulte la <a href="../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso compartido de informes<br /> </td> 
   <td> Compartir informes le permite compartir sus informes con los usuarios de Adobe Campaign como datos adjuntos de correo electrónico, incluso de forma recurrente y automatizada. Los usuarios que reciben informes recurrentes pueden cancelar la suscripción a estas comunicaciones mediante un vínculo específico en cada correo electrónico.<br /> Para obtener más información, consulte la <a href="../../reporting/using/reporting-interface.md#share-tab">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Insertar nuevas funciones<br /> </td> 
   <td> Vista previa de mensajes push: revise las notificaciones push en dispositivos iOS y Android desde el editor de contenido para ver exactamente lo que verán los destinatarios antes de probar o ejecutar el envío.<br /> Para obtener más información, consulte la <a href="../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification">documentación detallada</a>.<br /> Contenido disponible: cuando una aplicación no se abre en mucho tiempo, sus datos pueden quedar obsoletos. Esto hace que los datos tengan que actualizarse o reemplazarse en el momento en que un usuario finalmente abre la aplicación, lo que puede causar retrasos en el uso de la aplicación. Con la compatibilidad añadida de Contenido disponible, los usuarios de Adobe Campaign pueden activar su aplicación para actualizar sus datos en segundo plano al enviar una notificación push, lo que permite una mayor coherencia y control sobre la experiencia en la aplicación de un usuario.<br /> Contenido mutable: con la ayuda de Contenido mutable, ahora los usuarios de Adobe Campaign pueden aprovechar las extensiones de su aplicación móvil para modificar aún más el contenido o la presentación de las notificaciones push entrantes enviadas desde Adobe Campaign. Por ejemplo, los usuarios pueden aprovechar el contenido mutable para lo siguiente: <br /> 
    <ul> 
     <li> descifrar datos que se han entregado en formato cifrado </li> 
     <li> descargar imágenes u otros archivos multimedia y añadirlos como archivos adjuntos a una notificación </li> 
     <li> cambiar el texto del cuerpo o del título de una notificación </li> 
     <li> añadir un identificador de subproceso a una notificación </li> 
    </ul> Para obtener más información sobre el contenido disponible y el contenido mutable, consulte la <a href="../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios">documentación detallada</a>.<br /> <strong>Advertencia:</strong> estas actualizaciones de las notificaciones push requieren que los clientes actualicen sus aplicaciones móviles. Consulte <a href="https://experienceleague.adobe.com/docs/campaign-standard/using/administrating/configuring-mobile/push-payload.html">esta nota técnica</a> para obtener más información.<br /> </td> 
  </tr> 
  <tr> 
   <td> Entregas optimizadas para husos horarios<br /> </td> 
   <td> Programe notificaciones recurrentes por correo electrónico, SMS y push para que se entreguen en un día u hora específico en el huso horario de cada destinatario, lo que garantiza que los mensajes se envíen en el momento adecuado sin necesidad de configurar varios envíos. <br /> Para obtener más información, consulte la <a href="../../automating/using/scheduler.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Activación de actividad de señal API<br /> </td> 
   <td> Ahora es posible almacenar en déclencheur una actividad de señal para sus flujos de trabajo directamente desde la API de Adobe Campaign Standard.<br /> Para obtener más información, consulte la <a href="/help/api/using/triggering-a-signal-activity.md">documentación detallada</a> .<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* La búsqueda de perfiles se ha optimizado para mejorar el rendimiento.
* El identificador interno de los grupos de seguridad predeterminados ahora está en modo de solo lectura para los usuarios estándar.

_Correos electrónicos, mensajes SMS y correo directo_

* Se ha corregido un problema de visualización que se producía al insertar emojis en el contenido de los envíos.
* Se ha corregido un problema que permitía al usuario acceder a los registros de envío cuando el envío aún estaba en edición.
* El **[!UICONTROL Scheduler]** La actividad de ahora permite realizar las entregas según el huso horario del destinatario.
* SMS: la opción **[!UICONTROL Store incoming MO]** en la base de datos se ha añadido a cuentas externas. Cuando se selecciona, todos los SMS entrantes se almacenan en la **inSMS** tabla.
* SMS: los servicios ahora están adjuntos a un evento en lugar de a una plantilla transaccional.
* SMS: el tiempo de espera de conexión SMTP predeterminado se ha reducido a 30 segundos.

_Notificaciones push_

* Se ha corregido un error que impedía que se detuvieran los envíos de notificaciones push.
* Se ha añadido una opción en las opciones avanzadas de notificación push para activar la aplicación con una notificación push.
* Se ha añadido un botón de pausa para el vídeo de vista previa de notificaciones push.
* La vista previa de notificaciones push ya está disponible para diferentes dispositivos, como iPhone, Android y tabletas.

_Informes_

* Se ha corregido un error que mostraba tasas superiores al 100 %.
* Se ha corregido un problema que impedía a los usuarios descargar informes en CSV.
* Se ha añadido una nueva **[!UICONTROL Report]** elemento en la página principal.

_Flujos de trabajo_

* Se ha corregido un problema que provocaba un mensaje de error al utilizar datos adicionales en una consulta y agregar alias que contenían espacios. Los caracteres no alfanuméricos ahora se sustituyen por &quot;_&quot;.
* Se ha corregido un problema en el cual el flujo de trabajo técnico que calcula los KPI se podía detener de forma predeterminada en algunos casos.

_Perfiles y audiencias_

* Se ha corregido un error que se producía al agregar varios filtros en una consulta de audiencia.
* Se ha corregido un problema con la visualización que se producía al cambiar la imagen de un perfil.
* Se ha añadido información de objeto que muestra el número de resultado exacto después de contar la población de una consulta.
* Se ha corregido un problema que podía impedir que un usuario seleccionara una audiencia o cerrara la ventana del selector de audiencias.
* Se ha actualizado la lista de funciones disponibles en el editor de expresiones. El **FormatCurrency** y **ConvertCurrency** funciones se han eliminado.
