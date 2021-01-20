---
title: Usar la integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo utilizar Microsoft Dynamics 365 con la integración de Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: fe5d40235abc33c0ea7e929cd2e69b7030cea0b1
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---


# Uso de la integración de Microsoft Dynamics 365

Existen varios flujos de datos que realiza la integración de Adobe Campaign Standard con Microsoft Dynamics 365. Estos flujos se detallan en [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

Puede encontrar más detalles sobre los flujos de datos en este documento en la sección [Flujos de datos](#data-flows).

## Experiencia del usuario de Adobe Campaign Standard

Cuando se crea, modifica o elimina un contacto (si está habilitado) en Microsoft Dynamics 365, se enviará a Campaign Standard. Estos contactos estarán visibles en la pantalla Perfiles de la Campaña y se pueden dirigir a campañas de marketing. Consulte la pantalla Perfiles que aparece a continuación.

![](assets/MSdynamicsACS-usage1.png)

Cuando se modifica un atributo de exclusión en la Campaña, se reflejará en Dynamics 365 si ha seleccionado la configuración de exclusión **unidireccional (Campaña a Microsoft Dynamics 365)** o **bidireccional** y si tiene ese atributo concreto asignado correctamente.

## Experiencia de usuario de Microsoft Dynamics 365

Para la salida, las siguientes eventos de marketing por correo electrónico se envían de Campaña a Dynamics 365 y se muestran en la vista de línea de tiempo de Microsoft Dynamics 365 como actividades personalizadas:

* Envío de correo electrónico de Adobe Campaign

* Apertura de correo electrónico de Adobe Campaign

* Clic en la dirección URL del correo electrónico de Adobe Campaign

* Devolución de correo electrónico de Adobe Campaign

Para realizar la vista de la cronología de un contacto, vaya a la lista de contactos haciendo clic en el centro de ventas en el menú desplegable Dynamics 365. A continuación, haga clic en Contactos en la barra de menús de la izquierda y seleccione un contacto.

>[!NOTE]
>
>La aplicación **Adobe Campaign para Microsoft Dynamics 365** en AppSource deberá estar instalada en la instancia de Microsoft Dynamics 365 para poder realizar la vista de estos eventos. [Más información](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

Debajo puede ver una instantánea de la pantalla Contacto para &quot;Usuario de Dynamics&quot;. En la vista Línea de tiempo, verá que se ha enviado un correo electrónico al usuario de Dynamics asociado con el nombre de Campaña &quot;2019LoyaltyCamp&quot; y el nombre de Envío &quot;DM190&quot;. El usuario de Dynamics abrió el correo electrónico y también hizo clic en una URL del mismo; ambas acciones crearon eventos que también se muestran a continuación. Si mira hacia la esquina derecha, verá la tarjeta del Asistente de relaciones (RA); actualmente, contiene una tarea para realizar un seguimiento de la dirección URL donde se hizo clic.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Consulte a continuación para ver un resumen de la vista de línea de tiempo para el usuario de Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

A continuación se muestra un primer plano de la tarjeta del Asistente de Relaciones (RA). La aplicación AppSource contiene un flujo de trabajo que busca un evento de clics en URL de correo electrónico de Adobe. Cuando se produce este evento, se crea una tarea y se establece una fecha de vencimiento. Esto permite que la tarea aparezca en la tarjeta RA, lo que le proporciona una visibilidad adicional. Existe un flujo de trabajo similar para los eventos de devolución de correo electrónico de Adobe, agregando una tarea para reconciliar la dirección de correo electrónico no válida. Estos flujos de trabajo pueden desactivarse en la solución.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Si hace clic en el asunto del evento de envío, verá un formulario similar al siguiente. Los formularios para los eventos de apertura y devolución son similares.

![](assets/do-not-localize/mirror_page_url_send.png)

El formulario para los eventos de clics en direcciones URL de correo electrónico agrega un atributo adicional para la dirección URL en la que se hizo clic:

![](assets/do-not-localize/mirror_page_url_click.png)

A continuación se muestra una lista de los atributos y una descripción:

* **Asunto**: Asunto del evento; compuesto por el ID de Campaña y el ID de Envío del envío de correo electrónico

* **Propietario**: Usuario de la aplicación que se crea en los pasos posteriores al aprovisionamiento

* **Respecto** a: El nombre del contacto

* **Nombre** de campaña: El ID de Campaña en el Campaign Standard

* **Nombre** de envío: ID de Envío en Campaign Standard

* **Fecha de envío/apertura/clic/abono**: Fecha y hora en que se creó el evento

* **URL** de seguimiento: Dirección URL en la que se hizo clic

* **URL** de página espejo: Dirección URL de la página espejo del correo electrónico que se ha enviado/abierto/en el que se ha hecho clic/devuelto. El período de caducidad de la página espejo de correo electrónico se puede modificar en la pantalla de configuración de la actividad de canal de correo electrónico de la Campaña correspondiente. [Más información](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Para la exclusión, cuando se modifica un atributo de exclusión en Microsoft Dynamics 365, se reflejará en la Campaña si seleccionó la configuración de exclusión **Unidireccional (Campaña a Microsoft Dynamics 365)** o **Bidireccional** y si tiene ese atributo concreto asignado correctamente.

## Flujos de datos {#data-flows}

### Entrada de entidad personalizada y de contacto

Registros nuevos, actualizados y eliminados (Nota: se debe habilitar) se envían desde la tabla de contacto de Microsoft Dynamics 365 a la tabla de perfil de Campaña.

Las asignaciones de tabla se pueden configurar en la interfaz de usuario de la aplicación de integración para asignar atributos de tabla de Microsoft Dynamics 365 a atributos de tabla de Campaña. Las asignaciones de tabla se pueden modificar para agregar o quitar atributos, según sea necesario.

La ejecución inicial del flujo de datos está diseñada para transferir todos los registros asignados, incluidos los marcados como &quot;inactivos&quot;; posteriormente, la integración solo procesará actualizaciones incrementales. La excepción es si se vuelven a reproducir los datos o si se configura un filtro; se pueden configurar reglas de filtrado básicas basadas en atributos para determinar qué registros sincronizar con la Campaña.

Las reglas de reemplazo básicas se pueden configurar en la interfaz de usuario de la aplicación de integración para reemplazar un valor de atributo por otro distinto (por ejemplo, &quot;verde&quot; para &quot;#00FF00&quot;, &quot;F&quot; para 1, etc.).

Según el volumen de registros, es posible que el almacenamiento SFTP de la Campaña deba utilizarse para la transferencia de datos inicial. [Más información](#initial-data-transfer).

El atributo externalId de la tabla de perfiles de Campaña debe rellenarse con el valor contactId del atributo de contacto de Dynamics 365 para que funcione la llamada de contacto. Las entidades personalizadas de campaña también deben rellenarse con un atributo de ID único de Dynamics 365; sin embargo, este atributo se puede almacenar en cualquier atributo de entidad personalizado de Campaña (es decir, no tiene que ser externalId).

>[!NOTE]
>
>Para el ingreso de entidades personalizadas, el seguimiento de cambios debe habilitarse en Dynamics 365 para las entidades personalizadas sincronizadas.

#### Entidades personalizadas

La [integración de Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) admite entidades personalizadas, lo que permite sincronizar las entidades personalizadas de Dynamics 365 con los recursos personalizados correspondientes en Campaña.

Los nuevos datos de los recursos personalizados se pueden utilizar para varios fines, como la segmentación y la personalización.

La integración admite tablas vinculadas y no vinculadas. La vinculación se admite hasta tres niveles (por ejemplo, nivel1->nivel2->nivel3).

>[!IMPORTANT]
>
>Si algún registro de recursos personalizados de Campaña contiene información personal, se aplican recomendaciones específicas. Obtenga más información [en esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).


Al configurar los flujos de datos de entidad personalizados, es importante tener en cuenta lo siguiente:

* La creación y modificación de recursos personalizados de Campaña son operaciones sensibles que deben realizar únicamente los usuarios expertos.
* Para los flujos de datos de entidad personalizados, el seguimiento de cambios debe habilitarse en Dynamics 365 para las entidades personalizadas sincronizadas.
* Si un registro principal y un registro secundario vinculado se crean casi al mismo tiempo en Dynamics 365, debido al procesamiento paralelo de la integración, existe una pequeña posibilidad de que se pueda escribir un nuevo registro secundario en la Campaña antes de su registro principal.

* Si el principal y el secundario están vinculados en el lado de la Campaña mediante la opción **1 vínculo simple de cardinalidad**, el registro secundario permanecerá oculto e inaccesible (a través de la interfaz de usuario o la API) hasta que el registro principal llegue a la Campaña.

* (Suponiendo **1 vínculo simple de cardinalidad** en la Campaña) Si el registro secundario se actualiza o elimina en Dynamics 365 y ese cambio se escribe en la Campaña antes de que el registro principal se muestre en la Campaña (no es probable, pero es una posibilidad remota), esa actualización o eliminación no se procesará en la Campaña y se generará un error. En el caso de la actualización, el registro en cuestión deberá actualizarse de nuevo en Dynamics 365 para sincronizar el registro actualizado. En el caso de la eliminación, el registro en cuestión tendrá que encargarse por separado en la parte de la Campaña, ya que en Dynamics 365 ya no hay ningún registro que eliminar o actualizar.

* Si se encuentra en una situación en la que cree que tiene registros secundarios ocultos y no hay manera de acceder a ellos, puede cambiar temporalmente el tipo de vínculo de cardinalidad a **0 o 1 vínculo simple de cardinalidad** para acceder a esos registros.

En esta sección [encontrará una descripción general más completa de los recursos personalizados de Campaña.](../../developing/using/key-steps-to-add-a-resource.md)

### Flujo de eventos de mercadotecnia por correo electrónico{#email-marketing-event-flow}

Los eventos de marketing por correo electrónico se envían de Campaña a Microsoft Dynamics 365 para que aparezcan en la vista Línea de tiempo.

Tipos de evento de mercadotecnia admitidos:
* Enviar - correo electrónico enviado a destinatario
* Abrir: correo electrónico abierto por destinatario
* Haga clic en: URL dentro del correo electrónico en la que se hizo clic por destinatario
* Rebotar: el correo electrónico al destinatario experimentó una devolución forzada

Los siguientes atributos de evento se muestran en Dynamics 365:
* Nombre de la campaña de marketing
* Nombre del envío de correo electrónico
* Marca de tiempo
* URL de página espejo de correo electrónico
* Dirección URL en la que se hizo clic (solo eventos)

Los Eventos de mercadotecnia de correo electrónico se pueden habilitar o deshabilitar por tipo (enviar, abrir, hacer clic y rebotar) para que solo los tipos de evento seleccionados se pasen a Dynamics 365.

### Flujo de exclusión {#opt-out-flow}

Los valores de exclusión (por ejemplo, lista de bloqueados) se sincronizan entre sistemas; tiene las siguientes opciones para elegir al realizar la integración:

* **Unidireccional (Microsoft Dynamics 365 a Campaña)**: Dynamics 365 es la fuente de la verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección de Dynamics 365 a Campaign Standard&quot;
* **Unidireccional (Campaña a Microsoft Dynamics 365)**: Campaign Standard es la fuente de la verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde Campaign Standard a Dynamics 365
* **Bidireccional**: Dynamics 365 AND Campaign Standard son fuentes de verdad. Los atributos de exclusión se sincronizarán bidireccionalmente entre Campaign Standard y Dynamics 365

Como alternativa, si tiene un proceso independiente para administrar la sincronización de la exclusión entre los sistemas, el flujo de datos de exclusión de la integración puede deshabilitarse.

>[!NOTE]
>
>En la interfaz de usuario de la aplicación de integración, los **casos de uso unidireccional (Microsoft Dynamics 365 a Campaña)** y los **casos de uso de exclusión bidireccional** se configuran en un flujo de trabajo de exclusión independiente. [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>El caso de uso de exclusión **Unidireccional (Campaña a Microsoft Dynamics 365)** es una excepción; está configurado dentro del flujo de trabajo de ingreso (Contacto con Perfil).


El cliente debe especificar la asignación de flujo de exclusión, ya que los requisitos comerciales pueden diferir entre compañías. En el lado de la Campaña, solo se pueden usar los atributos de exclusión de OOTB para la asignación de exclusión:

* lista de bloqueados
* boldListEmail
* boldListFax
* boldListMobile
* boldListPhone
* boldListPostalMail
* boldListPushnotification
* ccpaOptOut

En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;donot&quot;; sin embargo, también puede utilizar otros atributos para fines de exclusión si los tipos de datos son compatibles.

### Transferencia de datos inicial {#initial-data-transfer}

La transferencia de datos inicial puede tardar un tiempo, dependiendo de cuántos registros se estén invirtiendo desde Microsoft Dynamics 365. Después de la transferencia de datos inicial, la integración recogerá las actualizaciones incrementales.
