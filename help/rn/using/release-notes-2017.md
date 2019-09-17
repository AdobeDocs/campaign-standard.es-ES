---
title: Notas de la versión 2017
seo-title: Notas de la versión 2017
description: Notas de la versión 2017
seo-description: Esta página enumera todas las versiones de 2017 de Adobe Campaign Standard.
page-status-flag: nunca activado
uuid: d73f8186-e309-441b-969d-71d0a1c33cf4
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: referencia
topic-tags: campaign-standard-releases
discoiquuid: 1cfd9b3b-9b3e-4587-9c46-b6fb02131654
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 7a091f0fd4b191a9f81dfe3a8c74e1624de72f12

---


# Notas de la versión 2017{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard para 2017?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

Vea las últimas actualizaciones [de](../../rn/using/documentation-updates.md) documentación de Adobe Campaign Standard. Si busca una versión más reciente, consulte esta [página](../../rn/using/release-notes.md).

## Versión 17.10: octubre de 2017 {#release-17-10---october-2017}

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
   <td> Administración de fatiga<br /> </td> 
   <td> La Administración de fatiga le permite crear reglas de fatiga para administrar la sobrecomunicación con perfiles. Las reglas de fatiga se crean fácilmente, pero son extremadamente flexibles con capacidades como contar mensajes a través de múltiples canales (incluyendo mensajes transaccionales), contar solamente entregas específicas o aplicar reglas a perfiles específicos.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/fatigue-rules.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creación de contenido: Importar desde una dirección URL<br /> </td> 
   <td> Importar desde una URL permite recuperar rápidamente el contenido creativo de un sitio web para crear correos electrónicos para cualquier entrega. Además, puede optimizar el proceso creativo permitiendo a terceros compartir contenido directamente a través de una URL. El contenido importado se puede utilizar de forma flexible como parte de una única entrega o a nivel de plantilla, lo que garantiza la coherencia de la marca para todas las campañas relacionadas, ya sean mensajes transaccionales o basados en flujos de trabajo, e incluye pruebas A/B o multivariadas. Importar desde una URL convierte y rastrea automáticamente todos los vínculos para supervisar el rendimiento del correo electrónico a través de los informes dinámicos.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/using-existing-content.md#importing-content-from-a-url"></a>detallada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches}

#### Plataforma {#platform}

* Se ha corregido un problema que podía impedir que los archivos comprimidos grandes se descomprimieran correctamente.
* Se ha mejorado la seguridad en la gestión de marca. La modificación del nombre y la dirección del remitente de una marca ahora está reservada para los administradores técnicos de Adobe.
* Para mejorar la seguridad, el contenido generado por el usuario (imágenes, páginas espejo, páginas de aterrizaje, etc.) el dominio adobe.com ya no puede servir. Ahora es obligatorio usar su propio dominio para manejar estos recursos, mediante el uso de la marca.
* Se ha corregido un problema de la interfaz al mostrar y filtrar actividades de marketing.
* Se ha corregido un problema que impedía que los campos de fecha de suscripción se actualizaran con una llamada de API POST Rest.

#### Correos electrónicos, mensajes SMS y correo directo {#emails--sms-messages-and-direct-mail}

* Se ha corregido un problema que podía impedir que se dirigiera a una audiencia de tipo de lista en un mensaje, lo que provocaba un error en la preparación.
* Se han añadido idiomas que faltan en las funciones de envío de correo electrónico multilingües.
* La miniatura de contenido, que se muestra en el panel de envío, ahora se actualiza automáticamente cuando el usuario modifica el contenido y lo guarda.
* Se ha corregido un problema relacionado con la zona horaria que impedía abrir un envío.

#### Notificaciones push {#push-notifications}

* Al configurar el canal de notificaciones push, la plataforma del proveedor push para iOS debe ser **apns** y para Android **gcm**.
* Se ha corregido un error que impedía que la aplicación móvil de iOS se agregara a la interfaz de Adobe Campaign.
* Las notificaciones push ahora son compatibles con aplicaciones móviles Android con GCM y FCM.
* Se ha corregido un error que impedía guardar el contenido al duplicar una plantilla de notificación push.
* Ahora es posible crear o actualizar un perfil de la base de datos de Adobe Campaign conciliando los datos de los usuarios de aplicaciones móviles.
* Adobe Campaign ahora prioriza el procesamiento de las notificaciones push de transacción sobre las notificaciones push estándar.

#### Informes {#reports}

* Se ha corregido un problema que impedía que los porcentajes de clics interactivos se mostraran en el contenido del correo electrónico.
* Se ha corregido un problema con la métrica de lista negra que se contaba como una devolución forzada en lugar de una devolución.
* Se ha corregido un problema que hacía que se mostraran recuentos negativos en los datos de resumen.
* Se ha corregido un problema que hacía que se contaran los perfiles en el segmento de edad incorrecto.
* Las fórmulas de cálculo de devoluciones en bruto y en bruto han cambiado.

#### Flujos de trabajo {#workflows}

* Se ha corregido un problema en la **[!UICONTROL Load file]** actividad que podía provocar errores después de agregar y quitar columnas manualmente en la actividad.
* El flujo de trabajo **[!UICONTROL deliverabilityUpdate]** técnico está programado para ejecutarse a las 2 de la mañana, hora del servidor.
* Se ha corregido un problema de seguridad que permitía realizar una exportación de lista sin la función de exportación.
* Se ha corregido un problema con la **[!UICONTROL Reconciliation]** actividad.
* Se ha corregido un problema con el uso de caracteres comodín en la **[!UICONTROL File Transfer]** actividad.

#### Perfiles y audiencias {#profiles-and-audiences}

* Se ha corregido un problema que podía impedir que una condición de una consulta se tuviera correctamente en cuenta en algunos casos específicos, lo que producía resultados erróneos.
* Se ha corregido un problema que podía impedir el acceso a los perfiles si estaban segmentados en un mensaje preparado pero que nunca se enviaba ni caducaba.

#### Integraciones {#integrations}

* Se ha corregido un problema que podía impedir que algunas fuentes de datos creadas para los activadores se mostraran y se seleccionaran correctamente.

#### Recursos personalizados {#custom-resources}

* Se ha corregido un problema que ocurría en las pantallas de lista donde las filas de recursos personalizados se podían mostrar sin ningún dato.
* Se ha corregido un problema que impedía que los campos de tipo booleano con el valor 'False' se mostraran en los recursos personalizados.

## Versión 17.9: septiembre de 2017 {#release-17-9---september-2017}

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
   <td> Biblioteca de plantillas de correo electrónico<br /> </td> 
   <td> Presentamos dieciocho plantillas nuevas y adaptables diseñadas en dos atractivos temas: Astro y Feather. Estas plantillas personalizables son agnósticas para la industria y están listas para utilizarse de inmediato. Las plantillas incluyen contenido para una variedad de casos de uso a fin de diseñar y distribuir sus campañas de marketing por correo electrónico de manera más rápida, eficiente y maravillosamente que nunca.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/using-reusable-content.md#content-templates"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Informes dinámicos con datos de perfil<br /> </td> 
   <td> Los informes dinámicos proporcionan informes comerciales totalmente personalizables y en tiempo real. Con esta versión, una potente mejora de Informes dinámicos añade acceso a los datos de perfil, lo que permite realizar análisis demográficos por dimensiones de perfil como sexo, ciudad, código postal y edad, además de datos funcionales de campañas de correo electrónico como aperturas y clics. Con la misma sencilla función de arrastrar y soltar, determinar el rendimiento de la campaña de correo electrónico en relación con los segmentos de clientes más importantes es más fácil que nunca.<br /> Para obtener más información, consulte la documentación <a href="../../reporting/using/about-dynamic-reports.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Suscripción masiva con origen y fecha<br /> </td> 
   <td> Con esta mejora de suscripción masiva, ahora puede almacenar información de suscripción (origen y fecha) directamente en la base de datos de Adobe Campaign Standard a través de la actividad Servicios de suscripción en un flujo de trabajo.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/subscription-services.md"></a>detallada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-1}

#### Plataforma {#platform-1}

* Algunos clientes deben poder aprovechar un ID de Adobe Campaign Standard, ya que no administran una clave única para identificar sus propios registros. Este ID (**ACS ID**) se puede exportar y utilizar como clave de reconciliación al actualizar los datos. Para obtener más información, consulte la documentación [](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)detallada.
* El protocolo FTP está en desuso. Ahora debería usar SFTP en su lugar. Para no bloquear las implementaciones existentes, las configuraciones existentes en FTP seguirán funcionando como antes, pero la opción no se mostrará para las nuevas actividades.

#### Correos electrónicos, mensajes SMS y correo directo {#emails--sms-messages-and-direct-mail-1}

* Ahora es posible crear nuevos criterios de alerta para utilizarlos en las notificaciones de alerta de envío. Para obtener más información, consulte la documentación [](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)detallada.
* Las notificaciones de envío tienen un nuevo diseño y se ha mejorado la experiencia del usuario del tablero de alertas de envío.
* Ahora, cuando se desactiva una cuenta externa de enrutamiento, se muestra una advertencia en los envíos afectados (correo electrónico, SMS y push) y el botón **Vista previa** se oculta en estos envíos.
* Se ha corregido un problema que provocaba un error en la vista previa de una prueba A/B en el contenido del correo electrónico cuando se habilitaba el texto dinámico en la línea de asunto.

#### Mensajes transaccionales {#transactional-messages}

* Ahora es posible definir cuándo desea enviar un mensaje de seguimiento, por ejemplo, 3 días después de enviar un mensaje transaccional. Para obtener más información, consulte la documentación [](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)detallada.
* Ahora es posible definir la fecha a partir de la cual deben enviarse los mensajes transaccionales vinculados a un evento.
* Se ha corregido un problema que provocaba un error SQL al ejecutar un flujo de trabajo que contenía un mensaje de seguimiento después de eliminar perfiles vinculados a eventos recibidos y procesados.
* Se ha corregido un error que impedía eliminar un perfil vinculado a un evento.
* Se ha corregido un problema que podía impedir que funcionara la redirección de los vínculos seguidos.
* Se ha corregido un problema que impedía desactivar el seguimiento de ciertos vínculos en un mensaje de correo electrónico o SMS.

#### Informes {#reports-1}

* Se ha mejorado el informe de **clics** interactivos. Además, ahora es posible mostrar clics interactivos según cada contenido condicional definido en una entrega y mostrar clics interactivos para cada ejecución de envíos recurrentes o mensajes transaccionales. Para obtener más información, consulte la documentación [](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion)detallada.
* Se ha corregido un problema que impedía que la métrica de cuarentena recuperara los datos correctos.
* Se ha agregado un nuevo intervalo de tiempo preestablecido al widget de calendario.
* Las métricas [de informes](../../reporting/using/indicator-calculation.md) dinámicos y los KPI [de](../../sending/using/confirming-the-send.md) campañas (mostrados en el tablero de mensajes enviados) se han alineado para lograr una mayor coherencia.
* Se ha corregido un problema que podía provocar que la tubería se bloqueara en debian 7.

#### Flujos de trabajo {#workflows-1}

* Se ha corregido un problema que podía impedir que funcionara la retención del archivo importado.

#### Integraciones {#integrations-1}

* Las eVars y los eventos ahora son compatibles con la integración de Analytics y Campaign.
* Al enviar un correo electrónico con el contenido del carro de compras abandonado, el parámetro de carga útil para elementos eliminados del carro de compras ahora es opcional.

#### Perfiles y audiencias {#profiles-and-audiences-1}

* Adobe Campaign ahora proporciona un informe que muestra el número de perfiles activos. Este informe es solo informativo, no tiene un impacto directo en la facturación. Para obtener más información, consulte la documentación [](../../audiences/using/active-profiles.md)detallada.
* Se ha corregido un problema que impedía que los perfiles se suscribieran a un servicio al usar la API de perfiles y servicios.

## Versión 17.7: julio de 2017 {#release-17-7---july-2017}

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
   <td> Envíos multilingües por correo electrónico y SMS<br /> </td> 
   <td> Defina y ejecute envíos multilingües de correo electrónico y SMS a través de una única entrega basada en el idioma preferido de los clientes segmentados automáticamente. Informar sobre el rendimiento de cada entrega en función del idioma y de los niveles individuales.<br /> Cada vez más empresas se enfrentan al desafío de entregar contenido en múltiples idiomas a medida que crecen dentro y fuera del país. Como tal, la racionalización de la entrega de mensajes localizados es un elemento clave de una estrategia eficaz de comunicación con los clientes para las empresas multinacionales; empresas de países con múltiples idiomas; y empresas que desean personalizar aún más su contenido a nivel lingüístico independientemente del lugar donde residan los clientes. Para obtener más información, consulte la documentación <a href="../../channels/using/creating-a-multilingual-email.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones de Adobe Campaign<br /> </td> 
   <td> Reciba notificaciones sobre actividades importantes del sistema directamente en Adobe Campaign Standard. Se le notificará, por ejemplo, sobre el progreso de las entregas en curso o cuando haya un error en el flujo de trabajo.<br /> Las notificaciones en tiempo real mantienen informados a los interesados pertinentes y proporcionan a los usuarios la capacidad de actuar de forma inmediata y directa en las notificaciones de actividades desde la aplicación. El resultado para los equipos es agilidad avanzada, eficiencia y ejecución más fluida de las campañas. Para obtener más información, consulte la documentación <a href="../../administration/using/sending-internal-notifications.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alerta de entrega<br /> </td> 
   <td> Además de ver las notificaciones directamente en Adobe Campaign Standard, Adobe Campaign ahora también ofrece un sistema de alertas por correo electrónico para activar alertas por correo electrónico a usuarios o partes interesadas externas de actividades importantes del sistema. Cree, administre y reciba alertas y tableros personalizables para realizar un seguimiento de los éxitos o errores de entrega.<br /> La alerta de entrega de Adobe Campaign aumenta la eficacia al mantener informados automáticamente a todos los usuarios de Adobe Campaign de una empresa sobre el estado de ejecución de la entrega, a través del correo electrónico y el tablero. Para obtener más información, consulte la documentación <a href="../../sending/using/receiving-alerts-when-failures-happen.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Id. declarado cifrado en orígenes de datos<br /> </td> 
   <td> Enviar desencadenantes de correo electrónico y SMS sin necesidad de un perfil existente en Campaign usando información de contacto cifrada (dirección de correo electrónico o número de teléfono) como ID declarada. Como Adobe Campaign Standard puede descodificar los ID declarados cifrados, Campaign ahora puede crear nuevos perfiles comercializables al recibir audiencias de otras soluciones de Experience Cloud que contengan contactos anteriormente desconocidos.<br /> Diríjase a clientes y clientes potenciales desconocidos en tiempo real a través de correo electrónico y SMS para mejorar la lealtad en su base de clientes existente y adquirir nuevos clientes, respectivamente. Saque el máximo partido a los datos de cookies de origen (de Adobe Audience Manager*) una vez que los posibles clientes se autentiquen y aprovechen estas perspectivas en Adobe Campaign. <br /> *Se requiere Adobe Audience Manager. Para obtener más información, consulte la documentación <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso compartido de KPI de Campaign a Analytics<br /> </td> 
   <td> Comparta datos de campaña con Adobe Analytics para medir las métricas de marketing por correo electrónico de Campaign junto con otros esfuerzos de marketing y publicidad a través de la conversión, unificando el comportamiento previo y posterior al clic.<br /> Rastree el rendimiento general directamente y descubra sinergias con programas externos en Analytics. Aplique el aprendizaje de esta vista consolidada a las campañas; en última instancia, se mejoran las tasas de apertura, pulsaciones y conversiones, lo que aumenta los ingresos y el rendimiento general de la campaña. <br /> Se requiere Adobe Analytics. Para obtener más información, consulte la documentación <a href="../../integrating/using/about-campaign-analytics-integration.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal de correo directo: devolución al remitente<br /> </td> 
   <td> Ahora se admiten los intercambios de archivos planos con proveedores de correo directo que incorporan información de devolución al remitente. Esta mejora del canal de correo directo permite excluir las direcciones postales correspondientes de futuras comunicaciones.<br /> Esto permite que se notifique a los especialistas en mercadotecnia de una dirección incorrecta y se ponga en contacto con el cliente a través de otros canales o que le anime a actualizar su dirección postal. Esto también reduce el número de dólares de mercadotecnia desperdiciados, ya que los especialistas en mercadotecnia evitan enviar correos a direcciones incorrectas. <br /> Direct Mail está disponible como canal complementario. Para obtener más información, consulte la documentación <a href="../../channels/using/return-to-sender.md"></a>detallada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-2}

#### General {#general}

* Se ha corregido un problema que permitía a cualquier usuario exportar listas. Ahora solo los usuarios con la **[!UICONTROL Export]** función pueden hacerlo.

#### Correos electrónicos, mensajes SMS y correo directo {#emails--sms-messages-and-direct-mail-2}

* Se ha corregido un problema con el flujo de trabajo **updateDeliveryExecInfo** que establecía el indicador **Para entregar** en 0 para envíos SMS.
* En los parámetros **** avanzados de las propiedades de la plantilla de envío, la lista desplegable **Enrutamiento** ahora solo muestra las cuentas externas correspondientes al tipo de mensaje de plantilla. Por ejemplo, una plantilla de envío de correo electrónico solo muestra cuentas externas de correo electrónico.
* Se ha corregido un problema con el formato de correo electrónico preferido definido para los perfiles de prueba. **[!UICONTROL Text]**
* Se ha corregido un problema que provocaba un error de JavaScript al seleccionar la zona horaria predeterminada en la pantalla de definición de programación de una entrega.
* Se ha corregido un problema que impedía que las trampas aparecieran en los registros de envío.
* En la pantalla de selección de plantillas del asistente para la creación de envíos, las plantillas de prueba A/B y de seguimiento ahora están ocultas de forma predeterminada. Para obtener más información, consulte la documentación [detallada](../../channels/using/creating-an-email.md).
* Se ha corregido un problema que permitía a cualquier usuario enviar envíos. Ahora solo los usuarios con la **[!UICONTROL Start deliveries]** función pueden hacerlo. Para obtener más información, consulte la documentación [detallada](../../sending/using/confirming-the-send.md).

#### Notificaciones push {#push-notifications-1}

* Se ha corregido un problema con la dirección URL del extremo **de seguimiento de** campaña que impedía la creación de informes.
* Se ha corregido un problema que impedía que el título de la notificación push se mostrara en dispositivos Android.
* Se ha corregido un problema que impedía que la notificación push se mostrara en dispositivos iOS cuando la notificación push solo contenía un título (y nada en el cuerpo del mensaje).
* Se ha corregido un problema que obligaba a realizar un seguimiento de las URL de datos adjuntos multimedia de una entrega, lo que impedía que los vídeos y las imágenes se incrustaran en la entrega. El seguimiento de direcciones URL del tipo mediaAttachmentURL ahora está desactivado de forma predeterminada para las notificaciones push.

#### Informes {#reports-2}

* Se corrigió un problema en el cual los valores aparecían diferentes entre gráficos y tablas.
* Se corrigió un problema que mostraba los valores de notificación push como valores de correo electrónico.
* Se corrigió un problema que mostraba valores como desconocidos cuando se creaba una entrega fuera de una campaña.
* Se corrigió un problema que mostraba datos de informes SMS como datos de aplicaciones móviles.

#### Flujos de trabajo {#workflows-2}

* Ahora puede filtrar los registros de flujo de trabajo (período de tiempo y búsqueda de texto). Para obtener más información, consulte la documentación [detallada](../../automating/using/executing-a-workflow.md#monitoring).
* Ahora hay una opción disponible en los envíos del flujo de trabajo para desactivar la confirmación antes del envío.
* Se ha corregido un problema que impedía configurar una transición de salida en el asistente de creación de envíos recurrentes.
* Se ha corregido un problema que se producía al usar una actividad de consulta de flujo de trabajo basada en un campo de recursos personalizado con una enumeración que tenía muchos valores

## Versión 17.5: mayo de 2017 {#release-17-5---may-2017}

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
   <td> Correo directo<br /> </td> 
   <td> Rompa la barrera digital y conéctese al mundo físico con el primer canal sin conexión de Adobe Campaign Standard, Direct Mail. Esta función le permite personalizar y generar el archivo requerido por los proveedores de correo directo como parte de sus campañas entre canales. Aproveche Direct Mail para volver a atraer clientes o para mejorar la experiencia del cliente con un atractivo punto de contacto táctil que conduce a los clientes a su aplicación, sitio web o tienda.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/about-direct-mail.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Email BCC<br /> </td> 
   <td> Email BCC permite guardar mensajes de correo electrónico únicos enviados a destinatarios individuales, lo que permite a la marca archivar esos mensajes. Al agregar una dirección de correo electrónico CCO a todos los correos electrónicos, los clientes de Adobe Campaign Standard pueden conservar una copia exacta de cada correo electrónico con esta función. Se trata de un requisito jurídico común para el sector de los servicios financieros y ayuda a los centros de atención al cliente a resolver conflictos en tiempo real.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/configuring-email-channel.md#archiving-emails"></a>detallada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-3}

#### Actualizaciones de interfaz {#interface-updates}

* En la barra superior, el **[!UICONTROL Timeline]** vínculo se ha eliminado y reemplazado por un vínculo a **[!UICONTROL Programs & Campaigns]** .

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages}

* Se ha corregido un problema que mostraba un color incorrecto para el estado de la **[!UICONTROL Retry in progress]** entrega. El color era gris en lugar de azul.

#### Flujos de trabajo {#workflows-3}

* Se ha corregido un problema que se producía al cambiar la acción para que se realizara en una **[!UICONTROL Transfer file]** actividad.

#### Informes {#reports-3}

* Se han cambiado los cálculos **[!UICONTROL Spam]** y los **[!UICONTROL Spam rate]** indicadores.
* Las **[!UICONTROL Bounce]** métricas se han mejorado para obtener un resultado más preciso.

#### Notificaciones push {#push-notifications-2}

* Se ha corregido un problema que impedía hacer clic en un evento push en el historial de marketing de un perfil.
* Se ha mejorado el uso de las notificaciones push en los flujos de trabajo.

## Versión 17.4: abril de 2017 {#release-17-4---april-2017}

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
   <td> Funciones mejoradas de edición de imágenes con el SDK creativo<br /> </td> 
   <td> Ahora tiene acceso a un conjunto completo de funciones con tecnología Creative SDK para mejorar las imágenes directamente en el editor de contenido al editar correos electrónicos o páginas de aterrizaje.<br /> Esta función no requiere la adquisición de soluciones adicionales de Creative Cloud.<br /> Para obtener más información, consulte la documentación <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push transaccionales<br /> </td> 
   <td> El canal de la aplicación móvil se ha agregado a las capacidades de mensajería transaccional de Adobe Campaign. Ahora se admiten tres canales para los mensajes transaccionales: correo electrónico, SMS y notificaciones push.<br /> Para obtener más información, consulte la documentación <a href="../../channels/using/transactional-push-notifications.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push recurrentes<br /> </td> 
   <td> Ahora puede configurar las notificaciones push recurrentes en un flujo de trabajo. Puede utilizar las notificaciones push recurrentes en situaciones en las que los clientes esperan actualizaciones periódicas, como recordatorios semanales, para extraer contenido o promociones nuevos.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/push-notification-delivery.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Conector Amazon Simple Storage Service (S3)<br /> </td> 
   <td> El conector Amazon Simple Storage Service (S3) ahora se puede utilizar para importar o exportar datos a Adobe Campaign. Se puede configurar en una actividad de flujo de trabajo. La configuración se realiza en una cuenta externa.<br /> Para obtener más información, consulte la documentación <a href="../../administration/using/external-accounts.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Dreamweaver en directo<br /> </td> 
   <td> La integración entre Adobe Campaign y Dreamweaver ya está activa. Ahora funciona con la última versión oficial de Dreamweaver (17.0.2).<br /> Esto requiere la instalación de la extensión de integración de Adobe Campaign desde aquí: <a href="http://adobe.ly/acdw_addon">http://adobe.ly/acdw_addon</a><br /> Para obtener más información, consulte este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-4}

#### Plataforma {#platform-2}

* Se ha corregido un problema de consumo de memoria.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-1}

* Se corrigió un problema en el cual el contenido no se podía sincronizar correctamente con los cambios más recientes al obtener la vista previa de un mensaje.
* Se ha corregido un problema que impedía crear o eliminar una regla de procesamiento de correo electrónico MX o Domain.
* Se ha corregido un problema que podía impedir que enviara correos electrónicos con varios alias.
* Se ha corregido un problema que impedía que aparecieran registros de entrega de reventado en los registros de envío de la entrega.
* Se ha corregido un problema que provocaba un error al mostrar las direcciones URL seguidas de una entrega sin URL en su contenido.
* Se ha corregido un problema que impedía que los atributos de tamaño de una imagen se aplicaran correctamente en el mensaje enviado.

#### Mensajes transaccionales {#transactional-messages-1}

* El campo rtEventHistoId ya no se expone como un campo de personalización en una plantilla de mensaje transaccional.

#### Páginas de aterrizaje {#landing-pages}

* Hemos optimizado el **[!UICONTROL by email]** filtro utilizado en las páginas de aterrizaje para reconciliar nuevos suscriptores con perfiles de base de datos.
* Se ha corregido un problema que mostraba entradas de texto libre en lugar de casillas de verificación al utilizar campos booleanos en una configuración de formulario.
* Se ha corregido un problema que impedía que se generaran miniaturas de página de aterrizaje.

#### Flujos de trabajo {#workflows-4}

* Se corrigió un error de visualización al editar una actividad **[!UICONTROL End]** o **[!UICONTROL External Signal]** (solo en Safari).
* Se mejoró el mensaje de error que se mostraba al editar una **[!UICONTROL Read Audience]** actividad que contenía una audiencia errónea.
* Se ha corregido un problema que podía provocar un error SQL al ejecutar una actividad de suscripción.

#### Integraciones {#integrations-2}

* Datos de puntos de interés: se ha corregido un error que se producía al contar los suscriptores de ubicación.

#### Audiencias y consultas {#audiences-and-queries}

* Se ha corregido un problema que impedía que se usaran agregados de suma y promedio en una colección del editor de consultas.
* Se ha corregido un problema que podía impedir que el editor de consultas se recargara después de cambiar el recurso del filtro.

#### Informes {#reports-4}

* Se ha corregido un problema que impedía que las métricas de tasa abierta se calcularan correctamente al seleccionar varias filas en una tabla.
* Se corrigió un error que sólo mostraba las métricas como valores enteros. Ahora las métricas se pueden mostrar con decimales.

#### Notificaciones push {#push-notifications-3}

* Se corrigió un problema en el cual no se mostraba un mensaje de error al crear una aplicación de Android vinculada a una aplicación móvil que no se había podido crear en MCPNS.
* Se ha corregido un problema que permitía a un usuario agregar sonidos a una notificación silenciosa.

## Versión 17.2: marzo de 2017 {#release-17-2---march-2017}

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
   <td> Informes dinámicos<br /> </td> 
   <td> Los informes dinámicos proporcionan una nueva generación de informes comerciales totalmente personalizables y en tiempo real. En función de los gráficos y las tablas dinámicas visuales, esta función permite arrastrar y soltar variables y dimensiones para analizar la eficacia y efectividad de las campañas de marketing. Los informes dinámicos también le permiten crear sus propios informes comerciales desde cero y guardarlos para usarlos posteriormente.<br /> Para obtener más información, consulte la documentación <a href="../../reporting/using/about-dynamic-reports.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Dreamweaver (Labs)<br /> </td> 
   <td> Con la integración de Adobe Campaign y Dreamweaver, ahora dispone de un proceso integrado para crear campañas de correo electrónico con las soluciones de Adobe.<br /> Puede editar los correos electrónicos de Adobe Campaign en Dreamweaver y hacer que el contenido se sincronice perfectamente entre ambas soluciones.<br /> Para la versión inicial, la integración está disponible como función "Labs" y solo funciona con Dreamweaver Pre Release Beta. Si desea activarlo, póngase en contacto con AC-DW-integration@adobe.com.<br /> Para obtener más información, consulte este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Optimización del tiempo de envío manual<br /> </td> 
   <td> Ahora puede definir manualmente una hora de envío personalizada por destinatario, en el nivel de entrega o mediante un flujo de trabajo. <br /> Hay dos opciones nuevas disponibles: <br /> 
    <ul> 
     <li> Todos los destinatarios reciben el mensaje teniendo en cuenta su huso horario. </li> 
     <li> Cada destinatario recibe el mensaje en una fecha y hora calculadas definidas por una fórmula. </li> 
    </ul> Para obtener más información, consulte la documentación <a href="../../sending/using/optimizing-the-sending-time.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push Nuevas capacidades<br /> </td> 
   <td> El canal de notificaciones push se ha mejorado con varias funciones nuevas:<br /> 
    <ul> 
     <li> Nueva interfaz de creación </li> 
     <li> Notificaciones silenciosas </li> 
     <li> Push interactivo </li> 
     <li> Compatibilidad con contenido enriquecido </li> 
     <li> Calculadora de tamaño de carga útil </li> 
    </ul> Para obtener más información, consulte la documentación <a href="../../channels/using/about-push-notifications.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: nueva actividad Señal<br /> </td> 
   <td> Activar un flujo de trabajo desde otro flujo de trabajo mediante la nueva actividad <span class="uicontrol">Señal</span> .<br /> Con la capacidad de iniciar un flujo de trabajo desde otro, ahora puede admitir viajes de clientes más complejos. Puede supervisar mejor los viajes de los clientes y reaccionar en caso de que haya problemas.<br /> Se han actualizado varias actividades de flujo de trabajo:<br /> 
    <ul> 
     <li> <span class="uicontrol">Actividad final</span> : una nueva ficha permite especificar un flujo de trabajo que se activará después de que se haya ejecutado esta actividad. </li> 
     <li> <span class="uicontrol">Actualizar actividad de datos</span> : utilice la nueva transición saliente vacía para agregar una actividad <strong>final</strong> que active otro flujo de trabajo. Las transiciones salientes vacías no transmiten ningún dato y no consumen espacio innecesario en el sistema </li> 
    </ul> Para obtener más información, consulte la documentación <a href="../../automating/using/external-signal.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: nueva actividad Leer audiencia<br /> </td> 
   <td> Inicie el proceso de segmentación con una audiencia existente que pueda seleccionar y refinar fácilmente en una actividad.<br /> Para obtener más información, consulte la documentación <a href="../../automating/using/read-audience.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Datos de puntos de interés<br /> </td> 
   <td> Los datos de puntos de interés integran Adobe Campaign con Adobe Analytics para móviles. Una marca puede recopilar datos de las ubicaciones móviles de los usuarios, denominadas <strong>puntos de interés</strong> , cuando éstos abren la aplicación de la marca. Esto permite a la marca aprovechar los flujos de trabajo de Adobe Campaign para enviar mensajes personalizados en función de la ubicación de los usuarios. Este canal aprovecha el SDK del servicio principal de Mobile.<br /> Tenga en cuenta que el uso de esta función requiere Analytics para móviles, que es una solución de pago.<br /> Para obtener más información, consulte la documentación <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de REST<br /> </td> 
   <td> Los recursos vinculados en cualquier nivel a los perfiles o recursos de servicios ya están disponibles en la API.<br /> Para obtener más información, consulte la documentación <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension"></a>detallada.<br /> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-5}

#### General {#general-1}

* Ahora es posible agregar datos de perfil al exportar registros de entrega.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-2}

* Se ha corregido un problema que provocaba que la **[!UICONTROL Request confirmation before sending messages]** opción permaneciera seleccionada incluso después de desmarcarla y guardar la entrega.
* Se ha corregido un problema que podía impedir la cancelación de la publicación de correos electrónicos transaccionales.
* Se corrigió un problema en el cual el contenido no se podía sincronizar correctamente con los cambios más recientes antes de previsualizar una entrega.

#### Páginas de aterrizaje {#landing-pages-1}

* Se corrigió un error que impedía que un usuario editara al hacer clic en el contenido de una página de aterrizaje.

#### Flujos de trabajo {#workflows-5}

* Se ha corregido un problema que podía evitar leer el contenido de la transición de rechazo de una **[!UICONTROL Load file]** actividad.
* Se ha corregido un problema que impedía que las columnas intercambiadas se tuvieran debidamente en cuenta al configurar una **[!UICONTROL Load file]** actividad.

## Versión 17.1: enero de 2017 {#release-17-1---january-2017}

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
   <td> Exportación de registros para informes externos<br /> </td> 
   <td> Exporte registros como los registros de entrega y seguimiento para procesarlos en sus herramientas de informes o de BI preferidas. Puede utilizar flujos de trabajo simples con consultas incrementales para automatizar las exportaciones regulares de nuevos registros.<br /> Además de la disponibilidad de los recursos de registro del selector de recursos, se realizaron mejoras en las actividades de consulta <a href="../../automating/using/incremental-query.md"></a> incremental y del archivo <a href="../../automating/using/extract-file.md">Extract</a> :<br /> 
    <ul> 
     <li> <span class="uicontrol">La consulta</span> incremental ahora le permite utilizar un campo de fecha para recuperar datos nuevos o actualizados. Anteriormente, todos los resultados de ejecuciones anteriores se excluían automáticamente, incluso si se actualizaban desde la última ejecución. </li> 
     <li> <span class="uicontrol">El archivo</span> de extracción ahora puede exportar etiquetas para valores de enumeración en lugar de ID. </li> 
    </ul> Estas actividades están disponibles para los administradores con acceso a todas las unidades geográficas y de organización.<br /> Para obtener más información sobre la exportación de registros, consulte la documentación <a href="../../automating/using/exporting-logs.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> Capacidades de marketing para mensajes transaccionales<br /> </td> 
   <td> Los especialistas en marketing ahora pueden enviar mensajes transaccionales en función de los perfiles de marketing del cliente. Esto les permite:<br /> 
    <ul> 
     <li> Aplicar reglas de tipología de marketing como, por ejemplo, <span class="uicontrol">Dirección</span> bloqueada. </li> 
     <li> Incluya el vínculo de cancelación de suscripción en los mensajes. </li> 
     <li> Agregue los mensajes transaccionales a los informes de entrega global. </li> 
     <li> Aproveche los mensajes transaccionales en el viaje del cliente. </li> 
    </ul> Para obtener más información, consulte la documentación <a href="../../channels/using/profile-transactional-messages.md"></a>detallada.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de mensajería transaccional<br /> </td> 
   <td> La API de mensajería transaccional ya está disponible a través de <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, lo que facilita su uso y supervisión:<br /> 
    <ul> 
     <li> Puede beneficiarse de las funciones de supervisión y generación de informes de la plataforma adobe.io. </li> 
     <li> La autenticación ahora se realiza mediante la autenticación basada en tokens adobe.io en lugar de la lista de direcciones permitidas por IP, lo que simplifica el proceso de seguridad. </li> 
     <li> Todas las API ahora están integradas en una sola plataforma, lo que simplifica más que nunca la adición de capacidades de mensajería transaccional a su integración si ya admite la API de perfil y servicios. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

### Parches {#patches-6}

#### General {#general-2}

* Las **[!UICONTROL Access authorization]** opciones han vuelto a las propiedades de la página de aterrizaje.
* Se ha corregido un problema que podía haber provocado que se procesara una imagen antigua en lugar de la imagen correcta. Esto ocurría si la imagen de origen se había actualizado en la definición de contenido de una página de envío o de aterrizaje.
* Se ha corregido un problema que impedía a los usuarios editar determinados campos en una cuenta externa de SFTP existente.
* Se han corregido varios problemas de la interfaz de usuario. Por ejemplo, ahora los usuarios pueden editar atributos de perfil y guardar las modificaciones sin tener problemas con la interfaz de usuario.

#### Correos electrónicos y mensajes SMS {#emails-and-sms-messages-3}

* Se ha corregido un problema relacionado con las plantillas de envío con contenido HTML que contiene un

#### Notificaciones push {#push-notifications-4}

* Se ha corregido un problema que podía haber impedido el postback de una aplicación al servidor de Adobe Campaign.
* Se ha corregido un problema que podía haber impedido **[!UICONTROL Play a sound]** y **[!UICONTROL Custom fields]** que se tuviera en cuenta en Android.
* Se ha corregido un problema que podía haber provocado que se agregara un carácter de escape adicional a los caracteres Unicode utilizados para los emoticones.
* Cuando se bloquea el autentificador de registro de un suscriptor, el estado correspondiente se actualiza inmediatamente en la lista de suscriptores de la aplicación en Adobe Campaign.

#### Flujos de trabajo {#workflows-6}

* Se ha corregido un problema que podía haber impedido la vista previa de consultas en recursos de eventos (por ejemplo, rtEvent).
* El archivo de rechazo generado por una **[!UICONTROL Load file]** actividad ahora se puede recuperar en su transición de salida y procesar en la siguiente actividad. Por ejemplo, cargue el archivo de rechazo a través de un servidor SFTP mediante **[!UICONTROL Transfer file]** .
* Se ha corregido un problema que podía impedir que un usuario limitara la población de un segmento si **[!UICONTROL Temporary resource]** se seleccionaba en la **[!UICONTROL General]** ficha de **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** las actividades ya no se pueden configurar para activar un flujo de trabajo más de una vez cada 10 minutos.
* Se ha corregido un problema que podía haber impedido que **[!UICONTROL Use common columns]** funcionara correctamente en una **[!UICONTROL Union]** actividad.

#### Integraciones {#integrations-3}

* Se ha corregido un problema que podía haber provocado un error al implementar un activador de evento en Adobe Campaign. Este error se producía cuando se habían agregado los metadatos "Probabilidad de retorno en 30 días" al activador Abandono en Adobe Marketing Cloud.
* Se ha corregido un problema que podía haber provocado que el flujo de trabajo técnico borrara el campo Dimensión de destino al importar audiencias desde el servicio principal Personas. Las consultas posteriores no pudieron recuperar las audiencias importadas.
* Se ha corregido un problema que podía haber provocado que la actividad **[!UICONTROL Save audience]** de un flujo de trabajo fallara al marcar la opción **[!UICONTROL Share in Adobe Marketing Cloud]** .

