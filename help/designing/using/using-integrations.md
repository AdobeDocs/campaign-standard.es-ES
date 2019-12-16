---
title: 'Diseño de correos electrónicos mediante integraciones de Adobe Campaign '
description: Descubra cómo diseñar correos electrónicos mediante integraciones de Adobe Campaign en el Diseñador de correo electrónico.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: designing
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1b70e18be29fd48d102313f6d741e9ffe053cc34

---


# Diseño de correo electrónico de varias soluciones {#multi-solution-email-design}

Adobe Campaign ofrece varias opciones de creación de correo electrónico. Puede utilizar soluciones como Dreamweaver para editar el contenido del correo electrónico y crear mensajes interactivos en el Diseñador de correo electrónico. También puede enviar contenido por correo electrónico con Adobe Experience Manager y utilizarlo en sus correos electrónicos en Adobe Campaign Standard.

## Edición de contenido en Dreamweaver {#editing-content-in-dreamweaver}

La integración de Adobe Campaign Standard con Dreamweaver le permite editar el contenido de un correo electrónico en la interfaz de Dreamweaver. Tiene acceso a la poderosa interfaz de Dreamweaver para diseñar y desarrollar contenido de correo electrónico interactivo.

* **Sincronización bidireccional**

   Cada vez que se realiza una edición en un producto, ésta se actualiza en tiempo real en el otro. Si desea cambiar el color del texto en Dreamweaver, en cuanto realice la edición, el color del texto estará activo en Campaign. Además, al seleccionar código en Dreamweaver o Campaign, como los números de línea son los mismos, la selección permanece entre los dos productos, lo que resulta muy útil cuando se busca algo específico en el código.

* **Carga de imágenes locales en Adobe Campaign mediante Dreamweaver**

   Al crear o editar un mensaje de correo electrónico en Dreamweaver, puede simplemente seleccionar una imagen del equipo de escritorio o local. Aunque Dreamweaver siempre le ha permitido hacer esto, cuando Dreamweaver y Campaign están conectados, el archivo local se carga inmediatamente en el servidor de Adobe Campaign: no es necesario cargar imágenes manualmente a medida que cambia el contenido. Además, garantiza que las últimas imágenes siempre estén activas en Campaign.

* **Adición de la personalización de campañas en Dreamweaver**

   Para el desarrollador de correo electrónico ya no es necesario agregar texto como `[[FIRSTNAME_PLACEHOLDER]]` ni buscar la sintaxis de las tablas del modelo de datos. La barra de herramientas Campaña de Dreamweaver se conecta directamente al modelo de datos de la instancia de Campaign. Esto significa que puede extraer los datos que desee para la personalización, de algo como Nombre a Dirección. Si ha creado bloques de contenido dentro de Campaign, también puede extraerlos directamente en Dreamweaver.

Esta capacidad se detalla en la documentación de Dreamweaver, a la que se puede acceder [aquí](https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html). También hay disponible un [vídeo](https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html) de demostración.

## Edición de contenido en Experience Manager {#editing-content-in-experience-manager}

El contenido del correo electrónico se puede editar en Experience Manager y luego utilizar para uno o varios mensajes de correo electrónico en Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Comparación de opciones de diseño de correo electrónico {#email-design-options-comparison}

Adobe Campaign ofrece varias opciones de creación de correo electrónico. En el cuadro que figura a continuación se muestran las principales posibilidades, beneficios y limitaciones de cada uno de ellos.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Email Designer<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Iniciar correo electrónico en blanco</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Escribir HTML</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td>  No admitido<br /> </td> 
   <td> Admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Actualizar HTML</strong><br /> </td> 
   <td> Solo dentro de un componente HTML<br /> </td> 
   <td>  No admitido<br /> </td> 
   <td> Admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalización básica</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalización avanzada</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td>  No admitido<br /> </td> 
   <td>  No admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Prueba/Vista previa</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Vista previa en la prueba de AEM<br /> en Campaign<br /> </td> 
   <td> Vista previa y prueba en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Listas de productos</strong><br /> </td> 
   <td> Admitido en mensajes transaccionales de correo electrónico<br /> </td> 
   <td>  No admitido<br /> </td> 
   <td>  No admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Beneficios</strong><br /> </td> 
   <td> 
     <p>- Fácil creación de correos electrónicos mediante la experiencia de arrastrar y soltar</p>
     <p>- Funciones similares al editor de contenido heredado</p>
     <p>- Contenido reutilizable con fragmentos</p>
  </td> 
   <td> 
     <p>- Reutilización de recursos de sitios web en correos electrónicos</p>
     <p>- Aprovechamiento del poder de Experience Manager en el contenido del correo electrónico</p>
    </td> 
   <td> 
    <p>- Capacidad de un desarrollador para codificar directamente un correo electrónico</p>
    <p>- Sincronización bidireccional</p>
    <p>- Edición sin conexión en Dreamweaver y sincronización posterior</p>
    <p>- Carga de imágenes en Adobe Campaign a través de Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitaciones</strong><br /> </td> 
   <td> 
     <p>- No hay contenido condicional dentro de los fragmentos</p>
     <p>- No es posible utilizar fragmentos de Experience Manager</p>
  </td> 
   <td> 
     <p>- Personalización avanzada difícil de implementar</p>
     <p>- Necesidad de enviar pruebas en Adobe Campaign</p>
  </td> 
   <td> Contenido dinámico no admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Audiencia</strong><br /> </td> 
   <td> Los especialistas en marketing que deseen mantener la flexibilidad para utilizar componentes HTML junto con las funciones de arrastrar y soltar<br /> </td> 
   <td> Los especialistas en marketing ya utilizan Experience Manager que desean utilizar plantillas de correo electrónico estándar con poca personalización<br /> </td> 
   <td> Desarrolladores que deseen codificar el contenido del correo electrónico e integrarse directamente con Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para obtener más información</strong><br /> </td> 
   <td> Consulte <a href="../../designing/using/designing-content-in-adobe-campaign.md">Acerca del Diseñador</a>de correo electrónico.<br /> </td> 
   <td> See <a href="../../integrating/using/integrating-with-experience-manager.md">Integrating with Experience Manager</a>.<br /> </td> 
   <td> Consulte <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver y Campaign</a> y vea este <a href="https://helpx.adobe.com/campaign/kt/acs/using/acs-dreamweaver-integration-feature-video-use.html">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>
