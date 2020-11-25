---
solution: Campaign Standard
product: campaign
title: Privacidad y consentimiento
description: Obtenga información sobre la privacidad, los datos personales y la gestión de consentimiento en Adobe Campaign Standard
audience: start
content-type: reference
topic-tags: discovering-the-interface
translation-type: tm+mt
source-git-commit: c76f4b6e3bc0feb50e5776836552fdceaff61ea7
workflow-type: tm+mt
source-wordcount: '1657'
ht-degree: 66%

---


# Privacidad y consentimiento {#privacy-and-consent}

## Recomendaciones generales {#general-recommendations}

Adobe Campaign es una potente herramienta para recopilar y procesar cantidades extremadamente grandes de datos, incluida información personal e información confidencial. Por eso, la privacidad debe administrarse cuidadosamente.

* Use la información personal de forma responsable y ética.

* Absténgase de enviar correos electrónicos no solicitados, notificaciones push y mensajes SMS (&quot;spam&quot;). Adobe cree firmemente en los principios del marketing autorizado para fomentar la lealtad y el valor de tiempo de vida del cliente; por lo tanto, Adobe prohíbe estrictamente el uso de Adobe Campaign para la entrega de mensajes no solicitados.

### Normas de privacidad {#privacy-regulations}

Para gestionar correctamente la privacidad y administrar los datos personales, siga la legislación aplicable a la región o regiones en las que opera. Estas normas incluyen lo siguiente:
* [RGPD](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Reglamento general de protección de datos de Europa)
* [DPA](https://www.gov.uk/data-protection) (aplicación del RGPD en el Reino Unido)
* [Directiva europea sobre privacidad y comunicaciones electrónicas](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) (ley estadounidense que establece las reglas y requisitos de los correos electrónicos comerciales)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (Ley de Privacidad del Consumidor de California)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Ley de Protección de Datos Personales de Tailandia)

>[!NOTE]
>
>For more on how GDPR, CCPA, PDPA, and LGPD apply to Adobe Campaign, see [this section](../../start/using/privacy-management.md#privacy-management-regulations).

### Privacidad de Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign forma parte de las soluciones de Adobe Experience Cloud. La forma en que se maneja la privacidad en Campaña obedece los principios generales de Adobe Experience Cloud, como los siguientes:

* **Información que se recopila al utilizar Adobe Experience Cloud**

   Como compañía que utiliza las soluciones de Adobe Experience Cloud, puede elegir qué información desea recopilar y enviar a su cuenta de Adobe Experience Cloud. Algunos ejemplos de los tipos de información que se pueden recopilar son la actividad de navegación web, las direcciones IP, la información de ubicación de dispositivos móviles, las tasas de éxito de una campaña, los artículos comprados o colocados en el carro de compras, etc.

   >[!NOTE]
   >
   >Al igual que con todos los productos de Adobe, Campaign recopila información sobre los usuarios de la aplicación y del sitio web. Para obtener más información sobre esto, consulte la Política de privacidad de [Adobe](https://www.adobe.com/es/privacy/policy.html).

* **Uso de Adobe Experience Cloud para recopilar información**

   * Las soluciones de Adobe Experience Cloud utilizan cookies y tecnologías similares, como señalizaciones web (también conocidas como etiquetas o píxeles), para permitirle recopilar información. Para obtener más información sobre las cookies y las capacidades de seguimiento con Adobe Campaign, consulte [esta sección](#tracking-capabilities).
   * También puede utilizar las tecnologías de Adobe Experience Cloud en sus aplicaciones móviles. Para obtener más información sobre el envío de envíos móviles con Campaña, consulte [esta página](https://helpx.adobe.com/es/campaign/kb/acs-mobile.html).

* **Opciones de privacidad de los usuarios sobre el uso de Adobe Experience Cloud**

   Adobe le pide que proporcione políticas de privacidad a sus clientes que describan lo siguiente:

   * Sus prácticas en cuanto a privacidad en relación con Adobe Experience Cloud
   * Cómo pueden los usuarios definir sus preferencias para la recopilación o el uso de su información en conexión con Adobe Experience Cloud

   >[!NOTE]
   >
   >Al igual que con todos los productos de Adobe, los usuarios de Campaign pueden optar por compartir información recopilada sobre ellos a través de aplicaciones y sitios web. Para obtener más información sobre esto, consulte las [Preguntas frecuentes sobre la información de uso de Adobe Experience Cloud](https://www.adobe.com/es/privacy/experience-cloud-usage-info-faq.html).

Para obtener más información sobre la privacidad de Adobe Experience Cloud, consulte [esta página](https://www.adobe.com/es/privacy/marketing-cloud.html).

## Datos personales y personas {#personal-data}

Al administrar la privacidad, es importante definir qué datos deben manejarse con cuidado y quién debe hacerlo.
* Los **datos personales** son información que puede identificar directa o indirectamente a un individuo.
* Los **datos personales confidenciales** son información relacionada con la raza, las opiniones políticas, las creencias religiosas, los antecedentes penales, la información genética, los datos de salud, las preferencias sexuales, la información biométrica, y la afiliación a sindicatos.

When integrating Campaign with other Experience Cloud solutions where audiences can be transferred from one system to another, such as the [Audience Destinations service](../../audiences/using/aep-about-audience-destinations-service.md), [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager or People core service](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md), or with other solutions such as [Microsoft Dynamics 365](../../integrating/using/working-with-campaign-standard-and-microsoft-dynamics-365.md), you need to pay extra care to personal data protection.

The [main regulations](#privacy-regulations) refer to the different entities that manage data as follows:
* Un **controlador de datos** es una autoridad que determina los medios y el propósito de recopilar, utilizar y compartir datos personales.
* Un **procesador de datos** es cualquier persona o parte que recopila, utiliza o comparte datos personales según lo indicado por el controlador de datos.
* Se entiende por **sujeto de datos** toda persona viva cuyos datos personales se recopilen, utilicen o compartan y que pueda identificarse, directa o indirectamente, por referencia a dichos datos personales.

Por lo tanto, como compañía que recopila y comparte datos personales, usted es el controlador de datos, sus clientes son los sujetos de datos y Adobe Campaign actúa como un procesador de datos al tratar sus datos personales como usted lo indica. Tenga en cuenta que, como controlador de datos, es su responsabilidad gestionar la relación con los temas de datos, como al administrar [solicitudes de privacidad](#privacy-requests).

### Caso de uso {#use-case-scenario}

Para ilustrar cómo interactúan las distintas personas, aquí se muestra un ejemplo de un caso de uso de la experiencia del cliente de RGPD de alto nivel.

En este ejemplo, una compañía aérea es el cliente de Adobe Campaign. Esta compañía es el **controlador** de datos y todos los clientes de la compañía de aerolíneas son **sujetos** de datos. Laura en este caso particular es cliente de la compañía aérea.

Estas son las distintas personalidades utilizadas en este ejemplo:

* **Laura** es el sujeto **de** datos. Ella es la destinatario que recibe mensajes de la compañía aérea. Laura puede ser una viajera frecuente, pero puede decidir en algún momento que no quiere publicidad personalizada o mensajes de marketing de la compañía aérea. Ella pedirá a la compañía aérea (según su proceso) que borre su número de viajero frecuente.

* **Anne** es la controladora **de** datos de la compañía aérea. Recibe la solicitud de Laura, recupera los ID útiles solicitados para identificar al sujeto de datos y envía la solicitud en Adobe Campaign.

* **Adobe Campaign** es el procesador **de datos**.

![](assets/privacy-gdpr-flow.png)

Este es el flujo general para este caso de uso:

1. El sujeto **** de datos (Laura) envía una solicitud de RGPD al controlador **de** datos por correo electrónico, atención al cliente o un portal web.

1. El controlador **de datos** (Anne) envía la solicitud de RGPD a la Campaña a través de la interfaz o mediante una API.

1. Una vez que el procesador **de** datos (Adobe Campaign) recibe la información, toma medidas en relación con la solicitud del RGPD y envía una respuesta o acuse de recibo al controlador **de** datos (Anne).

1. A continuación, el **controlador** de datos (Anne) revisa la información y la envía de vuelta al sujeto **de** datos (Laura).

## Adquisición de datos {#data-acquisition}

Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

* Los destinatarios siempre deben aceptar recibir comunicaciones. Para ello, siga atendiendo las solicitudes de exclusión lo más rápido posible y verifique el consentimiento a través de un proceso de doble inclusión. Para obtener más información sobre esto, consulte [Administración de la opción de inclusión y de exclusión en la Campaña](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) y [Configuración de un proceso](../../channels/using/setting-up-a-double-opt-in-process.md)de inclusión de dobles.
* No importe listas fraudulentas y utilice trampas para comprobar que el archivo cliente no se está utilizando de forma fraudulenta. Para obtener más información sobre esto, consulte [Uso de trampas](../../sending/using/using-traps.md).
* A través de la administración de derechos y consentimiento, puede rastrear las preferencias de sus destinatarios, así como administrar quién dentro de su organización puede acceder a qué datos. Para obtener más información, consulte [esta sección](#consent).
* Facilite y administre las solicitudes de privacidad de sus destinatarios. Para obtener más información, consulte [esta sección](#privacy-requests).

## Administración de la privacidad {#privacy-management}

La administración de la privacidad se refiere a todos los procesos y herramientas que pueden ayudarle a cumplir con las regulaciones de privacidad (RGPD, CCPA, etc.). Get an overview of what Privacy management is on [this page](../../start/using/privacy-management.md).

Adobe Campaign le ofrece varios conjuntos de funciones dedicadas a la administración de la privacidad:
* administración de consentimiento, retención de datos y funciones de usuario. Consulte [esta sección](#consent).
* Solicitudes de privacidad (derecho de acceso y derecho a ser olvidado). Consulte [esta sección](#privacy-requests).
* Exclusión para la venta de información personal (específica de la CCPA). Consulte [esta sección](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html#ccpa).

Las principales funcionalidades de privacidad en Campaign y un ejemplo de las personas implicadas se presentan en [esta sección](https://helpx.adobe.com/es/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Consentimiento, retención y funciones {#consent}

En principio, Adobe Campaign ofrece funcionalidades importantes que son esenciales para la privacidad:

* **Gestión del consentimiento**: A través del proceso de administración de suscripciones, puede administrar las preferencias de sus destinatarios y rastrear qué destinatarios han elegido qué tipo de suscripciones. Para obtener más información sobre esto, consulte [Suscripciones](../../audiences/using/about-subscriptions.md) y [Páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md).
* **Retención de datos**: Todas las tablas de registro estándar incorporadas tienen períodos de retención preestablecidos, lo que generalmente limita su almacenamiento de datos a 6 meses o menos. Se pueden configurar períodos de retención adicionales con flujos de trabajo. Para obtener más información, póngase en contacto con los consultores o administradores técnicos de Adobe.
* **Administración de derechos**: Adobe Campaign permite administrar los derechos asignados a los distintos operadores de campaña a través de diferentes funciones generadas previamente o personalizadas. Esto le permite administrar qué persona de su compañía puede acceder, modificar o exportar diferentes tipos de datos. Para obtener más información sobre esto, consulte [Acerca de la administración de acceso](../../administration/using/about-access-management.md).

For more on these features and how to manage them in Adobe Campaign, see [this section](../../start/using/privacy-management.md#consent-retention-roles).

### Solicitudes de privacidad {#privacy-requests}

Adobe Campaign proporciona funciones adicionales que le ayudan a facilitar su preparación como controlador de datos para determinadas solicitudes de privacidad:

* El **derecho de acceso** es el derecho del interesado a obtener del controlador de datos la confirmación de si se están procesando o no los datos personales que les conciernen, dónde y por qué.

* El **derecho al olvido** (solicitud de eliminación) autoriza al sujeto de datos a hacer que el controlador de datos borre sus datos personales.

The **Access** and **Delete** requests are presented in [this section](../../start/using/privacy-management.md#right-access-forgotten).

Los pasos de implementación para crear estas solicitudes se detallan en [esta sección](../../start/using/privacy-requests.md). También hay Tutorials disponibles [aquí](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html).

## Capacidades de seguimiento {#tracking-capabilities}

Gracias a sus funciones de seguimiento, Adobe Campaign le permite rastrear el comportamiento de sus destinatarios de envío mediante cookies de sesión y cookies permanentes. For more on tracking, see [this section](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Las regulaciones como el reglamento general de protección de datos (RGPD) establecen que las compañías requieren el acuerdo de los usuarios del sitio web antes de instalar las cookies. Debe informar a los usuarios de que los sitios están equipados con herramientas de seguimiento Web mediante una solicitud de autorización.

También puede agregar vínculos [](../../designing/using/links.md#about-tracked-urls) rastreados en los mensajes para medir el impacto del comportamiento de envíos y destinatarios en el informe integrado de indicadores [de](../../reporting/using/tracking-indicators.md) seguimiento o crear sus propios informes [](../../reporting/using/about-dynamic-reports.md)dedicados.
