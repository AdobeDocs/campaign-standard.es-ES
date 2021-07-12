---
solution: Campaign Standard
product: campaign
title: Acerca del correo postal
description: Descubra las principales características del canal de correo postal en Adobe Campaign.
audience: channels
content-type: reference
topic-tags: direct-mail
context-tags: delivery,directMailContent,back;deliveryCreation,wizard
feature: Correo directo
role: User
level: Intermediate
exl-id: 815b4a0d-0486-4867-b751-b5ca8b643cb9
source-git-commit: aeeb6b4984b3bdd974960e8c6403876fdfedd886
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 98%

---

# Acerca del correo directo{#about-direct-mail}

El correo postal es un canal sin conexión que le permite personalizar y generar el archivo requerido por los proveedores de correo postal. Esto le ofrece la posibilidad de mezclar canales en línea y sin conexión para los recorridos de los clientes.

>[!NOTE]
>
>Esta función es opcional. Compruebe el acuerdo de licencia. La función **[!UICONTROL Export]** es necesaria para utilizar el correo postal. Póngase en contacto con su administrador.

Los canales en línea permiten crear los mensajes (correo electrónico, SMS, envío por aplicaciones móviles, etc.) y enviarlos a su público directamente desde Adobe Campaign. Con los canales sin conexión esto es diferente. Al preparar una entrega de correo postal, Adobe Campaign genera un archivo con todos los perfiles de destino y la información de contacto elegida (por ejemplo, una dirección postal). Después, puede enviar este archivo al proveedor de correo postal que se encarga de la entrega real.

En la siguiente sección se explica cómo crear y generar un envío de correo postal con un solo paso. También puede incluir una actividad de correo postal en un flujo de trabajo para organizar campañas que combinen canales en línea y sin conexión. Para obtener más información, consulte la guía [Flujos de trabajo](../../automating/using/get-started-workflows.md).

El proceso de usuario en Adobe Campaign es el siguiente:

1. Creación de la entrega
1. Elección de la audiencia
1. Definición del contenido
1. Configuración de la fecha de contacto
1. Generación del archivo

**Temas relacionados:**

* [Caso de uso: Emparejamiento de envíos de correo electrónico y correo directo](../../automating/using/coupling-email-direct-mail.md)

## Recomendaciones {#recommendations}

### Proveedores de correo postal {#direct-mail-providers}

En primer lugar, debe ponerse en contacto con su proveedor de correo postal y conocer sus recomendaciones. Identifique qué información de perfil debe incluirse en el archivo de extracción para que puedan personalizar la comunicación y enviarla a la audiencia. Por ejemplo, el nombre y los apellidos, la dirección postal, un código promocional, etc. Estos campos son los que se agregan en la pestaña [Definición de la extracción](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) del contenido del correo postal.

Asegúrese de marcar la casilla **[!UICONTROL Address specified]** en la información de sus perfiles. Si esta opción está activada, el perfil se agregará al destinatario. Si no, se usará una regla de tipología durante la fase de preparación para excluir el perfil (consulte [Creación del correo postal](../../channels/using/creating-the-direct-mail.md)). Durante la importación de perfiles, no olvide actualizar este campo.

![](assets/direct_mail_22.png)

### Direcciones postales {#postal-addresses}

Cuando se agregan los campos que se incluirán en el archivo de extracción, los campos de dirección postal están disponibles en el nodo **[!UICONTROL Location]**.

Adobe Campaign incluye un conjunto de campos calculados predefinidos que siguen la normalización de direcciones postales más comunes. Los campos están disponibles en el nodo **[!UICONTROL Postal address]**.

Una dirección puede contener de forma predeterminada hasta seis líneas: el primer campo calculado (**[!UICONTROL Line 1]**) contiene el nombre y los apellidos, las líneas siguientes contienen la dirección postal (calle, etc.) y la última línea contiene el código postal y el municipio o ciudad.

![](assets/direct_mail_23.png)
