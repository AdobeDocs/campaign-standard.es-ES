---
title: Testing the subject line of an email
seo-title: Testing the subject line of an email
description: Testing the subject line of an email
seo-description: Discover how to define the subject line of an email in the Email Designer.
page-status-flag: never-activated
uuid: 571ffc01-6e41-4501-9094-2f812b041a10
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: enviar
content-type: referencia
topic-tags: editing-email-content
discoiquuid: 39b86fda-7766-4e5f-ab48-bcc536ab66b3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 3fc0d9d7e90a31ffb34efc33d6f5c148ba5aac90

---

# Prueba de la línea de asunto de un correo electrónico {#testing-a-subject}

Para probar la línea de asunto, siga los pasos a continuación:

1. Cree o abra su correo electrónico.
1. Abra el contenido e introduzca el asunto del correo electrónico en el campo de entrada correspondiente.
1. Haga clic en el **[!UICONTROL Test subject]** botón para acceder a la **[!UICONTROL Test your subject line]** ventana. Aún puede editar el asunto desde esta ventana.
1. Seleccione el modelo correcto que se debe tener en cuenta para la predicción de velocidad abierta. Existen varios modelos disponibles, cada uno de ellos correspondiente a una industria específica.
1. Click **[!UICONTROL Test]**.

A continuación, se analiza el asunto.

>[!NOTE]
>
>Si la línea de asunto es demasiado corta, no se puede analizar y se muestra un mensaje de error.

Se calculan varios indicadores y se muestra un conjunto de herramientas para ayudarle a:

* **Tasa** abierta prevista: Este gráfico le ofrece una idea de la velocidad de apertura que puede esperar para el correo electrónico con su asunto actual.
* **Duración** del asunto: Este indicador permite ver si la longitud actual del asunto es correcta o si debería ser más larga o más corta.
* **Palabras** de color: Al probar el tema, las palabras resaltadas en verde son las que contribuyen en mayor medida a aumentar la predicción de la tasa abierta. Las palabras resaltadas en rojo son las que menos contribuyen a aumentar la predicción de tasa abierta. Si agrega o elimina palabras en el asunto, las palabras resaltadas cambiarán.
* **Categorías y sugerencias** de palabras: Hacia la parte inferior de la ventana se muestran varias categorías relevantes para el modelo seleccionado. Estas categorías se ordenan por orden de importancia y permiten ver si el asunto contiene palabras que están asociadas con él a través de un símbolo de verificación. Each category contains a set of suggested words that could be used in your subject to make it more relevant and increase the open rate. Estas palabras son las palabras que se utilizan con más frecuencia en una categoría determinada.

>[!NOTE]
>
>Los campos de personalización y los signos de puntuación se eliminan del análisis de temas. En el caso del texto dinámico/condicional, todas las variantes se consideran una sola línea de asunto.

![](assets/predictive_subject_line_example.png)

## Importación de modelos {#importing-models}

De forma predeterminada, no hay ningún modelo en ejecución en el servidor de Adobe Campaign. Existen dos formas de obtener un modelo y activar la función:

* Puede formar un modelo local a partir de los datos de los mensajes de correo electrónico anteriores:

   * Si ya utiliza Adobe Campaign, el modelo local recibirá automáticamente formación sobre los mensajes que ya haya enviado.
   * If you are new to Adobe Campaign, you can extract a CSV file from your previous system/ESP that contains 4 columns: date, subject, sent, opens. Para ello, vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** y siga las instrucciones que aparecen en las pantallas sucesivas. When the subject upload is complete, import a local model as described below. The local model is automatically trained with the data you uploaded.
   * If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a pre-trained model or wait until you have enough delivery data in your system to train a local model. The system will automatically determine whether your current data set contains enough data to recognize patterns and to train the model.

      >[!NOTE]
      >
      >No hay un número definido de líneas de asunto necesarias para entrenar su propio modelo. To be able to train it, the subject lines need to be varied and to have no duplicates. If there is not enough data to process, the system will not be able to train the model. You can only have one trained model on your instance.
   To train a local model, download the subjectLineTraining.xml from here and use the package import feature to upload it to your Adobe Campaign instance. [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter)[](../../automating/using/managing-packages.md) A technical workflow will automatically do the training for you.

   The first time you want to train a model, an administrator can force the  to start from the  &gt;  &gt;  menu.**[!UICONTROL SubjectLine Training workflow]****[!UICONTROL Administration]****[!UICONTROL Application settings]****[!UICONTROL Workflows]**

   Once a model has been uploaded and trained, the feature is automatically activated and a new option appears next to the subject line field of your messages.

   Then, the technical workflow will automatically continue to train your model every week.

* You can import pre-trained models that are specific to certain industries (medical, etc.) mediante la función de importación [de](../../automating/using/managing-packages.md) paquetes. Estos modelos están disponibles [aquí](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) y no se pueden formar.

   Una vez cargado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

>[!NOTE]
>
>La importación y generación de modelos formados sólo puede realizarla un administrador.

Los modelos disponibles para su uso son:

* Industria cosmética: subjectInsightCosmetic.xml
* Supermercado: subjectInsightSupermarket.xml
* Industria médica: subjectInsightMedical.xml
* Modelo de formación: subjectlineTraining.xml.
