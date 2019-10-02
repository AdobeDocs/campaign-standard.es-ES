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
source-git-commit: 8b85bbad7458286252a2900ce730288f6e52442e

---

# Prueba de un sujeto {#testing-a-subject}

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
* **Categorías y sugerencias** de palabras: Hacia la parte inferior de la ventana se muestran varias categorías relevantes para el modelo seleccionado. Estas categorías se ordenan por orden de importancia y permiten ver si el asunto contiene palabras que están asociadas con él a través de un símbolo de verificación. Cada categoría contiene un conjunto de palabras sugeridas que se pueden usar en el asunto para hacerlo más relevante y aumentar la tasa abierta. Estas palabras son las palabras que se utilizan con más frecuencia en una categoría determinada.

>[!NOTE]
>
>Los campos de personalización y los signos de puntuación se eliminan del análisis de temas. En el caso del texto dinámico/condicional, todas las variantes se consideran una sola línea de asunto.

![](assets/predictive_subject_line_example.png)

## Importing models {#importing-models}

De forma predeterminada, no hay ningún modelo en ejecución en el servidor de Adobe Campaign. There are two ways to get a model and activate the feature:

* You can train a local model from the data of your previous email messages:

   * If you are already using Adobe Campaign, the local model will be automatically trained on the messages that you have already sent.
   * If you are new to Adobe Campaign, you can extract a CSV file from your previous system/ESP that contains 4 columns: date, subject, sent, opens. To do that, go to  &gt;  &gt;  &gt;  and follow the instructions provided on the successive screens. **[!UICONTROL Administration]****[!UICONTROL Channels]****[!UICONTROL Email]****[!UICONTROL Subject Line Import]** When the subject upload is complete, import a local model as described below. The local model is automatically trained with the data you uploaded.
   * If you are new to Adobe Campaign and cannot get a CSV file as described above, you can use a pre-trained model or wait until you have enough delivery data in your system to train a local model. The system will automatically determine whether your current data set contains enough data to recognize patterns and to train the model.

      >[!NOTE]
      >
      >There is no defined number of subject lines needed to train your own model. To be able to train it, the subject lines need to be varied and to have no duplicates. Si no hay suficientes datos para procesar, el sistema no podrá entrenar al modelo. You can only have one trained model on your instance.
   To train a local model, download the subjectLineTraining.xml from here and use the package import feature to upload it to your Adobe Campaign instance. [](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter)[](../../automating/using/managing-packages.md) Un flujo de trabajo técnico hará automáticamente la formación.

   The first time you want to train a model, an administrator can force the  to start from the  &gt;  &gt;  menu.**[!UICONTROL SubjectLine Training workflow]****[!UICONTROL Administration]****[!UICONTROL Application settings]****[!UICONTROL Workflows]**

   Una vez cargado y entrenado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

   A continuación, el flujo de trabajo técnico seguirá formando automáticamente a su modelo cada semana.

* Puede importar modelos preformados específicos de determinadas industrias (médicas, etc.) mediante la función de importación [de](../../automating/using/managing-packages.md) paquetes. Estos modelos están disponibles [aquí](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) y no se pueden formar.

   Una vez cargado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

>[!NOTE]
>
>La importación y generación de modelos formados sólo puede realizarla un administrador.

Los modelos disponibles para su uso son:

* Industria cosmética: subjectInsightCosmetic.xml
* Supermercado: subjectInsightSupermarket.xml
* Industria médica: subjectInsightMedical.xml
* Modelo de formación: subjectlineTraining.xml.