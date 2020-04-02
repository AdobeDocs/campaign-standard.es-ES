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
source-git-commit: 87168dca3604073d8a540c579448ab65f07cd976

---


# Resolución de problemas{#troubleshooting}

¿Está experimentando un problema de entrega? Puede encontrar la solución aquí.

## El mismo mensaje de error para un ISP {#same-error-for-an-isp}

**¿Por qué siempre recibo el mismo mensaje de error para un ISP en particular?**

Si siempre recibe el mismo mensaje de error para un ISP, es posible que el ISP haya detectado un error en su dirección de correo electrónico o IP. Lleve a cabo las siguientes recomendaciones:
* Compruebe si recibe un gran porcentaje de errores vinculados a direcciones de correo electrónico inexistentes (errores desconocidos **del** usuario).
* Actualice los formularios de suscripción para detectar cualquier error en los nombres de dominio introducidos (por ejemplo: gmaul.com o yaho.com).
* Si nota errores que indican que sus mensajes están declarados como correo no deseado o que sus mensajes están bloqueados constantemente, intente excluir los destinatarios que no han abierto o hecho clic en uno de sus mensajes en los últimos 12 meses desde el destinatario.

Si el problema persiste, póngase en contacto con los servicios comerciales o de entrega, o con el servicio de asistencia de Adobe Campaign.

## Lista negra versus cuarentena {#blacklisting-versus-quarantine}

* **¿Cuál es la diferencia entre una dirección de correo electrónico en la lista negra y una dirección de correo electrónico en cuarentena?**

   * El estado **[!UICONTROL Blacklisted]** es el resultado de un bucle de retroalimentación (cuando una persona informa un mensaje como correo no deseado).

   * El estado **[!UICONTROL Quarantined]** es el resultado de un rebote suave o fuerte.
   For more on this, see this [section](../../sending/using/understanding-quarantine-management.md#quarantine-vs-blacklisting).

* **¿Qué significan las diferentes razones de error de cuarentena?**

   Estas son 10 razones posibles: no definido, usuario desconocido, dominio inválido, dirección en la lista negra, rechazado, error omitido, inaccesible, cuenta deshabilitada, buzón lleno, no conectado.

   Para obtener más información sobre esto, consulte [Explicación de la administración](../../sending/using/understanding-quarantine-management.md)de cuarentenas.

## Anular la lista negra {#unblacklisting}

* **Uno de mis destinatarios fue en la lista negra por error. ¿Cómo puedo desbloquearlos para que pueda enviar mensajes de nuevo con inicio?**

   * Vaya a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * En los detalles del registro correspondiente, establezca el valor del **[!UICONTROL Status]** campo en **[!UICONTROL Valid]**.
   * Guarde el registro.

* **¿Cómo puedo averiguar si una de mis IP es en la lista negra? ¿Cómo desbloqueo mis IP?**

   Para comprobar si su dirección IP está en la lista negra, puede utilizar varios sitios Web para verificarla:
   * https://mxtoolbox.com/
   * https://whatismyipaddress.com/blacklist-check
   * https://www.blacklistalert.org/
   Generalmente, el resultado de la comprobación de la dirección IP devolverá una lista que contiene detalles de la lista negra y también el nombre del sitio Web que en la lista negra la dirección IP.

   Al hacer clic en el vínculo correspondiente, puede acceder a los detalles del sitio Web.

   A continuación, puede solicitar que el sitio web se elimine del sitio web que haya en la lista negra la dirección IP.

   >[!NOTE]
   >
   >El proceso de supresión de nombres de la lista puede variar según el sitio web. Algunos sitios requieren que cree una cuenta, mientras que otros solo necesitan que proporcione la dirección IP.
