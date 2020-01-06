---
title: Acerca de las plantillas
description: '"Las plantillas de Adobe Campaign le permiten preconfigurar parámetros según sus necesidades: las plantillas pueden contener una configuración completa o parcial de la actividad de marketing para simplificar el uso de Adobe Campaign para usuarios finales no técnicos."'
page-status-flag: never-activated
uuid: 018534b6-61a3-433e-bb60-49883c8b9386
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: managing-templates
discoiquuid: 95218ebe-5430-42a2-b900-1dadbbc92d99
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: cb5cc55c431cbe6050699a35ef2fff270f869dee

---


# Plantillas de actividades de marketing {#marketing-activity-templates}

## Acerca de las plantillas {#about-templates}

Cuando se crea una nueva actividad de marketing, la primera pantalla del asistente le pide que seleccione un tipo o una plantilla. Las plantillas le permiten preconfigurar ciertos parámetros según sus necesidades. La plantilla puede contener una configuración completa o parcial de la actividad de marketing. La administración de plantillas la realiza el administrador funcional.

El usuario final tiene una interfaz simplificada. Al crear una nueva actividad de marketing, solo tiene que seleccionar la plantilla que desee utilizar. No hay necesidad de preocuparse por ninguna configuración técnica. El administrador funcional de la plantilla ya lo ha preconfigurado.

Por ejemplo, en el caso de una plantilla de correo electrónico, puede rellenar previamente el contenido HTML, la audiencia y cualquier otro parámetro de la entrega: programación, perfiles de prueba, propiedades generales de la entrega, parámetros avanzados, etc. Esto le permite ahorrar tiempo al crear una nueva actividad.

![](assets/template_1.png)

Para cada tipo de actividad de marketing, hay una o varias plantillas listas para usar disponibles con una configuración mínima. Estas plantillas listas para usar no se pueden modificar ni eliminar.

Las plantillas están disponibles para las siguientes actividades de marketing:

* Programas
* Campañas
* Envíos por correo electrónico
* Entregas de SMS
* Notificaciones push
* Páginas de aterrizaje
* Flujos de trabajo
* Servicios
* Importar
* Mensajes transaccionales

## Creación de una nueva plantilla {#creating-a-new-template}

Las plantillas de mensaje pueden ser administradas por el administrador funcional de la plataforma, en el **[!UICONTROL Resources > Templates]**menú. Las plantillas listas para usar no se pueden modificar ni eliminar. Para crear una nueva plantilla, debe duplicar una existente.

1. Seleccione una plantilla existente. En nuestro ejemplo, hemos elegido un **[!UICONTROL Delivery template]**.

   ![](assets/template_2.png)

1. Pase el ratón sobre ella y, a continuación, seleccione la **[!UICONTROL Duplicate element]**opción.

   ![](assets/template_3.png)

1. Configure las opciones que desee, como lo haría al [crear una nueva actividad](../../start/using/marketing-activities.md#creating-a-marketing-activity) de marketing desde cero.

   ![](assets/template_4.png)

Las plantillas creadas pueden ser seleccionadas por el usuario estándar en la primera pantalla del asistente mientras se crea una actividad de marketing.

## Uso de una plantilla {#using-a-template}

Ahora veremos cómo utilizar una plantilla creada en la sección anterior.

>[!NOTE]
>
>La creación de una actividad de marketing basada en una plantilla generalmente se realiza mediante un perfil de tipo de usuario estándar.

1. Cree una nueva actividad de marketing.

   ![](assets/template_5.png)

1. En la primera pantalla del asistente, seleccione la plantilla que desee utilizar.

   ![](assets/template_6.png)

   La actividad de marketing está preconfigurada con los parámetros definidos en la plantilla.

   ![](assets/template_7.png)
