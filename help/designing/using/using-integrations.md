---
solution: Campaign Standard
product: campaign
title: 'Diseño de correos electrónicos mediante integraciones de Adobe Campaign '
description: Descubra cómo diseñar correos electrónicos mediante integraciones de Adobe Campaign en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
translation-type: tm+mt
source-git-commit: 2a92600df01fd3c78a2b35c8034a2ce347e5c1d8
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 6%

---


# Diseño de correo electrónico de varias soluciones {#multi-solution-email-design}

Adobe Campaign oferta varias opciones de creación de correo electrónico. Puede utilizar soluciones como Dreamweaver para editar el contenido del correo electrónico y crear mensajes interactivos en el Diseñador de correo electrónico. También puede enviar contenido por correo electrónico con Adobe Experience Manager y utilizarlo en sus correos electrónicos en Adobe Campaign Standard.

## Edición de contenido en Dreamweaver {#editing-content-in-dreamweaver}

La integración de Adobe Campaign Standard con Dreamweaver le permite editar el contenido de un correo electrónico en la interfaz de Dreamweaver. Tiene acceso a la poderosa interfaz de Dreamweaver para diseñar y desarrollar contenido de correo electrónico interactivo.

* **Sincronización bidireccional**

   Cada vez que se realiza una edición en un producto, ésta se actualiza en tiempo real en el otro. Si desea cambiar el color del texto en Dreamweaver, en cuanto realice esa edición, el color del texto estará activo en la Campaña. Además, cuando selecciona código en Dreamweaver o Campaña, ya que los números de línea son los mismos, la selección permanece entre los dos productos, lo que resulta muy útil cuando busca algo específico en el código.

* **Carga de imágenes locales en Adobe Campaign mediante Dreamweaver**

   Al crear o editar un mensaje de correo electrónico en Dreamweaver, puede simplemente seleccionar una imagen del equipo local o de escritorio. Aunque Dreamweaver siempre le ha permitido hacer esto, cuando Dreamweaver y Campaña están conectados, el archivo local se carga inmediatamente en el servidor de Adobe Campaign: no es necesario cargar imágenes manualmente a medida que cambia el contenido. Además, garantiza que las últimas imágenes siempre estén activas en Campaña.

* **Añadir personalización de Campañas en Dreamweaver**

   Para el desarrollador de correo electrónico ya no es necesario agregar texto como `[[FIRSTNAME_PLACEHOLDER]]` ni buscar la sintaxis de las tablas del modelo de datos. La barra de herramientas de Campaña de Dreamweaver se conecta directamente al modelo de datos de la instancia de Campaña. Esto significa que puede extraer los datos que desee para la personalización, de algo como Nombre a Dirección. Si ha creado Bloques de contenido dentro de la Campaña, también puede extraerlos directamente en Dreamweaver.

Esta capacidad se detalla en la documentación de Dreamweaver, accesible [aquí](https://helpx.adobe.com/es/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#video)

## Edición de contenido en Experience Manager {#editing-content-in-experience-manager}

El contenido del correo electrónico se puede editar en el Experience Manager y luego utilizar para uno o varios mensajes de correo electrónico en Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Listas de productos {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Uso de listados de productos"
>abstract="Las listas de productos le permiten hacer referencia a una colección de datos y mostrarla en el contenido del correo electrónico."

Las listas de productos le permiten hacer referencia a una o varias colecciones de datos en el contenido del correo electrónico. Estos listados están disponibles para correos electrónicos transaccionales. Una sección dedicada para esta función está disponible [aquí](../../channels/using/event-transactional-messages.md#using-product-listings-in-a-transactional-message).

## Comparación de opciones de diseño de correo electrónico {#email-design-options-comparison}

Adobe Campaign oferta varias opciones de creación de correo electrónico. En el cuadro que figura a continuación se muestran las principales posibilidades, beneficios y limitaciones de cada uno de ellos.

<table> 
 <thead> 
  <tr> 
   <th> </th> 
   <th> Diseñador de correo electrónico<br /> </th> 
   <th> Experience Manager<br /> </th> 
   <th> Dreamweaver<br /> </th> 
  </tr> 
 </thead> 
 <tbody> 
  <tr> 
   <td> <strong>Correo electrónico en blanco de inicio</strong><br /> </td> 
   <td> Compatible<br /> </td> 
   <td> Compatible<br /> </td> 
   <td> Compatible<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Escribir HTML</strong><br /> </td> 
   <td> Compatible<br /> </td> 
   <td> No admitido<br /> </td> 
   <td> Compatible<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Actualizar HTML</strong><br /> </td> 
   <td> Solo dentro de un componente HTML<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Compatible<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalización básica</strong><br /> </td> 
   <td> Compatible<br /> </td> 
   <td> Compatible<br /> </td> 
   <td> Compatible<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Personalización avanzada</strong><br /> </td> 
   <td> Compatible<br /> </td> 
   <td> Not supported<br /> </td> 
   <td> Not supported<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Prueba/Previsualización</strong><br /> </td> 
   <td> Compatible<br /> </td> 
   <td> Previsualización en Prueba de AEM<br /> en Campaña<br /> </td> 
   <td> Previsualización y prueba en Campaña<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Listas de productos</strong><br /> </td> 
   <td> Compatible con mensajes transaccionales de correo electrónico<br /> </td> 
   <td> No admitido<br /> </td> 
   <td> No admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ventajas</strong><br /> </td> 
   <td> 
     <p>- Fácil creación de correos electrónicos mediante la experiencia de arrastrar y soltar</p>
     <p>- Funciones similares al editor de contenido heredado</p>
     <p>- Contenido reutilizable con fragmentos</p>
  </td> 
   <td> 
     <p>- Reutilización de recursos de sitios web en correos electrónicos</p>
     <p>- Aprovechar el poder del Experience Manager en el contenido del correo electrónico</p>
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
   <td> Los especialistas en marketing que deseen mantener la flexibilidad para utilizar componentes HTML en combinación con funciones de arrastrar y soltar<br /> </td> 
   <td> Los especialistas en marketing ya utilizan Experience Manager que desean utilizar plantillas de correo electrónico estándar con poca personalización<br /> </td> 
   <td> Desarrolladores que deseen codificar el contenido del correo electrónico e integrarse directamente con Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para obtener más información</strong><br /> </td> 
   <td> Consulte <a href="../../designing/using/designing-content-in-adobe-campaign.md">Acerca del Diseñador de correo electrónico</a>.<br /> </td> 
   <td> Consulte <a href="../../integrating/using/integrating-with-experience-manager.md">Integración con Experience Manager</a>.<br /> </td> 
   <td> Consulte <a href="https://helpx.adobe.com/es/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver y Campaña</a> y vea este <a href="#video">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Tutorial video {#video}

Este vídeo muestra cómo crear y editar contenido para Adobe Campaign Standard con Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

Hay disponibles más vídeos de procedimientos para Campaign Standards [aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
