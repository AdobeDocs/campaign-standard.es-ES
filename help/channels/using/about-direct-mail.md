---
title: Acerca del correo directo
description: Descubra las principales características del canal de correo directo en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
feature: Direct Mail
role: User
level: Intermediate
exl-id: 815b4a0d-0486-4867-b751-b5ca8b643cb9
TQID: https://experienceleague.adobe.com/8VXdc-QOidRcDvgr5vMn-5bxHKYO6TnZS80FDsuA-GU
product_v2: id: dfc56824-e8b9-499e-85d4-21aedb507314
feature_v2: id: a075b2c1-7748-4328-b7f6-343aa314616a
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
level_v2: id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2: id: d00e9f03-e50b-4162-b143-0c0817c937c2
source-git-commit: 85d9a6a6a6b20412c2edadfc5ced5f5e248d1ac4
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 84%

---

# Acerca del correo directo{#about-direct-mail}

El correo directo es un canal sin conexión que le permite personalizar y generar el archivo requerido por los proveedores de correo directo. Esto le ofrece la posibilidad de mezclar canales en línea y sin conexión para los recorridos de los clientes.

>[!NOTE]
>
>Esta función es opcional. Compruebe el acuerdo de licencia. La función **[!UICONTROL Export]** es necesaria para utilizar el correo directo. Póngase en contacto con su administrador.

Los canales en línea le permiten crear sus mensajes (correo electrónico, SMS, envío por aplicaciones móviles, etc.) y enviarlos a su audiencia directamente desde Adobe Campaign. Con los canales sin conexión esto es diferente. Al preparar una entrega de correo directo, Adobe Campaign genera un archivo con todos los perfiles de destino y la información de contacto elegida (por ejemplo, una dirección postal). Después, puede enviar este archivo al proveedor de correo directo que se encarga de la entrega real.

En la siguiente sección se explica cómo crear y generar un envío de correo directo con un solo paso. También puede incluir una actividad de correo directo en un flujo de trabajo para organizar campañas que combinen canales en línea y sin conexión. Para obtener más información, consulte la guía [Flujos de trabajo](../../automating/using/get-started-workflows.md).

El proceso de usuario en Adobe Campaign es el siguiente:

1. Creación de la entrega
1. Elección del público
1. Definición del contenido
1. Configuración de la fecha de contacto
1. Generación del archivo

**Temas relacionados:**

* [Caso de uso: Emparejamiento de envíos de correo electrónico y correo directo](../../automating/using/coupling-email-direct-mail.md)

## Recomendaciones {#recommendations}

### Proveedores de correo postal {#direct-mail-providers}

En primer lugar, debe ponerse en contacto con su proveedor de correo directo y conocer sus recomendaciones. Identifique qué información de perfil debe incluirse en el archivo de extracción para que puedan personalizar la comunicación y enviarla al público. Por ejemplo, el nombre y los apellidos, la dirección postal, un código promocional, etc. Estos campos son los que agregará en la ficha [Definición de la extracción](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) del contenido del correo postal.

Asegúrese de marcar la casilla **[!UICONTROL Address specified]** en la información de sus perfiles. Si esta opción está activada, el perfil se agregará al destinatario. Si no, se usará una regla de tipología durante la fase de preparación para excluir el perfil (consulte [Creación del correo directo](../../channels/using/creating-the-direct-mail.md)). Durante la importación de perfiles, no olvide actualizar este campo.

![](assets/direct_mail_22.png)

### Direcciones postales {#postal-addresses}

Cuando se agregan los campos que se incluirán en el archivo de extracción, los campos de dirección postal están disponibles en el nodo **[!UICONTROL Location]**.

Adobe Campaign incluye un conjunto de campos calculados predefinidos que siguen la normalización de direcciones postales más comunes. Los campos están disponibles en el nodo **[!UICONTROL Postal address]**.

Una dirección puede contener de forma predeterminada hasta seis líneas: el primer campo calculado (**[!UICONTROL Line 1]**) contiene el nombre y los apellidos, las líneas siguientes contienen la dirección postal (calle, etc.) y la última línea contiene el código postal y el municipio o ciudad.

![](assets/direct_mail_23.png)
