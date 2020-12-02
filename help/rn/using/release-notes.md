---
solution: Campaign Standard
product: campaign
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
audience: rn
content-type: reference
topic-tags: campaign-standard-releases
translation-type: tm+mt
source-git-commit: fc755f3176622e1faf08ccfa4236e016110f9a68
workflow-type: tm+mt
source-wordcount: '2412'
ht-degree: 100%

---


# Última versión{#latest-release}

[Planificación de versiones](../../rn/using/release-planning.md) | [Versiones del Panel de control](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html) | [Actualizaciones de documentación](../../rn/using/documentation-updates.md) | [Notas de la versión anteriores](../../rn/using/release-notes-2020.md) | [Funciones obsoletas](../../rn/using/deprecated-features.md)

![](assets/do-not-localize/cp-icon.png) **la nueva versión de Panel de control de Campaign de octubre** con configuración de dominio mediante CNAME y nuevas funciones de supervisión de bases de datos. [Más información](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html).

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
<p>Para obtener más información, consulte la <a href="../../sending/using/control-group.md">documentación detallada</a> y el <a href="https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/communication-channels/email/control-groups.html?lang=es#communication-channels">videotutorial</a>.
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
  <p>Journey AI utiliza aprendizaje automático avanzado (ML) para permitir que las compañías optimicen el diseño y el envío de los recorridos de los clientes mediante la predicción de las preferencias de participación de cada individuo.</p>
  <P>Journey AI consta de dos características de ML:</p>
<ul> 
     <li> <strong>Puntuación de participación predictiva</strong>: identifica de forma inteligente el nivel de compromiso preferido de los clientes para destinar y personalizar de mejor manera los mensajes a fin de aumentar las conversiones y la retención. Vea el <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-engagement-scoring.html">vídeo explicativo</a>.</li> 
     <li> <strong>Optimización del tiempo de envío predictivo</strong>: predice el mejor momento para enviar correos electrónicos a cada individuo en una campaña a fin de maximizar las tasas de participación y mejorar el ROI de la campaña de correo electrónico. Vea el <a href="https://docs.adobe.com/content/help/es-ES/campaign-standard-learn/tutorials/communication-channels/email/journey-ai/predictive-send-time-optimization.html">vídeo explicativo</a>.</li>
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

