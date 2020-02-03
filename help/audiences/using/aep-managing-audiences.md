---
title: Administración de audiencias
description: Obtenga información sobre cómo administrar Adobe Experience Platform en Campaign Standard.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 19b22fa0780a0bf7c4b7a559270d7c8b32d89e38

---


# Administración de audiencias {#about-audiences}

>[!IMPORTANT]
>
>Audience Destinations Service se encuentra actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

## Acceso a audiencias

Para acceder a las audiencias de Adobe Experience Platform, seleccione la **[!UICONTROL Audiences]**tarjeta en la página de inicio de Campaign Standard o el**[!UICONTROL Audiences]** vínculo y, a continuación, seleccione **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Se muestran todas las audiencias creadas en Adobe Experience Platform. Hay una barra de búsqueda y filtros disponibles para ayudarle a encontrar la audiencia deseada.

![](assets/aep_audiences_list.png)

## Creación de audiencias

Las audiencias se crean directamente a partir de la lista de audiencias de Adobe Experience Platform. Para ello, siga estos pasos:

1. Vaya a la lista de audiencias y, a continuación, haga clic en el **[!UICONTROL New audience]**botón .

   ![](assets/aep_audiences_creation_create.png)

1. El Generador de segmentos unificado debería mostrarse ahora en su espacio de trabajo. Le permite crear un segmento con datos de la plataforma Adobe Experience que se utilizarán con el tiempo para crear su audiencia.

1. Asigne un nombre al segmento en el panel derecho e introduzca una descripción (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Para crear correctamente un segmento, debe seleccionar una directiva **de** combinación que coincida con el propósito de marketing de este segmento.

   En el panel de configuración, se selecciona una directiva de combinación predeterminada de plataforma. Para obtener más información sobre las directivas de combinación, consulte la sección dedicada de la guía del usuario del Generador [de segmentos](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)

   ![](assets/aep_audiences_mergepolicy.png)

1. Defina las reglas que identificarán los perfiles que se recuperarán en la audiencia.

   Para ello, arrastre los atributos o eventos deseados desde el panel izquierdo al espacio de trabajo, defina las reglas correspondientes y haga clic en el **[!UICONTROL Create segment]**botón para guardar el segmento (consulte[Uso del Generador](../../audiences/using/aep-using-segment-builder.md)de segmentos unificado).

   ![](assets/aep_audiences_creation_query.png)

La audiencia ya está lista para activarse, puede utilizarla como objetivo para sus campañas (consulte [Segmentación de audiencias](../../automating/using/aep-targeting-audiences.md)de Adobe Experience Platform).

## Edición de audiencias

Para editar una audiencia, ábrala y modifique las reglas según sea necesario en la interfaz del Generador de segmentos unificado (consulte [Uso del Generador](../../audiences/using/aep-using-segment-builder.md)de segmentos unificado).

Una vez completados los cambios, haga clic en el **[!UICONTROL Save segment]**botón para actualizar la audiencia.

![](assets/aep_audiences_editing.png)
