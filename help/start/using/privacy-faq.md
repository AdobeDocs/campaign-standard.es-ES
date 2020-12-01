---
title: Preguntas más frecuentes sobre privacidad
description: Obtenga información sobre la privacidad, los datos personales y la gestión de consentimiento en Adobe Campaign Standard
page-status-flag: never-activated
uuid: ed9e631c-5ad1-49f1-be1e-b710bc64dc91
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: discovering-the-interface
discoiquuid: 5227ca05-3856-4e54-aec6-14444d6534e3
translation-type: tm+mt
source-git-commit: 500a9575157a0652eac2504d2360f7a1cbd6189e
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 0%

---


# Preguntas más frecuentes sobre privacidad {#privacy-faq}

Estas son algunas de las preguntas más frecuentes sobre privacidad y consentimiento al usar Adobe Campaign.

## Términos clave {#key-terms}

**¿Cuáles son los términos clave sobre la privacidad?**

Los elementos que se enumeran a continuación enlazan a los términos y conceptos clave relacionados con la privacidad y el consentimiento en Adobe Campaign:

* [Normas sobre la gestión de la privacidad](../../start/using/privacy-management.md#privacy-management-regulations)
* [Datos personales y personas](../../start/using/privacy.md#personal-data)
* [Derecho de acceso y derecho al olvido](../../start/using/privacy-management.md#right-access-forgotten)
* [Consentimiento, retención y funciones](../../start/using/privacy-management.md#consent-retention-roles)

## Preparación de las normas de privacidad {#privacy-regulations-readiness}

**¿Qué sugerencia de Adobe Campaign para cumplir con las regulaciones de privacidad más recientes?**

El Adobe no proporciona asesoramiento jurídico. Debe trabajar con su propio asesor legal para asegurarse de que está tomando todas las medidas necesarias para el RGPD, la CCPA, la PDPA, la LGPD o cualquier otra disposición legal aplicable.

**Preparación para solicitudes de acceso a datos y eliminación**

* Identifique un proceso para recibir/responder a las solicitudes del sujeto de datos, incluido el nombramiento de un punto de contacto de privacidad.

* Revise los distintos datos de cliente almacenados en Adobe Campaign y determine identificadores únicos (probablemente habrá más de uno).

* Determine una directiva de validación/autenticación y un proceso para la confirmación de identidad del sujeto de datos.

* Asegúrese de que la respuesta del sujeto de datos sea fácil de entender.

**Considere el consentimiento**

* Lista y actualización, según sea necesario, de todos los puntos de contacto para la captura de datos del RGPD (es decir, considere el lenguaje, el mecanismo para el consentimiento y los registros de consentimiento).

* Asegúrese de que todos los correos electrónicos de marketing incluyan los vínculos de cancelación de suscripción.

* Evalúe la estrategia global de mercadotecnia por correo electrónico para determinar las implementaciones específicas de cada ubicación geográfica.

**Comprender los datos**

* Revise todos los orígenes de captura e importación de datos donde los datos fluyen a Adobe Campaign y documento qué campos se utilizan para sus esfuerzos de mercadotecnia.

* Elimine los atributos de datos que no se utilicen de la base de datos de Adobe Campaign.

* Utilice los datos disponibles en Adobe Campaign para comprobar la calidad de la captura y ofrecer a sus destinatarios experiencias más personalizadas.

* Revise y actualice los permisos de acceso a los datos para garantizar que los usuarios de Adobe Campaign puedan aprovechar completamente solo los datos necesarios para ejecutar sus campañas, pero no acceder a ningún dato más allá de esto.

* Asegúrese de que cada usuario de Adobe Campaign tenga los derechos de acceso adecuados para realizar las tareas necesarias, pero no tenga ningún otro derecho para realizar tareas adicionales.

## Mantener la participación del usuario {#preserve-user-engagement}

**¿Cómo pueden obtener el consentimiento los controladores de datos con un impacto mínimo en la participación del usuario?**

En los casos en que se necesite el consentimiento para determinadas actividades de comercialización, el consentimiento del consumidor deberá estar activo (es decir, no habrá silencio como casillas de verificación o de aprobación), desagregado y puede no estar condicionado a la oferta de los servicios.

Puede incluso haber casos en los que es necesario actualizar ciertos consentimientos para poder seguir utilizando datos a partir de ahora.

En lugar de pensar en estos requisitos de consentimiento mejorado como un riesgo para el universo comercializable, los especialistas en mercadotecnia podrían adoptarlos como un verdadero indicador de compromiso y lealtad de la marca, así como de satisfacción y confianza de los clientes.

## Administrar consentimiento {#manage-consent}

**¿Cómo pueden los controladores de datos administrar el consentimiento en Adobe Campaign?**

Adobe Campaign ya ofrece capacidades para administrar el consentimiento en más niveles que la mayoría de los especialistas en mercadotecnia mediante campos de datos personalizados o a través de uno o más servicios.

Los especialistas en mercadotecnia deben consultar con su asesor legal para obtener instrucciones sobre cómo proceder y luego aprovechar las capacidades ya integradas en Adobe Campaign.

Por ejemplo: ampliar el modelo de datos en Adobe Campaign para rastrear no sólo si las personas han elegido participar, sino también la marca de tiempo de la inclusión y algún tipo de indicador que capture el alcance preciso del consentimiento.

## Eliminación de datos {#data-deletion}

**¿Qué datos pueden eliminar los controladores de datos en Adobe Campaign en respuesta a una solicitud del cliente de un sujeto de datos?**

Se eliminarán todos los datos asociados al asunto de datos, incluidas las tablas predeterminadas y las personalizadas.

Técnicamente, se eliminarán todos los datos vinculados al sujeto de datos con `integrity="own"` .

Como controlador de datos, tiene la opción de personalizarlo cambiando la integridad de los vínculos definidos en los esquemas de datos (por ejemplo, si tiene una justificación comercial para no eliminar determinados datos).

**¿Cómo se ven afectados los informes cuando se eliminan envíos y registros de seguimiento?**

Los informes de Adobe Campaign se basan en indicadores calculados a partir de datos agregados de envíos y registros de seguimiento. Como resultado, la eliminación de los registros individuales no debería afectar a las métricas mostradas en los informes.

## Volver a importar datos {#re-import-data}

**A menudo, en Adobe Campaign, el registro se carga desde un origen de datos externo. ¿Debo tener en cuenta la posibilidad de volver a importar los datos más adelante?**

Como controlador de datos, deberá asegurarse de que cuando reciba una solicitud de eliminación, elimine todos los datos necesarios sobre el asunto de datos de todos los sistemas.

## Adhesión nuevamente {#opt-in-again}

**¿Puede un sujeto de datos, cuyos datos se han borrado de Adobe Campaign, optar de nuevo más tarde?**

Es posible que un sujeto de datos vuelva a participar o se añada como un nuevo destinatario después de que sus datos se hayan borrado de Adobe Campaign.

Puede utilizar la pista de auditoría que detalla cuándo se realizó la eliminación anterior y cuándo se creó el nuevo destinatario.