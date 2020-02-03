---
title: Uso del Generador de segmentos unificado
description: Aprenda a utilizar el Generador de segmentos unificado para crear audiencias.
page-status-flag: never-activated
uuid: b3996642-96ec-489e-b146-c8c2cb52aa32
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: audiences
content-type: reference
topic-tags: managing-audiences
discoiquuid: 750ecd8d-67a5-4180-bfec-2a8e3098c812
context-tags: audience,wizard;audience,overview;delivery,audience,back
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: e9d4239182a7ebdec61e85fece6ec49dca8f665a

---


# Uso del Generador de segmentos unificado {#using-the-unified-segment-builder}

>[!IMPORTANT]
>
>El servicio Destinos de audiencia está actualmente en fase beta, que puede estar sujeto a frecuentes actualizaciones sin previo aviso. Se requiere que los clientes estén alojados en Azure (actualmente en versión beta solo para Norteamérica) para acceder a estas capacidades. Póngase en contacto con el Servicio de atención al cliente de Adobe si desea obtener acceso.

El Generador de segmentos unificado permite crear audiencias definiendo reglas basadas en datos procedentes del servicio [de perfil](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation.html)unificado.

Esta sección presenta conceptos globales al crear un segmento. Para obtener información detallada sobre el propio Generador de segmentos unificado, consulte la guía [de usuario del Generador de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segmentos.

La interfaz del Generador de segmentos unificado se compone de la siguiente manera:

* El panel izquierdo proporciona todos los atributos, eventos y audiencias disponibles para generar el segmento arrastrando y soltando los campos deseados en el espacio de trabajo del generador de segmentos.
* El área central proporciona un espacio de trabajo para generar el segmento mediante la definición y combinación de reglas de los campos disponibles.
* El encabezado y el panel derecho muestran las propiedades del segmento (es decir, nombre, descripción y perfiles cualificados estimados para el segmento).

![](assets/aep_audiences_interface.png)

## Creación de un segmento

Para crear un segmento, siga estos pasos:

El Generador de segmentos unificado debería mostrarse ahora en su espacio de trabajo. Le permite crear un segmento con datos de la plataforma Adobe Experience que se utilizarán con el tiempo para crear su audiencia.

1. Asigne un nombre al segmento y, a continuación, introduzca una descripción (opcional).

   ![](assets/aep_audiences_creation_edit_name.png)

1. Asegúrese de que la directiva de combinación deseada está seleccionada en el panel de configuración.

   Para obtener más información sobre las directivas de combinación, consulte la sección dedicada de la guía del usuario del Generador [de segmentos](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)

   ![](assets/aep_audiences_mergepolicy.png)

1. Busque los campos deseados en el panel izquierdo y arrástrelos al área de trabajo central.

   ![](assets/aep_audiences_dragfield.png)

1. Configure las reglas correspondientes a los campos arrastrados.

   ![](assets/aep_audiences_configure_rules.png)

1. Haga clic en el botón **[!UICONTROL Create segment]**.

## Búsqueda de los campos correctos para un segmento

El panel izquierdo muestra todos los atributos, eventos y audiencias disponibles para su uso en la creación de reglas.

Los campos mostrados son atributos capturados por su empresa y se pueden poner a disposición a través del sistema [del Modelo de datos de](https://www.adobe.io/apis/experienceplatform/home/xdm.html)experiencia (XDM).

Los campos están organizados en fichas:

* **[!UICONTROL Attributes]**:: Atributos de perfil existentes que pueden originarse en la base de datos de Adobe Campaign y/o en la plataforma de Adobe Experience. Se refieren a la información estática adjunta a un perfil (por ejemplo, dirección de correo electrónico, país de residencia, estado del programa de lealtad, etc.).

   ![](assets/aep_audiences_attributestab.png)

* **[!UICONTROL Events]**:: Actividades que identifican a los consumidores que han tenido alguna interacción con los puntos de contacto con los clientes de su empresa, como &quot;cualquiera que haya pedido dos veces en dos semanas&quot;. Esto se puede transmitir desde Adobe Analytics o ingerir directamente en Adobe Experience Platform mediante herramientas de ETL de terceros.

   ![](assets/aep_audiences_eventstab.png)

>[!NOTE]
>
>**La segmentación** de varias entidades le permite ampliar los datos de perfil con datos adicionales basados en productos, almacenes u otras clases que no son de perfil. Una vez conectados, los datos de clases adicionales estarán disponibles como si fueran nativos del esquema de perfil.
>
>For more on this, refer to the [dedicated documentation](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/tutorials/segmentation/multi_entity_segmentation.md).

De forma predeterminada, el creador de segmentos unificados muestra los campos de los que están presentes los datos. Para mostrar el esquema completo, incluidos los campos para los que no hay datos, habilite la **[!UICONTROL Show full XDM schema]**opción desde la configuración.

![](assets/aep_audiences_populatedfields.png)

El símbolo al final de cada campo proporciona información adicional sobre el atributo y cómo utilizarlo.

![](assets/aep_audiences_isymbol.png)

## Definición de reglas para un segmento

>[!NOTE]
>
>La sección siguiente proporciona información global sobre la definición de reglas. Para obtener más información sobre esto, consulte la guía [de usuario del Generador de](https://www.adobe.io/apis/experienceplatform/home/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/segmentation/segment-builder-guide.md)segmentos.

Para crear una regla, siga estos pasos:

1. Busque el campo en el panel izquierdo que refleja los atributos o eventos en los que se basará la regla.

1. Arrastre el campo al espacio de trabajo central y configúrelo según la definición de segmento deseada. Para ello, hay disponibles varias funciones de cadena y de fecha y hora.

   En el ejemplo siguiente, la regla se dirigirá a todos los perfiles con sexo igual a &quot;Hombre&quot;.

   ![](assets/aep_audiences_malegender.png)

   La población estimada correspondiente al segmento se vuelve a calcular automáticamente en la **[!UICONTROL Segment Properties]**sección.

1. El **[!UICONTROL View Profiles]**botón le proporciona una vista previa de los 20 primeros registros correspondientes a la regla, lo que le permite validar rápidamente el segmento.

   ![](assets/aep_audiences_samplepreview.png)

   Puede agregar tantas reglas adicionales como desee para dirigirse a los perfiles correctos.

   Al agregar una regla a un contenedor, se agregará a cualquier regla existente con el operador Y. Haga clic en el operador para acceder a la opción y cambiarla a O.

   ![](assets/aep_audiences_andoperator.png)

Una vez vinculadas, las dos reglas forman un contenedor.

## Comparación de campos

El Generador de segmentos unificado permite comparar dos campos para definir una regla. Por ejemplo, las mujeres cuya dirección principal está en un código postal diferente de su dirección de trabajo.

Para ello, siga estos pasos:

1. Arrastre el primer campo que desee comparar (por ejemplo, el código postal de la dirección principal) al área de trabajo central.

   ![](assets/aep_audiences_comparing_1.png)

1. Seleccione el segundo campo (por ejemplo, el código postal de la dirección de trabajo) que se comparará con el primer campo.

   Arrástrelo al espacio de trabajo central, en el mismo contenedor que el primer campo, en el **[!UICONTROL Drop here to compare operands]**cuadro.

   ![](assets/aep_audiences_comparing_2.png)

1. Configure el operador entre los dos campos como desee. En este ejemplo, nuestro segmento requiere que el código postal de la dirección de inicio no sea igual a la dirección de trabajo uno.

   ![](assets/aep_audiences_comparing_3.png)

La regla ahora está configurada y lista para activarse como audiencia.
