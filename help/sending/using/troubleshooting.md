---
title: Solución de problemas de entrega en Adobe Campaign Standard
description: Descubra qué hacer cuando experimente problemas de entrega con Adobe Campaign Standard.
page-status-flag: never-activated
uuid: 286fceee-65a9-4cb9-b205-9ce5d024675c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: sheduling-messages
discoiquuid: 9c7fd670-bba9-4f3c-8cb1-87397a1acd27
context-tags: delivery,schedule,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b2df5ca4d38e35f57815924ffbe0313dc1a22b29

---


# Resolución de problemas{#troubleshooting}

¿Está experimentando un problema de entrega? Puede encontrar la solución aquí...

**¿Por qué siempre recibo el mismo mensaje de error para un ISP en particular?**

Si siempre recibe el mismo mensaje de error para un ISP, es posible que el ISP haya detectado un error en su dirección de correo electrónico o IP. Lleve a cabo las siguientes recomendaciones:
* Compruebe si recibe un gran porcentaje de errores vinculados a direcciones de correo electrónico inexistentes (errores desconocidos **del** usuario).
* Actualice los formularios de suscripción para detectar cualquier error en los nombres de dominio introducidos (por ejemplo: gmaul.com o yaho.com).
* Si observa errores que indican que los mensajes se declaran como correo no deseado o que los mensajes están bloqueados constantemente, intente excluir del destino a los destinatarios que no hayan abierto o hecho clic en uno de sus mensajes en los últimos 12 meses.

Si el problema persiste, póngase en contacto con los servicios comerciales o de entrega, o con la asistencia de Adobe Campaign.

**¿Cuál es la diferencia entre una dirección de correo electrónico bloqueada y una dirección de correo electrónico en cuarentena?**

El estado **[!UICONTROL Blacklisted]** es el resultado de un bucle de retroalimentación (cuando una persona informa un mensaje como correo no deseado).

El estado **[!UICONTROL Quarantined]** es el resultado de un rebote suave o fuerte.

**¿Qué significan las diferentes razones de error de cuarentena?**

Estas son 10 razones posibles: no definido, usuario desconocido, dominio no válido, dirección bloqueada, rechazado, error omitido, inaccesible, cuenta deshabilitada, buzón lleno, no conectado.

Para obtener más información sobre esto, consulte [Explicación de la administración](../../sending/using/understanding-quarantine-management.md)de cuarentena.

**Uno de mis destinatarios fue bloqueado por error. ¿Cómo puedo desbloquearlos para poder volver a enviarles mensajes?**

* Vaya a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
* En los detalles del registro correspondiente, establezca el valor del **[!UICONTROL Status]** campo en **[!UICONTROL Valid]**.
* Guarde el registro.

**¿Cómo puedo saber si una de mis IP está bloqueada? ¿Cómo desbloqueo mis IP?**

Para comprobar si su dirección IP está bloqueada, puede utilizar varios sitios Web para verificarla:
* http://mxtoolbox.com/
* http://whatismyipaddress.com/blacklist-check
* http://www.blacklistalert.org/

Generalmente, el resultado de la comprobación de la dirección IP devolverá una lista que contiene detalles de la lista negra y también el nombre del sitio Web que puso en la lista negra la dirección IP.

Al hacer clic en el vínculo, puede acceder a los detalles del sitio Web.

A continuación, puede solicitar que el sitio web se elimine del sitio web que haya bloqueado la dirección IP.

El proceso de supresión de nombres de la lista puede variar según el sitio web. Algunos sitios requieren que cree una cuenta, mientras que otros solo necesitan que proporcione la dirección IP.
