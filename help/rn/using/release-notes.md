---
solution: Campaign Standard
product: campaign
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Información general
role: Business Practitioner
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 887396a0871a8ed93642c55a49c8737f5c98bfc2
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Última versión{#latest-release}

## Versión 21.2: junio de 2021 {#release-21-2---june-2021}

A continuación se enumeran las nuevas funciones, mejoras y correcciones incluidas en la próxima versión del Campaign Standard. A continuación se enumeran las nuevas funciones, mejoras y correcciones incluidas en esta versión del Campaign Standard.

**Mejoras**

* Al diseñar una página de aterrizaje, ahora puede añadir una casilla de verificación obligatoria que los perfiles deben seleccionar antes de enviar el formulario. Para obtener más información, consulte la [documentación detallada](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox).

* Para la integración de Déclencheur, se ha mejorado el mensaje de error que se muestra cuando no hay datos de reconciliación en la carga útil de déclencheur: &quot;Faltan datos de alias en la carga útil&quot;.

* Se ha mejorado el rendimiento para recuperar notificaciones push de la cola.

**Otros cambios**

* El mecanismo de firma de URL para el seguimiento de vínculos se ha deshabilitado para evitar que un problema que estaba causando que algunos vínculos de seguimiento válidos y firmados se bloquearan incorrectamente después de ser modificados por herramientas de seguridad de terceros.

* En los envíos de varias variantes, los usuarios ya no pueden crear copias de idioma si se ha eliminado la variante predeterminada. Ahora se muestra un mensaje durante la creación de la copia de idioma. (CAMP-48235)

* El proceso de eliminación de perfiles en 2 pasos (obsoleto a partir de la versión 19.4 de Campaign) ahora está desactivado de forma predeterminada. Anteriormente, debía deshabilitarse manualmente desde la interfaz de Campaign antes de utilizar el servicio principal de privacidad. Si no lo hace, las solicitudes de eliminación permanecerán en estado pendiente sin completarse.

* En los informes dinámicos, se ha eliminado el segmento **Exclude Proof**. (CAMP-46161)

* Se ha añadido un nuevo mensaje de advertencia para informar al usuario cuando se carga un certificado iOS sin el valor platformPrincipal en la aplicación Campaign.

* El tamaño máximo de un correo electrónico ahora se establece en 100 MB de forma predeterminada. Este límite permite evitar cualquier error que pueda aumentar indefinidamente el tamaño de un correo electrónico, lo que puede provocar un bloqueo del sistema. (CAMP-47445) [Obtenga más información](../../sending/using/design-and-personalize.md#email-size)

* Los usuarios estándar ahora pueden usar la integración del servicio principal de recursos con el diseñador de correo electrónico.

* Se ha añadido un nuevo mensaje para confirmar que la migración de una aplicación push v4 a una aplicación push v5 se ha realizado correctamente.

* Durante la creación de tokens JSONWeb para autenticarse en la API de Campaign Standard, los perfiles de producto ahora se **consideran**. Esto significa que las unidades organizativas y las funciones asignadas al grupo de seguridad (que coincide con el perfil del producto en AdobeIO) se aplicarán a la cuenta técnica de IMS necesaria para las llamadas a la API de Campaign Standard Rest. (CAMP-47479)

**Parches**

* Se ha corregido un problema que impedía que se aplicara la opción de caducidad de la tabla de registro de procesos por lotes (**xtkjoblog**). Esto impedía que la tabla se purgara correctamente.

* Se ha corregido un problema que impedía cambiar el orden de los filtros en una actividad de flujo de trabajo **Segmentation**. (CAMP-48357)

* Se ha corregido una regresión de 20.4 que podía provocar que los envíos fallaran con un error de valor nulo. (CAMP-48591)

* Se ha corregido un problema que impedía enviar un informe a través del menú **Compartir** > **Enviar informe ahora** o **Enviar informe según lo programado**. (CAMP-47798)

* Se ha corregido una regresión que podría provocar tasas de apertura incorrectas para Gmail debido al filtrado de eventos de seguimiento recibidos de las cuentas de Gmail. (CAMP-46504)

* Se han corregido varios problemas que provocaban discrepancias de datos entre informes en Adobe Campaign Standard e informes en Adobe Analytics. (CAMP-47671, CAMP-47296)

* Se ha corregido un problema que impedía acceder a los registros de envío después de que la preparación hubiera fallado. (CAMP-48296)

* Se ha corregido un problema que podía mostrar un mensaje de error al intentar editar, eliminar o enviar un informe personalizado. (CAMP-47789, CAMP-47798)

* Se ha corregido un problema que provocaba que las llamadas de API fallaran al crear un nuevo recurso personalizado y habilitar la opción **No sincronizar**. (CAMP-48014)

* Se ha corregido un problema en el cual los recursos personalizados con la opción **Do not sync** habilitada podían hacer referencia a un esquema que se había vuelto a redactar o eliminado. Este problema provocaba un error al publicar los recursos personalizados.

* Se ha corregido un problema de exclusión de SMS al usar varios códigos cortos en la misma cuenta externa.

* Se ha corregido un problema que impedía acceder a un nuevo criterio de alerta de envío (&quot;el recurso al que está intentando acceder no está disponible&quot;) después de publicar la base de datos. (CAMP-48221)

* Se ha corregido un problema por el que faltaban registros de seguimiento en algunas instancias de Campaign con informes dinámicos. Se ha añadido un nuevo [flujo de trabajo técnico](../../administration/using/technical-workflows.md) para restaurar estos registros de seguimiento. (CAMP-47885)

* Se ha corregido un problema en el cual no se mostraban datos de envío en los informes dinámicos. Los informes se establecieron en 0. (CAMP-47480)

* Se ha corregido un problema que impedía que el cliente HTTP JavaScript del servidor se conectara a una dirección URL externa.

* Se ha corregido un problema que restablecía una actividad **Incremental query** después de cambiar el nombre interno del flujo de trabajo. Esto ocurría cuando se utilizaba un campo de fecha como modo incremental. (CAMP-47674)

* Se ha corregido un problema que impedía que la vista previa de la miniatura se mostrara en el resumen de la entrega al crear un correo electrónico multilingüe con la integración de Adobe Experience Manager. Este problema se producía al utilizar el botón **Language copy creation** para crear las variantes de correo electrónico. (CAMP-47810)

* Se ha corregido un problema que impedía a los usuarios acceder al envío principal desde el envío secundario Correo electrónico o SMS. (CAMP-47986)

* Se ha corregido un problema que podía provocar un exceso de consumo de CPU y memoria al enviar mensajes transaccionales a través de la API de REST con un evento personalizado que faltaba. (CAMP-47147)

* Se ha corregido un error con la API de mensajería transaccional que, a veces, impedía que se enviaran mensajes en tiempo real.

* Se ha corregido un problema por el cual los informes no se recibían después de usar la opción **Enviar informe según la programación**. (CAMP-48583, CAMP-47786)

* Se ha corregido un problema por el cual los informes recibidos después de utilizar la opción **Enviar informe ahora** estaban incompletos y faltaban datos. (CAMP-48583)

* Se ha corregido un problema con el Diseñador de correo electrónico en el cual las dimensiones de una imagen se reducían al cargar una imagen. (CAMP-47017)

* Se ha corregido un problema que impedía que se mostraran todas las plantillas de Experience Manager disponibles al crear una entrega. (CAMP-48132)

* Se ha corregido un error que impedía que el vínculo Campaña de la página Resumen de una entrega enviada redirigiera a los usuarios a la campaña relacionada. (CAMP-48012)

* Se ha corregido un problema en el Diseñador de correo electrónico en el que la integración del servicio principal de recursos seguía fallando al intentar seleccionar un recurso. (CAMP-47446)

* Se ha corregido un problema que bloqueaba algunos envíos de Journey Orchestration debido a que Campaign no admitía marcas de hora con un valor exacto (es decir, que terminaba con 00) enviado por eventos del Journey Orchestration.
