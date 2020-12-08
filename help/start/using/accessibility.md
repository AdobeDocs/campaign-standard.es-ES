---
solution: Campaign Standard
product: campaign
title: Accesibilidad en Adobe Campaign Standard
description: Obtenga información sobre la compatibilidad con la accesibilidad en Adobe Campaign Standard Workspace.
audience: designing
content-type: reference
topic-tags: accessibility
translation-type: tm+mt
source-git-commit: 6632216ce4697892ea08b32641c9c026482ca713
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 0%

---


# Accesibilidad en Adobe Campaign Standard {#accessibility-acs}

Obtenga información sobre la compatibilidad con la accesibilidad en Adobe Campaign Standard Workspace.

La accesibilidad se refiere a hacer que los productos sean utilizables para personas con discapacidades visuales, auditivas, cognitivas, motoras y de otro tipo. Algunos ejemplos de funciones de accesibilidad para productos de software son la compatibilidad con lectores de pantalla, equivalentes de texto para gráficos, métodos abreviados de teclado, cambio de colores de visualización a alto contraste, etc.

Adobe Campaign Standard proporciona algunas herramientas que hacen que sea accesible para su uso, como contraste, navegación mediante el teclado, ayuda contextual y cambio de tamaño interactivo.

## Funciones de accesibilidad {#accessibility-features}

### Contraste {#contrast}

La interfaz de usuario de Adobe Campaign Standard se esfuerza por ofrecer suficiente contraste en la aplicación para garantizar una experiencia de visualización accesible para los usuarios con deficiencias de visión o color bajas.

* Los iconos de pausa y cancelación de flujos de trabajo se han actualizado para mejorar el contraste entre el fondo y el primer plano.

   ![](assets/accessibility_1.png)

* El texto mostrado cuando un envío se realiza correctamente contenía texto verde grande con un contraste insuficiente entre el fondo y el primer plano. El contraste se ha actualizado con una relación mínima de 3:1.

   ![](assets/accessibility_2.png)

* Adobe Campaign Standard garantiza que el color, la forma o la ubicación no sean los únicos métodos utilizados para comunicar información o jerarquía.

### Interfaz de usuario {#user-interface}

La interfaz de usuario de Adobe Campaign Standard facilita a los usuarios la visualización y la escucha de contenido, incluida la separación del primer plano del fondo y la adición de textos alternativos a los distintos botones disponibles.

* Cuando el usuario deja en blanco un campo de ID requerido, un gráfico indica visualmente qué campo está en error con un texto de mensaje de error.

   ![](assets/accessibility_3.png)

* El contenido que aparece al pasar el ratón por encima o el enfoque puede ser descartado por el usuario y no oscurece otro contenido.

   ![](assets/accessibility_4.png)

* Se han añadido textos alternativos para botones de imagen que se pueden leer en lugar de ver una ilustración.

   ![](assets/accessibility_5.png)

* Las celdas de encabezados de tabla de datos no se dejan vacías en la esquina de la tabla al utilizar listas.

### Crear redimensionamiento interactivo para varios dispositivos {#resize-devices}

Al diseñar para varios dispositivos y plataformas, es importante crear una experiencia perfecta para tamaños de pantalla en resoluciones móviles y de escritorio.

Adobe Campaign Standard le permite diseñar y probar correos electrónicos y notificaciones push en diferentes dispositivos, como: iPhone, dispositivos Android, iPad, tablet Android y escritorio.

![](assets/accessibility_6.png)

## Ayuda contextual {#contextual-help}

La ayuda contextual puede ayudarle a comprender mejor los distintos campos y características solicitados disponibles. También le guiará a través de la documentación del producto para obtener más información sobre la función seleccionada.

Al diseñar un correo electrónico, puede situar el cursor sobre el botón de información. Aparecerá una información sobre herramientas que proporciona descripciones de funciones y vínculos a la documentación del producto.

![](assets/accessibility_7.png)

## Compatibilidad con ampliadores de pantalla {#screen-magnifiers}

Un lector de pantalla lee el texto que aparece en la pantalla del equipo. También lee información no textual, como etiquetas de botones o descripciones de imágenes en la aplicación, proporcionada en etiquetas o atributos de accesibilidad.

En Adobe Campaign Standard, el contenido y la funcionalidad siguen estando disponibles aunque el usuario anule las propiedades de espaciado de texto.

## Trabaje en su idioma preferido {#languages}

Adobe Campaign Standard está disponible en distintos idiomas: inglés, francés y alemán.

Tenga en cuenta que el idioma se configura en la instalación y no se puede cambiar posteriormente.

## Métodos abreviados de teclado {#shortcuts}

### Página principal {#homepage-shortcuts}

| Método abreviado | Acción |
|:-:|:-:|
| Ficha | Navegar por los elementos individuales de la interfaz de usuario |
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
| Mayús + CTRL + S | Guardar como |
| Alt + R | Actualizar proyecto |
| Mayús + CTRL + V | Descargar CSV |
| Alt + P | Imprimir |
| CTRL + Z | Deshacer |
| CTRL + Mayús + Z | Rehacer |
| Alt + B | Nuevo panel en blanco |
| Alt + A | Nueva forma libre |
| Alt + 1 | Nueva tabla improvisada |
| Alt + 2 | Nueva línea |
| Alt + 3 | Nueva barra |
| Alt + S | Enviar informe ahora |
| Mayús + Alt + S | Enviar informe según lo programado |
| Mayús = Alt + L | Informes programados |

## Lectura adicional {#further-reading}

Adobe Campaign Standard se esfuerza por proporcionar un grado de accesibilidad cada vez mayor, lo que facilita el uso del producto para todos.

Le recomendamos que utilice el [Formulario de comentarios de accesibilidad de Adobe](https://www.adobe.com/accessibility/feedback.html) para enviarnos sugerencias de mejora y problemas de accesibilidad en los que se encuentre.

También puede consultar [notas de la versión de Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/release-notes/release-notes.html?lang=en#release-notes) para seguir las últimas mejoras y características.