---
title: Campaña y gestión de datos de Microsoft Dynamics 365
description: Obtenga información sobre cómo Campaign Standard y Microsoft Dynamics 365 administran datos comunes
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 621c29ae08770b50629ba3d27116f93f8b5c3f62
workflow-type: tm+mt
source-wordcount: '1439'
ht-degree: 0%

---


# Administrar datos entre Campaña y Microsoft Dynamics 365

## Fuente de verdad para la sincronización unidireccional

Para la sincronización de contactos y entidades personalizadas, esta integración trata a Dynamics 365 como la fuente de la verdad.  Cualquier cambio en los atributos sincronizados debe realizarse en Dynamics 365, no en Campaña.  Si los cambios se realizan en Campaña, se pueden sobrescribir en Campaña durante la sincronización, ya que la sincronización está en una dirección.

## Eliminación de contacto

Si lo desea, la integración se puede configurar para que emita llamadas de eliminación de perfil a la Campaña cuando se elimine un contacto en Dynamics 365, para ayudar a mantener la integridad de los datos.

Sin embargo, la eliminación de un perfil es distinta de la eliminación de privacidad. Una eliminación de privacidad en la Campaña eliminará el registro de perfil de Campaña y las entradas de registro asociadas; mientras que una eliminación regular de perfiles sólo eliminará el registro de perfiles ACS, dejando remanentes en los registros de Campañas.

Si la función de eliminación de perfil está habilitada en la integración, deberán seguirse pasos adicionales para procesar correctamente las solicitudes de privacidad del sujeto de datos. Consulte los pasos de la [sección siguiente](#manage-privacy-requests).

## Privacidad

### Administrar solicitudes de privacidad {#manage-privacy-requests}

Esta integración está diseñada para transferir datos de usuarios finales (incluida, entre otros, la información personal, si está incluida en los datos de usuarios finales), entre Microsoft Dynamics 365 y Adobe Campaign Standard. Como controlador de datos, su compañía es responsable de cumplir con las leyes y regulaciones de privacidad aplicables a su recopilación y uso de datos personales.

La integración no emite ninguna privacidad del sujeto de datos (por ejemplo, RGPD) elimina o gestiona ninguna otra solicitud de privacidad (con excepción de la exclusión). Al procesar las solicitudes de privacidad, debe hacerlo en Dynamics 365 y en la Campaña (a través de Adobe Experience Platform Privacy Service) de forma independiente.

Si ha configurado la integración para que emita llamadas de eliminación de perfil regulares a la Campaña cuando se elimine un contacto en Dynamics 365, deben seguirse los pasos a continuación. Asegúrese de que no se haya realizado ninguna actualización en el registro en cuestión durante este proceso.

1. Enviar solicitud de eliminación de privacidad a [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Supervisar la solicitud hasta que se haya completado correctamente

1. Verificar que el registro ya no está en la instancia de Campaña

1. (Poco después) Emitir eliminación de privacidad en Dynamics 365

1. Verificar que el registro se ha eliminado de ambos sistemas

A continuación encontrará vínculos que le ayudarán a implementar las solicitudes de acceso o eliminación relacionadas con la privacidad en cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/microsoft-365/compliance/gdpr-dsr-dynamics365?toc=/microsoft-365/enterprise/toc.json)

* [Adobe Campaign Standard](https://www.adobe.io/apis/experiencecloud/gdpr/docs.html)


### Privacidad y recursos vinculados {#privacy-linked-resources}

Si algún registro de recursos personalizados de Campaña contiene información personal, aplicable al uso de la Campaña por parte de un cliente, dicho registro debe vincularse a un registro de perfiles de Campaña correspondiente (ya sea directamente o a través de otro recurso personalizado) de modo que una eliminación relacionada con la privacidad en el registro de perfil también pueda eliminar el registro de recursos personalizados vinculado que contenga información personal; las opciones de vinculación y eliminación entre las entidades deben configurarse para permitir esta eliminación en cascada de los registros vinculados. La información personal no debe introducirse en un recurso personalizado que no esté vinculado al perfil.

Obtenga información sobre cómo asignar recursos de Campaña y entidades de Dynamics 365 [en esta sección](../../integrating/using/map-campaign-custom-resources-and-dynamics-365-custom-entities.md).

## Desactivación

Debido a las diferencias en los atributos de exclusión entre Dynamics 365 y la Campaña, y a las diferencias en los requisitos comerciales de cada cliente, la asignación de exclusión se ha dejado como un ejercicio para que el cliente lo complete.  Es importante asegurarse de que las opciones de exclusión se asignan correctamente entre sistemas para que las preferencias de exclusión de los usuarios finales se mantengan y no reciban una comunicación a través de un canal del que hayan exclusión.

Tenga en cuenta que en las asignaciones de exclusión solo se pueden usar atributos de Campaña con el prefijo &quot;lista de bloqueados&quot; (por ejemplo, blockListEmail) o el atributo específico para la exclusión de CCPA.  En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;donot&quot;; sin embargo, también puede utilizar otros atributos para fines de exclusión si los tipos de datos son compatibles.

Al aprovisionar la integración, tendrá la oportunidad de especificar la configuración de exclusión que necesita para su negocio:

* Dynamics 365 es la fuente de la verdad para las exclusiones: los atributos de exclusión se sincronizarán en una dirección desde Dynamics 365 a Campaña
* La campaña es la fuente de la verdad para las exclusiones: los atributos de exclusión se sincronizarán en una dirección desde la Campaña a Dynamics 365
* Dynamics 365 AND Campaña son dos fuentes de verdad: los atributos de exclusión se sincronizarán bidireccionalmente entre Campaña y Dynamics 365

Como alternativa, si tiene un proceso independiente para administrar la sincronización de la exclusión entre los sistemas, el flujo de datos de exclusión de la integración puede deshabilitarse.

La configuración de exclusión bidireccional utiliza la lógica para determinar qué valor se debe escribir en ambos sistemas. La lógica compara las marcas de hora entre los dos sistemas (cambio de nivel de registro en Dynamics 365, cambio de nivel de atributo en la Campaña) para determinar qué sistema prevalece. Si la Campaña contiene la marca de tiempo más reciente, prevalece el valor de Campaña. Si Dynamics 365 contiene la marca de tiempo más reciente o si son iguales, entonces opt-out=TRUE ganará (suponiendo que uno de los valores sea TRUE).

>[!NOTE]
>
>Revise y, si corresponde, actualice las reglas de tipología predeterminadas y específicas de Adobe Campaign antes de realizar cambios aquí para asegurarse de que dichos cambios se apliquen correctamente a todas las comunicaciones salientes. Por ejemplo: asegúrese de que las asignaciones a las preferencias de exclusión reflejen con precisión las opciones de intención/comunicación del destinatario y no interrumpan involuntariamente el envío de relación o mensajes transaccionales, como las confirmaciones de pedidos de clientes.

Si ha seleccionado la configuración de exclusión bidireccional o de Campaña a la configuración de exclusión de Dynamics 365, los datos de exclusión de Campaña se exportarán periódicamente a través del flujo de trabajo a su área de almacenamiento de SFTP de Campaña (consulte &quot;Campaña del uso de SFTP más abajo&quot;). En el evento de que los flujos de trabajo de exclusión de la Campaña dejan de ejecutarse, deberá reiniciar manualmente lo antes posible para reducir la posibilidad de que se pierdan las sincronizaciones de exclusión.

## Uso de SFTP de campaña

El almacenamiento SFTP de su Campaña deberá ser utilizado por la integración en los casos de uso siguientes.  Deberá asegurarse de que su cuenta SFTP tenga la capacidad de almacenamiento adecuada para dar cabida a estos casos de uso.  Superar la capacidad de almacenamiento SFTP con licencia puede afectar gravemente el uso funcional de la Campaña, la integración o la cuenta SFTP.

| Ejemplo de uso | Descripción |
|---|---|
| Carga de datos inicial | Las tablas de Dynamics 365 con más de 500.000 registros deberán exportarse al almacenamiento SFTP de Campaña para importarse mediante el flujo de trabajo. A partir de ese momento, la integración utilizará API para actualizaciones incrementales. |
| Opción de exclusión y Campaña bidireccional a la exclusión unidireccional de Dynamics 365 | La exclusión bidireccional y la Campaña a los flujos de datos de exclusión uni-direccional de Dynamics 365 utilizarán el almacenamiento SFTP de Campaña. Un flujo de trabajo de ACS exportará cambios incrementales a la carpeta SFTP. Desde allí, la integración recogerá los registros y el proceso. |
| Recuperación ante desastres | En el improbable evento de un desastre del sistema, se seguirá el caso de uso de &quot;Carga de datos inicial&quot; para alimentar las actualizaciones incrementales de la Campaña que no se realizaron. |

## Datos de Campaña existentes

Esta integración sincronizará los contactos y las entidades personalizadas de Dynamics 365 a Campaña. Los registros de campaña creados fuera de la integración (es decir, no creados por el trabajo de sincronización) no se modificarán mediante la integración, incluidos los registros de Campaña existentes en el momento de la configuración de la integración.

Debido a que esta integración utiliza el **[!UICONTROL externalId]** campo de la Campaña para sincronizar registros de perfiles de Campaña con registros de contacto de Dynamics 365, este campo de Campaña (**[!UICONTROL externalId]** ) debe rellenarse con Dynamics 365 **[!UICONTROL contactId]** para los registros que desea sincronizar desde Dynamics 365.  Las entidades personalizadas también se sincronizan con un ID exclusivo de Dynamics 365. La entidad personalizada de Campaña deberá incluir este atributo de ID como columna de tabla. La columna externalId puede utilizarse para almacenar este valor de atributo, pero no es necesaria para las entidades personalizadas de Campaña.

Tenga en cuenta que Dynamics 365 sigue siendo la fuente de la verdad y que los datos del perfil de Campaña se pueden sobrescribir a medida que la integración detecta actualizaciones en Dynamics 365.  También es posible que se requieran otros pasos para habilitar la integración, según la implementación existente; por lo tanto, se recomienda que trabaje estrechamente con el contacto técnico de su Adobe.

>[!NOTE]
>
>Debido a la complejidad de las implementaciones de clientes existentes, se recomienda que trabaje con el contacto técnico de Adobe al planificar y configurar la integración.

## Frecuencia de sincronización de datos

La integración utiliza una arquitectura que permite detectar las actualizaciones y agregarlas a la &quot;cola&quot; de procesamiento poco después de que se produzcan en Dynamics 365 (es decir, flujo continuo, no procesamiento por lotes). Por este motivo, no es necesario especificar las frecuencias o programaciones de ejecución del flujo de datos.

La excepción a esto son las Campañas bidireccionales y los flujos de datos de exclusión de Dynamics 365. Para estas configuraciones de exclusión, los registros ACS actualizados se exportan a SFTP a través del flujo de trabajo ACS una vez al día, tras lo cual la herramienta de integración lee el archivo y procesa el registro.

## Acuerdo de uso de datos

Si se encuentra en las regiones EMEA o APAC, algunos de sus datos se procesarán en Estados Unidos como parte de esta integración. Para obtener más información, consulte [esta sección](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).
