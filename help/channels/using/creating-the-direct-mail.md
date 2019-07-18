---
title: Creación del correo directo
seo-title: Creación del correo directo
description: Creación del correo directo
seo-description: Siga estos pasos para crear una entrega de correo electrónico directa en Adobe Campaign.
page-status-flag: no activado nunca
uuid: 3 b 1365 c 4-4 ea 1-4434-818 b -05 ff 0 c 9 b 42 c 1
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: correo directo
discoiquuid: 5 b 02227 f -9438-4001-bc 2 f -3 d 8661 d 173 b 3
context-tags: delivery, directmailcontent, back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b0cf437ec97153b53bd4502171b24286abb25731

---


# Creating the direct mail{#creating-the-direct-mail}

La creación de una entrega de correo directa es muy similar a la creación de un correo electrónico normal. Los pasos siguientes describen la configuración específica de este canal. Refer to [Creating an email](../../channels/using/creating-an-email.md) for more information on other options.

1. Cree una nueva entrega de correo directo. You can create one from the Adobe Campaign [home page](../../start/using/interface-description.md#home-page), in a [campaign](../../start/using/marketing-activities.md#creating-a-marketing-activity) or in a [marketing activity list](../../start/using/programs-and-campaigns.md#creating-a-campaign).

   >[!NOTE]
   >
   >También puede agregar una actividad de correo directo en un flujo de trabajo. For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Choose either the out-of-the-box **[!UICONTROL Direct mail]** template or one of your own templates. For more information on templates, refer to the [Managing templates](../../start/using/about-templates.md) section.

   ![](assets/direct_mail_2.png)

1. Introduzca las propiedades generales del envío.

   ![](assets/direct_mail_3.png)

1. Defina la audiencia que desee incluir en el archivo de extracción, así como los perfiles de prueba y de reventado. See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >La definición de audiencia es muy similar a definir una audiencia de correo electrónico normal. See [Creating audiences](../../audiences/using/creating-audiences.md).

1. Edite el contenido del archivo: columnas que incluir para cada perfil, estructura de archivos, encabezado y pie de página. See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Click on the **[!UICONTROL Schedule]** section of the delivery dashboard to define the contact date. Para el correo directo, la fecha de contacto es obligatoria. For more information, refer to [Scheduling the send](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. If you added test profiles (refer to [Adding test and trap profiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)), you can test your delivery before preparing the final file. Permite crear un archivo de muestra que contiene únicamente los perfiles de prueba seleccionados.

   Click on **[!UICONTROL Test]** to generate the sample file. Click on **[!UICONTROL Summary]**, in the top left corner, then select **[!UICONTROL Proofs]**. On the left part of the screen, select the proof and click on **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >The **[!UICONTROL Export]** role is required to allow Adobe Campaign to export the file and make it available for download. Comuníquese con el administrador.

   ![](assets/direct_mail_19.png)

1. Once you have defined your delivery content, audience and contact date, click on the **[!UICONTROL Prepare]** button, on the delivery dashboard.

   ![](assets/direct_mail_16.png)

   Se aplican reglas de tipología. Por ejemplo, todas las direcciones postales no especificadas se excluyen del objetivo. This is why you need to make sure you have checked the **[!UICONTROL Address specified]** box in your profiles' information (see [Recommendations](../../channels/using/about-direct-mail.md#recommendations)). If you have defined a **[!UICONTROL Maximum volume of message]** in the direct mail properties or at the template level, it will also be applied here.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Puede establecer reglas globales de fatiga de canales múltiples que excluyan automáticamente perfiles sobresoltados de las campañas. See [Fatigue rules](../../administration/using/fatigue-rules.md).

1. Click on **[!UICONTROL Explore file]** to preview the first 100 lines of the file.

   ![](assets/direct_mail_18.png)

   El archivo completo es accesible para la descarga local en la parte izquierda de la pantalla. Downloading the file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

   >[!NOTE]
   >
   >The **[!UICONTROL Export]** role is required to allow Adobe Campaign to export the file and make it available for download. Comuníquese con el administrador.

   If you need to change the delivery content, you only have to click on the **[!UICONTROL Regenerate file]** button to take the change into account. No es necesario volver a realizar la preparación.

   ![](assets/direct_mail_21.png)

1. To confirm that the file is final, click on **[!UICONTROL Confirm]** in the delivery dashboard.

   ![](assets/direct_mail_20.png)

Ya está listo para enviar el archivo de extracción a su proveedor de correo directo. Para ello, tiene varias opciones:

* Enviarla a través de un correo electrónico normal, con el archivo adjunto
* Send it via Campaign: perform your direct mail within a campaign [workflow](../../automating/using/direct-mail-delivery.md) and add a **[!UICONTROL Transfer file]** to send the file via FTP for example. See [Transfer file](../../automating/using/transfer-file.md).

El proveedor recupera la lista de direcciones erróneas y envía esta información a Adobe Campaign, la cual automáticamente muestra las direcciones erróneas. See [Return to sender](../../channels/using/return-to-sender.md).
