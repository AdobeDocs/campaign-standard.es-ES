---
title: Uso compartido de audiencias con Audience Manager o el servicio principal People
description: Descubra cómo importar o exportar su audiencia en las distintas soluciones de Adobe Experience Cloud.
page-status-flag: nunca activado
uuid: a3701e72-5846-4241-afee-d713b499a27a
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrar
content-type: referencia
topic-tags: servicio de trabajo con campaña y audiencia-administrador-o-personas-núcleo
discoiquuid: 77af0772-52b5-46bc-a964-675b45965524
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Uso compartido de audiencias con Audience Manager o el servicio principal People{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importación de una audiencia {#importing-an-audience}

La integración del servicio principal Personas permite importar directamente una audiencia a Adobe Campaign mediante un flujo de trabajo técnico para enriquecer la base de datos. For more information on audience sharing in People core service, refer to this [documentation](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

La importación de audiencias/segmentos desde el servicio principal Personas en Adobe Campaign solo puede realizarse desde el **[!UICONTROL Audiences]** menú por usuarios conectados mediante IMS (autenticación mediante Adobe ID).

1. Vaya al **[!UICONTROL Audiences]** menú.
1. En la barra de acciones, seleccione **[!UICONTROL Create]** para ir a la pantalla y crear una audiencia.
1. Especifique la etiqueta de la nueva audiencia.
1. Configure la audiencia **[!UICONTROL Type]** para **[!UICONTROL Experience Cloud]** que indique que la audiencia que se está creando es una audiencia importada desde el servicio principal Personas.
1. En el **[!UICONTROL Name of the shared audience]** campo, seleccione la audiencia que desea importar. Solo se pueden importar segmentos. No se admiten datos granulares, lo que incluye pares de valor clave, características y reglas.

   ![](assets/aam_import_audience.png)

1. Seleccione el **[!UICONTROL Shared Data Source]**.

   Si la fuente de datos seleccionada está configurada para utilizar un algoritmo de codificación, una opción adicional le ofrece la posibilidad de **[!UICONTROL Force reconciliation with a profile]**. Seleccione esta opción si el **[!UICONTROL Channel]** campo del origen de datos está establecido en Correo electrónico o Móvil (SMS) y si desea aprovechar los datos de perfil.

   Si no selecciona el **[!UICONTROL Force reconciliation with a profile]** y **[!UICONTROL Channel]** está configurado en la fuente de datos AMC en Correo electrónico o Móvil (SMS), todos los ID declarados cifrados se descifran. Se crea o actualiza una audiencia de tipo **Archivo** con una lista de todas las direcciones de correo electrónico y los números de teléfono móvil. De este modo, no se pierde ninguna dirección de correo electrónico ni número de teléfono móvil al importar una audiencia compartida a través de esta integración, aunque ese perfil no exista en Campaign. Tenga en cuenta que este tipo de audiencias no se puede usar directamente, ya que es necesario reconciliarlas manualmente mediante flujos de trabajo.

1. Confirme la creación de la audiencia.

   A continuación, la audiencia se importa mediante un flujo de trabajo técnico. Se compone de registros en los que el ID ('ID del visitante' o 'ID declarado') se pudo conciliar con la dimensión de perfil. Las ID de los segmentos del servicio principal Personas que no reconozca Adobe Campaign no se importan.

La audiencia se importa ahora en la base de datos de Adobe Campaign. El proceso de importación tarda en sincronizarse de 24 a 36 horas cuando los segmentos se importan directamente desde el servicio principal Personas o Audience Manager. Después de este periodo, puede encontrar y utilizar la nueva audiencia en Adobe Campaign.

>[!NOTE]
>
>Si va a importar audiencias de Adobe Analytics a Adobe Campaign, estas audiencias deben compartirse primero en el servicio principal Personas o en Audience Manager. Este proceso tarda de 12 a 24 horas, que se deben añadir a la sincronización de 24 a 36 horas con Campaign. En ese caso específico, el tiempo que tarda en compartirse la audiencia puede alcanzar las 60 horas. Para obtener más información sobre el uso compartido de las audiencias de Adobe Analytics en el servicio principal Personas y Audience Manager, consulte esta [documentación](https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html).

## Exportación de un público {#exporting-an-audience}

Una audiencia se puede exportar desde Adobe Campaign a Audience Manager o al servicio principal Personas mediante un flujo de trabajo y la **[!UICONTROL Save audience]** actividad.

Se puede llevar a cabo en un nuevo flujo de trabajo y solo los usuarios conectados mediante IMS (autenticación mediante Adobe ID).

1. Cree un nuevo flujo de trabajo a partir de un programa, una campaña o la lista de actividades de marketing.
1. Con las diferentes actividades disponibles, establezca como objetivo un conjunto de perfiles.
1. Después de la segmentación, arrastre y suelte una **[!UICONTROL Save audience]** actividad en el flujo de trabajo y, a continuación, ábrala.
1. Select **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Especifique la audiencia mediante el **[!UICONTROL Shared audience]** campo. En la ventana que se abre, puede seleccionar una audiencia existente o crear una nueva:

   * Si selecciona una audiencia existente, solo se añaden los registros nuevos a la audiencia.
   * Para exportar la lista de perfiles a una audiencia nueva, complete el **[!UICONTROL Segment name]** campo y haga clic **[!UICONTROL Create]** antes de seleccionar la audiencia recién creada.
   ![](assets/aam_save_audience_segment_picker.png)

   Para que se puedan conciliar e intercambiar, los registros deben tener un Adobe Experience Cloud ID ('ID del visitante' o 'ID declarado'). Los registros no conciliados se omiten al importar y exportar audiencias.

1. Para finalizar, haga clic en la marca de verificación situada en la parte superior derecha de la pantalla.
1. Seleccione el **[!UICONTROL Shared Data Source]**.
1. Si lo desea, marque la **[!UICONTROL Generate an outbound transition]** casilla para utilizar los perfiles exportados. Solo se exportan los perfiles que se pueden conciliar.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo para exportar la audiencia. La sincronización entre Adobe Campaign y el servicio principal Personas puede tardar varias horas

La sincronización entre Adobe Campaign y el servicio principal Personas tarda de 24 a 36 horas. Después de este periodo, puede encontrar la nueva audiencia en el servicio principal Personas y reutilizarla en otras soluciones de Adobe Experience Cloud. Para obtener más información sobre el uso de una audiencia compartida de Adobe Campaign en el servicio principal Personas de Adobe, consulte la siguiente [documentación](https://marketing.adobe.com/resources/help/en_US/mcloud/t_audience_create.html).

**Temas relacionados:**

* [Flujos de trabajo](../../automating/using/workflow-data-and-processes.md)
* [Audiencias](../../audiences/using/about-audiences.md)

