---
title: Notas de revisión 2017
seo-title: Notas de revisión 2017
description: Notas de revisión 2017
seo-description: Esta página enumera todas las versiones de Adobe Campaign Standard 2017.
page-status-flag: no activado nunca
uuid: d 73 f 8186-e 309-441 b -969 d -71 d 0 a 1 c 33 cf 4
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: versiones estándar de campaña
discoiquuid: 1 cfd 9 b 3 b -9 b 3 e -4587-9 c 46-b 6 fb 02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Release Notes 2017{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard en 2017?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

View the latest [documentation updates](../../rn/using/documentation-updates.md) for Adobe Campaign Standard. If you're looking for a newer release, consult this [page](../../rn/using/release-notes.md).

## Release 17.10 - October 2017 {#release-17-10---october-2017}

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
   <td> Fatigue Management<br /> </td> 
   <td> Administración de fatiga permite crear reglas de fatiga para administrar la comunicación excesiva con perfiles. Las reglas de fatiga se crean fácilmente, pero son extremadamente flexibles con capacidades como contar mensajes en varios canales (incluidos los mensajes transaccionales), contar envíos específicos o aplicar reglas a perfiles específicos.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/fatigue-rules.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Content creation: Import from a URL<br /> </td> 
   <td> Importar desde una URL permite recuperar rápidamente el contenido creativo de un sitio web para crear correos electrónicos para cualquier entrega. Además, puede optimizar el proceso creativo permitiendo a terceros compartir contenido directamente mediante una URL. El contenido importado se puede utilizar de forma flexible como parte de una entrega única o a nivel de plantilla, garantizando la coherencia de la marca para todas las campañas relacionadas, tanto si se basan en flujos de trabajo como si son mensajes transaccionales, e incluyen pruebas A/B o multivariadas. Importar desde una dirección URL convierte y rastrea automáticamente todos los vínculos para supervisar el rendimiento del correo electrónico a través de informes dinámicos.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/importing-content-from-a-url.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches}

#### Platform {#platform}

* Se ha corregido un problema que podía impedir que los archivos comprimidos grandes se descomprimen correctamente.
* Se ha mejorado la seguridad en la administración de marca. La modificación del nombre de una marca y la dirección remitente ahora está reservada para los administradores técnicos de Adobe.
* Para mejorar la seguridad, el contenido generado por el usuario (imágenes, páginas reflejadas, páginas de aterrizaje, etc.) no se puede proporcionar con el dominio adobe.com. Ahora es obligatorio utilizar su propio dominio para gestionar estos recursos mediante el uso de la marca.
* Se ha corregido un problema de interfaz al mostrar y filtrar actividades de marketing.
* Se ha corregido un problema que impedía que los campos de fecha de suscripción se actualizasen con una llamada de POST REST API.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail}

* Se ha corregido un problema que impedía la segmentación de una audiencia de tipo de lista en un mensaje, lo que provocaba errores en la preparación.
* Se han añadido idiomas en las capacidades multilingües de envío de correo electrónico.
* La miniatura de contenido, mostrada en el panel de entrega, se actualiza automáticamente cuando el usuario modifica el contenido y guarda el contenido.
* Se ha corregido un problema relacionado con la zona horaria que impedía que se abriera una entrega.

#### Push notifications {#push-notifications}

* When configuring the push notification channel, the push provider platform for iOS should be **apns** and for Android **gcm**.
* Se ha corregido un error que impedía que la aplicación móvil de iOS se agregara en la interfaz de Adobe Campaign.
* Las notificaciones push ahora se admiten en aplicaciones móviles Android adaptadas para GCM y FCM.
* Se ha corregido un error que impedía que se guarde contenido al duplicar una plantilla de notificación Push.
* Ahora es posible crear o actualizar un perfil desde la base de datos de Adobe Campaign, reconciliando los datos de los usuarios de aplicaciones móviles.
* Ahora, Adobe Campaign prioriza el procesamiento de las notificaciones push transaccionales en las notificaciones Push estándar.

#### Reports {#reports}

* Se ha corregido un problema que impedía que los porcentajes de clic interactivos se mostraran en el contenido de correo electrónico.
* Se ha corregido un problema con la métrica de lista negra que se contaba como una devolución fuerte en lugar de una devolución.
* Se ha corregido un problema que provocaba que se mostraran recuentos negativos en los datos de resumen.
* Se ha corregido un problema que contaba los perfiles en el segmento de edad incorrecto.
* Las fórmulas de cálculo suave y de salida hacia otro sitio han cambiado.

#### Workflows {#workflows}

* Fixed an issue in the **[!UICONTROL Load file]** activity that could lead to errors after manually adding and removing columns in the activity.
* The **[!UICONTROL deliverabilityUpdate]** technical workflow is now scheduled to run at 2am, server time.
* Se ha corregido un problema de seguridad que permitía realizar una exportación de lista sin la función de exportación.
* Fixed an issue with the **[!UICONTROL Reconciliation]** activity.
* Fixed an issue with the use of wildcard characters in the **[!UICONTROL File Transfer]** activity.

#### Profiles and audiences {#profiles-and-audiences}

* Se ha corregido un problema que podía impedir que una condición de una consulta se tuviese en cuenta correctamente en algunos casos específicos, lo que producía resultados erróneos.
* Se ha corregido un problema que impedía el acceso de perfiles si se dirigían en un mensaje preparado pero nunca enviado y caducado.

#### Integrations {#integrations}

* Se ha corregido un problema que podía impedir que algunas fuentes de datos creadas para activadores se mostraran correctamente y se seleccionaran.

#### Custom resources {#custom-resources}

* Se ha corregido un problema que se producía en las pantallas de lista donde las filas de recursos personalizados podían mostrarse sin ningún dato.
* Se ha corregido un problema que impedía que los campos de tipo booleano con valor'False'se mostraran en recursos personalizados.

## Release 17.9 - September 2017 {#release-17-9---september-2017}

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
   <td> Library of Email templates<br /> </td> 
   <td> Presentamos dieciocho plantillas nuevas y adaptables diseñadas en dos atractivos temas: Astro y Feather. Estas plantillas personalizables son agnópticas y listas para usarse de inmediato. Las plantillas incluyen contenido para diversos casos de uso para que sus campañas de marketing por correo electrónico se diseñen y entreguen más rápido, de forma eficiente y más sencilla que nunca.<br /> Para obtener más información, consulte la documentación <a href="../../start/using/about-templates.md#content-templates">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dynamic Reporting with Profile Data<br /> </td> 
   <td> Informes dinámicos proporciona informes empresariales en tiempo real y totalmente personalizables. Con esta versión, la potente mejora de Informes dinámicos añade acceso a los datos de perfil, lo cual permite realizar análisis demográficos según dimensiones de perfil como sexo, ciudad, código postal y edad, además de datos funcionales de campaña de correo electrónico, como aperturas y clics. Con la misma interfaz fácil de usar para arrastrar y soltar, la determinación de cómo funcionó la campaña de correo electrónico en los segmentos de clientes más importantes es más fácil que nunca.<br /> Para obtener más información, consulte la documentación <a href="../../reporting/using/about-dynamic-reports.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Mass Subscription with Origin &amp; Date<br /> </td> 
   <td> Con esta mejora de suscripción masiva, ahora puede almacenar información de suscripción (origen y fecha) directamente en la base de datos de Adobe Campaign Standard a través de la actividad Servicios de suscripción en un flujo de trabajo.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/subscription-services.md">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-1}

#### Platform {#platform-1}

* Algunos clientes necesitan poder aprovechar un ID procedente de Adobe Campaign Standard porque no administran una clave única para identificar sus propios registros. This ID (**ACS ID**) can be exported as well as used as a reconciliation key while updating the data. For more information, refer to the [detailed documentation](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* El protocolo FTP se está desaprobando. Ahora debe utilizar SFTP. Para no bloquear implementaciones existentes, las configuraciones existentes en FTP seguirán funcionando como antes pero la opción no se mostrará para las nuevas actividades.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-1}

* Ahora es posible crear nuevos criterios de alerta para usarlos en notificaciones de alerta de entrega. For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Las notificaciones de notificación de envío tienen un diseño nuevo y la experiencia de usuario de alertas de entrega se ha mejorado.
* Now when a routing external account is disabled, a warning is displayed in the impacted deliveries (email, SMS and push) and the **Preview** button is hidden in these deliveries.
* Se ha corregido un problema que provocaba un error en la vista previa de una prueba A/B en el contenido de correo electrónico cuando se activaba texto dinámico en la línea de asunto.

#### Transactional messages {#transactional-messages}

* Ahora es posible definir cuándo desea enviar un mensaje de seguimiento, por ejemplo, 3 días después de enviar un mensaje de transacción. For more information, refer to the [detailed documentation](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Ahora es posible definir la fecha desde la que deben enviarse los mensajes transaccionales vinculados a un evento.
* Se ha corregido un problema que provocaba un error SQL al ejecutar un flujo de trabajo que contiene un mensaje de seguimiento tras eliminar perfiles vinculados a eventos recibidos y procesados.
* Se ha corregido un error que impedía eliminar un perfil vinculado a un evento.
* Se ha corregido un problema que impedía que el redireccionamiento de los vínculos rastreados funcionara.
* Se ha corregido un problema que impedía deshabilitar el seguimiento de ciertos vínculos en un mensaje de correo electrónico o SMS.

#### Reports {#reports-1}

* The **Hot clicks** report has been improved. Además, ahora es posible mostrar clics dinámicos según cada contenido condicional definido en una entrega y mostrar los clics activos para cada ejecución de entregas recurrentes o mensajes transaccionales. For more information, refer to the [detailed documentation](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Se ha corregido un problema que impedía que la métrica de cuarentena recuperara datos correctos.
* Se ha agregado un nuevo intervalo de tiempo preestablecido al widget del calendario.
* The [dynamic report metrics](../../reporting/using/indicator-calculation.md) and the [campaigns' KPIs](../../sending/using/confirming-the-send.md) (displayed on the dashboard of sent messages) have been aligned for more coherence.
* Se ha corregido un problema que podía provocar que se bloqueara en debian 7.

#### Workflows {#workflows-1}

* Se ha corregido un problema que impedía que la retención de archivos importados funcionara.

#### Integrations {#integrations-1}

* Ahora se admiten evars y eventos para la integración de Analytics y Campaign.
* Al enviar un correo electrónico con el contenido del carro abandonado, el parámetro de carga útil para elementos eliminados del carro de compras ahora es opcional.

#### Profiles and audiences {#profiles-and-audiences-1}

* Ahora, Adobe Campaign proporciona un informe que muestra el número de perfiles activos. Este informe solo es informativo, no tiene un impacto directo en la facturación. For more information, refer to the [detailed documentation](../../audiences/using/active-profiles.md).
* Se ha corregido un problema que impedía que los perfiles se suscribiesen a un servicio al utilizar la API de perfiles y servicios.

## Release 17.7 - July 2017 {#release-17-7---july-2017}

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
   <td> Multilingual email and SMS deliveries<br /> </td> 
   <td> Defina y ejecute entregas multilingües por correo electrónico y SMS a través de una entrega única basada en el idioma preferido de los clientes segmentados automáticamente. Informar sobre el rendimiento de cada entrega hasta los niveles de idioma y individuales.<br /> Cada vez más empresas se enfrentan al reto de entregar contenido en varios idiomas a medida que aumentan en casa y en el extranjero. Como tal, simplificar la entrega de mensajes localizados es una parte fundamental de una estrategia de comunicación de clientes eficaz para las empresas multinacionales; empresas en países con varios idiomas; y empresas que desean personalizar aún más su contenido en el nivel lingüístico independientemente de dónde residan los clientes. For more information, refer to the <a href="../../channels/using/creating-a-multilingual-email.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Adobe Campaign Notifications<br /> </td> 
   <td> Reciba notificaciones sobre actividades importantes del sistema directamente dentro de Adobe Campaign Standard. Se le notificará, por ejemplo, sobre el progreso de sus entregas continuas o cuando un flujo de trabajo se haya producido en error.<br /> Las notificaciones en tiempo real mantienen informados a las partes interesadas y proporcionan a los usuarios la capacidad de actuar inmediatamente y directamente con respecto a las notificaciones de la actividad desde la aplicación. El resultado para los equipos es la agilidad, eficiencia y ejecución más fluida de las campañas. For more information, refer to the <a href="../../administration/using/sending-internal-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Delivery Alerting<br /> </td> 
   <td> Además de ver las notificaciones directamente en Adobe Campaign Standard, Adobe Campaign ahora también proporciona un sistema de alerta por correo electrónico para activar las alertas por correo electrónico a los usuarios o las partes interesadas externas de las actividades importantes del sistema. Cree, administre y reciba alertas y tableros personalizables para rastrear la entrega correcta o incorrecta.<br /> Las alertas de entrega de Adobe Campaign mejoran la eficacia al mantener informados a todos los usuarios de Adobe Campaign de una empresa sobre el estado de ejecución de la entrega, por correo electrónico y por tablero. For more information, refer to the <a href="../../sending/using/receiving-alerts-when-failures-happen.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Encrypted Declared ID in Datasources<br /> </td> 
   <td> Envíe activadores de correo electrónico y SMS sin necesidad de un perfil existente en Campaign mediante la información de contacto cifrada (dirección de correo electrónico o número de teléfono) como ID declarado. Debido a que Adobe Campaign Standard puede descodificar los ID declarados, la campaña ahora puede crear nuevos perfiles comercializables al recibir audiencias de otras soluciones de Experience Cloud que contengan contactos desconocidos previamente.<br /> Establezca como objetivo a los clientes y a las perspectivas desconocidas en tiempo real mediante correo electrónico y SMS para mejorar la lealtad en la base de clientes existente y adquirir clientes nuevos, respectivamente. Aproveche al máximo los datos de cookies personales (de Adobe Audience Manager *) cuando los clientes autentican y aprovechan dichas perspectivas en Adobe Campaign. <br /> * Se requiere Adobe Audience Manager. For more information, refer to the <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> KPI sharing from Campaign to Analytics<br /> </td> 
   <td> Comparta datos de campaña con Adobe Analytics para medir las métricas de mercadotecnia por correo electrónico de Campaign junto con otros esfuerzos publicitarios y de mercadotecnia a través de la conversión, uniendo el comportamiento previo y posterior al clic.<br /> Rastree el rendimiento general directamente y descubra sinergias con programas externos en Analytics. Aplique su aprendizaje de esta vista consolidada a sus campañas; mejorando en última instancia las tasas de conversión, pulsaciones y conversiones que aumentan los ingresos y el rendimiento general de la campaña. <br /> Se requiere Adobe Analytics. For more information, refer to the <a href="../../integrating/using/about-campaign-analytics-integration.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Direct Mail Channel - Return To Sender<br /> </td> 
   <td> Ahora se admiten intercambios de archivos planos con proveedores de correo directo que incorporan información de retorno a remitente. Esta mejora en el canal de correo directo permite excluir las direcciones postales correspondientes de futuras comunicaciones.<br /> Esto permite a los especialistas en mercadotecnia recibir notificaciones de una dirección incorrecta e interactuar con el cliente a través de otros canales o para pedirle que actualice su dirección postal. Esto también reduce la cantidad de dinero de mercadotecnia desperdiciada, ya que los especialistas en mercadotecnia no pueden enviar correo a direcciones incorrectas. <br /> Direct Mail está disponible como canal complementario. For more information, refer to the <a href="../../channels/using/return-to-sender.md">detailed documentation</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-2}

#### General {#general}

* Se ha corregido un problema que permitía a cualquier usuario exportar listas. Now only users with the **[!UICONTROL Export]** role are allowed to.

#### Emails, SMS messages and direct mail {#emails--sms-messages-and-direct-mail-2}

* Fixed an issue with the **updateDeliveryExecInfo** workflow that set the **To deliver** indicator to 0 for SMS deliveries.
* In the **Advanced parameters** of the delivery template’s properties, the **Routing** drop-down list now only displays external accounts corresponding to the template message type. Por ejemplo, una plantilla de envío de correo electrónico solo muestra las cuentas externas de correo electrónico.
* Fixed an issue with the **[!UICONTROL Text]** preferred email format defined for test profiles.
* Se ha corregido un problema que provocaba un error de Javascript al seleccionar la zona horaria predeterminada en la pantalla de definición de programación de una entrega.
* Se ha corregido un problema que impedía que aparecieran las reventaciones en los registros de envío.
* En la pantalla de selección de plantillas del asistente para creación de envíos, el seguimiento y las plantillas de prueba A/B están ocultos de forma predeterminada. For more information, refer to the [detailed documention](../../channels/using/creating-an-email.md).
* Se ha corregido un problema que permitía que cualquier usuario enviara envíos. Now only users with the **[!UICONTROL Start deliveries]** role are allowed to. For more information, refer to the [detailed documention](../../sending/using/confirming-the-send.md).

#### Push notifications {#push-notifications-1}

* Fixed an issue with the **Campaign Tracking Endpoint** URL that prevented reporting.
* Se ha corregido un problema que impedía mostrar el título de notificación push en dispositivos Android.
* Se ha corregido un problema que impedía que la notificación push se mostrara en dispositivos iOS cuando la notificación push contenía únicamente un título (y nada en el cuerpo del mensaje).
* Se ha corregido un problema que provocaba que las URL de adjuntos de medios en una entrega se rastrearan, lo que impedía que se incrustaran vídeos e imágenes en la entrega. El seguimiento de URL del tipo mediaattachmenturl ahora se desactiva de forma predeterminada para las notificaciones push.

#### Reports {#reports-2}

* Se corrigió un problema en el cual los valores aparecían diferentes entre los gráficos y la tabla.
* Se corrigió un problema que mostraba valores de notificación push como valores de correo electrónico.
* Se ha corregido un problema que mostraba valores como desconocidos cuando se creaba una entrega fuera de una campaña.
* Se corrigió un problema que mostraba datos de informes SMS como datos de aplicaciones móviles.

#### Workflows {#workflows-2}

* Ahora puede filtrar los registros de flujo de trabajo (período de tiempo y búsqueda de texto). For more information, refer to the [detailed documention](../../automating/using/executing-a-workflow.md#monitoring).
* Ahora hay disponible una opción en los envíos de flujo de trabajo para desactivar la confirmación antes del envío.
* Se ha corregido un problema que impedía establecer una transición saliente en el asistente de creación de envío recurrente.
* Se ha corregido un problema que se producía al usar una actividad de consulta de flujo de trabajo basada en un campo de recursos personalizado con una enumeración con muchos valores

## Release 17.5 - May 2017 {#release-17-5---may-2017}

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
   <td> Direct mail<br /> </td> 
   <td> Rompa la barrera digital y conecte al mundo físico con el primer canal sin conexión de Adobe Campaign Standard, Direct Mail. Esta función le permite personalizar y generar el archivo requerido por proveedores de correo directo como parte de sus campañas multicanal. Aproveche Direct Mail para volver a involucrar a los clientes o para mejorar la experiencia del cliente con un atractivo touchpoint táctil que dirija a los clientes a su aplicación, sitio web o tienda.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/about-direct-mail.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> Email BCC permite guardar mensajes de correo electrónico únicos enviados a destinatarios individuales, permitiendo así que la marca archive esos mensajes. Al agregar una dirección de correo electrónico CCO a todos los correos electrónicos, los clientes de Adobe Campaign Standard pueden conservar una copia exacta de cada correo electrónico con esta función. Constituye un requisito legal común para el sector de servicios financieros y es útil para ayudar a los centros de atención al cliente a resolver conflictos en tiempo real.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/configuring-email-channel.md#archiving-emails">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-3}

#### Interface updates {#interface-updates}

* In the top bar, the **[!UICONTROL Timeline]** link has been removed and replaced with a link to **[!UICONTROL Programs & Campaigns]** .

#### Emails and SMS messages {#emails-and-sms-messages}

* Fixed an issue which displayed the wrong color for the **[!UICONTROL Retry in progress]** delivery status. El color era gris en lugar de azul.

#### Workflows {#workflows-3}

* Fixed an issue that occurred when changing the action to perform in a **[!UICONTROL Transfer file]** activity.

#### Reports {#reports-3}

* The **[!UICONTROL Spam]** and **[!UICONTROL Spam rate]** indicator calculations have been changed.
* The **[!UICONTROL Bounce]** metrics have been improved for a more accurate result.

#### Push notifications {#push-notifications-2}

* Se ha corregido un problema que impedía hacer clic en un evento push en el historial de marketing de un perfil.
* Se ha mejorado el uso de notificaciones push en flujos de trabajo.

## Release 17.4 - April 2017 {#release-17-4---april-2017}

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
   <td> Enhanced Image edition capabilities with the Creative SDK<br /> </td> 
   <td> Ahora tiene acceso a un conjunto completo de funciones ofrecidas por el SDK Creative para mejorar las imágenes directamente en el editor de contenido al editar correos electrónicos o páginas de aterrizaje.<br /> Esta función no requiere la adquisición de soluciones adicionales de Creative Cloud.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/modifying-images-with-the-adobe-creative-sdk.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional push notifications<br /> </td> 
   <td> El canal de aplicaciones móviles se ha agregado a las capacidades de mensajes transaccionales de Adobe Campaign. Ahora se admiten tres canales para los mensajes transaccionales: correo electrónico, SMS y notificaciones push.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/transactional-push-notifications.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Recurring push notifications<br /> </td> 
   <td> Ahora puede configurar notificaciones push recurrentes en un flujo de trabajo. Puede utilizar notificaciones push recurrentes en situaciones en las que sus clientes esperan actualizaciones periódicas como recordatorios semanales para extraer contenido o promociones nuevos.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/push-notification-delivery.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Amazon Simple Storage Service (S3) connector<br /> </td> 
   <td> El conector Amazon Simple Storage Service (S 3) ahora se puede utilizar para importar o exportar datos a Adobe Campaign. Se puede configurar en una actividad de flujo de trabajo. La configuración se realiza en una cuenta externa.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/external-accounts.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration live<br /> </td> 
   <td> La integración entre Adobe Campaign y Dreamweaver ya está activa. Ahora funciona con la última versión oficial publicada de Dreamweaver (17.0.2).<br /> Esto requiere la instalación de la extensión de Adobe Campaign Integration desde aquí: <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br /> Para obtener más información, consulte este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-4}

#### Platform {#platform-2}

* Se ha corregido un problema de consumo de memoria.

#### Emails and SMS messages {#emails-and-sms-messages-1}

* Se ha corregido un problema por el que el contenido no se podía sincronizar correctamente con los cambios más recientes al obtener una vista previa de un mensaje.
* Se ha corregido un problema que impedía crear o eliminar una regla de procesamiento de correo electrónico MX o Dominio.
* Se ha corregido un problema que impedía enviar correos electrónicos con alias múltiples.
* Se ha corregido un problema que impedía que los registros de envío de reventado aparecieran en los registros de envío del envío.
* Se ha corregido un problema que provocaba un error al mostrar las URL rastreadas de una entrega sin URL en su contenido.
* Se ha corregido un problema que impedía que los atributos de tamaño de una imagen se aplicaran correctamente en el mensaje enviado.

#### Transactional messages {#transactional-messages-1}

* El campo rteventhistoid ya no se expone como campo de personalización en una plantilla de mensaje transaccional.

#### Landing pages {#landing-pages}

* We have optimized the **[!UICONTROL by email]** filter used in landing pages to reconcile new subscribers with database profiles.
* Se ha corregido un problema que mostraba entradas de texto gratuitas en lugar de casillas de verificación al utilizar campos booleanos en una configuración de formulario.
* Se ha corregido un problema que impedía que se generaran miniaturas de página de aterrizaje.

#### Workflows {#workflows-4}

* Fixed a display error when editing an **[!UICONTROL End]** or **[!UICONTROL External Signal]** activity (on Safari only).
* Improved the error message displayed when editing a **[!UICONTROL Read Audience]** activity containing an erroneous audience.
* Se ha corregido un problema que podía provocar un error SQL al ejecutar una actividad de suscripción.

#### Integrations {#integrations-2}

* Datos de puntos de interés: Se ha corregido un error que se producía al contabilizar los suscriptores de ubicación.

#### Audiences and queries {#audiences-and-queries}

* Se ha corregido un problema que impedía la suma y el promedio de agregados de la colección en el editor de consultas.
* Se ha corregido un problema que podía evitar que el editor de consultas se volviera a cargar después de cambiar el recurso del filtro.

#### Reports {#reports-4}

* Se ha corregido un problema que impedía que se calcularan correctamente las métricas de Tasa de apertura al seleccionar varias filas en una tabla.
* Se ha corregido un error que solo mostraba métricas como valores enteros. Las métricas ahora se pueden mostrar con decimales.

#### Push notifications {#push-notifications-3}

* Se ha corregido un problema por el que no se mostraba un mensaje de error al crear una aplicación Android vinculada a una aplicación móvil que no había podido crearse en MCPNS.
* Se ha corregido un problema que permitía al usuario añadir sonidos a una notificación silenciosa.

## Release 17.2 - March 2017 {#release-17-2---march-2017}

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
   <td> Dynamic reporting<br /> </td> 
   <td> Informes dinámicos proporciona una nueva generación de informes empresariales en tiempo real y totalmente personalizables. Esta característica, basada en gráficos y tablas dinámicas visuales, permite arrastrar y soltar variables y dimensiones para analizar la eficacia y eficacia de sus campañas de marketing. Los informes dinámicos también permiten crear sus propios informes empresariales desde cero y guardarlos para usarlos posteriormente.<br /> Para obtener más información, consulte la documentación <a href="../../reporting/using/about-dynamic-reports.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Dreamweaver integration (Labs)<br /> </td> 
   <td> Con la integración de Adobe Campaign y Dreamweaver, ahora tiene un proceso integrado para crear campañas de correo electrónico con soluciones de Adobe.<br /> Puede editar los correos electrónicos de Adobe Campaign en Dreamweaver y sincronizar el contenido perfectamente entre ambas soluciones.<br /> Para la versión inicial, la integración está disponible como característica "Labs" y solo funciona con Dreamweaver Pre Release Beta. Si desea activarla, póngase en contacto con AC-DW-integration@adobe.com.<br /> Para obtener más información, consulte este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Manual send time optimization<br /> </td> 
   <td> Ahora puede definir manualmente un tiempo de envío personalizado por destinatario, en el nivel de entrega o mediante un flujo de trabajo. <br /> Hay dos nuevas opciones disponibles: <br /> 
    <ul> 
     <li> Todos los destinatarios reciben el mensaje teniendo en cuenta su zona horaria. </li> 
     <li> Cada destinatario recibe el mensaje en una fecha y hora calculadas según una fórmula. </li> 
    </ul> For more information, refer to the <a href="../../sending/using/optimizing-the-sending-time.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Push notifications New capabilities<br /> </td> 
   <td> The push notification channel has been enhanced with several new capabilities:<br /> 
    <ul> 
     <li> Nueva interfaz de creación </li> 
     <li> Notificaciones silenciosas </li> 
     <li> Push interactivo </li> 
     <li> Compatibilidad con contenido enriquecido </li> 
     <li> Calculadora de tamaño de carga útil </li> 
    </ul> For more information, refer to the <a href="../../channels/using/about-push-notifications.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Signal activity<br /> </td> 
   <td> Trigger a workflow from another workflow using the new <span class="uicontrol">Signal</span> activity.<br /> Ahora, con la capacidad de iniciar un flujo de trabajo desde otro, puede admitir trayectorias de clientes más complejas. Puede supervisar mejor las trayectorias de los clientes y reaccionar en caso de que haya problemas.<br /> Se han actualizado varias actividades de flujo de trabajo:<br /> 
    <ul> 
     <li> <span class="uicontrol">Actividad final</span> : una nueva ficha permite especificar un flujo de trabajo que se activará después de ejecutar esta actividad. </li> 
     <li> <span class="uicontrol">Actualizar</span> actividad de datos: use la nueva transición saliente vacía para agregar una <strong>actividad End</strong> que activa otro flujo de trabajo. Las transiciones salientes vacías no transmiten datos y no consumen espacio innecesario en el sistema </li> 
    </ul> For more information, refer to the <a href="../../automating/using/external-signal.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Workflows: new Read audience activity<br /> </td> 
   <td> Inicie el proceso de segmentación con una audiencia existente que pueda seleccionar y refinar fácilmente en una actividad.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/read-audience.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Points of Interest data<br /> </td> 
   <td> Los datos de Puntos de interés integran Adobe Campaign con Adobe Analytics for Mobile. A brand can collect data from users' mobile locations - called <strong>Points of Interest</strong> - when users open the brand's app. Esto permite a la marca aprovechar los flujos de trabajo de Adobe Campaign para enviar mensajes personalizados según las ubicaciones de los usuarios. Este canal aprovecha el SDK del servicio principal de Mobile.<br /> Tenga en cuenta que el uso de esta función requiere Analytics for Mobile, que es una solución de pago.<br /> Para obtener más información, consulte la documentación <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> REST APIs<br /> </td> 
   <td> Los recursos vinculados en cualquier nivel a los perfiles o recursos de servicios ya están disponibles en la API.<br /> Para obtener más información, consulte la documentación <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-5}

#### General {#general-1}

* Ahora es posible agregar datos de perfil al exportar registros de entrega.

#### Emails and SMS messages {#emails-and-sms-messages-2}

* Fixed an issue causing the **[!UICONTROL Request confirmation before sending messages]** option to remain selected even after unchecking it and saving the delivery.
* Se ha corregido un problema que podía impedir la cancelación de correos electrónicos transaccionales.
* Se ha corregido un problema por el que el contenido no se podía sincronizar correctamente con los cambios más recientes antes de previsualizar una entrega.

#### Landing pages {#landing-pages-1}

* Se ha corregido un error que impedía que un usuario editara al hacer clic en el contenido de una página de aterrizaje.

#### Workflows {#workflows-5}

* Fixed an issue that could prevent from reading the content of the reject transition of a **[!UICONTROL Load file]** activity.
* Fixed an issue that prevented swapped columns to be properly taken into account when configuring a **[!UICONTROL Load file]** activity.

## Release 17.1 - January 2017 {#release-17-1---january-2017}

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
   <td> Log export for external reporting<br /> </td> 
   <td> Los registros de exportación son registros de envío y de seguimiento para procesarlos en sus informes o herramientas BI preferidos. Puede utilizar flujos de trabajo simples con consultas incrementales para automatizar las exportaciones regulares de registros nuevos.<br /> Además de la disponibilidad de recursos de registro desde el selector de recursos, se realizaron mejoras en la consulta <a href="../../automating/using/incremental-query.md">incremental</a> y <a href="../../automating/using/extract-file.md">en Extraer</a> actividades de archivos:<br /> 
    <ul> 
     <li> <span class="uicontrol">Ahora, la consulta</span> incremental permite utilizar un campo de fecha para recuperar datos nuevos o actualizados. Anteriormente, todos los resultados de ejecuciones anteriores se excluían automáticamente, incluso si se actualizaban desde la última ejecución. </li> 
     <li> <span class="uicontrol">Ahora, Extraer archivo</span> puede exportar etiquetas para valores de enumeración en lugar de ID. </li> 
    </ul> Estas actividades están disponibles para los administradores con acceso a todas las unidades geográficas y de organización.<br /> Para obtener más información sobre la exportación de registros, consulte la documentación <a href="../../automating/using/exporting-logs.md">detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Marketing capabilities for transactional messages<br /> </td> 
   <td> Los especialistas en marketing ahora pueden enviar mensajes transaccionales basados en perfiles de marketing de clientes. This allows them to:<br /> 
    <ul> 
     <li> Apply marketing typology rules such as <span class="uicontrol">Blacklisted address</span> . </li> 
     <li> Incluya el vínculo de cancelación de suscripción dentro de los mensajes. </li> 
     <li> Agregue los mensajes transaccionales a los informes de entrega global. </li> 
     <li> Aproveche los mensajes transaccionales en el viaje del cliente. </li> 
    </ul> For more information, refer to the <a href="../../channels/using/profile-transactional-messages.md">detailed documentation</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Transactional Messaging API<br /> </td> 
   <td> The Transactional Messaging API is now available through <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, making it easier to use and to monitor:<br /> 
    <ul> 
     <li> Puede beneficiarse de los informes de la plataforma adobe. io y de los conocimientos de monitoreo. </li> 
     <li> La autenticación ahora se realiza mediante la autenticación basada en tokens adobe. io en lugar de en la lista de direcciones permitidas IP, lo que facilita el proceso de seguridad. </li> 
     <li> Todas las API ahora se integran en una sola plataforma, lo que hace que sea más sencillo que nunca agregar capacidades de mensajería transaccional a la integración si ya se admite la API de perfil y servicios. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Patches {#patches-6}

#### General {#general-2}

* **[!UICONTROL Access authorization]** Las opciones se han devuelto a las propiedades de página de aterrizaje.
* Se ha corregido un problema que causaba que se procesara una imagen antigua en lugar de la imagen correcta. Esto ocurría si la imagen de origen se había actualizado en la definición de contenido de una entrega o página de aterrizaje.
* Se ha corregido un problema que impedía que los usuarios editasen determinados campos en una cuenta externa SFTP existente.
* Se han corregido varios problemas de la interfaz de usuario. Por ejemplo, los usuarios ahora pueden editar atributos de perfil y guardar modificaciones sin tener problemas con la interfaz de usuario.

#### Emails and SMS messages {#emails-and-sms-messages-3}

* Se ha corregido un problema relacionado con las plantillas de envío con contenido HTML que contenía un

#### Push notifications {#push-notifications-4}

* Se ha corregido un problema que podía haber impedido el postback de una aplicación al servidor de Adobe Campaign.
* Fixed an issue that may have prevented **[!UICONTROL Play a sound]** and **[!UICONTROL Custom fields]** to be taken into account for Android.
* Se ha corregido un problema que podía haber provocado que se agregara un carácter de escape adicional a los caracteres Unicode utilizados para Emojis.
* Cuando el autentificador de registro de un suscriptor se encuentra bloqueado, el estado correspondiente ahora se actualiza inmediatamente en la lista de suscriptores de Adobe Campaign de la aplicación.

#### Workflows {#workflows-6}

* Se ha corregido un problema que podía haber impedido las vistas previas de consultas en los recursos del evento (por ejemplo, rtevent).
* The reject file generated by a **[!UICONTROL Load file]** activity can now be retrieved in its outbound transition and processed in the next activity. For example, upload the reject file via an SFTP server using **[!UICONTROL Transfer file]** .
* Fixed an issue that may have prevented a user from limiting the population of a segment if **[!UICONTROL Temporary resource]** was selected in the **[!UICONTROL General]** tab of **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** ya no se pueden configurar las actividades para desencadenar un flujo de trabajo más de una vez cada 10 minutos.
* Fixed an issue that may have prevented **[!UICONTROL Use common columns]** from working properly in an **[!UICONTROL Union]** activity.

#### Integrations {#integrations-3}

* Se ha corregido un problema que podía haber provocado un error al implementar un activador de eventos en Adobe Campaign. Este error se producía cuando se añadían los metadatos «Probabilidades al retorno en 30 días» al activador de abandono en Adobe Marketing Cloud.
* Se ha corregido un problema que podía haber provocado que el flujo de trabajo técnico borrara el campo Dimensión de objetivo al importar audiencias del servicio principal Personas. Las consultas subsiguientes no pudieron recuperar las audiencias importadas.
* Fixed an issue that may have caused the **[!UICONTROL Save audience]** activity of a workflow to fail when the option **[!UICONTROL Share in Adobe Marketing Cloud]** was checked.

