---
title: Migración de la aplicación móvil SDK v4 al SDK de Adobe Experience Platform
description: Este documento le permite migrar su aplicación móvil del SDK v4 al SDK para Adobe Experience Platform
audience: channels
content-type: reference
topic-tags: push-notifications
context-tags: mobileApp,overview
feature: Instance Settings
role: Admin
level: Experienced
exl-id: eb7a209e-069e-4068-966d-05344bd838c7
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '1202'
ht-degree: 1%

---

# Migración de la aplicación móvil del SDK v4 al SDK de Adobe Experience Platform {#sdkv4-migration}

>[!IMPORTANT]
>
> El proceso de migración es irreversible.
>
> Lea detenidamente el documento antes de iniciar la migración de la aplicación móvil SDK V4 al SDK para Adobe Experience Platform.

## Acerca de la migración del SDK V4

Adobe Campaign Standard procesa las aplicaciones móviles mediante el SDK V4 como aplicaciones independientes de las que utilizan el SDK de Adobe Experience Platform.
Después de actualizar la versión del SDK de Adobe de 4 a Adobe Experience Platform, las aplicaciones móviles deben seguir utilizando los datos y campañas del suscriptor de la aplicación existente: por lo tanto, es necesaria una migración.

>[!NOTE]
>
> Esta página documenta la migración de una aplicación móvil SDK v4 a una aplicación SDK para Adobe Experience Platform recién creada. Las aplicaciones móviles SDK v4 no se combinarán con una aplicación móvil del SDK de Adobe Experience Platform con **[!UICONTROL Configured]** **[!UICONTROL Property status]**.

| Qué no cambiará después de la migración |
|:-:|
| No habrá ningún efecto en los envíos y campañas existentes que utilicen la aplicación V4 del SDK migrado. |
| El nombre de la aplicación móvil seguirá siendo el mismo. |
| Se conservarán las credenciales de la plataforma para iOS y Android. |
| Se conservarán todos los suscriptores de la aplicación y sus datos. |
| La aplicación móvil v4 del SDK existente seguirá enviando datos (datos PII, información del suscriptor y del token) a Adobe Campaign Standard. |
| El **[!UICONTROL Organizational unit]** de la aplicación móvil seguirá siendo el mismo. |

| Qué cambiará después de la migración |
|:-:|
| La aplicación móvil estará disponible en **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**. Antes de la migración, estaba disponible en **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**. |
| El **[!UICONTROL Collect PII Endpoint]** de la aplicación cambiará. El **[!UICONTROL Collect PII Endpoint]** anterior seguirá funcionando, los datos enviados no se perderán. |
| La aplicación se asociará a un Adobe Experience Platform Launch **[!UICONTROL Mobile Property]**. Se procesará como una aplicación móvil recién creada. |
| La aplicación de SDK de Adobe Experience Platform original utilizada en la migración no existe como aplicación independiente. Solo estará disponible la aplicación SDK v4 migrada. |

## Migración de la aplicación móvil del SDK v4 al SDK para Adobe Experience Platform {#how-to-migrate}

Antes de migrar, debe tener en cuenta las siguientes recomendaciones:

* El proceso de migración es irreversible.
* No debe ejecutar la migración de varias aplicaciones al mismo tiempo. También debe asegurarse de que la migración de una misma aplicación no se active por varias ventanas al mismo tiempo.
* Antes de la migración, asegúrese de que tiene asignado el **[!UICONTROL Organizational unit]** de la aplicación móvil que desea migrar y de la aplicación de Adobe Experience Platform que está utilizando para la migración.
* Después de la migración, la aplicación se convertirá en una aplicación de SDK para Adobe Experience Platform. Sus cambios se vincularán a su correspondiente Launch **[!UICONTROL Mobile Property]**.

1. Cree un nuevo **[!UICONTROL Mobile property]** en Adobe Experience Platform Launch. Para obtener más información, consulte [Documentación de Adobe Experience Platform Launch](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property#create-a-mobile-property).

1. En Adobe Campaign Standard, en el menú avanzado, seleccione **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Workflows]** y abra el flujo de trabajo **[!UICONTROL syncWithLaunch]**. Compruebe si el flujo de trabajo ha finalizado sin errores.

1. Una vez finalizado el flujo de trabajo, en el menú **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]** , compruebe si la aplicación móvil está disponible en Adobe Campaign Standard y está en estado **[!UICONTROL Ready to Configure]** .

   ![](assets/aep_v4_2.png)

1. En **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (SDK V4)]**, seleccione la aplicación SDK V4 que desea migrar.

1. Seleccione la pestaña **[!UICONTROL Mobile application migration to AEP SDK]** .

   ![](assets/aep_v4_3.png)

1. En la lista desplegable **[!UICONTROL Select AEP SDK mobile application to merge current application with]**, seleccione la aplicación móvil del SDK de Adobe Experience Platform creada anteriormente.

1. Haga clic en **[!UICONTROL Migrate]**.

   ![](assets/aep_v4_4.png)

1. En la ventana **[!UICONTROL Migration application]**, haga clic en **[!UICONTROL Ok]**.

   ![](assets/aep_v4_5.png)

1. Aparece la ventana de finalización correcta, haga clic en **[!UICONTROL Go to Adobe Experience Platform SDK Channel list]**.

1. En la página de la lista de canales del SDK para Adobe Experience Platform, compruebe que la aplicación móvil V4 anterior esté configurada como **[!UICONTROL Ready To Configure]**.

1. Seleccione la aplicación móvil y haga clic en **[!UICONTROL Save]** para completar la migración.

Después de esta migración, los suscriptores recopilados por la versión V4 de la aplicación móvil y los nuevos suscriptores recopilados por la versión AEP de la aplicación móvil estarán disponibles en la aplicación migrada.

Para distinguir los dos tipos diferentes de suscriptores, puede agregar un nuevo campo personalizado de tipo **[!UICONTROL Text]** al ampliar el recurso personalizado **[!UICONTROL Subscriptions to an application (appSubscriptionRcp)]** como `sdkversion` o `appVersion` por ejemplo. Para obtener más información sobre cómo ampliar un recurso personalizado, consulte esta [página](../../developing/using/creating-or-extending-the-resource.md).
A continuación, debe configurar el Launch **[!UICONTROL Mobile property]** asociado para enviar este valor de campo personalizado en la llamada a Collect PII y cambiar la configuración de la aplicación móvil en consecuencia.

## Preguntas frecuentes {#faq}

### P: En la aplicación móvil SDK v4, la migración de la aplicación móvil a la pestaña SDK de Adobe Experience Platform no está visible. {#tab-not-visible}

A: En el menú avanzado **[!UICONTROL Administration]** > **[!UICONTROL Application Settings]** > **[!UICONTROL Options]**, compruebe el valor de la opción **[!UICONTROL Enable migration of mobile app from SDK v4 to Adobe Experience Platform SDK option]**. Debe estar establecido en 1 y habilitado de forma predeterminada. Es posible que el administrador lo haya deshabilitado manualmente.

![](assets/aep_v4_1.png)

### P: Desde la pestaña Mobile application migration to Adobe Experience Platform SDK , aparece el mensaje No data . {#no-data}

A: En la lista solo se muestra la aplicación apta de su **[!UICONTROL Organizational unit]**. Asegúrese de que tiene la aplicación de Adobe Experience Platform correcta para la migración. El **[!UICONTROL Property Status]** de la aplicación de Adobe Experience Platform debe establecerse en **[!UICONTROL Ready to Configure]** y el **[!UICONTROL Mobile app migration status]** en **[!UICONTROL Not Migrated]**.

![](assets/aep_v4_6.png)

### P: ¿Por qué no se puede utilizar para la migración la aplicación SDK de Adobe Experience Platform con el estado de propiedad configurado? {#property-status}

A: El proceso de migración conserva los suscriptores y atributos de SDK v4. Solo conserva la información relacionada con Launch desde la aplicación SDK de Adobe Experience Platform. Se perderán los suscriptores y otros datos de la aplicación de SDK para Adobe Experience Platform. Para evitar la pérdida de datos, solo las aplicaciones de SDK de Adobe Experience Platform con **[!UICONTROL Ready to Configure]** **[!UICONTROL Property Status]** son elegibles para la migración.

### P: Después de la migración, ¿dónde puedo encontrar mi aplicación móvil v4 SDK anterior? {#v4-app-not-visible}

A: La aplicación móvil después de la migración será visible desde el menú avanzado **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Mobile app (Adobe Experience Platform SDK)]**.

### P: Después de la migración, ¿dónde puedo encontrar la aplicación de SDK para Adobe Experience Platform recién creada? {#aep-not-visible}

A: La aplicación de SDK de Adobe Experience Platform recién creada que se utiliza para la migración no existe como aplicación independiente. Solo estará disponible la aplicación SDK v4 migrada.

### P: Si la unidad organizativa de la aplicación móvil SDK v4 está establecida en A (un elemento secundario de la unidad organizativa ALL) y el SDK de Adobe Experience Platform está establecido en ALL. ¿Cómo puedo migrar mi aplicación móvil? {#v4-org-unit}

A: Los administradores de **[!UICONTROL Organizational unit]** ALL tendrán los derechos para administrar ambas aplicaciones móviles y estarán a cargo de la migración.

### P: Si la unidad organizativa de la aplicación móvil SDK v4 está definida en A y la aplicación del SDK de Adobe Experience Platform en B (elemento del mismo nivel que la unidad organizativa A). ¿Cómo puedo migrar mi aplicación móvil? {#aep-org-unit}

A: Si la aplicación del SDK de Adobe Experience Platform es el recurso de un **[!UICONTROL Organizational unit]** hermano, la aplicación móvil no será visible para los usuarios del **[!UICONTROL Organizational unit]** A. La aplicación móvil estará disponible para los administradores del **[!UICONTROL Organizational unit]** ALL, pero no se recomienda que estos administradores migren la aplicación móvil.
En este caso, debe mover las aplicaciones móviles en el mismo **[!UICONTROL Organizational unit]** o en un **[!UICONTROL Organizational unit]** con un vínculo principal.
Para obtener más información sobre **[!UICONTROL Organizational unit]**, consulte esta [sección](../../administration/using/organizational-units.md).

### P: En la página de la aplicación móvil del SDK de Adobe Experience Platform (migrada desde la aplicación móvil v4), en la lista desplegable de configuración de canal push , no se muestra información como la fecha y el nombre cargados para la clave de Android o el certificado iOS {#no-information-v5}

A: El sistema no almacena esta información cuando se crea la aplicación móvil SDK V4. Al migrar la aplicación móvil SDK V4 a una aplicación móvil del SDK de Adobe Experience Platform, la aplicación móvil migrada no tendrá este tipo de información. Tan pronto como un usuario cargue un nuevo certificado de iOS o una clave de Android, los distintos detalles de la clave o certificado se almacenarán y mostrarán correctamente en la lista desplegable **[!UICONTROL Push channel settings]**.
