---
solution: Campaign Standard
product: campaign
title: Acerca de la importación y exportación de datos
description: Obtenga información sobre las distintas formas de importar y exportar datos con Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
role: Data Architect
level: Experienced
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 24%

---


# Acerca de la importación y exportación de datos{#about-data-import-and-export}

Según sus necesidades comerciales, tiene varias formas de importar y exportar datos con Adobe Campaign:

* **Paquetes**: los paquetes son archivos XML que permiten exportar e importar configuraciones y conjuntos de datos de una instancia de Adobe Campaign a otra. Las actualizaciones del sistema también se realizan mediante importaciones de paquetes.
* **Listas**: todas las pantallas de lista se pueden configurar y los datos mostrados se exportan en un archivo independiente.
* **Flujos de trabajo**: importe datos de archivos y utilícelos para actualizar la base de datos o enviar correos electrónicos. También puede seleccionar datos para exportar en archivos. Los flujos de trabajo son la mejor manera de automatizar las actualizaciones regulares, como las importaciones de perfiles.

   * La actividad de **[!UICONTROL Load file]** le permite importar datos en un formulario estructurado para utilizarlos en Adobe Campaign. Los datos se importan temporalmente y se necesita otra actividad para integrarlos definitivamente en la base de datos de Adobe Campaign. Para obtener más información sobre cómo utilizar esta actividad, consulte [esta sección](../../automating/using/load-file.md).
   * La actividad **[!UICONTROL Transfer file]** le permite recibir o enviar archivos, comprobar si hay archivos presentes o archivos de lista en Adobe Campaign. Puede utilizar esta actividad antes de **[!UICONTROL Load file]** en caso de que necesite recuperar el archivo de un origen externo. Para obtener más información sobre cómo utilizar esta actividad, consulte [esta sección](../../automating/using/transfer-file.md).

Al diseñar procesos de importación, se recomienda utilizar plantillas de flujo de trabajo que se adapten a sus necesidades. Para obtener más información sobre cómo configurar una plantilla de flujo de trabajo para importar datos, consulte [este caso de uso](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign también ofrece una forma simplificada de realizar importaciones regulares que consiste en diseñar **plantillas de importación**. Las plantillas de importación son plantillas de flujo de trabajo especializadas disponibles a través de una pantalla dedicada. Una vez diseñada, el usuario que realiza la importación solo debe cargar el archivo para importarlo en una vista simplificada.

**Temas relacionados**:

* [Importación de datos con plantillas de importación](../../automating/using/importing-data-with-import-templates.md)
* [Definición de plantillas de importación](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Administración de paquetes](../../automating/using/managing-packages.md)
