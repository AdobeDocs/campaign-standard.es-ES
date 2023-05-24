---
title: Solución de problemas de envío en Adobe Campaign Standard
description: Aprenda qué debe hacer cuando experimente problemas de envío con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
feature: Deliverability
role: User
level: Intermediate
exl-id: 0470b986-c00a-4441-8621-82c7112a9953
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 61%

---

# Resolución de problemas{#troubleshooting}

¿Está teniendo un problema de envío? Puede encontrar la solución aquí.

## El mismo mensaje de error para un ISP {#same-error-for-an-isp}

**¿Por qué siempre recibo el mismo mensaje de error para un ISP en particular?**

Si siempre recibe el mismo mensaje de error para un ISP, es posible que el ISP haya detectado un error en su dirección de correo electrónico o IP. Siga las siguientes recomendaciones:
* Compruebe si recibe un gran porcentaje de errores vinculados a direcciones de correo electrónico inexistentes (errores de **usuario desconocido**).
* Actualice los formularios de suscripción para detectar cualquier error en los nombres de dominio introducidos (por ejemplo: gmaul.com o yaho.com).
* Si nota errores que indican que sus mensajes están declarados como correo no deseado o que sus mensajes están bloqueados constantemente, intente excluir los destinatarios que no han abierto o hecho clic en uno de sus mensajes en los últimos 12 meses desde el destinatario.

Si el problema persiste, póngase en contacto con los servicios comerciales o de envío o con el servicio de asistencia de Adobe Campaign.

## Lista de bloqueados frente a cuarentena {#denylist-versus-quarantine}

* **¿Cuál es la diferencia entre una dirección de correo electrónico en la lista de bloqueados de la y una dirección de correo electrónico en cuarentena?**

   * El estado **[!UICONTROL On denylist]** es el resultado de un [bucle de retroalimentación](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/transition-process/infrastructure.html?lang=es#feedback-loops) (cuando una persona informa un mensaje como correo no deseado).

   * El estado **[!UICONTROL Quarantined]** es el resultado de un rechazo suave o fuerte.
   Para obtener más información, consulte esta [sección](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **¿Qué significan las diferentes razones de error de cuarentena?**

   Estas son 10 razones posibles: no definido, usuario desconocido, dominio inválido, dirección en la lista de bloqueados, rechazado, error omitido, inaccesible, cuenta deshabilitada, buzón lleno, sin conexión.

   Para obtener más información, consulte [Comprensión de la administración de cuarentena](../../sending/using/understanding-quarantine-management.md).

## Eliminación de la lista de bloqueados {#removing-from-denylist}

* **Uno de mis destinatarios fue agregado a la lista de bloqueados de la por error. ¿Cómo puedo quitarlos de la lista de bloqueados de la para que pueda volver a enviarles mensajes?**

   * Vaya a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * En los detalles del registro correspondiente, establezca el valor del campo **[!UICONTROL Status]** en **[!UICONTROL Valid]**.
   * Guarde el registro.

* **¿Cómo puedo averiguar si una de mis IP está en lista de bloqueados de la? ¿Cómo elimino mis IP de una lista de bloqueados?**

   Para comprobar si su dirección IP está en lista de bloqueados, puede utilizar varios sitios web para verificarla, como:
   * [MX Toolbox](https://mxtoolbox.com/)
   * [¿Cuál es mi dirección IP?](https://whatismyipaddress.com)

   Por lo general, el resultado de la comprobación de la dirección IP muestra una lista que contiene detalles de la lista de bloqueados de la dirección IP y también el nombre del sitio web que bloqueó la dirección IP.

   Al hacer clic en el enlace correspondiente, puede acceder a los detalles del sitio web.

   Puede solicitar que su sitio web se elimine de la lista del sitio web que añadió la dirección IP a su lista de bloqueados.

   >[!NOTE]
   >
   >El proceso de supresión de nombres de la lista puede variar según el sitio web. Algunos sitios requieren que cree una cuenta, mientras que otros solo necesitan que proporcione la dirección IP.
