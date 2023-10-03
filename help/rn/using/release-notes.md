---
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: c1271bc0128c583e9b39ef98a422487e1df20fce
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 59%

---


# Última versión{#latest-release}

![Panel de control](assets/do-not-localize/cp-icon.png) **Nueva versión de Panel de control**. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es){target="_blank"}.



## Versión 23.2: versión de otoño/invierno de 2023 {#fall-23}

>[!AVAILABILITY]
>
>Esta versión solo está disponible para un conjunto de organizaciones (disponibilidad limitada). Para obtener más información, póngase en contacto con el representante del Adobe.

### Mejoras {#fall-23-rn-improvements}

* **Integración con Adobe Experience Manager**. Al crear una plantilla de envío personalizada para mensajes transaccionales en Adobe Experience Manager, ahora puede seleccionar y utilizar los campos de personalización definidos en Campaign Standard en una lista desplegable. [Más información](../../integrating/using/creating-email-experience-manager.md)

* **Caducidad de cookie** : La caducidad predeterminada de las cookies ahora es de 6 meses, para ajustarse a las recomendaciones de la Agencia Francesa de Protección de Datos (CNIL).

* **Mejora de búsqueda de perfiles** - La búsqueda de perfiles se ha optimizado para reducir los escenarios de tiempo de espera de búsqueda

* **Localización** - Las traducciones del término &quot;audiencia&quot; al referirse a un grupo de perfiles destinados a recibir un mensaje se armonizaron en todos los productos de Digital Experience para los siguientes idiomas:

   * Alemán: Zielgruppe
   * Portugués brasileño: público-alvo
   * Español: público destinatario

  Estos cambios se implementarán gradualmente con las siguientes versiones de la interfaz de usuario y la documentación.


### Otros cambios {#fall-23-rn-other-changes}

* La mensajería transaccional ahora admite el uso de varias afinidades separadas por comas.

### Correcciones {#fall-23-rn-fixes}

* Se ha corregido una regresión que podría provocar problemas de rendimiento al utilizar flujos de trabajo grandes. (CAMP-53369)
* Se ha corregido un problema que impedía que funcionara el vínculo de correo electrónico en una alerta o notificación de flujo de trabajo. (CAMP-51874)

## Versión 23.1: versión de primavera/verano de 2023 {#apr-23}

### Mejoras {#e-rn-improvements}

* El servicio de mensajería push se ha modernizado para optimizar la asistencia. (CAMP-47959)
* El servicio de mensajería SMS se ha modernizado para proporcionar una mayor estabilidad. (CAMP-52217)
* Adobe ha realizado muchas correcciones de accesibilidad para mejorar la facilidad de uso general de la aplicación. Estos son algunos ejemplos de mejoras de accesibilidad:
   * La accesibilidad del teclado de la interfaz se ha optimizado en muchas pantallas.
   * La aplicación se ha mejorado para usuarios de pantalla táctil.
   * Se ha cambiado el color de varios elementos en la interfaz para mejorar la visibilidad.

### Otros cambios {#e-rn-changes}

* Se ha añadido la solución predeterminada **Flujo de trabajo de creación de informes de enriquecimiento**. Después de importar una asignación de destinatario de una instancia a otra, simplemente ejecute el flujo de trabajo para importar las entradas de enriquecimiento de creación de informes correspondientes. (CAMP-52452)

### Problemas solucionados{#e-rn-patches}

* Se ha corregido un problema que podría provocar un error de tiempo de espera al mostrar el informe **Clic activo**. (CAMP-51582)
* Se ha corregido un problema que podía impedir que usara la integración con el servicio **Lugares**. (CAMP-51923)
* Se ha corregido un problema que podía impedir que el planificador de flujos de trabajo funcionara correctamente. (CAMP-52003)
* Se ha corregido un problema que impedía que se mostraran los detalles del desglose al ver la versión PDF de un informe dinámico personalizado con un gran volumen de datos. (CAMP-52178)
* Se ha corregido un problema que podía mostrar un error al acceder a los informes. (CAMP-52500)
* Se ha corregido un problema que aplicaba incorrectamente el parámetro de conector SMS **Limitar instancias de MTA para esta cuenta** a todos los canales, en lugar de solo a SMS. (CAMP-52640)
