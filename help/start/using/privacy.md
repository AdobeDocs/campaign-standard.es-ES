---
title: Acerca de la privacidad y las recomendaciones en Adobe Campaign Standard
description: Esta sección trata sobre la administración de la privacidad en Adobe Campaign Standard.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0d7dc73afb2e3b69f461d0e389451c9deabc1f23

---


# Privacy and Consent{#privacy-and-consent}

## Recomendaciones generales {#general-recommendations}

El Adobe Campaign es una poderosa herramienta para recopilar y procesar grandes cantidades de datos, incluida la información personal y los datos confidenciales. Por eso la privacidad debe gestionarse con cuidado.

* Siempre haga un uso responsable y ético de la información personal.

* Abstenerse de enviar correos electrónicos no solicitados, notificaciones push y mensajes SMS (&quot;spam&quot;). Adobe cree firmemente en los principios del marketing autorizado para fomentar el valor y la lealtad de los clientes durante toda su vida y, por lo tanto, prohíbe estrictamente el uso del Adobe Campaign en el envío de mensajes no solicitados.

### Normas de privacidad {#privacy-regulations}

Para gestionar correctamente la privacidad y administrar los datos personales, trabaje dentro de las legislaciones aplicables a la región o regiones en las que opera. Estas normas incluyen:
* [RGPD](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Reglamento general europeo de protección de datos)
* [DPA](https://www.gov.uk/data-protection) (aplicación del RGPD en el Reino Unido)
* [Directiva europea sobre privacidad y comunicaciones electrónicas](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [Ley](https://www.ftc.gov/tips-advice/business-center/guidance/can-spam-act-compliance-guide-business) CAN-SPAM (ley estadounidense que establece las reglas y requisitos para el correo electrónico comercial)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&amp;division=3.&amp;title=1.81.5.&amp;part=4.&amp;chapter=&amp;article=) (California Consumer Privacy Act)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Ley de protección de datos personales de Tailandia)

>[!NOTE]
>
>Para obtener más información sobre cómo se aplican GDPR, CCPA y PDPA a Adobe Campaign, consulte [esta página](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

### Adobe Experience Cloud privacy {#experience-cloud-privacy}

Adobe Campaign forma parte de las soluciones de Adobe Experience Cloud. La forma en que se gestiona la privacidad en Campaña obedece a los principios generales de Adobe Experience Cloud, como los siguientes:

* **Qué información se recopila al utilizar Adobe Experience Cloud**

   Como compañía que utiliza las soluciones de Adobe Experience Cloud, puede elegir qué información desea recopilar y enviar a su cuenta de Adobe Experience Cloud. Algunos ejemplos de los tipos de información que se pueden recopilar son la actividad de navegación web, las direcciones IP, la información de ubicación de dispositivos móviles, las tasas de éxito de campaña, los artículos comprados o colocados en el carro de compras, etc.

   >[!NOTE]
   >
   >Al igual que con todos los productos de Adobe, Campaña recopila información sobre los usuarios de la aplicación y del sitio web. Para obtener más información sobre esto, consulte la Política de privacidad de [Adobe](https://www.adobe.com/privacy/policy.html).

* **Cómo se usa Adobe Experience Cloud para recopilar información**

   * Las soluciones de Adobe Experience Cloud utilizan cookies y tecnologías similares, como señalizaciones web (también conocidas como etiquetas o píxeles), para permitirle recopilar información. For more on cookies and tracking capabilities with Adobe Campaign, see [this section](#tracking-capabilities).
   * También puede utilizar las tecnologías de Adobe Experience Cloud en sus aplicaciones móviles. Para obtener más información sobre el envío de envíos móviles con Campaña, consulte [esta página](https://helpx.adobe.com/es/campaign/kb/acs-mobile.html).

* **Las opciones de privacidad de los usuarios sobre el uso de Adobe Experience Cloud**

   Adobe le pide que proporcione las políticas de privacidad de sus clientes que describen:

   * Sus prácticas de privacidad en relación con Adobe Experience Cloud
   * Cómo los usuarios pueden establecer sus preferencias para la recopilación o el uso de su información en conexión con Adobe Experience Cloud
   >[!NOTE]
   >
   >Al igual que para todos los productos de Adobe, los usuarios de Campaña pueden optar por compartir información recopilada sobre ellos a través de aplicaciones y sitios web. Para obtener más información sobre esto, consulte las preguntas más frecuentes [sobre la información de uso de](https://www.adobe.com/privacy/experience-cloud-usage-info-faq.html)Adobe Experience Cloud.

Para obtener más información sobre la privacidad de Adobe Experience Cloud, consulte [esta página](https://www.adobe.com/privacy/marketing-cloud.html).

## Datos personales y personas {#personal-data}

Al administrar la privacidad, es importante definir qué datos deben manejarse con cuidado y quién debe hacerlo.
* **Datos** personales es información que puede identificar directa o indirectamente a un individuo vivo.
* **Los Datos** Personales Sensibles son información relacionada con la raza, vistas políticas, creencias religiosas, antecedentes penales, información genética, datos de salud, preferencias sexuales, información biométrica, así como afiliación a la unión comercial.

Las [principales legislaciones](#privacy-regulations) se refieren a las diferentes entidades que administran los datos de la siguiente manera:
* A **Data Controller** is the authority that determines the means and purpose of collecting, using, and sharing personal data.
* Un procesador **de** datos es cualquier persona o parte que recopila, utiliza o comparte datos personales según lo indicado por el controlador de datos.
* Se entiende por sujeto **de** datos toda persona viva cuyos datos personales se recopilen, utilicen o compartan y que pueda identificarse, directa o indirectamente, por referencia a dichos datos personales.

Por lo tanto, como compañía que recopila y comparte datos personales, usted es el controlador de datos, sus clientes son los sujetos de datos y el Adobe Campaign actúa como un procesador de datos al tratar sus datos personales como usted lo indica. Tenga en cuenta que, como controlador de datos, es su responsabilidad gestionar la relación con los temas de datos, como al administrar solicitudes [de](#privacy-requests)privacidad.

Al integrar la Campaña con otras soluciones de Experience Cloud en las que se pueden transferir audiencias de un sistema a otro, como el servicio [Destinos de](../../audiences/using/aep-about-audience-destinations-service.md)Audiencia, el servicio [principal](../../integrating/using/about-campaign-analytics-integration.md)Adobe Analytics [, el administrador de](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md)Audiencias o Personas, o con otras soluciones como [Microsoft Dynamics 365](../../integrating/using/configure-microsoft-dynamics-365-for-campaign-integration.md), debe prestar especial atención a la protección de datos personales.

## Adquisición de datos {#data-acquisition}

Adobe Campaign le permite recopilar datos, incluida información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

* Siempre los destinatarios aceptan recibir comunicaciones. Para ello, siga cumpliendo las solicitudes de exclusión lo más rápido posible y verifique el consentimiento a través de un proceso de selección de dobles. Para obtener más información sobre esto, consulte [Administración de la opción de inclusión y de exclusión en la Campaña](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) y [Configuración de un proceso](../../channels/using/setting-up-a-double-opt-in-process.md)de inclusión de dobles.
* No importe listas fraudulentas y utilice trampas para comprobar que el archivo cliente no se está utilizando de forma fraudulenta. Para obtener más información sobre esto, consulte [Uso de trampas](../../sending/using/using-traps.md).
* A través de la administración de derechos y consentimiento, puede rastrear las preferencias de sus destinatarios, así como administrar quién dentro de su organización puede acceder a qué datos. Para obtener más información, consulte [esta sección](#consent).
* Facilite y administre las solicitudes de privacidad de sus destinatarios. Para obtener más información, consulte [esta sección](#privacy-requests).

## Administración de la privacidad {#privacy-management}

La administración de privacidad se refiere a todos los procesos y herramientas que pueden ayudarle a cumplir con las regulaciones de privacidad (RGPD, CCPA, etc.). Obtenga información general sobre qué es la administración de privacidad en [esta página](https://helpx.adobe.com/es/campaign/kb/campaign-privacy-overview.html).

Adobe Campaign le ofrece varios conjuntos de funciones dedicadas a la administración de la privacidad:
* Administración de consentimiento, retención de datos y funciones de usuario. Consulte [esta sección](#consent).
* Solicitudes de privacidad (derecho de acceso y derecho a ser olvidado). Consulte [esta sección](#privacy-requests).
* Exclusión para la venta de información personal (específica de CCPA). Consulte [esta sección](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ccpa).

Las principales capacidades de privacidad en Campaña y un ejemplo de las personas involucradas se presentan en [esta sección](https://helpx.adobe.com/campaign/kb/campaign-privacy-more.html#gdprpersonasandflow).


### Consentimiento, retención y funciones {#consent}

Originalmente, Adobe Campaign oferta características importantes que son esenciales para la privacidad:

* **Gestión** de consentimiento: A través del proceso de administración de suscripciones, puede administrar las preferencias de sus destinatarios y rastrear qué destinatarios han elegido qué tipo de suscripciones. Para obtener más información sobre esto, consulte [Suscripciones](../../audiences/using/about-subscriptions.md) y [Páginas de aterrizaje](../../channels/using/getting-started-with-landing-pages.md).
* **Retención** de datos: Todas las tablas de registro estándar incorporadas tienen períodos de retención preestablecidos, lo que generalmente limita su almacenamiento de datos a 6 meses o menos. Se pueden configurar períodos de retención adicionales con flujos de trabajo. Para obtener más información, póngase en contacto con los consultores o administradores técnicos de Adobe.
* **Administración** de derechos: Adobe Campaign le permite administrar los derechos asignados a los distintos operadores de Campaña mediante diferentes funciones personalizadas o prediseñadas. Esto le permite administrar quién dentro de su compañía puede acceder, modificar o exportar diferentes tipos de datos. Para obtener más información sobre esto, consulte [Acerca de la administración](../../administration/using/about-access-management.md)de acceso.

Para obtener más información sobre estas funciones y cómo administrarlas en Adobe Campaign, consulte [esta página](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#consent).

### Privacy requests {#privacy-requests}

Adobe Campaign proporciona funciones adicionales que le ayudan a facilitar su preparación como controlador de datos para determinadas solicitudes de privacidad:

* El **derecho de acceso** es el derecho del interesado a obtener del controlador de datos la confirmación de si se están procesando o no los datos personales que les conciernen, dónde y por qué.

* El **derecho al olvido** (solicitud de eliminación) autoriza al sujeto de datos a hacer que el controlador de datos borre sus datos personales.

>[!NOTE]
>
>Este conjunto de herramientas está disponible para ayudarle con la conformidad de privacidad de GDPR, CCPA y PDPA. Para obtener más información sobre estas diferentes regulaciones, consulte [esta página](https://helpx.adobe.com/campaign/kb/campaign-privacy-overview.html#whatisgdpr).

<!--* **GDPR** (General Data Protection Regulation) is the European Union’s (EU) privacy law that harmonizes and modernizes data protection requirements. GDPR applies to Adobe Campaign customers who hold data for Data Subjects residing in the EU.

* **CCPA** (California Consumer Privacy Act) provides California residents new rights in regards to their personal information and imposes data protection responsibilities on certain entities whom conduct business in California.

* **Thailand's PDPA** (Personal Data Protection Act) is the new privacy law that harmonizes and modernizes data protection requirements for Thailand. This regulation applies to Adobe Campaign customers who hold data for Data Subjects residing in this country.-->

Las solicitudes **de acceso** y **eliminación** se presentan en [esta página](https://helpx.adobe.com/campaign/kb/acs-privacy.html#righttoaccess). The implementation steps to create these requests are detailed on [this page](https://helpx.adobe.com/campaign/kb/acs-privacy.html#ManagingPrivacyRequests). Tutorials are also available [here](https://docs.adobe.com/content/help/en/campaign-standard-learn/tutorials/privacy/privacy-overview.html).

## Tracking capabilities {#tracking-capabilities}

Thanks to its tracking functionalities, Adobe Campaign enables you to track the behavior of your delivery recipients using session cookies and permanent cookies. For more on tracking, see [this page](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Las regulaciones como el Reglamento General de Protección de Datos (RGPD) establecen que las compañías requieren el acuerdo de los usuarios del sitio web antes de instalar las cookies. You must inform users that your sites are equipped with web tracking tools via an authorization request.

You can also add [tracked links](../../designing/using/links.md#about-tracked-urls) in your messages in order to measure the impact of your delivery and recipient behavior in the [Tracking indicators](../../reporting/using/tracking-indicators.md) built-in report, or create your own [dedicated reports](../../reporting/using/about-dynamic-reports.md).
