---
solution: Campaign Standard
product: campaign
title: Prácticas recomendadas de importación
description: Obtenga más información sobre las prácticas recomendadas a seguir al importar datos en la base de datos.
audience: automating
content-type: reference
topic-tags: workflow-general-operation
feature: Flujos de trabajo
role: Arquitecto de datos
translation-type: tm+mt
source-git-commit: 088b49931ee5047fa6b949813ba17654b1e10d60
workflow-type: tm+mt
source-wordcount: '572'
ht-degree: 81%

---


# Prácticas recomendadas de importación {#import-best-practices}

>[!CAUTION]
>
>Tenga en cuenta los límites de almacenamiento SFTP, almacenamiento de bases de datos y perfil activo según el contrato de Adobe Campaign mientras utiliza esta funcionalidad.

Tenga cuidado y siga las sencillas reglas detalladas debajo, ya que le pueden ayudar a garantizar la coherencia de los datos en la base de datos y a evitar errores comunes durante la actualización o las exportaciones de datos.

## Uso de plantillas de importación {#using-import-templates}

La mayoría de los flujos de trabajo de importación deben contener las siguientes actividades: **[!UICONTROL Load file]**, **[!UICONTROL Reconciliation]**, **[!UICONTROL Segmentation]**, **[!UICONTROL Deduplication]**, **[!UICONTROL Update data]**.

El uso de plantillas de importación facilita la preparación de importaciones similares y la coherencia de los datos en la base de datos.

En muchos proyectos, las importaciones se crean sin actividad de **[!UICONTROL Deduplication]** porque los archivos utilizados en el proyecto no tienen duplicados. Los duplicados aparecen en ocasiones al importar archivos diferentes. En este caso, la deduplicación resulta difícil. Por lo tanto, la deduplicación es una buena precaución en todos los flujos de trabajo de importación.

No dé por hecho que los datos entrantes son coherentes y correctos, o que el departamento de TI o el iniciador de Adobe Campaign se pueden encargar de ello. Durante el proyecto, tenga en cuenta la limpieza de los datos. Deduplique, reconcilie y mantenga la coherencia al importar datos.

Un ejemplo de plantilla de flujo de trabajo genérica diseñada para importar datos está disponible en el [Ejemplo: Importar plantilla de flujo de trabajo](../../automating/using/creating-import-workflow-templates.md) .

>[!NOTE]
>
>También puede utilizar [plantillas de importación](../../automating/using/importing-data-with-import-templates.md). Son plantillas de flujo de trabajo definidas por un administrador que, una vez activadas, solo ofrece la posibilidad de especificar el archivo que contiene los datos que se van a importar.

**Temas relacionados:**

* [Cargar actividad de archivo](../../automating/using/load-file.md)
* [Actividad de reconciliación](../../automating/using/reconciliation.md)
* [Actividad de segmentación](../../automating/using/segmentation.md)
* [Actividad de anulación de duplicación](../../automating/using/deduplication.md)
* [Actividad de actualización de datos](../../automating/using/update-data.md)

## Uso de formatos de archivo plano {#using-flat-file-formats}

El formato más eficaz para las importaciones es un archivo plano. Los archivos planos se pueden importar en modo masivo a nivel de base de datos.

Por ejemplo:

* Separador: tabulación o punto y coma
* Primera línea con encabezados
* Sin delimitador de cadenas
* Formato de fecha: AAAA/MM/DD HH:mm:SS

Ejemplo de archivo para importar:

```
lastname;firstname;birthdate;email;crmID
Smith;Hayden;23/05/1989;hayden.smith@example.com;124365
Mars;Daniel;17/11/1987;dannymars@example.com;123545
Smith;Clara;08/02/1989;hayden.smith@example.com;124567
Durance;Allison;15/12/1978;allison.durance@example.com;120987
```

## Uso de compresión {#using-compression}

Utilice archivos comprimidos para importar y exportar cuando sea posible. GZIP es compatible de forma predeterminada. Puede añadir preprocesamiento al importar archivos o posprocesamiento al extraer datos, respectivamente, en las actividades de flujo de trabajo **[!UICONTROL Load file]** y **[!UICONTROL Extract file]**.

**Temas relacionados:**

* [Cargar actividad de archivo](../../automating/using/load-file.md)
* [Actividad Extraer archivo](../../automating/using/extract-file.md)

## Importación en modo Delta {#importing-in-delta-mode}

Las importaciones regulares deben realizarse en modo delta. Esto significa que solo se envían datos modificados o nuevos a Adobe Campaign, en lugar de toda la tabla de una sentada.

Las importaciones completas deben utilizarse únicamente para la carga inicial.

## Mantenimiento de la coherencia {#maintaining-consistency}

Para mantener la coherencia de los datos en la base de datos de Adobe Campaign, siga los principios siguientes:

* Si los datos importados coinciden con una tabla de referencia de Adobe Campaign, se deben reconciliar con esa tabla en el flujo de trabajo. Los registros que no coinciden deben ser rechazados.
* Asegúrese de que los datos importados siempre estén **&quot;normalizados&quot;** (correo electrónico, número de teléfono, dirección de correo postal) y que esta normalización sea fiable y no cambie con los años. Si no es así, es probable que algunos duplicados aparezcan en la base de datos y, como Adobe Campaign no proporciona herramientas para establecer correspondencias &quot;difusas&quot;, resulta muy difícil administrarlos y eliminarlos.
* Los datos de transacciones deben tener una clave de reconciliación y se deben reconciliar con los datos existentes para evitar la creación de duplicados.
* **Importación de archivos relacionados en orden**. Si la importación está compuesta por varios archivos que dependen unos de otros, el flujo de trabajo debe asegurar que los archivos se importen en el orden correcto. Si un archivo falla, los demás archivos no se importan.
* **Deduplique**, reconcilie y mantenga la coherencia al importar datos.
