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
source-git-commit: 4b0c4fb13cc11c06e2487e531ca96574e49b6beb
workflow-type: tm+mt
source-wordcount: '2507'
ht-degree: 1%

---

# Prácticas recomendadas y limitaciones {#acs-msdyn-best-practices}

## Administración de datos {#acs-msdyn-manage-data}

Para la sincronización de contactos y entidades personalizadas, esta integración trata **Microsoft Dynamics 365 como fuente de verdad**.  Cualquier cambio en los atributos sincronizados debe realizarse en Dynamics 365 y no en Adobe Campaign Standard).  Si los cambios se realizan en Campaign, pueden sobrescribirse en Campaign durante la sincronización, ya que la sincronización se realiza en una dirección.

La integración se puede configurar de forma opcional para emitir llamadas de eliminación de perfiles a Campaign cuando se elimina un contacto en Dynamics 365 para ayudar a mantener la integridad de los datos. Sin embargo, una eliminación de perfil es diferente a una eliminación de privacidad. Una eliminación de privacidad en Campaign eliminará el registro de perfil de Campaign y las entradas de registro asociadas. mientras que una eliminación de perfil normal solo eliminará el registro de perfil de Campaign, dejando remanentes atrás en los registros de Campaign. Si la función de eliminación de perfiles está habilitada en la integración, deberán seguirse pasos adicionales para procesar correctamente las solicitudes de privacidad de los interesados. Consulte los pasos de la sección [Sección Privacidad a continuación](#manage-privacy-requests).

## Privacidad{#acs-msdyn-manage-privacy}

Esta integración está diseñada para transferir datos del usuario final entre Microsoft Dynamics 365 y Adobe Campaign Standard. Estos datos incluyen información personal si está contenida en sus datos de usuario final.  Como responsable del tratamiento de datos, su empresa es responsable de cumplir cualquier legislación y reglamento de privacidad que sea aplicable a su recopilación y uso de datos personales.

Esta integración está diseñada para transferir datos del usuario final (incluida, entre otros, información personal, si está contenida en los datos del usuario final), entre Microsoft Dynamics 365 y Adobe Campaign Standard. Como responsable del tratamiento de datos, su empresa es responsable de cumplir cualquier legislación y reglamento de privacidad que sea aplicable a su recopilación y uso de datos personales.

La integración no emite ninguna privacidad del interesado (p. ej., el RGPD) elimina o gestiona ninguna otra solicitud de privacidad (a excepción de la exclusión). Al procesar las solicitudes de privacidad, debe hacerlo tanto en Microsoft Dynamics 365 como en Campaign (a través de Adobe Experience Platform Privacy Service) de forma independiente.

Si ha configurado la integración para que emita llamadas de eliminación de perfiles normales en Campaign cuando se elimina un contacto en Dynamics 365, se deben seguir los pasos que se indican a continuación. Asegúrese de que no se realicen actualizaciones en el registro en cuestión durante este proceso.

1. Emitir solicitud de eliminación de privacidad a [Adobe Experience Platform Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service)

1. Supervisar la solicitud hasta que se haya completado correctamente

1. El registro de verificación ya no está en la instancia de Campaign

1. (Poco después) Ejecute el problema de eliminación de privacidad en Dynamics 365

1. Comprobar que el registro se ha eliminado de ambos sistemas

A continuación se muestran vínculos para ayudarle a implementar solicitudes de acceso o eliminación relacionadas con la privacidad en cada sistema:

* [Microsoft Dynamics 365](https://docs.microsoft.com/en-us/dynamics365/get-started/gdpr/)

* [Adobe Campaign Standard](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html)

>[!IMPORTANT]
>
>Si cualquier registro de recursos personalizados de Campaign contiene información personal que sea aplicable al uso de Campaign por parte de un cliente, dicho registro debe estar vinculado a un registro de perfil de Campaign correspondiente (directamente o a través de otro recurso personalizado), de modo que una eliminación relacionada con la privacidad en el registro de perfil también pueda eliminar el registro de recursos personalizado vinculado que contenga información personal; las opciones de vinculación y eliminación entre las entidades deben configurarse para permitir esta eliminación en cascada de los registros vinculados. La información personal no debe introducirse en un recurso personalizado que no esté vinculado al perfil.

## Exclusión {#opt-out}

Debido a las diferencias en los atributos de exclusión entre Microsoft Dynamics 365 y Campaign, y a las diferencias en los requisitos comerciales de cada cliente, la asignación de exclusión se ha dejado como un ejercicio para que el cliente lo complete.  Es importante asegurarse de que las exclusiones se asignan correctamente entre sistemas para que las preferencias de exclusión del usuario final se mantengan y no reciban una comunicación a través de un canal del que hayan excluido.

Tenga en cuenta que solo se puede usar lo siguiente en las asignaciones de exclusión:

* Atributos de campaña con el prefijo &quot;Ya no se puede contactar por&quot; (por ejemplo, Ya no se puede contactar por correo electrónico) o

* el atributo específico de la CCPA

Encontrará más información sobre los campos de entidad de perfil [here](../../developing/using/datamodel-profile.md).

En Dynamics 365, la mayoría de los campos de exclusión tienen el prefijo &quot;no válido&quot;; sin embargo, también puede utilizar otros atributos para la exclusión si los tipos de datos son compatibles.

Al aprovisionar la integración, tendrá la oportunidad de especificar qué configuración de exclusión necesita para su negocio:

* **Unidireccional (Microsoft Dynamics 365 to Campaign)**: Dynamics 365 es una fuente de verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde Dynamics 365 al Campaign Standard
* **Unidireccional (Campaign a Microsoft Dynamics 365)**: Campaign Standard es la fuente de verdad para las exclusiones. Los atributos de exclusión se sincronizarán en una dirección desde el Campaign Standard a Dynamics 365
* **Bidireccional**: Dynamics 365 AND Campaign Standard son fuentes de verdad. Los atributos de exclusión se sincronizarán bidireccionalmente entre Campaign Standard y Dynamics 365

Alternativamente, si tiene un proceso independiente para administrar la sincronización de exclusión entre los sistemas, el flujo de datos de exclusión de la integración se puede desactivar.

La configuración de exclusión bidireccional utiliza la lógica para determinar qué valor se debe escribir en ambos sistemas. La lógica compara las marcas de tiempo entre los dos sistemas (cambio de nivel de registro en Dynamics 365, cambio de nivel de atributo en Campaign) para determinar qué sistema prevalece. Si Campaign contiene la marca de tiempo más reciente, prevalecerá el valor Campaña . Si Dynamics 365 contiene la marca de tiempo más reciente o si son iguales, entonces opt-out=TRUE ganará (suponiendo que uno de los valores sea TRUE).

Obtenga información sobre cómo seleccionar las opciones de inclusión/exclusión en [esta sección](../../integrating/using/d365-acs-self-service-app-data-sync.md#opt-in-out-wf).

>[!NOTE]
>
>Revise y, si procede, actualice las reglas de tipología predeterminadas y específicas de Adobe Campaign antes de realizar cambios aquí para asegurarse de que dichos cambios se apliquen correctamente a todas las comunicaciones salientes. Por ejemplo, asegúrese de que cualquier asignación a las preferencias de exclusión refleje con precisión las opciones de intención/comunicación del destinatario y no interrumpa inadvertidamente la entrega de mensajes transaccionales o de relaciones, como confirmaciones de pedidos de clientes.

Si seleccionó la variable **Bidireccional** o **Unidireccional (Campaign a Microsoft Dynamics 365)** configuración de exclusión, los datos de exclusión de Campaign se exportan periódicamente a través del flujo de trabajo al área de almacenamiento SFTP de Campaign (consulte &quot;Uso de SFTP de Campaign a continuación&quot;). En el caso de que los flujos de trabajo de exclusión de la campaña dejen de ejecutarse, deberá reiniciar manualmente lo antes posible para reducir la posibilidad de que se pierdan las sincronizaciones de exclusión.

>[!IMPORTANT]
>
>Si necesita la variable **Bidireccional** o **Unidireccional (Campaign a Microsoft Dynamics 365)** configuración de exclusión, deberá realizar la solicitud al contacto técnico de su Adobe para que los flujos de trabajo de exclusión se configuren en la instancia de Campaign

## Uso de SFTP de Campaign

La integración debe utilizar el almacenamiento SFTP de Campaign en los casos de uso siguientes.  Deberá asegurarse de que su cuenta SFTP tenga la capacidad de almacenamiento adecuada para admitir estos casos de uso. Si se supera la capacidad de almacenamiento SFTP con licencia, el uso funcional de Campaign, la integración o la cuenta SFTP puede verse gravemente afectado.

| Caso de uso | Descripción |
|---|---|
| Bidireccional y unidireccional (Campaign a Microsoft Dynamics 365) | Los flujos de datos de exclusión bidireccional y unidireccional (Campaign a Microsoft Dynamics 365) utilizarán el almacenamiento SFTP de Campaign. Un flujo de trabajo de Campaign exportará cambios incrementales a la carpeta SFTP. A partir de ahí, la integración recogerá los registros y el proceso. |
| Registros de exclusión | Los registros de salida del conector serán útiles para solucionar el problema de la integración. Los registros de salida se pueden activar o desactivar. |


>[!IMPORTANT]
>
>Usted es el responsable de la información a la que accede y descarga desde las carpetas SFTP. Si la información contiene datos personales, usted es responsable de cumplir con las leyes y regulaciones de privacidad aplicables. [Más información](#acs-msdyn-manage-privacy).

## Administración de datos

### Datos de campaña existentes

Esta integración sincroniza contactos y entidades personalizadas de Microsoft Dynamics 365 a Campaign. La integración no modificará los registros de campaña creados fuera de la integración (es decir, no creados por el trabajo de sincronización), incluidos los registros de campaña existentes en el momento de la configuración de la integración.

Debido a que esta integración utiliza la variable **[!UICONTROL externalId]** para sincronizar registros de perfil de Campaign con registros de contacto de Dynamics 365, este campo Campaña (**[!UICONTROL externalId]** ) debe rellenarse con Microsoft Dynamics 365 **[!UICONTROL contactId]** para los registros que desea sincronizar desde Microsoft Dynamics 365.  Las entidades personalizadas también se sincronizan con un ID único de Microsoft Dynamics 365. La entidad personalizada de Campaign debe incluir este atributo de ID como columna de tabla. La columna externalId puede utilizarse para almacenar este valor de atributo, pero no es necesaria para entidades personalizadas de Campaign.

Tenga en cuenta que Microsoft Dynamics 365 sigue siendo la fuente de la verdad y que los datos de perfil de Campaign se pueden sobrescribir a medida que la integración detecta actualizaciones en Dynamics 365.  También puede haber otros pasos necesarios para habilitar la integración, según la implementación existente; por lo tanto, se recomienda que trabaje estrechamente con su contacto técnico de Adobe.

>[!NOTE]
>
>Debido a la complejidad de las implementaciones de clientes existentes, se recomienda que trabaje con el contacto técnico del Adobe al planificar y configurar la integración.

### Frecuencia de sincronización de datos

La integración utiliza una arquitectura que permite detectar y agregar actualizaciones a la &quot;cola&quot; de procesamiento poco después de que se produzcan en Microsoft Dynamics 365 (es decir, flujo continuo, no procesamiento por lotes). Por este motivo, no es necesario especificar las frecuencias o programaciones de ejecución del flujo de datos.

La excepción a esto son los flujos de datos de exclusión bidireccionales y de Campaign a Dynamics 365. Para estas configuraciones de exclusión, los registros de Campaign actualizados se exportan a SFTP a través de un flujo de trabajo de Campaign una vez al día, tras lo cual la herramienta de integración lee el archivo y procesa el registro.

### Acuerdo de uso de datos

Si se encuentra en regiones de EMEA o APAC, algunos de sus datos se procesarán en EE. UU. como parte de esta integración. Para obtener más información, consulte [esta sección](../../reporting/using/about-dynamic-reports.md#dynamic-reporting-usage-agreement).

## Seguridad y limitaciones

>[!IMPORTANT]
>
>Ciertas acciones de su parte (por ejemplo, ingesta inicial de registros, reproducción de datos de registros, etc.) podría provocar la ingesta de una gran cantidad de registros de Microsoft Dynamics 365 a su instancia de Adobe Campaign. Para reducir el riesgo de problemas de rendimiento, se recomienda detener todos los procesos de Campaign (por ejemplo, sin actividad de marketing, sin ejecución de flujos de trabajo, etc.) hasta después de que la gran carga de registros se haya introducido en Campaign.

### Entidades personalizadas

La variable [Integración con Microsoft Dynamics 365-Adobe Campaign Standard](../../integrating/using/d365-acs-get-started.md) admite entidades personalizadas, lo que permite sincronizar entidades personalizadas de Dynamics 365 con los recursos personalizados correspondientes en Campaign.

La integración admite tablas vinculadas y no vinculadas.

Al configurar los flujos de datos de entidad personalizados, es importante tener en cuenta lo siguiente:

* La creación y modificación de los recursos personalizados de Campaign son operaciones confidenciales que solo deben realizar usuarios expertos.
* Para los flujos de datos de entidad personalizados, el seguimiento de cambios debe estar habilitado en Dynamics 365 para las entidades personalizadas sincronizadas.
* Si se crea un registro principal y un registro secundario vinculado casi al mismo tiempo en Dynamics 365, debido al procesamiento paralelo de la integración, existe una pequeña posibilidad de que se pueda escribir un nuevo registro secundario en Campaign antes de su registro principal.

* Si el elemento principal y el secundario están vinculados en el lado de la campaña mediante la variable **1 cardinalidad simple enlace** , el registro secundario permanecerá oculto e inaccesible (a través de la interfaz de usuario o la API) hasta que el registro principal llegue a Campaign.

* (Suponiendo **1 cardinalidad simple enlace** en Campaign) Si el registro secundario se actualiza o elimina en Dynamics 365 y ese cambio se escribe en Campaign antes de que el registro principal se muestre en Campaign (no es probable, pero es una posibilidad remota), esa actualización o eliminación no se procesará en Campaign y se generará un error. En el caso de la actualización, el registro en cuestión deberá actualizarse de nuevo en Dynamics 365 para sincronizar el registro actualizado. En el caso de la eliminación, el registro en cuestión deberá tratarse por separado en Campaign, ya que ya no hay ningún registro en Dynamics 365 para eliminarlo o actualizarlo.

* Si se encuentra en una situación en la que cree que tiene registros secundarios ocultos y no hay forma de acceder a ellos, puede cambiar temporalmente el tipo de vínculo de cardinalidad a **0 o 1 cardinalidad simple enlace** para acceder a esos registros.

Puede encontrar una descripción general más completa de los recursos personalizados de Campaign [en esta sección](../../developing/using/key-steps-to-add-a-resource.md).

### Protecciones de integración

Las siguientes barreras deben tenerse en cuenta al planificar el uso de esta integración. Consulte con su representante técnico de Adobe si cree que supera estas barreras.

* Debe obtener una licencia del paquete de Campaign adecuado para admitir el volumen de llamadas al motor generado por la integración. Si se supera el volumen de llamadas al motor con licencia, puede producirse una degradación en el rendimiento de Campaign.

   Utilice lo siguiente para calcular el volumen de llamada del motor a partir de la integración:

   * Insertar registros (es decir, nuevo registro): 1 llamada al motor
   * El registro elimina: 1 llamada al motor
   * Registrar actualizaciones: 2 llamadas al motor (solo 1 llamada si el registro de destino es idéntico al registro de origen, es decir, si no se modifica el registro de campaña)

   Al calcular el volumen total de llamadas al motor de Campaign, es importante tener en cuenta otras fuentes de llamadas al motor, incluidas las páginas de aterrizaje, las aplicaciones web, JSSP, las API, los registros de aplicaciones móviles, etc.

   Vea la información del paquete de Adobe Campaign Standard aquí: [https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html)

* La integración admite un máximo de 15 millones de registros totales para la sincronización inicial con los recursos en Campaign. La sincronización incremental está limitada por el paquete de Adobe Campaign Standard.

* La oferta de integración estándar incluye compatibilidad con hasta veinte entidades personalizadas, cada una con un tamaño máximo de 50 columnas.

* Debe crear y publicar los recursos personalizados antes de implementar la integración.

* La profundidad máxima de la tabla al vincular tablas es de dos (es decir, tabla1->tabla2->tabla3)

* La integración admite hasta 5 columnas vinculadas por recurso personalizado. Vincular varias columnas entre recursos personalizados puede tener un impacto significativo en el rendimiento. **0 o 1 cardinalidad simple enlace** es preferible sobre **1 cardinalidad simple enlace**.

* La integración admite la transformación entre tipos de datos primitivos de Microsoft Dynamics 365 (booleano, entero, decimal, doble, cadena, fecha y fecha) y tipos de datos de Adobe Campaign Standard (entero, booleano, flotante, doble, fecha, fecha, fecha, hora, cadena). Los tipos de datos más avanzados se interpretan como cadenas y se sincronizan tal cual.

* Es posible que sea necesario establecer ventanas de mantenimiento de carga entre el Adobe y el cliente.

* Tenga en cuenta que los incrementos significativos o los &quot;picos&quot; en el uso de la integración (por ejemplo, un aumento brusco de los registros nuevos o actualizados) pueden causar ralentización en la sincronización de datos.

* Como parte de la integración, se espera que complete los pasos de configuración previos a la integración en Microsoft Azure y Dynamics 365. Consulte los pasos de configuración [en esta página](../../integrating/using/d365-acs-configure-d365.md)

* Se espera que traiga los modelos de datos de Dynamics 365 y Campaign a la integración y que los mantenga.

### Límites de integración

La integración se ha diseñado para resolver el caso de uso general del movimiento de datos común entre Microsoft Dynamics 365 y Campaign, pero no está pensada para tratar todos los casos de uso específicos de cada cliente:

* La integración no emite ninguna eliminación de privacidad (p. ej., RGPD). La responsabilidad de cumplir las solicitudes de privacidad del usuario final recae en el cliente; estas solicitudes deben realizarse tanto en Campaign (a través de Adobe Experience Platform Privacy Service) como en Dynamics 365 de forma independiente. La integración puede producir eliminaciones regulares para ayudar a sincronizar los datos, si lo desea.   Consulte [la sección Privacidad](#manage-privacy-requests) para obtener más información.

* No se sincronizarán los datos de perfil ni de entidad personalizada de Campaign a Dynamics 365, a excepción de la información de exclusión (si la configura el cliente).

* La administración de suscripciones de Campaign (es decir, suscripciones/cancelaciones de suscripción) no es compatible de forma nativa.

* No se admite la redacción y activación de campañas de correo electrónico de Campaign desde Dynamics 365.

* La integración sí **not** admiten la remodelación de datos entre los modelos de datos de Dynamics 365 y Campaign Standard. Se espera que la integración sincronice una tabla de Dynamics 365 con una tabla de Campaign.
