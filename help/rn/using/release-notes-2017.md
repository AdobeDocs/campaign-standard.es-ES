---
title: Notas de la versión 2017
description: Esta página enumera todas las versiones de 2017 de Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '4572'
ht-degree: 5%

---

# Notas de la versión 2017{#release-notes}

## Versión 17.10: octubre de 2017 {#release-17-10---october-2017}

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
   <td> Administración de fatiga<br /> </td> 
   <td> Administración de fatiga le permite crear reglas de fatiga para administrar la sobrecomunicación con los perfiles. Las reglas de fatiga se crean fácilmente, pero son extremadamente flexibles con capacidades como contar mensajes en varios canales (incluidos mensajes transaccionales), contar solo envíos específicos o aplicar reglas a perfiles específicos.<br /> Para obtener más información, consulte la <a href="../../sending/using/fatigue-rules.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creación de contenido: importar desde una dirección URL <br /> </td> 
   <td> La importación desde una dirección URL le permite recuperar rápidamente el contenido creativo de un sitio web para crear correos electrónicos para cualquier envío. Además, puede optimizar el proceso creativo permitiendo que terceros compartan contenido directamente a través de una dirección URL. El contenido importado se puede utilizar de forma flexible como parte de un único envío o a nivel de plantilla, lo que garantiza la coherencia de la marca para todas las campañas relacionadas, ya sean mensajes transaccionales o basados en flujos de trabajo, e incluye pruebas A/B o multivariable. Importar desde una URL convierte y rastrea automáticamente todos los vínculos para monitorizar el rendimiento del correo electrónico mediante el sistema de informes dinámico.<br /> Para obtener más información, consulte la <a href="../../designing/using/using-existing-content.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Se ha corregido un problema que podía impedir que los archivos comprimidos grandes se descomprimieran correctamente.
* Se ha mejorado la seguridad en la gestión de marcas. La modificación del nombre y la dirección del remitente de una marca ahora está reservada para los administradores técnicos de Adobe.
* Para mejorar la seguridad, el contenido generado por el usuario (imágenes, páginas espejo, páginas de aterrizaje, etc.) ya no se puede servir en el dominio adobe.com. Ahora es obligatorio que utilice su propio dominio para administrar estos recursos, a través del uso de la marca.
* Se ha corregido un problema de la interfaz al mostrar y filtrar actividades de marketing.
* Se ha corregido un problema que impedía que los campos de fecha de suscripción se actualizaran con una llamada de API de REST de POST.

_Correos electrónicos, mensajes SMS y correo directo_

* Se ha corregido un problema que podía impedir que se dirigiera a una audiencia de tipo lista en un mensaje, lo que provocaba que la preparación fallara.
* Se han añadido idiomas que faltan en las funciones de envío de correo electrónico multilingüe.
* La miniatura de contenido, que se muestra en el panel de envío, ahora se actualiza automáticamente cuando el usuario modifica el contenido y lo guarda.
* Se ha corregido un problema relacionado con la zona horaria que impedía abrir una entrega.

_Notificaciones push_

* Al configurar el canal de notificaciones push, la plataforma del proveedor push para iOS debe ser **apns** y para Android **gcm**.
* Se ha corregido un error que impedía que la aplicación móvil de iOS se agregara en la interfaz de Adobe Campaign.
* Las notificaciones push ahora son compatibles con las aplicaciones móviles de Android habilitadas para GCM y FCM.
* Se ha corregido un error que impedía guardar el contenido al duplicar una plantilla de notificación push.
* Ahora es posible crear o actualizar un perfil de la base de datos de Adobe Campaign reconciliando los datos de los usuarios de aplicaciones móviles.
* Adobe Campaign ahora prioriza el procesamiento de las notificaciones push transaccionales sobre las notificaciones push estándar.

_Informes_

* Se ha corregido un problema que impedía que los porcentajes de clics interactivos se mostraran en el contenido del correo electrónico.
* Se ha corregido un problema con la métrica de lista de bloqueados de la que se contaba como una devolución grave en lugar de una devolución.
* Se ha corregido un problema que provocaba que se mostraran recuentos negativos en los datos de resumen.
* Se ha corregido un problema que contaba perfiles en el segmento de edad incorrecto.
* Las fórmulas de cálculo de devoluciones suaves y duras han cambiado.

_Flujos de trabajo_

* Se ha corregido un problema en la actividad **[!UICONTROL Load file]** que podía provocar errores después de agregar y quitar manualmente columnas en la actividad.
* El flujo de trabajo técnico de **[!UICONTROL deliverabilityUpdate]** ahora está programado para ejecutarse a las 02:00, hora del servidor.
* Se ha corregido un problema de seguridad que permitía realizar una exportación de lista sin la función de exportación.
* Se corrigió un problema con la actividad **[!UICONTROL Reconciliation]**.
* Se corrigió un problema con el uso de caracteres comodín en la actividad **[!UICONTROL File Transfer]**.

_Perfiles y audiencias_

* Se ha corregido un problema que podía impedir que una condición de una consulta se tuviera en cuenta correctamente en algunos casos específicos, lo que producía resultados erróneos.
* Se ha corregido un problema que podía impedir que se accediera a los perfiles si estaban segmentados en un mensaje preparado, pero nunca enviado y caducado.

_Integraciones_

* Se ha corregido un problema que podía impedir que algunas fuentes de datos creadas para Déclencheur se mostraran y seleccionaran correctamente.

_Recursos personalizados_

* Se ha corregido un problema que se producía en las pantallas de lista en las que las filas de recursos personalizadas se podían mostrar sin ningún dato.
* Se ha corregido un problema que impedía que los campos de tipo booleano con valor &quot;False&quot; se mostraran en los recursos personalizados.

## Versión 17.9: septiembre de 2017 {#release-17-9---september-2017}

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
   <td> Biblioteca de plantillas de correo electrónico<br /> </td> 
   <td> Presentamos dieciocho nuevas plantillas adaptables diseñadas en dos hermosos temas: Astro y Feather. Estas plantillas personalizables no dependen del sector y están listas para utilizarse inmediatamente. Las plantillas incluyen contenido para una variedad de casos de uso a fin de que sus campañas de marketing por correo electrónico se diseñen y entreguen de forma más rápida, eficaz y hermosa que nunca.<br /> Para obtener más información, consulte la <a href="../../designing/using/using-reusable-content.md#content-templates">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Informes dinámicos con datos de perfil <br /> </td> 
   <td> El sistema de informes dinámico proporciona informes comerciales totalmente personalizables y en tiempo real. Con esta versión, una potente mejora de la creación de informes dinámicos agrega acceso a los datos de perfil, lo que permite el análisis demográfico por dimensiones de perfil como sexo, ciudad, código postal y edad, además de datos funcionales de campaña de correo electrónico como aperturas y clics. Con la misma interfaz de arrastrar y soltar fácil de usar, determinar el rendimiento de su campaña de correo electrónico en relación con los segmentos de clientes más importantes es más fácil que nunca.<br /> Para obtener más información, consulte la <a href="../../reporting/using/about-dynamic-reports.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Suscripción masiva con origen y fecha<br /> </td> 
   <td> Con esta mejora de la suscripción masiva, ahora puede almacenar la información de suscripción (origen y fecha) directamente en la base de datos de Adobe Campaign Standard a través de la actividad Servicios de suscripción en un flujo de trabajo.<br /> Para obtener más información, consulte la <a href="../../automating/using/subscription-services.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Algunos clientes deben poder aprovechar un ID proveniente de Adobe Campaign Standard, ya que no administran una clave única para identificar sus propios registros. Este identificador (**ACS ID**) se puede exportar y utilizar como clave de reconciliación al actualizar los datos. Para obtener más información, consulte la [documentación detallada](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* El protocolo FTP está en desuso. Ahora debe utilizar SFTP en su lugar. Para no bloquear las implementaciones existentes, las configuraciones existentes en FTP seguirán funcionando como antes, pero la opción no se mostrará para nuevas actividades.

_Correos electrónicos, mensajes SMS y correo directo_

* Ahora es posible crear nuevos criterios de alerta para utilizarlos en las notificaciones de alerta de entrega. Para obtener más información, consulte la [documentación detallada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Las notificaciones de alerta de envío tienen un nuevo diseño y la experiencia del usuario del panel de alertas de envío se ha mejorado.
* Ahora, cuando se deshabilita una cuenta externa de enrutamiento, se muestra una advertencia en los envíos afectados (correo electrónico, SMS y push) y el botón **Vista previa** está oculto en estos envíos.
* Se ha corregido un problema que provocaba un error en la previsualización de una prueba A/B en el contenido del correo electrónico cuando el texto dinámico estaba habilitado en la línea de asunto.

_Mensajes transaccionales_

* Ahora es posible definir cuándo desea enviar un mensaje de seguimiento, por ejemplo, 3 días después de enviar un mensaje transaccional. Para obtener más información, consulte la [documentación detallada](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Ahora es posible definir la fecha a partir de la cual se deben enviar los mensajes transaccionales vinculados a un evento.
* Se ha corregido un problema que provocaba un error de SQL al ejecutar un flujo de trabajo que contenía un mensaje de seguimiento después de eliminar perfiles vinculados a eventos recibidos y procesados.
* Se ha corregido un error que impedía eliminar un perfil vinculado a un evento.
* Se ha corregido un problema que podía impedir que funcionara la redirección de los vínculos rastreados.
* Se ha corregido un problema que impedía deshabilitar el seguimiento de ciertos vínculos en un mensaje de correo electrónico o SMS.

_Informes_

* Se ha mejorado el informe **Clics activos**. Además, ahora es posible mostrar clics activos según cada contenido condicional definido en una entrega y mostrar clics activos para cada ejecución de envíos recurrentes o mensajes transaccionales. Para obtener más información, consulte la [documentación detallada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Se ha corregido un problema que impedía que la métrica de cuarentena recuperara los datos correctos.
* Se ha añadido un nuevo lapso de tiempo preestablecido al widget de calendario.
* Las [métricas del informe dinámico](../../reporting/using/indicator-calculation.md) y los KPI de [campañas](../../sending/using/confirming-the-send.md) (mostrados en el panel de mensajes enviados) se han alineado para lograr una mayor coherencia.
* Se ha corregido un problema que podría provocar que la canalización se bloqueara en debian 7.

_Flujos de trabajo_

* Se ha corregido un problema que podía impedir que funcionara la retención de archivos importada.

_Integraciones_

* Ahora se admiten eVars y eventos para la integración de Analytics y Campaign.
* Al enviar un correo electrónico con el contenido del carro de compras abandonado, el parámetro de carga útil para los elementos eliminados del carro de compras ahora es opcional.

_Perfiles y audiencias_

* Adobe Campaign ahora proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación. Para obtener más información, consulte la [documentación detallada](../../audiences/using/active-profiles.md).
* Se ha corregido un problema que impedía que los perfiles se suscribieran a un servicio al usar la API de perfiles y servicios.

## Versión 17.7: julio de 2017 {#release-17-7---july-2017}

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
   <td> Envíos multilingües de correo electrónico y SMS<br /> </td> 
   <td> Defina y ejecute envíos multilingües de correos electrónicos y SMS a través de un único envío basado en el idioma preferido de los clientes segmentados automáticamente. Informe del rendimiento de cada envío en función del idioma y los niveles individuales.<br /> Cada vez más empresas se enfrentan al desafío de ofrecer contenido en varios idiomas a medida que crecen en casa y en el extranjero. De este modo, la racionalización de la entrega de mensajes localizados es una parte clave de una estrategia eficaz de comunicación con los clientes para empresas multinacionales, empresas de países con varios idiomas y empresas que desean personalizar aún más su contenido en el nivel lingüístico independientemente del lugar en el que residan los clientes. Para obtener más información, consulte la <a href="../../channels/using/creating-a-multilingual-email.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones de Adobe Campaign<br /> </td> 
   <td> Reciba notificaciones sobre actividades importantes del sistema directamente en Adobe Campaign Standard. Se le notificará, por ejemplo, sobre el progreso de sus envíos en curso o cuando un flujo de trabajo presente un error.<br /> Las notificaciones en tiempo real mantienen informadas a las partes interesadas relevantes y proporcionan a los usuarios la capacidad de actuar de forma inmediata y directa en las notificaciones de actividades desde la aplicación. El resultado para los equipos es una agilidad avanzada, eficiencia y una ejecución más fluida de las campañas. Para obtener más información, consulte la <a href="../../administration/using/sending-internal-notifications.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alerta de envío<br /> </td> 
   <td> Además de ver las notificaciones directamente en Adobe Campaign Standard, Adobe Campaign ahora también proporciona un sistema de alertas por correo electrónico para almacenar en déclencheur las alertas por correo electrónico de los usuarios o las partes interesadas externas de las actividades importantes del sistema. Cree, administre y reciba alertas y paneles personalizables para realizar un seguimiento de los éxitos o errores de entrega.<br /> Las alertas de entrega de Adobe Campaign aumentan la eficacia al mantener a todos los usuarios de Adobe Campaign implicados en una empresa informados automáticamente sobre el estado de ejecución de la entrega por correo electrónico y panel. Para obtener más información, consulte la <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID declarado cifrado en orígenes de datos <br /> </td> 
   <td> Envíe déclencheur de correo electrónico y SMS sin necesidad de un perfil existente en Campaign mediante el uso de información de contacto cifrada (dirección de correo electrónico o número de teléfono) como ID declarado. Dado que los ID declarados cifrados se pueden descodificar mediante Adobe Campaign Standard, Campaign ahora puede crear nuevos perfiles comercializables al recibir audiencias de otras soluciones de Experience Cloud que contengan contactos anteriormente desconocidos.<br /> Clientes objetivo y clientes potenciales desconocidos en tiempo real a través de correo electrónico y SMS para mejorar la lealtad en su base de clientes existente y adquirir nuevos clientes, respectivamente. Saque el máximo partido a los datos de cookies de origen (de Adobe Audience Manager*) una vez que los posibles clientes se autentifiquen y aprovechen esas perspectivas en Adobe Campaign. <br /> *Se requiere Adobe Audience Manager. Para obtener más información, consulte la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso compartido de KPI de Campaign a Analytics<br /> </td> 
   <td> Comparta datos de campaña con Adobe Analytics para medir las métricas de marketing por correo electrónico de Campaign junto con otros esfuerzos de marketing y publicidad mediante la conversión y la unificación del comportamiento previo y posterior al clic.<br />: efectúe un seguimiento directo del rendimiento general y descubra las sinergias con programas externos en Analytics. Vuelva a aplicar el aprendizaje desde esta vista consolidada a sus campañas; en última instancia, mejore las tasas de apertura, clics y conversión, lo que aumenta los ingresos y el rendimiento general de la campaña. Se requiere Adobe Analytics <br />. Para obtener más información, consulte la <a href="../../integrating/using/about-campaign-analytics-integration.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal De Correo Postal - Devolver Al Remitente<br /> </td> 
   <td> Ahora se admiten los intercambios de archivos planos con proveedores de correo directo que incorporan información de devolución al remitente. Esta mejora del canal de correo postal permite excluir las direcciones postales correspondientes de futuras comunicaciones.<br />: esto permite notificar a los especialistas en marketing una dirección incorrecta e interactuar con el cliente a través de otros canales o animarlos a actualizar su dirección postal. Esto también reduce el número de dólares de marketing malgastados, ya que los especialistas en marketing evitan enviar correos a direcciones incorrectas. <br /> el correo postal está disponible como canal de complemento. Para obtener más información, consulte la <a href="../../channels/using/return-to-sender.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_General_

* Se ha corregido un problema que permitía que cualquier usuario exportara listas. Ahora solo se permite el acceso a los usuarios con el rol **[!UICONTROL Export]**.

_Correos electrónicos, mensajes SMS y correo directo_

* Se ha corregido un problema con el flujo de trabajo **updateDeliveryExecInfo** que establecía el indicador **To deliver** en 0 para los envíos SMS.
* En los **parámetros avanzados** de las propiedades de la plantilla de envío, la lista desplegable **Enrutamiento** ahora solo muestra las cuentas externas correspondientes al tipo de mensaje de plantilla. Por ejemplo, una plantilla de envíos de correo electrónico solo muestra las cuentas externas de correo electrónico.
* Se ha corregido un problema con el formato de correo electrónico preferido de **[!UICONTROL Text]** definido para los perfiles de prueba.
* Se ha corregido un problema que provocaba un error de Javascript en al seleccionar la zona horaria predeterminada en la pantalla de definición de programación de una entrega.
* Se ha corregido un problema que impedía que las trampas aparecieran en los registros de envío.
* En la pantalla de selección de plantillas del asistente de creación de entregas, las plantillas de seguimiento y prueba A/B ahora están ocultas de forma predeterminada. Para obtener más información, consulte [documentación detallada](../../channels/using/creating-an-email.md).
* Se ha corregido un problema que permitía que cualquier usuario enviara envíos. Ahora solo se permite el acceso a los usuarios con el rol **[!UICONTROL Start deliveries]**. Para obtener más información, consulte [documentación detallada](../../sending/using/confirming-the-send.md).

_Notificaciones push_

* Se ha corregido un problema con la dirección URL **Extremo de seguimiento de campaña** que impedía la creación de informes.
* Se ha corregido un problema que impedía que el título de la notificación push se mostrara en los dispositivos Android.
* Se ha corregido un problema que impedía que se mostrara la notificación push en dispositivos iOS cuando la notificación push solo contenía un título (y nada en el cuerpo del mensaje).
* Se ha corregido un problema que obligaba a rastrear las direcciones URL de archivos adjuntos de medios en una entrega, lo que impedía que los vídeos e imágenes se incrustaran en la entrega. El seguimiento de direcciones URL del tipo mediaAttachmentURL ahora está desactivado de forma predeterminada para las notificaciones push.

_Informes_

* Se corrigió un problema en el cual los valores aparecían diferentes entre los gráficos y la tabla.
* Se ha corregido un problema que mostraba valores de notificaciones push como valores de correo electrónico.
* Se ha corregido un problema que mostraba valores como desconocidos cuando se creaba una entrega fuera de una campaña.
* Se ha corregido un problema que mostraba los datos de informes de SMS como datos de aplicaciones móviles.

_Flujos de trabajo_

* Ahora puede filtrar los registros de flujo de trabajo (período de tiempo y búsqueda de texto). Para obtener más información, consulte [documentación detallada](../../automating/using/monitoring-workflow-execution.md).
* Ahora hay disponible una opción en los envíos del flujo de trabajo para desactivar la confirmación antes del envío.
* Se ha corregido un problema que impedía establecer una transición saliente en el asistente de creación de envíos recurrentes.
* Se ha corregido un problema que se producía al utilizar una actividad de consulta de flujo de trabajo basada en un campo de recurso personalizado con una enumeración que tenía muchos valores

## Versión 17.5: mayo de 2017 {#release-17-5---may-2017}

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
   <td> Correo postal<br /> </td> 
   <td> Rompa la barrera digital y conéctese al mundo físico con el primer canal sin conexión de Adobe Campaign Standard, el correo postal. Esta función le permite personalizar y generar el archivo requerido por los proveedores de correo postal como parte de sus campañas en canales múltiples. Aproveche el correo directo para volver a atraer a los clientes o mejorar la experiencia del cliente con un punto de contacto táctil convincente que lleve a los clientes a su aplicación, sitio web o tienda.<br /> Para obtener más información, consulte la <a href="../../channels/using/about-direct-mail.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Correo electrónico CCO<br /> </td> 
   <td> Email BCC permite guardar correos electrónicos únicos enviados a destinatarios individuales, lo que permite a la marca archivar dichos mensajes. Al añadir una dirección de correo electrónico CCO a todos los correos electrónicos, los clientes de Adobe Campaign Standard pueden mantener una copia exacta de cada correo electrónico con esta función. Se trata de un requisito legal común para el sector de los servicios financieros y resulta útil para ayudar a los centros de servicio al cliente a resolver conflictos en tiempo real.<br /> Para obtener más información, consulte la <a href="../../sending/using/archiving.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Actualizaciones de la interfaz_

* En la barra superior, el vínculo **[!UICONTROL Timeline]** se ha eliminado y reemplazado por un vínculo a **[!UICONTROL Programs & Campaigns]**

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema que mostraba un color incorrecto para el estado de entrega **[!UICONTROL Retry in progress]**. El color era gris en lugar de azul.

_Flujos de trabajo_

* Se corrigió un problema que se producía al cambiar la acción para que se realice en una actividad de **[!UICONTROL Transfer file]**.

_Informes_

* Se han cambiado los cálculos del indicador **[!UICONTROL Spam]** y **[!UICONTROL Spam rate]**.
* Se mejoraron las métricas **[!UICONTROL Bounce]** para obtener un resultado más preciso.

_Notificaciones push_

* Se ha corregido un problema que impedía hacer clic en un evento push en el historial de marketing de un perfil.
* Se ha mejorado el uso de notificaciones push en flujos de trabajo.

## Versión 17.4: abril de 2017 {#release-17-4---april-2017}

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
   <td> Funciones mejoradas de edición de imágenes con Creative SDK<br /> </td> 
   <td> Ahora tiene acceso a un conjunto completo de funciones con el SDK de Creative para mejorar sus imágenes directamente en el editor de contenido al editar correos electrónicos o páginas de aterrizaje.<br /> Esta característica no requiere la adquisición de soluciones de Creative Cloud adicionales.<br /> Para obtener más información, consulte la <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push transaccionales<br /> </td> 
   <td> El canal de aplicaciones móviles se ha añadido a las funciones de mensajería transaccional de Adobe Campaign. Ahora se admiten tres canales para los mensajes transaccionales: correo electrónico, SMS y notificaciones push.<br /> Para obtener más información, consulte la <a href="../../channels/using/transactional-push-notifications.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push recurrentes<br /> </td> 
   <td> Ahora puede configurar notificaciones push recurrentes en un flujo de trabajo. Puede utilizar notificaciones push recurrentes en situaciones en las que los clientes esperan actualizaciones periódicas, como recordatorios semanales para ver contenido nuevo o promociones.<br /> Para obtener más información, consulte la <a href="../../automating/using/push-notification-delivery.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Conector Amazon Simple Storage Service (S3) <br /> </td> 
   <td> El conector Amazon Simple Storage Service (S3) ahora se puede utilizar para importar o exportar datos a Adobe Campaign. Se puede configurar en una actividad de flujo de trabajo. La configuración se realiza en una cuenta externa.<br /> Para obtener más información, consulte la <a href="../../administration/using/external-accounts.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Dreamweaver activa<br /> </td> 
   <td> La integración entre Adobe Campaign y Dreamweaver ya está activa. Ahora funciona con la última versión oficial publicada de Dreamweaver (17.0.2).<br /> Esto requiere la instalación de la extensión Adobe Campaign Integration. Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=es">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Se ha corregido un problema de consumo de memoria.

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema en el cual el contenido no se podía sincronizar correctamente con los cambios más recientes al obtener una vista previa de un mensaje.
* Se ha corregido un problema que impedía que se creara o eliminara una regla de procesamiento de correo electrónico MX o de dominio.
* Se ha corregido un problema que podía impedir que se enviaran correos electrónicos con varios alias.
* Se ha corregido un problema que impedía que los registros de envío de captura aparecieran en los registros de envío del envío.
* Se ha corregido un problema que provocaba un error al mostrar las direcciones URL rastreadas de una entrega sin una dirección URL en su contenido.
* Se ha corregido un problema que impedía que los atributos de tamaño de una imagen se aplicaran correctamente en el mensaje enviado.

_Mensajes transaccionales_

* El campo rtEventHistoId ya no se expone como campo de personalización en una plantilla de mensaje transaccional.

_Páginas de aterrizaje_

* Hemos optimizado el filtro **[!UICONTROL by email]** utilizado en las páginas de aterrizaje para reconciliar nuevos suscriptores con perfiles de base de datos.
* Se ha corregido un problema que mostraba entradas de texto libre en lugar de casillas de verificación al utilizar campos booleanos en una configuración de formulario.
* Se ha corregido un problema que impedía que se generaran miniaturas de página de aterrizaje.

_Flujos de trabajo_

* Se corrigió un error de visualización al editar una actividad **[!UICONTROL End]** o **[!UICONTROL External Signal]** (solo en Safari).
* Se mejoró el mensaje de error que se mostraba al editar una actividad **[!UICONTROL Read Audience]** que contenía una audiencia errónea.
* Se ha corregido un problema que podría provocar un error de SQL al ejecutar una actividad de suscripción.

_Integraciones_

* Datos de puntos de interés: se ha corregido un error que se producía al contar los suscriptores de ubicación.

_Audiencias y consultas_

* Se ha corregido un problema que impedía que se usaran agregados de suma y promedio en una colección en el editor de consultas.
* Se ha corregido un problema que podía impedir que el editor de consultas se volviera a cargar después de cambiar el recurso del filtro.

_Informes_

* Se ha corregido un problema que impedía que las métricas de tasa de apertura se calcularan correctamente al seleccionar varias filas en una tabla.
* Se ha corregido un error que solo mostraba métricas como valores enteros. Ahora las métricas se pueden mostrar con decimales.

_Notificaciones push_

* Se ha corregido un problema por el cual no se mostraba un mensaje de error al crear una aplicación de Android vinculada a una aplicación móvil que no se había podido crear en MCPNS.
* Se ha corregido un problema que permitía al usuario agregar sonidos a una notificación silenciosa.

## Versión 17.2: marzo de 2017 {#release-17-2---march-2017}

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
   <td> Informes dinámicos<br /> </td> 
   <td> El sistema de informes dinámico proporciona una nueva generación de informes comerciales totalmente personalizables y en tiempo real. Basada en gráficos y tablas dinámicas visuales, esta función le permite arrastrar y soltar variables y dimensiones para analizar la eficacia y efectividad de sus campañas de marketing. Los informes dinámicos también le permiten crear sus propios informes empresariales desde cero y guardarlos para usarlos más adelante.<br /> Para obtener más información, consulte la <a href="../../reporting/using/about-dynamic-reports.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Dreamweaver (Labs)<br /> </td> 
   <td> Con la integración de Adobe Campaign y Dreamweaver, ahora tiene un proceso integrado para crear campañas de correo electrónico con soluciones de Adobe.<br /> Puede editar correos electrónicos de Adobe Campaign en Dreamweaver y hacer que el contenido se sincronice perfectamente entre ambas soluciones.<br /> En la versión inicial, la integración está disponible como característica de "Labs" y solo funciona con Beta de la versión preliminar de Dreamweaver. Si desea activarlo, póngase en contacto con AC-DW-integration@adobe.com.<br /> Para obtener más información, consulte este <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=es">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Optimización del tiempo de envío manual<br /> </td> 
   <td> Ahora puede definir manualmente una hora de envío personalizada por destinatario: en el nivel de entrega o mediante un flujo de trabajo. <br /> Hay dos opciones nuevas disponibles: <br /> 
    <ul> 
     <li> Todos los destinatarios reciben el mensaje teniendo en cuenta su huso horario. </li> 
     <li> Cada destinatario recibe el mensaje en una fecha y hora calculadas definidas por una fórmula. </li> 
    </ul> Para obtener más información, consulte la <a href="../../sending/using/optimizing-the-sending-time.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push Nuevas funciones<br /> </td> 
   <td> El canal de notificaciones push se ha mejorado con varias funciones nuevas: <br /> 
    <ul> 
     <li> Nueva interfaz de creación </li> 
     <li> Notificaciones silenciosas </li> 
     <li> Inserción interactiva </li> 
     <li> Compatibilidad con contenido enriquecido </li> 
     <li> Calculadora de tamaño de carga útil </li> 
    </ul> Para obtener más información, consulte la <a href="../../channels/using/about-push-notifications.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: nueva actividad de señal <br /> </td> 
   <td> Almacene en déclencheur un flujo de trabajo de otro flujo de trabajo con la nueva actividad <span class="uicontrol">Signal</span>.<br /> Con la capacidad de iniciar un flujo de trabajo desde otro, ahora puede admitir recorridos de clientes más complejos. Puede supervisar mejor los recorridos de los clientes y reaccionar en caso de que haya problemas.<br /> Se han actualizado varias actividades de flujo de trabajo:<br /> 
    <ul> 
     <li> Actividad <span class="uicontrol">End</span>: una nueva pestaña le permite especificar un flujo de trabajo para almacenar en déclencheur después de ejecutar esta actividad. </li> 
     <li> Actividad <span class="uicontrol">Actualizar datos</span>: use la nueva transición saliente vacía para agregar una actividad <strong>End</strong> que ponga en déclencheur otro flujo de trabajo. Las transiciones salientes vacías no transmiten datos ni consumen espacio innecesario en el sistema </li> 
    </ul> Para obtener más información, consulte la <a href="../../automating/using/external-signal.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: nueva actividad de lectura de audiencia<br /> </td> 
   <td> Inicie el proceso de segmentación con una audiencia existente que pueda seleccionar y refinar fácilmente en una actividad.<br /> Para obtener más información, consulte la <a href="../../automating/using/read-audience.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Datos de puntos de interés<br /> </td> 
   <td> Los datos de puntos de interés integran Adobe Campaign con Adobe Analytics para dispositivos móviles. Una marca puede recopilar datos de las ubicaciones móviles de los usuarios, denominados <strong>puntos de interés</strong>, cuando estos abren la aplicación de la marca. Esto permite a la marca aprovechar los flujos de trabajo de Adobe Campaign para enviar mensajes personalizados según la ubicación de los usuarios. Este canal aprovecha el SDK del servicio principal de Mobile.<br /> Tenga en cuenta que el uso de esta función requiere Analytics para móviles, que es una solución de pago.<br /> Para obtener más información, consulte la <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de REST<br /> </td> 
   <td> Los recursos vinculados en cualquier nivel a los recursos de perfiles o servicios ahora están disponibles en la API.<br /> Para obtener más información, consulte la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_General_

* Ahora es posible añadir datos de perfil al exportar registros de envío.

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema que hacía que la opción **[!UICONTROL Request confirmation before sending messages]** permaneciera seleccionada incluso después de desmarcarla y guardar la entrega.
* Se ha corregido un problema que podía impedir la cancelación de la publicación de correos electrónicos transaccionales.
* Se ha corregido un problema en el cual el contenido no se podía sincronizar correctamente con los cambios más recientes antes de previsualizar una entrega.

_Páginas de aterrizaje_

* Se ha corregido un error que impedía que un usuario editara al hacer clic en el contenido de una página de aterrizaje.

_Flujos de trabajo_

* Se ha corregido un problema que podía impedir la lectura del contenido de la transición de rechazo de una actividad **[!UICONTROL Load file]**.
* Se ha corregido un problema que impedía que las columnas intercambiadas se tuvieran en cuenta correctamente al configurar una actividad **[!UICONTROL Load file]**.

## Versión 17.1: enero de 2017 {#release-17-1---january-2017}

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
   <td> Exportación de registro para informes externos <br /> </td> 
   <td> Exporte registros, como registros de envío y seguimiento, para procesarlos en sus herramientas de sistema de informes o BI preferidas. Puede utilizar flujos de trabajo simples con consultas incrementales para automatizar las exportaciones regulares de nuevos registros.<br /> Además de la disponibilidad de los recursos de registro del selector de recursos, se realizaron mejoras en las actividades <a href="../../automating/using/incremental-query.md">Incremental query</a> y <a href="../../automating/using/extract-file.md">Extraer archivo</a>:<br /> 
    <ul> 
     <li> <span class="uicontrol">La consulta incremental</span> ahora le permite usar un campo de fecha para recuperar datos nuevos o actualizados. Anteriormente, todos los resultados de ejecuciones anteriores se excluían automáticamente, incluso si se habían actualizado desde la última ejecución. </li> 
     <li> <span class="uicontrol">Extraer archivo</span> ahora puede exportar etiquetas para valores de enumeración en lugar de identificadores. </li> 
    </ul> Estas actividades están disponibles para los administradores con acceso a todas las unidades geográficas y de organización.<br /> Para obtener más información sobre la exportación de registros, consulte la <a href="../../automating/using/exporting-logs.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Funciones de marketing para mensajes transaccionales<br /> </td> 
   <td> Los especialistas en marketing ahora pueden enviar mensajes transaccionales basados en perfiles de marketing de clientes. Esto les permite:<br /> 
    <ul> 
     <li> Aplicar reglas de tipología de marketing como <span class="uicontrol">Dirección en la lista de bloqueados de la</span> </li> 
     <li> Incluir vínculos de baja en los mensajes. </li> 
     <li> Añadir mensajes transaccionales al sistema de informes de envío global. </li> 
     <li> Aprovechar mensajes transaccionales en el recorrido del cliente. </li> 
    </ul> Para obtener más información, consulte la <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de mensajería transaccional <br /> </td> 
   <td> La API de mensajería transaccional ya está disponible, lo que facilita su uso y supervisión:<br /> 
    <ul> 
     <li> Puede beneficiarse de las funcionalidades de supervisión y creación de informes de la plataforma Adobe Developer. </li> 
     <li> La autenticación ahora se realiza mediante la autenticación basada en tokens de adobe.io en lugar de la inclusión en la lista de permitidos IP, lo que simplifica el proceso de seguridad. </li> 
     <li> Todas las API están ahora integradas en una sola plataforma, lo que facilita más que nunca la incorporación de funcionalidades de mensajería transaccional a su integración si ya admite la API de perfil y servicios. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_General_

* Las opciones **[!UICONTROL Access authorization]** han vuelto a las propiedades de la página de aterrizaje.
* Se ha corregido un problema que podría haber provocado que se procesara una imagen antigua en lugar de la imagen correcta. Esto ocurría si la imagen de origen se había actualizado en la definición de contenido de una entrega o página de aterrizaje.
* Se ha corregido un problema que impedía a los usuarios editar ciertos campos en una cuenta externa SFTP existente.
* Se han corregido varios problemas de IU. Por ejemplo, ahora los usuarios pueden editar atributos de perfil y guardar modificaciones sin tener problemas con la interfaz de usuario.

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema relativo a las plantillas de envío con contenido de HTML que contenía un

_Notificaciones push_

* Se ha corregido un problema que podía haber impedido el postback de una aplicación al servidor de Adobe Campaign.
* Se ha corregido un problema que podía haber impedido que **[!UICONTROL Play a sound]** y **[!UICONTROL Custom fields]** se tuvieran en cuenta para Android.
* Se ha corregido un problema que podría haber provocado que se agregara un carácter de escape adicional a los caracteres Unicode utilizados para Emojis.
* Cuando se añade el token de registro de un suscriptor a la lista de bloqueados de, el estado correspondiente ahora se actualiza inmediatamente en la lista de la aplicación de suscriptores en Adobe Campaign.

_Flujos de trabajo_

* Se ha corregido un problema que podía haber impedido la previsualización de consultas en recursos de evento (p. ej. rtEvent).
* El archivo rechazado generado por una actividad **[!UICONTROL Load file]** ahora se puede recuperar en su transición saliente y procesar en la siguiente actividad. Por ejemplo, cargue el archivo rechazado a través de un servidor SFTP usando **[!UICONTROL Transfer file]**
* Se ha corregido un problema que podía impedir que un usuario limitara la población de un segmento si se seleccionaba **[!UICONTROL Temporary resource]** en la pestaña **[!UICONTROL General]** de **[!UICONTROL Segmentation]**
* **[!UICONTROL Scheduler]** actividades ya no pueden configurarse para almacenar en déclencheur un flujo de trabajo más de una vez cada 10 minutos.
* Se ha corregido un problema que podía impedir que **[!UICONTROL Use common columns]** funcionara correctamente en una actividad **[!UICONTROL Union]**.

_Integraciones_

* Se ha corregido un problema que podría haber provocado un error al implementar un déclencheur de eventos en Adobe Campaign. Este error se producía cuando se habían agregado los metadatos &quot;Probabilidad de retorno en 30 días&quot; al déclencheur de abandono en Adobe Marketing Cloud.
* Se ha corregido un problema que podía hacer que el flujo de trabajo técnico borrara el campo Dimension de destinatario al importar audiencias desde el servicio principal Personas. Las consultas posteriores no pudieron recuperar las audiencias importadas.
* Se ha corregido un problema que podría haber causado un error en la actividad **[!UICONTROL Save audience]** de un flujo de trabajo al marcar la opción **[!UICONTROL Share in Adobe Marketing Cloud]**.
