---
solution: Campaign Standard
product: campaign
title: Notas de la versión anteriores
description: Notas de la versión anteriores
feature: Información general
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: 4b10eb63-3fea-438e-a1a7-25fbf7b0e5b0
source-git-commit: fc542488cb52c4ff4e0457025a8312d2f2814cea
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 45%

---

# Notas de la versión anteriores {#new-release}

Esta página describe las nuevas funciones, mejoras y correcciones incluidas en la próxima versión de Campaign Standard.

>[!CAUTION]
>
> Este contenido está sujeto a cambios sin previo aviso hasta la fecha de actualización de los entornos de ensayo. Obtenga más información en la [página de planificación de versiones](../../rn/using/release-planning.md).


## Versión 21.3: septiembre de 2021 {#release-21-3---sept-2021}


**Novedades**


<table> 
<thead> 
<tr> 
<th> <strong>Interfaz de Experience Cloud unificada</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Se ha cambiado la barra de encabezado de Adobe Campaign para unificar y mejorar su experiencia en todos los productos y servicios de Experience Cloud. Estos cambios están diseñados para facilitar su vida, incluyendo:</p>
<ul>
<li>Es más fácil cambiar entre las organizaciones o a otra aplicación.</li>
<li>Guía del usuario mejorada: al incluir Experience League en el producto, los resultados de la búsqueda también incluyen resultados de foros de la comunidad y más contenido de vídeo, lo que facilita el acceso a más contenido para sacar el máximo partido de la aplicación. También hemos agregado un mecanismo de comentarios en el menú Ayuda, lo que facilita informar sobre problemas o compartir ideas.</li>
<li>Notificaciones mejoradas: la lista desplegable Notificaciones ahora tiene dos fichas (una para sus propias notificaciones de productos y otra para anuncios de productos globales).</li>
</ul>
<!--<p>For more information refer to the <a href="../../start/using/interface-description.md#top-bar">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

<table> 
<thead> 
<tr> 
<th> <strong>Pista de auditoría</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>La nueva función Pista de auditoría captura, en tiempo real, una lista completa de las acciones y eventos que se producen dentro de Adobe Campaign. Incluye una forma de autoservicio de acceder a un historial de datos para responder preguntas como:</p>
<ul>
<li>¿Qué ha pasado con este flujo de trabajo y quién lo actualizó por última vez?</li>
<li>¿Quién hizo los últimos cambios?</li>
<li>¿Cuál era el estado anterior?</li>
</ul>
<p>Adobe Campaign ahora audita las acciones de creación, edición y eliminación para: flujos de trabajo, opciones, recursos personalizados. También se realiza un seguimiento de las modificaciones de esos elementos.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>


<table> 
<thead> 
<tr> 
<th> <strong>Modo de diagnóstico del flujo de trabajo</strong><br /> </th> 
</tr> 
</thead> 
<tbody> 
<tr> 
<td>
<p>Ahora puede ejecutar flujos de trabajo de campaña en modo de diagnóstico. Este modo registra información para ayudar a solucionar los problemas de ejecución. El plan de ejecución completo se registra si una consulta de flujo de trabajo tarda, de forma predeterminada, más de un minuto.</p>
<!--<p>For more information refer to the <a href="../../administration/using/audit.md">detailed documentation</a>.
</p>-->
</td> 
</tr> 
</tbody> 
</table>

**Mejoras**

* Al crear una entrega recurrente en un flujo de trabajo, vinculado a un contenido de Adobe Experience Manager, el estado de aprobación del contenido ahora se comprueba antes de enviarlo.
* El límite de conexión a la base de datos ahora está alineado con el paquete de Campaign para evitar errores de conexión.
* Se ha añadido una comprobación de coherencia al crear índices en recursos personalizados y se han mejorado los mensajes de error.

**Parches**

* Se ha corregido un error de tiempo de espera al importar contenido de correo electrónico desde una dirección URL. (CAMP-49054)
* Se ha corregido un error (-69) que se producía al finalizar la sesión, al acceder a una dirección URL con marcador o al actualizar una página desde el explorador. (CAMP-49003, CAMP-48930, CAMP-48894)
* Se ha corregido un problema que se producía al sincronizar reglas desde el servidor de envío heredado al nuevo servidor de envío. (CAMP-48923)
* Se ha corregido un problema que se producía al cargar una plantilla de correo electrónico con etiquetas HTML en el Diseñador de correo electrónico. (CAMP-48243)
