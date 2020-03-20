---
title: Última versión
description: Esta página enumera todas las versiones recientes de Adobe Campaign Standard.
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
source-git-commit: b22d6ae9e7ccd305d437d5d4390e1d95393e6344

---


# Última versión{#latest-release}

[Planificación](https://helpx.adobe.com/campaign/kb/acs-release-planning.html) de versiones| [Versiones](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html) del Panel de control| Actualizaciones [de documentación](../../rn/using/documentation-updates.md) | Notas de revisión [anteriores](../../rn/using/release-notes-2019.md) | Características [obsoletas](https://helpx.adobe.com/campaign/kb/acs-deprecated-and-removed-features.html)

## Versión 20.2 - Marzo de 2020 {#release-20-2---march-2020}

**Novedades?**

<table> 
 <thead> 
  <tr> 
   <th> <strong>Integración de blob de Azure</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>El conector de almacenamiento de blob de Azure ahora se puede usar para importar o exportar datos a Adobe Campaign mediante una actividad de flujo de trabajo de archivos <strong>de</strong> transferencia. </p>
    <p>Para obtener más información, consulte la <a href="../../administration/using/external-accounts.md#microsoft-azure-external-account">documentación detallada</a>.</p>
   </td> 
  </tr> 
 </tbody> 
</table>

<table> 
 <thead> 
  <tr> 
   <th> <strong>Dominio e interfaz de Experience Cloud unificada</strong><br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <p>La barra superior de la interfaz se ha mejorado para mejorar la experiencia en todas las aplicaciones de Experience Cloud. El acceso a las soluciones se ha unificado con la siguiente dirección URL: experience.adobe.com/&lt;nombre de la aplicación&gt;. El encabezado ahora le permite cambiar más fácilmente entre las soluciones y muestra ayuda y notificaciones mejoradas.</p>
    <p>Para obtener más información, consulte la <a href="../../start/using/interface-description.md#top-bar">documentación detallada</a>. </p>
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
   <td> <p>Además de probar los perfiles, ahora puede probar los correos electrónicos en perfiles reales con objetivo. Esto le permite obtener una representación exacta del mensaje que recibirá el perfil: campos personalizados, información dinámica y personalizada, incluidos datos adicionales de flujos de trabajo, etc. </p>
    <p>For more information, refer to the <a href="../../sending/using/testing-messages-using-target.md">detailed documentation</a> and the <a href="https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/communication-channels/email/profile-substitution.html">tutorial video</a>. </p>
   </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>En abril se lanzarán nuevas funciones en el Panel de control de campañas, incluida la administración de registros TXT de Google, la supervisión de espacio en la base de datos y las alertas por correo electrónico. Para obtener más información sobre estas funciones, consulte la Nota [de revisión del panel de](https://docs.adobe.com/content/help/en/control-panel/using/release-notes.html)control.

**Mejoras**

* Se ha mejorado la experiencia de usuario de mensajería transaccional y se ha mejorado la coherencia de la interfaz. [Más información](../../channels/using/about-transactional-messaging.md)
* Campaign Standard ahora le permite enviar pruebas a perfiles de prueba con datos adicionales de flujos de trabajo.
* Se han actualizado los resguardos de la actividad de API externa. [Más información](../../automating/using/external-api.md)

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
* Se ha corregido un problema que provocaba que los campos de personalización destinados a un atributo de colección definido en HTML se copiaran en el contenido de texto sin formato al cambiar al modo de texto sin formato. (CAMP-40365)
* Se ha corregido un problema que impedía que los vínculos se insertaran en un segmento de texto seleccionado. (CAMP-41406)
* Se corrigió un problema que ocasionaba que la fecha se alterara al seleccionar una zona horaria en el editor de consultas. (CAMP-38277)

**Otros cambios**

* El flujo de trabajo **integrado Reconciliación de KPI con Adobe Analytics** ahora se ejecuta hasta la fecha actual en lugar de ejecutarse para un solo día.
* El MCPNS no admite la adición de APNS y APNS-SANDBOX como plataformas en una aplicación. Después de agregar correctamente el certificado en Adobe Campaign Standard, ya no podrá volver a cambiar la configuración, ya que solo se puede agregar una plataforma APNS (producción o simulación de pruebas) a la aplicación MCPNS.

**Integraciones de la plataforma de experiencias**

>[!NOTE]
>
>Las funciones de la plataforma de experiencia de Adobe en Campaign Standard se encuentran actualmente en versión beta, lo que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Consulte la documentación detallada: Conector [de datos de la plataforma de](../../administration/using/aep-about-data-connector.md)experiencia, destinos [de audiencia](../../audiences/using/aep-about-audience-destinations-service.md)

* En los registros de flujo de trabajo, cada 10 minutos, Campaign muestra ahora el número de registros que el trabajo que se está ejecutando ya ha procesado.
* Se ha corregido un problema que se podía producir al importar un perfil de Adobe Experience Platform que se había eliminado de la base de datos.
* Se ha corregido un problema en los registros de flujo de trabajo que podía mostrar un resultado incorrecto para el número total de registros importados.

**Parches**

* Se ha corregido un problema con la actividad de flujo de trabajo **Enriquecimiento** que se podía producir al agregar espacios en el campo **Alias** , el cual a continuación creaba un nuevo elemento de fila. (CAMP-39229)
* Se corrigió un problema en el cual cada perfil de prueba se podía dirigir al enviar un mensaje de prueba.
* Se ha corregido un problema que se producía tras cancelar la publicación y eliminar una configuración de evento. [Más información](../../administration/using/configuring-transactional-messaging.md#deleting-an-event)
* Se corrigió un problema en el cual el botón **Guardar** desaparecía al realizar cambios en los flujos de trabajo.
* Se ha corregido un problema que se producía al eliminar una solicitud de privacidad manualmente en Campaign después de que se procesara, lo que impedía que los datos asociados a la solicitud se eliminaran incluso después de la limpieza.
* Se ha corregido un problema que se podía producir al obtener una vista previa o enviar mensajes que incluían caracteres especiales de Adobe Experience Manager.
* Se ha corregido un problema que podía producirse en los flujos de trabajo al ejecutar una actividad con varias transiciones de entrada.