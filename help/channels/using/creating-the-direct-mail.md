---
title: Creación del correo postal
description: Siga estos pasos para crear una entrega de correo directo en Adobe Campaign.
page-status-flag: never-activated
uuid: 3b1365c4-4ea1-4434-818b-05ff0c9b42c1
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: direct-mail
discoiquuid: 5b02227f-9438-4001-bc2f-3d8661d173b3
context-tags: delivery,directMailContent,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Creación del correo postal{#creating-the-direct-mail}

La creación de una entrega directa de correo es muy similar a la creación de un correo electrónico normal. Los pasos siguientes describen la configuración específica de este canal. Consulte [Creación de un correo electrónico](../../channels/using/creating-an-email.md) para obtener más información sobre otras opciones.

1. Cree una nueva entrega de correo directo. Puede crear una desde la página [de](../../start/using/interface-description.md#home-page)inicio de Adobe Campaign, en una [campaña](../../start/using/marketing-activities.md#creating-a-marketing-activity) o en una lista [de actividades de](../../start/using/programs-and-campaigns.md#creating-a-campaign)marketing.

   >[!NOTE]
   >
   >También puede agregar una actividad de correo directo en un flujo de trabajo. For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Elija la plantilla lista para usar **[!UICONTROL Direct mail]**o una de sus propias plantillas. Para obtener más información sobre las plantillas, consulte la sección[Administración de plantillas](../../start/using/marketing-activity-templates.md).

   ![](assets/direct_mail_2.png)

1. Introduzca las propiedades generales de la entrega.

   ![](assets/direct_mail_3.png)

1. Defina la audiencia que desea incluir en el archivo de extracción, así como los perfiles de prueba y captura. See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >La definición de audiencia es muy similar a definir una audiencia de correo electrónico normal. Consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).

1. Edite el contenido del archivo: para incluir para cada perfil, estructura de archivos, encabezado y pie de página. See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Haga clic en la **[!UICONTROL Schedule]**sección del tablero de envío para definir la fecha de contacto. Para el correo directo, la fecha de contacto es obligatoria. Para obtener más información, consulte[Programación del envío](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Si ha agregado perfiles de prueba (consulte [Adición de perfiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)de prueba y captura), puede probar la entrega antes de preparar el archivo final. Le permite crear un archivo de muestra que contenga únicamente los perfiles de prueba seleccionados.

   Haga clic en **[!UICONTROL Test]**para generar el archivo de muestra. Haga clic en**[!UICONTROL Summary]**, en la esquina superior izquierda, luego seleccione **[!UICONTROL Proofs]**. En la parte izquierda de la pantalla, seleccione la prueba y haga clic en**[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >La función **[!UICONTROL Export]**es necesaria para permitir que Adobe Campaign exporte el archivo y lo haga disponible para su descarga. Póngase en contacto con el administrador.

   ![](assets/direct_mail_19.png)

1. Una vez definido el contenido de la entrega, la audiencia y la fecha de contacto, haga clic en el **[!UICONTROL Prepare]**botón del tablero de envío.

   ![](assets/direct_mail_16.png)

   Se aplican las reglas de tipología. Por ejemplo, todas las direcciones postales no especificadas se excluyen del destino. Por este motivo, debe asegurarse de haber marcado la **[!UICONTROL Address specified]**casilla en la información de sus perfiles (consulte[Recomendaciones](../../channels/using/about-direct-mail.md#recommendations)). Si ha definido un**[!UICONTROL Maximum volume of message]** en las propiedades de correo directo o en el nivel de plantilla, también se aplicará aquí.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Puede establecer reglas de fatiga globales entre canales que excluyan automáticamente perfiles superpuestos de las campañas. Consulte Reglas [de fatiga](../../administration/using/fatigue-rules.md).

1. Haga clic en **[!UICONTROL Explore file]**para obtener una vista previa de las primeras 100 líneas del archivo.

   ![](assets/direct_mail_18.png)

   Se puede acceder al archivo completo para la descarga local en la parte izquierda de la pantalla. Al descargar el archivo, se genera una entrada de registro en el **[!UICONTROL Export audits]**menú. Para obtener más información sobre las auditorías de exportación, consulte la sección[Auditoría de exportaciones](../../administration/using/auditing-export-logs.md).

   >[!NOTE]
   >
   >La función **[!UICONTROL Export]**es necesaria para permitir que Adobe Campaign exporte el archivo y lo haga disponible para su descarga. Póngase en contacto con el administrador.

   Si necesita cambiar el contenido de la entrega, solo tiene que hacer clic en el **[!UICONTROL Regenerate file]**botón para tener en cuenta el cambio. No hay necesidad de volver a pasar por la preparación.

   ![](assets/direct_mail_21.png)

1. Para confirmar que el archivo es final, haga clic en **[!UICONTROL Confirm]**en el panel de envío.

   ![](assets/direct_mail_20.png)

Ya está listo para enviar el archivo de extracción a su proveedor de correo directo. Para ello, tiene varias opciones:

* Enviarlo por correo electrónico regular, con el archivo adjunto
* Envíelo mediante campaña: realice el correo directo dentro de un [flujo de trabajo](../../automating/using/direct-mail-delivery.md) de campaña y agregue un **[!UICONTROL Transfer file]**para enviar el archivo por FTP, por ejemplo. Consulte[Transferir archivo](../../automating/using/transfer-file.md).

El proveedor recupera la lista de direcciones erróneas y envía esta información a Adobe Campaign, que automáticamente pone en negro las direcciones erróneas. See [Return to sender](../../channels/using/return-to-sender.md).
