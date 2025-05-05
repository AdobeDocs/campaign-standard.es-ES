---
title: Notas de la versión 2020
description: Esta página enumera todas las versiones de 2020 de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
feature: Overview
role: User
level: Beginner
hidefromtoc: true
exl-id: b6cf7152-2200-43d7-8d0a-d65752bb2c9b
source-git-commit: 1d8baca669235be10d373d985ea62f6f014c16f8
workflow-type: tm+mt
source-wordcount: '5267'
ht-degree: 97%

---

# Notas de la versión 2020{#release-notes-2020}

![](assets/do-not-localize/cp-icon.png) **Nuevo lanzamiento del Panel de control en junio** con monitorización de perfiles activos, auditoría de entregas de subdominios y administración de claves GPG. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es).

![](assets/do-not-localize/cp-icon.png) **la nueva versión de Panel de control de octubre** con configuración de dominio mediante CNAME y nuevas funciones de supervisión de bases de datos. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es).

## Versión 20.4: octubre de 2020 {#release-20-4---october-2020}

**Novedades**

<table> 
<thead> 
<tr> 
<th> <strong>Grupos de control</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Ahora puede utilizar <strong>Grupos de control</strong> para medir el impacto de sus campañas al excluir una parte de su audiencia. A continuación, podrá comparar el comportamiento de la población de destinatarios que recibió el mensaje con el comportamiento de los contactos a los que no estaban destinados. En función de los registros de envío, también puede destinar un grupo de control en campañas futuras.
</p>
<p>Para obtener más información, consulte la <a href="../../sending/using/control-group.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=es">videotutorial</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>API externa: compatibilidad con OAuth</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Adobe Campaign ahora admite OAuth para la autenticación en la actividad de flujo de trabajo de <strong>API externa</strong>. Esta nueva capacidad permite que esta actividad se comunique con sistemas que requieren soporte para OAuth.
</p>
<p>Para obtener más información, consulte la <a href="../../automating/using/external-api.md">documentación detallada</a>.
</p>
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Integración de Journey AI</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
  <td> <p>Nos complace anunciar Journey AI para todos los clientes de Adobe Campaign Standard.</p>
  <p>La IA del recorrido utiliza aprendizaje automático avanzado (ML) para permitir que las empresas optimicen el diseño y el envío de los recorridos de los clientes mediante la predicción de las preferencias de participación de cada individuo.</p>
  <P>Journey AI consta de dos características de ML:</p>
<ul> 
     <li> <strong>Puntuación de participación predictiva</strong>: identifica de forma inteligente el nivel de compromiso preferido de los clientes para destinar y personalizar de mejor manera los mensajes a fin de aumentar las conversiones y la retención. Vea el <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html?lang=es">vídeo explicativo</a>.</li> 
     <li> <strong>Optimización del tiempo de envío predictivo</strong>: predice el mejor momento para enviar correos electrónicos a cada individuo en una campaña a fin de maximizar las tasas de participación y mejorar el ROI de la campaña de correo electrónico. Vea el <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html?lang=es">vídeo explicativo</a>.</li>
    </ul>
  <p>Si desea obtener información sobre cómo empezar a utilizar Journey AI, consulte la <a href="../../sending/using/predictive.md">documentación detallada</a> y póngase en contacto con su ejecutivo de cuentas. Tenga en cuenta que mientras que Journey AI está disponible de forma gratuita para los clientes de Campaign existentes, existe un costo de implementación de aproximadamente 50 horas.</p>
    </td> 
</tr> 
</tbody> 
</table>

**Mejoras**

* **Administración de privacidad**: el campo de **exclusión de CCPA** que estaba disponible a través de la interfaz de Campaign y la API, ahora también se admite en el servicio principal de privacidad. Este campo les permite a los usuarios de Adobe Campaign rastrear si un consumidor ha optado por la venta de información personal. [Más información](https://helpx.adobe.com/es/content/help/es-ES/campaign/kb/acs-privacy.html#ccpa)
* **Mejoras en la ejecución del flujo de trabajo** (beta): en el contexto de una iniciativa mundial en torno a los flujos de trabajo, se han desarrollado algunas mejoras importantes para estabilizar la gestión de la memoria, reducir la latencia y optimizar la memoria consumida por los flujos de trabajo durante la ejecución. Estas mejoras están actualmente en fase beta y solo están disponibles para un conjunto de clientes. Está previsto que a principios de 2021 se disponga de una disponibilidad general.
* Para mejorar la seguridad, Campaign ahora utiliza un **mecanismo de firma** para hacer un seguimiento de los vínculos en los correos electrónicos.
* La configuración de la aplicación móvil se mejoró con **mensajes de error más claros** al cargar certificados de iOS o claves de Android.
* Se mejoró la **administración de errores de SMS** para evitar que se agreguen demasiados perfiles a la lista de cuarentena. De forma predeterminada, los errores de SMS ahora se configuran como errores recuperables en lugar de errores no recuperables. Consulte [esta página](https://helpx.adobe.com/es/campaign/kb/sms-connector-protocol-and-settings.html).

**Mejoras en el diseñador de correo electrónico**

* Mejoramos la experiencia del usuario con el Diseñador de correo electrónico con la **nueva ayuda contextual dinámica** que conecta completamente la interfaz del usuario y la documentación, lo que facilita el acceso al contenido de ayuda más reciente.
* Se ha corregido un problema que eliminaba los saltos de línea en un mensaje al editar la versión de texto. (CAMP-44483)
* Se ha corregido un problema que impedía que la versión de texto sin formato de una plantilla HTML se generara y sincronizara automáticamente. (CAMP-44195)
* Se ha corregido un problema que se podía producir al cambiar el tamaño de las imágenes. Una vez enviados los mensajes, las imágenes no se mostraban correctamente en Microsoft Outlook. (CAMP-44656)
* Se ha corregido un problema que se producía al insertar un botón y establecer su anchura en “auto”. Una vez enviado el mensaje, el contenido del botón no se mostraba completamente. (CAMP-44560)
* Se ha corregido un problema que se producía al cargar contenido desde un archivo HTML adjunto. Una vez que el mensaje se envió a una dirección de Gmail, el CSS no se aplicó, lo que provocó un problema de procesamiento. (CAMP-44085)
* Se ha corregido un problema que impedía que los fragmentos de contenido utilizados anteriormente en un mensaje se actualizaran cuando se modificaban directamente en la plantilla de contenido. (CAMP-43973)
* Se ha corregido un problema con la barra de búsqueda **Fragmentos**. Al buscar un fragmento existente, la barra de búsqueda no mostraba ningún resultado. (CAMP-44223)
* Se ha corregido un problema con las barras de búsqueda **Bloques de contenido** y **Fragmentos**. Al utilizar una de las barras de búsqueda, los resultados solo se mostraban si hacía clic en **Mostrar más resultados**. (CAMP-44205)
* Se ha corregido un problema que impedía que se aplicara el relleno entre texto e imágenes en Microsoft Outlook. (CAMP-45370)
* Se ha corregido un problema al duplicar un fragmento. Después de duplicar el fragmento, faltaban líneas HTML en el fragmento original. (CAMP-45207)
* Se ha corregido un error que causaba problemas de procesamiento en Microsoft Outlook. (CAMP-44749)
* Se ha corregido un error que se producía al modificar el relleno del **componente de estructura** en una plantilla de envíos. Las etiquetas CSS no transfirieron los cambios realizados en el relleno que ocasionaban un problema de procesamiento. (CAMP-45381)
* Se ha corregido un problema al cargar una imagen. La altura de la imagen se estableció automáticamente en 0, lo que provocó un problema de procesamiento. (CAMP-45366)

**Otros cambios**

* Se han agregado mecanismos de reintento en caso de error al intentar importar una audiencia de Experience Platform mediante una actividad de **audiencia de lectura**. (CAMP-43947, CAMP-43366)
* Las unidades organizativas ahora se configuran automáticamente para que coincidan con la unidad organizativa del usuario que crea el perfil o la entidad. Las unidades organizativas ya no se pueden eliminar y dejar vacías.
* Al publicar un recurso personalizado, ahora se muestra una ventana emergente de confirmación después de la preparación.
* Se ha mejorado el mensaje emergente que aparece cuando falla un recurso personalizado para una mejor claridad.
* Se ha mejorado el editor de expresiones en flujos de trabajo para evitar errores de ejecución. Hay [nuevas funciones](../../automating/using/customizing-workflow-external-parameters.md) disponibles: se pueden utilizar en todas las actividades que permiten utilizar variables de evento después de invocar a un flujo de trabajo con parámetros externos. Además, ahora se muestra la información de objeto en el editor de expresiones con la descripción de la función.
* [Se han agregado nuevos filtros a la lista de eventos transaccionales. ](../../channels/using/configuring-transactional-event.md#searching-transactional-events) Permiten filtrar las configuraciones de evento según su estado, así como la última vez que se recibió un evento.
* Los registros que se muestran al exportar los paquetes son más específicos y detallados sobre los errores encontrados en caso de error.
* Después de enviar un mensaje, ahora puede buscar, filtrar y exportar la lista de [direcciones URL rastreadas](../../sending/using/tracking-messages.md).
* La [sincronización automática entre Experience Platform Launch y Campaign](../../administration/using/configuring-a-mobile-application.md#aepsdk-workflow) ahora es GA y está activada de forma predeterminada.
* Se ha optimizado el tamaño de los paquetes de exportación de flujo de trabajo eliminando la exportación de envío de pruebas.
* Se ha agregado un nuevo mensaje para mostrar el tamaño del archivo descargado en la actividad de **transferencia de archivos**.
* Se han mejorado los mensajes de error para tokens de sesión no válidos.
* Un nuevo mecanismo ahora evita que el seguimiento de eventos de los servidores proxy se agregue a los registros de seguimiento y sistemas de informes.
* Se ha agregado un nuevo mensaje de advertencia para depurar las actividades de administración de datos conectadas a una actividad de envío.
* Se han mejorado las etiquetas del espacio de trabajo del sistema de informes.
* Se ha añadido un nuevo paso de validación para evitar la eliminación de objetos técnicos en los mensajes transaccionales.
* Se ha agregado un nuevo filtro en el estado de envío en la pestaña **lista de ejecución** de un mensaje transaccional para mejorar la resolución de problemas.
* Para mejorar el rendimiento y optimizar el tiempo de ejecución, se han eliminado los índices no utilizados, según las estadísticas de uso de las tablas identificadas en análisis preliminares para más de 350 clientes. Las tablas afectadas son: nmsaddressStatus, nmscampaign, nmsdelivery, nmslandingpage, nmsprogram, nmsrecipient, nmsseedmember, nmsservice, nmssubhistorcp, nmsaudience, xtkworkflow

**Parches**

* Se ha corregido un problema que impedía usar un vínculo de destino para notificaciones push o mensajería en la aplicación cuando el seguimiento estaba habilitado.
* Se ha corregido un problema en el cual no se respetaba la alta prioridad en mensajes transaccionales en caso de envío masivo significativo.
* Se ha corregido un problema que podía impedir que asignara marcas a un correo electrónico transaccional. Durante el paso de publicación se muestran varios mensajes de error. (CAMP-44988)
* Se ha corregido un problema en la interfaz de usuario del flujo de trabajo que impedía guardar información en campos que solicitaban valores numéricos. (CAMP-44025)
* Se ha corregido un problema que podía mostrar un mensaje de error al usar una **actividad de prueba** en un flujo de trabajo de plantilla de importación. (CAMP-42910)
* Se ha corregido un problema que se producía al usar una actividad de **audiencia de lectura** que contenía un campo de tipo de lista desglosada y se conectaba a actividades de **Unión** o **Enriquecimiento**. (CAMP-42795)
* Se ha corregido un problema en los informes dinámicos al usar los segmentos predeterminados para filtrar datos en los informes. (CAMP-42627)
* Se ha corregido un problema que impedía establecer una actividad de **Planificador** en 12 de la mañana. (CAMP-42674)
* Se ha corregido un problema que podía interrumpir el envío de mensajes SMS cuando la conexión SMPP era inestable. (CAMP-42789)
* Se ha corregido un problema que impedía que se mostrara el botón **Detener preparación** después de actualizar la página. (CAMP-42721)
* Se ha corregido un problema que impedía que se mostraran los porcentajes de los informes de clics interactivos al importar contenido desde una dirección URL. (CAMP-44468)
* Se ha corregido un problema que podía mostrar un error de tiempo de espera al seleccionar un perfil para utilizarlo en el contexto de la sustitución de perfiles. (CAMP-44746)
* Se ha corregido un problema que podía impedir que las instancias funcionaran después de implementar recursos personalizados con definiciones de vínculos incorrectas. (CAMP-44406)
* Se ha corregido un problema que creaba entidades vinculadas vacías (tipologías, marcas, etc.) después de copiar y pegar un envío en una plantilla de campaña. (CAMP-44765)
* Se ha corregido un problema que impedía que se enviaran pruebas debido a un manejo incorrecto de las tablas de preparación de envíos en caso de que se bloqueara o se reiniciara la base de datos de Azure.
* Se ha corregido un problema que podía impedir la eliminación de vínculos del contenido de Experience Manager en un envío configurado con contenido multilingüe. (CAMP-44029)
* Se ha corregido un problema en los informes dinámicos que podía mostrar un mensaje de error al intentar filtrar las dimensiones.  (CAMP-43097)
* Se ha corregido un problema que podía mostrar una pantalla en blanco al intentar acceder a perfiles en una instancia configurada con recursos personalizados que contenía definiciones de vínculos específicas. (CAMP-41009)
* Se ha corregido un problema con los flujos de trabajo que se podía producir al usar una actividad de **Enriquecimiento** con dos actividades de entrada con ambos recursos de destinatario vinculados entre sí. (CAMP-42133)
* Se ha corregido un problema que provocaba que los flujos de trabajo de importación se reprodujeran al usar una actividad de **transferencia de archivos**. (CAMP-43754)
* Se ha corregido un problema que provocaba que no se tuvieran en cuenta los duplicados al crear un perfil con registros exportados. (CAMP-45031)
* Se ha corregido un problema que provocaba discrepancias de datos entre los informes de Adobe Campaign y los exportados en archivos PDF. (CAMP-43010)
* Se ha corregido un error que ocasionaba que fallara el flujo de trabajo del envío de correo directo al usar campos de datos ya existentes en funciones. (CAMP-42737)
* Se ha corregido un problema al importar paquetes, incluidos eventos transaccionales y plantillas de mensajes. El proceso de importación se detuvo al 5%. (CAMP-42544)
* Se ha corregido un problema que provocaba un error (TypeError no capturado) tras modificar la actividad de **Enriquecimiento** y agregar datos adicionales en un flujo de trabajo. (CAMP-41877)
* Se ha corregido un error que impedía la eliminación del flujo de trabajo. Los registros tuvieron que purgarse para eliminar el flujo de trabajo. (CAMP-44144)
* Se ha corregido un error al crear una página de aterrizaje con código HTML. Las casillas de verificación obligatorias no se reconocieron en Campaign y no estaban disponibles en la página de aterrizaje publicada. (CAMP-44181)
* Se ha corregido un problema que provocaba que los flujos de trabajo se reprodujeran al usar una actividad de **espera**. (CAMP-43981)
* Se ha corregido un problema al enviar mensajes transaccionales que hacía que varias direcciones de correo electrónico se dirigieran varias veces a un mismo envío. (CAMP-44202)
* Se ha corregido un error al usar la sustitución de perfiles con la personalización targetData. (CAMP-44996)
* Se ha corregido un problema que ocasionaba que la previsualización del envío fallara al exportar una plantilla de envíos en un paquete. (CAMP-44084)
* Se ha corregido un problema que impedía que se enviaran pruebas a perfiles de prueba al usar asignaciones de destino personalizadas. (CAMP-43701)
* Se ha corregido un error que se producía en los flujos de trabajo al usar la actividad **Leer Audiencia** y al segmentar una audiencia configurada con una dimensión de segmentación distinta a **Perfil**.  (CAMP-41885)
* Se ha corregido un problema que provocaba errores cuando el flujo de trabajo técnico **updateEventsStatus** tardaba demasiado en recuperar el historial de eventos (cuando se detuvo el flujo de trabajo). El campo acumulado “sumQueueTime” no utilizado se ha eliminado del flujo de trabajo para resolver el problema. (CAMP-43920)
* Se ha corregido un problema de memoria al implementar recursos personalizados. (CAMP-42909)
* Se ha corregido el problema de los mensajes transaccionales de falta de atributos en las colecciones. Ahora todos los atributos que faltan se definen con un valor predeterminado y se incluyen en la carga útil. (CAMP-42882)
* Se ha corregido un problema que podía afectar al rendimiento al consultar los registros de envío de evento en tiempo real. (CAMP-42759)
* Se ha corregido un error que se producía al usar extensiones de archivo en mayúsculas con recursos compartidos. (CAMP-44159)
* Se ha corregido un problema que mostraba un mensaje de error al probar la conexión con una cuenta externa antes de crearla. El botón **Probar conexión** ahora solo se muestra una vez creada la cuenta externa.
* Se ha corregido un problema que dejaba los mensajes como pendientes después de reiniciar el MTA mejorado en instancias configuradas con el uso compartido.
* Se ha corregido un problema que podía hacer que el recuento de perfiles activos no coincidiera con el número efectivo de envíos entregados.
* Se ha corregido un problema que podía provocar latencia al buscar recursos en el editor de consultas de un flujo de trabajo.
* Se ha corregido un problema al seleccionar los campos **Especificar que se deben tener en cuenta en la opción de búsqueda de texto** en un recurso personalizado. Si la lista del campo se deja vacía, produce un error en la publicación del recurso personalizado.
* Se ha corregido un problema de rendimiento al mostrar la información general de los recursos personalizados con un gran volumen de datos.
* Se ha corregido un problema que impedía importar un envío mediante sustituciones de perfil.
* Se ha corregido un problema al usar la sustitución de perfiles que impedía que las pruebas se enviaran inmediatamente si el envío estaba programado.
* Se ha corregido un problema que se producía al cargar una clave de Android para una aplicación móvil. El mensaje que se mostraba después de cargar correctamente la clave mostraba el valor de la clave anterior.
* Se ha corregido un problema que impedía crear perfiles de prueba a partir de mensajes transaccionales después de crear una configuración de evento con una colección que no contenía ningún atributo.
* Se ha corregido un problema que podía impedir la publicación de recursos personalizados después de crear un nuevo filtro con un acumulado.
* Se ha corregido un problema que provocaba una tasa de apertura de seguimiento incorrecta para los destinatarios de Gmail debido al proxy de imagen de Gmail.
* Se ha corregido un problema que provocaba errores de Memoria insuficiente al importar un paquete.
* Se ha corregido un problema que ocasionaba que la acción de desvinculación de Experience Manager fallara cuando el contenido incluía una ruta con el carácter “%20”.
* Se ha corregido un error en las etiquetas al duplicar las actividades de flujo de trabajo.
* Se ha corregido un problema con el selector de mensajes transaccionales en una página de aterrizaje cuando se seleccionaba la opción de **mensaje de envío de Inicio**.
* Se ha corregido un problema con los mensajes transaccionales o envíos recurrentes que impedía que el estado del envío se inicializara con el valor predeterminado correcto. También se han mejorado los registros de los errores.
* Se ha corregido un problema al ampliar la **Suscripción a un esquema de aplicación** (appSubscriptionRcp) con un vínculo de perfil mediante un campo personalizado. El índice no se creó automáticamente, lo que podría afectar al tiempo de envío de notificaciones push. (CAMP-41120)



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
<p>Consulte el vídeo de <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/privacy/privacy-overview.html?lang=es">procedimiento</a>.</p>
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
<p>Para obtener más información, consulte la <a href="../../automating/using/external-api.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/managing-processes-and-data/data-management-activities/external-api-activity.html?lang=es">videotutorial</a>.</p>
</td> 
</tr> 
</tbody> 
</table>

**Funciones adicionales** (a partir del 13 de julio)

* **Optimización de tiempo de envío con tecnología de IA y puntuación de perfiles**: ahora puede optimizar el diseño y el envío de los recorridos de los clientes para predecir las preferencias de participación de cada individuo. Con la tecnología de Journey AI, Adobe Campaign puede analizar y predecir las tasas abiertas, los tiempos de envío óptimos y la probable reproducción basada en las métricas de participación históricas. [Más información](../../sending/using/predictive.md)
* **Nueva regulación de privacidad de Brasil**: además de las capacidades de privacidad ya disponibles en Campaign, Adobe le ayuda a prepararse para la Lei Geral de Proteçao de Datos (LGPD) de Brasil. Al crear una solicitud de privacidad, se ha agregado la regulación LGPD en el servicio principal de privacidad de Adobe. [Más información](https://helpx.adobe.com/es/campaign/kb/campaign-privacy-overview.html)

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

* Se ha mejorado la activación de audiencias de Adobe Experience Platform desde la actividad **Leer audiencia** para proporcionar un mejor rendimiento y estabilidad. Además, los registros de flujo de trabajo se han simplificado para añadir claridad y detallado con respecto a los trabajos de activación, lo que facilita la monitorización y la resolución de problemas al leer audiencias de Adobe Experience Platform.

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


![](assets/do-not-localize/cp-icon.png) **El nuevo Panel de control puede lanzarse** con la renovación de los certificados para los subdominios CNAME. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es).

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
    <p>Para obtener más información, consulte la <a href="../../sending/using/testing-messages-using-target.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html?lang=es">videotutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>En abril se lanzarán nuevas funciones en el Panel de control de Campaign, incluida la administración de registros TXT de Google, la supervisión de espacio en la base de datos y las alertas por correo electrónico. Para obtener más información sobre estas funciones, consulte la [Nota de la versión del Panel de control](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es).

**Mejoras**

* Se ha mejorado la experiencia de usuario de mensajería transaccional y se ha mejorado la coherencia de la interfaz. [Más información](../../channels/using/getting-started-with-transactional-msg.md)
* Ahora, Campaign Standard le permite enviar pruebas a perfiles de prueba con datos adicionales de flujos de trabajo.
* Se han actualizado los mecanismos de protección de la actividad API externa. [Más información](../../automating/using/external-api.md)

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
* El MCPNS no admite la adición de APNS y APNS-SANDBOX como plataformas en una aplicación. Después de añadir correctamente el certificado en Adobe Campaign Standard, ya no podrá volver a cambiar la configuración, ya que solo se puede añadir una plataforma APNS (producción o zona protegida) a la aplicación MCPNS.

**Integraciones de Experience Platform**

>[!NOTE]
>
>Las funciones de Adobe Experience Platform en Campaign Standard se encuentran actualmente en fase beta, por lo que pueden estar sujetas a actualizaciones frecuentes sin previo aviso. Consulte la documentación detallada: Experience Platform Data Connector, Audience Destinations

* Ahora, en los registros de flujo de trabajo y cada 10 minutos, Campaign muestra el número de registros que ya ha procesado el trabajo que se está ejecutando.
* Se ha corregido un problema que se podía producir al importar un perfil de Adobe Experience Platform que se hubiera eliminado de la base de datos.
* Se ha corregido un problema en los registros del flujo de trabajo que podía mostrar un resultado incorrecto para el número total de registros importados.

**Parches**

* Se ha corregido un problema con la actividad flujo de trabajo de **Enriquecimiento** que se podía producir al añadir espacios en el campo **Alias**, el cual a continuación creaba un nuevo elemento de fila. (CAMP-39229)
* Se ha corregido un problema en el cual cada perfil de prueba se podía dirigir al enviar un mensaje de prueba.
* Se ha corregido un problema que se producía tras cancelar la publicación y eliminar una configuración de evento. [Más información](../../channels/using/publishing-transactional-event.md#deleting-an-event)
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
    <p>Tenga en cuenta que esta capacidad solo está disponible para clientes alojados en Azure.</p>
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
    <p>Tenga en cuenta que esta capacidad solo está disponible para clientes alojados en Azure.</p>
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
* [!DNL Adobe Creative SDK] se ha retirado del mercado. Ahora está en desuso en Campaign Standard. Consulte la página [Funciones obsoletas y eliminadas](../../rn/using/deprecated-features.md).


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
