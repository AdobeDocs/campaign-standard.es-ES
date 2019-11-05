---
title: Importación de datos con plantillas de importación
description: Obtenga información sobre cómo recopilar datos para alimentar la base de datos de Campaign.
page-status-flag: nunca activado
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automatizar
content-type: referencia
topic-tags: importar y exportar datos
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Importación de datos con plantillas de importación{#importing-data-with-import-templates}

La importación de datos permite recopilar datos para alimentar la base de datos de la campaña.

Como alternativa a [Flujos de trabajo](../../automating/using/discovering-workflows.md), Adobe Campaign ofrece una función de importación simplificada que permite al usuario administrar determinados tipos de importación definidos por un administrador.

El principio operativo es el siguiente: un **administrador** define y administra las plantillas de importación (consulte [Definición de plantillas](../../automating/using/defining-import-templates.md)de importación). Estas plantillas de importación se ponen a disposición de los usuarios con vistas simplificadas en el menú **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Imports]** .

Por lo tanto, estos usuarios sólo tienen que seleccionar el tipo de importación que desean realizar y cargar el archivo con los datos que se van a importar. El flujo de trabajo definido por el administrador se ejecuta de forma transparente para el usuario, que puede acceder a los detalles del resultado de la importación una vez que haya finalizado.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Para obtener más información sobre las funciones, consulte [esta sección](../../administration/using/list-of-roles.md).

Las importaciones se pueden filtrar según la plantilla desde la que se ejecutaron, la fecha de ejecución y el estado de ejecución.

1. En la descripción general de importaciones, haga clic en el **[!UICONTROL Create]** botón . Se abre el asistente.
1. Seleccione el tipo de importación que desea realizar. Los tipos de importación corresponden a las plantillas de importación disponibles.
1. Si es necesario, descargue el archivo de muestra vinculado a la plantilla en el equipo para ver los tipos de datos esperados en el archivo que se va a importar.
1. Descargue el archivo que contiene los datos que desea importar en el asistente.
1. Inicie la importación. El asistente se cierra y vuelve a la lista de importaciones realizadas con la plantilla utilizada.
1. Actualice la página y seleccione la importación que acaba de realizar para ver los detalles de la ejecución.

   ![](assets/simplified_import1.png)

Ya están disponibles los detalles de la ejecución de importación. Tanto el archivo que se importó como el archivo que contiene los datos rechazados (datos que no se importaron) pueden descargarse en el equipo.
