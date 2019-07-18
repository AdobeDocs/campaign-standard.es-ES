---
title: Creación de una notificación push multilingües
seo-title: Creación de una notificación push multilingües
description: Creación de una notificación push multilingües
seo-description: Cree notificaciones push multilingües para dirigirse a los usuarios en sus idiomas y regiones preferidos.
page-status-flag: no activado nunca
uuid: d 4 aff 741-e 969-47 c 6-bae 8-787 c 6 c 673191
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: notificaciones push
discoiquuid: f 9 bb 2235-d 388-4025-9 ace -734 beb 0 c 1961
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6df0e764750a31f29d6fe3ec4d92e19b3f07f728

---


# Creating a multilingual push notification{#creating-a-multilingual-push-notification}

## About multilingual push notification {#about-multilingual-push-notification}

Personalice el contenido de notificaciones Push enviando mensajes basados en los idiomas y las regiones preferidos de los usuarios. Puede importar directamente variantes de contenido de notificaciones push multilingües en el editor de contenido y enviar una notificación push multilingües en una sola entrega.

Esta función aprovecha los idiomas preferidos especificados en los perfiles de los destinatarios o en las preferencias de idioma del sistema para los suscriptores de aplicaciones móviles, según la plantilla de envío utilizada para la notificación push. Si la preferencia de idioma no está completa para un usuario determinado, el sistema utilizará la variante predeterminada que se define al crear una notificación push multilingües. For more information on how to manage your profiles and subscribers, refer to this [guide](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para utilizar variantes de contenido multilingües para la entrega de notificaciones Push, siga estos pasos:

* [Paso 1: Cargar variante de contenido multilingüe](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [Paso 2: Vista previa y finalización de una notificación Push mediante variantes de contenido multilingües](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Paso 3: Enviar y analizar el envío de notificaciones push multilingües](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Step 1: Upload multilingual content variant {#step-1--upload-multilingual-content-variant}

Antes de personalizar la notificación push multilingües, primero es necesario cargar las variantes de contenido en una plantilla de envío multilingüe y crear la entrega.

>[!NOTE]
>
>También puede omitir este paso si desea crear una variante manualmente para cada variante de idioma.

1. In the **[!UICONTROL Marketing activities]**, click the **[!UICONTROL Create]** button then select **[!UICONTROL Push notification]**.
1. Select the template **[!UICONTROL Send multilingual push to Campaign profiles]** if you want to target the Adobe Campaign profiles who have subscribed to your mobile application or the template **[!UICONTROL Send multilingual push to app subscriber]** to send a push notification to all users who have opted in to receive notifications from your mobile application.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Tenga en cuenta que el menú desplegable mostrará las aplicaciones SDK V 4 y Adobe Experience Platform SDK.

1. In the **[!UICONTROL Audiences]** windows, drag and drop queries to fine tune your audience.

   The queries added depend on the chosen template: if you chose the **[!UICONTROL Send multilingual push to Campaign profiles]** template you can query known recipients of your mobile application. Whereas if you chose the **[!UICONTROL Send multilingual push to app subscriber]** template, you can query all subscribers of a particular app who have opted in.

   ![](assets/push_notif_audience.png)

1. In the **[!UICONTROL Manage Content Variants]** window, drag and drop your file or select a file from your computer.

   The file has to be UTF8 encoded and must have a specific layout which can be found by clicking the **[!UICONTROL Download the sample file]** option. También debe utilizar la sintaxis correcta para los valores de configuración regional. For more information regarding the file format and the supported locales, refer to this [technote](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. After uploading your file, the language variants are automatically populated in the **[!UICONTROL Variants]** tab. Note that you can provide a **[!UICONTROL Default variant]** in the file which will be your default content variant if no preferred language is specified for the targeted user.

   ![](assets/multivariant_push_5.png)

1. The **[!UICONTROL Variant selection]** tab will provide a script to determine which language preference to take into account depending on the delivery template. Esta es una secuencia de comandos lista para usar que no requiere que realice ningún cambio.
1. If you want to add more variants not present in the imported file, you can do so by clicking the **[!UICONTROL Add an element]** button and add as many new language variants as needed.

   Al agregar variantes distintas a las cargadas desde el archivo, no se vinculará contenido a este idioma. Tendrá que editar el contenido directamente en el tablero de entrega.

   ![](assets/multivariant_push_6.png)

1. Click **[!UICONTROL Create]** when the configuration is done. You can always come back to the **[!UICONTROL Content variant]** window and make some changes from your delivery dashboard.

   ![](assets/multivariant_push_8.png)

Ahora puede empezar a personalizar la notificación push multilingüe.

## Step 2: Preview and finalize a push notification using multilingual content variants {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Después de cargar el archivo con variantes de contenido, ahora puede obtener una vista previa de las distintas variantes de su envío de notificaciones Push.

También es posible crear y editar más variantes además de las cargadas desde el archivo.

1. In the **[!UICONTROL Content]** window from the delivery dashboard, the drop-down allows you to preview your push notification content depending on the chosen language.

   ![](assets/multivariant_push_7.png)

1. Si no se especifica una variante de contenido para un idioma concreto, haga clic en el icono de campana debajo de la vista previa para empezar a agregar contenido a esta variante de idioma.

   By clicking the **[!UICONTROL Content]** window, the push notification represents the content from the language selected in the drop down. Los cambios realizados en esta ventana solo afectarán a un idioma.

1. También puede hacer clic en una variante de contenido para personalizarla aún más por ejemplo con campos de personalización.

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Click the **[!UICONTROL Content variant]** window if you want to add or delete language variants.

   Tenga en cuenta que, al agregar un idioma nuevo, deberá agregar contenido manualmente a la notificación push vinculada al idioma agregado.

   ![](assets/multivariant_push_10.png)

La entrega de notificaciones push multilingües está lista para enviarse.

## Step 3: Send and analyze multilingual push notification delivery {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Las notificaciones push de contenido multilingüe de contenido están listas para enviarse a los usuarios.

1. To start preparing the send, click the **[!UICONTROL Prepare]** button.
1. When the preparation is finished with no warnings, you can click the **[!UICONTROL Confirm]** button to start sending your multilingual push.

   ![](assets/multivariant_push_12.png)

1. After successfully sending your push notification, click the **[!UICONTROL Reports]** icon then **[!UICONTROL Dynamic reports]** to analyze the success of your delivery.

   ![](assets/multivariant_push_13.png)

1. Select **[!UICONTROL Push notification report]**.
1. Drag and drop the **[!UICONTROL Variant]** dimension to your panel to start filtering your data.

   ![](assets/multivariant_push_11.png)

Ahora puede medir el impacto de su envío de notificaciones push multilingües en sus destinatarios.

**Temas relacionados:**

* [Informe de notificaciones Push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación Push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)

