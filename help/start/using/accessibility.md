---
title: Accesibilidad en Adobe Campaign Standard
description: Obtenga información sobre la compatibilidad con la accesibilidad en el Espacio de trabajo de Adobe Campaign Standard.
audience: designing
content-type: reference
topic-tags: accessibility
feature: Campaigns
role: User
level: Intermediate
exl-id: 958f7beb-ab41-4492-bc0a-e9e342e3c12e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 100%

---

# Accesibilidad en Adobe Campaign Standard {#accessibility-acs}

Obtenga información sobre la compatibilidad con la accesibilidad en el Espacio de trabajo de Adobe Campaign Standard.

La accesibilidad se refiere a hacer que los productos sean utilizables para personas con discapacidades visuales, auditivas, cognitivas, motoras y de otro tipo. Algunos ejemplos de funciones de accesibilidad para productos de software son contenido semánticamente estructurado, compatibilidad con lectores de pantalla, equivalentes de texto para gráficos, métodos abreviados de teclado, etc.

Adobe Campaign Standard ofrece funciones que hacen que sea más accesible usar, como contraste, etiquetas, contenido estructurado, navegación mediante el teclado y ayuda contextual.

## Funciones de accesibilidad {#accessibility-features}

### Contraste y color {#contrast}

La interfaz de usuario de Adobe Campaign Standard se esfuerza por ofrecer suficiente contraste en la aplicación para garantizar una experiencia de visualización accesible para los usuarios con deficiencias bajas de visión o color.

* El texto y los encabezados grandes se han mejorado para alcanzar una relación de contraste de 3:1.

   ![](assets/accessibility_2.png)

* El contenido de la ayuda y el texto independiente de la aplicación se han actualizado para alcanzar una relación de contraste de 4.5:1.

* Los iconos de pausa y cancelación de los flujos de trabajo se han actualizado para mejorar el contraste entre los colores del fondo y el primer plano.

   ![](assets/accessibility_1.png)

* El color, la forma y la ubicación no son los únicos métodos utilizados para comunicar información o jerarquía en la aplicación.

### Interfaz de usuario {#user-interface}

La interfaz de usuario de Adobe Campaign Standard facilita la interacción de todos los usuarios con el contenido mediante la adición de textos alternativos a los elementos visuales y el uso de una estructura semántica para transmitir información tanto visual como programáticamente.

* Cuando el usuario deja en blanco un campo de ID requerido, un gráfico indica visualmente qué campo da error con un mensaje de error y esa información se transmite mediante programación a usuarios con tecnologías de asistencia como lectores de pantalla.

   ![](assets/accessibility_3.png)

* El contenido que aparece al pasar el ratón por encima o el enfoque puede ser descartado por el usuario para no oscurecer otro contenido.

   ![](assets/accessibility_4.png)

* Se han añadido textos alternativos para las imágenes y nombres accesibles para los botones, que pueden leerse en voz alta con tecnología de asistencia en lugar de mostrar únicamente indicaciones visuales para identificar los elementos.

<!--
### Create responsive resize for multiple devices {#resize-devices}

When designing for multiple devices and platforms, it's important to create a seamless experience for screen sizes across mobile and desktop resolutions.

Adobe Campaign Standard allows you to design and test emails and push notifications on different devices such as: iPhone, Android devices, iPad, Android tablet and desktop.

![](assets/accessibility_6.png)
-->

## Ayuda contextual {#contextual-help}

La ayuda contextual puede permitir comprender mejor los distintos campos y las funciones solicitadas disponibles. También le guiará a través de la documentación del producto para obtener más información sobre la función seleccionada.

Al diseñar un correo electrónico, puede acceder a una información de herramienta que proporciona descripciones sobre las funciones y vínculos a la documentación del producto.

![](assets/accessibility_7.png)

## Soporte para tecnología de asistencia {#screen-magnifiers}

Nos esforzamos por hacer que la aplicación Adobe Campaign Standard sea lo más sencilla de usar posible gracias a diversas tecnologías de asistencia, entre las que se incluyen, entre otras, teclados modificados, software de ampliación de pantalla, lectores, software de reconocimiento de voz y otros dispositivos de asistencia.

## Trabaje en su idioma preferido {#languages}

Adobe Campaign Standard está disponible en distintos idiomas: inglés, francés y alemán.

Tenga en cuenta que el idioma se configura durante la instalación y no se puede cambiar posteriormente.

## Métodos abreviados de teclado {#shortcuts}

### Página principal {#homepage-shortcuts}

| Método abreviado | Acción |
|:-:|:-:|
| Pestaña | Navegar por los elementos individuales de la interfaz de usuario |
| Intro o espacio | Activar el elemento seleccionado |

### Diseñador de correo electrónico {#email-designer-shortcuts}

| Método abreviado | Acción |
|:-:|:-:|
| CTRL + Z | Deshacer |
| CTRL + Y | Rehacer |

### Informes dinámicos {#report-shortcuts}

| Método abreviado | Acción |
|:-:|:-:|
| CTRL + O | Abrir proyecto |
| CTRL + S | Guardar |
| Shift + CTRL + S | Guardar como |
| Alt + R | Actualizar proyecto |
| Shift + CTRL + V | Descargar CSV |
| Alt + P | Imprimir |
| CTRL + Z | Deshacer |
| CTRL + Shift + Z | Rehacer |
| Alt + B | Nuevo panel en blanco |
| Alt + A | Nueva forma libre |
| Alt + 1 | Nueva tabla de forma libre |
| Alt + 2 | Nueva línea |
| Alt + 3 | Nueva barra |
| Alt + S | Enviar informe ahora |
| Shift + Alt + S | Enviar informe según lo programado |
| Shift = Alt + L | Informes programados |

## Lectura adicional {#further-reading}

Adobe Campaign Standard se esfuerza por proporcionar un grado de accesibilidad cada vez mayor, lo que facilita el uso del producto para todas las personas.

Le recomendamos que utilice el [Formulario de comentarios de accesibilidad de Adobe](https://www.adobe.com/accessibility/feedback.html) para enviarnos sugerencias de mejora y si encuentra problemas de accesibilidad.

También puede consultar las [Notas de la versión de Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=es#release-notes) para estar al tanto de las mejoras y características nuevas.
