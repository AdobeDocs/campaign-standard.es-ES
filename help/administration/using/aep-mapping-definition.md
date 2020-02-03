---
title: Definición de asignación
description: Obtenga información sobre cómo asignar un campo de Campaign Standard con un campo de modelo de datos de experiencia (XDM).
page-status-flag: never-activated
uuid: 867b1c4b-4c79-4c52-9d0a-ef71993e50a2
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: administration
content-type: reference
topic-tags: configuring-channels
discoiquuid: 406c955a-b2d2-4099-9918-95f5fa966067
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 74e2e1e6cc9c045203f4cfbe37cab673b6761b89

---


# Definición de asignación {#mapping-definition}

>[!IMPORTANT]
>
>El servicio de datos de Campaign Standard está actualmente en fase beta, que puede estar sujeto a actualizaciones frecuentes sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

En esta sección, descubrirá cómo asignar un campo de Campaign Standard con un campo de modelo de datos de experiencia (XDM).

>[!NOTE]
>
>Para realizar esta tarea, los requisitos previos son:
>
> * una definición de esquema XDM mediante la interfaz o mediante la API REST asociada a XDM
> * una creación de conjunto de datos basada en la definición de esquema XDM


1. Vaya a **[!UICONTROL Administration]**>**[!UICONTROL Development]** > **[!UICONTROL Platform]**y elija la**[!UICONTROL Data mappings]** entrada.

1. Haga clic en **[!UICONTROL Create]**para iniciar una nueva asignación de XDM.

   ![](assets/aep_createmapping.png)

1. Complete los campos obligatorios y seleccione:

   * una dimensión **de** objetivo: es el esquema de Campaign Standard que se va a asignar
   * un **conjunto de datos**: es el paquete de datos asociado a un esquema XDM en Adobe Experience Platform.

>[!NOTE]
>
>Para que un lote se ingrese en Perfil del cliente en tiempo real o Servicio de identidad, el conjunto de datos debe estar [habilitado para Perfil](https://www.adobe.io/apis/experienceplatform/home/tutorials/alltutorials.html#!api-specification/markdown/narrative/tutorials/data_ingestion_tutorial/data_ingestion_tutorial.md)del cliente en tiempo real.
>
>Si el conjunto de datos seleccionado ya se está utilizando en una asignación de datos existente, aparecerá una advertencia para informarle de que los datos pueden sobrescribirse en Adobe Experience Platform. Esto puede suceder cuando hay algunos destinatarios comunes en las asignaciones de datos que usan un mismo conjunto de datos.

La siguiente pantalla presenta la sección en la que se puede crear una nueva asignación para cada campo en el esquema de Campaign Standard. **[!UICONTROL Field mappings]**

![](assets/aep_fieldmappings.png)

El **[!UICONTROL Create new field mapping]**botón permite seleccionar el campo Estándar de campaña y la expresión de ruta de campo correspondiente en el esquema XDM.

Si no puede encontrar un campo de Campaign Standard, puede utilizar el campo de búsqueda para buscar el campo. Actualmente, la búsqueda solo funciona para los campos que están abiertos en la jerarquía.

![](assets/aep_mapfield.png)

Los recursos extendidos definidos en Campaign Standard están asignados a todos los campos nativos. Se definen en la extensión _customer/default en XDM.

![](assets/aep_fieldscusmapping.png)

Puede personalizar la extensión XDM mediante la API y definir su propia extensión, lo que le permitirá un mejor control de la asignación.

Consulte el tutorial [de API de registro de](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/tutorials/schema_registry_api_tutorial/schema_registry_api_tutorial.md) esquemas para obtener más información sobre la API de XDM.

Para asignar un campo de enumeración, debe utilizar el editor de expresiones para definir cada valor de enumeración correspondiente al valor XDM. Por ejemplo, postalAdressfield debe definirse como:

![](assets/aep_enummapping.png)

Si el valor XDM se define como una enumeración en el esquema XDM, puede utilizar la función EXDM nativa que reemplazará automáticamente la sintaxis **lif** .

![](assets/aep_enummappingexdm.png)

Para editar una asignación XDM, ábrala, modifique la información deseada y guárdela.

>[!IMPORTANT]
>
>Por ahora, si edita un valor en la sección y luego hace clic fuera del campo, el cambio no se muestra en la interfaz hasta que hace clic en el **[!UICONTROL Field mappings]****[!UICONTROL Save]** botón. Este comportamiento se produce una sola vez, cuando la edición de **[!UICONTROL Field Mappings]**es la primera edición de la página.

![](assets/aep_editmapping.png)
