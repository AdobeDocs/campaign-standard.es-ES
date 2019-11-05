---
title: Acerca del correo postal
description: Descubra las principales características del canal de correo directo en Adobe Campaign.
page-status-flag: nunca activado
uuid: 24add992-2efe-4b73-81c9-cda3e921ab16
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: canales
content-type: referencia
topic-tags: direct-mail
discoiquuid: e1fbf39c-9c30-493c-8322-9c71e18ce98c
context-tags: entrega,directMailContent,back;deliveryCreation,asistente
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Acerca del correo postal{#about-direct-mail}

El correo postal es un canal sin conexión que le permite personalizar y generar el archivo requerido por los proveedores de correo postal. Esto le ofrece la posibilidad de mezclar canales en línea y sin conexión para los viajes de los clientes.

>[!NOTE]
>
>Esta función es opcional. Compruebe el acuerdo de licencia. La función **[!UICONTROL Export]** es necesaria para utilizar el correo directo. Póngase en contacto con el administrador.

Los canales en línea permiten crear los mensajes (correo electrónico, SMS, envío por aplicaciones móviles, etc.) y enviarlos a su público directamente desde Adobe Campaign. Con los canales sin conexión esto es diferente. Al preparar un envío de correo postal, Adobe Campaign genera un archivo con todos los perfiles de destino y la información de contacto elegida (por ejemplo, una dirección postal). Después, puede enviar este archivo al proveedor de correo postal que se encarga del envío real.

En la siguiente sección se explica cómo crear y generar una entrega directa de correo de una sola toma. También puede incluir una actividad de correo directo en un flujo de trabajo para orquestar campañas que combinen canales en línea y sin conexión. For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

El proceso de usuario en Adobe Campaign es el siguiente:

1. Creación del envío
1. Elección de la audiencia
1. Definición del contenido
1. Configuración de la fecha de contacto
1. Generación del archivo

## Recomendaciones {#recommendations}

### Proveedores de correo directo {#direct-mail-providers}

En primer lugar, debe ponerse en contacto con su proveedor de correo directo y recopilar sus recomendaciones. Identifique qué información de perfil debe incluirse en el archivo de extracción para poder personalizar la comunicación y enviarla a la audiencia. Por ejemplo, el nombre y los apellidos, la dirección postal, un código de promoción, etc. Estos campos son los que se agregan en la ficha [Definición de la extracción](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) del contenido del correo directo.

Asegúrese de marcar la **[!UICONTROL Address specified]** casilla en la información de sus perfiles. Si esta opción está activada, el perfil se agregará al destino. No lo es, se excluirá mediante una regla de tipología durante la fase de preparación (consulte [Creación del correo](../../channels/using/creating-the-direct-mail.md)directo). Durante la importación de perfiles, no olvide actualizar este campo.

![](assets/direct_mail_22.png)

### Direcciones postales {#postal-addresses}

Cuando se agregan los campos que se van a incluir en el archivo de extracción, los campos de dirección postal están disponibles en el **[!UICONTROL Location]** nodo.

Adobe Campaign le ofrece un conjunto de campos calculados predefinidos que siguen las normalización de direcciones postales más comunes. Los campos están disponibles en el **[!UICONTROL Postal address]** nodo.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

