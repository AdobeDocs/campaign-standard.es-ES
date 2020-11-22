---
solution: Campaign Standard
product: campaign
title: Creación de contenido personalizado
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
translation-type: tm+mt
source-git-commit: a7300666587362048431d0bafacc317170b317aa
workflow-type: tm+mt
source-wordcount: '905'
ht-degree: 81%

---


# Creación de contenido personalizado {#build-personalized-content}

Al diseñar el contenido del mensaje, trate de evitar problemas comunes que podrían impedir la ejecución del envío. La mayoría de las veces, los posibles errores están relacionados con la [personalización](../../designing/using/personalization.md), el formato al [utilizar un contenido](../../designing/using/using-existing-content.md) existente (y la [conversión de un contenido](../../designing/using/using-existing-content.md#converting-an-html-content) HTML) y [las imágenes](../../designing/using/images.md).

## Optimización de la personalización {#optimize-personalization}

Para evitar problemas comunes que podrían impedirle ejecutar su envío y mejorar la experiencia de sus destinatarios, Adobe Campaign le permite personalizar sus mensajes.

Puede utilizar los datos de destinatarios almacenados en la base de datos de Adobe Campaign o recopilados mediante seguimiento, páginas de aterrizaje, suscripciones, etc.
Los conceptos básicos de la personalización se presentan en [esta sección](../../designing/using/personalization.md).

Asegúrese de que el contenido del mensaje esté diseñado correctamente para evitar errores, que generalmente están relacionados con la personalización.

El contenido dinámico se puede agregar manualmente para mostrar diferentes contenidos a los destinatarios según las condiciones definidas en el editor de expresiones. Al agregar contenido dinámico, siempre debe dejar una variante predeterminada para los destinatarios que no cumplan las condiciones seleccionadas.
For more on dynamic content, refer to the [this section](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Sugerencias** : Previsualización el correo electrónico con diferentes perfiles de prueba para asegurarse de que el contenido dinámico se ha configurado correctamente.

## Creación de contenido optimizado {#optimize-content}

Cuando cree sus correos electrónicos, tenga en cuenta las optimizaciones generales que se describen a continuación.

* El correo electrónico debe tener un diseño sencillo

* Tenga en cuenta a los usuarios de dispositivos móviles

* Evite los correos electrónicos basados por completo en imágenes

* Utilice fuentes seguras para el correo electrónico

* Codifique caracteres especiales

### Línea de asunto

Cree una [línea de asunto ](../../designing/using/subject-line.md) para mejorar las tasas de apertura:

* Evite los asuntos demasiado largos. Utilice un máximo de 50 caracteres

* Evite utilizar palabras de forma repetida, tales como “gratis” u “oferta”, que podrían considerarse como spam

* Evite mayúsculas y caracteres especiales como &quot;!&quot;, &quot;£&quot;, &quot;€&quot; y &quot;$&quot;

### Página espejo

Incluya siempre un vínculo de página espejo. La posición preferida es la parte superior del correo electrónico. [Más información](../../designing/using/personalization.md#adding-a-content-block)

### Vínculo de cancelación de suscripción

El vínculo de cancelación de suscripción es esencial. Debe ser visible y válido, y el formulario debe ser funcional. Obtenga información sobre las directrices bajas [en esta sección](../../designing/using/personalization.md#about-targeting-dimension).

By default, when the message is analyzed, a control [typology rule](../../sending/using/control-rules.md) checks whether an opt-out link has been included and generates a warning if it is missing.

**Sugerencia**: Debido a que siempre es posible cometer un error humano, compruebe que el vínculo de no participación funciona correctamente antes de cada envío. Por ejemplo, al enviar la prueba, asegúrese de que el enlace es válido, que el formulario en línea está activo y que el campo No volver a enviar a destinatario cambia a Sí.

Obtenga información sobre cómo insertar un vínculo de no participación [en esta sección](../../designing/using/personalization.md#adding-a-content-block).

### Tamaño del correo electrónico

Para evitar problemas de rendimiento o de entrega, el tamaño máximo recomendado de un correo electrónico es de unos **35 KB**.

Para mantener el correo electrónico por debajo del límite, haga lo siguiente:

* Eliminar estilos redundantes o que no utilice

* Mover parte del contenido del correo electrónico a una página de aterrizaje

* Minimizar el código

Asegúrese de probar los cambios antes del envío final

### Longitud del SMS

De forma predeterminada, el número de caracteres de un SMS cumple con los estándares del GSM (Sistema Global de Comunicaciones Móviles). Los mensajes SMS con codificación GSM están limitados a 160 caracteres, o a 153 caracteres por SMS en el caso de los mensajes enviados en varias partes.

La transliteración consiste en reemplazar un carácter de un SMS por otro cuando el estándar GSM no tiene en cuenta dicho carácter. Tenga en cuenta que la inserción de campos de personalización en el contenido del mensaje SMS puede introducir caracteres que no se tienen en cuenta con la codificación GSM. Puede autorizar la transliteración de caracteres marcando la casilla correspondiente en la pestaña de la configuración del canal de SMPP de la **[!UICONTROL External account]** correspondiente.
Obtenga más información [en esta sección](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

**Sugerencias**:

* Para mantener todos los caracteres en sus mensajes SMS tal como están, para no alterar nombres adecuados por ejemplo, no habilites la transliteración.

* Sin embargo, si sus mensajes SMS contienen muchos caracteres que no se tienen en cuenta en el estándar GSM, habilite la transliteración para limitar los costes de envío de mensajes.

Obtenga más información [en esta sección](../../administration/using/configuring-sms-channel.md#sms-encoding--length-and-transliteration).

### Diseño de correo electrónico interactivo

El diseño interactivo garantiza que un correo electrónico se represente de forma óptima en el dispositivo en el que se abre.

* Utilice HTML de correo electrónico interactivo en lugar de HTML web

* Utilice el modo de vista previa y envíe pruebas para probar el diseño en tantos dispositivos como sea posible. Obtenga información sobre cómo [previsualización de mensajes](../../sending/using/previewing-messages.md) antes de enviarlos.

* Campaña Email Designer incluye plantillas con formato de diseño interactivo para dispositivos móviles. Learn more [in this page](../../designing/using/using-reusable-content.md#content-templates).

## Administración de imágenes {#manage-images}

Siga las directrices que se indican a continuación cuando tenga que administrar imágenes.

### Prevención del bloqueo de imágenes

Algunos clientes de correo electrónico bloquean las imágenes de forma predeterminada y algunos usuarios cambian su configuración para bloquearlas y optimizar el consumo de datos. Por lo tanto, si las imágenes no se descargan, se puede perder todo el mensaje. Para evitarlo:

* Equilibre el contenido con la imagen y el texto. Evite los correos electrónicos basados por completo en imágenes.

* Si se debe incluir texto en una imagen, use texto alternativo y de título para que el mensaje tenga el efecto deseado. Establezca el formato de texto alternativo o de título para mejorar el aspecto del diseño.

* Evite el uso de imágenes de fondo, ya que algunos servicios de correo electrónico no las admiten.

### Conversión de imágenes en interactivas

Intente que las imágenes sean interactivas y se puedan cambiar de tamaño. Tenga en cuenta que esto puede tener un impacto en los costes, ya que se tarda más en crear.

### Use referencias de imagen absoluta

Para que sean accesibles desde el exterior, las imágenes utilizadas en los mensajes de correo electrónico y recursos públicos vinculados a las campañas deben estar presentes en un servidor accesible de forma externa.

## Previsualice el mensaje   {#preview-msg}

Adobe recomienda previsualizar el mensaje para comprobar su personalización y cómo verán su envío sus destinatarios.

In the Email designer, the **[!UICONTROL Preview]** button lets you view the rendering of each content for a recipient. Los campos personalizados y los elementos condicionales del contenido se sustituyen por la información correspondiente del perfil seleccionado. [Más información](../../sending/using/previewing-messages.md)
