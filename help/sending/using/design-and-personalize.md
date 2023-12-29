---
title: Creación de contenido personalizado
audience: delivery
content-type: reference
topic-tags: deliveries-best-practices
index: y
description: Aprenda a diseñar el contenido del mensaje e intente evitar problemas comunes que podrían impedir la ejecución del envío. 
feature: Deliverability
role: User
level: Intermediate
exl-id: 938989c9-ef19-4297-9b8b-c38eb1cec1f0
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1039'
ht-degree: 67%

---

# Creación de contenido personalizado {#build-personalized-content}

Al diseñar el contenido del mensaje, trate de evitar problemas comunes que podrían impedir la ejecución del envío. La mayoría de las veces, los posibles errores están relacionados con [personalización](../../designing/using/personalization.md), el formato al [uso de contenido existente](../../designing/using/using-existing-content.md) - y [conversión de contenido de un HTML](../../designing/using/using-existing-content.md#converting-an-html-content) - y [imágenes](../../designing/using/images.md).

## Optimización de la personalización {#optimize-personalization}

Para evitar problemas comunes que podrían impedirle ejecutar su envío y mejorar la experiencia de sus destinatarios, Adobe Campaign le permite personalizar sus mensajes.

Puede utilizar los datos de destinatarios almacenados en la base de datos de Adobe Campaign o recopilados mediante seguimiento, páginas de aterrizaje, suscripciones, etc.
Los conceptos básicos de la personalización se presentan en [esta sección](../../designing/using/personalization.md).

Asegúrese de que el contenido del mensaje esté diseñado correctamente para evitar errores, que generalmente están relacionados con la personalización.

El contenido dinámico se puede añadir manualmente para mostrar contenido diferente a los destinatarios según las condiciones definidas en el editor de expresiones. Al añadir contenido dinámico, siempre debe dejar una variante predeterminada para los destinatarios que no cumplan las condiciones seleccionadas.
Para obtener más información sobre el contenido dinámico, consulte [esta sección](../../designing/using/personalization.md#defining-dynamic-content-in-an-email).

**Sugerencias** : Previsualice el correo electrónico con diferentes perfiles de prueba para asegurarse de que el contenido dinámico se ha configurado correctamente.

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

El vínculo de cancelación de suscripción es esencial. Debe ser visible y válido, y el formulario debe ser funcional. Conozca las directrices de vínculos de baja [en esta sección](../../designing/using/personalization.md#about-targeting-dimension).

De forma predeterminada, cuando se analiza el mensaje, un control [reglas de tipología](../../sending/using/control-rules.md) comprueba si se ha incluido un vínculo de no participación y genera una advertencia si falta.

**Sugerencia**: Debido a que siempre es posible cometer un error humano, compruebe que el vínculo de no participación funciona correctamente antes de cada envío. Por ejemplo, al enviar la prueba, asegúrese de que el enlace es válido, que el formulario en línea está activo y que el campo No volver a enviar a destinatario cambia a Sí.

Obtenga información sobre cómo insertar un vínculo de no participación [en esta sección](../../designing/using/personalization.md#adding-a-content-block).

### Tamaño del correo electrónico {#email-size}

Para evitar problemas de rendimiento o de envío, el tamaño máximo recomendado de un correo electrónico es de **35 KB**.

Para mantener el correo electrónico por debajo del límite, haga lo siguiente:

* Eliminar estilos redundantes o que no utilice

* Mover parte del contenido del correo electrónico a una [página de aterrizaje](../../channels/using/getting-started-with-landing-pages.md)

* Minimizar el código

Asegúrese de probar los cambios antes del envío final.

En Adobe Campaign, el tamaño máximo predeterminado de un correo electrónico se establece en **100 MB**. <!--This limit enables to prevent any error that could indefinitely increase the size of an email, which can lead to a system crash.-->

Si se alcanza el límite, el mensaje que lo supera fallará y se mostrará un mensaje de error en los registros de envío. Los demás mensajes del mismo envío no se ven afectados. En ese caso, debe adaptar la parte dinámica de la plantilla de correo electrónico o los fragmentos de contenido utilizados por la entrega. <!--If you need assistance, or if you have any question or request about the **[!UICONTROL Maximum message size]** option, reach out to your Adobe contact.-->

El Adobe recomienda mantener el valor predeterminado de tamaño máximo del mensaje. Sin embargo, este valor se puede cambiar en la variable **[!UICONTROL Maximum message size]** mediante la opción **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menú, por [administradores funcionales](../../administration/using/users-management.md#functional-administrators) solo.

>[!IMPORTANT]
>
>Si establece este valor en cero, no se aplicará ningún límite.

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

* Utilice el modo de vista previa y envíe pruebas para probar el procesamiento en tantos dispositivos como sea posible. Obtenga información sobre cómo [mensaje de previsualización](../../sending/using/previewing-messages.md) antes de enviar.

* El Diseñador de correo electrónico de Campaign incluye plantillas con formato de diseño interactivo para dispositivos móviles. Obtenga más información [en esta página](../../designing/using/using-reusable-content.md#content-templates).

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

## Previsualice el mensaje {#preview-msg}

Adobe recomienda previsualizar el mensaje para comprobar su personalización y cómo verán los destinatarios su entrega.

En el Diseñador de correo electrónico, la variable **[!UICONTROL Preview]** Este botón permite ver la renderización de cada contenido para un destinatario. Los campos personalizados y los elementos condicionales del contenido se sustituyen por la información correspondiente del perfil seleccionado. [Más información](../../sending/using/previewing-messages.md)
