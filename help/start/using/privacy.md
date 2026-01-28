---
title: Privacidad y consentimiento en Adobe Campaign Standard
description: Esta sección proporciona una visión general de la privacidad, los datos personales y la administración del consentimiento en Adobe Campaign Standard, así como las herramientas disponibles para administrarlos.
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
feature: Privacy
role: User
level: Intermediate
exl-id: 0fc71c2f-f294-43f7-825c-73ab4d43fcf7
source-git-commit: 6b683ccd93e10f78ff643eed9f374a794c085cb1
workflow-type: ht
source-wordcount: '1377'
ht-degree: 100%

---

# Privacidad y consentimiento{#privacy-and-consent}

## Recomendaciones generales {#general-recommendations}

Adobe Campaign es una potente herramienta para recopilar y procesar cantidades extremadamente grandes de datos, incluida información personal e información confidencial. Por eso, la privacidad debe administrarse cuidadosamente.

* Use la información personal de forma responsable y ética.

* Absténgase de enviar correos electrónicos no solicitados, notificaciones push y mensajes SMS (&quot;spam&quot;). Adobe cree firmemente en los principios del marketing autorizado para fomentar la lealtad y el valor de tiempo de vida del cliente; por lo tanto, Adobe prohíbe estrictamente el uso de Adobe Campaign para la entrega de mensajes no solicitados.

### Normas de privacidad {#privacy-regulations}

Para gestionar correctamente la privacidad y administrar los datos personales, siga la legislación aplicable a la región o regiones en las que opera. Estas normas incluyen lo siguiente:
* [RGPD](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-does-general-data-protection-regulation-gdpr-govern_en) (Reglamento General de Protección de Datos de Europa)
* [DPA](https://www.gov.uk/data-protection) (implementación del RGPD en el Reino Unido)
* [Directiva europea sobre privacidad y comunicaciones electrónicas](https://eur-lex.europa.eu/legal-content/EN/TXT/?uri=CELEX:02002L0058-20091219)
* [CAN-SPAM Act](https://www.ftc.gov/business-guidance/resources/can-spam-act-compliance-guide-business) (ley estadounidense que establece las reglas y requisitos de los correos electrónicos comerciales)
* [CCPA](https://leginfo.legislature.ca.gov/faces/codes_displayText.xhtml?lawCode=CIV&division=3.&title=1.81.5.&part=4.&chapter=&article=) (Ley de Privacidad del Consumidor de California)
* [PDPA](https://secureprivacy.ai/thailand-pdpa-summary-what-businesses-need-to-know/) (Ley de Protección de Datos Personales de Tailandia)

>[!NOTE]
>
>Para obtener más información sobre cómo se aplican el RGPD, la CCPA y la PDPA a Adobe Campaign, consulte [esta página](../../start/using/privacy-management.md#privacy-management-regulations).

### Privacidad de Adobe Experience Cloud {#experience-cloud-privacy}

Adobe Campaign forma parte de las soluciones de Adobe Experience Cloud. La forma en que se gestiona la privacidad en Campaign obedece a los principios generales de Adobe Experience Cloud, como los siguientes:

* **Información que se recopila al utilizar Adobe Experience Cloud**

  Como compañía que utiliza las soluciones de Adobe Experience Cloud, puede elegir qué información desea recopilar y enviar a su cuenta de Adobe Experience Cloud. Algunos ejemplos de los tipos de información que se pueden recopilar son la actividad de navegación web, las direcciones IP, la información de ubicación de dispositivos móviles, las tasas de éxito de una campaña, los artículos comprados o colocados en el carro de compras, etc.

  >[!NOTE]
  >
  >Al igual que con todos los productos de Adobe, Campaign recopila información sobre los usuarios de la aplicación y del sitio web. Para obtener más información sobre esto, consulte la Política de privacidad de [Adobe](https://www.adobe.com/privacy/policy.html).

* **Uso de Adobe Experience Cloud para recopilar información**

   * Las soluciones de Adobe Experience Cloud utilizan cookies y tecnologías similares, como señalizaciones web (también conocidas como etiquetas o píxeles), para permitirle recopilar información. Para obtener más información sobre las cookies y las capacidades de seguimiento con Adobe Campaign, consulte [esta sección](#tracking-capabilities).
   * También puede utilizar las tecnologías de Adobe Experience Cloud en sus aplicaciones móviles. Para obtener más información sobre el envío de envíos móviles con Campaña, consulte [esta página](../../channels/using/mobile-guide.md).

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
* Los **datos personales confidenciales** son información relacionada con el origen étnico, las opiniones políticas, las creencias religiosas, los antecedentes penales, la información genética, los datos de salud, las preferencias sexuales, la información biométrica y la afiliación a sindicatos.

La [legislación principal](#privacy-regulations) se refiere a las diferentes entidades que administran los datos de la siguiente manera:
* Un **controlador de datos** es una autoridad que determina los medios y el propósito de recopilar, utilizar y compartir datos personales.
* Un **procesador de datos** es cualquier persona o parte que recopila, utiliza o comparte datos personales según lo indicado por el controlador de datos.
* Se entiende por **sujeto de datos** toda persona viva cuyos datos personales se recopilen, utilicen o compartan y que pueda identificarse, directa o indirectamente, por referencia a dichos datos personales.

Por lo tanto, como compañía que recopila y comparte datos personales, usted es el controlador de datos, sus clientes son los sujetos de datos y Adobe Campaign actúa como un procesador de datos al tratar sus datos personales como usted lo indica. Tenga en cuenta que, como controlador de datos, es su responsabilidad gestionar la relación con los temas de datos, como al administrar [solicitudes de privacidad](#privacy-requests).

Al integrar Campaign con otras soluciones de Experience Cloud en las que los públicos se pueden transferir de un sistema a otro, [Adobe Analytics](../../integrating/using/about-campaign-analytics-integration.md), [Audience Manager o el servicio principal People](../../integrating/using/sharing-audiences-with-audience-manager-or-people-core-service.md), o con otras soluciones como [Microsoft Dynamics 365](../../integrating/using/d365-acs-get-started.md), debe prestar especial atención a la protección de datos personales.

## Adquisición de datos {#data-acquisition}

Adobe Campaign le permite recopilar datos, incluida la información personal y confidencial. Por lo tanto, es esencial que reciba y supervise el consentimiento de sus destinatarios.

* Los destinatarios siempre deben aceptar recibir comunicaciones. Para ello, siga atendiendo las solicitudes de exclusión lo más rápido posible y verifique el consentimiento a través de un proceso de doble inclusión. Para obtener más información sobre esto, consulte [Administración de la opción de inclusión y de exclusión en Campaign](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md) y [Configuración de un proceso](../../channels/using/setting-up-a-double-opt-in-process.md)de inclusión doble.
* No importe listas fraudulentas ni utilice trampas para comprobar que el archivo cliente no se está utilizando de forma fraudulenta. Para obtener más información sobre esto, consulte [Uso de trampas](../../sending/using/using-traps.md).
* A través de la administración de derechos y consentimiento, puede rastrear las preferencias de sus destinatarios, así como administrar quién dentro de su organización puede acceder a qué datos. Para obtener más información, consulte [esta sección](#consent).
* Facilite y administre las solicitudes de privacidad de sus destinatarios. Para obtener más información, consulte [esta sección](#privacy-requests).

## Administración de la privacidad {#privacy-management}

La administración de la privacidad se refiere a todos los procesos y herramientas que pueden ayudarle a cumplir con las regulaciones de privacidad (RGPD, CCPA, etc.). Obtenga información general sobre qué es la administración de la privacidad en [esta página](../../start/using/privacy-management.md#privacy-management-regulations).

Adobe Campaign le ofrece varios conjuntos de funciones dedicadas a la administración de la privacidad:
* administración de consentimiento, retención de datos y funciones de usuario. Consulte [esta sección](#consent).
* Solicitudes de privacidad (derecho de acceso y derecho a ser olvidado). Consulte [esta sección](#privacy-requests).
* Exclusión para la venta de información personal (específica de la CCPA). Consulte [esta sección](../../start/using/privacy-requests.md#sale-of-personal-information-ccpa).

Las principales funcionalidades de privacidad en Campaign y un ejemplo de las personas implicadas se presentan en [esta sección](#personal-data).


### Consentimiento, retención y funciones {#consent}

En principio, Adobe Campaign ofrece funcionalidades importantes que son esenciales para la privacidad:

* **Gestión del consentimiento**: A través del proceso de administración de suscripciones, puede administrar las preferencias de sus destinatarios y rastrear qué destinatarios han elegido qué tipo de suscripciones. Para obtener más información sobre esto, consulte [Suscripciones](../../audiences/using/about-subscriptions.md) y [Páginas de destino](../../channels/using/getting-started-with-landing-pages.md).
* **Retención de datos**: Todas las tablas de registro integradas tienen períodos de retención preestablecidos, lo que generalmente limita su almacenamiento de datos a 6 meses o menos. Se pueden configurar períodos de retención adicionales con flujos de trabajo. Para obtener más información, póngase en contacto con los consultores o administradores técnicos de Adobe.
* **Administración de derechos**: Adobe Campaign permite administrar los derechos asignados a los distintos operadores de campaña a través de diferentes funciones generadas previamente o personalizadas. Esto le permite administrar qué persona de su compañía puede acceder, modificar o exportar diferentes tipos de datos. Para obtener más información sobre esto, consulte [Acerca de la administración de acceso](../../administration/using/about-access-management.md).

Para obtener más información sobre estas funciones y cómo administrarlas en Adobe Campaign, consulte [esta página](../../start/using/privacy-management.md#consent-retention-roles).

### Solicitudes de privacidad {#privacy-requests}

Adobe Campaign proporciona funciones adicionales que le ayudan a facilitar su preparación como controlador de datos para determinadas solicitudes de privacidad:

* El **derecho de acceso** es el derecho del interesado a obtener del controlador de datos la confirmación de si se están procesando o no los datos personales que les conciernen, dónde y por qué.

* El **Derecho al olvido** (solicitud de eliminación) autoriza al sujeto de datos a hacer que el controlador de datos borre sus datos personales.

>[!NOTE]
>
>Este conjunto de herramientas se encuentra aquí para ayudarle con su cumplimiento de la privacidad de RGDP, CCPA y PDPA. Para obtener más información sobre estas diferentes regulaciones, consulte [esta página](../../start/using/privacy-management.md#privacy-management-regulations).

Las solicitudes de **acceso** y **eliminación** se presentan en [esta página](../../start/using/privacy-management.md#right-access-forgotten). Los pasos de implementación para crear estas solicitudes se detallan en [esta página](../../start/using/privacy-requests.md#about-privacy-requests). También hay Tutoriales disponibles [aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/privacy/privacy-overview.html?lang=es).

## Funcionalidades de seguimiento {#tracking-capabilities}

Gracias a sus funcionalidades de seguimiento, Adobe Campaign le permite supervisar el comportamiento de los destinatarios de la entrega con cookies de sesión y permanentes. Para obtener más información sobre el seguimiento, consulte [esta página](../../sending/using/tracking-messages.md).

>[!NOTE]
>
>Las regulaciones como el Reglamento General de Protección de Datos (RGPD) establecen que las compañías requieren el acuerdo de los usuarios del sitio web antes de instalar las cookies. Debe informar a los usuarios de que los sitios están equipados con herramientas de seguimiento Web mediante una solicitud de autorización.

También puede agregar vínculos [](../../designing/using/links.md#about-tracked-urls) rastreados en los mensajes para medir el impacto del comportamiento de envíos y destinatarios en el informe integrado de indicadores [de](../../reporting/using/tracking-indicators.md) seguimiento o crear sus propios informes [](../../reporting/using/about-dynamic-reports.md)dedicados.
