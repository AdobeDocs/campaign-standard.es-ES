---
title: Uso compartido de audiencias con Audience Manager o el servicio principal People
description: Obtenga información sobre cómo importar o exportar su audiencia dentro de las distintas soluciones de Adobe Experience Cloud.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: People Core Service Integration
role: Data Architect
level: Intermediate
exl-id: b0d063de-863c-42e7-98dd-c4c86da3281e
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 26%

---

# Uso compartido de audiencias con Audience Manager o el servicio principal People{#sharing-audiences-with-audience-manager-or-people-core-service}

## Importación de una audiencia {#importing-an-audience}

La integración del servicio principal Personas permite importar directamente una audiencia en Adobe Campaign a través de un flujo de trabajo técnico para enriquecer la base de datos. Para obtener más información sobre cómo compartir audiencias en el servicio principal Personas, consulte esta [documentación](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=es).

La importación de audiencias o segmentos desde el servicio principal Personas en Adobe Campaign solo la pueden realizar desde el menú **[!UICONTROL Audiences]** los usuarios conectados mediante IMS (autenticación mediante Adobe ID).

1. Vaya al menú **[!UICONTROL Audiences]**.
1. En la barra de acciones, seleccione **[!UICONTROL Create]** para que se muestre en pantalla y se cree una audiencia.
1. Especifique la etiqueta de la nueva audiencia.
1. Establezca la audiencia **[!UICONTROL Type]** en **[!UICONTROL Experience Cloud]** para indicar que la audiencia que se está creando es una audiencia importada desde el servicio principal Personas.
1. En el campo **[!UICONTROL Name of the shared audience]**, seleccione la audiencia que desea importar. Solo se pueden importar segmentos. No se admiten datos granulares, lo que incluye pares de valor clave, características y reglas.

   ![](assets/aam_import_audience.png)

1. Seleccione el(la) **[!UICONTROL Shared Data Source]** correspondiente.

   Si el origen de datos seleccionado está configurado para utilizar un algoritmo de cifrado, una opción adicional le ofrece la posibilidad de **[!UICONTROL Force reconciliation with a profile]**. Marque esta opción si el campo **[!UICONTROL Channel]** de la fuente de datos está establecido en Correo electrónico o Móvil (SMS) y si desea aprovechar los datos de perfil.

   Si no selecciona **[!UICONTROL Force reconciliation with a profile]** y **[!UICONTROL Channel]** está establecido en la fuente de datos AMC como Correo electrónico o Móvil (SMS), se descifrarán todos los ID declarados cifrados. Se crea/actualiza una audiencia de tipo **Archivo** con una lista de todas las direcciones de correo electrónico/números de teléfono móvil. De este modo, no se pierde ninguna dirección de correo electrónico ni número de teléfono móvil al importar una audiencia compartida a través de esta integración, aunque ese perfil no exista en Campaign. Tenga en cuenta que este tipo de audiencias no se puede utilizar directamente, ya que deben reconciliarse manualmente mediante flujos de trabajo.

1. Confirme para crear la audiencia.

   A continuación, la audiencia se importa mediante un flujo de trabajo técnico. Se compone de registros cuya ID (&quot;ID de visitante&quot; o &quot;ID declarada&quot;) se pudo conciliar con la dimensión del perfil. Las ID de los segmentos del servicio principal Personas que no reconozca Adobe Campaign no se importan.

La audiencia se importará en la base de datos de Adobe Campaign. El proceso de importación tarda en sincronizarse de 24 a 36 horas cuando los segmentos se importan directamente desde el servicio principal Personas o Audience Manager. Después de este periodo, puede encontrar y utilizar la nueva audiencia en Adobe Campaign.

>[!NOTE]
>
>Si se están importando audiencias de Adobe Analytics a Adobe Campaign, dichas audiencias deben compartirse primero en el servicio principal Personas o en un Audience Manager. Este proceso tarda de 12 a 24 horas, que se deben añadir a la sincronización de 24 a 36 horas con Campaign. En ese caso específico, el tiempo que tarda en compartirse la audiencia puede alcanzar las 60 horas. Para obtener más información sobre el uso compartido de las audiencias de Adobe Analytics en el servicio principal Personas y Audience Manager, consulte esta [documentación](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=es).

## Exportación de un público {#exporting-an-audience}

Se puede exportar una audiencia de Adobe Campaign al Audience Manager o al servicio principal Personas mediante un flujo de trabajo y la actividad **[!UICONTROL Save audience]**.

Se puede llevar a cabo en un nuevo flujo de trabajo y solo por usuarios conectados mediante IMS (autenticación mediante Adobe ID).

1. Cree un nuevo flujo de trabajo a partir de un programa, una campaña o la lista de actividades de marketing.
1. Mediante las diferentes actividades disponibles, establezca como objetivo un conjunto de perfiles.
1. Después del objetivo, arrastre y suelte una actividad **[!UICONTROL Save audience]** en el flujo de trabajo y ábrala.
1. Seleccione **[!UICONTROL Share in Adobe Experience Cloud]**.

   ![](assets/aam_save_audience_activity.png)

1. Especifique la audiencia utilizando el campo **[!UICONTROL Shared audience]**. En la ventana que se abre, puede elegir entre seleccionar una audiencia existente o crear una nueva:

   * Si selecciona una audiencia existente, solo se añaden los registros nuevos a la audiencia.
   * Para exportar la lista de perfiles a una audiencia nueva, complete el campo **[!UICONTROL Segment name]** y haga clic en **[!UICONTROL Create]** antes de seleccionar la audiencia recién creada.

   ![](assets/aam_save_audience_segment_picker.png)

   Para poder conciliarlos e intercambiarlos, los registros deben tener un Adobe Experience Cloud ID (&quot;ID de visitante&quot; o &quot;ID declarada&quot;). Los registros no reconciliados se omiten al importar y exportar audiencias.

1. Para finalizar, haga clic en la marca de verificación situada en la parte superior derecha de la pantalla.
1. Seleccione el(la) **[!UICONTROL Shared Data Source]** correspondiente.
1. Si lo desea, marque la casilla **[!UICONTROL Generate an outbound transition]** para utilizar los perfiles exportados. Solo se exportan los perfiles que se pueden reconciliar.
1. Confirme la configuración de la actividad y guarde el flujo de trabajo.
1. Inicie el flujo de trabajo para exportar la audiencia. La sincronización entre Adobe Campaign y el servicio principal Personas puede tardar varias horas

La sincronización entre Adobe Campaign y el servicio principal Personas tarda de 24 a 36 horas. Después de este periodo, puede encontrar la nueva audiencia en el servicio principal Personas y reutilizarla en otras soluciones de Adobe Experience Cloud. Para obtener más información sobre el uso de una audiencia compartida de Adobe Campaign en el servicio principal Personas de Adobe, consulte la siguiente [documentación](https://experienceleague.adobe.com/docs/core-services/interface/audiences/t-audience-create.html?lang=es).

**Temas relacionados:**

* [Flujos de trabajo](../../automating/using/get-started-workflows.md)
* [Públicos](../../audiences/using/about-audiences.md)
