---
solution: Campaign Standard
product: campaign
title: Solución de problemas de capacidad de entrega en Adobe Campaign Standard
description: Aprenda qué hacer cuando experimente problemas de entrega con Adobe Campaign Standard.
audience: sending
content-type: reference
topic-tags: sheduling-messages
context-tags: delivery,schedule,back
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '459'
ht-degree: 64%

---


# Resolución de problemas{#troubleshooting}

¿Está teniendo un problema de envío? Puede encontrar la solución aquí.

## El mismo mensaje de error para un ISP {#same-error-for-an-isp}

**¿Por qué siempre recibo el mismo mensaje de error para un ISP en particular?**

Si siempre recibe el mismo mensaje de error para un ISP, es posible que el ISP haya detectado un error en su dirección de correo electrónico o IP. Siga las siguientes recomendaciones:
* Compruebe si recibe un gran porcentaje de errores vinculados a direcciones de correo electrónico inexistentes (errores de **usuario desconocido**).
* Actualice los formularios de suscripción para detectar cualquier error en los nombres de dominio introducidos (por ejemplo: gmaul.com o yaho.com).
* Si nota errores que indican que sus mensajes están declarados como correo no deseado o que sus mensajes están bloqueados constantemente, intente excluir los destinatarios que no han abierto o hecho clic en uno de sus mensajes en los últimos 12 meses desde el destinatario.

Si el problema persiste, póngase en contacto con los servicios comerciales o de entrega o con el servicio de asistencia de Adobe Campaign.

## Lista de bloqueados frente a cuarentena {#denylist-versus-quarantine}

* **¿Cuál es la diferencia entre una dirección de correo electrónico en lista de bloqueados y una dirección de correo electrónico en cuarentena?**

   * El estado **[!UICONTROL On denylist]** es el resultado de un bucle de retroalimentación (cuando una persona informa un mensaje como correo no deseado).

   * El estado **[!UICONTROL Quarantined]** es el resultado de un rechazo suave o fuerte.
   Para obtener más información, consulte esta [sección](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist).

* **¿Qué significan las diferentes razones de error de cuarentena?**

   Estas son 10 razones posibles: no definido, usuario desconocido, dominio inválido, dirección en lista de bloqueados, rechazado, error omitido, inaccesible, cuenta deshabilitada, buzón lleno, no conectado.

   Para obtener más información, consulte [Comprensión de la administración de cuarentena](../../sending/using/understanding-quarantine-management.md).

## Eliminación de la lista de bloqueados {#removing-from-denylist}

* **Uno de mis destinatarios fue agregado a la  de lista de bloqueados por error. ¿Cómo puedo eliminarlos de la  de lista de bloqueados para que pueda enviar mensajes de nuevo con inicio?**

   * Vaya a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * En los detalles del registro correspondiente, establezca el valor del campo **[!UICONTROL Status]** en **[!UICONTROL Valid]**.
   * Guarde el registro.

* **¿Cómo puedo saber si una de mis IP está en  lista de bloqueados? ¿Cómo elimino mis IP de una lista de bloqueados?**

   Para comprobar si su dirección IP está en lista de bloqueados, puede utilizar varios sitios Web para verificarla, como:
   * [MX Toolbox](https://mxtoolbox.com/)
   * [¿Cuál es mi dirección IP?](https://whatismyipaddress.com)

   Generalmente, el resultado de la comprobación de la dirección IP devolverá una lista que contiene detalles de la  de lista de bloqueados y también el nombre del sitio web que bloqueó la dirección IP.

   Al hacer clic en el enlace correspondiente, puede acceder a los detalles del sitio web.

   Puede solicitar que su sitio web se elimine de la lista del sitio web que añadió la dirección IP a su lista de bloqueados.

   >[!NOTE]
   >
   >El proceso de supresión de nombres de la lista puede variar según el sitio web. Algunos sitios requieren que cree una cuenta, mientras que otros solo necesitan que proporcione la dirección IP.
