---
title: Notas de la versión anteriores
description: Notas de la versión anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 7767b39a48502f97e2b3af9d21a3f49b9283ab2e
workflow-type: ht
source-wordcount: '468'
ht-degree: 100%

---

# Notas de la versión anteriores {#new-release}

Esta página describe las nuevas funciones, mejoras y correcciones incluidas en la próxima versión de Campaign Standard.

>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Obtenga más información en la [página de planificación de versiones](../../rn/using/release-planning.md).

## Versión 22.2 de junio de 2022 {#rn-2022}

**Mejoras**

* **Servicio de notificación de Adobe**: Campaign viene con el servicio de notificación de Adobe que permite a las soluciones de Experience Cloud alertar a los usuarios entre Experience Cloud sobre las actividades que son importantes que conozcan. A partir de la versión 22.2, la experiencia del usuario se ha mejorado: las notificaciones se priorizan y las notificaciones generadas por el producto se separan de los anuncios de estado del Adobe. Además, cuando la notificación hace referencia a un flujo de trabajo específico, ahora puede acceder al flujo de trabajo correspondiente directamente desde el correo electrónico o la notificación interna del producto.  Para obtener más información sobre las notificaciones de Adobe Campaign, consulte [Notificaciones de Adobe Campaign](../../administration/using/sending-internal-notifications.md).

* **Optimización en el inicio del flujo de trabajo**: Adobe ha añadido una nueva funcionalidad que puede ajustar el número de flujos de trabajo que se inician aproximadamente al mismo tiempo. Esto ayudaría a evitar picos de CPU que podrían haber llevado a interrupciones del servicio o downtime. Adobe lo habilitaría después de la versión 22.2. No hay ningún elemento de acción adicional en el cliente con respecto al mismo.

* **Accesibilidad**: Adobe ha realizado muchas correcciones de accesibilidad para mejorar la facilidad de uso general de la aplicación. Actualmente, estas funciones solo están habilitadas para un conjunto de usuarios que las adoptaron por primera vez, y se implementarán para todos los clientes en la versión ACS 2.3. Algunos ejemplos de mejoras de accesibilidad son los siguientes:

   * Garantizar que haya un indicador de enfoque visible para los elementos enfocables en cada pantalla
   * Creación de puntos de referencia de página para facilitar la navegación
   * Adición del nombre, la función, el valor y el estado para muchos controles
   * Corrección de problemas con el orden de enfoque dinámico en las pantallas principales

**Actualización de seguridad**

* Apache Tomcat se ha actualizado de la versión 7 a la versión 8.5.


**Parches**

* Se ha corregido un problema en el flujo de trabajo técnico Facturación debido a un error de clave duplicada. (CAMP-51029)
* Se ha añadido la categoría del explorador Microsoft Edge que falta en Seguimiento de informes. Anteriormente, se clasificaban con las aperturas de Microsoft Chrome. (CAMP-51165)
* Se ha corregido un problema con las solicitudes de RGPD que no eliminaban datos de tablas secundarias. (CAMP-48276)
* Se ha corregido un problema en el Diseñador de correo electrónico que provocaba que la condición de visibilidad de un fragmento no se guardara en una plantilla de mensaje transaccional. (CAMP-50338)
* Se ha corregido un problema en los informes de campaña que provocaba que no se tuviera en cuenta el intervalo de fechas. (CAMP-50991)
* Se ha corregido un error que provocaba que fallaran los correos electrónicos programados: el análisis de entrega no se pudo iniciar porque la entrega seguía en estado &quot;Reintento pendiente&quot;. (CAMP-50302)
* Se ha corregido un problema en el Diseñador de correo electrónico al previsualizar un correo electrónico con una sustitución de perfiles. (CAMP-49312)
* Se ha corregido un problema con un valor vacío en las enumeraciones personalizadas: al crear un recurso personalizado con un campo que es una enumeración de texto y contiene solo un valor, este valor se establece ahora de forma predeterminada, de modo que puede crear una consulta en este campo como una solicitud simple. (CAMP-50606)
