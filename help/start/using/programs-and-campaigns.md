---
title: Programas y campañas
seo-title: Programas y campañas
description: Programas y campañas
seo-description: En Adobe Campaign, los programas y las campañas le permiten agrupar y orquestar las distintas actividades de marketing vinculadas a ellas. Los informes sobre programas y campañas permiten analizar su impacto.
page-status-flag: no activado nunca
uuid: fe 2812 a 8-196 f -4 aba-a 739-fbbfffd 754 cb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: planes de mercadotecnia
discoiquuid: 21 b 84028-d 1 a 7-4 ad 6-891 a -862 a 94565514
context-tags: campaign, overview; Campaignexplorer, main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb6396228e42f99f7e184a82e6c894b09a164cd9

---


# Programs and campaigns{#programs-and-campaigns}

## About plans, programs and campaigns {#about-plans--programs-and-campaigns}

Adobe Campaign le permite planificar campañas de marketing en las que puede crear y administrar distintos tipos de actividades: correos electrónicos, mensajes SMS, notificaciones push, flujos de trabajo, páginas de aterrizaje. Estas campañas y su contenido se pueden agrupar en programas.

Los programas y las campañas permiten agrupar y ver las distintas actividades de marketing vinculadas a ellos.

* A **program** may contain other programs as well as campaigns, workflows, and landing pages. Aparece en la cronología y le ayuda a organizar sus actividades de mercadotecnia: puede separarlas por país, por marca, por unidad, etc.
* A **campaign** enables you to gather all the marketing activities of your choice under a single entity. Una campaña puede contener correos electrónicos, SMS, notificaciones push, mensajes directos, flujos de trabajo y páginas de aterrizaje.

Para organizar mejor los planes de mercadotecnia, Adobe recomienda la siguiente jerarquía: Programa &gt; Subprogramas &gt; Campañas &gt; Flujos de trabajo &gt; Entregas.

Los informes sobre programas y campañas permiten analizar su impacto. Por ejemplo, puede generar informes en el nivel de campaña para agregar datos sobre todos los envíos contenidos en esa campaña.

**Temas relacionados:**

* [Línea de tiempo](../../start/using/timeline.md)
* [Acerca de los informes dinámicos](../../reporting/using/about-dynamic-reports.md)

## Creating a program {#creating-a-program}

El programa es el primer nivel de organización. Puede contener subprogramas, campañas, flujos de trabajo o páginas de aterrizaje.

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card.
1. Click on the **[!UICONTROL Create]** button.
1. In the **[!UICONTROL Creation mode]** screen, select a program type.

   ![](assets/programs_and_campaigns_2.png)

   The program types available are based on templates defined in the **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Program templates]** section. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the program.

   ![](assets/programs_and_campaigns_3.png)

1. Seleccione una fecha de inicio y de finalización en el programa. Estas fechas solo se aplican al programa mismo.

   Puede crear su programa dentro de un programa principal. Para ello, seleccione el programa principal de los programas existentes.

1. Click on **[!UICONTROL Create]** to confirm the creation of the program.

El programa se crea y se muestra. Use the **[!UICONTROL Create]** button to add sub-programs, campaigns, workflows or landing pages.

>[!NOTE]
>
>También puede crear un programa a partir de la lista de actividades de marketing.

## Creating a campaign {#creating-a-campaign}

En programas y subprogramas, puede agregar campañas. Las campañas pueden contener actividades de marketing como correos electrónicos, SMS, notificaciones push, flujos de trabajo y páginas de aterrizaje.

1. From the Adobe Campaign home page, select the **[!UICONTROL Programs & Campaigns]** card and access a program or sub-program.
1. Click on the **[!UICONTROL Create]** button and select **[!UICONTROL Campaign]**.
1. In the **[!UICONTROL Creation mode]** screen, select a campaign type.

   ![](assets/programs_and_campaigns_7.png)

   The campaign types available are based on templates defined in **[!UICONTROL Resources]** &gt; **[!UICONTROL Templates]** &gt; **[!UICONTROL Campaign templates]**. For more on this, refer to the [Managing templates](../../start/using/about-templates.md) section.

1. In the **[!UICONTROL Properties]** screen, enter the name and ID of the campaign.
1. Seleccione una fecha de inicio y de finalización en la campaña. Estas fechas solo se aplican a la propia campaña.

   ![](assets/programs_and_campaigns_8.png)

1. Click on **[!UICONTROL Create]** to confirm the creation of the campaign.

La campaña se crea y se muestra. Use the **[!UICONTROL Create]** button to add marketing activities to your campaign.

>[!NOTE]
>
>Según el contrato de licencia, puede acceder solo a algunas de estas actividades.

También puede crear una campaña desde la lista de actividades de marketing. Puede elegir vincular la actividad de mercadotecnia a un programa o subprograma principal a través de la ventana de propiedades de la campaña.

## Programs and campaigns icons and statuses {#programs-and-campaigns-icons-and-statuses}

Cada programa y cada campaña de la lista tiene un símbolo visual y un icono cuyo color indica el estado de ejecución. Este estado depende del período de validez del programa o de la campaña.

* Gray: the program/campaign has not yet started - **[!UICONTROL Editing]** status.
* Blue: the program/campaign is in progress - **[!UICONTROL In progress]** status.
* Green: the program/campaign has finished - **[!UICONTROL Finished]** status. By default, the current date is automatically shown as the validity start date and the end date is calculated according to the start date (**D+186 days**). Estas fechas se pueden cambiar en las propiedades de programa o de campaña.

![](assets/programs_and_campaigns.png)

