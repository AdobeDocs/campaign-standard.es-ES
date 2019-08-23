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
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Creación de una notificación push multilingües{#creating-a-multilingual-push-notification}

## Acerca de la notificación Push multilingües {#about-multilingual-push-notification}

Personalice el contenido de notificaciones Push enviando mensajes basados en los idiomas y las regiones preferidos de los usuarios. Puede importar directamente variantes de contenido de notificaciones push multilingües en el editor de contenido y enviar una notificación push multilingües en una sola entrega.

Esta función aprovecha los idiomas preferidos especificados en los perfiles de los destinatarios o en las preferencias de idioma del sistema para los suscriptores de aplicaciones móviles, según la plantilla de envío utilizada para la notificación push. Si la preferencia de idioma no está completa para un usuario determinado, el sistema utilizará la variante predeterminada que se define al crear una notificación push multilingües. Para obtener más información sobre cómo administrar los perfiles y los suscriptores, consulte esta [guía](../../audiences/using/about-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para utilizar variantes de contenido multilingües para la entrega de notificaciones Push, siga estos pasos:

* [Paso 1: Cargar variante de contenido multilingüe](../../channels/using/creating-a-multilingual-push-notification.md#step-1--upload-multilingual-content-variant)
* [Paso 2: Vista previa y finalización de una notificación Push mediante variantes de contenido multilingües](../../channels/using/creating-a-multilingual-push-notification.md#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Paso 3: Enviar y analizar el envío de notificaciones push multilingües](../../channels/using/creating-a-multilingual-push-notification.md#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Paso 1: Cargar variante de contenido multilingüe {#step-1--upload-multilingual-content-variant}

Antes de personalizar la notificación push multilingües, primero es necesario cargar las variantes de contenido en una plantilla de envío multilingüe y crear la entrega.

>[!NOTE]
>
>También puede omitir este paso si desea crear una variante manualmente para cada variante de idioma.

1. En **[!UICONTROL Marketing activities]**, haga clic en **[!UICONTROL Create]** el botón y seleccione **[!UICONTROL Push notification]**.
1. Seleccione la plantilla **[!UICONTROL Send multilingual push to Campaign profiles]** si desea dirigirse a los perfiles de Adobe Campaign que se han suscrito a la aplicación móvil o a la plantilla **[!UICONTROL Send multilingual push to app subscriber]** para enviar una notificación push a todos los usuarios que hayan elegido recibir notificaciones desde su aplicación móvil.

   ![](assets/multivariant_push_2.png)

1. Introduzca las propiedades de notificaciones push y seleccione su aplicación móvil en **[!UICONTROL Associate a Mobile App to a delivery]** el campo.

   Tenga en cuenta que el menú desplegable mostrará las aplicaciones SDK V 4 y Adobe Experience Platform SDK.

1. En **[!UICONTROL Audiences]** las ventanas, arrastre y suelte las consultas para ajustar la audiencia.

   Las consultas agregadas dependen de la plantilla elegida: si elige **[!UICONTROL Send multilingual push to Campaign profiles]** la plantilla, puede consultar a los destinatarios conocidos de su aplicación móvil. Si elige la **[!UICONTROL Send multilingual push to app subscriber]** plantilla, puede consultar a todos los suscriptores de una aplicación en particular que hayan elegido.

   ![](assets/push_notif_audience.png)

1. En **[!UICONTROL Manage Content Variants]** la ventana, arrastre y suelte el archivo o seleccione un archivo del equipo.

   El archivo debe estar codificado en UTF 8 y debe tener un diseño específico que se pueda encontrar haciendo clic en la **[!UICONTROL Download the sample file]** opción. También debe utilizar la sintaxis correcta para los valores de configuración regional. Para obtener más información sobre el formato de archivo y las configuraciones regionales admitidas, consulte esta [nota técnica](http://helpx.adobe.com/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Después de cargar el archivo, las variantes de idioma se rellenan automáticamente en **[!UICONTROL Variants]** la ficha. Tenga en cuenta que puede proporcionar **[!UICONTROL Default variant]** un archivo en el archivo que será su variante de contenido predeterminada si no se especifica ningún idioma preferido para el usuario objetivo.

   ![](assets/multivariant_push_5.png)

1. La **[!UICONTROL Variant selection]** ficha proporciona una secuencia de comandos para determinar qué preferencia de idioma debe tener en cuenta en función de la plantilla de entrega. Esta es una secuencia de comandos lista para usar que no requiere que realice ningún cambio.
1. Si desea agregar más variantes no presentes en el archivo importado, haga clic en **[!UICONTROL Add an element]** el botón y agregue tantas variantes de idioma nuevas como sea necesario.

   Al agregar variantes distintas a las cargadas desde el archivo, no se vinculará contenido a este idioma. Tendrá que editar el contenido directamente en el tablero de entrega.

   ![](assets/multivariant_push_6.png)

1. Haga clic **[!UICONTROL Create]** en cuando se realice la configuración. Siempre puede regresar a **[!UICONTROL Content variant]** la ventana y realizar algunos cambios desde el tablero de envío.

   ![](assets/multivariant_push_8.png)

Ahora puede empezar a personalizar la notificación push multilingüe.

## Paso 2: Vista previa y finalización de una notificación Push mediante variantes de contenido multilingües {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Después de cargar el archivo con variantes de contenido, ahora puede obtener una vista previa de las distintas variantes de su envío de notificaciones Push.

También es posible crear y editar más variantes además de las cargadas desde el archivo.

1. En **[!UICONTROL Content]** la ventana del tablero de envío, la lista desplegable permite obtener una vista previa del contenido de la notificación push según el idioma elegido.

   ![](assets/multivariant_push_7.png)

1. Si no se especifica una variante de contenido para un idioma concreto, haga clic en el icono de campana debajo de la vista previa para empezar a agregar contenido a esta variante de idioma.

   Al hacer clic en **[!UICONTROL Content]** la ventana, la notificación Push representa el contenido del idioma seleccionado en la lista desplegable. Los cambios realizados en esta ventana solo afectarán a un idioma.

1. También puede hacer clic en una variante de contenido para personalizarla aún más por ejemplo con campos de personalización.

   Para obtener más información sobre cómo personalizar la notificación Push, consulte esta [sección](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Haga clic en **[!UICONTROL Content variant]** la ventana si desea agregar o eliminar variantes de idioma.

   Tenga en cuenta que, al agregar un idioma nuevo, deberá agregar contenido manualmente a la notificación push vinculada al idioma agregado.

   ![](assets/multivariant_push_10.png)

La entrega de notificaciones push multilingües está lista para enviarse.

## Paso 3: Enviar y analizar el envío de notificaciones push multilingües {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Las notificaciones push de contenido multilingüe de contenido están listas para enviarse a los usuarios.

1. Para comenzar a preparar el envío, haga clic en **[!UICONTROL Prepare]** el botón.
1. Cuando la preparación termina sin advertencias, puede hacer clic en **[!UICONTROL Confirm]** el botón para comenzar a enviar push multilingüe.

   ![](assets/multivariant_push_12.png)

1. Después de enviar correctamente la notificación Push, haga clic en **[!UICONTROL Reports]** el icono para **[!UICONTROL Dynamic reports]** analizar el éxito de la entrega.

   ![](assets/multivariant_push_13.png)

1. Seleccione **[!UICONTROL Push notification report]**.
1. Arrastre y suelte **[!UICONTROL Variant]** la dimensión en el panel para comenzar a filtrar los datos.

   ![](assets/multivariant_push_11.png)

Ahora puede medir el impacto de su envío de notificaciones push multilingües en sus destinatarios.

**Temas relacionados:**

* [Informe de notificaciones Push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación Push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)
* [Obtención de audiencias multilingües mediante un flujo de trabajo](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
