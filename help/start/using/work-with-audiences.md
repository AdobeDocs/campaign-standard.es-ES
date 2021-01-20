---
solution: Campaign Standard
product: campaign
title: Personalización de listas
description: '"Aprenda a personalizar la visualización y a actuar en pantallas de lista en Adobe Campaign Standard:ordenar, filtrar, eliminar o duplicar elementos. Las pantallas de listas muestran elementos de uno o varios recursos determinados."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: 434edb8e1c3396ad29edd9ee60866c93e82a2c1b
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 11%

---


# Uso de perfiles y audiencias

<table>
<tr>
    <td valign="top">
        <a href="../../start/using/work-with-audiences.md"><img width="60px" alt="condiciones" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/creating-a-service.md"><img width="60px" alt="condiciones" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-custom-resources.md"><img width="60px" alt="condiciones" src="assets/icon_profile.svg"/></a>
    </td>
    <td valign="top">
        <a href="../../api/using/interacting-with-marketing-history.md"><img width="60px" alt="condiciones" src="assets/icon_profile.svg"/></a>
    </td>
</tr>
<tr>
<td>Perfiles del cliente</td>
<td>Enriquecimiento de la base de datos</td>
<td>Organizar sus audiencias</td>
<td>Administración de la privacidad</td>
</tr>
</table>

## Perfiles del cliente {#customer-profiles}

<img width="60px" alt="condiciones" src="assets/icon_profile.svg"/>

Los perfiles de Adobe Campaign representan todos los contactos almacenados en la base de datos. Cada perfil corresponde a una entrada de la base de datos que contiene la información necesaria para que ese perfil sea dirigido, calificado y rastreado individualmente. Esto significa que un perfil puede ser: un cliente, un cliente potencial, un individuo suscrito a un boletín, un destinatario, un usuario o cualquier otra denominación según la organización.

**Más información**

* [Acerca de los perfiles](../../audiences/using/about-profiles.md)
* [Acceso al número de Perfiles activos de su organización](../../audiences/using/active-profiles.md)

## Enriqueciendo la base de datos {#populating-database}

<img width="60px" alt="condiciones" src="assets/icon_populate.svg"/>

Campaign Standard oferta varias herramientas para ayudarle a ampliar su base de datos de mercadotecnia. Esta sección detalla los diferentes métodos que puede utilizar para inyectar datos en Campaña, con referencias a las documentaciones dedicadas.

### Importación de datos mediante flujos de trabajo {#importing-data-through-workflows}

Los flujos de trabajo le permiten recopilar datos e importarlos a la base de datos de Campañas mediante el uso de actividades [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md). En [esta sección](../../automating/using/about-data-import-and-export.md) se presenta información genérica y optimizaciones para importar datos mediante flujos de trabajo.

Además, puede configurar plantillas para importar datos. El uso de plantillas de importación es una práctica recomendada si necesita importar archivos con la misma estructura de forma regular. Puede configurar dos tipos de plantillas:

* **Plantillas** de flujo de trabajo: son flujos de trabajo preconfigurados que puede configurar una vez según sus necesidades y volver a utilizar cada vez que desee importar datos y actualizar la base de datos. En [esta sección](../../automating/using/creating-import-workflow-templates.md) se detalla un ejemplo de plantilla de flujo de trabajo para importar datos.

* **Importar plantillas** de datos: al igual que las plantillas de flujo de trabajo, se trata de plantillas basadas en flujos de trabajo que se configuran para cargar archivos para actualizar la base de datos. Una vez configurados, se ponen a disposición de los usuarios con una vista simplificada en el menú **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**. Para obtener más información sobre las plantillas de datos de importación, consulte la [documentación dedicada](../../automating/using/importing-data-with-import-templates.md).

### Recopilación de datos de páginas de aterrizaje {#collecting-data-from-landing-pages}

Las páginas de aterrizaje son formularios web que se pueden utilizar para recopilar datos y crear o actualizar la información existente en la base de datos. El principio es el siguiente:

* Cree y diseñe su página de aterrizaje agregando campos de entrada para recopilar datos (nombre, apellidos, correo electrónico, etc.).
* Asigne cada campo de entrada con el campo correspondiente de la base de datos.
* Haga que la página de aterrizaje esté disponible en línea a través de un sitio web o a través de un vínculo directo en un mensaje.

Para obtener más información sobre páginas de aterrizaje, consulte la [documentación dedicada](../../channels/using/getting-started-with-landing-pages.md).

**Más información**

* xxxx
* xxxx

### Sincronización de perfiles de Microsoft Dynamics 365

La integración de Campaign Standard con Microsoft Dynamics 365 le permite pasar datos de contacto de Microsoft Dynamics 365 a la base de datos de Campaña.
Estos contactos son visibles en la lista de Perfiles y se pueden dirigir a campañas de marketing. Para obtener más información sobre esta integración, consulte la [documentación dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Tenga en cuenta que el conector Campaign Standard-Microsoft Dynamics 365 está actualmente en disponibilidad limitada y que está sujeto a varias limitaciones, detalladas en la documentación.

**Más información**

* xxxx
* xxxx

### Importación de datos mediante llamadas de API

Las API de Campaign Standard permiten realizar operaciones para actualizar la base de datos, como la creación, actualización o eliminación de perfiles o servicios. Para obtener más información sobre cómo utilizar las API, consulte la [documentación dedicada](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Antes de realizar la creación masiva de perfiles o la actualización mediante llamadas de API, compruebe las limitaciones de escala correspondientes a su contrato de licencia. Para obtener más información, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Más información**

* xxxx
* xxxx

## Organización de las audiencias {#organizing-audiences}

<img width="60px" alt="condiciones" src="assets/icon_audience.svg"/>

Para permitirle entregar mensajes relevantes y eficaces y captar a sus clientes de manera eficaz, Adobe Campaign integra funcionalidades avanzadas de análisis y determinación de objetivos.

Gracias a los flujos de trabajo y al editor de consultas, puedes crear audiencias que serán blanco de tus diferentes campañas, dependiendo de la información que tengas sobre ellos, sus actividades, su idioma, sus preferencias o su historial de marketing. Esto le permite filtrar los perfiles suscritos, por ejemplo, o crear audiencias de destinatario según un número ilimitado de criterios.

**Más información**

* [Acerca de las audiencias](../../audiences/using/about-audiences.md)
* [Creación de audiencias](../../audiences/using/creating-audiences.md)

## Administración de la privacidad {#privacy-management}

<img width="60px" alt="condiciones" src="assets/icon_privacy.svg"/>

El Reglamento General de Protección de Datos (GDPR) es la nueva normativa sobre privacidad de la Unión Europea que unifica y moderniza los requisitos de protección de datos. El RGPD se aplica a los clientes de Adobe Campaign que albergan datos de sujetos de datos que residan en la UE. Además de las capacidades de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), aprovechamos esta oportunidad en nuestra función de procesador de datos para incluir capacidades adicionales, a fin de facilitar su preparación como controlador de datos para determinadas solicitudes de RGPD.

Consulte esta [guía](https://helpx.adobe.com/es/campaign/kb/campaign-privacy.html) para obtener más información sobre las herramientas y funcionalidades que proporciona Adobe Campaign para ayudarle a cumplir con el RGPD.

**Más información**

* xxxx
* xxxx