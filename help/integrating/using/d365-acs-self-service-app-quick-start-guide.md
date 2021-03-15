---
title: 'Introducción a la herramienta de integración '
description: Introducción a la herramienta de integración
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Integración de Microsoft CRM
role: Arquitecto de datos
level: Intermedio
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '1077'
ht-degree: 2%

---


# Introducción a la aplicación de integración de autoservicio {#gs-self-service-app}

La integración de Adobe Campaign Standard con la aplicación de integración de autoservicio de Microsoft Dynamics 365 le permite configurar flujos de datos, controlar si se están ejecutando o no y en qué entorno. Sin embargo, debe completar algunos requisitos previos antes de empezar a usar la aplicación de integración de autoservicio.

## Conceptos y restricciones {#concepts-and-restrictions}

Antes de comenzar con la herramienta de integración, debe comprender los conceptos y las barreras asociadas con la integración y realizar algunos pasos iniciales para obtener acceso.

Obtenga más información en estas secciones:

* [Introducción a la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Prácticas recomendadas y limitaciones de integración](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Conozca los pasos clave para implementar esta integración](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Usar la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Requisitos previos {#self-service-app-prerequisites}

Debe configurar Microsoft Dynamics 365 y Adobe Campaign Standard para que la aplicación de integración tenga acceso a los datos. Esto tardará algún tiempo en configurarse en Dynamics 365, Adobe Campaign Standard y Adobe I/O; sin embargo, una vez configuradas, podrá controlar la integración a través de la interfaz de usuario de la aplicación de integración de autoservicio.

Obtenga más información en estas secciones:

* [Configuración de Microsoft Dynamics 365 para integración con Campaign](../../integrating/using/d365-acs-configure-d365.md)
* [Configuración de Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Asignación de recursos personalizados de Campaign y entidades personalizadas de Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Pasos clave para configurar la aplicación de integración de autoservicio {#self-service-app-configuration-steps}

A continuación, puede empezar con la herramienta de integración. Siga los pasos a continuación:

1. [Obtenga acceso a la aplicación de integración](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Configurar la aplicación de integración para su uso](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Implementación de la sincronización de datos](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Configuración de flujos de trabajo de sincronización](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Vínculo a la aplicación de integración {#self-service-app-link}

Abra un explorador y vaya al conector asociado con su región:

* [Asia-Pacífico](https://d365-acs-ap.ea.adobe.com/)
* [Europa, Oriente Medio o África (EMEA)](https://d365-acs-em.ea.adobe.com/)
* [América](https://d365-acs-am.ea.adobe.com/)

## Confirmación de solicitud de privacidad {#self-service-app-acknowledgement}

Al navegar por la interfaz de usuario de autoservicio por primera vez, se le presentará la confirmación de privacidad. Debe reconocer que comprende su función en la realización de solicitudes de privacidad en Campaign y Microsoft Dynamics 365 por separado antes de continuar.
Obtenga más información sobre sus responsabilidades de privacidad y sobre cómo administrar las solicitudes de privacidad en [esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Configuración de las credenciales {#self-service-app-credentials}

Cuando vaya a la interfaz de usuario por primera vez, debería ver una página con un encabezado que tenga este aspecto:

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> Es normal recibir alertas que mencionen que &quot;no se puede conectar&quot; a Adobe Campaign Standard o Microsoft Dynamics 365 si la configuración de la aplicación aún no se ha configurado.

Compruebe que las selecciones &quot;ORG&quot; e &quot;INSTANCE&quot; sean las que desea configurar.  Si no es así, haga clic en la lista desplegable y seleccione la organización y la instancia correctas.

>[!IMPORTANT]
>
> Si está configurando el conector por primera vez o es nuevo en este proceso, **strong** le instamos a seleccionar la instancia &quot;stage&quot; o &quot;dev&quot;. Asegúrese de comprobar que la configuración funciona bien antes de intentar la configuración en producción.

Si tiene la organización y la instancia correctas, haga clic en el menú &quot;hamburguesa&quot; para mostrar un menú desplegable. A continuación, haga clic en **[!UICONTROL Settings...]** en el menú desplegable para visitar la página donde introdujo sus credenciales para Microsoft Dynamics 365 y Campaign (consulte a continuación).

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

En la página **[!UICONTROL Settings]**, rellene las siguientes secciones:

* Credenciales de Microsoft Dynamics 365
* Credenciales de Adobe

Vaya [aquí](../../integrating/using/d365-acs-self-service-app-settings.md) para encontrar información más detallada sobre dónde encontrar la información para cada entrada. Cuando haya terminado, haga clic en el botón **[!UICONTROL Save]** en la parte inferior.

## Compruebe la configuración inicial {#self-service-app-initial-config}

Suponiendo que haya completado los requisitos previos anteriores y haya agregado correctamente todas sus credenciales, ahora vamos a navegar a la página **[!UICONTROL Workflows]** . Obtenga más información sobre los flujos de trabajo de la aplicación de integración en [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

En la página **[!UICONTROL Workflows]** , haga clic en el icono de lápiz asociado al flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para editar su configuración.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

En la página **[!UICONTROL Microsoft Dynamics 365 to Campaign]** puede acceder a la lista de asignaciones de tabla que ha configurado.  De forma predeterminada, tendrá una asignación de contacto/perfil predeterminada. Todas las demás entidades personalizadas deberán configurarse por separado.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

En la página **[!UICONTROL Edit Table Mapping]**, marque la sección **[!UICONTROL Mappings]** para asegurarse de que los campos de Microsoft Dynamics 365 se asignen al campo correcto en Campaign. Si necesita añadir otras asignaciones, hágalo ahora, así como cualquier reemplazo o filtro. [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Si desea agregar nuevas asignaciones, consulte [esta sección](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) para obtener más información.

Una vez que la configuración sea correcta, haga clic en el botón **[!UICONTROL Play]** situado junto al flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para iniciar la integración y el flujo de datos.

>[!IMPORTANT]
>
>Le **recomendamos encarecidamente** que primero ejecute esto en los entornos de fase o desarrollo antes de ejecutarse en producción. Compruebe que la instancia de stage/dev esté seleccionada en el encabezado.


![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Una vez ejecutado, debe poder probarlo agregando o modificando entradas en Microsoft Dynamics 365 y observando esos cambios en Adobe Campaign en unos minutos. Si en cualquier momento necesita detener este proceso, simplemente presione el mismo botón para detenerlo. [Obtenga más información](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Espacio de trabajo de la aplicación de integración {#self-service-app-workspace}

### Encabezado de aplicación {#app-header}

El encabezado de la aplicación de autoservicio le permite definir qué organización e instancia está viendo o configurando actualmente.

Seleccione la **ORG** y la **INSTANCIA** que desea ver/editar. Estos campos aparecen como de solo lectura, sin embargo, se vuelven editables cuando se coloca el cursor del ratón sobre ellos.

Se mostrará un menú desplegable cuando haga clic en el botón con las tres líneas horizontales ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) en el lado derecho del encabezado.

Las entradas del menú desplegable son:

* **Configuración**: Al seleccionar esta opción, se le enviará a una pantalla que le permitirá especificar las credenciales de API para Microsoft Dynamics 365 y Adobe Campaign, así como otras configuraciones generales de la aplicación.

* **Documentación**: Esta opción es un vínculo a la documentación de Adobe Campaign específica de esta integración

* **Servicio de atención** al cliente: Este es un vínculo a la documentación del Experience Cloud relacionada con la apertura de un ticket del Servicio de atención al cliente

* **Cerrar sesión**: Esto le cerrará la sesión de la aplicación y le permitirá volver a iniciarla como otro usuario.

* **Acerca de**: Se muestra un cuadro de diálogo que contiene información sobre la aplicación, incluida la información de copyright.

### Rutas de exploración {#app-breadcrumbs}

Las rutas de exploración aparecen en la parte superior de algunas pantallas a medida que navega por la aplicación.

**Ejemplo:**

A continuación, se muestra un ejemplo de la pantalla **[!UICONTROL Edit Table Mapping]** que muestra las rutas de exploración y el título de la página. En este caso, puede hacer clic en el texto **[!UICONTROL Workflows]** o **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para ir a una de las pantallas anteriores. **[!UICONTROL Edit Table Mapping]** en las rutas de exploración no se puede hacer clic en este caso porque es la pantalla actual.

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### Botones comunes {#app-buttons}

Los iconos siguientes se utilizan en varias páginas de la aplicación de autoservicio.

![](assets/do-not-localize/d365-to-acs-icon-add.png) - Agregar un nuevo elemento a una lista.

![](assets/do-not-localize/d365-to-acs-icon-edit.png) - Editar algo que ya existe

![](assets/do-not-localize/d365-to-acs-icon-delete.png) - Eliminar un elemento de una lista de elementos
