---
title: Acerca de la importación y exportación de datos
description: Obtenga información sobre las distintas formas de importar y exportar datos con Adobe Campaign.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: 208e8629-c3e2-4f36-bae7-46ffc3f56a1b
TQID: 'https://experienceleague.adobe.com/WP1mlY9lQQu5qWqIx5L89VE6MxnOhxoYewTWAYwfFTI'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 24%
---
# Acerca de la importación y exportación de datos{#about-data-import-and-export}

Según las necesidades de su empresa, tiene varias formas de importar y exportar datos con Adobe Campaign:

* **Paquetes**: los paquetes son archivos XML que permiten exportar e importar configuraciones y conjuntos de datos de una instancia de Adobe Campaign a otra. Las actualizaciones del sistema también se realizan mediante importaciones de paquetes.
* **Listas**: se pueden configurar todas las pantallas de lista y los datos mostrados se pueden exportar en un archivo independiente.
* **Flujos de trabajo**: importe datos de archivos y utilícelos para actualizar la base de datos o enviar correos electrónicos. También puede seleccionar datos para exportar en archivos. Los flujos de trabajo son la mejor manera de automatizar las actualizaciones regulares, como las importaciones de perfiles.

  * La actividad de **[!UICONTROL Load file]** le permite importar datos en un formulario estructurado para utilizarlos en Adobe Campaign. Los datos se importan temporalmente y se necesita otra actividad para integrarlos definitivamente en la base de datos de Adobe Campaign. Para obtener más información sobre cómo usar esta actividad, consulte [esta sección](../../automating/using/load-file.md).
  * La actividad **[!UICONTROL Transfer file]** le permite recibir o enviar archivos, comprobar si hay archivos presentes o archivos de lista en Adobe Campaign. Puede utilizar esta actividad antes de **[!UICONTROL Load file]** en caso de que necesite recuperar el archivo de un origen externo. Para obtener más información sobre cómo usar esta actividad, consulte [esta sección](../../automating/using/transfer-file.md).

Al diseñar procesos de importación, se recomienda utilizar plantillas de flujo de trabajo que se puedan adaptar para adaptarlas a sus necesidades. Para obtener más información sobre cómo configurar una plantilla de flujo de trabajo para importar datos, consulte [este caso de uso](../../automating/using/creating-import-workflow-templates.md).

Adobe Campaign también ofrece una forma simplificada de realizar importaciones regulares que consiste en diseñar **plantillas de importación**. Las plantillas de importación son plantillas de flujo de trabajo especializadas disponibles a través de una pantalla dedicada. Una vez diseñado, el usuario que realiza la importación solo tiene que cargar el archivo para importarlo en una vista simplificada.

**Temas relacionados**:

* [Importación de datos con plantillas de importación](../../automating/using/importing-data-with-import-templates.md)
* [Definición de plantillas de importación](../../automating/using/importing-data-with-import-templates.md#setting-up-import-templates)
* [Administración de paquetes](../../automating/using/managing-packages.md)
