---
title: 'Introducción a la herramienta de integración '
description: Introducción a la herramienta de integración
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
translation-type: tm+mt
source-git-commit: 1e05db3fecc87a026750f40acb0ff063706e3f38
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 2%

---


# Introducción a la aplicación de integración de autoservicio {#gs-self-service-app}

La integración de Adobe Campaign Standard con la aplicación de integración de autoservicio de Microsoft Dynamics 365 le permite configurar los flujos de datos, controlar si se están ejecutando o no y en qué entorno. Sin embargo, debe completar algunos requisitos previos antes de empezar a utilizar la aplicación de integración de autoservicio.

## Conceptos y restricciones {#concepts-and-restrictions}

Antes de comenzar con la herramienta de integración, debe comprender los conceptos y las protecciones asociadas con la integración y realizar algunos pasos iniciales para obtener acceso.

Obtenga más información en estas secciones:

* [Introducción a la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md)
* [Prácticas recomendadas y limitaciones de integración](../../integrating/using/d365-acs-notices-and-recommendations.md)
* [Conozca los pasos clave para implementar esta integración](../../integrating/using/d365-acs-get-started.md#request-and-implement-this-integration)
* [Usar la integración con Microsoft Dynamics 365](../../integrating/using/d365-acs-using-the-integration.md)

## Requisitos previos {#self-service-app-prerequisites}

Debe configurar Microsoft Dynamics 365 y Adobe Campaign Standard para que la aplicación de integración tenga acceso a sus datos. Esto tardará algún tiempo en configurarse en Dynamics 365, Adobe Campaign Standard y Adobe I/O; sin embargo, una vez configuradas, podrá controlar la integración a través de la interfaz de usuario de la aplicación de integración de autoservicio.

Obtenga más información en estas secciones:

* [Configuración de Microsoft Dynamics 365 para integración con Campaign](../../integrating/using/d365-acs-configure-d365.md)
* [Configuración de Adobe I/O](../../integrating/using/d365-acs-configure-adobe-io.md)
* [Asignar recursos personalizados de Campaña y entidades personalizadas de Microsoft Dynamics 365](../../integrating/using/d365-acs-notices-and-recommendations.md)

## Pasos clave para configurar la aplicación de integración de autoservicio {#self-service-app-configuration-steps}

A continuación, puede establecer inicios con la herramienta de integración. Siga los pasos a continuación:

1. [Obtenga acceso a la aplicación de integración](../../integrating/using/d365-acs-self-service-app-control-access.md)
1. [Configurar la aplicación de integración para su uso](../../integrating/using/d365-acs-self-service-app-settings.md)
1. [Implementar la sincronización de datos](../../integrating/using/d365-acs-self-service-app-data-sync.md)
1. [Configuración de flujos de trabajo de sincronización](../../integrating/using/d365-acs-self-service-app-workflows.md)

## Vínculo a la aplicación de integración {#self-service-app-link}

Abra un navegador y vaya al conector asociado con su región:

* [Asia Pacífico](http://d365-acs-ap.ea.adobe.com/)
* [Europa, Oriente Medio o África (EMEA)](http://d365-acs-em.ea.adobe.com/)
* [América](http://d365-acs-na.ea.adobe.com/)

## Confirmación de solicitud de privacidad {#self-service-app-acknowledgement}

Al navegar por la interfaz de usuario de autoservicio por primera vez, se le mostrará la confirmación de privacidad. Debe reconocer que comprende su función en la realización de solicitudes de privacidad en Campaña y en Microsoft Dynamics 365 por separado antes de poder continuar.
Obtenga más información sobre sus responsabilidades de privacidad y sobre cómo administrar las solicitudes de privacidad en [esta sección](../../integrating/using/d365-acs-notices-and-recommendations.md#acs-msdyn-manage-privacy).

## Configuración de las credenciales {#self-service-app-credentials}

Al buscar por primera vez en la interfaz de usuario, debería ver una página con un encabezado que tenga este aspecto:

![](assets/d365-to-acs-ui-header.png)

>[!NOTE]
>
> Es normal recibir alertas que mencionen que &quot;no se puede conectar&quot; a Adobe Campaign Standard o Microsoft Dynamics 365 si la configuración de la aplicación aún no se ha configurado.

Verifique que las selecciones &quot;ORG&quot; e &quot;INSTANCE&quot; sean las que planea configurar.  Si no es así, haga clic en la lista desplegable y seleccione la organización y la instancia correctas.

>[!IMPORTANT]
>
> Si está configurando el conector por primera vez y/o es nuevo en este proceso, **fuertemente** le instamos a seleccionar la instancia &quot;stage&quot; o &quot;dev&quot;. Asegúrese de que la configuración funciona bien antes de intentar la configuración en producción.

Si tiene la organización y la instancia correctas, haga clic en el menú &quot;hamburguesa&quot; para mostrar un menú desplegable. A continuación, haga clic en **[!UICONTROL Settings...]** en el menú desplegable para visitar la página en la que ha introducido sus credenciales para Microsoft Dynamics 365 y Campaña (véase más abajo).

![](assets/d365-to-acs-ui-page-workflows-menu-pointers.png)

En la página **[!UICONTROL Settings]**, complete las siguientes secciones:

* Credenciales de Microsoft Dynamics 365
* Credenciales de Adobe

Vaya [aquí](../../integrating/using/d365-acs-self-service-app-settings.md) para encontrar información más detallada sobre dónde encontrar la información de cada entrada. Cuando haya terminado, haga clic en el botón **[!UICONTROL Save]** en la parte inferior.

## Compruebe la configuración inicial {#self-service-app-initial-config}

Suponiendo que haya completado los requisitos previos anteriores y haya agregado correctamente todas sus credenciales, ahora navegaremos a la página **[!UICONTROL Workflows]**. Obtenga más información sobre los flujos de trabajo de la aplicación de integración en [esta página](../../integrating/using/d365-acs-self-service-app-workflows.md).

En la página **[!UICONTROL Workflows]**, haga clic en el icono de lápiz asociado al flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para editar su configuración.

![](assets/d365-to-acs-ui-page-workflows-ingress-edit-pointer.png)

En la página **[!UICONTROL Microsoft Dynamics 365 to Campaign]**, puede acceder a la lista de las asignaciones de tabla que ha configurado.  Le asignará de forma predeterminada una asignación de contacto/perfil lista para usar. Todas las demás entidades personalizadas deberán configurarse por separado.

![](assets/d365-to-acs-ui-page-ingress-top-pointers.png)

En la página **[!UICONTROL Edit Table Mapping]**, marque la sección **[!UICONTROL Mappings]** para asegurarse de que los campos de Microsoft Dynamics 365 se asignen al campo correcto de la Campaña. Si necesita agregar otras asignaciones, hágalo ahora, así como cualquier reemplazo o filtros. [Más información](../../integrating/using/d365-acs-self-service-app-data-sync.md).

Si desea agregar nuevas asignaciones, consulte [esta sección](../../integrating/using/d365-acs-self-service-app-data-sync.md#add-a-new-mapping) para obtener más información.

Una vez que la configuración sea correcta, haga clic en el botón **[!UICONTROL Play]** situado junto al flujo de trabajo **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para inicio de la integración y el flujo de datos.

>[!IMPORTANT]
>
>Le recomendamos **enfáticamente** que primero ejecute esto en los entornos de Etapa o Dev antes de ejecutarlo en Producción. Verifique que la instancia de stage/dev esté seleccionada en el encabezado.


![](assets/d365-to-acs-ui-page-workflows-ingress-play-pointer.png)

Una vez ejecutada, debe poder realizar pruebas agregando o modificando entradas en Microsoft Dynamics 365 y observando esos cambios en Adobe Campaign en unos minutos. Si en cualquier momento necesita detener este proceso, simplemente presione el mismo botón para detenerlo. [Más información](../../integrating/using/d365-acs-self-service-app-workflows.md#workflow-status)


## Espacio de trabajo de la aplicación de integración {#self-service-app-workspace}

### Encabezado de aplicación {#app-header}

El encabezado de la aplicación de autoservicio le permite definir la organización y la instancia que está viendo o configurando en ese momento.

Seleccione el **ORG** y la **INSTANCIA** que desea editar/vista. Estos campos aparecen como de solo lectura, pero se pueden editar al colocar el cursor del ratón sobre ellos.

Se mostrará un menú desplegable cuando haga clic en el botón con las tres líneas horizontales ![](assets/d365-to-acs-icon-hamburger.png) en la parte derecha del encabezado.

Las entradas del menú desplegable son

* **Configuración**: Si selecciona esta opción, se le enviará a una pantalla que le permitirá especificar las credenciales de API para Microsoft Dynamics 365 y Adobe Campaign, así como otras opciones generales para la aplicación.

* **Documentación**: Esta opción es un vínculo a la documentación de Adobe Campaign específica de esta integración

* **Servicio de atención** al cliente: Se trata de un vínculo a la documentación del Experience Cloud relacionada con la apertura de un ticket del Servicio de atención al cliente

* **Cerrar sesión**: Esto le permitirá cerrar sesión en la aplicación y volver a iniciarla como otro usuario.

* **Acerca** de: Muestra un cuadro de diálogo que contiene información sobre la aplicación, incluida la información de copyright.

### Rutas de exploración {#app-breadcrumbs}

Las rutas de navegación aparecen en la parte superior de algunas pantallas a medida que navega por la aplicación.

**Ejemplo:**

A continuación se muestra un ejemplo de la pantalla **[!UICONTROL Edit Table Mapping]** que muestra las rutas de exploración y el título de la página. En este caso, puede hacer clic en el texto **[!UICONTROL Workflows]** o **[!UICONTROL Microsoft Dynamics 365 to Campaign]** para ir a una de las pantallas anteriores. **[!UICONTROL Edit Table Mapping]** en las rutas de exploración no se puede hacer clic en este caso porque es la pantalla actual.

![](assets/d365-to-acs-breadcrumbs-ingress.png)

### Botones comunes {#app-buttons}

Los iconos siguientes se utilizan en varias páginas de la aplicación de autoservicio.

![](assets/d365-to-acs-icon-add.png) - Añadir un nuevo elemento en una lista.

![](assets/d365-to-acs-icon-edit.png) - Editar algo que ya existe

![](assets/d365-to-acs-icon-delete.png) - Eliminar un elemento de una lista de elementos