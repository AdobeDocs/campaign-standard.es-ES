---
title: Notas de las versiones anteriores
description: Notas de las versiones anteriores
feature: Overview
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: 25e842d2b012a07b3f1ef1ff5490a6b4afa0e887
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 27%

---


# Notas de las versiones anteriores {#e-new-release}

Esta página describe las mejoras y correcciones incluidas en la próxima versión de Campaign Standard.
>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Obtenga más información en la [página de planificación de versiones](../../rn/using/release-planning.md).

## Versión 23.1: versión de primavera/verano de 2023 {#apr-23}

### Mejoras {#e-rn-improvements}

* El servicio de mensajería push se ha modernizado para optimizar el mantenimiento. (CAMP-47959)
* El servicio de mensajería SMS se ha modernizado para proporcionar una mayor estabilidad. (CAMP-52217)
* La solución predeterminada **Flujo de trabajo de creación de enriquecimiento de informes** se ha añadido. Después de importar una asignación de destino de una instancia a otra, simplemente ejecute el flujo de trabajo para importar las entradas de enriquecimiento de informes correspondientes. (CAMP-52452)

### Parches{#e-rn-patches}

* Se ha corregido un problema que podría provocar un error de tiempo de espera al mostrar la variable **Clic en caliente** informe. (CAMP-51582)
* Se ha corregido un problema que podía impedir que usara la integración con la variable **Lugares** servicio. (CAMP-51923)
* Se ha corregido un problema que podía impedir que el programador de flujos de trabajo funcionara correctamente. (CAMP-52003)
* Se ha corregido un problema que impedía que se mostraran los detalles del desglose al ver la versión del PDF de un informe dinámico personalizado con un gran volumen de datos. (CAMP-52178)
* Se ha corregido un problema que podía mostrar un error al acceder a los informes. (CAMP-52500)
* Se ha corregido un problema que aplicaba incorrectamente la variable **Limitar instancias de MTA para esta cuenta** Parámetro de conector SMS a todos los canales en lugar de aplicar solo a SMS. (CAMP-52640)
