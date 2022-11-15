---
title: Notas de la versión de 2022
description: Esta página enumera todas las versiones de 2022 de Adobe Campaign Standard.
feature: Overview
role: User
level: Beginner
exl-id: 8c722084-988d-47bd-98ad-9f5a422980a0
source-git-commit: 77c5baaf51b82ea001326f3f20c8ab183155f9e6
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 100%

---

# Notas de la versión de 2022{#release-notes-2022}

## Versión 22.2 de junio de 2022 {#june-2022}

**Mejoras**

* **Servicio de notificación de Adobe**: Campaign viene con el servicio de notificación de Adobe que permite a las soluciones de Experience Cloud alertar a los usuarios entre Experience Cloud sobre las actividades que son importantes que conozcan. A partir de la versión 22.2, la experiencia del usuario se ha mejorado: las notificaciones se priorizan y las notificaciones generadas por el producto se separan de los anuncios de estado del Adobe. Además, cuando la notificación hace referencia a un flujo de trabajo específico, ahora puede acceder al flujo de trabajo correspondiente directamente desde el correo electrónico o la notificación interna del producto.  Para obtener más información sobre las notificaciones de Adobe Campaign, consulte [Notificaciones de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

<!--
* **Optimization in Workflow startup** - Adobe has added a new capability which can tune the number of workflows that start around the same time. This would help prevent CPU spikes that could have led to service interruptions or downtime. Adobe would enable it after 22.2 release. There is no further action item on customer regarding the same.
-->

* **Accesibilidad**: Adobe ha realizado muchas correcciones de accesibilidad para mejorar la facilidad de uso general de la aplicación. Actualmente, estas funciones solo están habilitadas para un conjunto de usuarios que las adoptaron por primera vez, y se implementarán para todos los clientes en versiones futuras. Algunos ejemplos de mejoras de accesibilidad son los siguientes:

   * Garantizar que haya un indicador de enfoque visible para los elementos enfocables en cada pantalla
   * Creación de puntos de referencia de página para facilitar la navegación
   * Adición del nombre, la función, el valor y el estado para muchos controles
   * Corrección de problemas con el orden de enfoque dinámico en las pantallas principales


**Parches**

* Se ha corregido un problema en el flujo de trabajo técnico Facturación debido a un error de clave duplicada. (CAMP-51029)
* Se ha añadido la categoría del explorador Microsoft Edge que falta en Seguimiento de informes. Anteriormente, se clasificaban con las aperturas de Microsoft Chrome. (CAMP-51165)
* Se ha corregido un problema con las solicitudes de RGPD que no eliminaban datos de tablas secundarias. (CAMP-48276)
* Se ha corregido un problema en el Diseñador de correo electrónico que provocaba que la condición de visibilidad de un fragmento no se guardara en una plantilla de mensaje transaccional. (CAMP-50338)
* Se ha corregido un problema en los informes de campaña que provocaba que no se tuviera en cuenta el intervalo de fechas. (CAMP-50991)
* Se ha corregido un error que provocaba que fallaran los correos electrónicos programados: el análisis de entrega no se pudo iniciar porque la entrega seguía en estado &quot;Reintento pendiente&quot;. (CAMP-50302)
* Se ha corregido un problema en el Diseñador de correo electrónico al previsualizar un correo electrónico con una sustitución de perfiles. (CAMP-49312)
* Se ha corregido un problema con un valor vacío en las enumeraciones personalizadas: al crear un recurso personalizado con un campo que es una enumeración de texto y contiene solo un valor, este valor se establece ahora de forma predeterminada, de modo que puede crear una consulta en este campo como una solicitud simple. (CAMP-50606)


## Versión 22.1: febrero de 2022 {#feb-2022}

**Novedades**

<table> 
<thead> 
<tr> 
<th> <strong>Actualización de seguridad para las vulnerabilidades de seguridad de Apache Log4j</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Apache log4j ha corregido las vulnerabilidades notificadas en la versión 2.17.1 de Apache log4j. Adobe Campaign Standard utiliza Apache log4j y esta versión incluye el último Apache log4j v2.17.1 </p>
</td> 
</tr> 
</tbody> 
</table>

**Correcciones de seguridad**

* Nuevo mecanismo de firma de URL para el seguimiento incluido en esta versión. El mecanismo previo se ha deshabilitado para evitar un problema que causaba que algunos vínculos de seguimiento válidos y firmados se bloquearan incorrectamente después de ser modificados por herramientas de seguridad de terceros. (CAMP-48983)

**Mejoras**

* Se ha mejorado el procesamiento de los datos de creación de informes para evitar sobrecargar el sistema. (CAMP-47578)
* Después de enviar los mensajes en la aplicación, puede optar por desactivar la entrega. Esto le permite eliminar su entrega sin perder datos de creación de informes. (CAMP-48469)
* Para evitar cualquier problema, los usuarios ya no pueden utilizar el mismo nombre para una columna de tabla personalizada que el utilizado para la clave principal automática en la base de datos. `"<dataType><resourceName>Id"`. (CAMP-49358)
* Ahora puede monitorizar su entrega y rastrear los registros de trabajos con el nuevo desplegable **Historial de trabajos** del tablero de los mensajes. [Más información](../../sending/using/monitoring-a-delivery.md) (CAMP-49840)
* Se ha mejorado la estabilidad y el estado de la base de datos, al reducir las tuplas, cuando se envía un gran número de mensajes a través de todos los canales a lo largo del tiempo. (CAMP-49755, CAMP-49792, CAMP-49849)
* Para garantizar que las conexiones de base de datos se actualicen automáticamente en caso de que se bloquee o reinicie, se han implementado mejoras en el Agente de transferencia de correo de Campaign (MTA). (CAMP-48063)
* Una nueva opción de seguimiento **Utilizar el píxel de seguimiento en la parte superior del correo electrónico** se ha añadido a las propiedades de correo electrónico, lo que le permite mover el píxel de seguimiento al principio del correo electrónico en lugar de al final. (CAMP-49672)

**Parches**

* Se ha corregido un problema con la opción **Enviar informe ahora** en Informes dinámicos: los trabajos de generación de PDF fallaron con entregas que incluían varias variantes. (CAMP-49120)
* Se ha corregido un problema que impedía a los usuarios actualizar o desvincular contenido de Adobe Experience Manager (AEM) de sus envíos de Adobe Campaign Standard cuando un contenido duplicado en AEM compartía la misma clave (cq:uuid). (CAMP-49161)
* Se ha corregido un error al acceder a una instancia en la que las páginas no se cargaban, no se podían abrir los envíos o no se podía guardar ninguna modificación pendiente. (CAMP-50195)
* Se ha corregido un problema que impedía abrir los criterios de alerta de entrega si el campo **Filtro de entrega** aplicado por este criterio no se ha rellenado. (CAMP-49093)
* Se ha corregido un problema que se producía al editar el botón **Secundario** en entregas en la aplicación que impidieron que se tuvieran en cuenta los cambios. (CAMP-50250)
* Se ha corregido un error en las instancias de japonés que impedía a los usuarios elegir Varias veces al día como **Frecuencia de ejecución** en la actividad del **Planificador**. (CAMP-50247)
* Se ha corregido un problema que se producía al trabajar en una interfaz de usuario japonesa y que mostraba un mensaje de error al seleccionar una hora en una actividad del planificador. (CAMP-49289)
* Se ha corregido un error con los informes de notificaciones push que mostraban notificaciones push descartadas como **Apertura** en lugar de **Impresión**. (CAMP-45980)
* Se ha corregido un problema que podría provocar errores al abrir un informe. (CAMP-49222)
* Se ha corregido un problema que podría provocar que la preparación del correo electrónico falle después de eliminar un vínculo al contenido de AEM. (CAMP-49877)
* Para resolver varios problemas, se ha mejorado el mecanismo de reintentos de envíos, incluido el contenido importado de una dirección URL. [Más información](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time) (CAMP-48888)
* Se ha corregido un problema que se producía después de crear un nuevo filtro en un recurso personalizado y, a continuación, utilizarlo como clave de reconciliación en una página de aterrizaje. Si el recurso personalizado se volvió a publicar, el filtro se eliminó de la lista de claves de reconciliación disponibles para la página de aterrizaje. (CAMP-49516)
* Se ha corregido un problema en las páginas de aterrizaje al usar condiciones dinámicas con casillas de verificación. (CAMP-48604)
* Se ha corregido un problema que se producía en una actividad de **Consulta** al usar la condición de filtro En octubre o antes. Al trabajar desde una instancia configurada en una zona horaria europea, el mes seleccionado para filtrar se mostraba en septiembre en lugar de octubre, debido a un problema al convertir la zona horaria. (CAMP-48602)
* Para optimizar la capacidad de envío, Adobe Campaign ahora envía correos electrónicos con codificación de 7 bits en lugar de 8 bits. Esto evita que los relés intermedios invaliden la firma DKIM que podría afectar a la autenticidad de los mensajes. (CAMP-49016)
* Se ha mejorado el rendimiento al duplicar audiencias para evitar cualquier problema al trabajar con audiencias grandes. (CAMP-49639)
* Se ha corregido un problema que podía impedir que un filtro personalizado mostrara los resultados correctos cuando se usaba en una actividad de **Consulta**. (CAMP-49417)
* Se ha corregido un error que mostraba un mensaje de error al intentar utilizar un fragmento en una entrega con una coma en su nombre. El problema se ha resuelto y ahora se pueden usar comas en los nombres de los fragmentos. (CAMP-49216)
