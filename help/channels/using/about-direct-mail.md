---
title: Acerca del correo directo
seo-title: Acerca del correo directo
description: Acerca del correo directo
seo-description: Descubrir las principales especificidades del canal de correo directo en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 24 add 992-2 efe -4 b 73-81 c 9-cda 3 e 921 ab 16
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: correo directo
discoiquuid: e 1 fbf 39 c -9 c 30-493 c -8322-9 c 71 e 18 ce 98 c
context-tags: delivery, directmailcontent, back; Deliverycreation, wizard
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# About direct mail{#about-direct-mail}

El correo directo es un canal sin conexión que permite personalizar y generar el archivo requerido por proveedores de correo directo. Ofrece la posibilidad de mezclar canales en línea y sin conexión en sus trayectorias de clientes.

>[!NOTE]
>
>Esta función es opcional. Verifique su contrato de licencia. The **[!UICONTROL Export]** role is required to use direct mail. Comuníquese con el administrador.

Los canales en línea permiten crear mensajes (correo electrónico, SMS, entrega de aplicaciones móviles, etc.) y enviarlos directamente a su audiencia desde Adobe Campaign. Con los canales sin conexión, es diferente. Cuando se prepara una entrega de correo directo, Adobe Campaign genera un archivo que incluye todos los perfiles de destino y la información de contacto elegida (por ejemplo, la dirección postal). A continuación, podrá enviar este archivo a su proveedor de correo directo que se encargará del envío real.

La siguiente sección explica cómo crear y generar una entrega de correo electrónico directa de una sola toma. También tiene la posibilidad de incluir una actividad de correo directo en un flujo de trabajo para orquestar campañas que combinen canales en línea y sin conexión. For more on this, refer to the [Workflows](../../automating/using/workflow-data-and-processes.md) guide.

El proceso de usuario en Adobe Campaign es el siguiente:

1. Creación de la entrega
1. Elección de la audiencia
1. Definición del contenido
1. Configuración de la fecha de contacto
1. Generación del archivo

## Recommendations {#recommendations}

### Direct mail providers {#direct-mail-providers}

Primero, debe comunicarse con su proveedor de correo directo y recopilar sus recomendaciones. Identifique qué información de perfil debe incluirse en el archivo de extracción para personalizar la comunicación y enviarla a la audiencia. Por ejemplo, el nombre y el apellido, la dirección postal, un código de promoción, etc. These fields are the ones that you will add in the [Defining the extraction](../../channels/using/defining-the-direct-mail-content.md#defining-the-extraction) tab of the direct mail's content.

Make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information. Si se activa esta opción, el perfil se agregará al objetivo. It is not, it will excluded by a typology rule during the preparation phase (see [Creating the direct mail](../../channels/using/creating-the-direct-mail.md)). Durante la importación de perfil, no olvide actualizar este campo.

![](assets/direct_mail_22.png)

### Postal addresses {#postal-addresses}

When you add the fields to include in the extraction file, the postal address fields are available in the **[!UICONTROL Location]** node.

Adobe Campaign ofrece un conjunto de campos calculados predefinidos que siguen las normalizaciones de direcciones postales más comunes. The fields are available in the **[!UICONTROL Postal address]** node.

An address can contain up to six lines by default: the first calculated field ( **[!UICONTROL Line 1]** contains the first name and last name, the next lines contain the postal address (road etc.), and the last line contains the ZIP/Postal code and town or city.

![](assets/direct_mail_23.png)

