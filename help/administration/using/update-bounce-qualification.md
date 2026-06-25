---
title: Actualización de la calificación de devoluciones después de una interrupción del ISP
description: Obtenga información sobre cómo actualizar la calificación de devoluciones después de una interrupción del ISP.
audience: delivery
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
TQID: https://experienceleague.adobe.com/PcNbVFzTVJhadANGQ5uogj16VHiaNIf7HVn-7X-EbJA
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
topic_v2:
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c2422ff58487b6e8251eab2508760cd201b2eebe
workflow-type: tm+mt
source-wordcount: 441
ht-degree: 67%

---

# Actualización de la calificación de devoluciones después de una interrupción del ISP {#update-bounce-qualification.md}

## Contexto

En caso de interrupción de un ISP, los correos electrónicos enviados a través de Campaign no se pueden enviar correctamente a su destinatario: estos correos electrónicos se marcarán erróneamente como rechazos.

En diciembre de 2020, un problema global en Gmail hizo que algunos mensajes de correo electrónico enviados a direcciones de correo electrónico de Gmail válidas fueran rechazados incorrectamente como direcciones de correo electrónico no válidas por los servidores de Gmail con la siguiente respuesta de rechazo: *&quot;550-5.1.1 La cuenta de correo electrónico a la que intentó llegar no existe.&quot;*

Google ha declarado que las interrupciones y cortes de Gmail que causaron este problema empezaron el 14 de diciembre a las 6:55AM y terminaron a las 6:09PM EST el 15 de diciembre. Nuestro análisis de datos también mostró un pico muy corto en los rebotes de Gmail en 2:06AM EST el 16 de diciembre, la mayoría ocurrió el 15 de diciembre entre las 2:00 pm EST y las 6:30 pm EST.

>[!NOTE]
>
>Puede consultar el Panel de control de estado de Google Workspace en [esta página](https://www.google.com/appsstatus#hl=en&v=status).


Por lógica de gestión de devoluciones estándar, Adobe Campaign añadió automáticamente estos destinatarios a la lista de cuarentena con una configuración **[!UICONTROL Status]** de **[!UICONTROL Quarantine]**. Para corregir esto, debe actualizar la tabla de cuarentena en Campaign buscando y quitando estos destinatarios o cambiando su **[!UICONTROL Status]** a **[!UICONTROL Valid]** para que el flujo de trabajo de limpieza nocturno los elimine.

Para encontrar los destinatarios afectados por este problema de Gmail, o en caso de que esto vuelva a suceder con cualquier otro ISP, consulte las instrucciones a continuación.

## Proceso de actualización

Deberá ejecutar una consulta en la tabla de cuarentena para filtrar todos los destinatarios de Gmail (u otro ISP) que se hayan visto potencialmente afectados por la interrupción para que se puedan eliminar de la lista de cuarentena e incluirlos en futuros envíos de correo electrónico de Campaign.

En función del periodo de tiempo del problema, se indican a continuación las directrices recomendadas para esta consulta.

>[!IMPORTANT]
>
>Estas fechas/horas se basan en la zona horaria estándar del este (EST). Ajuste la zona horaria de la instancia.

Para instancias de Campaign con información de respuesta de rechazo SMTP en el campo **[!UICONTROL Error text]** de la lista de cuarentena:

* **Texto de error (texto de cuarentena)** contiene &quot;550-5.1.1 La cuenta de correo electrónico a la que intentó llegar no existe&quot; Y **Texto de error (texto de cuarentena)** contiene &quot;support.google.com&quot; **
* **Estado de la actualización (@lastModified)** el 14/12/2020 a las 6:55:00, o después
* **Estado de la actualización (@lastModified)** el 16/12/2020 a las 6:00:00 h, o antes

Una vez que tenga la lista de destinatarios afectados, puede aplicarles un estado **[!UICONTROL Valid]** para que el flujo de trabajo **[!UICONTROL Database cleanup]** los elimine de la lista de cuarentena, o simplemente elimínelos de la tabla.

**Temas relacionados:**

* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Calificación del correo rechazado](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)

