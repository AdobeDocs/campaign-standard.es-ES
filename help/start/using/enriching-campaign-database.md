---
title: Enriquecimiento de la base de datos
description: Obtenga información sobre los distintos métodos para enriquecer la base de datos.
page-status-flag: nunca activado
uuid: 71f53808-0309-49f6-a4ee-3446eac9758a
contentOwner: lemaitre
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: referencia
topic-tags: about-adobe-campaign
discoiquuid: d8c8a318-9433-4aec-b378-fd0beb50e9fb
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Enriquecimiento de la base de datos{#enriching-the-database}

Campaign Standard ofrece varias herramientas para ayudarle a ampliar su base de datos de marketing. Esta sección detalla los diferentes métodos que puede utilizar para inyectar datos en Campaign, con referencias a las documentaciones dedicadas.

## Importación de datos mediante flujos de trabajo {#importing-data-through-workflows}

Los flujos de trabajo permiten recopilar datos e importarlos a la base de datos de Campaign mediante el uso de [**[!UICONTROL Data management]**](../../automating/using/about-data-management-activities.md) actividades.

La información genérica y las prácticas recomendadas al importar datos a través de flujos de trabajo se presentan en [esta sección](../../automating/using/importing-data.md).

Además, puede configurar plantillas para importar datos. El uso de plantillas de importación es una práctica recomendada si necesita importar archivos con la misma estructura de forma regular.

Puede configurar dos tipos de plantillas:

* **Plantillas** de flujo de trabajo: estos son flujos de trabajo preconfigurados que puede configurar una vez según sus necesidades, y reutilizar cada vez que desee importar datos y actualizar la base de datos.

   En [esta sección](../../automating/using/importing-data.md#example--import-workflow-template)se detalla un ejemplo de plantilla de flujo de trabajo para importar datos.

* **Importar plantillas** de datos: al igual que las plantillas de flujo de trabajo, se trata de plantillas basadas en flujos de trabajo, que se configuran para cargar archivos para actualizar la base de datos. Una vez configurados, se ponen a disposición de los usuarios con una vista simplificada en el menú **[!UICONTROL Profile & audiences]** / **[!UICONTROL Imports]** .

   Para obtener más información sobre las plantillas de datos de importación, consulte la documentación [](../../automating/using/importing-data-with-import-templates.md)dedicada.

## Recopilación de datos de páginas de aterrizaje {#collecting-data-from-landing-pages}

Las páginas de aterrizaje son formularios Web que se pueden utilizar para recopilar datos y crear o actualizar la información existente en la base de datos.

El principio es el siguiente:

* Cree y diseñe su página de aterrizaje agregando campos de entrada para recopilar datos (nombre, apellidos, correo electrónico, etc.).
* Asigne cada campo de entrada con el campo correspondiente de la base de datos.
* Haga que la página de aterrizaje esté disponible en línea a través de un sitio web o de un vínculo directo en un mensaje.

Para obtener más información sobre las páginas de aterrizaje, consulte la documentación [](../../channels/using/about-landing-pages.md)dedicada.

## Sincronización de perfiles de Microsoft Dynamics 365

La integración de Campaign Standard con Microsoft Dynamics 365 le permite pasar datos de contacto de Microsoft Dynamics 365 a la base de datos de Campaign.
Estos contactos están visibles en la lista Perfiles y se pueden dirigir a las campañas de marketing.

For more on this integration, refer to the [dedicated documentation](https://helpx.adobe.com/campaign/kb/acs-ms-dynamics.html).

>[!NOTE]
>
>Tenga en cuenta que el conector Campaign Standard-Microsoft Dynamics 365 está actualmente en disponibilidad limitada y que está sujeto a varias limitaciones, detalladas en la documentación.

## Importación de datos mediante llamadas de API

Las API de Campaign Standard permiten realizar operaciones para actualizar la base de datos, como la creación, actualización o eliminación de perfiles o servicios.

For more on how to use the APIs, refer to the [dedicated documentation](https://docs.campaign.adobe.com/doc/standard/en/api/ACS_API.html).

>[!CAUTION]
>
>Antes de realizar la creación masiva de perfiles o la actualización mediante llamadas de API, compruebe las limitaciones de escala correspondientes a su contrato de licencia. Para obtener más información, consulte [esta página](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html#ITInfrastructureResourcesbyActiveProfilesTiers).
