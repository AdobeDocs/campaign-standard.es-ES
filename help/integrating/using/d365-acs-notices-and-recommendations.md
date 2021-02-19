---
solution: Campaign Standard
product: campaign
title: Campaña y gestión de datos de Microsoft Dynamics 365
description: Obtenga información sobre cómo Campaign Standard y Microsoft Dynamics 365 administran datos comunes
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
translation-type: tm+mt
source-git-commit: cce30fd5cd3d5d63563d1dab3bb1e7554c26fb3e
workflow-type: tm+mt
source-wordcount: '2467'
ht-degree: 1%

---


# Prácticas recomendadas y limitaciones {#acs-msdyn-best-practices}

## Administrar datos {#acs-msdyn-manage-data}

Para la sincronización de contactos y entidades personalizadas, esta integración trata a **Microsoft Dynamics 365 como la fuente de verdad**.  Cualquier cambio en los atributos sincronizados debe realizarse en Dynamics 365 y no en Adobe Campaign Standard).  Si los cambios se realizan en Campaña, se pueden sobrescribir en Campaña durante la sincronización, ya que la sincronización está en una dirección.

La integración puede configurarse de forma opcional para emitir llamadas de eliminación de perfil a la Campaña cuando se elimina un contacto en Dynamics 365 para ayudar a mantener la integridad de los datos. Sin embargo, la eliminación de un perfil es distinta de la eliminación de privacidad. Una eliminación de privacidad en la Campaña eliminará el registro de perfil de Campaña y las entradas de registro asociadas; mientras que una eliminación regular de perfiles sólo eliminará el registro de perfiles de Campaña, dejando remanentes en los registros de Campañas. Si la función de eliminación de perfil está habilitada en la integración, deberán seguirse pasos adicionales para procesar correctamente las solicitudes de privacidad del sujeto de datos. Consulte los pasos de la sección [Privacidad a continuación](#manage-privacy-requests).

## Privacidad{#acs-msdyn-manage-privacy}

Esta integración está diseñada para transferir datos del usuario final entre Microsoft Dynamics 365 y Adobe Campaign Standard. Estos datos incluyen información personal si están contenidos en los datos del usuario final.  Como controlador de datos, su compañía es responsable de cumplir con las leyes y regulaciones de privacidad aplicables a su recopilación y uso de datos personales.

Esta integración está diseñada para transferir datos de usuarios finales (incluida, entre otros, la información personal, si está incluida en los datos de usuarios finales), entre Microsoft Dynamics 365 y Adobe Campaign Standard. Como controlador de datos, su compañía es responsable de cumplir con las leyes y regulaciones de privacidad aplicables a su recopilación y uso de datos personales.

La integración no emite ninguna privacidad del sujeto de datos (por ejemplo, RGPD) elimina o gestiona ninguna otra solicitud de privacidad (con excepción de la exclusión). Al procesar solicitudes de privacidad, debe hacerlo en Microsoft Dynamics 365 y en Campaña (mediante Adobe Experience Platform Privacy Service) de forma independiente.

Si ha configurado la integración para que emita llamadas de eliminación de perfil regulares a la Campaña cuando se elimine un contacto en Dynamics 365, deben seguirse los pasos a continuación. Asegúrese de que no se haya realizado ninguna actualización en el registro en cuestión durante este proceso.

1. Emitir la solicitud de eliminación de privacidad a [Adobe Experience Platform Privacy Service](https://www.adobe.io/apis/experiencecloud/gdpr.html)

1. Supervisar la solicitud hasta que se haya completado correctamente

1. Verificar que el registro ya no está en la instancia de Campaña

1. (Poco después) Emitir eliminación de privacidad en Dynamics 365

1. Verificar que el registro se ha eliminado de ambos sistemas

A continuación encontrará vínculos que le ayudarán a implementar las solicitudes de acceso o eliminación relacionadas con la privacidad en cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Si algún registro de recursos personalizados de Campaña contiene información personal, aplicable al uso de la Campaña por parte de un cliente, dicho registro debe vincularse a un registro de perfiles de Campaña correspondiente (ya sea directamente o a través de otro recurso personalizado) de modo que una eliminación relacionada con la privacidad en el registro de perfil también pueda eliminar el registro de recursos personalizados vinculado que contenga información personal; las opciones de vinculación y eliminación entre las entidades deben configurarse para permitir esta eliminación en cascada de los registros vinculados. La información personal no debe introducirse en un recurso personalizado que no esté vinculado al perfil.

## Opción de exclusión {#opt-out}

Debido a las diferencias en los atributos de exclusión entre Microsoft Dynamics 365 y la Campaña, y a las diferencias en los requisitos comerciales de cada cliente, la asignación de exclusión se ha dejado como un ejercicio para que el cliente lo complete.  Es importante asegurarse de que las opciones de exclusión se asignan correctamente entre los sistemas para que las preferencias de exclusión de los usuarios finales se mantengan y no reciban una comunicación a través de un canal del que hayan exclusión.

Tenga en cuenta que en las asignaciones de exclusión solo se pueden usar las siguientes opciones:

* Atributos de campaña con el prefijo &#39;Ya no contacto por&#39; (por ejemplo, ya no contacto por correo electrónico) o

* el atributo específico de CCPA

Encontrará más información sobre los campos de entidad de Perfil [aquí](../../developing/using/datamodel-profile.md).

En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;no&quot;, pero también puede utilizar otros atributos para la exclusión si los tipos de datos son compatibles.

Al aprovisionar la integración, tendrá la oportunidad de especificar la configuración de exclusión que necesita para su negocio:

* **Unidireccional (Microsoft Dynamics 365 a Campaña)**: Dynamics 365 es la fuente de la verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde Dynamics 365 al Campaign Standard
* **Unidireccional (Campaña a Microsoft Dynamics 365)**: Campaign Standard es la fuente de la verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde Campaign Standard a Dynamics 365
* **Bidireccional**: Dynamics 365 AND Campaign Standard son fuentes de verdad. Los atributos de exclusión se sincronizarán bidireccionalmente entre Campaign Standard y Dynamics 365

Como alternativa, si tiene un proceso independiente para administrar la sincronización de la exclusión entre los sistemas, el flujo de datos de exclusión de la integración puede deshabilitarse.

La configuración de exclusión bidireccional utiliza la lógica para determinar qué valor se debe escribir en ambos sistemas. La lógica compara las marcas de hora entre los dos sistemas (cambio de nivel de registro en Dynamics 365, cambio de nivel de atributo en la Campaña) para determinar qué sistema prevalece. Si la Campaña contiene la marca de tiempo más reciente, prevalece el valor de Campaña. Si Dynamics 365 contiene la marca de tiempo más reciente o si son iguales, entonces opt-out=TRUE ganará (suponiendo que uno de los valores sea TRUE).

Obtenga información sobre cómo seleccionar las opciones de inclusión/exclusión en [esta sección](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Revise y, si corresponde, actualice las reglas de tipología predeterminadas y específicas de Adobe Campaign antes de realizar cambios aquí para asegurarse de que dichos cambios se apliquen correctamente a todas las comunicaciones salientes. Por ejemplo: asegúrese de que las asignaciones a las preferencias de exclusión reflejen con precisión las opciones de intención/comunicación del destinatario y no interrumpan involuntariamente el envío de relación o mensajes transaccionales, como las confirmaciones de pedidos de clientes.

Si seleccionó la configuración de exclusión **bidireccional** o **unidireccional (Campaña a Microsoft Dynamics 365)**, los datos de exclusión de Campaña se exportarán periódicamente a través del flujo de trabajo a su área de almacenamiento de SFTP de Campaña (consulte &quot;Uso de SFTP de Campaña más abajo&quot;). En el evento de que los flujos de trabajo de exclusión de la Campaña dejan de ejecutarse, deberá reiniciar manualmente lo antes posible para reducir la posibilidad de que se pierdan las sincronizaciones de exclusión.

>[!IMPORTANT]
>
>Si necesita la configuración de exclusión **bidireccional** o **unidireccional (Campaña a Microsoft Dynamics 365)**, deberá hacer la solicitud al contacto técnico de su Adobe para que se configuren los flujos de trabajo de exclusión en la instancia de Campaña

## Uso de SFTP de campaña

El almacenamiento SFTP de su Campaña deberá ser utilizado por la integración en los casos de uso siguientes.  Deberá asegurarse de que su cuenta SFTP tenga la capacidad de almacenamiento adecuada para dar cabida a estos casos de uso. Superar la capacidad de almacenamiento SFTP con licencia puede afectar gravemente el uso funcional de la Campaña, la integración o la cuenta SFTP.

| Ejemplo de uso | Descripción |
|---|---|
| Bidireccional y unidireccional (Campaña a Microsoft Dynamics 365) | Los flujos de datos de exclusión bidireccionales y unidireccionales (Campaña a Microsoft Dynamics 365) utilizarán el almacenamiento SFTP de Campaña. Un flujo de trabajo de Campaña exportará los cambios incrementales a la carpeta SFTP. Desde allí, la integración recogerá los registros y el proceso. |
| Registros de exclusión | Los registros de salida del conector serán útiles para solucionar el problema de la integración. Los registros de salida pueden activarse o desactivarse. |


>[!IMPORTANT]
>
>Usted es responsable de la información a la que accede y descarga desde las carpetas SFTP. Si la información contiene datos personales, usted es responsable de cumplir con las leyes y regulaciones de privacidad aplicables. [Más información](#acs-msdyn-manage-privacy).

## Gestión de datos

### Datos de Campaña existentes

Esta integración sincronizará los contactos y las entidades personalizadas de Microsoft Dynamics 365 a Campaña. Los registros de campaña creados fuera de la integración (es decir, no creados por el trabajo de sincronización) no se modificarán mediante la integración, incluidos los registros de Campaña existentes en el momento de la configuración de la integración.

Debido a que esta integración utiliza el campo **[!UICONTROL externalId]** en la Campaña para sincronizar registros de perfiles de Campaña con registros de contacto de Dynamics 365, este campo de Campaña (**[!UICONTROL externalId]** ) debe rellenarse con Microsoft Dynamics 365 **[!UICONTROL contactId]** para los registros que desee sincronizar desde Microsoft Dynamics 365.  Las entidades personalizadas también se sincronizan con un ID único de Microsoft Dynamics 365. La entidad personalizada de Campaña deberá incluir este atributo de ID como columna de tabla. La columna externalId puede utilizarse para almacenar este valor de atributo, pero no es necesaria para las entidades personalizadas de Campaña.

Tenga en cuenta que Microsoft Dynamics 365 sigue siendo la fuente de la verdad y que los datos del perfil de Campaña se pueden sobrescribir a medida que la integración detecta actualizaciones en Dynamics 365.  También es posible que se requieran otros pasos para habilitar la integración, según la implementación existente; por lo tanto, se recomienda que trabaje estrechamente con el contacto técnico de su Adobe.

>[!NOTE]
>
>Debido a la complejidad de las implementaciones de clientes existentes, se recomienda que trabaje con el contacto técnico de Adobe al planificar y configurar la integración.

### Frecuencia de sincronización de datos

La integración utiliza una arquitectura que permite detectar las actualizaciones y agregarlas a la &quot;cola&quot; de procesamiento poco después de que se produzcan en Microsoft Dynamics 365 (es decir, flujo continuo, no procesamiento por lotes). Por este motivo, no es necesario especificar las frecuencias o programaciones de ejecución del flujo de datos.

La excepción a esto son los flujos de datos de exclusión bidireccionales y de Campaña a Dynamics 365. Para estas configuraciones de exclusión, los registros de Campaña actualizados se exportan a SFTP a través de un flujo de trabajo de Campaña una vez al día, tras lo cual la herramienta de integración lee el archivo y procesa el registro.

### Acuerdo de uso de datos

Si se encuentra en las regiones EMEA o APAC, algunos de sus datos se procesarán en Estados Unidos como parte de esta integración. Para obtener más información, consulte [esta sección](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Guardias y limitaciones

>[!IMPORTANT]
>
>Ciertas acciones de su parte (por ejemplo, ingesta inicial de registros, reproducción de datos de registros, etc.) podría resultar en una gran carga de registros que se ingieran de Microsoft Dynamics 365 a su instancia de Adobe Campaign. Para reducir el riesgo de problemas de rendimiento, se recomienda que detenga todos los procesos de Campaña (por ejemplo, sin actividad de marketing, sin ejecución de flujos de trabajo, etc.) hasta después de que la gran carga de registros se haya ingerido en Campaña.

### Entidades personalizadas

La [integración de Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) admite entidades personalizadas, lo que permite sincronizar las entidades personalizadas de Dynamics 365 con los recursos personalizados correspondientes en Campaña.

La integración admite tablas vinculadas y no vinculadas.

Al configurar los flujos de datos de entidad personalizados, es importante tener en cuenta lo siguiente:

* La creación y modificación de recursos personalizados de Campaña son operaciones sensibles que deben realizar únicamente los usuarios expertos.
* Para los flujos de datos de entidad personalizados, el seguimiento de cambios debe habilitarse en Dynamics 365 para las entidades personalizadas sincronizadas.
* Si un registro principal y un registro secundario vinculado se crean casi al mismo tiempo en Dynamics 365, debido al procesamiento paralelo de la integración, existe una pequeña posibilidad de que se pueda escribir un nuevo registro secundario en la Campaña antes de su registro principal.

* Si el principal y el secundario están vinculados en el lado de la Campaña mediante la opción **1 vínculo simple de cardinalidad**, el registro secundario permanecerá oculto e inaccesible (a través de la interfaz de usuario o la API) hasta que el registro principal llegue a la Campaña.

* (Suponiendo **1 vínculo simple de cardinalidad** en la Campaña) Si el registro secundario se actualiza o elimina en Dynamics 365 y ese cambio se escribe en la Campaña antes de que el registro principal se muestre en la Campaña (no es probable, pero es una posibilidad remota), esa actualización o eliminación no se procesará en la Campaña y se generará un error. En el caso de la actualización, el registro en cuestión deberá actualizarse de nuevo en Dynamics 365 para sincronizar el registro actualizado. En el caso de la eliminación, el registro en cuestión tendrá que encargarse por separado en la parte de la Campaña, ya que en Dynamics 365 ya no hay ningún registro que eliminar o actualizar.

* Si se encuentra en una situación en la que cree que tiene registros secundarios ocultos y no hay manera de acceder a ellos, puede cambiar temporalmente el tipo de vínculo de cardinalidad a **0 o 1 vínculo simple de cardinalidad** para acceder a esos registros.

En esta sección [encontrará una descripción general más completa de los recursos personalizados de Campaña.](../../developing/using/key-steps-to-add-a-resource.md)

### Guardias de integración

Al planificar el uso de esta integración, deben tenerse en cuenta las siguientes barreras. Consulte con el representante técnico de su Adobe si cree que excede estas protecciones.

* Deberá obtener una licencia del paquete de Campaña adecuado para admitir el volumen de llamadas del motor generado por la integración. Exceder el volumen de llamadas al motor con licencia podría causar una degradación en el rendimiento de la Campaña.

   Utilice lo siguiente para ayudarle a calcular el volumen de llamadas del motor a partir de la integración:

   * Inserciones de registros (es decir, nuevo registro): 1 llamada al motor
   * El registro elimina: 1 llamada al motor
   * Actualizaciones de registros: 2 llamadas de motor (solo 1 llamada si el registro de destino es idéntico al registro de origen, es decir, si no se modifica el registro de Campaña)

   Al calcular el volumen de llamadas del motor de Campaña general, es importante tener en cuenta otras fuentes de llamadas del motor, como páginas de aterrizaje, WebApps, JSSP, API, registros de aplicaciones móviles, etc.

   Información del paquete de Campaña de vista aquí: https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html

* La integración admite un máximo de 30 millones de contactos.

* La oferta de integración estándar incluye compatibilidad con hasta cinco entidades personalizadas, cada una con un tamaño máximo de 50 columnas.

* Deberá crear y publicar sus recursos personalizados antes de implementar la integración.

* La profundidad máxima de tabla al enlazar tablas es de dos (por ejemplo: tabla1->tabla2->tabla3)

* La compatibilidad con los tipos de datos de Microsoft Dynamic 365 es limitada. Si el modelo de datos contiene un tipo de datos distinto de los tipos de datos simples (por ejemplo, cadenas, enteros, decimales, etc.), es posible que tenga que actualizar el modelo de datos antes de utilizar la integración.

* Si elige conservar los datos existentes en las entidades personalizadas de Campaña, deberá preparar los datos para la integración.

* Es posible que sea necesario establecer ventanas de mantenimiento integradas entre el Adobe y el cliente.

* Tenga en cuenta que los incrementos significativos o los &quot;picos&quot; en el uso de la integración (por ejemplo, un aumento brusco de los registros nuevos o actualizados) pueden causar desaceleraciones en la sincronización de datos.

* Como parte de la integración, se espera que complete los pasos de configuración previos a la integración en Microsoft Azure y Dynamics 365. Consulte los pasos de configuración [en esta página](../../integrating/using/d365-acs-configure-d365.md)

* Se espera que traiga los modelos de datos de Dynamics 365 y Campaña a la integración y que los mantenga.

### Límites de integración

La integración se diseñó para resolver el caso de uso general del movimiento de datos común entre Microsoft Dynamics 365 y Campaña, pero no está pensada para abordar todos los casos de uso específicos de cada cliente:

* La integración no emite ninguna eliminación de privacidad (por ejemplo, RGPD). La responsabilidad de cumplir las solicitudes de privacidad de los usuarios finales recae en el cliente; estas solicitudes deben realizarse en Campaña (a través de Adobe Experience Platform Privacy Service) y Dynamics 365 de forma independiente. Si lo desea, la integración puede generar eliminaciones regulares para facilitar la sincronización de datos.   Consulte [la sección Privacidad](#manage-privacy-requests) para obtener más información.

* No se sincronizarán datos de perfiles ni de entidades personalizadas de la Campaña a Dynamics 365, a excepción de la información de exclusión (si la configura el cliente).

* La administración de suscripciones de campaña (es decir, suscripciones/cancelaciones de suscripción) no es compatible de forma nativa.

* No se admite la composición y activación de campañas de correo electrónico de Campaña desde Dynamics 365.

* La integración **no** admite la remodelación de datos entre los modelos de datos de Dynamics 365 y Campaign Standard. Se espera que la integración sincronice una tabla de Dynamics 365 con una tabla de Campaña.
