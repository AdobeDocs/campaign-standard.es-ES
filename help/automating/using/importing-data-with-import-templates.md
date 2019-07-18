---
title: Importación de datos con plantillas de importación
seo-title: Importación de datos con plantillas de importación
description: Importación de datos con plantillas de importación
seo-description: Descubra cómo recopilar datos para la fuente de su base de datos de campaña.
page-status-flag: no activado nunca
uuid: bfc 03235-2032-448 a-a 9 ed -21 ff 2 a 83 fa 09
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: importar y exportar datos
discoiquuid: fb 511 bb 8-6 be 7-43 f 6-86 ab -94 d 5 cfa 3 efc 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Importing data with import templates{#importing-data-with-import-templates}

La importación de datos permite recopilar datos para generar la base de datos de su campaña.

Alternatively to [Workflows](../../automating/using/discovering-workflows.md), Adobe Campaign offers a simplified import function that allows the user to manage certain types of import that were defined by an administrator.

The operating principle is as follows: an **administrator** defines and manages import templates (see [Defining import templates](../../automating/using/defining-import-templates.md)). These import templates are then made available to users with simplified views under the **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** menu.

Por lo tanto, estos usuarios sólo tienen que seleccionar el tipo de importación que desean realizar y cargar el archivo con los datos que se van a importar. El flujo de trabajo definido por el administrador se ejecuta de forma transparente para el usuario, que puede acceder a los detalles del resultado de la importación una vez que haya terminado.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Para obtener más información sobre las funciones, consulte [esta sección](../../administration/using/list-of-roles.md).

Las importaciones se pueden filtrar según la plantilla desde la que se ejecutaron, la fecha de ejecución y el estado de ejecución.

1. From the imports overview, click the **[!UICONTROL Create]** button. Se abre el asistente.
1. Seleccione el tipo de importación que desee realizar. Los tipos de importación corresponden a las plantillas de importación disponibles.
1. Si es necesario, descargue el archivo de ejemplo vinculado a la plantilla a su equipo para ver los tipos de datos esperados en el archivo que se va a importar.
1. Descargue el archivo que contiene los datos que se van a importar en el asistente.
1. Inicie la importación. El asistente se cierra y regresa a la lista de importaciones realizadas con la plantilla utilizada.
1. Actualice la página y seleccione la importación que acaba de llevar a cabo para ver los detalles de ejecución.

   ![](assets/simplified_import1.png)

Ahora están disponibles los detalles de la ejecución de importación. Tanto el archivo que se importó como el archivo que contiene los datos rechazados (datos que no se importaron) pueden descargarse en el equipo.
