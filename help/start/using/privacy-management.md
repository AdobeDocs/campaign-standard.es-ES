---
title: Administración de privacidad en Adobe Campaign Standard
description: Obtenga más información sobre las funciones de Adobe Campaign Standard para administrar la privacidad.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 2dc4ac62e3b10753f7b8681d86cfe7f3b3a30a20
workflow-type: tm+mt
source-wordcount: '928'
ht-degree: 38%

---


# Administración de la privacidad {#privacy-management}

Adobe Campaign ofrece un conjunto de herramientas para ayudarle a cumplir con las normas de privacidad (incluye el RGPD, la CCPA, la PDPA y la LGPD).

* This section presents general information on what Privacy management is and the features provided by Adobe Campaign to manage the [Right to Access and Right to be Forgotten](#right-access-forgotten).

* También contiene información sobre las características importantes para administrar la privacidad ([consentimiento, retención de datos y funciones](#consent-retention-roles)de usuario), así como prácticas recomendadas para ayudarlo a cumplir con la privacidad al utilizar Adobe Campaign.

## Regulaciones sobre administración de la privacidad {#privacy-management-regulations}

Las funciones de Adobe Campaign le ayudan a cumplir con las siguientes regulaciones:

* **El RGPD (** reglamento general de protección de datos[](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en)) es la ley de privacidad de la Unión Europea (UE) que armoniza y moderniza los requisitos de protección de datos de los países de la UE.
* **La CCPA** ([Ley de Privacidad del Consumidor de California](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=)) proporciona a los residentes de California nuevos derechos respecto a su información personal e impone responsabilidades de protección de datos para las entidades que operen en California.
* **PDPA** (Ley[de Protección de Datos](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/)Personales) es la nueva ley de privacidad que armoniza y moderniza los requisitos de protección de datos para Tailandia.
* **La LGPD** ([ley general de protección de datos](https://iapp.org/media/pdf/resource_center/Brazilian_General_Data_Protection_Law.pdf)) entrará en vigor a principios de 2021 para todas las compañías que recopilen o procesen datos personales en Brasil.

Todas estas normativas se aplican a los clientes de Adobe Campaign que poseen datos de sujetos de datos residentes en las regiones o países respectivos antes mencionados (UE, California, Tailandia y Brasil).

>[!NOTE]
>
>Para obtener más información sobre los datos personales y las distintas entidades que administran los datos (controlador de datos, procesador de datos y sujeto de datos), consulte [Datos personales y personas](../../start/using/privacy.md#personal-data).

## Right to Access and Right to be Forgotten {#right-access-forgotten}

Para ayudarle a facilitar su preparación para la privacidad, Adobe Campaign le permite gestionar solicitudes de **acceso** y **eliminación** .

* The **Right to Access** is the right for the Data Subject to obtain from the Data Controller confirmation as to whether or not personal data concerning them is being processed, where and for what purpose. El controlador de datos proporciona una copia de los datos personales de forma gratuita y en formato electrónico.

* Also known as Data Erasure, the **Right to be Forgotten** (delete request) entitles the Data Subject to have the Data Controller erase his/her personal data, cease further dissemination of the data, and potentially have third parties halt processing of the data.

Para obtener información sobre cómo crear solicitudes **de acceso** y **eliminación** y cómo procesarlas, consulte los pasos [de](../../start/using/privacy-requests.md#about-privacy-requests)implementación.

Tutorials on Privacy management in Campaign Standard are also available [here](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=en#privacy).

## Consentimiento, retención y funciones {#consent-retention-roles}

Además de las capacidades más recientes de **Derecho de acceso** y **Derecho al olvido** , Adobe Campaign oferta otras características importantes que son esenciales para la privacidad:

* [Gestión](#consent-management)de consentimiento: Funcionalidad de suscripción para la administración de preferencias
* [Retención](#data-retention)de datos: períodos de retención de datos en todas las tablas de registro estándar, se pueden configurar períodos de retención adicionales con flujos de trabajo
* [Gestión de derechos](#rights-management): acceso a los datos administrado mediante el derecho asignado 

### Gestión de consentimiento {#consent-management}

El consentimiento implica la aceptación por parte del sujeto de datos del procesamiento de los datos personales relacionados con un sujeto de datos. La obtención del consentimiento necesario para ese procesamiento es responsabilidad del controlador de datos. Aunque Adobe Campaign puede proporcionar algunas funciones para ayudar a un cliente a administrar el consentimiento relacionado con el servicio, Adobe no es responsable del consentimiento. Los clientes deben trabajar con sus propios departamentos legales para determinar sus propios procesos y prácticas para cualquier consentimiento necesario.

Las funciones que ayudan a administrar algunos aspectos del consentimiento han sido fundamentales para Adobe Campaign desde el principio. A través del proceso de administración de suscripciones, los clientes pueden rastrear qué destinatarios han elegido qué tipo de suscripciones, ya sean boletines informativos, promociones diarias o semanales, o cualquier otro tipo de programa de mercadotecnia.

![](assets/privacy-consent-management.png)

Para obtener más información sobre la administración de consentimientos, consulte [Acerca de las suscripciones](../../audiences/using/about-subscriptions.md) y [Introducción a las páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md).

Además de las herramientas de Gestión de Consentimiento proporcionadas por Adobe Campaign, usted tiene la posibilidad de rastrear si un consumidor ha optado por la venta de Información Personal. Consulte [esta sección](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

### Retención de datos {#data-retention}

En cuanto a la retención, las tablas de registro integradas en Campaña tienen períodos de retención preestablecidos, lo que generalmente limita su almacenamiento de datos a seis meses o menos.

A continuación se muestran los valores de retención predeterminados para las tablas predeterminadas. Tenga en cuenta que los administradores técnicos de Adobe configuran los ajustes de retención durante la implementación y los valores pueden variar en función de los requisitos de los clientes.

* **Seguimiento consolidado**: 6 meses
* **Registros de envío**: 6 meses
* **Registros de seguimiento**: 6 meses
* **Eventos**: 1 mes
* **Estadísticas del procesamiento de eventos**: 6 meses
* **Eventos archivados**: 6 meses
* **Entidades** temporales: 7 días
* **Eventos de mapa ignorados**: 1 mes
* **Alertas de envío**: 1 mes
* **Registro de exportaciones:** 6 meses

Y de manera similar a eliminar, utilizando la funcionalidad estándar del flujo de trabajo, es posible configurar períodos de retención para cualquier tabla personalizada.

Póngase en contacto con los consultores o administradores técnicos de Adobe para obtener más información sobre la retención o si necesita configurar la retención para tablas personalizadas.

### Gestión de derechos {#rights-management}

Adobe Campaign permite administrar los derechos asignados a los distintos operadores de campaña a través de diferentes funciones creadas previamente o personalizadas.

Una ventaja es que permite administrar que empleados dentro de su empresa pueden acceder a distintos tipos de datos. Por ejemplo, puede tener diferentes especialistas en marketing que abarquen los distintos geos y que cada especialista en marketing solo pueda acceder a los datos de su público.

De igual modo, esta funcionalidad también le permite configurar diferentes funciones para cada usuario, como limitar quién puede enviar envíos o más relevantes para la administración de privacidad, que pueden modificar o exportar datos.

![](assets/privacy-user-management.png)

For more on access management, see [this section](../../administration/using/about-access-management.md).