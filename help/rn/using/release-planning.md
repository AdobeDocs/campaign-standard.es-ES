---
solution: Campaign Standard
product: campaign
title: Planificación de versiones de Campaign Standard
description: Esta página enumera las próximas versiones de Adobe Campaign Standard.
audience: rn
content-type: reference
topic-tags: campaign-standard-release-planning
feature: Información general
role: Business Practitioner
level: Beginner
exl-id: 1f48d4da-5622-4fab-af87-fcce0e40ade1
source-git-commit: c98aa913f4004d49a897ea71e39cbfe6b3dd53c1
workflow-type: tm+mt
source-wordcount: '462'
ht-degree: 97%

---

# Planificación de versiones {#release-planning}

Adobe mejora continuamente sus soluciones añadiendo nuevas funciones, mejoras y correcciones.

Todas las instancias de Adobe Campaign Standard se actualizan con cada nueva versión. No se requiere ninguna acción para la actualización.

Las actualizaciones se implementan en dos fases. En primer lugar, las instancias de prueba se actualizan para permitir a nuestros clientes probar nuevas funciones y adaptar su configuración si es necesario. Las instancias de producción se actualizan posteriormente.

Todas las fechas de lanzamiento están sujetas a cambios: le recomendamos que visite esta página con regularidad para buscar actualizaciones.

## Versión 21.2: Versión de junio de 2021 {#release-21-2-release}

Las actualizaciones de entorno se producen en olas, durante los intervalos de tiempo indicados a continuación. Las fechas exactas se comunican por correo electrónico a cada cliente.

Encontrará información detallada sobre esta versión en las [Notas de la versión anteriores](../../rn/using/e-release-notes.md).

<table>
 <thead>
  <tr>
   <th> Entorno<br /> </th>
   <th> Fechas<br /> </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td>Prueba<br /> </td>
   <td>7-8 de junio de 2021<br /> </td>
  </tr>
  <tr>
   <td> Producción<br /> </td>
   <td>14-21 de junio de 2021<br /> </td>
  </tr>
 </tbody>
</table>

Si tiene alguna duda, póngase en contacto con el [Equipo de atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/using/support-for-experience-cloud.html).

Suscríbase a las [notificaciones de versiones de Campaign Standard](http://amc-mkt-prod1-t.adobe-campaign.com/lp/LP25?service=%40rZ5cqp2DgNzrgz0alKPInakNbPSTeJYozZYnS7Wbs802u4GlISkHZX4omtK00nAU6xzZ6luEWQzr7kQ9pkCwJYumWkU) para obtener detalles acerca de las próximas versiones directamente en su bandeja de entrada.

## Preguntas y respuestas {#questions-and-answers}

**P: ¿Cuál es el impacto?**

R: Los cambios se enumeran en las [notas de la versión](../../rn/using/release-notes.md), incluidos los vínculos a la documentación relacionada. Adobe también recomienda consultar la página [Funciones obsoletas y eliminadas](../../rn/using/deprecated-features.md). Estas páginas están disponibles para la nueva versión en la fecha para el entorno de ensayo de la actualización.

**P: ¿Cuál es el proceso de validación?**

R: A medida que se actualiza la instancia de prueba, Adobe recomienda validar los procesos y casos de uso que funcionan correctamente con esta nueva versión e informar de cualquier problema al [equipo de Atención al cliente de Adobe](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).

**P: ¿Habrá acceso a la instancia durante el proceso de actualización?**

R: No. Durante la actualización de la instancia, es posible que la base de datos no esté accesible durante unos minutos. Todos los procesos se reinician automáticamente.

**P: ¿Seguirán enviándose los mensajes?**

R: No. Los mensajes no se enviarán durante unos minutos. Tan pronto como se complete la actualización, los procesos se reinician automáticamente.

**P: ¿Seguirán funcionando los flujos de trabajo y realizarán envíos?**

R: No. Durante la actualización de la compilación, tanto el servidor de flujo de trabajo como el MTA se detienen. Esto significa que los flujos de trabajo no se ejecutarán y los envíos no se realizarán durante unos minutos. No se requiere ninguna acción: los flujos de trabajo se reiniciarán en cuanto se actualice la instancia.

**P: ¿Seguirá funcionando el seguimiento de vínculos en los mensajes durante la actualización?**

R: Sí, funcionará. No se pueden enviar nuevos correos electrónicos durante la actualización, pero los vínculos de seguimiento incluidos en los mensajes de correo electrónico ya enviados estarán operativos.

**P: ¿Cómo sé que se completó la actualización?**

R: Al iniciar sesión en Campaign, aparecerá una ventana emergente de notificación que indica la versión más reciente.

Para cualquier otra pregunta, póngase en contacto con [el equipo de Atención al cliente de Adobe](https://helpx.adobe.com/enterprise/using/support-for-experience-cloud.html).
