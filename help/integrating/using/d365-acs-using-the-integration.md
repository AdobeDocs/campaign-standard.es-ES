---
title: Uso de la integración con Microsoft Dynamics 365
description: Aprenda a utilizar Microsoft Dynamics 365 con integración de Campaign Standard
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: fb464183-13bf-4b47-ac27-4b785bafef37
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1607'
ht-degree: 1%

---

# Uso de la integración con Microsoft Dynamics 365

Existen varios flujos de datos que Adobe Campaign Standard Integration with Microsoft Dynamics 365 realiza. Estos flujos se detallan en [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

Puede encontrar más información sobre los flujos de datos en este documento en la sección [Flujos de datos](#data-flows)  para obtener más información.

## Experiencia del usuario de Adobe Campaign Standard

Cuando se crea, modifica o elimina un contacto (si se elimina está habilitado) en Microsoft Dynamics 365, se envía al Campaign Standard. Estos contactos estarán visibles en la pantalla Perfiles de Campaign y se pueden segmentar en las campañas de marketing. Consulte la pantalla Perfiles a continuación.

![](assets/MSdynamicsACS-usage1.png)

Cuando se modifica un atributo de exclusión en Campaign, este se refleja en Dynamics 365 si ha seleccionado la variable **Unidireccional (Campaign a Microsoft Dynamics 365)** o **Bidireccional** configuración de exclusión y si tiene ese atributo en particular asignado correctamente.

## Experiencia del usuario en Microsoft Dynamics 365

Para comenzar, los siguientes eventos de marketing por correo electrónico se envían de Campaign a Dynamics 365 y se muestran en la vista Cronología de Microsoft Dynamics 365 como actividades personalizadas:

* Envío de correo electrónico de Adobe Campaign

* Apertura de correo electrónico de Adobe Campaign

* Clic en la dirección URL del correo electrónico de Adobe Campaign

* Devolución de correo electrónico de Adobe Campaign

Para ver la línea de tiempo de un contacto, vaya a la lista de contactos haciendo clic en el Centro de ventas en el menú desplegable de Dynamics 365. A continuación, haga clic en Contactos en la barra de menú de la izquierda y seleccione un contacto.

>[!NOTE]
>
>La variable **Adobe Campaign para Microsoft Dynamics 365** La aplicación en AppSource deberá estar instalada en la instancia de Microsoft Dynamics 365 para poder ver estos eventos. [Más información](../../integrating/using/d365-acs-configure-d365.md#install-appsource-app).

A continuación puede ver una instantánea de la pantalla Contacto para &quot;Usuario de Dynamics&quot;. En la vista Cronología, verá que se ha enviado un correo electrónico a Dynamics User asociado con los nombres de campaña &quot;2019LoyaltyCamp&quot; y &quot;DM190&quot;. El usuario de Dynamics abrió el correo electrónico y también hizo clic en una dirección URL del mismo; ambas acciones crearon eventos que también se muestran a continuación. Si mira hacia la esquina derecha, verá la tarjeta Asistente de relación (RA); actualmente, contiene una tarea para realizar un seguimiento de la dirección URL donde se hizo clic.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Consulte a continuación para ver un resumen de la vista Cronología del usuario de Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

A continuación se muestra un primer plano de la tarjeta del Asistente de Relaciones (RA). La aplicación AppSource contiene un flujo de trabajo que observa un evento de clic de URL de correo electrónico de Adobe. Cuando se produce este evento, se crea una tarea y se establece una fecha de vencimiento. Esto permite que la tarea se muestre en la tarjeta RA, lo que le proporciona una visibilidad adicional. Hay un flujo de trabajo similar para los eventos de devolución de correo electrónico de Adobe, agregando una tarea para reconciliar la dirección de correo electrónico no válida. Estos flujos de trabajo se pueden desactivar en la solución .

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Si hace clic en el asunto del suceso send , verá un formulario similar al que se muestra a continuación. Los formularios para los eventos de apertura y devolución son similares.

![](assets/do-not-localize/mirror_page_url_send.png)

El formulario para eventos de clic de URL de correo electrónico agrega un atributo adicional para la URL en la que se hizo clic:

![](assets/do-not-localize/mirror_page_url_click.png)

A continuación se muestra una lista de los atributos y una descripción:

* **Asunto**: Asunto del evento; compuesto por el ID de campaña y el ID de entrega de la entrega de correo electrónico

* **Propietario**: El usuario de la aplicación que se crea en los pasos posteriores al aprovisionamiento

* **Acerca de**: Nombre del contacto

* **Nombre de campaña**: El ID de campaña en el Campaign Standard

* **Nombre de la entrega**: El ID de entrega en el Campaign Standard

* **Fecha de envío/apertura/clic/rechazo**: Fecha y hora en que se creó el evento

* **URL de seguimiento**: Dirección URL en la que se hizo clic

* **URL de página espejo**: La dirección URL a la página espejo del correo electrónico que se ha enviado, abierto, en el que se ha hecho clic o rechazado. El periodo de caducidad de la página espejo del correo electrónico se puede modificar en la pantalla de configuración de la actividad correspondiente del canal de correo electrónico de Campaign. [Más información](../../administration/using/configuring-email-channel.md#validity-period-parameters).

>[!NOTE]
>
>Para la exclusión, cuando se modifica un atributo de exclusión en Microsoft Dynamics 365, este se refleja en Campaign si ha seleccionado la variable **Unidireccional (Campaign a Microsoft Dynamics 365)** o **Bidireccional** configuración de exclusión y si tiene ese atributo en particular asignado correctamente.

## Flujos de datos {#data-flows}

### Contacto e ingreso de entidad personalizado

Registros nuevos, actualizados y eliminados (Nota: eliminado debe estar habilitado) se envían desde la tabla de contacto de Microsoft Dynamics 365 a la tabla de perfil de Campaign.

Las asignaciones de tabla se pueden configurar en la interfaz de usuario de la aplicación de integración para asignar atributos de tabla de Microsoft Dynamics 365 a atributos de tabla de Campaign. Las asignaciones de tabla se pueden modificar para añadir o eliminar atributos según sea necesario.

La ejecución inicial del flujo de datos está diseñada para transferir todos los registros asignados, incluidos los marcados como &quot;inactivos&quot;; posteriormente, la integración solo procesará actualizaciones incrementales. La excepción a esto es si los datos se reproducen o si se ha configurado un filtro; se pueden configurar reglas básicas de filtrado basadas en atributos para determinar qué registros sincronizar con Campaign.

Se pueden configurar reglas de reemplazo básicas en la interfaz de usuario de la aplicación de integración para reemplazar un valor de atributo con otro (por ejemplo, &quot;verde&quot; para &quot;#00FF00&quot;, &quot;F&quot; para 1, etc.).

Según el volumen de registros, es posible que el almacenamiento SFTP de Campaign deba utilizarse para la transferencia de datos inicial. [Más información](#initial-data-transfer).

El atributo externalId de la tabla de perfiles de Campaign debe rellenarse con el atributo contactId de Dynamics 365 para que funcione el ingreso de contacto. Las entidades personalizadas de Campaign también deben rellenarse con un atributo de ID único de Dynamics 365; sin embargo, este atributo se puede almacenar en cualquier atributo de entidad personalizado de Campaign (es decir, no tiene que ser externalId).

>[!NOTE]
>
>Para el ingreso de entidades personalizado, el seguimiento de cambios debe estar habilitado dentro de Dynamics 365 para entidades personalizadas sincronizadas.

#### Entidades personalizadas

La variable [Integración con Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) admite entidades personalizadas, lo que permite sincronizar entidades personalizadas de Dynamics 365 con los recursos personalizados correspondientes en Campaign.

Los nuevos datos de los recursos personalizados se pueden utilizar para varios fines, incluida la segmentación y la personalización.

La integración admite tablas vinculadas y no vinculadas. La vinculación se admite hasta tres niveles (es decir, nivel1->nivel2->nivel3).

>[!IMPORTANT]
>
>Si algún registro de recursos personalizados de Campaign contiene información personal, se aplican recomendaciones específicas. Obtenga más información [en esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-data).

Al configurar los flujos de datos de entidad personalizados, es importante tener en cuenta lo siguiente:

* La creación y modificación de los recursos personalizados de Campaign son operaciones confidenciales que solo deben realizar usuarios expertos.
* Para los flujos de datos de entidad personalizados, el seguimiento de cambios debe estar habilitado en Dynamics 365 para las entidades personalizadas sincronizadas.
* Si se crea un registro principal y un registro secundario vinculado casi al mismo tiempo en Dynamics 365, debido al procesamiento paralelo de la integración, existe una pequeña posibilidad de que se pueda escribir un nuevo registro secundario en Campaign antes de su registro principal.

* Si el elemento principal y el secundario están vinculados en el lado de la campaña mediante la variable **1 cardinalidad simple enlace** , el registro secundario permanecerá oculto e inaccesible (a través de la interfaz de usuario o la API) hasta que el registro principal llegue a Campaign.

* (Suponiendo **1 cardinalidad simple enlace** en Campaign) Si el registro secundario se actualiza o elimina en Dynamics 365 y ese cambio se escribe en Campaign antes de que el registro principal se muestre en Campaign (no es probable, pero es una posibilidad remota), esa actualización o eliminación no se procesará en Campaign y se generará un error. En el caso de la actualización, el registro en cuestión deberá actualizarse de nuevo en Dynamics 365 para sincronizar el registro actualizado. En el caso de la eliminación, el registro en cuestión deberá tratarse por separado en Campaign, ya que ya no hay ningún registro en Dynamics 365 para eliminarlo o actualizarlo.

* Si se encuentra en una situación en la que cree que tiene registros secundarios ocultos y no hay forma de acceder a ellos, puede cambiar temporalmente el tipo de vínculo de cardinalidad a **0 o 1 cardinalidad simple enlace** para acceder a esos registros.

Puede encontrar una descripción general más completa de los recursos personalizados de Campaign [en esta sección](../../developing/using/key-steps-to-add-a-resource.md).

### Flujo de evento de marketing por correo electrónico{#email-marketing-event-flow}

Los eventos de marketing por correo electrónico se envían de Campaign a Microsoft Dynamics 365 para que aparezcan en la vista Cronología.

Tipos de eventos de marketing compatibles:
* Envío: correo electrónico enviado al destinatario
* Abrir: correo electrónico abierto por destinatario
* Haga clic en - URL dentro del correo electrónico en el que se hizo clic por destinatario
* Devolución: el correo electrónico al destinatario ha experimentado una devolución grave

Los siguientes atributos de evento se muestran en Dynamics 365:
* Nombre de la campaña de marketing
* Nombre del envío de correo electrónico
* Marca de tiempo
* Dirección URL de la página espejo de correo electrónico
* URL donde se hizo clic (solo eventos de clic)

Los eventos de marketing por correo electrónico se pueden habilitar o deshabilitar por tipo (enviar, abrir, hacer clic, saltar), de modo que solo los tipos de eventos que seleccione se pasen a Dynamics 365.

### Flujo de exclusión {#opt-out-flow}

Los valores de exclusión (por ejemplo, lista de bloqueados de ) se sincronizan entre sistemas; tiene las siguientes opciones para elegir al realizar la incorporación:

* **Unidireccional (Microsoft Dynamics 365 to Campaign)**: Dynamics 365 es una fuente de verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde Dynamics 365 al Campaign Standard&quot;
* **Unidireccional (Campaign a Microsoft Dynamics 365)**: Campaign Standard es la fuente de verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde el Campaign Standard a Dynamics 365
* **Bidireccional**: Dynamics 365 AND Campaign Standard son fuentes de verdad. Los atributos de exclusión se sincronizarán bidireccionalmente entre Campaign Standard y Dynamics 365

Alternativamente, si tiene un proceso independiente para administrar la sincronización de exclusión entre los sistemas, el flujo de datos de exclusión de la integración se puede desactivar.

>[!NOTE]
>
>En la interfaz de usuario de la aplicación de integración, la variable **Unidireccional (Microsoft Dynamics 365 to Campaign)** y **Bidireccional** los casos de uso de exclusión se configuran en un flujo de trabajo de exclusión independiente. [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).
>
>La variable **Unidireccional (Campaign a Microsoft Dynamics 365)** el caso de uso de exclusión es una excepción; está configurado dentro del flujo de trabajo de ingreso (contacto con perfil).

El cliente debe especificar la asignación de flujo de exclusión, ya que los requisitos comerciales pueden diferir entre empresas. En el lado de Campaign, solo se pueden utilizar los atributos de exclusión de OOTB para la asignación de exclusión:

* lista de bloqueados
* denyListEmail
* denyListFax
* denyListMobile
* denyListPhone
* denyListPostalMail
* denyListPushnotification
* ccpaOptOut

En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;no&quot;; sin embargo, también puede utilizar otros atributos para fines de exclusión si los tipos de datos son compatibles.

### Transferencia de datos inicial {#initial-data-transfer}

La transferencia de datos inicial puede tardar un tiempo dependiendo de cuántos registros esté incorporando desde Microsoft Dynamics 365. Después de la transferencia de datos inicial, la integración recogerá las actualizaciones incrementales.
