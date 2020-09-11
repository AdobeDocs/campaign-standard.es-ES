---
title: Usar la integración con Microsoft Dynamics 365
description: Obtenga información sobre cómo utilizar Microsoft Dynamics 365 con la integración de Campaign Standard
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ca6b418351cfbe539da9f1f4a542c2d7014dfc24
workflow-type: tm+mt
source-wordcount: '1186'
ht-degree: 1%

---


# Usar la integración con Microsoft Dynamics 365

Esta integración realiza varios trabajos:

* **Ingreso**:

   * Incorporar **contactos** de Dynamics 365 en Campaña

   * **Entidades** personalizadas: Incluya tablas personalizadas de Dynamics 365 en Campaña. Obtenga más información [en esta sección](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

* **Egress**: Incorporar eventos de marketing por correo electrónico de ACS a D365 (envío por correo electrónico, apertura, clic, devolución)

* **Exclusión**: Estado de exclusión de sincronización bidireccional (por ejemplo, lista de bloqueados)

Puede encontrar más detalles sobre los flujos de datos [en esta sección](#data-flows).

## Experiencia del usuario de Adobe Campaign Standard

Cuando se crea o modifica un contacto (o se elimina, si está habilitado) en Dynamics 365, se envía a la Campaña.  Estos contactos estarán visibles en la pantalla Perfiles de la Campaña y se pueden dirigir a campañas de marketing.  Consulte la pantalla Perfiles que aparece a continuación.

![](assets/MSdynamicsACS-usage1.png)

Cuando se modifica un atributo de exclusión en la Campaña, se reflejará en Dynamics 365 si ha seleccionado la configuración de exclusión bidireccional o de Campaña a Dynamics 365 y si tiene ese atributo concreto correctamente asignado.

## Experiencia del usuario de Microsoft Dynamics 365

Para la salida, las siguientes eventos de marketing por correo electrónico se envían de Campaña a Dynamics 365 y se muestran en la vista de línea de tiempo de Dynamics 365 como actividades personalizadas:

* Envío de correo electrónico de Adobe Campaign

* Apertura de correo electrónico de Adobe Campaign

* Clic en la dirección URL del correo electrónico de Adobe Campaign

* Devolución de correo electrónico de Adobe Campaign

Para realizar la vista de la cronología de un contacto, vaya a la lista de contactos haciendo clic en el centro de ventas en el menú desplegable Dynamics 365.  A continuación, haga clic en Contactos en la barra de menús de la izquierda y seleccione un contacto.

>[!NOTE]
>
>La aplicación de Adobe Campaign para Dynamics 365 en AppSource deberá estar instalada en la instancia de Dynamics 365 para poder realizar la vista de estos eventos.

Debajo puede ver una instantánea de la pantalla Contacto para &quot;Usuario de Dynamics&quot;.  En la vista Línea de tiempo, verá que se ha enviado un correo electrónico al usuario de Dynamics asociado con el nombre de Campaña &quot;2019LoyaltyCamp&quot; y el nombre de Envío &quot;DM190&quot;.  El usuario de Dynamics abrió el correo electrónico y también hizo clic en una URL del mismo; ambas acciones crearon eventos que también se muestran a continuación.  Si mira hacia la esquina derecha, verá la tarjeta del Asistente de relaciones (RA); actualmente, contiene una tarea para realizar un seguimiento de la dirección URL donde se hizo clic.

![](assets/do-not-localize/MSdynamicsACS-usage4.png)

Consulte a continuación para ver un resumen de la vista de línea de tiempo para el usuario de Dynamics.

![](assets/do-not-localize/MSdynamicsACS-usage5.png)

A continuación se muestra un primer plano de la tarjeta del Asistente de Relaciones (RA).  La aplicación AppSource contiene un flujo de trabajo que busca un evento de clics en URL de correo electrónico de Adobe.  Cuando se produce este evento, se crea una tarea y se establece una fecha de vencimiento.  Esto permite que la tarea aparezca en la tarjeta RA, lo que le proporciona una visibilidad adicional.  Existe un flujo de trabajo similar para los eventos de devolución de correo electrónico de Adobe, agregando una tarea para reconciliar la dirección de correo electrónico no válida.  Estos flujos de trabajo pueden desactivarse en la solución.

![](assets/do-not-localize/MSdynamicsACS-usage6.png)

Si hace clic en el asunto del evento de envío, verá un formulario similar al siguiente.  Los formularios para los eventos de apertura y devolución son similares.

![](assets/do-not-localize/mirror_page_url_send.png)

El formulario para los eventos de clics en direcciones URL de correo electrónico agrega un atributo adicional para la dirección URL en la que se hizo clic:

![](assets/do-not-localize/mirror_page_url_click.png)

A continuación se muestra una lista de los atributos y una descripción:

* Asunto: Asunto del evento; compuesto por el ID de Campaña y el ID de Envío del envío de correo electrónico

* Propietario: Usuario de la aplicación que se crea en los pasos posteriores al aprovisionamiento

* Sobre: El nombre del contacto

* Nombre de campaña: El ID de Campaña en el Campaign Standard

* Nombre del envío: ID de Envío en Campaign Standard

* Fecha de envío/apertura/clic/abono: Fecha y hora en que se creó el evento

* URL de seguimiento: Dirección URL en la que se hizo clic

* URL de página espejo: Dirección URL de la página espejo del correo electrónico que se ha enviado/abierto/en el que se ha hecho clic/devuelto

>[!NOTE]
>
>El período de caducidad de la página espejo de correo electrónico se puede modificar en la pantalla de configuración de la actividad de canal de correo electrónico de la Campaña correspondiente (consulte Parámetros [de período de](../../administration/using/configuring-email-channel.md#validity-period-parameters)validez).

>[!NOTE]
Para la exclusión, cuando se modifica un atributo de exclusión en Dynamics 365, se reflejará en la Campaña si ha seleccionado la configuración de la exclusión bidireccional o de Dynamics 365 to-Campaña y si tiene ese atributo concreto asignado correctamente.

## Flujos de datos {#data-flows}

### Ingreso de entidad personalizada y de contacto

Los registros nuevos y actualizados (y eliminados, si están habilitados) se envían desde la tabla de contacto de Dynamics 365 a la tabla de perfil de Campaña.

Las asignaciones de tabla se pueden configurar para asignar atributos de tabla de Dynamics 365 a atributos de tabla de Campaña. Las asignaciones de tabla se pueden modificar para agregar o quitar atributos, según sea necesario.

La ejecución inicial del flujo de datos está diseñada para transferir todos los registros asignados, incluidos los marcados como &quot;inactivos&quot;; posteriormente, la integración solo procesará actualizaciones incrementales. La excepción a esto es si se configura un filtro; se pueden configurar reglas de filtrado básicas basadas en atributos para determinar qué registros sincronizar con la Campaña.

Se pueden configurar reglas de reemplazo básicas para reemplazar un valor de atributo por otro diferente (por ejemplo, &quot;verde&quot; para &quot;#00FF00&quot;, &quot;F&quot; para 1, etc.).

Según el volumen de registros, es posible que el almacenamiento SFTP de la Campaña deba utilizarse para la transferencia de datos inicial.  Consulte la sección &quot;Transferencia de datos inicial&quot;.

El atributo externalId de la tabla de perfiles de Campaña debe rellenarse con el valor contactId del atributo de contacto de Dynamics 365 para que funcione la llamada de contacto. Las entidades personalizadas de campaña también deben rellenarse con un atributo de ID único de Dynamics 365; sin embargo, este atributo se puede almacenar en cualquier atributo de entidad personalizado de Campaña (es decir, no tiene que ser externalId).

>[!NOTE]
Para el ingreso de entidades personalizadas, el seguimiento de cambios debe habilitarse en Dynamics 365 para las entidades personalizadas sincronizadas.

### Flujo de Evento de mercadotecnia de correo electrónico

Los eventos de marketing por correo electrónico se envían de Campaña a Dynamics 365 para que aparezcan en la vista Cronología.

Tipos de evento de mercadotecnia admitidos:
* Enviar - correo electrónico enviado a destinatario
* Abrir: correo electrónico abierto por destinatario
* Haga clic en: URL dentro del correo electrónico en la que se hizo clic por destinatario
* Rebotar: el correo electrónico al destinatario experimentó una devolución forzada

Los atributos de evento siguientes se muestran en D365:
* Nombre de la campaña de marketing
* Nombre del envío de correo electrónico
* Marca de tiempo
* URL de página espejo de correo electrónico
* Dirección URL en la que se hizo clic (solo eventos)

Los Eventos de mercadotecnia de correo electrónico se pueden habilitar o deshabilitar por tipo (enviar, abrir, hacer clic y rebotar) para que solo los tipos de evento seleccionados se pasen a Dynamics 365.

### Flujo de exclusión

Los valores de exclusión (por ejemplo, lista de bloqueados) se sincronizan entre sistemas; tiene las siguientes opciones para elegir al realizar la integración:
* Dynamics 365 es la fuente de la verdad para las exclusiones: los atributos de exclusión se sincronizarán en una dirección de Dynamics 365 a Campaign Standard
* Campaign Standard es la fuente de la verdad para las exclusiones: los atributos de exclusión se sincronizarán en una dirección desde Campaign Standard a Dynamics 365
* Dynamics 365 AND Campaign Standard son dos fuentes de verdad: los atributos de exclusión se sincronizarán bidireccionalmente entre Campaign Standard y Dynamics 365

Como alternativa, si tiene un proceso independiente para administrar la sincronización de la exclusión entre los sistemas, el flujo de datos de exclusión de la integración puede deshabilitarse.

El cliente debe especificar la asignación de flujo de exclusión, ya que los requisitos comerciales pueden diferir entre compañías.  En el lado de la Campaña, solo se pueden usar los atributos de exclusión de OOTB para la asignación de exclusión:
* blockList
* blockListEmail
* blockListFax
* blockListMobile
* blockListPhone
* blockListPostalMail
* blockListPushnotification
* ccpaOptOut

En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;donot&quot;; sin embargo, también puede utilizar otros atributos para fines de exclusión si los tipos de datos son compatibles.

### Transferencia de datos inicial

Las tablas de Dynamics 365 con más de 500.000 registros deberán exportarse a su almacenamiento SFTP de Campaña para importarse mediante el flujo de trabajo de Campaña.

La transferencia de datos inicial es una transferencia de datos única basada en archivos. Después de la transferencia de datos, la integración utilizará API para las actualizaciones incrementales.
