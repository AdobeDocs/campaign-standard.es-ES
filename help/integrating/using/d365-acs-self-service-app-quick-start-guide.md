---
title: Introducción a la herramienta de integración
description: Introducción a la herramienta de integración
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
role: Data Architect
level: Intermediate
exl-id: e73e2069-e86d-4be2-bf73-22e6dc164340
source-git-commit: e7fdaa4b1d77afdae8004a88bbe41bbbe75a3f3c
workflow-type: tm+mt
source-wordcount: '1079'
ht-degree: 1%

---

# Introducción a la aplicación de integración de autoservicio {#gs-self-service-app}

La aplicación de integración de Adobe Campaign Standard con Microsoft Dynamics 365 le permite configurar flujos de datos, controlar si se están ejecutando o no y en qué entorno. Sin embargo, debe completar algunos requisitos previos antes de empezar a utilizar la aplicación de integración de autoservicio.

## Conceptos y restricciones {#concepts-and-restrictions}

Antes de comenzar con la herramienta de integración, debe comprender los conceptos y las protecciones asociadas con la integración y realizar algunos pasos iniciales para obtener acceso.

Obtenga más información en estas secciones:

* [Introducción a la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Prácticas recomendadas y limitaciones de integración](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Conozca los pasos clave para implementar esta integración](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Uso de la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Requisitos previos {#self-service-app-prerequisites}

Debe configurar Microsoft Dynamics 365 y Adobe Campaign Standard para que la aplicación de integración tenga acceso a sus datos. Esta configuración tardará algún tiempo en realizarse en Dynamics 365, Adobe Campaign Standard y Adobe I/O; sin embargo, una vez configurada, podrá controlar la integración a través de la interfaz de usuario de la aplicación de integración de autoservicio.

Obtenga más información en estas secciones:

* [Configuración de Microsoft Dynamics 365 para integración con Campaign](../../integrating/using/d365-acs-configure-d365.md)
* [Configuración del Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Asignación de recursos personalizados de Campaign y entidades personalizadas de Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Pasos clave para configurar la aplicación de integración de autoservicio {#self-service-app-configuration-steps}

A continuación, puede empezar con la herramienta de integración. Siga los pasos a continuación:

1. [Obtenga acceso a la aplicación de integración](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Configure la aplicación de integración para su uso](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Implementación de sincronización de datos](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Configuración de flujos de trabajo de sincronización](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Vínculo a la aplicación de integración {#self-service-app-link}

Abra un explorador y vaya al conector asociado a su región:

* [Asia-Pacífico](https://d365-acs-ap.ea.adobe.com/)
* [Europa, Oriente Medio o África (EMEA)](https://d365-acs-em.ea.adobe.com/)
* [América](https://d365-acs-am.ea.adobe.com/)

## Confirmación de solicitud de privacidad {#self-service-app-acknowledgement}

Al navegar a la interfaz de usuario de autoservicio por primera vez, se le mostrará el reconocimiento de privacidad. Debe reconocer que comprende su función al realizar solicitudes de privacidad en Campaign y Microsoft Dynamics 365 por separado antes de poder continuar.
Obtenga más información acerca de sus responsabilidades en materia de privacidad y cómo administrar las solicitudes de privacidad en [esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Configuración de las credenciales {#self-service-app-credentials}

Cuando vaya a la interfaz de usuario por primera vez, debería ver una página con un encabezado similar al siguiente:

![](assets/do-not-localize/d365-to-acs-ui-header.png)

>[!NOTE]
>
> Es normal recibir alertas que mencionan que es &quot;incapaz de conectarse&quot; a Adobe Campaign Standard o Microsoft Dynamics 365 si la configuración de la aplicación aún no se ha establecido.

Compruebe que las selecciones &quot;ORG&quot; e &quot;INSTANCE&quot; sean las que planea configurar.  Si no es así, haga clic en la lista desplegable y seleccione la organización y la instancia correctas.

>[!IMPORTANT]
>
> Si está configurando el conector por primera vez o es nuevo en este proceso, utilice **enérgico** le anima a seleccionar la instancia &quot;stage&quot; o &quot;dev&quot;. Debe asegurarse de que la configuración funciona correctamente antes de intentar realizar la instalación en producción.

Si tiene la organización y la instancia correctas, haga clic en el menú &quot;hamburguesa&quot; para mostrar un menú desplegable. Luego haga clic en **[!UICONTROL Settings...]** en el menú desplegable para visitar la página donde escribe las credenciales de para Microsoft Dynamics 365 y Campaign (consulte a continuación).

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-menu-pointers.png)

En el **[!UICONTROL Settings]** , rellene las secciones siguientes:

* Credenciales de Microsoft Dynamics 365
* Credenciales de Adobe

Ir [aquí](../../integrating/using/d365-acs-self-service-app-settings.md) para obtener información más detallada sobre dónde encontrar la información de cada entrada. Cuando haya terminado, haga clic en **[!UICONTROL Save]** botón en la parte inferior.

## Comprobar la configuración inicial {#self-service-app-initial-config}

Si ha completado los requisitos previos anteriores y ha agregado correctamente todas las credenciales, vamos a navegar a la **[!UICONTROL Workflows]** página. Obtenga más información sobre los flujos de trabajo de la aplicación de integración en [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

En el  **[!UICONTROL Workflows]** , haga clic en el icono de lápiz asociado a la página **[!UICONTROL Microsoft Dynamics 365 to Campaign]** flujo de trabajo para editar su configuración.

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

En el **[!UICONTROL Microsoft Dynamics 365 to Campaign]** , puede acceder a la lista de las asignaciones de tabla que ha configurado.  De forma predeterminada, se le asigna una asignación de contacto/perfil lista para usar. Todas las demás entidades personalizadas deberán configurarse por separado.

![](assets/do-not-localize/d365-to-acs-ui-page-ingress-top-pointers.png)

En el **[!UICONTROL Edit Table Mapping]** , marque la **[!UICONTROL Mappings]** para garantizar que los campos de Microsoft Dynamics 365 se asignen al campo correcto en Campaign. Si necesita agregar otras asignaciones, hágalo ahora, así como cualquier reemplazo o filtro. [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Si desea añadir nuevas asignaciones, consulte [esta sección](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) para obtener más información.

Una vez que la configuración sea correcta, haga clic en **[!UICONTROL Play]** junto al botón **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para iniciar la integración y el flujo de datos.

>[!IMPORTANT]
>
>Nosotros **enérgico** Se recomienda ejecutar esto primero en los entornos de ensayo o desarrollo antes de ejecutar en producción. Compruebe que la instancia de stage/dev esté seleccionada en el encabezado.
>

![](assets/do-not-localize/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Una vez que se esté ejecutando, debería poder realizar pruebas agregando o modificando entradas en Microsoft Dynamics 365 y observando esos cambios en Adobe Campaign en unos minutos. Si en cualquier momento necesita detener este proceso, simplemente pulse el mismo botón para detenerlo. [Más información](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Integración de App Workspace {#self-service-app-workspace}

### Encabezado de aplicación {#app-header}

El encabezado de la aplicación de autoservicio le permite definir qué organización e instancia está viendo o configurando en ese momento.

Seleccione el **ORG** y el **INSTANCIA** desea ver o editar. Estos campos aparecen como de solo lectura, pero se pueden editar cuando se coloca el cursor del ratón sobre ellos.

Se mostrará un menú desplegable cuando haga clic en el botón con las tres líneas horizontales ![](assets//do-not-localize/d365-to-acs-icon-hamburger.png) en el lado derecho del encabezado.

Las entradas del menú desplegable son las siguientes:

* **Configuración**: si selecciona esta opción, aparecerá una pantalla que le permite especificar las credenciales de la API para Microsoft Dynamics 365 y Adobe Campaign, así como otra configuración general de la aplicación.

* **Documentación**: esta opción es un vínculo a la documentación de Adobe Campaign específica de esta integración

* **Atención al cliente**: este es un vínculo a la documentación del Experience Cloud relacionada con la apertura de un ticket del Servicio de atención al cliente

* **Cerrar sesión**: esto cerrará la sesión de la aplicación y le permitirá volver a iniciar sesión como otro usuario.

* **Acerca de**: Muestra un cuadro de diálogo que contiene información sobre la aplicación, incluida la información de copyright.

### Rutas {#app-breadcrumbs}

Las rutas de exploración aparecen en la parte superior de algunas pantallas a medida que navega por la aplicación.

**Ejemplo:**

A continuación se muestra un ejemplo de la **[!UICONTROL Edit Table Mapping]** que muestra las rutas de exploración y el título de la página. En este caso, puede hacer clic en **[!UICONTROL Workflows]** o **[!UICONTROL Microsoft Dynamics 365 to Campaign]** texto para ir a una de las pantallas anteriores. **[!UICONTROL Edit Table Mapping]** en las rutas de exploración no se puede hacer clic en este caso porque es la pantalla actual.

![](assets/do-not-localize/d365-to-acs-breadcrumbs-ingress.png)

### Botones comunes {#app-buttons}

Los siguientes iconos se utilizan en varias páginas de la aplicación de autoservicio.

![](assets/do-not-localize/d365-to-acs-icon-add.png) - Agregar un nuevo elemento a una lista.

![](assets/do-not-localize/d365-to-acs-icon-edit.png) - Editar algo que ya existe

![](assets/do-not-localize/d365-to-acs-icon-delete.png) - Eliminar un elemento de una lista de elementos
