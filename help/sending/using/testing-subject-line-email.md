---
title: Prueba de la línea de asunto de un correo electrónico
description: Descubra cómo definir la línea de asunto de un correo electrónico en el Diseñador de correo electrónico.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: sending
content-type: reference
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6f89b420f0f98c13da1bfff8f9b1b29e015aef89

---

# Prueba de la línea de asunto de un correo electrónico {#testing-a-subject}


## Acerca de la línea de asunto predictiva {#about-predictive-subject-line}

Al editar un mensaje de correo electrónico, puede probar distintas líneas de asunto y obtener una estimación de su tasa de apertura antes de enviarlo.

Esta función está deshabilitada de forma predeterminada. Se activa cuando se importa el primer modelo. Un modelo es el resultado de conjuntos de datos de capacitación específicos de un sector determinado. Los modelos permiten al sistema predecir la velocidad de apertura del correo electrónico cuando se envía una nueva línea de asunto.

>[!NOTE]
>
>Esta función está disponible para los mensajes de correo electrónico y para las bases de datos que solo contienen contenido en inglés. El modelo entrenado será incoherente y dará lugar a resultados erróneos si la instancia contiene correos electrónicos en otros idiomas. La opción que permite probar un asunto solo está visible si ya hay un modelo disponible en la instancia.

Para obtener más información sobre la importación de modelos, consulte esta [sección](#importing-models).

## Prueba de la línea de asunto {#testing-subject-line}

Para probar la línea de asunto, siga los pasos a continuación:

1. Cree o abra su correo electrónico.
1. Abra el contenido e introduzca el asunto del correo electrónico en el campo de entrada correspondiente.
1. Haga clic en el **[!UICONTROL Test subject]** botón para acceder a la **[!UICONTROL Test your subject line]** ventana. Aún puede editar el asunto desde esta ventana.
1. Seleccione el modelo correcto que se debe tener en cuenta para la predicción de velocidad abierta. Existen varios modelos disponibles, cada uno de ellos correspondiente a una industria específica. Para obtener más información sobre el uso de modelos, consulte esta [sección](#importing-models).
1. Haga clic **[!UICONTROL Test]**.

A continuación, se analiza el asunto.

>[!NOTE]
>
>Si la línea de asunto es demasiado corta, no se puede analizar y se muestra un mensaje de error.

Se calculan varios indicadores y se muestra un conjunto de herramientas para ayudarle a:

* **Tasa** abierta prevista: Este gráfico le ofrece una idea de la velocidad de apertura que puede esperar para el correo electrónico con su asunto actual.
* **Duración** del asunto: Este indicador permite ver si la longitud actual del asunto es correcta o si debería ser más larga o más corta.
* **Palabras** de color: Al probar el tema, las palabras resaltadas en verde son las que contribuyen en mayor medida a aumentar la predicción de la tasa abierta. Las palabras resaltadas en rojo son las que menos contribuyen a aumentar la predicción de tasa abierta. Si agrega o elimina palabras en el asunto, las palabras resaltadas cambiarán.
* **Categorías y sugerencias** de palabras: Hacia la parte inferior de la ventana, se muestran varias categorías relevantes para el modelo seleccionado. Estas categorías se ordenan por orden de importancia y permiten ver si el asunto contiene palabras que están asociadas con él a través de un símbolo de verificación. Cada categoría contiene un conjunto de palabras sugeridas que se pueden usar en el asunto para hacerlo más relevante y aumentar la tasa abierta. Estas palabras son las palabras que se utilizan con más frecuencia en una categoría determinada.

>[!NOTE]
>
>Los campos de personalización y los signos de puntuación se eliminan del análisis de temas. En el caso del texto dinámico/condicional, todas las variantes se consideran una sola línea de asunto.

![](assets/predictive_subject_line_example.png)

## Importación de modelos {#importing-models}

De forma predeterminada, no hay ningún modelo en ejecución en el servidor de Adobe Campaign. Existen dos formas de obtener un modelo y activar la función:

* Puede formar un modelo local a partir de los datos de los mensajes de correo electrónico anteriores.
* Puede importar modelos preformados específicos de determinadas industrias (médicas, etc.) mediante la función de importación [de](../../automating/using/managing-packages.md) paquetes.

### Formación de un modelo local {#training-local-model}

* Si ya está utilizando Adobe Campaign, el modelo local recibirá automáticamente formación sobre los mensajes que ya ha enviado.
* Si es nuevo en Adobe Campaign, puede extraer un archivo CSV del sistema o ESP anterior que contenga 4 columnas: fecha, asunto, abre, enviado. Para ello, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** y siga las instrucciones que aparecen en las pantallas sucesivas. Una vez completada la carga del asunto, importe un modelo local como se describe a continuación. El modelo local se capacita automáticamente con los datos cargados.
* Si es nuevo en Adobe Campaign y no puede obtener un archivo CSV como se describe anteriormente, puede utilizar un modelo [](#pre-trained-models) preentrenado o esperar a que tenga suficientes datos de entrega en el sistema para formar un modelo local. El sistema determinará automáticamente si el conjunto de datos actual contiene datos suficientes para reconocer patrones y para entrenar el modelo.

>[!NOTE]
>
>No hay un número definido de líneas de asunto necesarias para entrenar su propio modelo. For more on this, see [Troubleshooting](#troubleshooting).
>
>Sólo puede tener un modelo entrenado en su instancia.

Para entrenar un modelo local:
1. Descargue subjectLineTraining.xml desde [aquí](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) y utilice la función de importación [de](../../automating/using/managing-packages.md) paquetes para cargarla en la instancia de Adobe Campaign. Un flujo de trabajo técnico hará automáticamente la formación.
1. La primera vez que desee formar un modelo, un administrador puede forzar el **[!UICONTROL SubjectLine Training workflow]** inicio desde el menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** .
1. Una vez cargado y entrenado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.
1. A continuación, el flujo de trabajo técnico seguirá formando automáticamente a su modelo cada semana.

### Importación de modelos preentrenados {#pre-trained-models}

Para acceder a estos modelos, haga clic [aquí](https://support.neolane.net/webApp/extranetLogin) y vaya a **[!UICONTROL Download Center]**. Utilice la función de importación [de](../../automating/using/managing-packages.md) paquetes para cargar un modelo en la instancia de Adobe Campaign.

Los modelos disponibles para su uso son:

* Industria cosmética: subjectInsightCosmetic.xml
* Supermercado: subjectInsightSupermarket.xml
* Industria médica: subjectInsightMedical.xml
* Modelo de formación: subjectlineTraining.xml.

Estos modelos no se pueden formar.

Una vez cargado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

>[!NOTE]
>
>La importación y generación de modelos formados sólo puede realizarla un administrador.

## Resolución de problemas {#troubleshooting}

La línea de asunto predictiva es un proceso de aprendizaje automático que tiene en cuenta todas las líneas de asunto que ha cargado con sus tarifas abiertas. Esto permite al sistema predecir la velocidad de apertura de un correo electrónico cuando se envía una nueva línea de asunto.

Para poder formar tu propio modelo, las líneas de asunto deben ser variadas y no deben tener duplicados, independientemente del número de líneas de asunto que se utilicen para entrenar tu modelo.

La calidad de las líneas temáticas es esencial. Si no hay suficientes datos de calidad para procesar, o si todas las líneas de asunto anteriores son demasiado similares, el sistema no podrá entrenar el modelo y puede que reciba un mensaje de error. Significa que su conjunto de registros existente no permite ofrecer una sugerencia predictiva confiable.

En este caso, debe revisar los datos que está cargando y asegurarse de que las líneas de asunto son lo suficientemente variadas como para capacitar eficazmente a su modelo.

<!--Some clients have reported this issue: I have had the subject line training workflow running for about a year now.  It has trained on 883 records and I am still seeing the message "The existing dataset is not enough to generate a model."  I do get an error in the workflow every time it runs "XML-110009 Unable to find the element 'runwf' of path '/' (document with schema 'serverConf')".

For this, campaign takes the subject line as training data and tries to come up with significant enough model to predict open rate with 95% confidence.

The 400 subject line number is mention with at least and is only indicative, model generation will also depend on quality of these lines.

It may happen that even 10k subject lines don't lead to model generation if they are too similar.

It means that it can be case that you don't have enough subject lines to generate the model and it is giving this error.

If you are getting an error/warning message, it means that your existing set of records is not enough for the predictive subject module to give a high confidence suggestion.

Adobe recommends reviewing the data you are uploading as the similarity of the subject lines might be the issue.-->
