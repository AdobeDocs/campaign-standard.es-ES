---
title: Administración de datos de Campaign y Microsoft Dynamics 365
description: Descubra cómo Campaign Standard y Microsoft Dynamics 365 administran datos comunes
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-ms-dynamics
feature: Microsoft CRM Integration
role: Data Architect
level: Experienced
exl-id: aab6f005-f3da-4c0b-b856-da8504e611dc
source-git-commit: 17522f4df86c7fb46593472316d57b4ba4acee2b
workflow-type: tm+mt
source-wordcount: '2523'
ht-degree: 1%

---

# Prácticas recomendadas y limitaciones {#acs-msdyn-best-practices}

## Administración de datos {#acs-msdyn-manage-data}

Para la sincronización de contactos y entidades personalizadas, esta integración trata a **Microsoft Dynamics 365 como la fuente de la verdad**.  Cualquier cambio en los atributos sincronizados debe realizarse en Dynamics 365 (y no en Adobe Campaign Standard).  Si los cambios se realizan en Campaign, pueden sobrescribirse finalmente en Campaign durante la sincronización, ya que la sincronización va en una dirección.

La integración se puede configurar de forma opcional para que emita llamadas de eliminación de perfiles a Campaign cuando se elimine un contacto en Dynamics 365 para ayudar a mantener la integridad de los datos. Sin embargo, una eliminación de perfil es diferente a una eliminación de privacidad. Una eliminación de privacidad en Campaign eliminará el registro de perfil de Campaign y las entradas de registro asociadas; mientras que una eliminación de perfil normal solo eliminará el registro de perfil de Campaign, dejando remanentes en los registros de Campaign. Si la función de eliminación de perfiles está habilitada en la integración, se deberán seguir pasos adicionales para procesar correctamente las solicitudes de privacidad del interesado. Consulte los pasos de la sección [Privacidad a continuación](#manage-privacy-requests).

## Privacidad{#acs-msdyn-manage-privacy}

Esta integración está diseñada para transferir datos del usuario final entre Microsoft Dynamics 365 y Adobe Campaign Standard. Estos datos incluyen información personal si está contenida en sus datos de usuario final.  Como responsable del tratamiento de datos, su empresa es responsable de cumplir con las leyes y regulaciones de privacidad aplicables a su recopilación y uso de datos personales.

Esta integración está diseñada para transferir datos del usuario final (incluida, entre otras cosas, la información personal, si está contenida en los datos del usuario final), entre Microsoft Dynamics 365 y Adobe Campaign Standard. Como responsable del tratamiento de datos, su empresa es responsable de cumplir con las leyes y regulaciones de privacidad aplicables a su recopilación y uso de datos personales.

La integración no emite ninguna política de privacidad del sujeto de los datos (por ejemplo, RGPD), elimina ni gestiona ninguna otra solicitud de privacidad (con la excepción de la exclusión). Al procesar solicitudes de privacidad, debe hacerlo tanto en Microsoft Dynamics 365 como en Campaign (a través de Adobe Experience Platform Privacy Service) de forma independiente.

Si ha configurado la integración para que emita llamadas regulares de eliminación de perfiles a Campaign cuando se elimine un contacto en Dynamics 365, se deben seguir los pasos a continuación. Asegúrese de que no se realicen actualizaciones en el registro en cuestión durante este proceso.

1. Enviar solicitud de eliminación de privacidad a [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. Monitorizar la solicitud hasta que se haya completado correctamente

1. Verifique que el registro ya no esté en la instancia de Campaign

1. (Poco después) Eliminar la privacidad del problema en Dynamics 365

1. Verificar que el registro se haya eliminado de ambos sistemas


>[!IMPORTANT]
>
>Si algún registro de recurso personalizado de Campaign contiene información personal, aplicable al uso de Campaign por parte de un cliente, dicho registro debe vincularse a un registro de perfil de Campaign correspondiente (directamente o a través de otro recurso personalizado) para que una eliminación relacionada con la privacidad en el registro de perfil también pueda eliminar el registro de recurso personalizado vinculado que contiene información personal; las opciones de vinculación y eliminación entre las entidades deben configurarse para permitir esta eliminación en cascada de los registros vinculados. La información personal no debe introducirse en un recurso personalizado que no esté vinculado al perfil.

## Exclusión {#opt-out}

Debido a las diferencias en los atributos de exclusión entre Microsoft Dynamics 365 y Campaign, y a las diferencias en los requisitos comerciales de cada cliente, la asignación de exclusión se ha dejado como un ejercicio para que el cliente la complete.  Es importante asegurarse de que las exclusiones se asignen correctamente entre sistemas, de modo que las preferencias de exclusión del usuario final se mantengan y no reciba una comunicación a través del canal al que se ha excluido.

Tenga en cuenta que solo se pueden utilizar los siguientes elementos en las asignaciones de exclusión:

* Atributos de campaña con el prefijo &quot;Ya no se puede contactar por&quot; (por ejemplo, Ya no se puede contactar por correo electrónico) o

* el atributo específico de la CCPA

Encontrará más información sobre los campos de entidad de perfil [aquí](../../developing/using/datamodel-profile.md).

En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;no&quot;, pero también puede utilizar otros atributos para fines de exclusión si los tipos de datos son compatibles.

Al aprovisionar la integración, tendrá la oportunidad de especificar qué configuración de exclusión necesita para su negocio:

* **Unidireccional (de Microsoft Dynamics 365 a Campaign)**: Dynamics 365 es la fuente fiable para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde Dynamics 365 a Campaign Standard
* **Unidireccional (de Campaign a Microsoft Dynamics 365)**: El Campaign Standard es la fuente fiable de las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde Campaign Standard a Dynamics 365
* **Bidireccional**: Dynamics 365 AND Campaign Standard son fuentes de verdad. Los atributos de exclusión se sincronizarán bidireccionalmente entre Campaign Standard y Dynamics 365

Alternativamente, si tiene un proceso independiente para administrar la sincronización de exclusión entre los sistemas, se puede desactivar el flujo de datos de exclusión de la integración.

La configuración de exclusión bidireccional utiliza la lógica para determinar qué valor escribir en ambos sistemas. La lógica compara las marcas de tiempo entre los dos sistemas (cambio de nivel de registro en Dynamics 365, cambio de nivel de atributo en Campaign) para determinar qué sistema prevalece. Si Campaign contiene la marca de tiempo más reciente, prevalece el valor de Campaign. Si Dynamics 365 contiene la marca de tiempo más reciente o si son iguales, entonces opt-out=TRUE ganará (suponiendo que uno de los valores sea TRUE).

Aprenda a seleccionar las opciones de inclusión/exclusión en [esta sección](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Revise y, si procede, actualice las reglas de tipología predeterminadas y específicas en Adobe Campaign antes de realizar cambios aquí para garantizar que dichos cambios se apliquen correctamente a todas las comunicaciones salientes. Por ejemplo, asegúrese de que cualquier asignación a preferencias de exclusión refleje con precisión las opciones de intención/comunicación del destinatario y no interrumpa inadvertidamente la entrega de mensajes transaccionales o de relación, como confirmaciones de pedidos de clientes.

Si seleccionó la configuración de exclusión **Bidireccional** o **Unidireccional (de Campaign a Microsoft Dynamics 365)**, los datos de exclusión de Campaign se exportarán periódicamente a través del flujo de trabajo al área de almacenamiento SFTP de Campaign (consulte &quot;Uso de SFTP de Campaign a continuación&quot;). En caso de que los flujos de trabajo de exclusión de Campaign dejen de ejecutarse, deberá reiniciarse manualmente lo antes posible para reducir la posibilidad de que se pierdan sincronizaciones de exclusión.

>[!IMPORTANT]
>
>Si necesita la configuración de exclusión **Bidireccional** o **Unidireccional (de Campaign a Microsoft Dynamics 365)**, tendrá que realizar la solicitud al contacto técnico de Adobe para que se configuren los flujos de trabajo de exclusión en la instancia de Campaign

## Uso de SFTP de Campaign

La integración debe utilizar su almacenamiento SFTP de Campaign en los casos de uso que se indican a continuación.  Debe asegurarse de que su cuenta SFTP tenga la capacidad de almacenamiento adecuada para dar cabida a estos casos de uso. El exceso de la capacidad de almacenamiento SFTP con licencia puede afectar gravemente al uso funcional de Campaign, la integración o la cuenta SFTP.

| Ejemplo de uso | Descripción |
|---|---|
| Bidireccional y unidireccional (Campaign to Microsoft Dynamics 365) | Los flujos de datos de exclusión bidireccionales y unidireccionales (de Campaign a Microsoft Dynamics 365) utilizarán el almacenamiento SFTP de Campaign. Un flujo de trabajo de Campaign exportará los cambios incrementales a la carpeta SFTP. A partir de ahí, la integración recoge los registros y el proceso. |
| Registros de exclusión | Los registros de salida del conector serán útiles para solucionar los problemas de la integración. Los registros de salida se pueden activar y desactivar. |


>[!IMPORTANT]
>
>Usted es responsable de la información a la que accede y descarga desde las carpetas SFTP. Si la información contiene datos personales, usted es responsable de cumplir con las leyes y regulaciones de privacidad aplicables. [Más información](#acs-msdyn-manage-privacy).

## Administración de datos

### Datos de Campaign existentes

Esta integración sincroniza contactos y entidades personalizadas de Microsoft Dynamics 365 a Campaign. La integración no modifica los registros de campaña creados fuera de la integración (es decir, no creados por el trabajo de sincronización), incluidos los registros de campaña existentes en el momento de la configuración de la integración.

Debido a que esta integración utiliza el campo **[!UICONTROL externalId]** en Campaign para sincronizar los registros de perfil de Campaign con los registros de contacto de Dynamics 365, este campo de Campaign (**[!UICONTROL externalId]** ) debe rellenarse con Microsoft Dynamics 365 **[!UICONTROL contactId]** para los registros que desea sincronizar desde Microsoft Dynamics 365.  Las entidades personalizadas también se sincronizan con un ID único de Microsoft Dynamics 365. La entidad personalizada Campaign debe incluir este atributo de ID como una columna de tabla. La columna externalId se puede utilizar para almacenar este valor de atributo, pero no es necesaria para las entidades personalizadas de Campaign.

Tenga en cuenta que Microsoft Dynamics 365 sigue siendo la fuente fiable y que los datos del perfil de Campaign se pueden sobrescribir a medida que la integración detecta actualizaciones en Dynamics 365.  También puede haber otros pasos necesarios para habilitar la integración, según la implementación existente; por lo tanto, se recomienda trabajar estrechamente con el contacto técnico de Adobe.

>[!NOTE]
>
>Debido a la complejidad de las implementaciones de clientes existentes, se recomienda que trabaje con el contacto técnico de Adobe al planificar y configurar la integración.

### Frecuencia de sincronización de datos

La integración utiliza una arquitectura que permite detectar actualizaciones y agregarlas a la &quot;cola&quot; de procesamiento poco después de que se produzcan en Microsoft Dynamics 365 (es decir, flujo continuo, no procesamiento por lotes). Por este motivo, no es necesario especificar las frecuencias de ejecución o programaciones del flujo de datos.

La excepción a esto son los flujos de datos de exclusión bidireccionales y de Campaign a Dynamics 365. Para estas configuraciones de exclusión, los registros de Campaign actualizados se exportan a SFTP a través de un flujo de trabajo de Campaign una vez al día, después de lo cual la herramienta de integración lee el archivo y procesa el registro.

### Acuerdo de uso de datos

Si se encuentra en regiones de EMEA o APAC, algunos de sus datos se procesarán en Estados Unidos como parte de esta integración. Para obtener más información, consulte [esta sección](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Mecanismos de protección y limitaciones

>[!IMPORTANT]
>
>Ciertas acciones por su parte (por ejemplo, ingesta inicial de registros, reproducción de datos de registros, etc.) Esto podría provocar una gran carga de registros ingeridos desde Microsoft Dynamics 365 a la instancia de Adobe Campaign. Para reducir el riesgo de problemas de rendimiento, se recomienda detener todos los procesos de Campaign (por ejemplo, sin actividad de marketing, sin ejecución de flujos de trabajo, etc.) hasta que se incorpora la gran carga de registros en Campaign.

### Entidades personalizadas

La [integración de Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) admite entidades personalizadas, lo que permite que las entidades personalizadas de Dynamics 365 se sincronicen con los recursos personalizados correspondientes en Campaign.

La integración admite tablas vinculadas y no vinculadas.

Al configurar flujos de datos de entidad personalizados, es importante tener en cuenta lo siguiente:

* La creación y modificación de recursos personalizados de Campaign son operaciones sensibles que deben realizar únicamente los usuarios expertos.
* Para los flujos de datos de entidad personalizados, el seguimiento de cambios debe habilitarse en Dynamics 365 para entidades personalizadas sincronizadas.
* Si se crea un registro principal y un registro secundario vinculado casi a la misma hora en Dynamics 365, debido al procesamiento paralelo de la integración, existe una pequeña posibilidad de que se pueda escribir un nuevo registro secundario en Campaign antes de su registro principal.

* Si el elemento principal y el secundario están vinculados en el lado de la campaña mediante la opción **1 de vínculo simple de cardinalidad**, el registro secundario permanecerá oculto e inaccesible (a través de la interfaz de usuario o la API) hasta que el registro principal llegue a Campaign.

* (Suponiendo que la cardinalidad **1 es un vínculo simple** en Campaign). Si el registro secundario se actualiza o elimina en Dynamics 365 y ese cambio se escribe en Campaign antes de que el registro principal aparezca en Campaign (no es probable, pero es una posibilidad remota), esa actualización o eliminación no se procesará en Campaign y se generará un error. En caso de actualización, el registro en cuestión deberá actualizarse de nuevo en Dynamics 365 para sincronizar el registro actualizado. En caso de eliminación, el registro en cuestión deberá tratarse por separado en el lado de la campaña, ya que ya no hay un registro en Dynamics 365 para eliminar o actualizar.

* Si se encuentra con una situación en la que cree que tiene registros secundarios ocultos y no hay forma de acceder a ellos, puede cambiar temporalmente el tipo de vínculo de cardinalidad a **0 o 1 vínculo simple de cardinalidad** para acceder a esos registros.

Se puede encontrar una descripción general más completa de los recursos personalizados de Campaign [en esta sección](../../developing/using/key-steps-to-add-a-resource.md).

### Protecciones de integración

Al planificar el uso de esta integración, deben tenerse en cuenta las siguientes limitaciones. Consulte con su técnico de Adobe si cree que sobrepasa estas barreras.

* Deberá obtener la licencia del paquete de Campaign adecuado para admitir el volumen de llamadas al motor generado por la integración. Si se supera el volumen de llamadas al motor con licencia, podría causar una degradación en el rendimiento de la campaña.

  Utilice lo siguiente para ayudar a calcular el volumen de llamadas al motor desde la integración:

   * Inserciones de registros (es decir, nuevo registro): 1 acceso al motor
   * Eliminación de registros: 1 petición de motor
   * Actualizaciones de registros: 2 llamadas al motor (solo 1 llamada si el registro de destino es idéntico al registro de origen, es decir, si no hay cambios en el registro de campaña)

  Al estimar el volumen total de llamadas al motor de Campaign, es importante tener en cuenta otras fuentes de llamadas al motor, como páginas de aterrizaje, WebApps, JSSP, API, registros de aplicaciones móviles, etc.

  Vea la información del paquete de Adobe Campaign Standard aquí: [https://helpx.adobe.com/es/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/es/legal/product-descriptions/campaign-standard.html)

* La integración admite un máximo de 15 millones de registros totales para la sincronización inicial con los recursos en Campaign. La sincronización incremental está limitada por el paquete de Adobe Campaign Standard.

* La oferta de integración estándar incluye compatibilidad con hasta veinte entidades personalizadas, cada una con un máximo de 50 columnas.

* Deberá crear y publicar los recursos personalizados antes de implementar la integración.

* La profundidad máxima de la tabla al vincular tablas es de dos (es decir, tabla1->tabla2->tabla3)

* La integración admite hasta 5 columnas vinculadas por recurso personalizado. La vinculación de varias columnas entre recursos personalizados puede tener un impacto significativo en el rendimiento. Se prefiere **0 o 1 vínculo simple de cardinalidad** sobre **1 vínculo simple de cardinalidad**.

* La integración admite la transformación entre tipos de datos primitivos de Microsoft Dynamics 365 (booleano, entero, decimal, doble, cadena, fecha y hora, fecha) y tipos de datos de Adobe Campaign Standard (entero, booleano, flotante, doble, fecha, fecha y hora, cadena). Los tipos de datos más avanzados se interpretan como cadenas y se sincronizan tal cual.

* Es posible que sea necesario establecer ventanas de mantenimiento de incorporación entre el Adobe y el cliente.

* Tenga en cuenta que los incrementos significativos o los &quot;picos&quot; en el uso de la integración (por ejemplo, un aumento pronunciado de registros nuevos o actualizados) pueden provocar ralentizaciones en la sincronización de datos.

* Como parte de la integración, se espera que complete los pasos de configuración previos a la integración en Microsoft Azure y Dynamics 365. Ver los pasos de configuración [en esta página](../../integrating/using/d365-acs-configure-d365.md)

* Se espera que lleve sus modelos de datos de Dynamics 365 y Campaign a la integración y los mantenga.

### Límites de integración

La integración se diseñó para resolver el caso de uso general del movimiento de datos común entre Microsoft Dynamics 365 y Campaign, pero no pretende abordar cada caso de uso específico de cada cliente:

* La integración no emite ninguna eliminación de privacidad (por ejemplo, RGPD). La responsabilidad de cumplir las solicitudes de privacidad del usuario final corresponde al cliente; dichas solicitudes deben realizarse tanto en Campaign (a través de Adobe Experience Platform Privacy Service) como en Dynamics 365 de forma independiente. La integración puede realizar eliminaciones regulares para ayudar con la sincronización de datos, si lo desea.   Revise [la sección Privacidad](#manage-privacy-requests) para obtener más información.

* No se sincronizarán datos de perfil o de entidad personalizada de Campaign a Dynamics 365, con la excepción de la información de exclusión (si la ha configurado el cliente).

* La administración de suscripciones de Campaign (es decir, suscripciones/cancelaciones de suscripción) no es compatible de forma nativa.

* No se admite la composición y activación de campañas de correo electrónico de Campaign desde Dynamics 365.

* La integración **no** admite la remodelación de datos entre los modelos de datos de Dynamics 365 y Campaign Standard. Se espera que la integración sincronice una tabla de Dynamics 365 con una tabla de Campaign.
