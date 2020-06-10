---
title: Planificación de versiones de Campaign Standard
description: Esta página lista próximas versiones de Adobe Campaign Standard.
page-status-flag: never-activated
uuid: null
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
discoiquuid: null
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c7ed307e982e3fe41b2e3a7d0de7de356338bc08
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 5%

---


# Planificación de versiones {#release-planning}

Adobe mejora continuamente sus soluciones añadiendo nuevas funciones, mejoras y correcciones.

Todas las instancias de Adobe Campaign Standard se actualizan con cada nueva versión. No se requiere ninguna acción para la actualización.

Las actualizaciones se implementan en dos fases. En primer lugar, las instancias de Stage se actualizan para permitir a nuestros clientes probar nuevas capacidades y adaptar su configuración si es necesario. Las instancias de producción se actualizan posteriormente.

Todas las fechas de lanzamiento están sujetas a cambios: le recomendamos que visite esta página con regularidad para buscar actualizaciones.

**¡NUEVO!** Suscríbase a las notificaciones [de la versión de](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) Campaign Standard para obtener detalles sobre próximas versiones directamente en la bandeja de entrada.

## Versión 20.4: versión de octubre {#release-20-4-oct-release}

Las actualizaciones de Entorno se producen en olas, durante los intervalos de tiempo indicados a continuación. Encontrará información detallada sobre esta versión en las [Notas](../../rn/using/release-notes.md)de la versión. Si tiene alguna duda, póngase en contacto con [Adobe Client Care](https://helpx.adobe.com/es/enterprise/using/support-for-experience-cloud.html).

<table>
 <thead>
  <tr>
   <th> Entorno<br /> </th>
   <th> Fechas<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Fase<br /> </td>
   <td>21 y 22 de septiembre de 2020<br /> </td>
  </tr>
  <tr>
   <td> Producción<br /> </td>
   <td>28 de septiembre a 5 de octubre de 2020<br /> </td>
  </tr>
 </tbody>
</table>



## Preguntas y respuestas {#questions-and-answers}

**P: ¿Cuál es el impacto?**

A: Los cambios se enumeran en las [Notas](../../rn/using/release-notes.md)de la versión, incluidos los vínculos a la documentación relacionada. Adobe también recomienda consultar la página [Funciones](https://helpx.adobe.com/es/campaign/kb/acs-deprecated-and-removed-features.html)obsoletas y eliminadas. Estas páginas están disponibles para la nueva versión en la fecha de actualización de Stage entorno.

**P: ¿Cuál es el proceso de validación?**

A: A medida que se actualiza la instancia de ensayo, Adobe recomienda validar los procesos y casos de uso que funcionan correctamente con esta nueva versión e informar de cualquier problema a [Adobe Client Care](https://helpx.adobe.com/es/enterprise/using/support-for-experience-cloud.html).

**P: ¿Habrá acceso a la instancia durante el proceso de actualización?**

A: No. Durante la actualización de la instancia, es posible que la base de datos no esté accesible durante unos minutos. Todos los procesos se reinician automáticamente.

**P: ¿Seguirán enviándose los mensajes?**

A: No. Los mensajes no se enviarán durante unos minutos. Tan pronto como se complete la actualización, los procesos se reinician automáticamente.

**P: ¿Seguirán los flujos de trabajo corriendo y enviarán los envíos?**

A: No. Durante la actualización de la compilación, tanto el servidor de flujo de trabajo como MTA se detienen. Esto significa que los flujos de trabajo no se ejecutarán y los envíos no se enviarán durante unos minutos. No se requiere ninguna acción: Los flujos de trabajo volverán a inicio en cuanto se actualice la instancia.

**P: ¿Seguirá funcionando el seguimiento de vínculos en los mensajes durante la actualización?**

A: Sí, funcionarán. No se pueden enviar nuevos correos electrónicos durante la actualización, pero los vínculos de seguimiento incluidos en los mensajes de correo electrónico ya enviados estarán operativos.

**P: ¿Cómo sé que se completó la actualización?**

A: Al iniciar sesión en la Campaña, se mostrará una ventana emergente de notificación de lanzamiento con la versión más reciente.

Para cualquier otra pregunta, póngase en contacto con [Adobe Client Care](https://helpx.adobe.com/es/enterprise/using/support-for-experience-cloud.html).
