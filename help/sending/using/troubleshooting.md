---
title: Solución de problemas de capacidad de entrega en Adobe Campaign Standard
description: Aprenda qué hacer cuando experimente problemas de entrega con el Adobe Campaign Standard.
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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '473'
ht-degree: 51%

---


# Resolución de problemas{#troubleshooting}

¿Está teniendo un problema de envío? Puede encontrar la solución aquí.

## El mismo mensaje de error para un ISP {#same-error-for-an-isp}

**¿Por qué siempre recibo el mismo mensaje de error para un ISP en particular?**

Si siempre recibe el mismo mensaje de error para un ISP, es posible que el ISP haya detectado un error en su dirección de correo electrónico o IP. Siga las siguientes recomendaciones:
* Compruebe si recibe un gran porcentaje de errores vinculados a direcciones de correo electrónico inexistentes (errores de **usuario desconocido**).
* Actualice los formularios de suscripción para detectar cualquier error en los nombres de dominio introducidos (por ejemplo: gmaul.com o yaho.com).
* Si nota errores que indican que sus mensajes están declarados como correo no deseado o que sus mensajes están bloqueados constantemente, intente excluir los destinatarios que no han abierto o hecho clic en uno de sus mensajes en los últimos 12 meses desde el destinatario.

Si el problema persiste, póngase en contacto con los servicios comerciales o de entrega, o con el servicio de asistencia de Adobe Campaign.

## Lista de bloques frente a cuarentena {#block-list-versus-quarantine}

* **¿Cuál es la diferencia entre una dirección de correo electrónico en una lista de bloques y una dirección de correo electrónico en cuarentena?**

   * El estado **[!UICONTROL On block list]** es el resultado de un bucle de retroalimentación (cuando una persona informa un mensaje como correo no deseado).

   * El estado **[!UICONTROL Quarantined]** es el resultado de un rechazo suave o fuerte.
   For more on this, see this [section](../../sending/using/understanding-quarantine-management.md#quarantine-vs-block-list).

* **¿Qué significan las diferentes razones de error de cuarentena?**

   Estas son 10 razones posibles: no definido, usuario desconocido, dominio inválido, dirección en la lista de bloques, rechazado, error omitido, inaccesible, cuenta deshabilitada, buzón lleno, no conectado.

   Para obtener más información, consulte [Comprensión de la administración de cuarentena](../../sending/using/understanding-quarantine-management.md).

## Quitando de la lista de bloques {#removing-from-block-list}

* **Uno de mis destinatarios fue agregado a la lista de bloques por error. ¿Cómo eliminarlos de la lista de bloqueos para que pueda enviar mensajes de nuevo con inicio?**

   * Vaya a **[!UICONTROL Administration > Channels > Quarantines > Addresses]**.
   * En los detalles del registro correspondiente, establezca el valor del campo **[!UICONTROL Status]** en **[!UICONTROL Valid]**.
   * Guarde el registro.

* **¿Cómo puedo saber si una de mis IP está en una lista de bloques? ¿Cómo elimino mis IP de una lista de bloques?**

   Para comprobar si su dirección IP está en una lista de bloques, puede utilizar varios sitios Web para verificarla, como:
   * [Cuadro de herramientas MX](https://mxtoolbox.com/)
   * [¿Cuál es mi dirección IP?](https://whatismyipaddress.com)
   Generalmente, el resultado de la comprobación de la dirección IP devolverá una lista que contiene detalles de la lista de bloques y también el nombre del sitio web que bloqueó la dirección IP.

   Al hacer clic en el enlace correspondiente, puede acceder a los detalles del sitio web.

   A continuación, puede solicitar que el sitio Web sea eliminado del sitio Web que agregó la dirección IP a la lista de bloques.

   >[!NOTE]
   >
   >El proceso de supresión de nombres de la lista puede variar según el sitio web. Algunos sitios requieren que cree una cuenta, mientras que otros solo necesitan que proporcione la dirección IP.
