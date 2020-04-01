---
title: '"Uso de Campaign Standard y Microsoft Dynamics 365: Avisos y recomendaciones"'
description: Obtenga información sobre cómo trabajar con Campaign Standard y Microsoft Dynamics 365
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 620be6615d162672948c3dccdae2752b8c999c47

---


# Uso de Campaign Standard y Microsoft Dynamics 365: Avisos y recomendaciones

## Compatibilidad con la región

Esta integración está disponible en las regiones de Norteamérica, EMEA y APAC.

Si se encuentra en las regiones EMEA o APAC, algunos de sus datos se procesarán en Estados Unidos como parte de esta integración. Para obtener más información, consulte [esta sección](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Fuente de la verdad para la sincronización de contacto unidireccional

Para la sincronización de entidades personalizadas y de contacto, esta integración trata a Dynamics 365 como la fuente de la verdad. Cualquier cambio en los atributos sincronizados debe realizarse en Microsoft Dynamics 365, no en Adobe Campaign Standard. Si los cambios se realizan en Campaña, se pueden sobrescribir en Campaña durante la sincronización, ya que la sincronización está en una dirección.  Además, la sincronización de contactos está diseñada para extraer todos los registros de contacto, tanto si están marcados como activos o inactivos en Microsoft Dynamics 365.

## Administración de solicitudes de privacidad

Esta integración está diseñada para transferir datos de usuarios finales (incluida, entre otros, la información personal, si está incluida en los datos de usuarios finales), entre Microsoft Dynamics 365 y Adobe Campaign Standard.  Como controlador de datos, su compañía es responsable de cumplir con las leyes y regulaciones de privacidad aplicables a su recopilación y uso de datos personales.

Para esta integración, debe procesar cada solicitud del sujeto de datos en cada sistema de forma independiente para que el cambio se refleje en ambas bases de datos. El cambio debe ejecutarse primero en Microsoft Dynamics 365 y, a continuación, en Adobe Campaign Standard. La única excepción a esto es que se agregará una solicitud de eliminación relacionada con la privacidad a la cola de Herramientas de privacidad en Campaign Standard cuando se elimine un contacto en Dynamics 365.

A continuación encontrará vínculos que le ayudarán a implementar las solicitudes de acceso o eliminación relacionadas con la privacidad en cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)

## Eliminación de contacto

Dado que Dynamics 365 es la fuente de la verdad, las eliminaciones de contacto en Dynamics 365 se reflejarán en la Campaña.

Cuando se elimina un contacto en Dynamics 365, la integración coloca en la cola una solicitud de eliminación relacionada con la privacidad en la pantalla de herramientas o solicitud de privacidad de Campaña.  Si ha desactivado el proceso de dos pasos para solicitudes de eliminación relacionadas con la privacidad, Campaña se encargará de la eliminación.

Sin embargo, si el proceso de dos pasos está habilitado, deberá entrar en la pantalla de solicitud/herramientas de privacidad, una vez que se hayan ejecutado los flujos de trabajo técnicos de privacidad, y confirmar si los registros están correctos para ser eliminados.  Sólo entonces Campaña se encargará de la eliminación.

Para obtener más información, consulte [Cómo ejecutar solicitudes de eliminación relacionadas con la privacidad en Adobe Campaign Standard](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/privacy/execute-privacy-requests.html)

>[!CAUTION]
>
>Si el proceso de dos pasos está habilitado para solicitudes de privacidad en Campaña, las eliminaciones en Dynamics 365 no se reflejarán automáticamente en la Campaña.  Deberá entrar en la pantalla de solicitud de privacidad de Campaña para confirmar las eliminaciones.

>[!NOTE]
>
>Esta integración crea una solicitud con el ID externo (es decir, el ID de contacto de Dynamics 365) como identificador de registro/perfil.

## Desactivación

Debido a las diferencias en los atributos de exclusión entre Dynamics 365 y la Campaña, y a las diferencias en los requisitos comerciales de cada cliente, la asignación de exclusión se ha dejado como un ejercicio para que el cliente lo complete. Es importante asegurarse de que las opciones de exclusión se asignan correctamente entre los sistemas para que las preferencias de exclusión de los usuarios finales se mantengan y no reciban una comunicación a través de un canal del que hayan exclusión.

Tenga en cuenta que en las asignaciones de exclusión solo se pueden usar atributos de Campaña con el prefijo &quot;blackList&quot; (por ejemplo, blackListEmail) o el atributo específico para la exclusión de CCPA.  En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;doNot&quot;; sin embargo, también puede utilizar atributos personalizados que ha creado para fines de exclusión si los tipos de datos son compatibles.

Al aprovisionar la integración, tendrá la oportunidad de especificar la configuración de exclusión que necesita para su negocio:

* Dynamics 365 es la fuente de la verdad para las exclusiones: los atributos de exclusión se sincronizarán en una dirección de Dynamics 365 a Campaign Standard
* Campaign Standard es la fuente de la verdad para las exclusiones: los atributos de exclusión se sincronizarán en una dirección desde Campaign Standard a Dynamics 365
* Dynamics 365 AND Campaign Standard son dos fuentes de verdad: los atributos de exclusión se sincronizarán bidireccionalmente entre Campaign Standard y Dynamics 365

Siga las instrucciones posteriores al aprovisionamiento de la guía del usuario [Unifi](https://drive.google.com/drive/folders/16seHF45e6bFxHX15zWLqFLEXymCuA_wn) para asignar correctamente estos valores.

La configuración bidireccional de exclusión utiliza la lógica para determinar qué valor se debe escribir en ambos sistemas.  La lógica compara las marcas de hora entre los dos sistemas (cambio de nivel de registro en Dynamics 365, cambio de nivel de atributo en la Campaña) para determinar qué sistema prevalece.  Si la Campaña contiene la marca de tiempo más reciente, prevalece el valor de Campaña.  Si Dynamics 365 contiene la marca de tiempo más reciente o si son iguales, entonces opt-out=TRUE ganará (suponiendo que uno de los valores sea TRUE).

**Rechazos en virtud de la Ley de Protección al Consumidor de California (CCPA) y legislación similar.**

La función de configuración de exclusión bidireccional no es capaz actualmente de cumplir ciertos requisitos legales de la CCPA y/o de otras leyes de privacidad de datos. Los clientes que deben cumplir con la CCPA o requisitos legales similares relacionados con las exclusiones son responsables de implementar su propia solución de terceros para realizar sincronizaciones bidireccionales.

>[!NOTE]
>
>Se recomienda que, si su compañía no requiere la compatibilidad con la exclusión bidireccional, seleccione una opción de exclusión en una dirección.

>[!NOTE]
>
>Revise y, si procede, actualice las reglas de tipología predeterminadas y específicas del Adobe Campaign antes de realizar cambios aquí para asegurarse de que dichos cambios se apliquen correctamente a todas las comunicaciones salientes. Por ejemplo: asegúrese de que las asignaciones a las preferencias de exclusión reflejen con precisión las opciones de intención/comunicación del destinatario y no interrumpan involuntariamente el envío de relación o mensajes transaccionales, como las confirmaciones de pedidos de clientes.

## Datos de Campaña existentes

Esta integración sincronizará Contactos y entidades personalizadas de Dynamics 365 a Campaña. Los registros de Campaña creados fuera de la integración (es decir, no creados por el trabajo de sincronización) no se verán afectados por la integración, incluidos los registros de Campaña existentes en el momento de la configuración de la integración.

Debido a que esta integración utiliza el **[!UICONTROL externalId]** campo de Campaign Standard para sincronizar registros de perfiles de Campaña con registros de contacto de Dynamics 365, este campo de Campaña (**[!UICONTROL externalId]** ) debe rellenarse con Dynamics 365 **[!UICONTROL contactId]** para los registros que desea sincronizar desde Dynamics 365.  Las entidades personalizadas también deberán tener este campo presente y rellenado correctamente para mantener la sincronización.  No obstante, tenga en cuenta que Dynamics 365 seguirá siendo la fuente de la verdad y que los datos del perfil de Campaña se pueden sobrescribir a medida que la integración detecte actualizaciones en Dynamics 365.  También es posible que se requieran otros pasos para habilitar la integración, según la implementación existente; por lo tanto, se recomienda trabajar en estrecha colaboración con el contacto técnico de Adobe.

>[!NOTE]
>
>Debido a la complejidad de las implementaciones de clientes existentes, se recomienda trabajar con su contacto técnico de Adobe al planificar y configurar la integración.
