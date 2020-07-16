---
title: Funciones de participación predictiva del usuario
description: Aprenda a utilizar la puntuación de tiempo de envío predictiva y participación.
page-status-flag: never-activated
uuid: c2c13934-9819-4e18-b5c7-60915c907f37
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: ai-powered-emails
discoiquuid: 609355f6-9003-41b9-9981-ea787419fbf5
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: ddf585def583acefbb25e7a48318966cd2af49a7
workflow-type: tm+mt
source-wordcount: '1057'
ht-degree: 0%

---


# Optimización del diseño y el envío con correos electrónicos alimentados por AI{#journey-ai}

## Introducción a los correos electrónicos con tecnología AI{#journey-ai-ovv}

Mediante la Campaña, puede optimizar el diseño y el envío de los viajes de los clientes para predecir las preferencias de participación de cada individuo. Con Journey AI, el Adobe Campaign puede analizar y predecir las tasas abiertas, los tiempos de envío óptimos y la probable reproducción basada en métricas de participación históricas.

**Modelos de aprendizaje automático**

Adobe Campaign Standard oferta dos nuevos modelos de aprendizaje automático: **Optimizaciones** de tiempo de envío predictivas y Puntuación de participación **predictiva**. Estos dos modelos se denominan conjuntamente Journey AI, que es una clase de modelos de aprendizaje automático específicos para diseñar y ofrecer mejores viajes al cliente.

* **Optimización** del tiempo de envío predictiva: La optimización predictiva del tiempo de envío predice cuál es el mejor tiempo de envío para cada perfil de destinatario de aperturas de correo electrónico o clics. Para cada perfil de destinatario, las puntuaciones indican la mejor hora de envío para cada día de semana y qué día de semana es mejor enviar para obtener los mejores resultados.

* **Puntuación** de participación predictiva: La puntuación de participación predictiva predice la probabilidad de que un destinatario se involucre con un mensaje, así como la probabilidad de exclusión (cancelar la suscripción) en los próximos 7 días después del siguiente envío de correo electrónico. Las probabilidades se dividen además en bloques según el riesgo específico de separación, medio o bajo. Además, el modelo también proporciona la clasificación del percentil de riesgo para que los clientes entiendan dónde está la clasificación de un determinado cliente en relación con otros.

>[!CAUTION]
>Esta capacidad no está disponible de forma predeterminada como parte del producto. La implementación requiere la participación de Adobe Consulting. Póngase en contacto con su representante de Adobe para obtener más información.
>
>Por separado, la función requería el uso de un almacenamiento de Azure que el cliente debía proporcionar.

## Optimización del tiempo de envío predictivo{#predictive-send-time}

### Optimice los clics y las aperturas{#about-predictive-send-time}

La optimización predictiva del tiempo de envío predice cuál es el mejor tiempo de envío para cada perfil de destinatario de aperturas de correo electrónico y clics. Para cada perfil de destinatario, las puntuaciones indican la mejor hora de envío para cada día de semana y qué día de semana es mejor enviar para obtener los mejores resultados.

Dentro del modelo de optimización del tiempo de envío predictivo, hay dos submodelos:
* El tiempo de envío predictivo para la apertura es el mejor momento para enviar una comunicación al cliente para maximizar las aperturas
* El tiempo de envío predictivo para clics es la mejor vez que se debe enviar una comunicación al cliente para maximizar los clics

**Entrada** de modelo: Registros de envío, registros de seguimiento y atributos de perfil (no PII)

**Salida** del modelo: Mejor momento para enviar un mensaje (para aperturas y clics)


Detalles de salida

* Calcular la mejor hora del día para enviar un correo electrónico durante los próximos 7 días con intervalos de 1 hora (por ejemplo: 9:00 am, 10:00 am, 11:00 am)
* El modelo indicará el mejor momento en los próximos 7 días para enviar el correo electrónico
* Cada tiempo óptimo se calcula dos veces: una vez para maximizar la tasa de apertura y una vez para maximizar la tasa de clics
* Se dan 16 campos (14 para los días de la semana y 2 para toda la semana):
   * mejor momento para enviar un correo electrónico para optimizar los clics para el lunes: valores entre 0 y 23
   * mejor momento para enviar un correo electrónico para optimizar las aperturas para el lunes: valores entre 0 y 23
   * mejor momento para enviar un correo electrónico para optimizar los clics para el martes: valores entre 0 y 23
   * ...
   * mejor momento para enviar un correo electrónico para optimizar los clics para el domingo: valores entre 0 y 23
   * mejor momento para enviar un correo electrónico para optimizar las aperturas para el domingo: valores entre 0 y 23
   * ...
   * mejor día para enviar un correo electrónico para optimizar las aperturas para toda la semana: de lunes a domingo
   * mejor momento para enviar un correo electrónico para optimizar las aperturas para toda la semana: valores entre 0 y 23

>[!NOTE]
>
>Estas funciones predictivas solo se aplican a los envíos de correo electrónico.
>
>El modelo necesita al menos un mes de datos para producir resultados significativos.


### Acceso a puntuaciones de perfil{#access-predictive-send-time-scores}

Una vez implementadas en Campaña, las funciones de aprendizaje automático enriquecen los datos de perfiles con nuevas fichas con las mejores puntuaciones de apertura y clic. Las métricas son calculadas por Journey AI y se ponen en Campaña mediante flujos de trabajo técnicos.

Para acceder a estas métricas, debe:

1. Abra un perfil y haga clic en el botón Editar.

1. Haga clic en la ficha **Enviar puntuación de tiempo por clic** o **Enviar puntuación de tiempo por apertura** .

De forma predeterminada, las puntuaciones de perfil proporcionarán la mejor hora del día para cada día de la semana y la mejor hora general de la semana.

![](assets/do-not-localize/SendTimeScore.png)

### Enviar mensajes en el mejor momento{#use-predictive-send-time}

Para que los mensajes de correo electrónico se publiquen a la hora óptima por perfil, el envío debe programarse con la opción **[!UICONTROL Send at a custom date defined by a formula]**.
Obtenga información sobre cómo calcular la fecha de envío [en esta sección](../../sending/using/computing-the-sending-date.md).

La fórmula debe rellenarse con la mejor hora específica del día en que se va a salir el envío.

![](assets/do-not-localize/ComputeSendingDate.png)

Ejemplo de fórmula:

```
AddHours([currentDelivery/scheduling/@contactDate], 
[cusSendTimeScoreByClickprofile_link/@EMAIL_BEST_TIME_TO_CLICK_WEDNESDAY])
```

![](assets/do-not-localize/SendingDateFormula.png)

>[!NOTE]
>
>El modelo de datos puede variar según la implementación.



## Puntuación de participación predictiva {#predictive-scoring}

La puntuación de participación predictiva le permite:

* **Seleccione una audiencia**: mediante la actividad de consulta, puede seleccionar la audiencia para interactuar con un mensaje específico
* **Excluir una audiencia**: mediante la actividad de consulta, puede eliminar la audiencia para cancelar la suscripción
* **Personalizar**: personalizar mensaje en función del nivel de participación (los usuarios con un alto nivel de participación recibirán un mensaje diferente al que reciben los que no participan)

Este modelo utiliza varias puntuaciones para indicar:

* **Abra Puntuación de participación / Haga clic en Puntuación** de participación: este valor coincide con la probabilidad de que un suscriptor interactúe con un mensaje específico (abrir o hacer clic). Los valores van de 0,0 a 1,0.
* **Probabilidad** Baja: este valor coincide con la probabilidad de que el destinatario cancele la suscripción del canal de correo electrónico a partir de un correo electrónico abierto. Los valores van de 0,0 a 1,0.
* **Nivel** de retención:  este valor clasifica a los usuarios en tres niveles: baja, media y alta. Es muy probable que el alto permanezca con la marca y el bajo valor que probablemente se cancele la suscripción.
* **Rango percentil de retención**: Clasificación de perfiles en términos de probabilidad baja. Los valores van de 0,0 a 1,0. Por ejemplo: si la clasificación de porcentaje de retención es 0,953, es más probable que este destinatario permanezca con la marca y tenga menos probabilidades de cancelar la suscripción que el 95,3% de todos los destinatarios.

>[!NOTE]
>
>Estas funciones predictivas solo se aplican a los envíos de correo electrónico.
>
>El modelo necesita al menos un mes de datos para producir resultados significativos.


**Entrada** de modelo: Registros de envío, registros de seguimiento y atributos de perfil específicos

**Salida** de modelo: Un atributo de perfil que describe la puntuación y la categoría del perfil


### Uso de la puntuación de participación para el canal de correo electrónico

Para acceder a estas métricas, debe:

1. Abra un perfil y haga clic en el botón Editar.

1. Haga clic en la ficha Puntuaciones de **participación para el Canal** de correo electrónico.

Mediante una actividad de consulta en un flujo de trabajo, puede utilizar la puntuación para optimizar la audiencia.

Por ejemplo, con los criterios de nivel **de** retención:

![](assets/do-not-localize/predictive_score_query.png)























