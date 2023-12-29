---
title: Creación de una notificación push multilingüe
description: Cree notificaciones push multilingües para dirigirse a los usuarios en sus idiomas y regiones preferidos.
audience: channels
content-type: reference
topic-tags: push-notifications
feature: Push
role: User
level: Intermediate
exl-id: 1b81f6e9-cb31-4664-af78-22e70043fbc8
source-git-commit: b5e98c07ee55cab0b6a628a97162ccd64711501a
workflow-type: tm+mt
source-wordcount: '909'
ht-degree: 1%

---

# Creación de una notificación push multilingüe{#creating-a-multilingual-push-notification}

## Acerca de las notificaciones push multilingües {#about-multilingual-push-notification}

Personalice el contenido de las notificaciones push enviando mensajes en función de los idiomas y las regiones preferidos por los usuarios. Puede importar directamente variantes de contenido de notificaciones push multilingües en el editor de contenido y enviar una notificación push multilingüe en un solo envío.

Esta función aprovecha los idiomas preferidos especificados en los perfiles de los destinatarios o la preferencia de idioma del sistema para los suscriptores de aplicaciones móviles en función de la plantilla de envío utilizada para las notificaciones push. Si la preferencia de idioma no se rellena para un usuario en particular, el sistema utilizará la variante predeterminada definida al crear una notificación push multilingüe. Para obtener más información sobre cómo administrar los perfiles y suscriptores, consulte [guía](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para utilizar variantes de contenido multilingües para la entrega de notificaciones push, siga estos pasos:

* [Paso 1: Cargar variante de contenido multilingüe](#step-1--upload-multilingual-content-variant)
* [Paso 2: Previsualizar y finalizar una notificación push mediante variantes de contenido multilingüe](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Paso 3: Envío y análisis de notificaciones push multilingües](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Paso 1: Cargar variante de contenido multilingüe {#step-1--upload-multilingual-content-variant}

Antes de personalizar la notificación push multilingüe, primero debemos cargar las variantes de contenido en una plantilla de envío multilingüe y crear la entrega.

>[!NOTE]
>
>También puede omitir este paso si desea crear una variante manualmente para cada variante de idioma.

1. En el **[!UICONTROL Marketing activities]**, haga clic en **[!UICONTROL Create]** y luego seleccione **[!UICONTROL Push notification]**.
1. Seleccione la plantilla **[!UICONTROL Send multilingual push to Campaign profiles]** si desea dirigirse a los perfiles de Adobe Campaign que se han suscrito a la aplicación móvil o a la plantilla **[!UICONTROL Send multilingual push to app subscriber]** para enviar una notificación push a todos los usuarios que se hayan suscrito para recibir notificaciones de su aplicación móvil.

   ![](assets/multivariant_push_2.png)

1. Introduzca las propiedades de las notificaciones push y seleccione la aplicación móvil en la **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Tenga en cuenta que la lista desplegable mostrará tanto las aplicaciones de SDK V4 como las de SDK para Adobe Experience Platform.

1. En el **[!UICONTROL Audiences]** Windows, arrastre y suelte las consultas para ajustar la audiencia.

   Las consultas agregadas dependen de la plantilla elegida: si elige la **[!UICONTROL Send multilingual push to Campaign profiles]** puede consultar los destinatarios conocidos de su aplicación móvil. Mientras que si elige la **[!UICONTROL Send multilingual push to app subscriber]** , puede consultar todos los suscriptores de una aplicación concreta que hayan elegido participar.
   >[!NOTE]
   >
   >Si se dirige a audiencias con idiomas específicos, debe enumerar todos los idiomas de destino en el archivo CSV.

   ![](assets/push_notif_audience.png)

1. En el **[!UICONTROL Manage Content Variants]** , arrastre y suelte el archivo o seleccione un archivo del equipo.

   El archivo debe tener codificación UTF8 y tener un diseño específico que se pueda encontrar haciendo clic en **[!UICONTROL Download the sample file]** opción. También debe utilizar la sintaxis adecuada para los valores de configuración regional. Para obtener más información sobre el formato de archivo y las configuraciones regionales admitidas, consulte esta sección [página](../../channels/using/generating-csv-multilingual-push.md).

   ![](assets/multivariant_push_4.png)

1. Después de cargar el archivo, las variantes de idioma se rellenan automáticamente en la variable **[!UICONTROL Variants]** pestaña. Tenga en cuenta que puede proporcionar un **[!UICONTROL Default variant]** en el archivo, que será la variante de contenido predeterminada si no se especifica ningún idioma preferido para el usuario de destino.

   ![](assets/multivariant_push_5.png)

1. El **[!UICONTROL Variant selection]** proporcionará un script para determinar qué preferencia de idioma se tendrá en cuenta según la plantilla de envío. Se trata de un script listo para usar que no requiere que realice ningún cambio.
1. Si desea agregar más variantes que no están presentes en el archivo importado, puede hacerlo haciendo clic en **[!UICONTROL Add an element]** y añada tantas variantes de idioma nuevas como sea necesario.

   Al añadir variantes distintas de las cargadas desde el archivo, no se enlazará ningún contenido a este idioma. Debe editar el contenido directamente en el panel de envío.

   ![](assets/multivariant_push_6.png)

1. Clic **[!UICONTROL Create]** cuando finalice la configuración. Siempre puedes volver a la página **[!UICONTROL Content variant]** y realice algunos cambios desde el panel de envío.

   ![](assets/multivariant_push_8.png)

Ahora puede empezar a personalizar la notificación push multilingüe.

## Paso 2: Previsualizar y finalizar una notificación push mediante variantes de contenido multilingüe {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Después de cargar el archivo que contiene las variantes de contenido, ahora puede previsualizar las diferentes variantes de su envío de notificaciones push.

También es posible crear y editar más variantes además de las cargadas desde el archivo.

1. En el **[!UICONTROL Content]** en el panel de envío, la lista desplegable permite previsualizar el contenido de las notificaciones push en función del idioma elegido.

   ![](assets/multivariant_push_7.png)

1. Si no se especifica una variante de contenido para un idioma en particular, haga clic en el icono de campana debajo de la vista previa para empezar a añadir contenido a esta variante de idioma.

   Al hacer clic en **[!UICONTROL Content]** , la notificación push representa el contenido del idioma seleccionado en la lista desplegable. Los cambios realizados en esta ventana solo afectarán a un idioma.

1. También puede hacer clic en una variante de contenido para personalizarla aún más, por ejemplo, con campos de personalización.

   Para obtener más información sobre cómo personalizar las notificaciones push, consulte esta sección [sección](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Haga clic en **[!UICONTROL Content variant]** si desea añadir o eliminar variantes de idioma.

   Tenga en cuenta que al añadir un nuevo idioma, tendrá que añadir manualmente contenido a la notificación push vinculada al idioma añadido.

   ![](assets/multivariant_push_10.png)

La entrega multilingüe de notificaciones push ya está listo para enviarse.

## Paso 3: Envío y análisis de notificaciones push multilingües {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Las notificaciones push de variante de contenido multilingüe ya están listas para enviarse a los usuarios.

1. Para empezar a preparar el envío, haga clic en **[!UICONTROL Prepare]** botón.
1. Cuando finalice la preparación sin advertencias, puede hacer clic en el icono **[!UICONTROL Confirm]** para empezar a enviar la notificación push multilingüe.

   ![](assets/multivariant_push_12.png)

1. Después de enviar correctamente la notificación push, haga clic en **[!UICONTROL Reports]** icono entonces **[!UICONTROL Dynamic reports]** para analizar el éxito de su envío.

   ![](assets/multivariant_push_13.png)

1. Seleccione **[!UICONTROL Push notification report]**.
1. Arrastre y suelte el **[!UICONTROL Variant]** al panel para empezar a filtrar los datos.

   ![](assets/multivariant_push_11.png)

Ahora puede medir el impacto del envío multilingüe de notificaciones push en los destinatarios.

**Temas relacionados:**

* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)
