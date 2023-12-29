---
title: Personalización de listas
description: '"Aprenda a personalizar la visualización y a actuar en las pantallas de lista de Adobe Campaign Standard: ordenar, filtrar, eliminar o duplicar elementos. Las pantallas de listas muestran elementos de uno o varios recursos determinados".'
audience: start
content-type: reference
topic-tags: discovering-the-interface
source-git-commit: bee4da592e0b3727949bc44c6e41b81d4e7e73d4
workflow-type: tm+mt
source-wordcount: '775'
ht-degree: 6%

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

Los perfiles de Adobe Campaign representan todos los contactos almacenados en la base de datos. Cada perfil corresponde a una entrada en la base de datos que contiene la información necesaria para que ese perfil se oriente, califique y rastree individualmente. Esto significa que un perfil puede ser: un cliente, un cliente potencial, una persona suscrita a un boletín, un destinatario, un usuario o cualquier otra denominación según la organización.

**Más información**

* [Acerca de los perfiles](../../audiences/using/about-profiles.md)
* [Acceso al número de perfiles activos de la organización](../../audiences/using/active-profiles.md)

## Enriquecimiento de la base de datos {#populating-database}

<img width="60px" alt="condiciones" src="assets/icon_populate.svg"/>

Campaign Standard ofrece varias herramientas para ayudarle a ampliar su base de datos de marketing. Esta sección detalla los diferentes métodos que puede utilizar para insertar datos en Campaign, con referencias a la documentación dedicada.

### Importación de datos mediante flujos de trabajo {#importing-data-through-workflows}

Los flujos de trabajo le permiten recopilar datos e importarlos en la base de datos de Campaign mediante el uso de [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) actividades. La información genérica y las prácticas recomendadas al importar datos a través de flujos de trabajo se presentan en [esta sección](../../automating/using/about-data-import-and-export.md).

Además, puede configurar plantillas para importar datos. El uso de plantillas de importación es una práctica recomendada para importar archivos con la misma estructura de forma regular. Puede configurar dos tipos de plantillas:

* **Plantillas de flujo de trabajo**: se trata de flujos de trabajo preconfigurados que se pueden configurar una vez según sus necesidades y reutilizar cada vez que desee importar datos y actualizar la base de datos. Un ejemplo de plantilla de flujo de trabajo para importar datos se detalla en [esta sección](../../automating/using/creating-import-workflow-templates.md).

* **Importar plantillas de datos**: al igual que las plantillas de flujo de trabajo, estas son plantillas basadas en flujos de trabajo que se configuran para cargar archivos y actualizar la base de datos. Una vez configuradas, están disponibles para los usuarios con una vista simplificada en la **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** menú. Para obtener más información sobre la importación de plantillas de datos, consulte la [documentación dedicada](../../automating/using/importing-data-with-import-templates.md).

### Recopilación de datos de páginas de aterrizaje {#collecting-data-from-landing-pages}

Las páginas de aterrizaje son formularios web que se pueden utilizar para recopilar datos y crear o actualizar la información existente en la base de datos. El principio es el siguiente:

* Cree y diseñe su página de aterrizaje añadiendo campos de entrada para recopilar datos (nombre, apellidos, correo electrónico, etc.).
* Asigne cada campo de entrada con el campo correspondiente de la base de datos.
* Hacer que la página de aterrizaje esté disponible en línea a través de un sitio web o mediante un vínculo directo a un mensaje.

Para obtener más información sobre las páginas de aterrizaje, consulte [documentación dedicada](../../channels/using/getting-started-with-landing-pages.md).

**Más información**

* xxxx
* xxxx

### Sincronización de perfiles de Microsoft Dynamics 365

La integración de Campaign Standard con Microsoft Dynamics 365 le permite pasar datos de contacto de Microsoft Dynamics 365 a la base de datos de Campaign.
Estos contactos se pueden ver en la lista Perfiles y se pueden segmentar en campañas de marketing. Para obtener más información, consulte [documentación dedicada](../../integrating/using/d365-acs-get-started.md).

>[!NOTE]
>
>Tenga en cuenta que el conector de Campaign Standard-Microsoft Dynamics 365 está actualmente en disponibilidad limitada y que está sujeto a varias limitaciones, detalladas en la documentación.

**Más información**

* xxxx
* xxxx

### Importación de datos mediante llamadas API

Las API de Campaign Standard le permiten realizar operaciones para actualizar la base de datos, como la creación, actualización o eliminación de perfiles o servicios. Para obtener más información sobre cómo utilizar las API, consulte la [documentación dedicada](../../api/using/get-started-apis.md).

>[!CAUTION]
>
>Antes de realizar la creación o actualización masiva de perfiles mediante llamadas a la API, compruebe las limitaciones de escala correspondientes a su acuerdo de licencia. Para obtener más información, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).

**Más información**

* xxxx
* xxxx

## Organización de las audiencias {#organizing-audiences}

<img width="60px" alt="condiciones" src="assets/icon_audience.svg"/>

Para permitirle enviar mensajes relevantes y eficaces, y atraer a sus clientes de forma eficaz, Adobe Campaign integra funcionalidades avanzadas de análisis y segmentación.

Gracias a los flujos de trabajo y al editor de consultas, puede crear audiencias a las que se dirigen las diferentes campañas, según la información que tenga sobre ellas, sus actividades, su idioma, sus preferencias o su historial de marketing. Esto le permite filtrar los perfiles suscritos, por ejemplo, o crear audiencias de destino con un número ilimitado de criterios.

**Más información**

* [Acerca de las audiencias](../../audiences/using/about-audiences.md)
* [Creación de audiencias](../../audiences/using/creating-audiences.md)

## Administración de la privacidad {#privacy-management}

<img width="60px" alt="condiciones" src="assets/icon_privacy.svg"/>

El RGPD es la nueva ley de privacidad de la Unión Europea (UE) que armoniza y moderniza los requisitos de protección de datos. El RGPD se aplica a los clientes de Adobe Campaign que albergan datos de sujetos de datos que residan en la UE. Además de las funciones de privacidad ya disponibles en Adobe Campaign (incluida la administración de consentimientos, la configuración de retención de datos y las funciones de usuario), aprovechamos esta oportunidad en nuestra función de procesador de datos para incluir funciones adicionales que le ayudarán a prepararse como controlador de datos para determinadas solicitudes de RGPD.

Consulte [esta sección](../../start/using/privacy.md) para obtener más información sobre las herramientas y funcionalidades que proporciona Adobe Campaign para ayudarle a cumplir con el RGPD.

**Más información**

* xxxx
* xxxx