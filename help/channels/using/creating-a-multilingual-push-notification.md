---
solution: Campaign Standard
product: campaign
title: Creación de una notificación push multilingüe
description: Cree notificaciones push multilingües para destinatario a los usuarios en sus idiomas y regiones preferidos.
audience: channels
content-type: reference
topic-tags: push-notifications
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '920'
ht-degree: 3%

---


# Creación de una notificación push multilingüe{#creating-a-multilingual-push-notification}

## Acerca de la notificación push multilingüe {#about-multilingual-push-notification}

Personalice el contenido de las notificaciones push enviando mensajes en función de los idiomas y regiones preferidos de los usuarios. Puede importar directamente variantes de contenido de notificaciones push multilingües en el editor de contenido y enviar una notificación push multilingüe en un solo envío.

Esta función aprovecha los idiomas preferidos especificados en los perfiles de destinatarios o la preferencia de idioma del sistema para los suscriptores de aplicaciones móviles, según la Plantilla de envíos utilizada para la notificación push. Si no se rellena la preferencia de idioma para un usuario determinado, el sistema utilizará la variante predeterminada que se define al crear una notificación push multilingüe. Para obtener más información sobre cómo administrar sus perfiles y suscriptores, consulte esta [guía](../../audiences/using/get-started-profiles-and-audiences.md).

![](assets/multivariant_push_1.png)

Para utilizar variantes de contenido multilingüe en el envío de notificaciones Push, siga estos pasos:

* [Paso 1: Cargar variante de contenido multilingüe](#step-1--upload-multilingual-content-variant)
* [Paso 2: Previsualización y finalización de una notificación push mediante variantes de contenido multilingüe](#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants)
* [Paso 3: Enviar y analizar envíos de notificaciones push multilingües](#step-3--send-and-analyze-multilingual-push-notification-delivery)

## Paso 1: Cargar variante de contenido multilingüe {#step-1--upload-multilingual-content-variant}

Antes de personalizar la notificación push multilingüe, primero debemos cargar las variantes de contenido en una Plantilla de envíos multilingüe y crear el envío.

>[!NOTE]
>
>También puede omitir este paso si desea crear una variante manualmente para cada variante de idioma.

1. En el **[!UICONTROL Marketing activities]**, haga clic en el **[!UICONTROL Create]** botón y seleccione **[!UICONTROL Push notification]**.
1. Seleccione la plantilla **[!UICONTROL Send multilingual push to Campaign profiles]** si desea enviar una destinatario a los perfiles de Adobe Campaign que se hayan suscrito a la aplicación móvil o a la plantilla **[!UICONTROL Send multilingual push to app subscriber]** para que envíen una notificación push a todos los usuarios que hayan adhesión para recibir notificaciones desde la aplicación móvil.

   ![](assets/multivariant_push_2.png)

1. Enter your push notification properties and select your mobile app in the **[!UICONTROL Associate a Mobile App to a delivery]** field.

   Tenga en cuenta que el menú desplegable mostrará las aplicaciones SDK V4 y SDK de Adobe Experience Platform.

1. En las **[!UICONTROL Audiences]** ventanas, arrastre y suelte las consultas para ajustar la audiencia.

   Las consultas agregadas dependen de la plantilla elegida: si elige la **[!UICONTROL Send multilingual push to Campaign profiles]** plantilla, puede consulta de destinatarios conocidos de la aplicación móvil. Mientras que si elige la **[!UICONTROL Send multilingual push to app subscriber]** plantilla, puede realizar la consulta de todos los suscriptores de una aplicación concreta que hayan adhesión.
   >[!NOTE]
   >
   >Si destinatario audiencias con idiomas específicos, debe realizar la lista de todos los idiomas objetivo en el archivo CSV.

   ![](assets/push_notif_audience.png)

1. En la **[!UICONTROL Manage Content Variants]** ventana, arrastre y suelte el archivo o seleccione un archivo del equipo.

   El archivo debe tener codificación UTF8 y un diseño específico que se puede encontrar haciendo clic en la **[!UICONTROL Download the sample file]** opción. También debe utilizar la sintaxis adecuada para los valores de configuración regional. Para obtener más información sobre el formato de archivo y las configuraciones regionales admitidas, consulte esta [nota técnica](https://helpx.adobe.com/es/campaign/kb/acs-generate-csv-multilingual-push.html).

   ![](assets/multivariant_push_4.png)

1. Después de cargar el archivo, las variantes de idioma se rellenan automáticamente en la **[!UICONTROL Variants]** ficha. Tenga en cuenta que puede proporcionar una **[!UICONTROL Default variant]** en el archivo que será su variante de contenido predeterminada si no se especifica ningún idioma preferido para el usuario de destino.

   ![](assets/multivariant_push_5.png)

1. La **[!UICONTROL Variant selection]** ficha proporciona una secuencia de comandos para determinar qué preferencia de idioma se debe tener en cuenta en función de la Plantilla de envíos. Se trata de una secuencia de comandos lista para usar que no requiere que realice ningún cambio.
1. Si desea agregar más variantes que no estén presentes en el archivo importado, puede hacerlo haciendo clic en el **[!UICONTROL Add an element]** botón y agregando tantas variantes de idioma nuevas como sea necesario.

   Al agregar variantes distintas a las cargadas desde el archivo, no se vinculará ningún contenido a este idioma. Tendrá que editar el contenido directamente en el panel de envío.

   ![](assets/multivariant_push_6.png)

1. Haga clic **[!UICONTROL Create]** cuando se haya completado la configuración. Siempre puede volver a la **[!UICONTROL Content variant]** ventana y realizar algunos cambios desde el panel de envío.

   ![](assets/multivariant_push_8.png)

Ahora puede personalizar la inicio mediante notificaciones push multilingües.

## Paso 2: Previsualización y finalización de una notificación push mediante variantes de contenido multilingüe {#step-2--preview-and-finalize-a-push-notification-using-multilingual-content-variants}

Después de cargar el archivo que contiene variantes de contenido, ahora puede realizar la previsualización de las distintas variantes desde el envío de notificaciones push.

También es posible crear y editar más variantes además de las cargadas desde el archivo.

1. En la **[!UICONTROL Content]** ventana del panel de envío, la lista desplegable le permite realizar previsualizaciones en el contenido de las notificaciones push según el idioma elegido.

   ![](assets/multivariant_push_7.png)

1. Si no se ha especificado una variante de contenido para un idioma determinado, haga clic en el icono de campana debajo de la previsualización para añadir contenido a esta variante de idioma en el inicio.

   Al hacer clic en la **[!UICONTROL Content]** ventana, la notificación push representa el contenido del idioma seleccionado en la lista desplegable. Los cambios realizados en esta ventana solo afectarán a un idioma.

1. También puede hacer clic en una variante de contenido para personalizarla aún más, por ejemplo con campos de personalización.

   For more information on how to customize your push notification, refer to this [section](../../channels/using/customizing-a-push-notification.md).

   ![](assets/multivariant_push_9.png)

1. Haga clic en la **[!UICONTROL Content variant]** ventana si desea agregar o eliminar variantes de idioma.

   Tenga en cuenta que al agregar un nuevo idioma, tendrá que agregar contenido manualmente a la notificación push vinculada al idioma agregado.

   ![](assets/multivariant_push_10.png)

El envío de notificaciones push multilingües ya está listo para enviarse.

## Paso 3: Enviar y analizar envíos de notificaciones push multilingües {#step-3--send-and-analyze-multilingual-push-notification-delivery}

Las notificaciones push de la variante de contenido multilingüe ya están listas para enviarse a los usuarios.

1. Para inicio de la preparación del envío, haga clic en el **[!UICONTROL Prepare]** botón.
1. Cuando la preparación haya terminado sin advertencias, puede hacer clic en el **[!UICONTROL Confirm]** botón para enviar el mensaje push multilingüe en inicio.

   ![](assets/multivariant_push_12.png)

1. Después de enviar correctamente la notificación push, haga clic en el **[!UICONTROL Reports]** icono y luego **[!UICONTROL Dynamic reports]** para analizar el éxito del envío.

   ![](assets/multivariant_push_13.png)

1. Seleccione **[!UICONTROL Push notification report]**.
1. Arrastre y suelte la **[!UICONTROL Variant]** dimensión en el panel para filtrar los datos en inicio.

   ![](assets/multivariant_push_11.png)

Ahora puede medir el impacto del envío de notificaciones push multilingües en sus destinatarios.

**Temas relacionados:**

* [Informe de notificaciones push](../../reporting/using/push-notification-report.md)
* [Envío de una notificación push dentro de un flujo de trabajo](../../automating/using/push-notification-delivery.md)
* [Alcance de audiencias multilingües mediante un flujo de trabajo](https://helpx.adobe.com/es/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
