---
title: Notas de la versión 2017
description: Esta página enumera todas las versiones de 2017 de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: 73a1ec49-fcbc-406b-9590-1ad20da9e73b
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '4613'
ht-degree: 8%

---

# Notas de la versión 2017{#release-notes}

¿Busca una versión específica de Adobe Campaign Standard para 2017?

Cada versión incorpora nuevas funciones y parches. Haga clic en una versión para ver su contenido.

Ver las últimas [actualizaciones de documentación](../../rn/using/documentation-updates.md) para Adobe Campaign Standard. Si está buscando una versión más reciente, consulte esta [página](../../rn/using/release-notes.md).

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
   <td> La administración de fatiga permite crear reglas de fatiga para administrar la comunicación excesiva con los perfiles. Las reglas de fatiga se crean fácilmente, pero son extremadamente flexibles con capacidades como contar mensajes en varios canales (incluidos mensajes transaccionales), solo contar envíos específicos o aplicar reglas a perfiles específicos.<br /> Para obtener más información, consulte la <a href="../../sending/using/fatigue-rules.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Creación de contenido: Importar desde una dirección URL<br /> </td> 
   <td> Importar desde una URL permite recuperar rápidamente el contenido creativo de un sitio web para crear correos electrónicos para cualquier envío. Además, puede optimizar el proceso creativo permitiendo que terceros compartan contenido directamente a través de una URL. El contenido importado se puede utilizar de forma flexible como parte de un solo envío o a nivel de plantilla para garantizar la coherencia de la marca en todas las campañas relacionadas, ya sean mensajes transaccionales o basados en flujos de trabajo, e incluir pruebas A/B o multivariadas. Importar desde una dirección URL convierte y rastrea automáticamente todos los vínculos para supervisar el rendimiento del correo electrónico a través de los informes dinámicos.<br /> Para obtener más información, consulte la <a href="../../designing/using/using-existing-content.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Se ha corregido un problema que podía impedir que los archivos comprimidos de gran tamaño se descomprimieran correctamente.
* Se ha mejorado la seguridad en la administración de marcas. La modificación del nombre y la dirección del remitente de una marca ahora está reservada para los administradores técnicos de Adobe.
* Para mejorar la seguridad, el contenido generado por el usuario (imágenes, páginas espejo, páginas de aterrizaje, etc.) el dominio adobe.com ya no puede servirlo. Ahora es obligatorio que utilice su propio dominio para gestionar estos recursos, mediante el uso de la promoción de la marca.
* Se ha corregido un problema con la interfaz al mostrar y filtrar actividades de marketing.
* Se ha corregido un problema que impedía actualizar los campos de fecha de suscripción con una llamada a la API de POST Rest.

_Correos electrónicos, mensajes SMS y correo postal_

* Se ha corregido un problema que podía impedir que se dirigiera a una audiencia de tipo lista en un mensaje, lo que provocaba que la preparación fallara.
* Se han añadido idiomas que faltaban en las funciones de envío de correo electrónico multilingüe.
* La miniatura de contenido, que se muestra en el panel de envío, ahora se actualiza automáticamente cuando el usuario modifica el contenido y lo guarda.
* Se ha corregido un problema relacionado con la zona horaria que impedía abrir una entrega.

_Notificaciones push_

* Al configurar el canal de notificaciones push, la plataforma del proveedor push para iOS debe ser **apns** y para Android **gcm**.
* Se ha corregido un error que impedía que la aplicación móvil de iOS se agregara en la interfaz de Adobe Campaign.
* Las notificaciones push ahora son compatibles con las aplicaciones móviles Android compatibles con GCM y FCM.
* Se ha corregido un error que impedía guardar contenido al duplicar una plantilla de notificación push.
* Ahora es posible crear o actualizar un perfil de la base de datos de Adobe Campaign conciliando los datos de los usuarios de aplicaciones móviles.
* Adobe Campaign ahora prioriza el procesamiento de las notificaciones push transaccionales sobre las notificaciones push estándar.

_Informes_

* Se ha corregido un problema que impedía que los porcentajes de clics interactivos se mostraran en el contenido del correo electrónico.
* Se ha corregido un problema con la métrica de  de lista de bloqueados que se contaba como un rechazo grave en lugar de una devolución.
* Se ha corregido un problema que provocaba que se mostraran recuentos negativos en los datos de resumen.
* Se ha corregido un problema que contaba perfiles en el segmento de edad incorrecto.
* Las fórmulas de cálculo de rechazos leves y duros han cambiado.

_Flujos de trabajo_

* Se ha corregido un problema en la variable **[!UICONTROL Load file]** actividad que podría provocar errores después de añadir y eliminar manualmente las columnas de la actividad.
* La variable **[!UICONTROL deliverabilityUpdate]** el flujo de trabajo técnico está programado para ejecutarse a las 2 de la mañana, hora del servidor.
* Se ha corregido un problema de seguridad que permitía realizar una exportación de lista sin la función de exportación.
* Se ha corregido un problema con la variable **[!UICONTROL Reconciliation]** actividad.
* Se ha corregido un problema con el uso de caracteres comodín en la variable **[!UICONTROL File Transfer]** actividad.

_Perfiles y audiencias_

* Se ha corregido un problema que podía impedir que una condición de una consulta se tuviera correctamente en cuenta en algunos casos específicos, lo que producía resultados erróneos.
* Se ha corregido un problema que podía impedir que se accediera a los perfiles si estaban segmentados en un mensaje preparado pero nunca enviado y caducado.

_Integraciones_

* Se ha corregido un problema que podía impedir que algunas fuentes de datos creadas para Déclencheur se mostraran y seleccionaran correctamente.

_Recursos personalizados_

* Se ha corregido un problema que se producía en las pantallas de lista en el que las filas de recursos personalizadas se podían mostrar sin datos.
* Se ha corregido un problema que impedía que los campos de tipo booleano con el valor &quot;False&quot; se mostraran en los recursos personalizados.

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
   <td> Presentamos dieciocho plantillas nuevas y adaptables diseñadas en dos hermosos temas: Astro y Feather. Estas plantillas personalizables no dependen del sector y están listas para utilizarse de inmediato. Las plantillas incluyen contenido para diversos casos de uso con el fin de diseñar y entregar sus campañas de marketing por correo electrónico de forma más rápida, eficiente y bonita que nunca.<br /> Para obtener más información, consulte la <a href="../../designing/using/using-reusable-content.md#content-templates">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Informes dinámicos con datos de perfil<br /> </td> 
   <td> Informes dinámicos proporciona informes empresariales totalmente personalizables y en tiempo real. Con esta versión, una potente mejora de los informes dinámicos añade acceso a los datos de perfil, lo que permite realizar análisis demográficos por dimensiones de perfil como sexo, ciudad, código postal y edad, además de datos funcionales de campañas de correo electrónico como aperturas y clics. Con la misma interfaz fácil de usar de arrastrar y soltar, determinar el rendimiento de su campaña de correo electrónico en relación con los segmentos de clientes más importantes es más fácil que nunca.<br /> Para obtener más información, consulte la <a href="../../reporting/using/about-dynamic-reports.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Suscripción masiva con origen y fecha<br /> </td> 
   <td> Con esta mejora de Suscripción masiva, ahora puede almacenar información de suscripción (origen y fecha) directamente en la base de datos de Adobe Campaign Standard a través de la actividad Servicios de suscripción en un flujo de trabajo.<br /> Para obtener más información, consulte la <a href="../../automating/using/subscription-services.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Algunos clientes deben poder aprovechar un ID procedente de Adobe Campaign Standard, ya que no administran una clave única para identificar sus propios registros. Este ID (**ID de ACS**) se puede exportar y utilizar como clave de reconciliación al actualizar los datos. Para obtener más información, consulte la [documentación detallada](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources).
* El protocolo FTP está en desuso. Ahora debería usar SFTP en su lugar. Para no bloquear las implementaciones existentes, las configuraciones existentes en FTP seguirán funcionando como antes, pero la opción no se mostrará para las nuevas actividades.

_Correos electrónicos, mensajes SMS y correo postal_

* Ahora es posible crear nuevos criterios de alerta para utilizarlos en las notificaciones de alerta de envío. Para obtener más información, consulte la [documentación detallada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Las notificaciones de alertas de entrega tienen un nuevo diseño y se ha mejorado la experiencia del usuario del panel de alertas de entrega.
* Ahora, cuando una cuenta externa de enrutamiento está desactivada, se muestra una advertencia en los envíos afectados (correo electrónico, SMS y push) y en la variable **Vista previa** está oculto en estos envíos.
* Se ha corregido un problema que provocaba un error en la vista previa de una prueba A/B en el contenido del correo electrónico cuando se habilitaba texto dinámico en la línea de asunto.

_Mensajes transaccionales_

* Ahora es posible definir cuándo desea enviar un mensaje de seguimiento, por ejemplo, 3 días después de enviar un mensaje transaccional. Para obtener más información, consulte la [documentación detallada](../../channels/using/follow-up-messages.md#sending-a-follow-up-message).
* Ahora es posible definir la fecha desde la cual se deben enviar los mensajes transaccionales vinculados a un evento.
* Se ha corregido un problema que provocaba un error SQL al ejecutar un flujo de trabajo que contenía un mensaje de seguimiento después de eliminar perfiles vinculados a eventos recibidos y procesados.
* Se ha corregido un error que impedía eliminar un perfil vinculado a un evento.
* Se ha corregido un problema que podía impedir que funcionara la redirección de los vínculos rastreados.
* Se ha corregido un problema que impedía deshabilitar el seguimiento de ciertos vínculos en un mensaje de correo electrónico o SMS.

_Informes_

* La variable **Clics activos** se ha mejorado. Además, ahora es posible mostrar clics activos según cada contenido condicional definido en un envío y mostrar clics activos para cada ejecución de envíos recurrentes o mensajes transaccionales. Para obtener más información, consulte la [documentación detallada](../../sending/using/receiving-alerts-when-failures-happen.md#creating-a-delivery-alerting-criterion).
* Se ha corregido un problema que impedía que la métrica de cuarentena recuperara los datos correctos.
* Se ha agregado un nuevo intervalo de tiempo preestablecido al widget de calendario.
* La variable [métricas de informes dinámicos](../../reporting/using/indicator-calculation.md) y [KPI de campañas](../../sending/using/confirming-the-send.md) (mostrado en el panel de mensajes enviados) se han alineado para lograr una mayor coherencia.
* Se ha corregido un problema que podría provocar que la canalización se bloquee en debian 7.

_Flujos de trabajo_

* Se ha corregido un problema que podía impedir que funcionara la retención de archivos importada.

_Integraciones_

* Los eventos y eVars ahora son compatibles con la integración de Analytics y Campaign.
* Al enviar un correo electrónico con el contenido del carro abandonado, el parámetro de carga útil para los elementos eliminados del carro de compras ahora es opcional.

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
   <td> Defina y ejecute envíos multilingües de correo electrónico y SMS a través de un único envío basado en el idioma preferido de los clientes segmentados automáticamente. Informe del rendimiento de cada envío en función del idioma y los niveles individuales.<br /> Cada vez más empresas se enfrentan al desafío de entregar contenido en múltiples idiomas a medida que crecen en el país y en el extranjero. Como tal, la racionalización de la entrega de mensajes localizados es una parte clave de una estrategia eficaz de comunicación con los clientes para las empresas multinacionales; empresas de países con lenguas múltiples; y empresas que desean personalizar aún más su contenido en el nivel lingüístico independientemente de dónde residan los clientes. Para obtener más información, consulte la <a href="../../channels/using/creating-a-multilingual-email.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones de Adobe Campaign<br /> </td> 
   <td> Reciba notificaciones sobre actividades importantes del sistema directamente en Adobe Campaign Standard. Se le notificará, por ejemplo, sobre el progreso de los envíos en curso o cuando haya un error en un flujo de trabajo.<br /> Las notificaciones en tiempo real mantienen informadas a las partes interesadas y permiten a los usuarios actuar de forma inmediata y directa sobre las notificaciones de actividades desde la aplicación. El resultado para los equipos es agilidad avanzada, eficiencia y una ejecución más fluida de las campañas. Para obtener más información, consulte la <a href="../../administration/using/sending-internal-notifications.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Alerta de entrega<br /> </td> 
   <td> Además de ver las notificaciones directamente en Adobe Campaign Standard, Adobe Campaign ahora también proporciona un sistema de alerta por correo electrónico para enviar alertas por correo electrónico de déclencheur a usuarios o partes interesadas externas de actividades importantes del sistema. Cree, administre y reciba alertas y tableros personalizables para realizar un seguimiento de los envíos correctos o fallidos.<br /> Las alertas de entrega de Adobe Campaign aumentan la eficacia al mantener informados automáticamente a todos los usuarios de Adobe Campaign implicados en una empresa sobre el estado de ejecución de la entrega, por correo electrónico y por panel. Para obtener más información, consulte la <a href="../../sending/using/receiving-alerts-when-failures-happen.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> ID declarado cifrado en fuentes de datos<br /> </td> 
   <td> Envíe déclencheur de correo electrónico y SMS sin necesidad de un perfil existente en Campaign utilizando información de contacto cifrada (dirección de correo electrónico o número de teléfono) como ID declarado. Adobe Campaign Standard puede descodificar los ID declarados cifrados, por lo que ahora Campaign puede crear nuevos perfiles comercializables al recibir audiencias de otras soluciones de Experience Cloud que contengan contactos previamente desconocidos.<br /> Diríjase a clientes y posibles clientes desconocidos en tiempo real mediante correo electrónico y SMS para mejorar la lealtad en su base de clientes existente y adquirir nuevos clientes, respectivamente. Aproveche al máximo los datos de cookies de origen (de Adobe Audience Manager*) una vez que los clientes potenciales se autentiquen y aprovechen esta información en Adobe Campaign. <br /> *Se requiere Adobe Audience Manager. Para obtener más información, consulte la <a href="../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Uso compartido de KPI de Campaign a Analytics<br /> </td> 
   <td> Comparta datos de campaña con Adobe Analytics para medir las métricas de marketing por correo electrónico de Campaign junto con otras iniciativas de marketing y publicidad a través de la conversión, unificando el comportamiento previo y posterior al clic.<br /> Rastree el rendimiento general directamente y descubra sinergias con programas externos en Analytics. Aplique el aprendizaje de esta vista consolidada en sus campañas; mejora en última instancia las tasas de apertura, clics y conversión, lo que aumenta los ingresos y el rendimiento general de la campaña. <br /> Adobe Analytics es obligatorio. Para obtener más información, consulte la <a href="../../integrating/using/about-campaign-analytics-integration.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Canal de correo postal: Devolver al remitente<br /> </td> 
   <td> Ahora se admiten los intercambios de archivos planos con proveedores de correo directo que incorporan información de retorno al remitente. Esta mejora en el canal de correo postal permite excluir las direcciones postales correspondientes de futuras comunicaciones.<br /> Esto permite que se notifique a los especialistas en marketing de una dirección incorrecta y que se pongan en contacto con el cliente a través de otros canales o que les anime a actualizar su dirección postal. Esto también reduce el número de dólares de marketing desperdiciados, ya que los especialistas en marketing evitan enviar correos a direcciones incorrectas. <br /> Correo postal está disponible como canal complementario. Para obtener más información, consulte la <a href="../../channels/using/return-to-sender.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_General_

* Se ha corregido un problema que permitía a cualquier usuario exportar listas. Ahora solo los usuarios con la variable **[!UICONTROL Export]** se permiten.

_Correos electrónicos, mensajes SMS y correo postal_

* Se ha corregido un problema con la variable **updateDeliveryExecInfo** flujo de trabajo que configura la variable **Para entregar** indicador a 0 para entregas SMS.
* En el **Parámetros avanzados** de las propiedades de la plantilla de envío, la variable **Enrutamiento** la lista desplegable ahora solo muestra las cuentas externas correspondientes al tipo de mensaje de plantilla. Por ejemplo, una plantilla de envíos de correo electrónico solo muestra cuentas externas de correo electrónico.
* Se ha corregido un problema con la variable **[!UICONTROL Text]** formato de correo electrónico preferido definido para perfiles de prueba.
* Se ha corregido un problema que provocaba un error de Javascript al seleccionar la zona horaria predeterminada en la pantalla de definición de programación de una entrega.
* Se ha corregido un problema que impedía que las trampas aparecieran en los registros de envío.
* En la pantalla de selección de plantillas del asistente para la creación de envíos, las plantillas de prueba A/B y de seguimiento ahora están ocultas de forma predeterminada. Para obtener más información, consulte [documentación detallada](../../channels/using/creating-an-email.md).
* Se ha corregido un problema que permitía a cualquier usuario enviar envíos. Ahora solo los usuarios con la variable **[!UICONTROL Start deliveries]** se permiten. Para obtener más información, consulte [documentación detallada](../../sending/using/confirming-the-send.md).

_Notificaciones push_

* Se ha corregido un problema con la variable **Punto final del seguimiento de campaña** URL que impidió la creación de informes.
* Se ha corregido un problema que impedía que el título de la notificación push se mostrara en los dispositivos Android.
* Se ha corregido un problema que impedía que la notificación push se mostrara en los dispositivos iOS cuando la notificación push solo contenía un título (y nada en el cuerpo del mensaje).
* Se ha corregido un problema que obligaba a rastrear las URL de archivos adjuntos de medios de una entrega, lo que impedía que los vídeos e imágenes se incrustaran en la entrega. El seguimiento de direcciones URL del tipo mediaAttachmentURL ahora está desactivado de forma predeterminada para las notificaciones push.

_Informes_

* Se ha corregido un problema por el que los valores aparecían diferentes entre gráficos y tablas.
* Se ha corregido un problema que mostraba los valores de las notificaciones push como valores de correo electrónico.
* Se ha corregido un problema que mostraba valores como desconocidos cuando se creaba una entrega fuera de una campaña.
* Se ha corregido un problema que mostraba los datos de informes SMS como datos de aplicaciones móviles.

_Flujos de trabajo_

* Ahora puede filtrar los registros de flujo de trabajo (periodo de tiempo y búsqueda de texto). Para obtener más información, consulte [documentación detallada](../../automating/using/monitoring-workflow-execution.md).
* Ahora hay disponible una opción en los envíos del flujo de trabajo para desactivar la confirmación antes del envío.
* Se ha corregido un problema que impedía configurar una transición saliente en el asistente de creación de envíos recurrentes.
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
   <td> Correo directo<br /> </td> 
   <td> Rompa la barrera digital y conéctese al mundo físico con el primer canal sin conexión de Adobe Campaign Standard, Direct Mail. Esta función le permite personalizar y generar el archivo requerido por los proveedores de correo postal como parte de sus campañas multicanal. Aproveche Direct Mail para volver a atraer clientes o para mejorar la experiencia del cliente con un atractivo punto de contacto táctil que lleve a los clientes a su aplicación, sitio web o tienda.<br /> Para obtener más información, consulte la <a href="../../channels/using/about-direct-mail.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Correo electrónico CCO<br /> </td> 
   <td> Email BCC permite guardar mensajes de correo electrónico exclusivos enviados a destinatarios individuales, lo que permite a la marca archivar esos mensajes. Al añadir una dirección de correo electrónico CCO a todos los correos electrónicos, los clientes de Adobe Campaign Standard pueden mantener una copia exacta de cada correo electrónico con esta función. Se trata de un requisito legal común para el sector de los servicios financieros y es útil para ayudar a los centros de servicios al cliente a resolver conflictos en tiempo real.<br /> Para obtener más información, consulte la <a href="../../sending/using/archiving.md">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Actualizaciones de interfaz_

* En la barra superior, la variable **[!UICONTROL Timeline]** el vínculo se ha eliminado y se ha sustituido por un vínculo a **[!UICONTROL Programs & Campaigns]** .

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema que mostraba un color incorrecto para el **[!UICONTROL Retry in progress]** estado de entrega. El color era gris en lugar de azul.

_Flujos de trabajo_

* Se ha corregido un problema que se producía al cambiar la acción que se va a realizar en una **[!UICONTROL Transfer file]** actividad.

_Informes_

* La variable **[!UICONTROL Spam]** y **[!UICONTROL Spam rate]** se han cambiado los cálculos del indicador.
* La variable **[!UICONTROL Bounce]** se han mejorado para obtener un resultado más preciso.

_Notificaciones push_

* Se ha corregido un problema que impedía hacer clic en un evento push en el historial de marketing de un perfil.
* Se ha mejorado el uso de las notificaciones push en los flujos de trabajo.

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
   <td> Ahora tiene acceso a un conjunto completo de funciones con tecnología Creative SDK para mejorar sus imágenes directamente en el editor de contenido al editar correos electrónicos o páginas de aterrizaje.<br /> Esta función no requiere la adquisición de soluciones de Creative Cloud adicionales.<br /> Para obtener más información, consulte la <a href="../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push transaccionales<br /> </td> 
   <td> El canal de aplicaciones móviles se ha agregado a las funciones de mensajería transaccional de Adobe Campaign. Ahora se admiten tres canales para mensajes transaccionales: correo electrónico, SMS y notificaciones push.<br /> Para obtener más información, consulte la <a href="../../channels/using/transactional-push-notifications.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push recurrentes<br /> </td> 
   <td> Ahora puede configurar notificaciones push recurrentes en un flujo de trabajo. Puede utilizar notificaciones push recurrentes en situaciones en las que los clientes esperen actualizaciones periódicas, como recordatorios semanales, para comprobar el contenido nuevo o las promociones.<br /> Para obtener más información, consulte la <a href="../../automating/using/push-notification-delivery.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Conector Amazon Simple Storage Service (S3)<br /> </td> 
   <td> El conector Amazon Simple Storage Service (S3) ahora se puede utilizar para importar o exportar datos a Adobe Campaign. Se puede configurar en una actividad de flujo de trabajo. La configuración se realiza en una cuenta externa.<br /> Para obtener más información, consulte la <a href="../../administration/using/external-accounts.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Dreamweaver en directo<br /> </td> 
   <td> La integración entre Adobe Campaign y Dreamweaver ya está activa. Ahora funciona con la última versión oficial publicada de Dreamweaver (17.0.2).<br /> Esto requiere la instalación de la extensión de integración de Adobe Campaign. Para obtener más información, consulte <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=es">video</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_Plataforma_

* Se ha corregido un problema de consumo de memoria.

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema en el cual el contenido no se podía sincronizar correctamente con los cambios más recientes al obtener la vista previa de un mensaje.
* Se ha corregido un problema que impedía crear o eliminar una regla de procesamiento de correo electrónico MX o Domain.
* Se ha corregido un problema que podía impedir que se enviaran correos electrónicos con varios alias.
* Se ha corregido un problema que impedía que los registros de envío de trampa aparecieran en los registros de envío de la entrega.
* Se ha corregido un problema que provocaba un error al mostrar las direcciones URL rastreadas de una entrega sin ninguna dirección URL en su contenido.
* Se ha corregido un problema que impedía que los atributos de tamaño de una imagen se aplicaran correctamente en el mensaje enviado.

_Mensajes transaccionales_

* El campo rtEventHistoId ya no se expone como campo de personalización en una plantilla de mensaje transaccional.

_Páginas de aterrizaje_

* Hemos optimizado el **[!UICONTROL by email]** filtro utilizado en páginas de aterrizaje para reconciliar nuevos suscriptores con perfiles de base de datos.
* Se ha corregido un problema que mostraba entradas de texto libre en lugar de casillas de verificación al usar campos booleanos en una configuración de formulario.
* Se ha corregido un problema que impedía que se generaran miniaturas de página de aterrizaje.

_Flujos de trabajo_

* Se ha corregido un error de visualización al editar un **[!UICONTROL End]** o **[!UICONTROL External Signal]** actividad (solo en Safari).
* Se ha mejorado el mensaje de error que se mostraba al editar un **[!UICONTROL Read Audience]** actividad que contiene una audiencia errónea.
* Se ha corregido un problema que podría provocar un error SQL al ejecutar una actividad de suscripción.

_Integraciones_

* Datos de puntos de interés: se ha corregido un error que se producía al contar los suscriptores de ubicación.

_Audiencias y consultas_

* Se ha corregido un problema que impedía que se usaran agregados de suma y promedio en una colección en el editor de consultas.
* Se ha corregido un problema que podía impedir que el editor de consultas se recargara después de cambiar el recurso del filtro.

_Informes_

* Se ha corregido un problema que impedía que las métricas de tasa de apertura se calcularan correctamente al seleccionar varias filas en una tabla.
* Se ha corregido un error que solo mostraba las métricas como valores enteros. Ahora, las métricas se pueden mostrar con decimales.

_Notificaciones push_

* Se ha corregido un problema por el que no se mostraba un mensaje de error al crear una aplicación de Android vinculada a una aplicación móvil que no se había podido crear en MCPNS.
* Se ha corregido un problema que permitía a un usuario añadir sonidos a una notificación silenciosa.

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
   <td> Informes dinámicos proporciona una nueva generación de informes empresariales en tiempo real y totalmente personalizables. Basado en gráficos y tablas dinámicas visuales, esta función permite arrastrar y soltar variables y dimensiones para analizar la eficacia y efectividad de las campañas de marketing. Los informes dinámicos también le permiten crear sus propios informes empresariales desde cero y guardarlos para usarlos más adelante.<br /> Para obtener más información, consulte la <a href="../../reporting/using/about-dynamic-reports.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Integración de Dreamweaver (Labs)<br /> </td> 
   <td> Con la integración de Adobe Campaign y Dreamweaver, ahora tiene un proceso integrado para crear campañas de correo electrónico con soluciones de Adobe.<br /> Puede editar correos electrónicos de Adobe Campaign en Dreamweaver y hacer que el contenido se sincronice perfectamente entre ambas soluciones.<br /> Para la versión inicial, la integración está disponible como función "Labs" y solo funciona con Dreamweaver Pre Release Beta. Si desea activarlo, póngase en contacto con AC-DW-integration@adobe.com.<br /> Para obtener más información, consulte <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html">video</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Optimización del tiempo de envío manual<br /> </td> 
   <td> Ahora puede definir manualmente una hora de envío personalizada por destinatario (en el nivel de envío o mediante un flujo de trabajo). <br /> Hay dos nuevas opciones disponibles: <br /> 
    <ul> 
     <li> Todos los destinatarios reciben el mensaje teniendo en cuenta su huso horario. </li> 
     <li> Cada destinatario recibe el mensaje en una fecha y hora calculadas definidas por una fórmula. </li> 
    </ul> Para obtener más información, consulte la <a href="../../sending/using/optimizing-the-sending-time.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Notificaciones push Nuevas funciones<br /> </td> 
   <td> El canal de notificaciones push se ha mejorado con varias funciones nuevas:<br /> 
    <ul> 
     <li> Nueva interfaz de creación </li> 
     <li> Notificaciones silenciosas </li> 
     <li> Push interactivo </li> 
     <li> Compatibilidad con contenido enriquecido </li> 
     <li> Calculadora de tamaño de carga útil </li> 
    </ul> Para obtener más información, consulte la <a href="../../channels/using/about-push-notifications.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: nueva actividad Señal<br /> </td> 
   <td> Déclencheur de un flujo de trabajo desde otro flujo de trabajo mediante el nuevo <span class="uicontrol">Señal</span> actividad.<br /> Con la capacidad de iniciar un flujo de trabajo desde otro, ahora puede admitir recorridos de cliente más complejos. Puede supervisar mejor los recorridos de los clientes y reaccionar en caso de que haya problemas.<br /> Se han actualizado varias actividades de flujo de trabajo:<br /> 
    <ul> 
     <li> <span class="uicontrol">Fin</span> actividad: una nueva pestaña le permite especificar un flujo de trabajo para el déclencheur después de ejecutar esta actividad. </li> 
     <li> <span class="uicontrol">Actualización de datos</span> actividad: utilice la nueva transición saliente vacía para añadir un <strong>Fin</strong> actividad que déclencheur otro flujo de trabajo. Las transiciones salientes vacías no transmiten datos ni consumen espacio innecesario en el sistema </li> 
    </ul> Para obtener más información, consulte la <a href="../../automating/using/external-signal.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Flujos de trabajo: nueva actividad Leer audiencia<br /> </td> 
   <td> Inicie el proceso de segmentación con una audiencia existente que pueda seleccionar y refinar fácilmente en una actividad.<br /> Para obtener más información, consulte la <a href="../../automating/using/read-audience.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Datos de puntos de interés<br /> </td> 
   <td> Los datos de Puntos de interés integran Adobe Campaign con Adobe Analytics para Mobile. Una marca puede recopilar datos de las ubicaciones móviles de los usuarios, denominadas <strong>Puntos de interés</strong> : cuando los usuarios abren la aplicación de la marca. Esto permite a la marca aprovechar los flujos de trabajo de Adobe Campaign para enviar mensajes personalizados en función de la ubicación de los usuarios. Este canal aprovecha el SDK del servicio principal de Mobile.<br /> Tenga en cuenta que esta función requiere Analytics para dispositivos móviles, que es una solución de pago.<br /> Para obtener más información, consulte la <a href="../../integrating/using/about-campaign-points-of-interest-data-integration.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de REST<br /> </td> 
   <td> Los recursos vinculados en cualquier nivel a los perfiles o recursos de servicios ahora están disponibles en la API.<br /> Para obtener más información, consulte la <a href="../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension">documentación detallada</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_General_

* Ahora es posible añadir datos de perfil al exportar registros de envío.

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema que provocaba que la variable **[!UICONTROL Request confirmation before sending messages]** para permanecer seleccionada incluso después de desmarcarla y guardar la entrega.
* Se ha corregido un problema que podía impedir la cancelación de la publicación de correos electrónicos transaccionales.
* Se ha corregido un problema por el cual el contenido no se podía sincronizar correctamente con los cambios más recientes antes de previsualizar un envío.

_Páginas de aterrizaje_

* Se ha corregido un error que impedía que un usuario editara al hacer clic en el contenido de una página de aterrizaje.

_Flujos de trabajo_

* Se ha corregido un problema que podía impedir la lectura del contenido de la transición de rechazo de una **[!UICONTROL Load file]** actividad.
* Se ha corregido un problema que impedía que las columnas intercambiadas se tuvieran debidamente en cuenta al configurar un **[!UICONTROL Load file]** actividad.

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
   <td> Exportación de registros para informes externos<br /> </td> 
   <td> Exporte registros como "logs" de envío y seguimiento para procesarlos en sus herramientas preferidas de creación de informes o BI. Puede utilizar flujos de trabajo simples con consultas incrementales para automatizar las exportaciones regulares de registros nuevos.<br /> Además de la disponibilidad de los recursos de registro del selector de recursos, se han realizado mejoras en el <a href="../../automating/using/incremental-query.md">Consulta incremental</a> y <a href="../../automating/using/extract-file.md">Extraer archivo</a> actividades:<br /> 
    <ul> 
     <li> <span class="uicontrol">Consulta incremental</span> ahora le permite utilizar un campo de fecha para recuperar datos nuevos o actualizados. Anteriormente, todos los resultados de ejecuciones anteriores se excluían automáticamente, incluso si se actualizaban desde la última ejecución. </li> 
     <li> <span class="uicontrol">Extraer archivo</span> Ahora puede exportar etiquetas para valores de enumeración en lugar de ID. </li> 
    </ul> Estas actividades están disponibles para los administradores con acceso a todas las unidades geográficas y de organización.<br /> Para obtener más información sobre la exportación de registros, consulte la <a href="../../automating/using/exporting-logs.md">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> Funciones de marketing para mensajes transaccionales<br /> </td> 
   <td> Los especialistas en marketing ahora pueden enviar mensajes transaccionales basados en perfiles de marketing de los clientes. Esto les permite:<br /> 
    <ul> 
     <li> Aplicar reglas de tipología de marketing como <span class="uicontrol">Dirección en lista de bloqueados</span> . </li> 
     <li> Incluir vínculos de baja en los mensajes. </li> 
     <li> Añadir mensajes transaccionales al sistema de informes de envío global. </li> 
     <li> Aprovechar mensajes transaccionales en el recorrido del cliente. </li> 
    </ul> Para obtener más información, consulte la <a href="../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities">documentación detallada</a>.<br /> </td> 
  </tr> 
  <tr> 
   <td> API de mensajería transaccional<br /> </td> 
   <td> La API de mensajería transaccional ya está disponible a través de <a href="https://docs.campaign.adobe.com/doc/standard/en/adobeio.html">adobe.io</a>, facilitando su uso y monitoreando:<br /> 
    <ul> 
     <li> Puede beneficiarse de las funcionalidades de supervisión e informes de la plataforma adobe.io. </li> 
     <li> La autenticación ahora se realiza mediante la autenticación basada en tokens de adobe.io en lugar de la inclusión en la lista de permitidos IP, lo que simplifica el proceso de seguridad. </li> 
     <li> Todas las API están ahora integradas en una sola plataforma, lo que facilita más que nunca la adición de funciones de mensajería transaccional a su integración si ya es compatible con la API de perfil y servicios. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

**Parches**

_General_

* La variable **[!UICONTROL Access authorization]** se han devuelto a las propiedades de la página de aterrizaje.
* Se ha corregido un problema que puede haber provocado que se procese una imagen antigua en lugar de la imagen correcta. Esto ocurría si la imagen de origen se había actualizado en la definición de contenido de una página de entrega o de aterrizaje.
* Se ha corregido un problema que impedía que los usuarios editaran ciertos campos en una cuenta externa SFTP existente.
* Se han corregido varios problemas de la interfaz de usuario. Por ejemplo, los usuarios ahora pueden editar atributos de perfil y guardar modificaciones sin tener problemas con la interfaz de usuario.

_Correos electrónicos y mensajes SMS_

* Se ha corregido un problema relativo a las plantillas de envío con contenido de HTML que contiene un

_Notificaciones push_

* Se ha corregido un problema que podía haber impedido el postback de una aplicación al servidor de Adobe Campaign.
* Se ha corregido un problema que podría haber evitado **[!UICONTROL Play a sound]** y **[!UICONTROL Custom fields]** para tener en cuenta para Android.
* Se ha corregido un problema que podría haber hecho que se agregara un carácter de escape adicional a los caracteres Unicode utilizados para Emojis.
* Cuando se añade un token de registro de un suscriptor a la  de lista de bloqueados, el estado correspondiente se actualiza inmediatamente en la lista de suscriptores de la aplicación en Adobe Campaign.

_Flujos de trabajo_

* Se ha corregido un problema que podía haber impedido previsualizaciones de consultas sobre recursos de eventos (por ejemplo, rtEvent).
* El archivo rechazado generado por un **[!UICONTROL Load file]** ahora se puede recuperar la actividad en su transición saliente y procesarla en la siguiente actividad. Por ejemplo, cargue el archivo rechazado a través de un servidor SFTP utilizando **[!UICONTROL Transfer file]** .
* Se ha corregido un problema que podía haber impedido a un usuario limitar la población de un segmento si **[!UICONTROL Temporary resource]** se ha seleccionado en la variable **[!UICONTROL General]** pestaña **[!UICONTROL Segmentation]** .
* **[!UICONTROL Scheduler]** las actividades ya no se pueden configurar para que se almacenen en déclencheur en un flujo de trabajo más de una vez cada 10 minutos.
* Se ha corregido un problema que podría haber evitado **[!UICONTROL Use common columns]** desde que funciona correctamente en un **[!UICONTROL Union]** actividad.

_Integraciones_

* Se ha corregido un problema que podía haber provocado un error al implementar un déclencheur de eventos en Adobe Campaign. Este error se producía cuando los metadatos &quot;Probabilidad de retorno en 30 días&quot; se habían agregado al déclencheur de abandono en Adobe Marketing Cloud.
* Se ha corregido un problema que podía haber provocado que el flujo de trabajo técnico borrara el campo Dimension de destino al importar audiencias desde el servicio principal Personas. Las consultas posteriores no pudieron recuperar las audiencias importadas.
* Se ha corregido un problema que podría haber provocado que la variable **[!UICONTROL Save audience]** actividad de un flujo de trabajo que falla cuando la opción **[!UICONTROL Share in Adobe Marketing Cloud]** se ha comprobado.
