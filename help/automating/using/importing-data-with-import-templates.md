---
title: Importación de datos con plantillas de importación
description: Obtenga información sobre cómo recopilar datos para alimentar la base de datos de Campañas.
page-status-flag: never-activated
uuid: bfc03235-2032-448a-a9ed-21ff2a83fa09
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: fb511bb8-6be7-43f6-86ab-94d5cfa3efc9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 68e825bc3b6b7f94f61875e7da2bc8f63f06d9cb

---


# Importación de datos con plantillas de importación{#importing-data-with-import-templates}

La importación de datos permite recopilar datos para alimentar la base de datos de la Campaña.

Como alternativa a [Flujos de trabajo](../../automating/using/get-started-workflows.md), Adobe Campaign oferta una función de importación simplificada que permite al usuario gestionar determinados tipos de importación definidos por un administrador.

El principio de funcionamiento es el siguiente: un **administrador** define y gestiona plantillas de importación (consulte [Definición de plantillas de importación](../../automating/using/defining-import-templates.md)). Estas plantillas de importación se ponen a disposición de los usuarios con vistas simplificadas en el menú **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Imports]** .

Por lo tanto, estos usuarios sólo tienen que seleccionar el tipo de importación que desean realizar y cargar el archivo con los datos que se van a importar. El flujo de trabajo definido por el administrador se ejecuta de forma transparente para el usuario, que puede acceder a los detalles del resultado de la importación una vez que haya finalizado.

>[!NOTE]
>
>Import data function can be managed by users with **[!UICONTROL GENERIC IMPORT (import)]** and **[!UICONTROL WORKFLOW (workflow)]** roles. Para obtener más información sobre las funciones, consulte [esta sección](../../administration/using/list-of-roles.md).

Las importaciones se pueden filtrar según la plantilla desde la que se ejecutaron, la fecha de ejecución y el estado de ejecución.

1. En la descripción general de importaciones, haga clic en el **[!UICONTROL Create]** botón . Se abre el asistente.
1. Seleccione el tipo de importación que desea realizar. Los tipos de importación corresponden a las plantillas de importación disponibles.
1. Si es necesario, descargue el archivo de muestra vinculado a la plantilla en el equipo para realizar la vista de los tipos de datos esperados en el archivo que se va a importar.
1. Descargue el archivo que contiene los datos que desea importar en el asistente.
1. Inicio la importación. El asistente se cierra y le lleva de nuevo a la lista de las importaciones realizadas con la plantilla utilizada.
1. Actualice la página y seleccione la importación que acaba de realizar para vista de los detalles de ejecución.

   ![](assets/simplified_import1.png)

Ya están disponibles los detalles de la ejecución de la importación. Tanto el archivo que se importó como el archivo que contiene los datos rechazados (datos que no se importaron) pueden descargarse en el equipo.
