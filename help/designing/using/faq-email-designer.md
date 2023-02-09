---
title: Preguntas más frecuentes del Diseñador de correo electrónico
description: Preguntas más frecuentes sobre el Diseñador de correo electrónico.
audience: designing
content-type: reference
topic-tags: working-with-campaign-and-analytics
feature: Email Design
role: User
level: Intermediate
exl-id: f3208380-a4cf-4944-aa24-883995d1075d
source-git-commit: 13d419c5fc51845ee14f8a3b288f4c467e0a60d9
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---

# Preguntas más frecuentes del Diseñador de correo electrónico

## ¿Cuál es la diferencia entre bloques de contenido y fragmentos de contenido?

Los bloques de contenido y los fragmentos de contenido son fragmentos de contenido reutilizable que son comunes en varios correos electrónicos. Se utilizan para garantizar la coherencia entre los correos electrónicos y también para optimizar/estandarizar la creación de correos electrónicos. Las diferencias entre bloques de contenido y fragmentos de contenido son el nivel de personalización posible.

* Los bloques de contenido son HTML puros en los que el código de HTML se inserta manualmente (no es una interfaz de usuario fácil de usar, es un código fuente directo). Aunque está realmente orientado a personas con conocimiento HTML, permite un nivel de personalización que no está disponible en los fragmentos de contenido.

* Los fragmentos de contenido son fragmentos visuales de contenido creados mediante el Diseñador de correo electrónico, utilizando su IU de fácil uso. Sin embargo, no es posible personalizar el contenido. Si la personalización es necesaria, solo se puede realizar mediante bloques de contenido.

## ¿Cómo puedo añadir relleno a un elemento desde la estructura del HTML?

Puede agregar relleno utilizando la ruta de exploración del HTML.

1. En la parte inferior izquierda de la pantalla, haga clic en la ruta de exploración del HTML.

   ![](assets/do-not-localize/breadcrumb.png)

1. Haga clic en el elemento al que desee agregar un relleno.
1. Haga clic en la etiqueta principal en la ruta de exploración del HTML.
Ahora puede agregar un relleno a este elemento.

## ¿Se puede importar contenido de HTML en el Diseñador de correo electrónico?

Puede cargar su propio contenido de HTML en el Diseñador de correo electrónico. Si no se ha creado mediante el Diseñador de correo electrónico, se cargará en modo de compatibilidad diseñado para mantener el HTML original, pero limita ciertas funciones de edición a través de la interfaz de usuario.

Para obtener más información, consulte [Modo de compatibilidad](../../designing/using/using-existing-content.md#compatibility-mode)

## ¿Cómo creo mi primer contenido de correo electrónico?

En primer lugar, cree un correo electrónico desde la página principal.
A continuación, para añadir contenido a un correo electrónico, debe añadir un componente de estructura e insertar un componente de contenido en él.

Para obtener más información, consulte [Creación de un correo electrónico desde cero](../../designing/using/quick-start.md#from-scratch-email)

## ¿Por qué necesito actualizar los fragmentos?

El Diseñador de correo electrónico está en constante mejora. Si creó contenido de correo electrónico desde cero, a partir de una plantilla predeterminada o si creó fragmentos, es posible que tenga que actualizar el contenido a la última versión para evitar problemas como problemas de colisión con CSS.

Para obtener más información, consulte [Actualización de fragmentos](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

## ¿Puedo guardar un estilo en un tema?

Los estilos no se pueden guardar como un tema para su reutilización futura. Sin embargo, el estilo CSS se puede guardar en una plantilla de contenido o en un correo electrónico.

Para obtener más información, consulte [Estilos](../../designing/using/styles.md)

## ¿Qué fuentes están disponibles?

Al editar estilos, solo las fuentes web oficialmente admitidas por la mayoría de los clientes de correo electrónico están disponibles de forma predeterminada a través de la interfaz de usuario. El uso de fuentes personalizadas requiere actualizar el código del HTML.
