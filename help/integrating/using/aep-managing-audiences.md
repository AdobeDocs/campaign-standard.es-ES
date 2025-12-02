---
title: Administración de públicos de Adobe Experience Platform
description: Obtenga información sobre cómo administrar Adobe Experience Platform en Campaign Standard.
audience: audiences
content-type: reference
topic-tags: managing-audiences
context-tags: audience,wizard;audience,overview;delivery,audience,back
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 2f6c5cc6-0634-4418-a2ee-e1c133d9cbd2
hide: true
hidefromtoc: true
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 2%

---

# Administración de públicos de Adobe Experience Platform {#about-audiences}

>[!IMPORTANT]
>
>El servicio Audience Destinations se encuentra actualmente en fase beta, por lo que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Los clientes deben estar alojados en Azure (actualmente en fase beta solo para Norteamérica) para acceder a estas funciones. Si desea acceder, póngase en contacto con el Servicio de atención al cliente de Adobe.

## Acceso a las audiencias de Adobe Experience Platform

Para acceder al generador de segmentos de Adobe Experience Platform, vaya a la tarjeta **[!UICONTROL Audiences]** en la página de inicio de Campaign Standard (o al vínculo **[!UICONTROL Audiences]** en el encabezado) y, a continuación, seleccione el entorno **[!UICONTROL Adobe Experience Platform]**.

![](assets/aep_audiences_access.png)

Primero se le dirigirá a la página de lista de segmentos de Adobe Experience Platform, donde se puede acceder a los segmentos de Adobe Experience Platform ya existentes para editarlos más.

Hay disponibles una barra de búsqueda y un filtro para ayudarle a encontrar el segmento de Adobe Experience Platform deseado.

![](assets/aep_audiences_list.png)

## Creación de audiencias de Adobe Experience Platform

Para crear una audiencia de Adobe Experience Platform directamente en Campaign Standard, siga estos pasos:

1. En la página de lista de segmentos de Adobe Experience Platform, haga clic en el botón **[!UICONTROL New audience]** ubicado en la esquina derecha.

   ![](assets/aep_audiences_creation_create.png)

1. El Generador de segmentos debe mostrarse en el espacio de trabajo. Le permite crear un segmento utilizando datos de Adobe Experience Platform que finalmente se utilizarán para crear su audiencia.

1. Asigne un nombre al segmento en el panel derecho e introduzca una descripción (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Para crear correctamente un segmento, debe seleccionar una **política de combinación** que coincida con el propósito de marketing para este segmento.

   En el panel de configuración, se selecciona una política de combinación predeterminada de Platform. Para obtener más información sobre las políticas de combinación, consulte la sección dedicada de la [guía del usuario del Generador de segmentos](https://experienceleague.adobe.com/docs/experience-platform/segmentation/ui/overview.html).

   ![](assets/aep_audiences_mergepolicy.png)

1. Defina las reglas que identificarán los perfiles que se recuperarán en la audiencia.

   Para ello, arrastre los atributos o eventos deseados del panel izquierdo al espacio de trabajo, defina las reglas correspondientes y haga clic en el botón **[!UICONTROL Create segment]** para guardar el segmento (consulte [Uso del Generador de segmentos](../../integrating/using/aep-using-segment-builder.md)).

   ![](assets/aep_audiences_creation_query.png)

La audiencia ya está lista para activarse. Puede usarla como objetivo para sus campañas (consulte [Segmentación de audiencias de Adobe Experience Platform](../../integrating/using/aep-targeting-audiences.md)).

## Edición de audiencias

Para editar una audiencia, ábrala y modifique las reglas según sea necesario en la interfaz del Generador de segmentos (consulte [Uso del Generador de segmentos](../../integrating/using/aep-using-segment-builder.md)).

Una vez completados los cambios, haga clic en el botón **[!UICONTROL Save segment]** para actualizar la audiencia.

![](assets/aep_audiences_editing.png)
