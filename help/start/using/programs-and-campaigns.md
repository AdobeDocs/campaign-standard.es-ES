---
title: Programas y campañas
description: En Adobe Campaign, los programas y las campañas le permiten agrupar y orquestar las distintas actividades de marketing vinculadas a ellas. Los informes sobre programas y campañas le permiten analizar su impacto.
page-status-flag: never-activated
uuid: fe2812a8-196f-4aba-a739-fbbfffd754cb
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: marketing-plans
discoiquuid: 21b84028-d1a7-4ad6-891a-862a94565514
context-tags: campaign,overview;campaignExplorer,main
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c26f98c8edd832beeedfedafb8ad27730cc30d25

---


# Programas y campañas{#programs-and-campaigns}

## Acerca de los planes, programas y campañas {#about-plans--programs-and-campaigns}

Adobe Campaign le permite planificar campañas de marketing en las que puede crear y administrar diferentes tipos de actividades: correos electrónicos, mensajes SMS, notificaciones push, flujos de trabajo, páginas de aterrizaje. Estas campañas y su contenido se pueden agrupar en programas.

Los programas y las campañas le permiten reagruparse y ver las diferentes actividades de mercadotecnia que están vinculadas a ellos.

* Un **programa** puede contener otros programas, así como campañas, flujos de trabajo y páginas de aterrizaje. Aparece en la línea de tiempo y le ayuda a organizar sus actividades de marketing: puede separarlos por país, marca, unidad, etc.
* Una **campaña** le permite recopilar todas las actividades de mercadotecnia de su elección en una sola entidad. Una campaña puede contener correos electrónicos, SMS, notificaciones push, correos directos, flujos de trabajo y páginas de aterrizaje.

Para organizar mejor los planes de marketing, Adobe recomienda la siguiente jerarquía: Programa > Subprogramas > Campañas > Flujos de trabajo > Entregas.

Los informes sobre programas y campañas le permiten analizar su impacto. Por ejemplo, puede generar informes a nivel de campaña para agregar datos sobre todos los envíos contenidos en esa campaña.

**Temas relacionados:**

* [Cronología](../../start/using/timeline.md)
* [Acerca de los informes dinámicos](../../reporting/using/about-dynamic-reports.md)

## Creación de un programa {#creating-a-program}

El programa es el primer nivel de organización. Puede contener subprogramas, campañas, flujos de trabajo o páginas de aterrizaje.

1. En la página de inicio de Adobe Campaign, seleccione la **[!UICONTROL Programs & Campaigns]**tarjeta.
1. Click on the **[!UICONTROL Create]**button.
1. En la **[!UICONTROL Creation mode]**pantalla, seleccione un tipo de programa.

   ![](assets/programs_and_campaigns_2.png)

   Los tipos de programa disponibles se basan en plantillas definidas en la sección **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Program templates]**. For more on this, refer to the[Managing templates](../../start/using/marketing-activity-templates.md)section.

1. En la **[!UICONTROL Properties]**pantalla, introduzca el nombre y la ID del programa.

   ![](assets/programs_and_campaigns_3.png)

1. Seleccione una fecha de inicio y de finalización para el programa. Estas fechas sólo se aplican al propio programa.

   Puede crear el programa dentro de un programa principal. Para ello, seleccione el programa principal de los programas existentes.

1. Haga clic en **[!UICONTROL Create]**para confirmar la creación del programa.

Se crea y se muestra el programa. Utilice el **[!UICONTROL Create]**botón para agregar subprogramas, campañas, flujos de trabajo o páginas de aterrizaje.

>[!NOTE]
>
>También puede crear un programa a partir de la lista de actividades de marketing.

## Creación de una campaña {#creating-a-campaign}

En programas y subprogramas, puede agregar campañas. Las campañas pueden contener actividades de marketing como correos electrónicos, SMS, notificaciones push, flujos de trabajo y páginas de aterrizaje.

1. En la página de inicio de Adobe Campaign, seleccione la **[!UICONTROL Programs & Campaigns]**tarjeta y acceda a un programa o subprograma.
1. Haga clic en el **[!UICONTROL Create]**botón y seleccione**[!UICONTROL Campaign]**.
1. En la pantalla, **[!UICONTROL Creation mode]**seleccione un tipo de campaña.

   ![](assets/programs_and_campaigns_7.png)

   Los tipos de campaña disponibles se basan en plantillas definidas en **[!UICONTROL Resources]**>**[!UICONTROL Templates]** > **[!UICONTROL Campaign templates]**. For more on this, refer to the[Managing templates](../../start/using/marketing-activity-templates.md)section.

1. En la **[!UICONTROL Properties]**pantalla, introduzca el nombre y la ID de la campaña.
1. Seleccione una fecha de inicio y de finalización para la campaña. Estas fechas solo se aplican a la propia campaña.

   ![](assets/programs_and_campaigns_8.png)

1. Haga clic en **[!UICONTROL Create]**para confirmar la creación de la campaña.

La campaña se crea y se muestra. Utilice el **[!UICONTROL Create]**botón para agregar actividades de marketing a la campaña.

>[!NOTE]
>
>Según el contrato de licencia, solo puede acceder a algunas de estas actividades.

También puede crear una campaña a partir de la lista de actividades de marketing. Puede elegir vincular la actividad de marketing a un programa o subprograma principal a través de la ventana de propiedades de la campaña.

## Iconos y estados de campañas y programas {#programs-and-campaigns-icons-and-statuses}

Cada programa y cada campaña de la lista tiene un símbolo visual y un icono cuyo color indica el estado de la ejecución. Este estado depende del período de validez del programa o de la campaña.

* Gris: el programa/campaña aún no ha comenzado - **[!UICONTROL Editing]**estado.
* Azul: el programa/campaña está en curso - **[!UICONTROL In progress]**estado.
* Verde: el programa/campaña ha finalizado - **[!UICONTROL Finished]**estado. De forma predeterminada, la fecha actual se muestra automáticamente como la fecha de inicio de validez y la fecha de finalización se calcula según la fecha de inicio (** D+186 días **). Puede cambiar estas fechas en las propiedades del programa o de la campaña.

![](assets/programs_and_campaigns.png)

