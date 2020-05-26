---
title: Acerca de la importación y exportación de datos
description: Obtenga información sobre las distintas formas de importar y exportar datos con Adobe Campaign.
page-status-flag: never-activated
uuid: f6810364-555c-4b72-8a9c-4ae2fcb2ba63
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
discoiquuid: 31215773-6c0c-48f1-9101-da0ea2a366da
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 0deabe17442b679a340a4497945837b83b4c9207
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 6%

---


# Acerca de la importación y exportación de datos{#about-data-import-and-export}

Según sus necesidades comerciales, tiene varias formas de importar y exportar datos con Adobe Campaign:

* **Paquetes**: los paquetes son archivos XML que permiten exportar e importar configuraciones y conjuntos de datos de una instancia de Adobe Campaign a otra. Las actualizaciones del sistema también se realizan mediante importaciones de paquetes.
* **Listas**: se pueden configurar todas las pantallas de lista y exportar los datos mostrados en un archivo independiente.
* **Flujos de trabajo**: importe datos de los archivos y utilícelos para actualizar la base de datos o enviar correos electrónicos. También puede seleccionar datos para exportar en archivos. Los Flujos de trabajo son la mejor manera de automatizar las actualizaciones regulares, como las importaciones de perfiles.

   * La **[!UICONTROL Load file]** actividad permite importar datos en un formulario estructurado para utilizarlos en Adobe Campaign. Los datos se importan temporalmente y se necesita otra actividad para integrarlos definitivamente en la base de datos de Adobe Campaign. For more on how to use this activity, refer to [this section](../../automating/using/load-file.md).
   * La **[!UICONTROL Transfer file]** actividad le permite recibir o enviar archivos, probar si hay archivos presentes o archivos de lista en Adobe Campaign. Puede utilizar esta actividad antes de una **[!UICONTROL Load file]** en caso de que necesite recuperar el archivo de una fuente externa. For more on how to use this activity, refer to [this section](../../automating/using/transfer-file.md).

Al diseñar procesos de importación, se recomienda utilizar plantillas de flujo de trabajo que puede adaptar a sus necesidades. Para obtener más información sobre cómo configurar una plantilla de flujo de trabajo para importar datos, consulte [este caso](../../automating/using/creating-import-workflow-templates.md)de uso.

El Adobe Campaign también oferta una forma simplificada de realizar importaciones regulares que consiste en diseñar **plantillas de importación**. Las Plantillas de importación son plantillas de flujo de trabajo especializadas disponibles a través de una pantalla dedicada. Una vez diseñado, el usuario que realiza la importación solo tiene que cargar el archivo para importarlo en una vista simplificada.

**Temas relacionados**:

* [Importación de datos con plantillas de importación](../../automating/using/importing-data-with-import-templates.md)
* [Definición de plantillas de importación](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Administración de paquetes](../../automating/using/managing-packages.md)
