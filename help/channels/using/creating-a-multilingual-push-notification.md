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
source-wordcount: '903'
ht-degree: 2%

---

# Creación de una notificación push multilingüe{#creating-a-multilingual-push-notification}

## Acerca de la notificación push multilingüe {#about-multilingual-push-notification}

Personalice el contenido de las notificaciones push enviando mensajes en función de los idiomas y regiones preferidos de los usuarios. Puede importar directamente variantes de contenido de notificaciones push multilingües en el editor de contenido y enviar una notificación push multilingüe en una única entrega.

Esta función aprovecha los idiomas preferidos especificados en los perfiles de los destinatarios o las preferencias de idioma del sistema para los suscriptores de aplicaciones móviles en función de la plantilla de envío utilizada para las notificaciones push. Si las preferencias de idioma no se rellenan para un usuario en particular, el sistema utilizará la variante predeterminada que se define al crear una notificación push multilingüe. Para obtener más información sobre cómo administrar sus perfiles y suscriptores, consulte esta [guía](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para utilizar variantes de contenido multilingüe en la entrega de notificaciones push, siga estos pasos:

* [Paso 1: Cargar variante de contenido multilingüe](#step-1--upload-multilingual-content-variant)
* [Paso 2: Vista previa y finalización de una notificación push mediante variantes de contenido multilingüe](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Paso 3: Envío y análisis de una entrega de notificaciones push multilingües](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Paso 1: Cargar variante de contenido multilingüe {#step-1--upload-multilingual-content-variant}

Antes de personalizar la notificación push multilingüe, primero debemos cargar las variantes de contenido en una plantilla de envío multilingüe y crear la entrega.

>[!NOTE]
>
>También puede omitir este paso si desea crear una variante manualmente para cada variante de idioma.

1. En el **[!UICONTROL Marketing activities]**, haga clic en **[!UICONTROL Create]** a continuación, seleccione **[!UICONTROL Push notification]**.
1. Seleccione la plantilla **[!UICONTROL Send multilingual push to Campaign profiles]** si desea dirigirse a los perfiles de Adobe Campaign que se han suscrito a su aplicación móvil o a la plantilla **[!UICONTROL Send multilingual push to app subscriber]** para enviar una notificación push a todos los usuarios que hayan elegido recibir notificaciones desde la aplicación móvil.

   ![](assets/multivariant_push_2.png)

1. Introduzca las propiedades de la notificación push y seleccione la aplicación móvil en la **[!UICONTROL Associate a Mobile App to a delivery]** campo .

   Tenga en cuenta que la lista desplegable mostrará las aplicaciones SDK V4 y SDK de Adobe Experience Platform.

1. En el **[!UICONTROL Audiences]** ventanas, arrastre y suelte las consultas para ajustar la audiencia.

   Las consultas agregadas dependen de la plantilla elegida: si elige el **[!UICONTROL Send multilingual push to Campaign profiles]** plantilla puede consultar los destinatarios conocidos de su aplicación móvil. Mientras que si elige la variable **[!UICONTROL Send multilingual push to app subscriber]** , puede consultar a todos los suscriptores de una aplicación en particular que han elegido entrar.
   >[!NOTE]
   >
   >Si segmenta audiencias con idiomas específicos, debe enumerar todos los idiomas de destino en el archivo CSV.

   ![](assets/push_notif_audience.png)

1. En el **[!UICONTROL Manage Content Variants]** , arrastre y suelte el archivo o seleccione un archivo del equipo.

   El archivo debe tener codificación UTF8 y una presentación específica que se pueda encontrar haciendo clic en la **[!UICONTROL Download the sample file]** . También debe utilizar la sintaxis adecuada para los valores de configuración regional. Para obtener más información sobre el formato de archivo y las configuraciones regionales compatibles, consulte esta [página](../../channels/using/generating-csv-multilingual-push.md).

   ![](assets/multivariant_push_4.png)

1. Después de cargar el archivo, las variantes de idioma se rellenan automáticamente en la variable **[!UICONTROL Variants]** pestaña . Tenga en cuenta que puede proporcionar una **[!UICONTROL Default variant]** en el archivo que será su variante de contenido predeterminada si no se especifica ningún idioma preferido para el usuario de destino.

   ![](assets/multivariant_push_5.png)

1. La variable **[!UICONTROL Variant selection]** proporciona una secuencia de comandos para determinar qué preferencia de idioma se debe tener en cuenta en función de la plantilla de envío. Se trata de un script listo para usar que no requiere que realice ningún cambio.
1. Si desea agregar más variantes que no estén presentes en el archivo importado, puede hacerlo haciendo clic en el botón **[!UICONTROL Add an element]** y añada tantas variantes de idioma nuevas como sea necesario.

   Al añadir variantes que no sean las cargadas desde el archivo, no se vinculará ningún contenido a este idioma. Deberá editar el contenido directamente en el panel de envío.

   ![](assets/multivariant_push_6.png)

1. Haga clic en **[!UICONTROL Create]** cuando se haya completado la configuración. Siempre puede volver a la **[!UICONTROL Content variant]** y realice algunos cambios desde el panel de envío.

   ![](assets/multivariant_push_8.png)

Ahora puede empezar a personalizar la notificación push multilingüe.

## Paso 2: Vista previa y finalización de una notificación push mediante variantes de contenido multilingüe {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Después de cargar el archivo que contiene variantes de contenido, ahora puede obtener una vista previa de las diferentes variantes de la entrega de notificaciones push.

También es posible crear y editar más variantes además de las cargadas desde el archivo.

1. En el **[!UICONTROL Content]** en el panel de entregas, la lista desplegable le permite previsualizar el contenido de las notificaciones push en función del idioma elegido.

   ![](assets/multivariant_push_7.png)

1. Si no se ha especificado una variante de contenido para un idioma en particular, haga clic en el icono de campana situado debajo de la vista previa para empezar a añadir contenido a esta variante de idioma.

   Al hacer clic en el botón **[!UICONTROL Content]** , la notificación push representa el contenido del idioma seleccionado en la lista desplegable. Los cambios realizados en esta ventana solo afectan a un idioma.

1. También puede hacer clic en una variante de contenido para personalizarla aún más, por ejemplo, con campos de personalización.

   Para obtener más información sobre cómo personalizar la notificación push, consulte esta [sección](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Haga clic en el **[!UICONTROL Content variant]** si desea añadir o eliminar variantes de idioma.

   Tenga en cuenta que al agregar un nuevo idioma, tendrá que añadir contenido manualmente a la notificación push vinculada al idioma añadido.

   ![](assets/multivariant_push_10.png)

El envío de notificaciones push multilingües ya está listo para enviarse.

## Paso 3: Envío y análisis de una entrega de notificaciones push multilingües {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Las notificaciones push de la variante de contenido multilingüe ya están listas para enviarse a los usuarios.

1. Para empezar a preparar la entrega, haga clic en el botón **[!UICONTROL Prepare]** botón.
1. Cuando finalice la preparación sin advertencias, puede hacer clic en el botón **[!UICONTROL Confirm]** para empezar a enviar la notificación push multilingüe.

   ![](assets/multivariant_push_12.png)

1. Después de enviar correctamente la notificación push, haga clic en el botón **[!UICONTROL Reports]** icono **[!UICONTROL Dynamic reports]** para analizar el éxito de su envío.

   ![](assets/multivariant_push_13.png)

1. Seleccione **[!UICONTROL Push notification report]**.
1. Arrastre y suelte la **[!UICONTROL Variant]** al panel para filtrar los datos.

   ![](assets/multivariant_push_11.png)

Ahora puede medir el impacto de la entrega de notificaciones push multilingües en los destinatarios.

**Temas relacionados:**

* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)
