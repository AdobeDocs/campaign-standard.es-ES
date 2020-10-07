---
title: Definición de la asignación
description: Obtenga información sobre cómo asignar un campo Campaign Standard con un campo de modelo de datos de experiencia (XDM).
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 2%

---


# Definición de la asignación {#mapping-definition}

>[!IMPORTANT]
>
>El conector de datos de Adobe Experience Platform se encuentra actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Si desea obtener acceso, póngase en contacto con el Servicio de atención al cliente de Adobe.

En esta sección, descubrirá cómo asignar un campo Campaign Standard con un campo de modelo de datos de experiencia (XDM).

Para realizar esta tarea, los requisitos previos son:

* una definición de Esquema XDM mediante la interfaz o mediante la API REST asociada a XDM
* una creación de conjunto de datos basada en la definición de esquema XDM

1. Vaya a **[!UICONTROL Administration]** > **[!UICONTROL Development]** > **[!UICONTROL Platform]** y elija la **[!UICONTROL Data mappings]** entrada.

1. Haga clic en **[!UICONTROL Create]** para inicio de una nueva asignación XDM.

   ![](assets/aep_createmapping.png)

1. Complete los campos obligatorios y seleccione:

   * una **dimensión de segmentación**: este es el esquema del Campaign Standard para asignar
   * un **conjunto de datos**: este es el paquete de datos asociado a un esquema XDM en Adobe Experience Platform.

>[!NOTE]
>
>Para que un lote se ingrese en Perfil del cliente en tiempo real o servicio de identidad, el conjunto de datos debe estar [habilitado para el Perfil](https://docs.adobe.com/content/help/en/experience-platform/rtcdp/intro/get-started.html)del cliente en tiempo real.
>
>Si el conjunto de datos seleccionado ya se está utilizando en una asignación de datos existente, aparecerá una advertencia para informarle de que los datos se pueden sobrescribir en Adobe Experience Platform. Esto puede suceder cuando hay algunos destinatarios comunes en las asignaciones de datos que usan un mismo conjunto de datos.

La siguiente pantalla presenta la sección en la que se puede crear una nueva asignación para cada campo del esquema de Campaign Standard. **[!UICONTROL Field mappings]**

![](assets/aep_fieldmappings.png)

El **[!UICONTROL Create new field mapping]** botón permite seleccionar el campo Campaign Standard y la expresión de ruta de campo correspondiente en el esquema XDM.

Si no puede encontrar un campo Campaign Standard, puede utilizar el campo de búsqueda para buscar el campo. Actualmente, la búsqueda solo funciona para los campos que están abiertos en la jerarquía.

![](assets/aep_mapfield.png)

Los recursos extendidos definidos en Campaign Standard se asignan como todos los campos nativos. Se definen en la extensión _customer/default en XDM.

![](assets/aep_fieldscusmapping.png)

Puede personalizar la extensión XDM mediante la API y definir su propia extensión, lo que le permitirá un mejor control de la asignación.

Consulte el tutorial [de la API del Registro de](https://docs.adobe.com/content/help/es-ES/experience-platform/xdm/api/getting-started.html) Esquema para obtener más información sobre la API de XDM.

Para asignar un campo de lista desglosada, debe utilizar el editor de expresiones para definir cada valor de lista desglosada correspondiente al valor XDM. Por ejemplo, postalAdressfield debe definirse como:

![](assets/aep_enummapping.png)

Si el valor XDM está definido como una lista desglosada en el Esquema XDM, puede utilizar la función EXDM nativa que reemplazará automáticamente la sintaxis **lif** .

![](assets/aep_enummappingexdm.png)

Para editar una asignación XDM, ábrala, modifique la información deseada y guárdela.

![](assets/aep_editmapping.png)

>[!IMPORTANT]
>
>Por ahora, si edita un valor en la sección y luego hace clic fuera del campo, el cambio no se muestra en la interfaz hasta que hace clic en el **[!UICONTROL Field mappings]** **[!UICONTROL Save]** botón. Este comportamiento se produce una sola vez, cuando la edición de **[!UICONTROL Field Mappings]** es la primera edición de la página.
