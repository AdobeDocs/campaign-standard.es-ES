---
solution: Campaign Standard
product: campaign
title: Notas de la versión 2020
description: Esta página enumera todas las versiones de 2020 de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '2948'
ht-degree: 99%

---


# Notas de la versión 2020{#release-notes-2020}

[Planificación de versiones](https://helpx.adobe.com/es/campaign/kb/acs-release-planning.html) | [Versiones del Panel de control](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html) | [Actualizaciones de documentación](../../rn/using/documentation-updates.md) | [Notas de la versión anteriores](../../rn/using/release-notes-2019.md) | [Funciones obsoletas](https://helpx.adobe.com/es/campaign/kb/acs-deprecated-and-removed-features.html)

![](assets/do-not-localize/cp-icon.png) **Nuevo lanzamiento del Panel de control de Campaign en junio** con monitorización de perfiles activos, auditoría de entregas de subdominios y administración de claves GPG. [Más información](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html).

## Versión 20.3: mayo de 2020 {#release-20-3---may-2020}

**Novedades**

<table> 
<thead> 
<tr> 
<th> <strong>Ley de Protección de Datos Personales de Tailandia (PDPA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td> <p>La Ley de Protección de Datos Personales de Tailandia (PDPA, por sus siglas en inglés) es la nueva ley de privacidad que armoniza y actualiza los requisitos de protección de datos para Tailandia. Esta ley se aplica a los clientes de Adobe Campaign que mantienen datos de sujetos de datos que residen en la UE.</p>
<p>Además de las funciones de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimientos, la configuración de retención de datos y los roles de usuario), aprovechamos esta oportunidad para incluir funciones adicionales que le ayudarán a prepararse para la PDPA:</p>
<ul>
<li>Derecho al acceso y derecho a la eliminación: aprovechamos las funciones añadidas para el RGPD y la CCPA. <a href="https://helpx.adobe.com/content/help/es/campaign/kb/acs-privacy.html#righttoaccess">Más información</a> </li>
<li><p>Al crear una solicitud de privacidad, se ha agregado el tipo de regulación PDPA en el servicio principal de privacidad. Este método es el que debe utilizar para todas las solicitudes de acceso y eliminación. El uso de la API y la interfaz de Campaign para las solicitudes de acceso y eliminación quedará obsoleto.  Consulte el artículo <a href="../../rn/using/deprecated-features.md">Funciones obsoletas y eliminadas</a>.</p></li>
</ul>
<p>Consulte el vídeo de <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/privacy/privacy-overview.translate.html">procedimiento</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Actividad de API externa (GA)</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>La actividad de <strong>API externa</strong> está pasando de beta a GA. Esta versión ofrece más flexibilidad al analizador de cuerpos de respuesta JSON. Ahora puede hacer lo siguiente:</p>
<ul>
<li>Analizar un JSON anidado con una profundidad máxima de 10 niveles. </li>
<li>Analizar las propiedades seleccionadas como nodos de hoja de un JSON y acoplarlas en una sola fila de tabla.</li>
<li>Seleccionar y utilizar un objeto de matriz de un JSON sin tener que nombrar al objeto "data" ni tenerlo en el nivel superior.</li>
</ul>
<p><strong>Precaución:</strong> Los clientes deberán <strong>reemplazar todas las actividades de API externas beta</strong> con actividades de API externas de GA en sus flujos de trabajo.  Los flujos de trabajo que utilizan la versión beta de la API externa dejarán de funcionar en la versión 20.3.</p>
<p>Para obtener más información, consulte la <a href="../../automating/using/external-api.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/managing-processes-and-data/data-management-activities/external-api-activity.translate.html">videotutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Funciones adicionales** (a partir del 13 de julio)

* **Optimización de tiempo de envío con tecnología de IA y puntuación de perfiles**: ahora puede optimizar el diseño y el envío de los recorridos de los clientes para predecir las preferencias de participación de cada individuo. Con la tecnología de Journey AI, Adobe Campaign puede analizar y predecir las tasas abiertas, los tiempos de envío óptimos y la probable reproducción basada en las métricas de participación históricas. [Más información](../../sending/using/predictive.md)
* **Nueva regulación de privacidad de Brasil**: además de las funcionalidades de privacidad disponibles en Campaign, Adobe le ayuda a facilitar su preparación para la Lei Geral de Proteçao de Datos (LGPD) de Brasil. Al crear una solicitud de privacidad, se ha agregado la regulación LGPD en el servicio principal de privacidad de Adobe. [Más información](https://helpx.adobe.com/es/campaign/kb/campaign-privacy-overview.html)

**Mejoras**

* El número de caracteres que se puede utilizar en el campo **Prefijo** para [probar mensajes con perfiles de destino](../../sending/using/testing-messages-using-target.md) se ha aumentado de 32 a 500 caracteres.
* La cantidad máxima de eventos en tiempo real que se puede publicar en una instancia ha aumentado de 350 a 2000. (CAMP-41608)
* La sincronización entre Adobe Launch y Campaign Standard se ha mejorado mediante el flujo de trabajo técnico syncWithLaunch. Este flujo de trabajo permite la importación automática de todas las propiedades móviles de Adobe Launch a Adobe Campaign Standard. Para obtener más información, consulte [esta página](../../administration/using/technical-workflows.md).

   Deberá enviar un ticket al Servicio de atención al cliente de Adobe (directamente o a través de su contacto de Adobe) para que el flujo de trabajo técnico de syncWithLaunch esté habilitado en la instancia de Campaign. (CAMP-40082)

**Mejoras en el diseñador de correo electrónico**

* El diseñador de correo electrónico ahora puede gestionar un formato HTML más flexible que W3C estricto. (CAMP-42529)
* Se ha corregido un problema con las [imágenes en las que se puede hacer clic](../../designing/using/links.md#inserting-a-link) para evitar que se muestren vínculos junto a la imagen en bloques de contenido. (CAMP-41586)
* Se ha corregido un problema que impedía la redirección a una página de aterrizaje cuando la dirección [URL rastreada](../../designing/using/links.md#about-tracked-urls) tenía una categoría añadida en la plantilla. (CAMP-41537)
* Se ha corregido un problema con el relleno de botones en Outlook.
* Se ha corregido un problema que provocaba que las etiquetas HTML aparecieran en texto sin formato.
* La búsqueda de bloques de contenido ahora muestra resultados de búsqueda del servidor, así como resultados precargados. (CAMP-41870)

**Otros cambios**

* La interfaz de publicación de recursos personalizada se ha mejorado con mensajes de error más claros.
* Las asignaciones de envío no utilizadas se han eliminado de la interfaz.
* Se han eliminado funciones de administrador innecesarias de la interfaz.
* Ahora las casillas de verificación pueden ser obligatorias en una página de aterrizaje.
* Al descargar el archivo CSV de un informe dinámico, se ha eliminado el límite de 200 filas. Ahora puede incluir cada fila del informe. (CAMP-40810)
* Se ha añadido el lenguaje ES-US a la lista de idiomas predeterminados para correos electrónicos multilingües. (CAMP-42279)
* Los archivos descargados con una actividad Transferir archivo ahora se eliminarán después de X días, donde X se determina con el campo **Historial en días** en el menú **Ejecución** de las propiedades Flujo de trabajo. [Más información](../../automating/using/managing-execution-options.md)

**Integraciones de Experience Platform**

* Se ha mejorado la activación de audiencias de [Experience Platform](../../automating/using/aep-targeting-audiences.md) de Adobe desde la actividad **Leer audiencia** para proporcionar un mejor rendimiento y estabilidad. Además, los registros de flujo de trabajo se han simplificado para añadir claridad y detallado con respecto a los trabajos de activación, lo que facilita la monitorización y la resolución de problemas al leer audiencias de Adobe Experience Platform.

**Parches**

* Se ha corregido un error que hacía que se creara un recurso fantasma durante el trabajo de publicación de un recurso personalizado.
* Se ha corregido un problema que podía impedir que se mostrara el Historial de marketing de los perfiles si el recurso Perfil se ampliaba con un recurso personalizado. (CAMP-41009)
* Se ha corregido un problema con las plantillas de la página de aterrizaje integradas que mostraban su contenido en francés al abrir el editor. (CAMP-41639)
* Se ha corregido un problema en las notificaciones push con contenido dinámico que podía impedir que se mostraran emojis. (CAMP-40715)
* Se ha corregido un problema con la actividad **Deduplicación** que podía hacer que se asignara un código de segmento incorrecto a una de las transiciones de complemento salientes. (CAMP-41400)
* Se ha corregido un error que impedía que se eliminaran informes programados. (CAMP-41302)
* Se ha corregido un problema que provocaba discrepancias entre el panel de envíos y el informe **Resumen de envíos**. (CAMP-41145)
* Se ha corregido un problema que provocaba un problema de visualización de superposición de caracteres en informes descargados.
* Se ha corregido un problema que impedía que la previsualización de un envío funcionara para la sustitución de pruebas.
* Se ha corregido un error al eliminar campos personalizados de una notificación local en la aplicación.
* Se ha corregido un problema que impedía que la función charIndex funcionara con una actividad **Fin** o **Transferir archivo** en un flujo de trabajo.
* Se ha corregido un problema con flujos de trabajo que se podía producir al usar una actividad de **Enriquecimiento** con dos actividades de entrada, incluidos los recursos de destinatario que tenían un vínculo entre ellos. (CAMP-42133)
* Se ha corregido un problema que podía impedir que se ejecutara un flujo de trabajo al usar funciones desconocidas. (CAMP-41873)
* Se ha corregido un problema con flujos de trabajo que se podía producir al crear audiencias con varias actividades **Guardar audiencia** con transiciones salientes complementarias. (CAMP-39992)
* Se ha corregido un problema que provocaba discrepancias en los datos al utilizar la personalización en correos electrónicos transaccionales. (CAMP-41842)
* Se han corregido problemas que se producían al eliminar campos personalizados en envíos de notificaciones push. (CAMP-37586)
* Se ha corregido un error que impedía a los usuarios realizar cambios en los informes. (CAMP-42505)


![](assets/do-not-localize/cp-icon.png) **El nuevo Panel de control de Campaign puede lanzarse** con la renovación de los certificados para los subdominios CNAME. [Más información](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html).

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

* Se ha mejorado la experiencia de usuario de mensajería transaccional y se ha mejorado la coherencia de la interfaz. [Más información](../../channels/using/getting-started-with-transactional-msg.md)
* Ahora, Campaign Standard le permite enviar pruebas a perfiles de prueba con datos adicionales de flujos de trabajo.
* Se han actualizado las protecciones de la actividad API externa. [Más información](../../automating/using/external-api.md)

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
    <p>Tenga en cuenta que esta funcionalidad solo está disponible para los clientes alojados en Azure. Para obtener más información sobre esta funcionalidad y las condiciones para activarla, consulte la <a href="../../developing/using/aep-about-data-connector.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/administrating/adobe-experience-platform-data-connector/understanding-the-adobe-experience-platform-data-connector.html">videotutorial</a>.</p>
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
* [!DNL Adobe Creative SDK] ha sido desmantelado. Ahora está en desuso en Campaign Standard. Consulte la página [Funciones obsoletas y eliminadas](https://helpx.adobe.com/es/campaign/kb/acs-deprecated-and-removed-features.html).


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
* Se ha corregido un problema que impedía que se enviaran mensajes en la aplicación al añadir un perfil de prueba al envío.
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
