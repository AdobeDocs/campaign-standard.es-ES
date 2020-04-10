---
title: Última versión
description: Esta página lista todas las versiones recientes de Adobe Campaign Standard.
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
source-git-commit: 66e480e957d12275d2ce5575c99b0808462588f9

---


# Última versión{#latest-release}

[Planificación](https://helpx.adobe.com/es/campaign/kb/acs-release-planning.html) de versiones| [Versiones](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html) del Panel de control| Actualizaciones [de documentación](../../rn/using/documentation-updates.md) | Notas de revisión [anteriores](../../rn/using/release-notes-2019.md) | Características [obsoletas](https://helpx.adobe.com/es/campaign/kb/acs-deprecated-and-removed-features.html)

[Haga clic aquí](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) para suscribirse a las notificaciones de la versión y obtener detalles sobre las últimas versiones de Adobe Experience Cloud directamente en la bandeja de entrada.

## Versión 20.2: abril de 2020 {#release-20-2---april-2020}

**Novedades**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integración de blob de Azure</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>El conector de almacenamiento de blob de Azure ahora se puede utilizar para importar o exportar datos a Adobe Campaign mediante una actividad de flujo de trabajo de archivo <strong>de</strong> transferencia. </p>
    <p>Para obtener más información, consulte la <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentación detallada</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Pruebas de correo electrónico con perfiles de objetivo</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>Además de probar los perfiles, ahora puede probar los correos electrónicos en perfiles con objetivos reales. Esto le permite obtener una representación exacta del mensaje que recibirá el perfil: campos personalizados, información dinámica y personalizada, incluidos datos adicionales de flujos de trabajo, etc. </p>
    <p>Para obtener más información, consulte la <a href="../../sending/using/testing-messages-using-target.md">documentación detallada</a> y el <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">videotutorial</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>En abril se lanzarán nuevas funciones en el Panel de control de Campañas, incluida la administración de registros TXT de Google, la supervisión de espacio en la base de datos y las alertas por correo electrónico. Para obtener más información sobre estas funciones, consulte la Nota [de revisión del panel de](https://docs.adobe.com/content/help/es-ES/control-panel/using/release-notes.html)control.

**Mejoras**

* Se ha mejorado la experiencia de usuario de mensajería transaccional y se ha mejorado la coherencia de la interfaz. [Más información](../../channels/using/about-transactional-messaging.md)
* Campaign Standard ahora le permite enviar pruebas a perfiles de prueba con datos adicionales de flujos de trabajo.
* Se han actualizado los protecciones de la actividad de API externa. [Más información](../../automating/using/external-api.md)

**Mejoras en el Diseñador de correo electrónico**

* Se ha corregido un problema que afectaba al escape al hacer clic varias veces en una imagen personalizada.
* Se ha corregido un problema que se producía al duplicar componentes de texto dinámico y que podía provocar la duplicación de líneas erróneas. (CAMP-41249)
* Se ha corregido un problema con el relleno en Outlook al definir el relleno en el nivel de tabla en lugar del nivel de div.
* Se ha corregido un problema que provocaba que se modificara la anchura de una imagen al cambiar al modo HTML. (CAMP-41116)
* Se ha corregido un problema que impedía que el componente de medios sociales fuera accesible al proporcionar texto alternativo a los iconos. (CAMP-41345)
* Se ha corregido un problema que provocaba que se mostraran `<br>` etiquetas visibles al usar copiar y pegar en el Diseñador de correo electrónico.
* Se ha corregido un problema que provocaba que las etiquetas HTML se mostraran en el correo electrónico después de cambiar del contenido HTML al texto sin formato. (CAMP-41138)
* Se ha corregido un problema que impedía procesar botones con un solo borde definido.
* Se ha corregido un problema en la sangría HTML que provocaba que el pie de página de los correos electrónicos se moviera hacia la izquierda en Microsoft Outlook. (CAMP-40987)
* Se ha corregido un problema que provocaba que los campos de personalización dirigidos a un atributo de colección definido en HTML se copiaran en el contenido de texto sin formato al cambiar al modo de texto sin formato. (CAMP-40365)
* Se ha corregido un problema que impedía que los vínculos se insertaran en un segmento de texto seleccionado. (CAMP-41406)
* Se ha corregido un problema que provocaba que la fecha se modificara al seleccionar una zona horaria en el editor de consultas. (CAMP-38277)

**Otros cambios**

* El flujo de trabajo **integrado Reconciliación de KPI con Adobe Analytics** ahora se ejecuta hasta la fecha actual en lugar de ejecutarse para un solo día.
* El MCPNS no admite la adición de APNS y APNS-SANDBOX como plataformas en una aplicación. Después de agregar correctamente el certificado en Adobe Campaign Standard, ya no podrá volver a cambiar la configuración, ya que solo se puede agregar una plataforma APNS (producción o simulación de pruebas) a la aplicación MCPNS.

**Integraciones de la plataforma de experiencias**

>[!NOTE]
>
>Las funciones de la plataforma de Adobe Experience Platform en Campaign Standard se encuentran actualmente en fase beta, lo que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Consulte la documentación detallada: Conector [de datos de la plataforma de](../../administration/using/aep-about-data-connector.md)experiencia, destinos de [Audiencia](../../audiences/using/aep-about-audience-destinations-service.md)

* En los registros de flujo de trabajo, cada 10 minutos, la Campaña ahora muestra el número de registros que ya ha procesado el trabajo que se está ejecutando.
* Se ha corregido un problema que se podía producir al importar un perfil de Adobe Experience Platform que se hubiera eliminado de la base de datos.
* Se ha corregido un problema en los registros de flujo de trabajo que podía mostrar un resultado incorrecto para el número total de registros importados.

**Parches**

* Se ha corregido un problema con la actividad del flujo de trabajo de **Enriquecimiento** que se podía producir al agregar espacios en el campo **Alias** , el cual a continuación creaba un nuevo elemento de fila. (CAMP-39229)
* Se corrigió un problema en el cual cada perfil de prueba se podía dirigir al enviar un mensaje de prueba.
* Se ha corregido un problema que se producía tras cancelar la publicación y eliminar una configuración de evento. [Más información](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Se corrigió un problema en el cual el botón **Guardar** desaparecía al realizar cambios en flujos de trabajo.
* Se ha corregido un problema que se producía al eliminar una solicitud de privacidad manualmente en Campaña después de procesarla, lo que impedía que los datos asociados a la solicitud se eliminaran incluso después de la limpieza.
* Se ha corregido un problema que se podía producir al obtener una vista previa o enviar mensajes que incluían caracteres especiales de Adobe Experience Manager.
* Se ha corregido un problema que se podía producir en flujos de trabajo al ejecutar una actividad con varias transiciones de entrada.
* Se ha corregido un problema que impedía que los usuarios estándar usaran las &#39;Suscripciones a una aplicación&#39; como dimensión de destinatario en una consulta de flujo de trabajo o un envío. (CAMP-37618)