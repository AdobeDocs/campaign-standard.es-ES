---
title: Administración de audiencias de Adobe Experience Platform
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
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 3%

---


# Administración de audiencias de Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>El Servicio de Destinos de audiencia está actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea obtener acceso, póngase en contacto con el Servicio de atención al cliente de Adobe.

## Acceso a audiencias de Adobe Experience Platform

Para acceder al generador de segmentos de Adobe Experience Platform, vaya a la **[!UICONTROL Audiences]** tarjeta en la página de inicio del Campaign Standard (o al **[!UICONTROL Audiences]** vínculo en el encabezado) y, a continuación, seleccione el **[!UICONTROL Adobe Experience Platform]** entorno.

![](assets/aep_audiences_access.png)

Primero se le dirigirá a la página de lista de segmentos de Adobe Experience Platform, donde se puede acceder a los segmentos de Adobe Experience Platform existentes para editarlos más adelante.

Hay una barra de búsqueda y un filtro disponibles para ayudarle a encontrar el segmento de Adobe Experience Platform deseado.

![](assets/aep_audiences_list.png)

## Creación de audiencias de Adobe Experience Platform

Para crear una audiencia de Adobe Experience Platform directamente en Campaign Standard, siga estos pasos:

1. En la página de lista de segmentos de Adobe Experience Platform, haga clic en el **[!UICONTROL New audience]** botón situado en la esquina derecha.

   ![](assets/aep_audiences_creation_create.png)

1. El Generador de segmentos ahora debe mostrarse en su espacio de trabajo. Le permite crear un segmento usando datos de Adobe Experience Platform que eventualmente se utilizarán para crear su audiencia.

1. Asigne un nombre al segmento en el panel derecho e introduzca una descripción (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Para crear correctamente un segmento, debe seleccionar una directiva **de** combinación que coincida con el propósito de marketing de este segmento.

   En el panel de configuración, se selecciona una directiva de combinación predeterminada de plataforma. Para obtener más información sobre las directivas de combinación, consulte la sección dedicada en la guía del usuario del Generador [de segmentos](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Defina las reglas que identificarán los perfiles que se recuperarán en la audiencia.

   Para ello, arrastre los atributos y/o eventos deseados desde el panel izquierdo al espacio de trabajo, defina las reglas correspondientes y haga clic en el **[!UICONTROL Create segment]** botón para guardar el segmento (consulte [Uso del Generador](../../audiences/using/aep-using-segment-builder.md)de segmentos).

   ![](assets/aep_audiences_creation_query.png)

La audiencia ya está lista para activarse, puede utilizarla como destinatario para sus campañas (consulte [Targeting Adobe Experience Platform audiencias](../../automating/using/aep-targeting-audiences.md)).

## Edición de audiencias

Para editar una audiencia, ábrala y modifique las reglas según sea necesario en la interfaz del Generador de segmentos (consulte [Uso del Generador](../../audiences/using/aep-using-segment-builder.md)de segmentos).

Una vez completados los cambios, haga clic en el **[!UICONTROL Save segment]** botón para actualizar la audiencia.

![](assets/aep_audiences_editing.png)
