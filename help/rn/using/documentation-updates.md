---
title: Actualizaciones de la documentación
description: Obtenga información acerca de las últimas actualizaciones de la documentación de Adobe Campaign Standard
feature: Overview
role: User
level: Beginner
exl-id: 3f77825e-cb98-4cb1-9775-a8b6995e9da1
source-git-commit: 6530ca1726a2aff18c5be9566d8008c317918e64
workflow-type: tm+mt
source-wordcount: '7224'
ht-degree: 100%

---

# Actualizaciones de la documentación{#documentation-updates}

Además de las [Notas de la versión](../../rn/using/release-notes.md) de Adobe Campaign, esta página enumera todas las nuevas actualizaciones de la documentación de Adobe Campaign Standard.

## Noviembre de 2022 {#doc-updates-november-2022}

Se ha añadido una nota para recomendar evitar espacios en blanco en el campo ID de los envíos. [Más información](../../channels/using/creating-an-email.md)

Se ha añadido información en la página de **[!UICONTROL Extract file]** actividad del flujo de trabajo para extraer datos a un archivo CSV con una codificación específica. [Más información](../../automating/using/extract-file.md)

## Versión 22.3: otoño/invierno de 2022 {#release-22-3}

Se han publicado las notas de la versión 22.3 de Campaign Standard de otoño/invierno. [Más información](release-notes.md)

<!--Data retention periods have been updated to reflect changes coming with 22.3 release. [Read more](../../administration/using/data-retention.md)-->


## Versión 22.2 de junio de 2022 {#release-22-2}

**Mejoras incluidas en la versión**

**Servicio de notificación de Adobe**: Campaign viene con el servicio de notificación de Adobe que permite a las soluciones de Experience Cloud alertar a los usuarios entre Experience Cloud sobre las actividades que son importantes que conozcan. [Más información](../../administration/using/sending-internal-notifications.md).

**Otros cambios**

Las integraciones con Adobe Experience Platform Data Connector y con el servicio Audience Destinations ya no se utilizan. [Más información](deprecated-features.md)

Se ha detallado el uso del modo de prueba SMTP. [Más información](../../administration/using/configuring-email-channel.md#smtp-test-mode)

## Marzo de 2022 {#doc-updates-march-2022}

Se ha incluido una nota para especificar que al enviar pruebas utilizando la sustitución de perfiles se añaden registros a los registros de los perfiles seleccionados. [Más información](../../sending/using/testing-messages-using-target.md)

## Versión 22.1: febrero de 2022 {#release-22-1}

**Mejoras incluidas en la versión**

Se ha mejorado el mecanismo de reintentos de los envíos, incluido el contenido importado de una dirección URL. [Más información](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

Nivel de acceso actualizado de las opciones que controlan la auditoría: las opciones anteriores para activar/desactivar [Pista de auditoría](../../administration/using/audit.md) no eran accesibles para los [administradores funcionales](../../administration/using/users-management.md#functional-administrators). Con este cambio, se modifica el nivel de acceso de la auditoría para proporcionar control a los administradores funcionales. [Más información](../../administration/using/audit.md#enable-disable-audit)

El nuevo desplegable **Historial de trabajos** se ha añadido al panel de mensajes. [Más información](../../sending/using/monitoring-a-delivery.md)

**Otros cambios**

Se ha añadido una nota de advertencia sobre palabras clave que activan las respuestas automáticas de SMS: solo deben contener caracteres alfanuméricos. [Más información](../../channels/using/managing-incoming-sms.md)

Se ha añadido una nota a la sección de correo electrónico de las pruebas A/B: si la población total es inferior a 50 000, cada variante debe representar al menos el 10 % de la población total. De lo contrario, los registros mostrarán una advertencia. [Más información](../../channels/using/designing-an-a-b-test-email.md)

Se ha actualizado la descripción de la opción **[!UICONTROL Delete the source files after transfer]** en la actividad **Transferir archivo**, incluido un recordatorio para monitorizar manualmente el tamaño del contenido archivado en el directorio SFTP en caso de que la opción no esté seleccionada. [Más información](../../automating/using/transfer-file.md)

Se han actualizado todos los vínculos obsoletos de las secciones **Privacidad**. [Más información](../../start/using/privacy.md)

Se ha añadido un vínculo directo a la documentación de Panel de control de Campaign en la tabla de contenidos de la documentación de Campaign Standard.

## Versión 21.3: septiembre de 2021 {#release-21-3---september-2021}

**Nuevas funcionalidades incluidas en la versión**

Mejora de la interfaz de Experience Cloud unificada: [más información](../../start/using/interface-description.md#top-bar)

Nueva capacidad de pista de auditoría: [más información](../../administration/using/audit.md)

Modo de diagnóstico del flujo de trabajo: [más información](../../automating/using/managing-execution-options.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido una nueva sección sobre cómo quitar una dirección de la lista de cuarentena. [Más información](../../sending/using/understanding-quarantine-management.md#removing-a-quarantined-address)

Se ha aclarado la sección **Cuarentena frente a Lista de bloqueados**. [Más información](../../sending/using/understanding-quarantine-management.md#quarantine-vs-denylist)

## Julio de 2021 {#doc-updates-july-2021}

Se ha añadido una nueva sección para describir cómo puede permitir a los usuarios suscribirse o cancelar la suscripción de varios servicios desde una sola página de aterrizaje. [Más información](../../channels/using/managing-landing-page-form-data.md#multiple-subscriptions)

Se ha actualizado y aclarado la sección **Administración de los datos del formulario de la página de aterrizaje**. [Más información](../../channels/using/managing-landing-page-form-data.md)

## Versión 21.2: junio de 2021 {#release-21-2---june-2021}

**Nuevas funciones incluidas en la versión**

Validación de páginas de aterrizaje: ahora puede añadir una opción de acuerdo obligatoria a sus páginas de aterrizaje. [Más información](../../channels/using/managing-landing-page-form-data.md#agreement-checkbox)

La sección **Tamaño de correo electrónico** se ha actualizado con información sobre el tamaño máximo de un correo electrónico, que ahora se establece en 100 MB de forma predeterminada. [Más información](../../sending/using/design-and-personalize.md#email-size)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido información sobre cómo cambiar la asignación de destinatario en una notificación push transaccional. [Más información](../../channels/using/transactional-push-notifications.md#change-target-mapping)

## Mayo de 2021 {#doc-updates-may-2021}

Se ha actualizado la sección del informe **Perfiles activos**. [Más información](../../audiences/using/active-profiles.md)

La página **Planificación de versiones** se ha actualizado con nuevas fechas. [Más información](../../rn/using/release-planning.md)


## Abril de 2021 {#doc-updates-april-2021}

Se ha incluido una nueva sección sobre cómo usar Orígenes y destinos de Adobe Experience Platform para compartir datos entre Campaign Standard y Adobe Real-time Customer Data Platform (RTCDP). [Más información](../../integrating/using/get-started-sources-destinations.md)

## Marzo de 2021 {#doc-updates-march-2021}

Nueva página de **Opciones de ayuda y asistencia**. [Más información](../../support.md)

La sección que enumera los pasos clave para enviar un mensaje se ha mejorado con información y referencias adicionales. [Más información](../../channels/using/key-steps-to-send-a-message.md)

Se ha añadido información para especificar que, al seleccionar una audiencia en una consulta, su definición se copia y no se hace referencia a ella. [Obtenga más información](../../audiences/using/selecting-an-audience-in-a-message.md)

La información relacionada con el servicio Destinos de audiencia y el Conector de datos de Adobe Experience Platform se ha reagrupado en una nueva sección. [Más información](../../integrating/using/aep-about-audience-destinations-service.md)

Ahora, la fuente de datos de **ID declarado** también se puede utilizar con la integración del servicio principal Personas. Se ha añadido información en la documentación de la integración de Campaign-Audience Manager o del servicio principal Personas. [Más información](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Se ha añadido información sobre cómo implementar el seguimiento local para la aplicación móvil. [Más información](../../administration/using/local-tracking.md)

La sección [Entrega](../../sending/using/about-deliverability.md) se ha actualizado y ahora incluye vínculos a la nueva [Guía de prácticas recomendadas de entrega de Adobe](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/introduction.html?lang=es). Toda la información genérica relacionada con la capacidad de envío que se puede aplicar a varias soluciones de Adobe se ha trasladado al [Apéndice de la Guía de prácticas recomendadas](https://experienceleague.adobe.com/docs/deliverability-learn/deliverability-best-practice-guide/additional-resources/general-resources.html?lang=es#additional-resources).

## Versión 21.1: febrero de 2021 {#release-21-1---february-2021}

**Nuevas funcionalidades incluidas en la versión**

Servicio de comentarios de correo electrónico: [Más información](../../sending/using/confirming-the-send.md#message-indicators)

Mejoras en la integración de Adobe Experience Manager: [Más información](../../integrating/using/creating-multilingual-email-aem.md)

Interfaz de Experience Cloud unificada: [Más información](../../start/using/interface-description.md#top-bar)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido información sobre cómo buscar un perfil en función del correo electrónico, el nombre, los apellidos o cualquier campo personalizado. [Puede obtener más información](../../audiences/using/integrated-customer-profile.md)

Se ha añadido información sobre la nueva función GetOption que le permite devolver el valor de una función especificada al llamar a un flujo de trabajo con parámetros externos. [Puede obtener más información](../../automating/using/customizing-workflow-external-parameters.md#using-events-variables)

Se ha añadido información sobre la nueva variable de salida **[!UICONTROL filesCount]** disponible después de usar una actividad **[!UICONTROL Transfer file]**. [Puede obtener más información](../../automating/using/transfer-file.md#output-variables)

La sección **Configuración del canal de correo electrónico** se ha actualizado para aclarar cuál es la configuración de correo electrónico más reciente aplicable. Algunos parámetros heredados que aún se utilizan para determinados clientes se enumeran en la parte inferior de esta página. [Obtenga más información](../../administration/using/configuring-email-channel.md)

Se ha añadido información sobre cómo asegurarse de que un flujo de trabajo programado no se vuelva a programar hasta que una o más tareas de una ejecución anterior sigan pendientes. [Obtenga más información](../../automating/using/scheduled-workflows-execution.md)

## Diciembre de 2020 {#doc-updates-december-2020}

**La capacidad de asunto predictivo** ya no se utiliza. [Más información](../../rn/using/deprecated-features.md)

La sección **Introducción a la mensajería transaccional** ahora incluye [esquemas mejorados](../../channels/using/getting-started-with-transactional-msg.md#transactional-messaging-operating-principle) para una mejor comprensión del proceso.

Ya está disponible un caso de uso de extremo a extremo para ilustrar el proceso de implementación de la mensajería transaccional. [Más información](../../channels/using/transactional-messaging-use-case.md)

La sección **Privacidad** se ha movido [aquí](../../start/using/privacy.md).

Hay una nueva página de **Accesibilidad** disponible: detalla el soporte de accesibilidad en el espacio de trabajo de Adobe Campaign Standard. [Más información](../../start/using/accessibility.md)

Se ha añadido una nota de advertencia en la que se indica que, para lograr un rendimiento óptimo, el número de mensajes transaccionales publicados debe ser inferior a 100. [Más información](../../channels/using/transactional-messaging-limitations.md#transactional-message-number)

La página de configuración y el protocolo del conector SMS se ha movido [aquí](../../administration/using/sms-protocol.md).

La sección **Uso de listados de productos en un mensaje transaccional** se ha movido [aquí](../../designing/using/using-product-listings.md).

## Noviembre de 2020 {#doc-updates-november-2020}

La sección **Datos personales y personas** se ha actualizado con un escenario de caso de uso para ilustrar cómo interactúan las distintas personas en lo que respecta a la privacidad. [Más información](../../start/using/privacy.md#use-case-scenario)

Se ha añadido una nueva sección que enumera las preguntas más frecuentes sobre Privacidad. [Más información](../../start/using/privacy-faq.md)

La sección **Privacidad** se ha movido y enriquecido con dos páginas nuevas: [Administración de privacidad](../../start/using/privacy-management.md) y [Administración de solicitudes de privacidad](../../start/using/privacy-requests.md).

La sección **Mensajería transaccional** se ha reorganizado y reunido en un solo lugar para mejorar la navegación. [Obtenga más información](../../channels/using/getting-started-with-transactional-msg.md)

Se ha añadido información en la sección Conector de datos de Adobe Experience Platform sobre el error de validación de asignación de datos relacionado con la administración de privacidad y cómo solucionarlo. [Más información](../../integrating/using/aep-mapping-activation.md)

## Versión 20.4: octubre de 2020 {#release-20-4---october-2020}

**Nuevas funciones incluidas en la versión**

Grupos de control: [Más información](../../sending/using/control-group.md)

API externa (compatibilidad con OAuth): [Más información](../../automating/using/external-api.md)

Integración de la inteligencia artificial aplicada a la trayectoria: [Más información](../../sending/using/predictive.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha enriquecido la sección sobre cómo invocar a un flujo de trabajo con parámetros externos con las nuevas funciones disponibles en el editor de expresiones. [Más información](../../automating/using/customizing-workflow-external-parameters.md)

Se ha agregado una recomendación a las optimizaciones de flujos de trabajo sobre el número de actividades que se deben utilizar por flujo de trabajo. [Más información](../../automating/using/best-practices-workflows.md#number-activities)

Se ha añadido una nueva sección sobre las prácticas recomendadas de entregas. [Más información](../../sending/using/delivery-best-practices.md)

Se ha agregado una sección para describir los nuevos filtros que permiten buscar las configuraciones de evento según su estado y hasta la última vez que se recibió un evento. [Más información](../../channels/using/configuring-transactional-event.md#searching-transactional-events)

## Septiembre de 2020 {#doc-updates-september-2020}

Se ha reorganizado y aclarado la sección **Mensajes transaccionales de eventos**. [Más información](../../channels/using/editing-transactional-message.md)

Se ha agregado una nota de precaución para advertir a los usuarios sobre la limitación de permisos relacionada con el acceso al registro. [Más información](../../administration/using/users-management.md)

Se ha añadido una nueva sección para detallar el proceso de creación de una nueva marca. [Más información](../../administration/using/branding.md#creating-a-brand)

Ya está disponible la nueva integración de Campaign Standard con Microsoft Dynamics 365. [Más información](../../integrating/using/d365-acs-get-started.md)

Se ha agregado información sobre las fuentes anónimas en el informe Perfiles activos. [Más información](../../audiences/using/active-profiles.md)

## Agosto de 2020 {#doc-updates-august-2020}

Hay disponible una nueva sección actualizada sobre cómo empezar a utilizar la mensajería transaccional. [Más información](../../channels/using/getting-started-with-transactional-msg.md)

La sección **Limitaciones de mensajería transaccional** se movió [aquí](../../channels/using/transactional-messaging-limitations.md).

La sección **Preparación del envío** se ha movido [aquí](../../sending/using/preparing-the-send.md).

## Julio de 2020 {#doc-updates-july-2020}

Se añadió una nueva sección con directrices relacionadas con la supervisión de Campaign Standard. [Más información](../../administration/using/monitoring-guidelines.md)

Se ha actualizado la sección de limitaciones y mecanismos de protección de API externas. [Más información](../../automating/using/external-api.md#guardrails)

Se ha actualizado la página Información general sobre administración de privacidad para incluir información sobre la Ley de Protección de Datos Personales de Tailandia (PDPA) y el Lei Geral de Proteção de Dados (LGPD) de Brasil. [Más información](https://helpx.adobe.com/es/campaign/kb/campaign-privacy-overview.html#whatisgdpr)

Se ha reorganizado y mejorado la guía de canal móvil. Se ha añadido una nueva guía de Configuración de canales móviles con documentación técnica sobre la configuración móvil. [Más información](../../administration/using/push-tracking.md)

Se ha actualizado la página Administración de privacidad en Campaign Standard, incluida una aclaración sobre cómo administrar las solicitudes de privacidad mediante la integración del servicio principal de privacidad. [Más información](https://helpx.adobe.com/es/campaign/kb/acs-privacy.html#ManagingPrivacyRequests)

Nuevas funciones de los correos electrónicos con tecnología de IA: envíe la optimización del tiempo y la puntuación del perfil. [Más información](../../sending/using/predictive.md)

## Junio de 2020 {#doc-updates-june-2020}

Los casos de uso del flujo de trabajo se han actualizado y reorganizado en secciones temáticas. [Más información](../../automating/using/about-workflow-use-cases.md)

Se han agregado casos de uso sobre cómo [cifrar](../../automating/using/managing-encrypted-data.md#use-case-gpg-encrypt) y [descifrar](../../automating/using/managing-encrypted-data.md#use-case-gpg-decrypt) datos mediante el Panel de control y los Flujos de trabajo de la campaña.

Las referencias al sitio web de asistencia heredado se han sustituido por la nueva dirección URL. [Más información](../../support.md)

La configuración de la cuenta Litmus personalizada se ha eliminado de la capacidad de procesamiento de la Bandeja de entrada. [Más información](../../sending/using/email-rendering.md)

La integración de Campaign Standard con Microsoft Dynamics 365 no está disponible actualmente. Se está desarrollando un nuevo conector que estará disponible en el futuro. Se han eliminado las páginas de ayuda relacionadas. [Más información](../../integrating/using/d365-acs-get-started.md)

## Mayo de 2020 {#doc-updates-may-2020}

La página de información general sobre el Campaign Standard se ha enriquecido y reorganizado en temas temáticos. [Más información](../../start/using/about-campaign-standard.md)

La sección Parámetros de canal de correo electrónico se ha aclarado con más información sobre los campos de máscaras autorizadas y el ID de informes de entrega. [Más información](../../administration/using/configuring-email-channel.md)

La configuración de una aplicación móvil mediante los SDK de Adobe Experience Platform está ahora disponible en la documentación principal con más información sobre el flujo de trabajo técnico de la aplicación móvil de sincronización AEPSDK desde Launch. [Más información](../../administration/using/configuring-a-mobile-application.md)

## Versión 20.3: mayo de 2020 {#release-20-3---may-2020}

**Nuevas funciones incluidas en la versión**

Ley de Protección de Datos Personales de Tailandia (PDPA): [Más información](https://helpx.adobe.com/content/help/es/campaign/kb/acs-privacy.html)

Actividad de API externa (GA): [Más información](../../automating/using/external-api.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido información sobre el campo **[!UICONTROL History in days]** de las propiedades de los flujos de trabajo que ahora incluye los archivos descargados por la actividad **[!UICONTROL Transfer file]**. [Más información](../../automating/using/managing-execution-options.md)

Se ha añadido información en la sección de sustitución de perfiles sobre el límite de 500 caracteres del prefijo de línea de asunto. [Más información](../../sending/using/testing-messages-using-target.md)

Se ha añadido una nueva sección dedicada a la privacidad y el consentimiento a la documentación principal. [Más información](../../start/using/privacy.md)

Se ha agregado un caso de uso para permitirle convertir correos electrónicos de editor heredados en el Diseñador de correo electrónico. [Más información](../../designing/using/converting-emails-from-legacy-editor.md)

Se ha añadido una sección de preguntas frecuentes sobre el Diseñador de correo electrónico. [Más información](../../designing/using/faq-email-designer.md)

## Abril de 2020 {#doc-updates-april-2020}

La integración de Microsoft Dynamics 365 con la documentación de Adobe Campaign Standard ya está disponible en la documentación principal. [Más información](../../integrating/using/d365-acs-get-started.md)

Se han añadido recursos adicionales a la página de inicio de documentación. [Más información](../../campaign-standard-home.md)

Se ha añadido información sobre el servicio de Experience Cloud ID (ECID) a la documentación de Adobe Experience Platform Data Connector. [Más información](../../integrating/using/aep-about-data-connector.md#key-concepts)

La sección mensajería transaccional se ha mejorado con información sobre cómo acceder a los últimos eventos transaccionales y capturas de pantalla actualizadas. [Más información](../../channels/using/publishing-transactional-event.md#previewing-and-publishing-the-event)

Se ha mejorado y actualizado la documentación sobre tipologías y reglas de tipología con información adicional sobre reglas de tipología integradas. [Más información](../../sending/using/about-typology-rules.md)

Se ha añadido información sobre la acción **[!UICONTROL File listing]** de la actividad **[!UICONTROL Transfer file]**. [Más información](../../automating/using/transfer-file.md)

La documentación sobre reintentos después de un error temporal de entrega se ha actualizado con más detalles sobre cómo se administran los reintentos una vez actualizados al MTA mejorado. [Más información](../../sending/using/understanding-delivery-failures.md#retries-after-a-delivery-temporary-failure)

Se ha mejorado y aclarado la sección Eliminación de un mensaje transaccional. [Más información](../../channels/using/publishing-transactional-message.md#deleting-a-transactional-message)

La sección **Vista previa de entregas** se ha actualizado con ejemplos de entregas móviles. [Más información](../../sending/using/previewing-messages.md)

Se ha añadido una práctica recomendada con respecto a la mensajería transaccional y la eliminación de eventos en tiempo real no utilizados. [Más información](../../channels/using/configuring-transactional-event.md#creating-an-event)

La sección Configuración de canales de correo electrónico se ha actualizado con una aclaración sobre todas las configuraciones de correo electrónico que ahora administra el MTA mejorado de Adobe Campaign. [Más información](../../administration/using/configuring-email-channel.md)

La sección de mensajería transaccional se ha actualizado con más información sobre los derechos necesarios para editar configuraciones de eventos y sobre cómo enriquecer las colecciones de los mensajes transaccionales. [Más información](../../channels/using/configuring-transactional-event.md).

## Versión 20.2: abril de 2020 {#release-20-2---april-2020}

**Nuevas funciones incluidas en la versión**

Integración de blob de Azure: [Más información](../../administration/using/external-accounts.md#microsoft-azure-external-account)

Pruebas de correo electrónico con perfiles de destino: [Más información](../../sending/using/testing-messages-using-target.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido la limitación al procesamiento de mensajes en la aplicación. [Más información](../../channels/using/customizing-an-in-app-message.md)

Se ha añadido información sobre cómo utilizar los agregados en una actividad **[!UICONTROL Query]**. [Más información](../../automating/using/query.md#adding-an-aggregate)

Se ha agregado limitación con MCPNS al configurar una aplicación móvil. [Más información](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html)

Se ha agregado una nueva sección de directrices de configuración a la guía Administración. La sección sobre exploradores y sistemas operativos compatibles se ha trasladado de la guía de introducción a esta sección. La nota técnica sobre los extremos de red de Campaign Standard también se ha agregado a esta sección. [Más información](../../administration/using/about-configuration-guidelines.md)

Ya está disponible una nueva sección que describe cómo eliminar una configuración de evento. [Más información](../../channels/using/publishing-transactional-event.md#deleting-an-event)

Las secciones de mensajería transaccional se han actualizado para reflejar las pequeñas actualizaciones y mejoras de la interfaz de usuario múltiple. [Más información](../../channels/using/getting-started-with-transactional-msg.md)

Se ha actualizado la información relacionada con los mecanismos de protección de actividad de API externas. [Más información](../../automating/using/external-api.md)

## Marzo de 2020 {#doc-updates-march-2020}

Se ha añadido información más detallada sobre el MTA mejorado a la documentación principal, en particular sobre las reglas de procesamiento de correo electrónico y la calificación de correo devuelto. [Más información](../../administration/using/configuring-email-channel.md#email-processing-rules)

Se ha movido y actualizado la sección dedicada al archivado con Email BCC. [Más información](../../sending/using/archiving.md)

La documentación de Configuración de una aplicación móvil y las páginas relacionadas se han actualizado para reflejar la depreciación del SDK V4. [Más información](https://developer.adobe.com/client-sdks/documentation/v4-end-of-life-faq/)

Se ha actualizado y mejorado la documentación sobre la integración de Adobe Campaign Standard y Adobe Experience Manager. [Más información](../../integrating/using/configure-experience-manager.md)

La documentación del Diseñador de correos electrónicos de Campaign y las páginas relacionadas se han actualizado para indicar que [!DNL Adobe Creative SDK] ha quedado obsoleto. [Más información](../../rn/using/deprecated-features.md)

Ya está disponible una nueva sección dedicada a las prácticas recomendadas del modelo de datos de Campaign Standard. [Más información](../../developing/using/data-model-best-practices.md)

Se ha añadido información sobre el derecho de integración de **[!UICONTROL Workflow]**. [Más información](../../administration/using/list-of-roles.md)

Se ha añadido información sobre el **[!UICONTROL History in days field]** disponible en las propiedades de los flujos de trabajo. [Más información](../../automating/using/about-workflow-execution.md)

## Versión 20.1: febrero de 2020 {#release-20-1---february-2020}

**Nuevas funciones incluidas en la versión**

Adobe Experience Platform Data Connector (versión beta): [Más información](../../integrating/using/aep-about-data-connector.md)

Audience Destinations (versión beta): [Más información](../../integrating/using/aep-about-audience-destinations-service.md)

**Otras actualizaciones de la documentación incluidas en la versión**

La documentación de administración de la privacidad se ha actualizado con información sobre cómo crear el campo de exclusión de CCPA para los recursos de perfil personalizados. [Más información](https://helpx.adobe.com/content/help/es/campaign/kb/acs-privacy.html)

Las Notas de la versión se han reorganizado y mejorado. [Más información](../../rn/using/release-notes.md)

Se ha agregado información relacionada con el grupo de seguridad Administradores, especificando que la unidad organizativa **[!UICONTROL All (all)]** se le ha asignado y que no se puede modificar. [Más información](../../administration/using/managing-groups-and-users.md)

Se ha añadido información sobre cómo definir un huso horario específico para utilizarlo de forma predeterminada en un flujo de trabajo. [Más información](../../automating/using/building-a-workflow.md)

Se ha añadido información en la guía de Uso de API sobre el nuevo parámetro **_forcePagination=true**, que le permite realizar la paginación en tablas grandes. [Más información](../../api/using/pagination.md)

Hay disponible una nueva sección que describe las advertencias que se pueden mostrar en un panel de mensajes. [Más información](../../channels/using/message-dashboard.md#warnings)

Ya está disponible la documentación de MTA mejorado de Adobe Campaign, que describe la infraestructura de envío actualizada, lo que permite mejorar la capacidad de la entrega, el rendimiento y la gestión de devoluciones. [Más información](https://helpx.adobe.com/es/campaign/kb/campaign-enhanced-mta.html)

Se han agregado notas para indicar que las URL del servidor de aplicaciones y del servidor de página espejo deben ser seguras para que las previsualizaciones de la página de aterrizaje y de la página espejo se muestren desde la interfaz de usuario de Campaign. [Más información](../../administration/using/branding.md#configuring-and-using-brands)

La sección Exportación de registros se ha actualizado para reflejar la disponibilidad del ID de registro de entregas en los recursos de Registros de entregas y Registros de seguimiento, lo que permite exportar un identificador único para cada registro. [Más información](../../automating/using/exporting-logs.md)

## Enero de 2020 {#doc-updates-january-2020}

La documentación sobre la entrega se ha actualizado con una nueva sección sobre la certificación de IP. <!--[Read more](../../sending/using/ip-certification.md)-->

Hay disponible una nueva sección que describe cómo crear un flujo de trabajo de entrega multicanal. [Más información](../../automating/using/workflow-cross-channel-delivery.md)

Se ha actualizado la sección Cálculo de indicador para los informes dinámicos. [Más información](../../reporting/using/indicator-calculation.md)

Se ha añadido una nueva página sobre las directrices generales para las entregas móviles en Adobe Campaign Standard. [Más información](https://helpx.adobe.com/es/campaign/kb/acs-mobile.html)

La documentación de Uso de Campaign y Experience Manager se ha actualizado con una nueva sección **Sugerencias sobre cómo utilizar la integración de Campaign y Experience Manager**. [Más información](../../integrating/using/integrating-with-experience-manager.md#tips-aem)

La página de inicio de la documentación de las API se ha mejorado con el redireccionamiento a los diferentes temas. [Más información](../../api/using/get-started-apis.md)

## De noviembre a diciembre de 2019 {#doc-updates-december-2019}

Se ha actualizado la documentación de Configuración de la cuenta externa S3. [Más información](../../administration/using/external-accounts.md#amazon-s3-external-account)

Se ha reorganizado la sección Diseño del contenido del correo electrónico. [Más información](../../designing/using/designing-content-in-adobe-campaign.md)

La guía de introducción a la capacidad de entrega se ha integrado en la documentación principal y se ha actualizado. [Más información](../../sending/using/about-deliverability.md)

La guía de introducción sobre cómo exportar e importar recursos personalizados se ha integrado en la documentación principal. [Más información](../../automating/using/exporting-importing-custom-resources.md)

Se ha añadido un nuevo caso de uso que describe cómo crear un grupo de control mediante un flujo de trabajo en Campaign Standard.

La información relacionada con las propiedades de las páginas de aterrizaje se ha movido a una sección dedicada. [Más información](../../channels/using/configuring-landing-page.md)

La documentación del Panel de control se ha integrado en el nuevo conjunto de documentos de colaboración. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es)

Se ha actualizado la tabla de **cálculo de indicador**. [Más información](../../reporting/using/indicator-calculation.md)

El conjunto de documentación de las API se ha integrado en la documentación de Campaign Standard.[Más información](../../api/using/get-started-apis.md)

La sección de introducción a la creación de un correo electrónico personalizado se ha movido y actualizado. [Más información](https://helpx.adobe.com/es/campaign/kb/acs-get-started-with-emails.html)

Se ha actualizado la guía de introducción a las prácticas recomendadas de entrega. [Más información](../../sending/using/delivery-best-practices.md)

El modelo de datos se ha integrado en la documentación de Campaign Standard. [Más información](../../developing/using/datamodel-audience.md)

El nuevo extremo **/customResources** de la API se ha agregado a la documentación de la API.[Más información](../../api/using/interacting-with-custom-resources.md)

## Versión 19.4: octubre de 2019 {#release-19-4---october-2019}

**Nuevas funciones incluidas en la versión**

California Consumer Privacy Act (CCPA): [Más información](https://helpx.adobe.com/es/content/help/es-ES/campaign/kb/acs-privacy.html#ccpa)

Integración de Microsoft Dynamics 365 (GA): [Más información](../../integrating/using/d365-acs-get-started.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha actualizado la lista de mensajes de error para Adobe Campaign. [Más información](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=es)

La guía de introducción al RGPD se ha mejorado y enriquecido. Ahora es una documentación de administración de la privacidad que incluye el RGPD y la CCPA. [Más información](https://helpx.adobe.com/content/help/es/campaign/kb/campaign-privacy.html)

Se ha añadido un nuevo gráfico que presenta el proceso de publicación de mensajería transaccional. [Más información](../../channels/using/publishing-transactional-message.md#transactional-messaging-pub-process)

La guía de introducción a las prácticas recomendadas de entrega se ha movido y actualizado. [Más información](../../sending/using/delivery-best-practices.md)

Se ha añadido una nueva sección. Proporciona una descripción general de los diferentes métodos que le permiten enriquecer la base de datos de Campaign Standard. [Más información](../../audiences/using/enriching-campaign-database.md)

Se ha añadido una nueva sección en la que se describe cómo aplicar estilo a los enlaces con el Diseñador de correo electrónico. [Más información](../../designing/using/styles.md#about-styling-links)

Se ha añadido información relacionada con la privacidad a la documentación de las API [Haga clic aquí](../../api/using/creating-a-privacy-request.md)

## Septiembre a octubre de 2019 {#doc-updates-october-2019}

Se ha añadido una nueva sección relacionada con la configuración de Campaign Standard. [Más información](../../administration/using/about-campaign-standard-settings.md)

Se ha añadido una nueva sección que describe cómo enviar un correo electrónico de confirmación personalizado y automático a los perfiles que se suscriben a un servicio específico. [Más información](../../audiences/using/confirming-subscription-to-a-service.md)

La sección Mensajería transaccional se ha modificado con las últimas actualizaciones de la interfaz de usuario, incluida la edición de contenido con el Diseñador de correo electrónico. [Más información](../../channels/using/editing-transactional-message.md)

Se ha reorganizado el capítulo páginas de aterrizaje. También se ha enriquecido con una nueva sección en la que se detallan los pasos para establecer una página de aterrizaje. [Más información](../../channels/using/getting-started-with-landing-pages.md)

Se ha añadido una nueva sección en la sección Notificaciones push sobre cómo crear y actualizar información de perfil basada en datos de suscripción de aplicaciones móviles. [Más información](../../channels/using/updating-profile-with-mobile-app-data.md)

Se ha añadido un nuevo ejemplo que muestra cómo enviar un correo electrónico que contiene datos adicionales recuperados de una actividad de carga de archivo. [Más información](../../automating/using/sending-email-enriched-fields.md)

Se ha añadido una nueva sección sobre cómo utilizar trampas. [Más información](../../sending/using/using-traps.md).

Se ha añadido una nota sobre la opción **Launch_URL_Campaign** en la página sobre cómo configurar una aplicación móvil con los SDK de Adobe Experience Platform. [Más información](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html)

Se ha reorganizado la guía del Diseñador de correo electrónico. [Más información](../../designing/using/designing-content-in-adobe-campaign.md)

## Agosto de 2019 {#doc-updates-august-2019}

Se ha añadido una nueva sección con casos de uso en flujos de trabajo centrados en consultas. [Más información](../../automating/using/workflow-created-query-with-complement.md)

Se ha agregado un procedimiento en la sección de resolución de problemas del flujo de trabajo sobre cómo mostrar consultas SQL en la pestaña Registro. [Más información](../../automating/using/best-practices-workflows.md#troubleshooting-data-management-activities)

Se ha añadido un nuevo artículo de ayuda con información relacionada con la administración de subdominios y certificados dentro del Panel de control. [Más información](https://experienceleague.adobe.com/docs/control-panel/using/subdomains-and-certificates/subdomains-branding.html?lang=es)

Se ha actualizado la sección que describe los fragmentos y las plantillas de contenido. [Más información](../../designing/using/using-reusable-content.md#content-templates)

Se ha añadido una nueva sección sobre cómo guardar contenido de correo electrónico como plantilla en el Diseñador de correo electrónico. [Más información](../../designing/using/using-reusable-content.md#saving-content-as-template)

## Versión 19.3: julio de 2019 {#release-19-3---july-2019}

**Nuevas funciones incluidas en la versión**

Actividad de API externa (versión beta pública): [Más información](../../automating/using/external-api.md)

Informe sobre el segmento de flujo de trabajo: [Más información](../../reporting/using/creating-a-report-workflow-segment.md)

**Otras actualizaciones de la documentación incluidas en la versión**

La Guía de implementación de Campaign Standard ya está activa.[Más información](https://helpx.adobe.com/es/campaign/kb/campaign-standard-implementation-guide.html)

Se ha creado un conjunto de nuevos artículos de ayuda sobre la implementación y el uso del conector de Microsoft Dynamics 365. Tenga en cuenta que esta función se encuentra actualmente en disponibilidad limitada.[Más información](../../integrating/using/d365-acs-get-started.md)

Se ha añadido una nota en la sección [Invocación de un flujo de trabajo con parámetros](../../automating/using/calling-a-workflow-with-external-parameters.md) sobre la preparación de entregas y su periodo de agregación.

Se ha añadido información sobre cómo personalizar la etiqueta de una entrega con variables de evento que se han declarado en la actividad de señal externa del flujo de trabajo. [Más información](../../automating/using/external-signal.md)

Se ha añadido una nueva sección que detalla cómo crear un usuario en Adobe Campaign Standard. [Más información](../../administration/using/users-management.md)

Ahora hay disponible un nuevo artículo con sugerencias para simplificar las campañas de marketing, incluidos los enlaces a la documentación del producto y videotutoriales.[Más información](https://helpx.adobe.com/es/campaign/kb/simplify-campaign-management.html)

Se ha añadido una resolución de problemas para la Creación de informes dinámicos. [Más información](../../reporting/using/troubleshooting.md)

Se ha añadido un diagrama que explica cómo gestionan la información personal las distintas plantillas en la aplicación. [Más información](../../channels/using/preparing-and-sending-an-in-app-message.md)

Se ha actualizado la sección sobre cómo guardar contenido de correo electrónico como fragmento en el Diseñador de correo electrónico. [Más información](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

Se ha añadido una advertencia sobre cómo los espacios en blanco adicionales pueden afectar al diseño de un contenido de correo electrónico. [Más información](../../designing/using/personalization.md#creating-custom-content-blocks)

Se ha añadido una nueva sección sobre las actualizaciones recomendadas del Diseñador de correo electrónico. [Más información](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-updates)

<!-- A new section on how to send proofs using real customer data has been added. [Read more](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs-using-additional-data) -->

Se ha añadido una nueva sección sobre las prácticas recomendadas del flujo de trabajo. [Más información](../../automating/using/best-practices-workflows.md)

Se ha actualizado la lista de mensajes de error para Standard y Campaign Classic. [Más información](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=es)

Se ha añadido una advertencia en la documentación de recursos personalizada. Se recomienda usar un máximo de 30 caracteres para los ID de recursos personalizados. Esto también se aplica a los campos de recursos personalizados, las claves, los índices y los enlaces. [Más información](../../developing/using/creating-or-extending-the-resource.md)

## De junio a julio de 2019 {#doc-updates-2019}

Se ha añadido una nueva página sobre las limitaciones de las páginas de aterrizaje. [Más información](../../channels/using/getting-started-with-landing-pages.md#landing-page-limitations)

Se ha añadido un caso de uso sobre cómo invocar a un perfil mediante una clave de identificación compuesta. [Más información](../../developing/using/uc-calling-resource-id-key.md)

Se ha agregado una recomendación con respecto al uso de entregas recurrentes sin periodo de agregación al invocar a un flujo de trabajo con parámetros. [Más información](../../automating/using/calling-a-workflow-with-external-parameters.md)

Se ha actualizado la lista de mensajes de error para Standard y Campaign Classic. [Más información](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=es)

Se ha añadido una advertencia en la documentación de recursos personalizada. Se recomienda usar un máximo de 30 caracteres para los ID de recursos personalizados. Esto también se aplica a los campos de recursos personalizados, las claves, los índices y los enlaces. [Más información](../../developing/using/creating-or-extending-the-resource.md)

## Versión 19.2: mayo de 2019 {#release-19-2---may-2019}

**Nuevas funciones incluidas en la versión**

Panel de control: [Más información](https://experienceleague.adobe.com/docs/control-panel/using/control-panel-home.html?lang=es)

Notificaciones locales: [Más información](../../channels/using/customizing-an-in-app-message.md#customizing-a-local-notification-message-type)

Mejora del flujo de trabajo: Añada una carga útil a la actividad de señal externa: [Más información](../../automating/using/calling-a-workflow-with-external-parameters.md)

Mejora de las páginas de aterrizaje: Google reCAPTCHA: [Más información](../../channels/using/configuring-landing-page.md#setting-google-recaptcha)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha actualizado el artículo Delegación de nombres de dominio. [Más información](https://helpx.adobe.com/es/campaign/kb/domain-name-delegation.html)

Se ha publicado un nuevo artículo de Planificación de versiones para compartir las próximas fechas de lanzamiento. [Más información](https://helpx.adobe.com/es/campaign/kb/acs-release-planning.html)

Se han actualizado los enlaces de ayuda contextual disponibles directamente desde Adobe Campaign.

La siguiente [página](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=es) se convierte en la página oficial de vídeos de Adobe Campaign Standard.

Se ha añadido una sección sobre retención de datos que incluye los valores de retención predeterminados para las tablas estándar. [Más información](../../administration/using/data-retention.md)

Se ha añadido una sección sobre actualizaciones y operaciones de mantenimiento. [Más información](../../administration/using/updates-and-maintenance-operations.md)

Se ha añadido información sobre la nueva opción de ordenación en la actividad de **transferencia de archivo**. [Más información](../../automating/using/transfer-file.md)

Se ha actualizado la [documentación de las API de REST](../../api/using/get-started-apis.md):

* Se ha añadido una nueva sección con información genérica sobre por qué utilizar las API de REST de Campaign Standard.
* Se ha puesto a disposición una colección de solicitudes de API prediseñadas que representan casos de uso comunes.
* Se ha añadido una nueva sección sobre cómo administrar las unidades organizativas.
* Se ha añadido información sobre cómo crear un servicio.
* Se ha añadido información sobre cómo invocar a un flujo de trabajo con parámetros.

Se ha añadido información sobre la nueva actividad de **prueba**. [Más información](../../automating/using/test.md)

La guía Automatización se ha actualizado con enlaces a actividades de flujo de trabajo relacionadas. [Más información](../../automating/using/workflow-interface.md#palette)

Se ha actualizado la sección Cálculo de indicador para los informes dinámicos. [Más información](../../reporting/using/indicator-calculation.md)

Se ha añadido una tabla de compatibilidad de creación de informes dinámicos para comprender mejor la compatibilidad entre dimensiones y métricas. [Más información](https://experienceleague.adobe.com/docs/campaign-standard/assets/dynamic_report_compatibility.pdf)

Se ha actualizado la lista de funciones para los flujos de trabajo. [Más información](../../automating/using/list-of-functions.md)

El capítulo Diseño de contenido se ha reorganizado y mejorado con una nueva sección que describe claramente los diferentes métodos para diseñar un correo electrónico con el Diseñador de correo electrónico utilizando el contenido existente. [Más información](../../designing/using/using-existing-content.md)

Se ha añadido una nueva sección sobre cómo guardar el contenido del correo electrónico como un fragmento en el Diseñador de correo electrónico. [Más información](../../designing/using/using-reusable-content.md#saving-content-as-a-fragment)

La sección Administración de enlaces se ha actualizado con información adicional sobre cómo administrar las URL rastreadas en el Diseñador de correo electrónico. [Más información](../../designing/using/links.md#inserting-a-link)

Se ha añadido una nueva sección para describir el proceso de reintento de mensaje transaccional específico. [Más información](../../channels/using/transactional-message-execution.md#transactional-message-retry-process)

La sección Publicación de un recurso con extensión API se ha aclarado y actualizado con los últimos cambios en la interfaz de usuario. [Más información](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

Se ha cambiado el nombre de la sección Archivado de correos electrónicos y se ha reorganizado. [Más información](../../sending/using/archiving.md)

La sección Creación de un correo electrónico se ha actualizado para reflejar los cambios más recientes en la interfaz. [Más información](../../channels/using/creating-an-email.md)

El artículo del [protocolo de conector SMS y la configuración](https://helpx.adobe.com/es/campaign/kb/sms-connector-protocol-and-settings.html) de la Base de conocimiento se han actualizado con la nueva opción añadida a la cuenta externa SMS para limitar el número de instancias de MTA permitidas para conectarse al proveedor de SMPP.

La Guía de introducción se ha enriquecido y reorganizado. [Más información](../../start/using/about-campaign-standard.md)

Se ha actualizado la página Funciones obsoletas y eliminadas. [Más información](../../rn/using/deprecated-features.md)

Se ha actualizado y mejorado la sección Integración de Dreamweaver. [Más información](../../designing/using/using-integrations.md#editing-content-in-dreamweaver)

## Versión 19.1: febrero de 2019 {#release-19-1---february-2019}

**Nuevas funciones incluidas en la versión**

Mejoras en la creación de informes del canal push: [Más información](../../reporting/using/push-notification-report.md)

Integración de Launch para aplicaciones móviles: [Más información](../../administration/using/configuring-a-mobile-application.md#using-adobe-experience-platform-sdk)

Mensajería en la aplicación móvil: [Más información](../../channels/using/about-in-app-messaging.md)

Mejoras en el flujo de trabajo: Más información [aquí](../../automating/using/workflow-interface.md#duplicating-workflow-activities) y [aquí](../../automating/using/load-file.md#configuration)

**Otras actualizaciones de la documentación incluidas en la versión**

Se han añadido la nueva experiencia de integración para crear contenido de correo electrónico y otras mejoras en el Diseñador de correo electrónico al capítulo Edición de contenido de correo electrónico. [Más información](../../designing/using/designing-content-in-adobe-campaign.md#email-designer-home-page)

Se ha añadido una nueva sección sobre las limitaciones de mensajería transaccional. [Más información](../../channels/using/transactional-messaging-limitations.md)

Se ha añadido una nueva sección que compara las diferentes opciones de creación de correo electrónico en Adobe Campaign. [Más información](../../designing/using/using-integrations.md#email-design-options-comparison)

La sección Creación de bloques de contenido personalizado se ha mejorado con detalles sobre dimensiones de segmentación. [Más información](../../designing/using/personalization.md#creating-custom-content-blocks)

Se ha añadido una advertencia que indica que el Diseñador de correo electrónico no admite Internet Explorer 11. [Más información](../../administration/using/about-configuration-guidelines.md)

Las advertencias sobre el impacto de la nueva redacción se han añadido a la sección Eliminación de un recurso. [Más información](../../developing/using/deleting-a-resource.md)

Se ha actualizado el capítulo sobre cómo añadir o ampliar un recurso. [Más información](../../developing/using/creating-or-extending-the-resource.md)

Se ha añadido un caso de uso sobre cómo ampliar el recurso personalizado de perfiles. [Más información](../../developing/using/extending-the-profile-resource-with-a-new-field.md)

Se ha añadido información sobre cómo vincular recursos personalizados. [Más información](../../developing/using/configuring-the-resource-s-data-structure.md#defining-links-with-other-resources)

Se ha añadido una nueva nota técnica sobre cómo mostrar una imagen desde una notificación push de Adobe Campaign Standard. [Más información](../../administration/using/image-push-notification.md)

Se ha añadido una nueva nota técnica sobre la implementación del seguimiento push. [Más información](../../administration/using/push-tracking.md)

Se ha actualizado la lista de mensajes de error para Standard y Campaign Classic. [Más información](https://experienceleague.adobe.com/developer/campaign-errors/error_codes.html?lang=es)

Se ha actualizado la documentación sobre la integración de activadores y Campaign. [Más información](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Actualización de los enlaces de ayuda contextual disponibles directamente desde Adobe Campaign.

Se ha añadido una nota sobre la adición de una marca de tiempo en el nombre del archivo que contiene los rechazos. [Más información](../../automating/using/load-file.md#configuration)

Se ha añadido información al importar campos formados por columnas de longitud fija. [Más información](../../automating/using/load-file.md#configuration)

Se ha añadido información sobre la opción que permite mantener los rechazos en un archivo. Esta opción ahora le permite aplicar una fase de procesamiento posterior al archivo que contiene los rechazos. [Más información](../../automating/using/load-file.md#configuration)

Se ha añadido una nueva sección sobre cómo duplicar las actividades de flujo de trabajo mediante operaciones de copiar y pegar. [Más información](../../automating/using/workflow-interface.md#duplicating-workflow-activities)

Se ha añadido información sobre la nueva opción de las actividades de consulta ([más información](../../automating/using/query-samples.md)) y segmentación ([más información](../../automating/using/segmentation.md)), que permite añadir una transición saliente después de la actividad si no recupera ningún dato.

Se ha añadido información en la sección de actividad de actualización de datos del nuevo campo Tamaño de lote que permite definir el tamaño máximo del lote para los datos que se van a cargar. [Más información](../../automating/using/update-data.md#configuration)

Se ha añadido información en la sección de actividad de extracción de archivo sobre la nueva opción que le permite desactivar el proceso de generación de archivos si la transición saliente está vacía. [Más información](../../automating/using/extract-file.md#configuration)

## Versión 19.0: enero de 2019 {#release-19-0---january-2019}

**Nuevas funciones incluidas en la versión**

Disponibilidad general del Diseñador de correo electrónico: [Más información](../../designing/using/designing-content-in-adobe-campaign.md)

Listas de productos en correos electrónicos transaccionales: [Más información](../../designing/using/using-product-listings.md)

Vista móvil en el Diseñador de correo electrónico: [Más información](../../designing/using/plain-text-html-modes.md#switching-to-mobile-view)

Mejoras en la versión beta de la mensajería en la aplicación: [Más información](../../channels/using/about-in-app-messaging.md)

**Otras actualizaciones de la documentación incluidas en la versión**

La guía de Diseño de contenido se ha actualizado para reflejar la disponibilidad general del Diseñador de correo electrónico y la obsolescencia del editor de contenido de correo electrónico heredado. [Más información](../../designing/using/designing-content-in-adobe-campaign.md)

Se ha actualizado la documentación de [notificaciones push](../../channels/using/about-in-app-messaging.md) y [en la aplicación](../../channels/using/about-push-notifications.md) .

Se ha añadido más información sobre los diferentes tipos de audiencias en Adobe Campaign. [Más información](../../audiences/using/about-audiences.md)

Se ha actualizado el capítulo Usuarios y seguridad para reflejar la depreciación de las unidades geográficas. [Más información](../../administration/using/organizational-units.md)

Se ha añadido información sobre la nueva opción de la actividad de carga de datos que le permite aplicar una fase de procesamiento posterior al archivo que contiene los registros rechazados (por ejemplo, compresión en formato zip). [Más información](../../automating/using/load-file.md)

Se ha añadido información sobre el nuevo campo en la actividad de actualización de datos que le permite configurar el tamaño máximo de lote de los datos que se van a cargar. [Más información](../../automating/using/update-data.md)

Se ha actualizado la documentación de [importación de contenido desde una URL](../../designing/using/using-existing-content.md#importing-content-from-a-url) con información relacionada con el Diseñador de correo electrónico.

Microsoft Edge (última versión) se ha añadido a la lista de exploradores compatibles para equipos. [Más información](../../administration/using/about-configuration-guidelines.md)

Se ha añadido información sobre la nueva opción de la actividad de extracción de archivo que impide generar un archivo si la transición entrante está vacía. [Más información](../../automating/using/extract-file.md)

La sección Configuración de una aplicación móvil mediante el SDK V4 se ha movido [aquí](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html).

La sección Configuración de una aplicación móvil mediante el SDK de Adobe Experience Platform se ha movido [aquí](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdk.html).

Los vídeos se han actualizado y movido [aquí](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/overview.html?lang=es).

Se ha actualizado la sección Tipo de usuarios. [Más información](../../administration/using/users-management.md)

## Versión 18.9: septiembre de 2018 {#release-18-9---september-2018}

**Nuevas funciones incluidas en la versión**

Mensajería en la aplicación (versión beta): [Más información](../../channels/using/about-in-app-messaging.md)

Integración de Adobe Launch para aplicaciones móviles (versión beta): [Más información](../../sending/using/managing-typologies.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha actualizado la guía de notificaciones push con cambios en la interfaz. [Más información](../../channels/using/about-push-notifications.md)

Se ha añadido información sobre cómo eliminar una audiencia. [Más información](../../audiences/using/creating-audiences.md#deleting-audiences)

Se ha actualizado la sección de informes integrados de notificaciones push. [Más información](../../reporting/using/push-notification-report.md)

## Versión 18.7: julio de 2018 {#release-18-7---july-2018}

**Nuevas funciones incluidas en la versión**

[Indicador de alta prioridad](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-android) y [filtro de tipología](../../sending/using/managing-typologies.md) para suscriptores de aplicaciones móviles.

Importación automática de contenido desde una URL en tiempo de preparación. [Más información](../../designing/using/using-existing-content.md#retrieving-content-from-a-url-automatically-at-preparation-time)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido una nueva nota técnica sobre el protocolo y la configuración del conector SMS. [Más información](https://helpx.adobe.com/es/campaign/kb/sms-connector-protocol-and-settings.html)

Se ha actualizado la documentación de integración de Experience Manager con Adobe Campaign. [Más información](../../reporting/using/creating-a-custom-profile-dimension.md)

La guía “Diseño de contenido” se ha reorganizado completamente, especialmente para presentar los dos editores que le permiten diseñar contenido para correos electrónicos. [Más información](../../designing/using/designing-content-in-adobe-campaign.md)

Aprenda a hacer que el contenido externo se pueda editar completamente con el SDK de Creative creando fragmentos a partir de los correos electrónicos existentes. [Más información](../../designing/using/designing-from-scratch.md)

La lista de los atributos HTML para el cumplimiento total con el Creative Designer ya está disponible en esta [sección](../../designing/using/using-existing-content.md#editing-existing-contents-with-the-email-designer).

Se ha añadido información sobre el idioma predeterminado de la plantilla multilingüe. [Más información](../../channels/using/multilingual-messages-template.md)

La guía Usuarios y seguridad se ha actualizado para reflejar la depreciación de la capacidad de la unidad geográfica en las nuevas instancias de Campaign Standard, así como en las instancias existentes sin crear unidades geográficas, a partir de la versión 18.7. [Más información](../../rn/using/deprecated-features.md)

## Versión 18.6: junio de 2018 {#release-18-6---june-2018}

**Nuevas funciones incluidas en la versión**

La documentación de la API se actualizó con información sobre la API del **historial**. Se ha añadido un caso de uso sobre cómo recuperar la página espejo de una entrega enviada a un perfil. [Más información](../../api/using/interacting-with-marketing-history.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha actualizado y reorganizado la documentación sobre la integración de activadores y Campaign. [Más información](../../integrating/using/about-adobe-experience-cloud-triggers.md)

Se ha añadido un caso de uso paso a paso sobre cómo crear una dimensión de perfil personalizada. [Más información](../../reporting/using/creating-a-custom-profile-dimension.md)

Se ha reorganizado la documentación del uso de Campaign y Audience Manager o del servicio principal People. [Más información](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Se ha actualizado la definición de la función de preparación de entregas. [Más información](../../administration/using/list-of-roles.md)

Se ha añadido un ejemplo en la sección de actividad de consultas sobre cómo destinar perfiles que hicieron clic en un vínculo específico de una entrega. [Más información](../../automating/using/query-samples.md#targeting-profiles-who-clicked-a-specific-link-)

Se ha añadido una sección en la documentación de API relacionada con **filtros personalizados**. [Más información](../../api/using/filtering.md)

## Versión 18.5: mayo de 2018 {#release-18-5---may-2018}

**Nuevas funciones incluidas en la versión**

RGPD: Integración de servicios principales: [Más información](../../start/using/privacy-management.md)

Mejoras de push: comentarios detallados sobre la entrega: [Más información](../../channels/using/preparing-and-sending-a-push-notification.md#sending-the-notification)

Extensión de los registros de entrega: [Más información](../../developing/using/configuring-the-resource-s-data-structure.md#defining-sending-logs-extension)

Creación de informes dinámicos con datos de perfil personalizados: [Más información](../../channels/using/creating-a-multilingual-push-notification.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido la lista de las métricas de Campaign que se encuentran en Analytics. [Más información](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Se ha añadido información sobre la opción Licencias en el menú Administración. [Más información](../../administration/using/licenses.md)

Se ha añadido información sobre cómo utilizar campos personalizados en una notificación push. [Más información](../../channels/using/customizing-a-push-notification.md#add-custom-fields)

Se ha actualizado la guía paso a paso de prácticas recomendadas de entrega. [Más información](../../sending/using/delivery-best-practices.md)

Se ha añadido información sobre los tipos de registro de seguimiento. [Más información](../../sending/using/tracking-messages.md#tracking-logs)

La sección de actividad de consulta se ha actualizado con ejemplos de consultas. [Más información](../../automating/using/query.md#query-samples)

Se cambió el nombre de la sección de la lista de bloqueados a “Explicación de los procesos de inclusión y exclusión”. Se ha actualizado con información sobre cómo administrar la inclusión en canales específicos y cómo configurar páginas de aterrizaje para administrar la inclusión y la exclusión. [Más información](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Conozca las prácticas recomendadas para utilizar los servidores SFTP alojados por Adobe. [Más información](../../administration/using/external-accounts.md#sftp-external-account)

Se ha actualizado la lista de SKU de Analytics compatibles para la integración con activadores. [Más información](../../integrating/using/configuring-triggers-in-experience-cloud.md#configuring-solutions-and-services)

Algunas páginas de la documentación del editor de contenido se han fusionado para ofrecer una vista más completa de las diferentes acciones disponibles. [Más información](../../designing/using/designing-content-in-adobe-campaign.md)

## Versión 18.3: marzo de 2018 {#release-18-3---march-2018}

**Nuevas funciones incluidas en la versión**

Reglamento General de Protección de Datos (RGPD) de la UE: [Más información](../../start/using/privacy.md)

Creative Designer para correo electrónico: [Más información](../../designing/using/designing-content-in-adobe-campaign.md)

Entregas push multilingües: [Más información](../../channels/using/creating-a-multilingual-push-notification.md)

Uso de recursos personalizados en la mensajería transaccional - [Más información](../../channels/using/configuring-transactional-event.md#enriching-the-transactional-message-content)

**Otras actualizaciones de la documentación incluidas en la versión**

La API del RGPD reagrupa funciones que permiten el procesamiento automático de solicitudes de RGPD. [Más información](../../api/using/creating-a-privacy-request.md)

Se añadió información sobre cómo configurar páginas de aterrizaje para que se puedan incluir a los destinatarios en la lista de bloqueados. [Más información](../../audiences/using/managing-opt-in-and-opt-out-in-campaign.md)

Se ha reorganizado la sección [Configuración de mensaje transaccional](../../channels/using/configuring-transactional-event.md) y se ha añadido un [caso de uso paso a paso](../../channels/using/transactional-messaging-use-case.md).

Se ha añadido una nota técnica para aprender a generar un archivo CSV multilingüe para utilizarlo en las notificaciones push. [Más información](https://helpx.adobe.com/es/campaign/kb/acs-generate-csv-multilingual-push.html).

Información añadida sobre la plantilla de importación **Actualización de las cuarentenas de correo postal y registros de entregas**. [Más información](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)

Se ha actualizado la lista de flujos de trabajo técnicos. [Más información](../../administration/using/technical-workflows.md)

Se ha actualizado la sección de actividad del planificador. [Más información](../../automating/using/scheduler.md)

Se ha actualizado la lista de materiales de ayuda sobre Campaign y la integración de soluciones de Adobe. [Más información](../../integrating/using/get-started-campaign-integrations.md).

Se ha actualizado la ayuda contextual de Campaign Standard en el producto.

## Versión 18.2: febrero de 2018 {#release-18-2---february-2018}

**Nuevas funciones incluidas en la versión**

Suscripción: suscripción o cancelación de la suscripción de una lista de perfiles a varios servicios: [Más información](../../automating/using/subscription-services.md)

Actividad de enriquecimiento: enriquecer datos basados en transiciones anteriores: [Más información](../../automating/using/enrichment.md)

**Otras actualizaciones de la documentación incluidas en la versión**

La mayoría de las URL para las integraciones de soluciones de Adobe y Campaign han cambiado. Compruebe sus marcadores. [Más información](../../integrating/using/get-started-campaign-integrations.md)

El modelo de datos v1 ya está disponible con la estructura SQL para los recursos integrados: [Más información](../../developing/using/datamodel-introduction.md)

Información añadida sobre cómo preparar un mensaje en una entrega [Más información](../../sending/using/preparing-the-send.md)

Las notas de la versión se han reorganizado en varias páginas para obtener una mejor vista global de las diferentes versiones.

La sección **[!UICONTROL Working with typologies]** se ha actualizado para mejorar la visibilidad. [Más información](../../sending/using/about-typology-rules.md)

Ya está disponible una nueva opción que permite obtener rendimiento al definir muchos datos adicionales en una **[!UICONTROL Query]**. [Más información](../../automating/using/query-samples.md)

El ejemplo de importación de perfil se ha actualizado con algunas sugerencias para que sus perfiles estén listos para recibir correos postales. [Más información](../../automating/using/about-data-import-and-export.md)

Hay una nueva actividad disponible en flujos de trabajo: la actividad **[!UICONTROL Enrichment]**. [Más información](../../automating/using/enrichment.md)

La actividad **[!UICONTROL Subscription Services]** se ha actualizado para admitir más casos de uso, incluido el uso de un solo archivo para actualizar las suscripciones a varios servicios. [Más información](../../automating/using/subscription-services.md)

Se ha añadido un caso de uso paso a paso sobre cómo preparar una entrega. [Más información](../../sending/using/preparing-the-send.md)

Se ha eliminado la sección que incluye la lista de autorizaciones. [Más información](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf) (PDF).

Se ha añadido un caso de uso paso a paso sobre cómo usar la respuesta automática de SMS. [Más información](../../channels/using/managing-incoming-sms.md#managing-stop-sms)

Se ha añadido información sobre cómo enviar una entrega en función de los husos horarios de los usuarios en un flujo de trabajo recurrente. [Más información](../../automating/using/recurring-push-notifications.md)

Se ha reorganizado la sección **[!UICONTROL Customizing a push notification]** con casos de uso paso a paso. [Más información](../../channels/using/customizing-a-push-notification.md)

Nueva sección dedicada a la administración de la lista de bloqueados. [Más información](../../audiences/using/about-opt-in-and-opt-out-in-campaign.md)

Se ha actualizado la información sobre errores y cuarentenas de entregas. [Más información](../../sending/using/monitoring-a-delivery.md)

Nuevas secciones dedicadas a [asignaciones de destinatarios](../../administration/using/target-mappings-in-campaign.md) y [dimensiones de segmentación y recursos](../../automating/using/query.md#targeting-dimensions-and-resources).

## Versión 18.1: enero de 2018 {#release-18-1---january-2018}

**Nuevas funciones incluidas en la versión**

Creación de informes para la gestión de la fatiga: [Más información](../../sending/using/fatigue-rules.md#viewing-the-fatigue-rule-summary-report)

Uso compartido de informes: [Más información](../../reporting/using/reporting-interface.md#share-tab)

Mejoras de push: Más información [aquí](../../channels/using/preparing-and-sending-a-push-notification.md#preparing-the-notification) y [aquí](../../channels/using/customizing-a-push-notification.md#change-the-notification-behavior-for-ios)

Entregas optimizadas para zonas horarias: [Más información](../../automating/using/scheduler.md)

Activación de actividad de señal de API: [Más información](../../api/using/triggering-a-signal-activity.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha actualizado la sección de creación de servicios. [Más información](../../audiences/using/creating-a-service.md)

Se han añadido casos de uso para una mejor comprensión de los grupos y unidades de seguridad. [Más información](../../administration/using/organizational-units.md)

Se han mejorado las definiciones y los cálculos de dimensiones, las métricas y los segmentos en los informes dinámicos. [Más información](../../reporting/using/list-of-components-.md)

Se ha añadido información sobre la recuperación de mensajes SMS entrantes con un flujo de trabajo. [Más información](../../administration/using/configuring-sms-channel.md)

Se ha añadido información sobre la configuración de historias de la actividad de transferencia de archivos. [Más información](../../automating/using/transfer-file.md)

Se han actualizado las instrucciones para configurar la integración con Audience Manager o el servicio principal People. [Más información](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

## Versión 17.10: octubre de 2017 {#release-17-10---october-2017}

**Nuevas funciones incluidas en la versión**

Administración de fatiga: [Más información](../../sending/using/fatigue-rules.md)

Creación de contenido: Importación desde una URL [(Más información)](../../designing/using/using-existing-content.md#importing-content-from-a-url)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha actualizado la muestra de prueba A/B. [Más información](../../channels/using/designing-an-a-b-test-email.md)

Nueva nota técnica sobre cómo crear o actualizar datos de perfil cuando una aplicación móvil envía datos de “Recopilación de PII”. [Más información](https://helpx.adobe.com/es/campaign/kb/acs-updating-profile-based-on-subscription.html)

Se ha añadido una sección sobre las nuevas funciones de seguimiento de exportación. [Más información](../../administration/using/auditing-export-logs.md)

Se han añadido las precisiones sobre la exportación de paquetes integrada. [Más información](../../automating/using/managing-packages.md)

Se han actualizado la definición y los ejemplos de cuenta externa. [Más información](../../administration/using/external-accounts.md)

Se han actualizado varias capturas de pantalla para reflejar los cambios en las categorías del editor de consultas.

La sección [Alerta de entrega](../../sending/using/receiving-alerts-when-failures-happen.md) se ha movido y reorganizado.

La sección “Recursos personalizados” se ha aclarado con un procedimiento más detallado sobre cómo [definir filtros](../../developing/using/configuring-filter-definition.md).

Se ha actualizado y aclarado la [nota técnica](https://helpx.adobe.com/es/campaign/kb/integrate-mobile-sdk.html) sobre cómo integrar el SDK móvil de Adobe Marketing Cloud con una aplicación móvil para recibir notificaciones push de Adobe Campaign Standard.

Se ha añadido una nota técnica que explica la estructura de la carga recibida en una aplicación móvil. [Más información.](../../administration/using/push-payload.md)

La [sección](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html) de configuración de canal push se ha actualizado con nuevos datos de carga en la versión del sistema operativo para añadirlos al definir devoluciones en la interfaz de Adobe Mobile Services.

La documentación de SMS se ha actualizado con algunas aclaraciones agregadas a la sección de [respuestas automáticas de SMS](../../channels/using/managing-incoming-sms.md#managing-stop-sms).

Nueva sección dedicada a la administración de flujos de trabajo mediante la API. [Más información](../../api/using/controlling-a-workflow.md)

Nueva sección dedicada a las claves primarias y al uso de un ID comercial como clave en la API. [Más información](../../api/using/get-started-apis.md)

Se ha añadido información sobre el filtrado simple y múltiple en la API. [Más información](../../api/using/filtering.md)

## Versión 17.9: septiembre de 2017 {#release-17-9---september-2017}

**Nuevas funciones incluidas en la versión**

Biblioteca de plantillas de correo electrónico: [Más información](../../designing/using/using-reusable-content.md#content-templates)

Creación de informes dinámicos con datos de perfil: [Más información](../../reporting/using/about-dynamic-reports.md)

Mejora de la suscripción masiva: [Más información](../../automating/using/subscription-services.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Lista detallada de todos los componentes disponibles en Informes dinámicos y algunos cambios en las fórmulas. [Más información](../../reporting/using/list-of-components-.md)

Lista detallada de los KPI compartidos con Adobe Analytics. [Más información](../../integrating/using/campaign-dimensions-and-metrics-in-analytics.md)

Nuevo vídeo de informe dinámico.

Se han añadido recomendaciones de cuenta S3. [Más información](../../administration/using/external-accounts.md#amazon-s3-account-recommendations)

Se ha actualizado la sección sobre los distintos tipos de usuarios. [Más información](../../administration/using/users-management.md)

Se ha actualizado la sección sobre la personalización del origen de imagen. [Más información](../../designing/using/personalization.md#personalizing-an-image-source)

Se ha añadido documentación al informe de perfiles activos. [Más información](../../audiences/using/active-profiles.md)

La documentación de [Alerta de entrega](../../sending/using/receiving-alerts-when-failures-happen.md#delivery-alerting-reasons) se ha actualizado con una sección de resolución de problemas que presenta algunas sugerencias sobre las acciones que puede realizar al recibir alertas.

Hay disponible una nueva guía de introducción: presenta algunas de las prácticas recomendadas que se pueden utilizar para ofrecer Adobe Campaign, desde la creación y la segmentación hasta la entrega y la supervisión. [Más información](../../sending/using/delivery-best-practices.md)

La documentación de los mensajes de seguimiento se ha actualizado con un caso de uso mejorado. [Más información](../../channels/using/follow-up-messages.md#sending-a-follow-up-message)

Documentación añadida en el ID de ACS. [Más información](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

Se han añadido nuevas funciones de cifrado y hash con ejemplos. [Más información](../../automating/using/list-of-functions.md)

Se ha actualizado la sección sobre la actividad del flujo de trabajo de transferencia de archivo. [Más información](../../automating/using/transfer-file.md)

Se ha añadido información sobre la opción “Solicitar confirmación antes de enviar mensajes” en la actividad del flujo de trabajo de envío de correo electrónico. [Más información](../../automating/using/email-delivery.md)

## Versión 17.7: julio de 2017 {#release-17-7---july-2017}

**Nuevas funciones incluidas en la versión**

Entregas multilingües (correo electrónico y SMS): [Más información](../../channels/using/creating-a-multilingual-email.md)

Notificaciones de Adobe Campaign: [Más información](../../administration/using/sending-internal-notifications.md)

Alerta de entrega: [Más información](../../sending/using/receiving-alerts-when-failures-happen.md)

ID declarado cifrado en orígenes de datos: [Más información](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Uso compartido de KPI de Campaign a Analytics: [Más información](../../integrating/using/about-campaign-analytics-integration.md)

Canal de correo postal: Devolver al remitente: [Más información](../../channels/using/return-to-sender.md)

**Otras actualizaciones de la documentación incluidas en la versión**

Las guías de introducción y los vídeos explicativos se han reagrupado en una sección dedicada.

Se ha actualizado la documentación de procesamiento del correo electrónico. [Más información](../../sending/using/email-rendering.md)

Se ha actualizado la tabla de cálculo del indicador del informe. [Más información](../../reporting/using/indicator-calculation.md)

La documentación de la creación de informes se ha actualizado con cuatro métricas nuevas. [Más información](../../reporting/using/list-of-components-.md)

Se ha añadido documentación sobre la generación de ID únicos para perfiles. [Más información](../../developing/using/configuring-the-resource-s-data-structure.md#generating-a-unique-id-for-profiles-and-custom-resources)

El mecanismo de inclusión doble ahora se documenta con un procedimiento paso a paso. [Más información](../../channels/using/setting-up-a-double-opt-in-process.md)

Se ha actualizado la sección Lista de funciones. [Más información](../../administration/using/list-of-roles.md)

## Versión 17.5: mayo de 2017 {#release-17-5---may-2017}

**Nuevas funciones incluidas en la versión**

Correo postal: [Más información](../../channels/using/about-direct-mail.md)

Email BCC: [Más información](../../sending/using/archiving.md)

**Otras actualizaciones de la documentación incluidas en la versión**

La guía “Entregas” se ha reorganizado y se ha cambiado el nombre a “Canales”. [Más información](../../channels/using/get-started-communication-channels.md)

Se han actualizado numerosas capturas de pantalla para reflejar los cambios en la interfaz.

Ahora hay disponible una nueva nota técnica: “Integración del SDK móvil de Adobe con su aplicación móvil”. [Más información](https://helpx.adobe.com/es/campaign/kb/integrate-mobile-sdk.html)

Se añadieron instrucciones para configurar el servicio principal People o la integración de Audience Manager con Adobe Campaign. [Más información](../../integrating/using/integration-with-audience-manager-or-people-core-service.md)

Se ha revisado la tabla de autorizaciones para que el uso de ciertas funciones sea más claro. [Más información](https://experienceleague.adobe.com/docs/campaign-standard/assets/acs_rights.pdf)

Actualización de los enlaces de ayuda contextual disponibles directamente desde Adobe Campaign.

## Versión 17.4: abril de 2017 {#release-17-4---april-2017}

**Nuevas funciones incluidas en la versión**

Funciones mejoradas de edición de imágenes con el SDK de Creative: [Más información](../../designing/using/images.md#modifying-images-with-the-adobe-creative-sdk)

Notificaciones push transaccionales: [Más información](../../channels/using/transactional-push-notifications.md)

Notificaciones push recurrentes: [Más información](../../automating/using/push-notification-delivery.md)

Conector Amazon Simple Storage Service (S3): [Más información](../../administration/using/external-accounts.md)

Integración de Dreamweaver en vivo: [Más información](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=es)

**Otras actualizaciones de la documentación incluidas en la versión**

Se ha añadido una sección sobre los distintos tipos de usuarios de Adobe Campaign. [Más información](../../administration/using/users-management.md)

La guía de Flujo de trabajo se ha reorganizado y ampliado. Encuentre fácilmente cómo [compilar](../../automating/using/building-a-workflow.md) y [ejecutar](../../automating/using/about-workflow-execution.md) un flujo de trabajo, cómo [dirigir](../../automating/using/about-targeting-activities.md) y [administrar](../../automating/using/about-targeting-activities.md#enriching-data) sus datos, cómo [importarlos y exportarlos,](../../automating/using/about-data-import-and-export.md) y cómo usar los datos de flujo de trabajo para actualizar la base de datos o para realizar envíos.

El cálculo del indicador de informes ya está disponible para los informes dinámicos, incluida la descripción completa y la fórmula de cálculo. [Más información](../../reporting/using/indicator-calculation.md)

Nueva sección sobre la configuración de Adobe Mobile Services para utilizar las notificaciones push y los datos del punto de interés en Adobe Campaign. [Más información](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html)

Se han actualizado las secciones de configuración e implementación de aplicaciones móviles, incluidos los pasos más detallados para configurar y enviar notificaciones push. [Más información](https://helpx.adobe.com/es/campaign/kb/configuring-app-sdkv4.html)

Se ha actualizado la sección sobre cómo trabajar con imágenes en Campaign. [Más información](../../designing/using/images.md#setting-up-image-properties)

Se ha actualizado la integración con Adobe Analytics para móviles (punto de interés), incluidos los pasos de configuración y el caso de uso. [Más información](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

## Versión 17.2: marzo de 2017 {#release-17-2---march-2017}

**Nuevas funciones incluidas en la versión**

Creación de informes dinámicos: [Más información](../../reporting/using/about-dynamic-reports.md)

Integración de Dreamweaver (Labs): [Más información](https://experienceleague.adobe.com/docs/campaign-learn/campaign-standard-tutorials/designing-content/email-designer/dreamweaver-integration.html?lang=es)

Optimización del tiempo de envío manual: [Más información](../../sending/using/optimizing-the-sending-time.md)

Mejoras en las notificaciones push: [Más información](../../channels/using/about-push-notifications.md)

Flujos de trabajo: nueva actividad de señal: [Más información](../../automating/using/external-signal.md)

Flujos de trabajo: nueva actividad de lectura de audiencia: [Más información](../../automating/using/read-audience.md)

Datos de puntos de interés: [Más información](../../integrating/using/about-campaign-points-of-interest-data-integration.md)

Recursos vinculados en las API de REST: [Más información](../../developing/using/updating-the-database-structure.md#publishing-a-resource-with-api-extension)

**Otras actualizaciones de la documentación incluidas en la versión**

Integración de activadores: se han añadido dos casos de uso. [Más información](../../integrating/using/abandonment-triggers-use-cases.md)

Hemos rediseñado la documentación de la API de desarrollador con nuevos fragmentos de código e información para mejorar la experiencia del usuario. [Más información](../../api/using/get-started-apis.md)

Descubra ejemplos de las nuevas actividades de flujo de trabajo de [Lectura de audiencia](../../automating/using/read-audience.md) y [Señal externa](../../automating/using/external-signal.md).

## Versión 17.1: enero de 2017 {#release-17-1---january-2017}

**Nuevas funciones incluidas en la versión**

Exportación de registros para la creación de informes externa: [Más información](../../automating/using/exporting-logs.md)

API de mensajería transaccional: [Más información](../../api/using/get-started-apis.md)

Funciones de marketing para los mensajes transaccionales: [más información](../../channels/using/editing-transactional-message.md#profile-transactional-message-specificities)

**Otras actualizaciones de la documentación incluidas en la versión**

Actividad de flujo de trabajo de consulta incremental: nuevo modo incremental: [Más información](../../automating/using/incremental-query.md)

Actualización de actividad de flujo de trabajo del planificador: [Más información](../../automating/using/scheduler.md)

Cambio de URL: Servicio principal de recursos: [Más información](../../integrating/using/working-with-campaign-and-assets-core-service.md)

Cambio de URL: Servicio principal People: [Más información](../../integrating/using/about-campaign-audience-manager-or-people-core-service-integration.md)

Se ha reorganizado la guía Perfiles y audiencias. [Más información](../../audiences/using/get-started-profiles-and-audiences.md)
