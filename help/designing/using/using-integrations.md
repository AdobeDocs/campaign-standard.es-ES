---
solution: Campaign Standard
product: campaign
title: 'Diseño de correos electrónicos a través de integraciones de Adobe Campaign '
description: Descubra cómo diseñar correos electrónicos a través de integraciones de Adobe Campaign en el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Diseño de correo electrónico
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 8%

---

# Diseño de correo electrónico de varias soluciones {#multi-solution-email-design}

Adobe Campaign ofrece varias opciones de creación de correo electrónico. Puede utilizar soluciones como Dreamweaver para editar el contenido del correo electrónico y crear mensajes interactivos en el Diseñador de correo electrónico. También puede enviar contenido por correo electrónico con Adobe Experience Manager y utilizarlo en los mensajes de correo electrónico en Adobe Campaign Standard.

## Edición de contenido en Dreamweaver {#editing-content-in-dreamweaver}

La integración de Adobe Campaign Standard con Dreamweaver permite editar el contenido de un correo electrónico en la interfaz de Dreamweaver. Tiene acceso a la potente interfaz de Dreamweaver para diseñar y desarrollar contenido de correo electrónico interactivo.

* **Sincronización bidireccional**

   Cada vez que se realiza una edición en un producto, esta se actualiza en tiempo real en el otro. Si desea cambiar el color del texto en Dreamweaver, tan pronto como realice la edición, el color del texto estará activo en Campaign. Además, al seleccionar código en Dreamweaver o Campaign, ya que los números de línea son los mismos, la selección se mantiene entre los dos productos, lo que resulta muy útil cuando se busca algo específico en el código.

* **Carga de imágenes locales en Adobe Campaign mediante Dreamweaver**

   Al crear o editar un correo electrónico en Dreamweaver, simplemente puede seleccionar una imagen del escritorio o del equipo local. Aunque Dreamweaver siempre le ha permitido hacerlo, cuando Dreamweaver y Campaign están conectados, el archivo local se carga inmediatamente en el servidor de Adobe Campaign: no es necesario cargar imágenes manualmente como cambios de contenido. Además, garantiza que las últimas imágenes estén siempre activas en Campaign.

* **Añadir personalización de Campaign en Dreamweaver**

   Para el desarrollador de correo electrónico, ya no es necesario agregar texto como `[[FIRSTNAME_PLACEHOLDER]]` ni buscar la sintaxis de las tablas del modelo de datos. La barra de herramientas de Campaign en Dreamweaver se conecta directamente al modelo de datos de la instancia de Campaign. Esto significa que puede incorporar cualquier dato que desee personalizar, de algo como Nombre a Dirección. Si ha creado bloques de contenido dentro de Campaign, también puede extraerlos directamente en Dreamweaver.

Esta funcionalidad se detalla en la documentación de Dreamweaver accesible [aquí](https://helpx.adobe.com/es/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Descubra esta función en vídeo](#video)

## Edición de contenido en Experience Manager {#editing-content-in-experience-manager}

El contenido del correo electrónico se puede editar en Experience Manager y luego utilizar para uno o varios mensajes de correo electrónico en Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Listas de productos {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Uso de listados de productos"
>abstract="Las listas de productos permiten hacer referencia a una recopilación de datos y mostrarla en el contenido del correo electrónico."

Las listas de productos permiten hacer referencia a una o más colecciones de datos en el contenido del correo electrónico. Estas listas están disponibles para correos electrónicos transaccionales. Hay disponible una sección dedicada para esta función [aquí](../../designing/using/using-product-listings.md).

## Comparación de opciones de diseño de correo electrónico {#email-design-options-comparison}

Adobe Campaign ofrece varias opciones de creación de correo electrónico. En el cuadro siguiente se muestran las principales posibilidades, ventajas y limitaciones de cada una de ellas.

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
   <td> <strong>Iniciar correo electrónico en blanco</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Escribir HTML</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td> No admitido<br /> </td> 
   <td> Admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Actualizar HTML</strong><br /> </td> 
   <td> Solo dentro de un componente HTML<br /> </td> 
   <td> No admitido<br /> </td> 
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
   <td> No admitido<br /> </td> 
   <td> No admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Prueba/Vista previa</strong><br /> </td> 
   <td> Admitido<br /> </td> 
   <td> Vista previa en AEM<br /> Prueba en Campaign<br /> </td> 
   <td> Vista previa y prueba en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Listas de productos</strong><br /> </td> 
   <td> Admitido en mensajes transaccionales de correo electrónico<br /> </td> 
   <td> No admitido<br /> </td> 
   <td> No admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Ventajas</strong><br /> </td> 
   <td> 
     <p>- Generación sencilla de correos electrónicos mediante la experiencia de arrastrar y soltar</p>
     <p>: Funciones similares al editor de contenido heredado</p>
     <p>- Contenido reutilizable con fragmentos</p>
  </td> 
   <td> 
     <p>- Reutilización de recursos del sitio web en correos electrónicos</p>
     <p>- Aprovechamiento del poder del Experience Manager en el contenido del correo electrónico</p>
    </td> 
   <td> 
    <p>: capacidad de un desarrollador para codificar directamente un correo electrónico</p>
    <p>- Sincronización bidireccional</p>
    <p>- Edición sin conexión en Dreamweaver y sincronización posterior</p>
    <p>- Carga de imágenes a Adobe Campaign mediante Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitaciones</strong><br /> </td> 
   <td> 
     <p>- Sin contenido condicional dentro de los fragmentos</p>
     <p>- No es posible utilizar fragmentos de Experience Manager</p>
  </td> 
   <td> 
     <p>: la personalización avanzada es difícil de implementar</p>
     <p>: necesidad de enviar pruebas en Adobe Campaign</p>
  </td> 
   <td> Contenido dinámico no admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Audiencia</strong><br /> </td> 
   <td> Los especialistas en marketing que deseen mantener la flexibilidad para utilizar componentes HTML en combinación con funciones de arrastrar y soltar<br /> </td> 
   <td> Los especialistas en marketing ya utilizan un Experience Manager que desea utilizar plantillas de correo electrónico estándar con poca personalización<br /> </td> 
   <td> Desarrolladores que desean codificar el contenido del correo electrónico e integrarse directamente con Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para obtener más información</strong><br /> </td> 
   <td> Consulte <a href="../../designing/using/designing-content-in-adobe-campaign.md">Acerca del Diseñador de correo electrónico</a>.<br /> </td> 
   <td> Consulte <a href="../../integrating/using/integrating-with-experience-manager.md">Integración con el Experience Manager</a>.<br /> </td> 
   <td> Consulte <a href="https://helpx.adobe.com/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver y Campaign</a> y vea este <a href="#video">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear y editar contenido para Adobe Campaign Standard mediante Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

Hay disponibles más vídeos prácticos del Campaign Standard [aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
