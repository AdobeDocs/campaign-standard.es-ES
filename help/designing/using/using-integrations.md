---
title: Diseño de correos electrónicos mediante integraciones de Adobe Campaign
description: Descubra cómo diseñar correos electrónicos mediante integraciones de Adobe Campaign en el Designer de correo electrónico.
audience: designing
content-type: reference
topic-tags: editing-email-content
feature: Email Design
role: User
level: Intermediate
exl-id: d5c72f69-68a2-4523-956f-f265ae79b470
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '706'
ht-degree: 5%

---

# Diseño de correo electrónico con varias soluciones {#multi-solution-email-design}

Adobe Campaign ofrece varias opciones de creación de correo electrónico. Puede utilizar soluciones como Dreamweaver para editar el contenido del correo electrónico y crear mensajes adaptables en el Designer de correo electrónico. También puede enviar contenido por correo electrónico con Adobe Experience Manager y utilizarlo en sus correos electrónicos en Adobe Campaign Standard.

## Edición de contenido en Dreamweaver {#editing-content-in-dreamweaver}

La integración de Adobe Campaign Standard con Dreamweaver permite editar el contenido de un correo electrónico en la interfaz de Dreamweaver. Tiene acceso a la potente interfaz de Dreamweaver para diseñar y desarrollar contenido de correo electrónico adaptable.

* **Sincronización bidireccional**

  Cada vez que se realiza una edición en un producto, se actualiza en tiempo real en el otro. Si desea cambiar el color del texto en Dreamweaver, tan pronto como realice esa edición, el color del texto estará activo en Campaign. Además, cuando se selecciona código en Dreamweaver o Campaign, ya que los números de línea son los mismos, la selección permanece entre los dos productos, lo que resulta muy útil cuando se busca algo específico en el código.

* **Cargar imágenes locales en Adobe Campaign a través de Dreamweaver**

  Al crear o editar un correo electrónico en Dreamweaver, simplemente puede seleccionar una imagen del escritorio o del equipo local. Aunque Dreamweaver siempre le ha permitido hacer esto, cuando Dreamweaver y Campaign están conectados, el archivo local se carga inmediatamente en el servidor de Adobe Campaign: no es necesario cargar manualmente las imágenes a medida que cambia el contenido. Además, garantiza que las imágenes más recientes estén siempre activas en Campaign.

* **Agregar personalización de campaña en Dreamweaver**

  Para el desarrollador de correo electrónico, ya no es necesario agregar texto como `[[FIRSTNAME_PLACEHOLDER]]` ni buscar la sintaxis de las tablas del modelo de datos. La barra de herramientas de Campaign en Dreamweaver se conecta directamente al modelo de datos de la instancia de Campaign. Esto significa que puede extraer cualquier dato que desee para su personalización de un nombre a una dirección. Si ha creado bloques de contenido dentro de Campaign, también puede extraerlos directamente en Dreamweaver.

Esta funcionalidad se detalla en la Documentación de Dreamweaver [accesible aquí](https://helpx.adobe.com/es/dreamweaver/using/working-with-dreamweaver-and-campaign.html).

![](assets/do-not-localize/how-to-video.png) [Descubra esta funcionalidad en vídeo](#video)

## Edición de contenido en Experience Manager {#editing-content-in-experience-manager}

El contenido del correo electrónico se puede editar en Experience Manager y, a continuación, utilizar para uno o varios mensajes de correo electrónico en Adobe Campaign Standard. Consulte [este documento](../../integrating/using/integrating-with-experience-manager.md).

## Listados de productos {#product-listing}

>[!CONTEXTUALHELP]
>id="ac_product_listing"
>title="Uso de listados de productos"
>abstract="Las listas de productos permiten hacer referencia a una recopilación de datos y mostrarla en el contenido del correo electrónico."

Las listas de productos le permiten hacer referencia a una o más colecciones de datos en el contenido del correo electrónico. Estos anuncios están disponibles para correos electrónicos transaccionales. Hay disponible [aquí](../../designing/using/using-product-listings.md) una sección dedicada a esta característica.

## Comparación de opciones de diseño de correo electrónico {#email-design-options-comparison}

Adobe Campaign ofrece varias opciones de creación de correo electrónico. En el cuadro que figura a continuación se muestran las principales posibilidades, ventajas y limitaciones de cada una de ellas.

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
   <td> Compatible<br /> </td> 
   <td> Compatible<br /> </td> 
   <td> Compatible<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTML de escritura</strong><br /> </td> 
   <td> Compatible<br /> </td> 
   <td> No admitido<br /> </td> 
   <td> Compatible<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>HTML de la actualización</strong><br /> </td> 
   <td> Solamente dentro de un componente de HTML <br /> </td> 
   <td> No admitido<br /> </td> 
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
   <td> No admitido<br /> </td> 
   <td> No admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Revisión/Previsualización</strong><br /> </td> 
   <td> Compatible<br /> </td> 
   <td> AEM Vista previa en la revisión <br /> de la prueba en la campaña <br /> </td> 
   <td> Vista previa y revisión en Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>listados de productos</strong><br /> </td> 
   <td> Compatible con mensajes transaccionales de correo electrónico <br /> </td> 
   <td> No admitido<br /> </td> 
   <td> No admitido<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Beneficios</strong><br /> </td> 
   <td> 
     <p>- Generación sencilla de correo electrónico mediante la experiencia de arrastrar y soltar</p>
     <p>: Funcionalidades similares al editor de contenido heredado</p>
     <p>- Contenido reutilizable con fragmentos</p>
  </td> 
   <td> 
     <p>- Reutilización de recursos del sitio web en correos electrónicos</p>
     <p>: Aprovechamiento del poder del Experience Manager en el contenido del correo electrónico</p>
    </td> 
   <td> 
    <p>: Capacidad para que un desarrollador codifique directamente un correo electrónico</p>
    <p>- Sincronización bidireccional</p>
    <p>: Edición sin conexión en Dreamweaver y sincronización posterior</p>
    <p>: Carga de imágenes en Adobe Campaign a través de Dreamweaver</p>
  </td> 
  </tr> 
  <tr> 
   <td> <strong>Limitaciones</strong><br /> </td> 
   <td> 
     <p>- Sin contenido condicional dentro de los fragmentos</p>
     <p>- No es posible utilizar fragmentos de Experience Manager</p>
  </td> 
   <td> 
     <p>: Personalización avanzada difícil de implementar</p>
     <p>- Necesita enviar pruebas en Adobe Campaign</p>
  </td> 
   <td> No se admite contenido dinámico<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Audiencia</strong><br /> </td> 
   <td> Los especialistas en marketing que deseen mantener la flexibilidad para utilizar componentes de HTML en combinación con las características de arrastrar y soltar<br /> </td> 
   <td> Los especialistas en marketing ya están usando un Experience Manager que desea usar plantillas de correo electrónico estándar con poca personalización<br /> </td> 
   <td> Desarrolladores que deseen codificar el contenido del correo electrónico e integrarlo directamente con Adobe Campaign<br /> </td> 
  </tr> 
  <tr> 
   <td> <strong>Para obtener más información</strong><br /> </td> 
   <td> Ver <a href="../../designing/using/designing-content-in-adobe-campaign.md">Acerca del correo electrónico Designer</a>.<br /> </td> 
   <td> Ver <a href="../../integrating/using/integrating-with-experience-manager.md">Integración con el Experience Manager</a>.<br /> </td> 
   <td> Ver <a href="https://helpx.adobe.com/es/dreamweaver/using/working-with-dreamweaver-and-campaign.html">Dreamweaver y Campaign</a> y ver este <a href="#video">vídeo</a>.<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Tutorial en vídeo {#video}

Este vídeo muestra cómo crear y editar contenido para Adobe Campaign Standard mediante Dreamweaver.

>[!VIDEO](https://video.tv.adobe.com/v/23121?quality=12&captions=eng)

Hay disponibles [más vídeos de procedimientos para el Campaign Standard aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
