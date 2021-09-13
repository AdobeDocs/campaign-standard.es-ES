---
title: Personalización de listas
description: '"Aprenda a personalizar la visualización y a actuar en las pantallas de lista en Adobe Campaign Standard:clasificación, filtrado, eliminación o duplicación de elementos. Las pantallas de listas muestran los elementos de uno o varios recursos determinados."'
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
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
<td>Perfiles de cliente</td>
<td>Enriquecimiento de la base de datos</td>
<td>Organizar las audiencias</td>
<td>Administración de la privacidad</td>
</tr>
</table>

## Perfiles de cliente {#customer-profiles}

<img width="60px" alt="condiciones" src="assets/icon_profile.svg"/>

Los perfiles de Adobe Campaign representan todos los contactos almacenados en la base de datos. Cada perfil corresponde a una entrada de la base de datos que contiene la información necesaria para que ese perfil sea segmentado, cualificado y rastreado individualmente. Esto significa que un perfil puede ser: un cliente, un cliente potencial, una persona suscrita a un boletín, un destinatario, un usuario o cualquier otra denominación según la organización.

**Más información**

* [Acerca de los perfiles](../../audiences/using/about-profiles.md)
* [Acceso al número de perfiles activos de su organización](../../audiences/using/active-profiles.md)

## Enriquecimiento de la base de datos {#populating-database}

<img width="60px" alt="condiciones" src="assets/icon_populate.svg"/>

Campaign Standard ofrece varias herramientas para ayudarle a ampliar su base de datos de marketing. Esta sección detalla los diferentes métodos que se pueden utilizar para insertar datos en Campaign, con referencias a la documentación dedicada.

### Importación de datos mediante flujos de trabajo {#importing-data-through-workflows}

Los flujos de trabajo permiten recopilar datos e importarlos a la base de datos de Campaign mediante el uso de actividades [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md). La información genérica y las prácticas recomendadas al importar datos mediante flujos de trabajo se presentan en [esta sección](../../automating/using/about-data-import-and-export.md).

Además, puede configurar plantillas para importar datos. El uso de plantillas de importación es una práctica recomendada si necesita importar archivos con la misma estructura de forma regular. Puede configurar dos tipos de plantillas:

* **Plantillas** de flujo de trabajo: son flujos de trabajo preconfigurados que se pueden configurar una vez según sus necesidades y reutilizar cada vez que desee importar datos y actualizar la base de datos. En [esta sección](../../automating/using/creating-import-workflow-templates.md) se detalla un ejemplo de plantilla de flujo de trabajo para importar datos.

* **Importar plantillas** de datos: al igual que las plantillas de flujo de trabajo, se trata de plantillas basadas en flujos de trabajo, que se configuran para cargar archivos para actualizar la base de datos. Una vez configurados, están disponibles para los usuarios con una vista simplificada en el menú **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]**. Para obtener más información sobre las plantillas de datos de importación, consulte la [documentación dedicada](../../automating/using/importing-data-with-import-templates.md).

### Recopilación de datos de páginas de aterrizaje {#collecting-data-from-landing-pages}

Las páginas de aterrizaje son formularios web que se pueden utilizar para recopilar datos y crear o actualizar información existente en la base de datos. El principio es el siguiente:

* Cree y diseñe su página de aterrizaje añadiendo campos de entrada para recopilar datos (nombre, apellidos, correo electrónico, etc.).
* Asigne cada campo de entrada con el campo correspondiente de la base de datos.
* Haga que la página de aterrizaje esté disponible en línea a través de un sitio web o mediante un vínculo directo a un mensaje.

Para obtener más información sobre las páginas de aterrizaje, consulte la [documentación dedicada](../../channels/using/getting-started-with-landing-pages.md).

**Más información**

* xxxx
* xxxx

### Sincronización de perfiles de Microsoft Dynamics 365

La integración de Campaign Standards con Microsoft Dynamics 365 le permite pasar datos de contacto de Microsoft Dynamics 365 a la base de datos de Campaign.
Estos contactos están visibles en la lista Perfiles y se pueden seleccionar como objetivo en las campañas de marketing. Para obtener más información sobre esta integración, consulte la [documentación dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Tenga en cuenta que el conector Campaign Standard-Microsoft Dynamics 365 está actualmente en disponibilidad limitada y que está sujeto a varias limitaciones, detalladas en la documentación.

**Más información**

* xxxx
* xxxx

### Importación de datos mediante llamadas a API

Las API de Campaign Standard permiten realizar operaciones para actualizar la base de datos, como la creación, actualización o eliminación de perfiles o servicios. Para obtener más información sobre cómo utilizar las API, consulte la [documentación dedicada](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Antes de realizar la creación o actualización masiva de perfiles mediante llamadas a la API, compruebe las limitaciones de escala correspondientes a su contrato de licencia. Para obtener más información, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Más información**

* xxxx
* xxxx

## Organización de audiencias {#organizing-audiences}

<img width="60px" alt="condiciones" src="assets/icon_audience.svg"/>

Para permitirle enviar mensajes relevantes y eficaces y captar la atención de sus clientes de forma eficaz, Adobe Campaign integra funcionalidades de análisis avanzado y determinación de objetivos.

Gracias a los flujos de trabajo y al editor de consultas, puede crear audiencias a las que se dirigirán las diferentes campañas, en función de la información que tenga sobre ellos, sus actividades, su idioma, sus preferencias o su historial de marketing. Esto le permite filtrar perfiles suscritos por ejemplo, o crear audiencias de destino según un número ilimitado de criterios.

**Más información**

* [Acerca de las audiencias](../../audiences/using/about-audiences.md)
* [Creación de audiencias](../../audiences/using/creating-audiences.md)

## Administración de la privacidad {#privacy-management}

<img width="60px" alt="condiciones" src="assets/icon_privacy.svg"/>

El Reglamento General de Protección de Datos (GDPR) es la nueva normativa sobre privacidad de la Unión Europea que unifica y moderniza los requisitos de protección de datos. El RGPD se aplica a los clientes de Adobe Campaign que albergan datos de sujetos de datos que residan en la UE. Además de las funcionalidades de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimiento, la configuración de retención de datos y las funciones de usuario), estamos tomando esta oportunidad en nuestro rol como procesador de datos para incluir funcionalidades adicionales, para ayudar a facilitar su preparación como controlador de datos para ciertas solicitudes de RGPD.

Consulte esta [guía](https://experienceleague.adobe.com/docs/campaign-classic/using/getting-started/privacy/privacy-management.html?lang=es) para obtener más información sobre las herramientas y funcionalidades que proporciona Adobe Campaign para ayudarle a cumplir con el RGPD.

**Más información**

* xxxx
* xxxx