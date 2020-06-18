---
title: Creación del correo postal
description: Siga estos pasos para crear un envío de correo directo en Adobe Campaign.
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
source-git-commit: 012546e109b085b7ed968bcefa8f76482656ae0d
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 1%

---


# Creación del correo postal{#creating-the-direct-mail}

Crear un envío de correo directo es muy similar a crear un correo electrónico normal. Los pasos siguientes describen la configuración específica de este canal. Consulte [Creación de un correo electrónico](../../channels/using/creating-an-email.md) para obtener más información sobre otras opciones.

1. Cree un nuevo envío de correo directo. Puede crear una desde la [página de inicio](../../start/using/interface-description.md#home-page)de Adobe Campaign, en una [campaña](../../start/using/marketing-activities.md#creating-a-marketing-activity) o en una lista [de actividad de](../../start/using/programs-and-campaigns.md#creating-a-campaign)marketing.

   >[!NOTE]
   >
   >También puede agregar una actividad de correo directo en un flujo de trabajo. For more on this, refer to the [Workflows](../../automating/using/direct-mail-delivery.md) guide.

   ![](assets/direct_mail_1.png)

1. Elija la plantilla lista para usar **[!UICONTROL Direct mail]** o una de sus propias plantillas. Para obtener más información sobre las plantillas, consulte la sección [Administración de plantillas](../../start/using/marketing-activity-templates.md) .

   ![](assets/direct_mail_2.png)

1. Introduzca las propiedades generales del envío.

   ![](assets/direct_mail_3.png)

1. Defina la audiencia que desee incluir en el archivo de extracción, así como los perfiles de prueba y captura. See [Defining the direct mail audience](../../channels/using/defining-the-direct-mail-audience.md).

   ![](assets/direct_mail_4.png)

   >[!NOTE]
   >
   >La definición de audiencia es muy similar a la definición de una audiencia de correo electrónico normal. Consulte [Creación de audiencias](../../audiences/using/creating-audiences.md).

1. Edite el contenido del archivo: para incluir para cada perfil, estructura de archivos, encabezado y pie de página. See [Defining the direct mail content](../../channels/using/defining-the-direct-mail-content.md).

   ![](assets/direct_mail_5.png)

1. Haga clic en la **[!UICONTROL Schedule]** sección del panel de envío para definir la fecha de contacto. Para el correo directo, la fecha de contacto es obligatoria. Para obtener más información, consulte [Programación del envío](../../sending/using/about-scheduling-messages.md).

   ![](assets/direct_mail_8.png)

1. Si ha agregado perfiles de prueba (consulte [Añadir perfiles](../../channels/using/defining-the-direct-mail-audience.md#adding-test-and-trap-profiles)de prueba y captura), puede probar el envío antes de preparar el archivo final. Le permite crear un archivo de muestra que contenga únicamente los perfiles de prueba seleccionados.

   Haga clic en **[!UICONTROL Test]** para generar el archivo de muestra. Haga clic en **[!UICONTROL Summary]**, en la esquina superior izquierda, luego seleccione **[!UICONTROL Proofs]**. En la parte izquierda de la pantalla, seleccione la prueba y haga clic en **[!UICONTROL Download file]**.

   >[!NOTE]
   >
   >La función **[!UICONTROL Export]** es necesaria para permitir a Adobe Campaign exportar el archivo y hacer que esté disponible para la descarga. Póngase en contacto con el administrador.

   ![](assets/direct_mail_19.png)

1. Una vez definido el contenido de su envío, la audiencia y la fecha de contacto, haga clic en el **[!UICONTROL Prepare]** botón, en el panel de envío.

   ![](assets/direct_mail_16.png)

   Se aplican Reglas de tipología. Por ejemplo, todas las direcciones postales no especificadas se excluyen del destinatario. Por este motivo, debe asegurarse de haber marcado la **[!UICONTROL Address specified]** casilla en la información de sus perfiles (consulte [Recomendaciones](../../channels/using/about-direct-mail.md#recommendations)). Si ha definido un **[!UICONTROL Maximum volume of message]** en las propiedades de correo directo o en el nivel de plantilla, también se aplicará aquí.

   ![](assets/direct_mail_25.png)

   >[!NOTE]
   >
   >Puede establecer reglas globales de fatiga entre canales que excluyan automáticamente los perfiles superpuestos de las campañas. Consulte Reglas [de fatiga](../../sending/using/fatigue-rules.md).

1. Haga clic en **[!UICONTROL Explore file]** para previsualización de las primeras 100 líneas del archivo.

   ![](assets/direct_mail_18.png)

   Se puede acceder al archivo completo para la descarga local en la parte izquierda de la pantalla. Al descargar el archivo, se genera una entrada de registro en el **[!UICONTROL Export audits]** menú. Para obtener más información sobre las auditorías de exportación, consulte la sección [Auditoría de exportaciones](../../administration/using/auditing-export-logs.md) .

   >[!NOTE]
   >
   >La función **[!UICONTROL Export]** es necesaria para permitir a Adobe Campaign exportar el archivo y hacer que esté disponible para la descarga. Póngase en contacto con el administrador.

   Si necesita cambiar el contenido de envío, solo tiene que hacer clic en el **[!UICONTROL Regenerate file]** botón para tener en cuenta el cambio. No hay necesidad de volver a pasar por la preparación.

   ![](assets/direct_mail_21.png)

1. Para confirmar que el archivo es final, haga clic en **[!UICONTROL Confirm]** en el panel de envío.

   ![](assets/direct_mail_20.png)

Ya está listo para enviar el archivo de extracción a su proveedor de correo directo. Para ello, tiene varias opciones:

* Enviarlo por correo electrónico regular, con el archivo adjunto
* Enviarlo por Campaña: realice el correo directo dentro de un [flujo de trabajo](../../automating/using/direct-mail-delivery.md) de campaña y agregue un **[!UICONTROL Transfer file]** para enviar el archivo por FTP, por ejemplo. Consulte [Transferir archivo](../../automating/using/transfer-file.md).

El proveedor recupera la lista de direcciones erróneas y envía esta información al Adobe Campaign, que automáticamente agrega a la lista de bloques las direcciones erróneas. See [Return to sender](../../channels/using/return-to-sender.md).
