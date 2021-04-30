---
solution: Campaign Standard
product: campaign
title: Problema de firma de direcciones URL rastreadas
description: Problema de firma de direcciones URL rastreadas
translation-type: tm+mt
source-git-commit: 830c003e36cec41e5cf480f66812900312609e9f
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 3%

---


# Problema de firma de URL rastreadas {#tracked-urls}

Después de los cambios recientes, las direcciones URL rastreadas enviadas por Campaign pueden fallar. Algunos buzones pueden verse más afectados que otros, ya que algunas empresas cuentan con herramientas de seguridad específicas que pueden afectar a los vínculos y alterar el mecanismo de firma de la dirección URL.

Como consecuencia, Adobe decidió desactivar el mecanismo de firma para el seguimiento de vínculos. Este procedimiento corrige todos los vínculos de seguimiento.

Tenga en cuenta que los vínculos de baja pueden fallar como cualquier otro vínculo, la frecuencia es variable de host a host pero es inferior al 1%.

**¿Estás afectado?**

Algunos usuarios de Campaign Standards se ven afectados porque el mecanismo de firma para el seguimiento de vínculos en correos electrónicos se ha introducido en [Campaign Standard 20.4](release-notes-2020.md#release-20-4---october-2020) - octubre de 2020 - y está habilitado de forma predeterminada para todos los clientes.

**¿Cómo se actualiza?**

Adobe trabajará con usted para actualizar su configuración en breve. Recibirá una notificación por correo electrónico con su cronología de actualización.

**¿Cuál es el impacto?**

El mantenimiento requiere un tiempo de inactividad máximo de 25 minutos y durante este periodo todas las entregas, los vínculos de seguimiento y las llamadas a la API no funcionarán.

Una vez completada la actualización, todos los vínculos funcionan según lo esperado.

>[!NOTE]
>
>Para cualquier pregunta acerca de estos cambios, póngase en contacto con el [Servicio de atención al cliente de Adobe](https://helpx.adobe.com/es/enterprise/admin-guide.html/enterprise/using/support-for-experience-cloud.ug.html).

