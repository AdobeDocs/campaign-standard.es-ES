---
title: Actualización de la calificación de devoluciones después de una interrupción del ISP
description: Obtenga información sobre cómo actualizar la calificación de devoluciones después de una interrupción del ISP.
audience: delivery
hidefromtoc: true
exl-id: b06e9009-70c7-459f-8a9f-d5b7020d662f
source-git-commit: bfba6b156d020e8d2656239e713d2d24625bda54
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 91%

---

# Actualización de la calificación de devoluciones después de una interrupción del ISP {#update-bounce-qualification.md}

Si NO está ejecutando la última versión de Campaign, esta sección puede aplicarse a usted. Consulte con su representante de Adobe Campaign.

## Contexto

En caso de interrupción de un ISP, los correos electrónicos enviados a través de Campaign no se pueden enviar correctamente a su destinatario: estos correos electrónicos se marcarán erróneamente como rechazos.

En diciembre de 2020, un problema mundial con Gmail hizo que algunos mensajes de correo electrónico enviados a direcciones de correo electrónico de Gmail válidas fueran rechazados incorrectamente como direcciones de correo electrónico no válidas por los servidores de Gmail con la siguiente respuesta de rechazo: *“550-5.1.1 La cuenta de correo electrónico a la que intentó llegar no existe”.*

Google ha dicho que los cortes y las interrupciones de Gmail que causaron este problema empezaron el 14 de diciembre a las 06:55 h y terminaron a las 18:09 h EST del 15 de diciembre. Nuestro análisis de datos también mostró un pico muy corto en los rebotes de Gmail a las 02:06 h EST del 16 de diciembre, la mayoría ocurrió el 15 de diciembre entre las 14:00 h EST y las 18:30 h EST.

>[!NOTE]
>
>Puede consultar el Tablero de estado de Google Workspace en [esta página](https://www.google.com/appsstatus#hl=en&amp;v=status).


Por lógica de gestión de devoluciones estándar, Adobe Campaign añadió automáticamente estos destinatarios a la lista de cuarentena con una configuración **[!UICONTROL Status]** de **[!UICONTROL Quarantine]**. Para corregir esto, debe actualizar la tabla de cuarentena en Campaign buscando y quitando estos destinatarios o cambiando su **[!UICONTROL Status]** a **[!UICONTROL Valid]** para que el flujo de trabajo de limpieza nocturno los elimine.

Para encontrar los destinatarios afectados por este problema de Gmail, o en caso de que esto vuelva a suceder con cualquier otro ISP, consulte las instrucciones a continuación.

## Proceso de actualización

Deberá ejecutar una consulta en la tabla de cuarentena para filtrar todos los destinatarios de Gmail (u otro ISP) que se hayan visto potencialmente afectados por la interrupción para que se puedan eliminar de la lista de cuarentena e incluirlos en futuros envíos de correo electrónico de Campaign.

En función del periodo de tiempo del problema, se indican a continuación las directrices recomendadas para esta consulta.

>[!IMPORTANT]
>
>Estas fechas/horas se basan en la zona horaria estándar del este (EST). Ajuste la zona horaria de la instancia.

Para instancias de Campaign con información de respuesta de rechazo SMTP en el campo **[!UICONTROL Error text]** de la lista de cuarentena:

* **El texto de error (texto de cuarentena)** contiene “550-5.1.1 La cuenta de correo electrónico que intentó alcanzar no existe” Y **el texto de error (texto de cuarentena)** contiene “support.google.com” **
* **Actualizar estado (@lastModified)** a partir del 14/12/2020 6:55:00 AM
* **Actualizar estado (@lastModified)** el 16/12/2020 6 o antes:00:00 AM

Una vez que tenga la lista de destinatarios afectados, puede aplicarles un estado **[!UICONTROL Valid]** para que el flujo de trabajo **[!UICONTROL Database cleanup]** los elimine de la lista de cuarentena, o simplemente elimínelos de la tabla.

**Temas relacionados:**
* [Comprensión de los errores de entrega](../../sending/using/understanding-delivery-failures.md)
* [Clasificación del correo rechazado](../../sending/using/understanding-delivery-failures.md#bounce-mail-qualification)
