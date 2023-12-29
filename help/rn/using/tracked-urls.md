---
title: Problema de firma de URL rastreadas
description: Problema de firma de URL rastreadas
hidefromtoc: true
hide: true
exl-id: 8c2725a8-2c3a-448a-8c04-c0c2a5950574
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '196'
ht-degree: 100%

---

# Problema de firma de URL rastreadas {#tracked-urls}

Después de los cambios recientes, las direcciones URL rastreadas enviadas por Campaign pueden dar errores. Algunos buzones pueden verse más afectados que otros, ya que algunas empresas cuentan con herramientas de seguridad específicas que pueden afectar a los vínculos y alterar el mecanismo de firma de las URL.

Como consecuencia, Adobe ha optado por desactivar el mecanismo de firma para el seguimiento de vínculos. Este procedimiento corrige todos los vínculos de seguimiento.

Tenga en cuenta que los vínculos de baja pueden dar error como los demás. La frecuencia es variable en función del host, pero es inferior al 1 %.

**¿Se ha visto afectado?**

Algunos usuarios de Campaign Standard se ven afectados porque el mecanismo de firma del seguimiento de vínculos en correos electrónicos se ha introducido en [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) (octubre de 2020), pero está habilitado de forma predeterminada para todos los clientes.

**¿Cómo realizar la actualización?**

Recibirá la ayuda de Adobe en breve para actualizar su configuración. Se le enviará una notificación por correo electrónico con la cronología de la actualización.

**¿Cuáles son las consecuencias?**

Las tareas de mantenimiento requieren un tiempo de inactividad máximo de 25 minutos y, durante este periodo, todas las entregas, los vínculos de seguimiento y las llamadas a la API no funcionarán.

Una vez completada la actualización, todos los vínculos funcionarán según lo esperado.

>[!NOTE]
>
>En caso de que tenga preguntas acerca de estos cambios, póngase en contacto con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).
>
