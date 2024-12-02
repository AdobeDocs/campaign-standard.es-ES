---
title: Planificación de versiones de Campaign Standard
description: Esta página enumera las próximas versiones de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Overview
role: User
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: 8da7d90905745b99f52841483a2d540e9781104e
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 97%

---

# Planificación de versiones {#release-planning}

Adobe mejora continuamente sus soluciones añadiendo nuevas funciones, mejoras y correcciones.

Todas las instancias de Adobe Campaign Standard se actualizan con cada nueva versión. No se requiere ninguna acción para la actualización.

Las actualizaciones se implementan en dos fases. En primer lugar, las fases de prueba se actualizan para permitirle probar nuevas funciones y adaptar su configuración si es necesario. Las instancias de producción se actualizan posteriormente.

Todas las fechas de las versiones están sujetas a cambios: visite esta página regularmente para buscar actualizaciones. Las actualizaciones de entorno se producen en olas, durante los intervalos de tiempo indicados a continuación. Las fechas exactas se comunican por correo electrónico a cada cliente.

## Versión 25.1: versión de invierno de 2025 {#release-25-1-release}

Encontrará información detallada acerca de esta versión en las [Notas de la versión](release-notes.md) cuando comiencen las actualizaciones del entorno de ensayo.

<table>
 <thead>
  <tr>
   <th> Entornos </th>
   <th> Fechas</th>
   <!--th> General Availability </th-->
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Prueba </td>
   <td>7 de enero a 4 de febrero de 2025 </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
  <tr>
   <td>Producción </td>
   <td>13 de enero a 25 de febrero de 2025 </td>
   <!--td>2025 - Dates to be confirmed</td-->
  </tr>
 </tbody>
</table>

## Preguntas y respuestas {#questions-and-answers}

**P: ¿Cuál es el impacto?**

R: Los cambios se enumeran en las [notas de la versión](../../rn/using/release-notes.md), incluidos los vínculos a la documentación relacionada. Adobe también recomienda consultar la página [Funciones obsoletas y eliminadas](../../rn/using/deprecated-features.md). Estas páginas están disponibles para la nueva versión en la fecha para el entorno de ensayo de la actualización.

**P: ¿Cuál es el proceso de validación?**

R: A medida que se actualiza la instancia de prueba, Adobe recomienda validar los procesos y casos de uso que funcionan correctamente con esta nueva versión e informar de cualquier problema al [equipo de Atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/using/support-for-experience-cloud.html).

**P: ¿Habrá acceso a la instancia durante el proceso de actualización?**

R: No. Durante la actualización de la instancia, es posible que la base de datos no esté accesible durante unos minutos. Todos los procesos se reinician automáticamente.

**P: ¿Seguirán enviándose los mensajes?**

R: No. Los mensajes no se enviarán durante unos minutos. Cuando se completa la actualización, los procesos se reinician automáticamente.

**P: ¿Seguirán funcionando los flujos de trabajo y realizarán envíos?**

R: No. Durante la actualización de la compilación, tanto el servidor de flujo de trabajo como el MTA se detienen. Como consecuencia, los flujos de trabajo no se ejecutarán y los envíos no se realizarán durante unos minutos. No se requiere ninguna acción: los flujos de trabajo se reiniciarán en cuanto se actualice la instancia.

**P: ¿Seguirá funcionando el seguimiento de vínculos en los mensajes durante la actualización?**

R: Sí, funcionará. No se pueden enviar nuevos correos electrónicos durante la actualización, pero los vínculos de seguimiento incluidos en los mensajes de correo electrónico ya enviados estarán operativos.

**P: ¿Cómo sé que se completó la actualización?**

R: Al iniciar sesión en Campaign, aparecerá una ventana emergente de notificación que indica la versión más reciente.

Para cualquier otra pregunta, póngase en contacto con [el equipo de Atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/using/support-for-experience-cloud.html).
