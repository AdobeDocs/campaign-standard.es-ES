---
title: Notas de las versiones anteriores
description: Notas de las versiones anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 485927b217fb68064897dd877c2f4a6dd208d443
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Notas de las versiones anteriores {#e-new-release}

Esta página describe las mejoras y correcciones incluidas en la próxima versión de Campaign Standard.
>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Obtenga más información en la [página de planificación de versiones](../../rn/using/release-planning.md).

## Versión 23.1: versión de primavera/verano de 2023 {#apr-23}

### Mejoras {#e-rn-improvements}

* El servicio de mensajería push se ha modernizado para mejorar la compatibilidad. (CAMP-47959)
* El servicio de mensajería SMS se ha mejorado para proporcionar una mejor estabilidad. (CAMP-52217)
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
