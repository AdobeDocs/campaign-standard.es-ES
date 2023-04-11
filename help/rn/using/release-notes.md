---
title: Última versión
description: Esta página detalla el contenido de la última versión de Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: e1f55a9b-be51-4f57-8719-fed7efc89113
source-git-commit: f9bd5901d68c09ba20d5d48d263f4818c2e1e86a
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 16%

---


# Última versión{#latest-release}

![Panel de control](assets/do-not-localize/cp-icon.png) **Nueva versión de Panel de control**. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/release-notes.html?lang=es){target="_blank"}.

## Versión 23.1: versión de primavera/verano de 2023 {#apr-23}

### Mejoras {#e-rn-improvements}

* El servicio de mensajería push se ha modernizado para mejorar la compatibilidad. (CAMP-47959)
* El servicio de mensajería SMS se ha mejorado para proporcionar una mejor estabilidad. (CAMP-52217)
* Adobe ha realizado muchas correcciones de accesibilidad para mejorar la facilidad de uso general de la aplicación. Estos son algunos ejemplos de mejoras de accesibilidad:
   * La accesibilidad del teclado de la interfaz se ha optimizado en muchas pantallas.
   * La aplicación se ha mejorado para usuarios de pantalla táctil.
   * Se ha cambiado el color de varios elementos en la interfaz para mejorar la visibilidad.

### Otros cambios {#e-rn-changes}

* La solución predeterminada **Flujo de trabajo de creación de enriquecimiento de informes** se ha añadido. Después de importar una asignación de destino de una instancia a otra, simplemente ejecute el flujo de trabajo para importar las entradas de enriquecimiento de informes correspondientes. (CAMP-52452)

### Problemas solucionados{#e-rn-patches}

* Se ha corregido un problema que podría provocar un error de tiempo de espera al mostrar la variable **Clic en caliente** informe. (CAMP-51582)
* Se ha corregido un problema que podía impedir que usara la integración con la variable **Lugares** servicio. (CAMP-51923)
* Se ha corregido un problema que podía impedir que el programador de flujos de trabajo funcionara correctamente. (CAMP-52003)
* Se ha corregido un problema que impedía que se mostraran los detalles del desglose al ver la versión del PDF de un informe dinámico personalizado con un gran volumen de datos. (CAMP-52178)
* Se ha corregido un problema que podía mostrar un error al acceder a los informes. (CAMP-52500)
* Se ha corregido un problema que aplicaba incorrectamente la variable **Limitar instancias de MTA para esta cuenta** Parámetro de conector SMS a todos los canales en lugar de aplicar solo a SMS. (CAMP-52640)
