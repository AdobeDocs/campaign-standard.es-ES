---
title: Notas de la versión 2020
description: Esta página enumera todas las versiones de 2020 de Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 1cf2e40c-beca-43db-8261-a1820ee86ad3
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
discoiquuid: 5c7bfb74-4002-4ffe-87e8-bddb41d34b41
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ad110413fd325894405b421999baccda2c7cef4a
workflow-type: tm+mt
source-wordcount: '1825'
ht-degree: 99%

---


# Notas de la versión 2020{#release-notes-2020}

[Planificación de versiones](https://helpx.adobe.com/es/campaign/kb/acs-release-planning.html) | [Versiones del Panel de control](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html) | [Actualizaciones de documentación](../../rn/using/documentation-updates.md) | [Notas de la versión anteriores](../../rn/using/release-notes-2019.md) | [Funciones obsoletas](https://helpx.adobe.com/es/campaign/kb/acs-deprecated-and-removed-features.html)

## Versión 20.2: abril de 2020 {#release-20-2---april-2020}

**Novedades**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integración de Azure Blob</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>El conector de almacenamiento Azure Blob ahora se puede utilizar para importar o exportar datos de Adobe Campaign mediante la opción en el flujo de trabajo <strong>Transferir archivo</strong>. </p>
    <p>Para obtener más información, consulte la <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentación detallada</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pruebas de correo electrónico con perfiles de destino</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Además de probar los perfiles, ahora puede probar los correos electrónicos en perfiles de destino reales. Esto le permite obtener una representación exacta del mensaje que recibirá el perfil: campos personalizados, información dinámica y personalizada, incluidos los datos adicionales de flujos de trabajo, etc. </p>
    <p>Para obtener más información, consulte la <a href="../../sending/using/testing-messages-using-target.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.translate.html">videotutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>En abril se lanzarán nuevas funciones en el Panel de control de Campaign, incluida la administración de registros TXT de Google, la supervisión de espacio en la base de datos y las alertas por correo electrónico. Para obtener más información sobre estas funciones, consulte la [Nota de la versión del Panel de control](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html).

**Mejoras**

* Se ha mejorado la experiencia de usuario de mensajería transaccional y se ha mejorado la coherencia de la interfaz. [Más información](../../channels/using/about-transactional-messaging.md)
* Ahora, Campaign Standard le permite enviar pruebas a perfiles de prueba con datos adicionales de flujos de trabajo.
* Se han actualizado los protecciones de la actividad API externa. [Más información](../../automating/using/external-api.md)

**Mejoras en el Diseñador de correo electrónico**

* Se ha corregido un problema que afectaba al escape al hacer clic varias veces en una imagen personalizada.
* Se ha corregido un problema que se producía al duplicar componentes de texto dinámico y que podía provocar la duplicación de líneas erróneas. (CAMP-41249)
* Se ha corregido un problema con el relleno en Outlook al definirlo en el nivel de tabla en lugar del nivel de div.
* Se ha corregido un problema que provocaba que se modificara la anchura de una imagen al cambiar al modo HTML. (CAMP-41116)
* Se ha corregido un problema que impedía que el componente de medios sociales fuera accesible al proporcionar texto alternativo a los iconos. (CAMP-41345)
* Se ha corregido un problema que provocaba que se mostraran las etiquetas visibles `<br>` al usar copiar y pegar en el Diseñador de correo electrónico.
* Se ha corregido un problema que provocaba que las etiquetas HTML se mostraran en el correo electrónico después de cambiar del contenido HTML a texto sin formato. (CAMP-41138)
* Se ha corregido un problema que impedía procesar botones con un solo borde definido.
* Se ha corregido un problema en la sangría HTML que provocaba que el pie de página de los correos electrónicos se moviera hacia la izquierda en Microsoft Outlook. (CAMP-40987)
* Se ha corregido un problema que provocaba que los campos de personalización dirigidos a un atributo de recopilación definido en HTML se copiaran en el contenido de texto sin formato al cambiar al modo de texto sin formato. (CAMP-40365)
* Se ha corregido un problema que impedía que los vínculos se insertaran en un segmento de texto seleccionado. (CAMP-41406)
* Se ha corregido un problema que provocaba que la fecha se modificara al seleccionar una zona horaria en el editor de consultas. (CAMP-38277)

**Otros cambios**

* El flujo de trabajo integrado **Reconciliación de KPI con Adobe Analytics** ahora se ejecuta hasta la fecha actual en lugar de ejecutarse para un solo día.
* El MCPNS no admite la adición de APNS y APNS-SANDBOX como plataformas en una aplicación. Después de añadir correctamente el certificado en Adobe Campaign Standard, ya no podrá volver a cambiar la configuración, ya que solo se puede añadir una plataforma APNS (producción o simulación de pruebas) a la aplicación MCPNS.

**Integraciones de Experience Platform**

>[!NOTE]
>
>Las funciones de Adobe Experience Platform en Campaign Standard se encuentran actualmente en fase beta, por lo que pueden estar sujetas a actualizaciones frecuentes sin previo aviso. Consulte la documentación detallada: [Experience Platform Data Connector](../../developing/using/aep-about-data-connector.md), [Audience Destinations](../../audiences/using/aep-about-audience-destinations-service.md)

* Ahora, en los registros de flujo de trabajo y cada 10 minutos, Campaign muestra el número de registros que ya ha procesado el trabajo que se está ejecutando.
* Se ha corregido un problema que se podía producir al importar un perfil de Adobe Experience Platform que se hubiera eliminado de la base de datos.
* Se ha corregido un problema en los registros del flujo de trabajo que podía mostrar un resultado incorrecto para el número total de registros importados.

**Parches**

* Se ha corregido un problema con la actividad flujo de trabajo de **Enriquecimiento** que se podía producir al añadir espacios en el campo **Alias**, el cual a continuación creaba un nuevo elemento de fila. (CAMP-39229)
* Se ha corregido un problema en el cual cada perfil de prueba se podía dirigir al enviar un mensaje de prueba.
* Se ha corregido un problema que se producía tras cancelar la publicación y eliminar una configuración de evento. [Más información](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Se ha corregido un problema por el cual el botón **Guardar** desaparecía al realizar cambios en flujos de trabajo.
* Se ha corregido un problema que se producía al eliminar una solicitud de privacidad manualmente en Campaign después de procesarla, lo que impedía que los datos asociados a la solicitud se eliminaran incluso después de la limpieza.
* Se ha corregido un problema que se podía producir al obtener una vista previa o enviar mensajes que incluían caracteres especiales de Adobe Experience Manager.
* Se ha corregido un problema que se podía producir en los flujos de trabajo al ejecutar una actividad con varias transiciones de entrada.
* Se ha corregido un problema que impedía que los usuarios estándar usaran las “Suscripciones a una aplicación” como dimensión de segmentación en una consulta de flujo de trabajo o un envío. (CAMP-37618)

## Versión 20.1.4: febrero de 2020 {#release-20-1-4---february-2020}

* Se ha corregido un problema al activar la opción **Leer audiencia** en flujos de trabajo existentes. (CAMP-41002)

## Versión 20.1.3: febrero de 2020 {#release-20-1-3---february-2020}

* Se ha corregido un problema de regresión introducido en la versión 20.1 por CAMP-39273 para los clientes que utilizan un loophole. Se ha vuelto a la versión anterior a CAMP-39273.

## Versión 20.1.2: febrero de 2020 {#release-20-1-2---february-2020}

**Mejoras en el Diseñador de correo electrónico**

* Se ha corregido un problema que añadía un elemento de etiqueta HTML en un fragmento obsoleto al realizar un parche y, a continuación, guardar el contenido. (CAMP-40685)
* Se ha corregido un problema que añadía un espacio al usar contenido dinámico. (CAMP-40605)
* Se ha corregido un problema al configurar una plantilla de correo electrónico transaccional. (CAMP-40604)

## Versión 20.1: febrero de 2020 {#release-20-1---february-2020}

**Novedades**


<table> 
 <thead> 
  <tr> 
   <th> <strong>Adobe Experience Platform Data Connector (beta)</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Ahora, Adobe Experience Platform Data Connector está integrado con Adobe Campaign Standard. Puede hacer que los datos de Campaign estén disponibles en Adobe Experience Platform asignando datos XTK (datos incorporados en Campaign) al modelo de datos de Adobe Experience Platform (XDM). </p>
    <p>Tenga en cuenta que esta funcionalidad solo está disponible para los clientes alojados en Azure. Para obtener más información sobre esta funcionalidad y las condiciones para activarla, consulte la <a href="../../developing/using/aep-about-data-connector.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">videotutorial</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Audience Destinations (beta) </strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Audience Destinations le permite compartir segmentos de Adobe Experience Platform en Adobe Campaign.</p>
    <p>Tenga en cuenta que esta funcionalidad solo está disponible para los clientes alojados en Azure. Para obtener más información sobre esta funcionalidad y las condiciones para activarla, consulte la <a href="../../audiences/using/aep-about-audience-destinations-service.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/profiles-and-audiences/audience-destinations/audience-destinations-overview.translate.html">videotutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

**Mejoras**

* Disponibilidad global del MTA mejorado: ahora, los mensajes (incluidos los mensajes transaccionales) se envían por el MTA mejorado de Adobe Campaign, que proporciona una infraestructura de envío mejorada y permite mejorar la entrega, el rendimiento y la gestión de devoluciones. [Más información](https://helpx.adobe.com/es/campaign/kb/campaign-enhanced-mta.html)

* Se ha mejorado la administración de zonas horarias. Ahora, puede definir una [zona horaria específica](../../automating/using/building-a-workflow.md) para todo un flujo de trabajo. La zona horaria seleccionada se aplicará a todas las actividades del flujo de trabajo. Ahora, la información sobre la zona horaria configurada para el operador o el servidor se muestra en la interfaz (en registros y después de seleccionar una zona horaria). (CAMP-37672)

* Ahora, las API de Campaign Standard permiten realizar paginación al utilizar tablas grandes, añadiendo el parámetro `_forcePagination=true` a la dirección URL de la llamada. [Más información](../../api/using/pagination.md)

* El ID de registro de envío (que es un identificador único para cada registro) ya está disponible en los recursos de registros de envío y registros de seguimiento para todas las dimensiones de segmentación. Esto permite identificar el envío o los registros de seguimiento al exportar, por ejemplo. [Más información](../../automating/using/exporting-logs.md)

**Mejoras en el Diseñador de correo electrónico**

* Se han añadido las instrucciones de texto obligatorias que faltaban al crear una audiencia.
* Se ha corregido un problema al hacer clic en el botón **Cambiar contenido** en el asistente del editor de correo electrónico antiguo.
* Se ha corregido un problema que impedía que los encabezados se alinearan con el contenido del informe Resumen de servicios. (CAMP-38103)
* Se ha corregido un problema que impedía que las variantes de contenido dinámico se eliminaran sin afectar al resto de la línea de asunto. (CAMP-40096)
* Se ha corregido un problema con la prueba A/B al usar la variante B en la línea de asunto. (CAMP-40327)
* Se ha corregido un problema que impedía arrastrar y soltar archivos al utilizar la función de importación de HTML de carga. (CAMP-39326)
* Se ha corregido un problema que impedía copiar y pegar texto desde un editor de texto. (CAMP-39028)
* Se ha corregido un problema que impedía que se mostraran las sugerencias de términos. (CAMP-38970)
* Se ha corregido un problema que impedía a los usuarios guardar fragmentos. (ATU-2447)
* Se ha corregido un problema que impedía que las estructuras dinámicas se duplicaran. (CAMP-38367)
* Se ha corregido un problema que impedía que el contenido dinámico conservara las condiciones cuando se duplicaba. (CAMP-39051)

**Otros cambios**

* Ahora, el filtro “Envíos con error de preparación” tiene en cuenta la fecha de creación de los envíos en lugar de la fecha de la última modificación.
* La unidad organizativa del grupo de seguridad de los administradores ya no se puede cambiar.
* Al crear un perfil, ahora se debe rellenar el campo Unidad organizativa.
* Ahora, un activador de Experience Cloud solo se puede eliminar si se eliminan el evento y la plantilla transaccional vinculados a él.
* El SDK de Adobe Creative se ha retirado del mercado. Ahora está en desuso en Campaign Standard. Consulte la página [Funciones obsoletas y eliminadas](https://helpx.adobe.com/es/campaign/kb/acs-deprecated-and-removed-features.html).


**Parches**

* Se ha corregido un problema al realizar una solicitud de eliminación de privacidad que impedía que los datos de usuario se eliminaran en los registros de exclusión. (CAMP-39003)
* Se ha corregido un problema que provocaba problemas de accesibilidad al cambiar el tamaño del texto en un elemento de contenedor.
* Se ha corregido un problema que impedía a los usuarios descartar la ventana emergente Calendario que aparece al pasar el ratón por las actividades de marketing.
* Se ha corregido un problema en la actividad **[!UICONTROL External API]** que mostraba el botón **[!UICONTROL Confirm]** aunque no se modificaran los datos.
* Se ha corregido un problema al usar una actividad de **[!UICONTROL Union]** en consultas con diferentes dimensiones de segmentación. Los datos de transición solo mostraban registros de la dimensión de segmentación del conjunto principal. (CAMP-36831)
* Se ha corregido un problema que podía provocar un error al usar una actividad de **[!UICONTROL Reconciliation]** en contextos específicos, por ejemplo, con dos actividades entrantes, una de las cuales era de exclusión. (CAMP-37490)
* Se han corregido problemas de rendimiento que podían producirse al seleccionar y actualizar perfiles de prueba. (CAMP-37976)
* Se ha corregido un problema que podía mostrar páginas de error al suscribirse o cancelar la suscripción mediante páginas de aterrizaje. (CAMP-37771)
* Se ha corregido un problema que se producía al cargar contenido en formato zip, con archivos PNG referenciados en HTML con su extensión en mayúsculas. (CAMP-37913)
* Se ha corregido un problema que impedía que se enviaran mensajes en la aplicación al agregar un perfil de prueba al envío.
* Se ha corregido un error con la actividad flujo de trabajo de API externa que fallaba al vincularse a actividades de enriquecimiento.
* Se ha corregido un problema que podía hacer que el estado de los mensajes SMS se mostrara incorrectamente.
* Se ha corregido un problema con los recursos personalizados que provocaba que las entradas duplicadas aparecieran en diferentes extremos de API.
* Se ha corregido un problema que impedía que las páginas de aterrizaje estuvieran disponibles tras la publicación. (CAMP-38695)
* Se ha corregido un error que se producía al mostrar datos de una transición de intersección procedentes de dos recursos diferentes. (CAMP-38974)
* Se ha corregido un problema que provocaba que el valor de lista desglosada de una plantilla de envíos se configurara incorrectamente. (CAMP-38388)
* Se ha corregido un error con los envíos masivos de correo electrónico que mostraban el estado de los envíos como “pendiente” y el estado “enviado” como “finalizado”. (CAMP-35355)
* Se ha corregido un error que mostraba el dominio del remitente incorrectamente en el sistema de informes dinámico. (CAMP-33123)
* Se ha corregido un problema que provocaba discrepancias en los recuentos de bajas en el sistema de informes dinámico. (CAMP-39949)
* Se ha corregido un problema que impedía que las direcciones se mostraran en la pantalla de registro de envío al enviar mensajes en la aplicación.
* Se ha corregido un problema que impedía que los registros de envío de SMS se actualizaran con el número correcto de devoluciones. (CAMP-38395)
* Se ha corregido una laguna que permitía que las llamadas posteriores a la suscripción de la aplicación actualizaran los tokens de notificaciones push. (CAMP-39273)
