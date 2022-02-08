---
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: 5eb01b215a898c28c0a12ceec074d0682cdec0af
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 99%

---


# Última versión{#latest-release}

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
* Ahora puede monitorizar su entrega y rastrear los registros de trabajos con el nuevo desplegable **Historial de trabajos** del tablero de los mensajes. (CAMP-49840)
* Se ha mejorado la estabilidad y el estado de la base de datos, al reducir las tuplas, cuando se envía un gran número de mensajes a través de todos los canales a lo largo del tiempo. (CAMP-49755, CAMP-49792, CAMP-49849)
* Para garantizar que las conexiones de base de datos se actualicen automáticamente en caso de que se bloquee o reinicie, se han implementado mejoras en el Agente de transferencia de correo de Campaign (MTA). (CAMP-48063)


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

