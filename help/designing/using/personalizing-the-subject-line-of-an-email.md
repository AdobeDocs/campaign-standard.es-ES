---
title: Personalización de la línea del asunto de un correo electrónico
seo-title: Personalización de la línea del asunto de un correo electrónico
description: Personalización de la línea del asunto de un correo electrónico
seo-description: Puede personalizar el asunto de un correo electrónico, pero también probar distintas líneas de asunto y obtener una estimación de su tasa abierta.
page-status-flag: no activado nunca
uuid: 345 b 5 f 4 b -8 e 2 c -4 f 8 e-bce 7-0 e 9 b 40 a 44932
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: personalizar contenido
discoiquuid: f 7 a 5 e 935-54 cf -422 e -8459-27221409 a 200
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 782a5f89b0361f1cbe59c9b353ca90dec90c3906

---


# Personalización de la línea del asunto de un correo electrónico{#personalizing-the-subject-line-of-an-email}

## Personalización de un asunto de correo electrónico {#personalizing-an-email-subject}

El asunto del mensaje es obligatorio para preparar y enviar el mensaje.

>[!NOTE]
>
>Si la línea del asunto está vacía, aparece una advertencia en el panel de mensajes y en el de correo electrónico de Designer.

Para configurar el asunto del mensaje de correo electrónico, vaya **[!UICONTROL Properties]** a la ficha de la página principal de Designer Designer (accesible a través del icono de inicio) y rellene la **[!UICONTROL Subject]** sección.

![](assets/email_designer_subject.png)

También puede agregar campos de personalización, bloques de contenido y contenido dinámico a la línea del asunto haciendo clic en los iconos correspondientes.

**Temas relacionados:**

* [Inserción de un campo de personalización](../../designing/using/inserting-a-personalization-field.md)
* [Adición de un bloque de contenido](../../designing/using/adding-a-content-block.md)
* [Definición de contenido dinámico en un mensaje de correo electrónico](../../designing/using/defining-dynamic-content-in-an-email.md)

## Línea de asunto predictiva {#predictive-subject-line}

Al editar un correo electrónico, puede probar distintas líneas de asunto y obtener una estimación de su velocidad abierta antes de enviarla.

Esta función está deshabilitada de forma predeterminada. Se activa cuando se importa el primer modelo. Un modelo es el resultado de conjuntos de datos de capacitación específicos de un sector determinado. Los modelos permiten al sistema predecir la velocidad abierta del mensaje de correo electrónico cuando se envía una nueva línea de asunto.

>[!NOTE]
>
>Esta función está disponible para mensajes de correo electrónico y para bases de datos que contienen contenido en inglés solamente. El modelo formado será incoherente y dará lugar a resultados erróneos si su instancia contiene correos electrónicos en otros idiomas. La opción que le permite probar un asunto solo es visible si un modelo ya está disponible en su instancia.

### Prueba de un asunto {#testing-a-subject}

Para probar la línea de asunto:

1. Cree o abra su correo electrónico.
1. Abra el contenido e introduzca el asunto del correo electrónico en el campo de entrada correspondiente.
1. Haga clic **[!UICONTROL Test subject]** en el botón para acceder a **[!UICONTROL Test your subject line]** la ventana. Todavía puede editar el asunto desde esta ventana.
1. Seleccione el modelo correcto para tener en cuenta la predicción de velocidad abierta. Hay varios modelos disponibles, cada uno correspondiente a un sector específico.
1. Click **[!UICONTROL Test]**.

Se analiza el asunto.

>[!NOTE]
>
>Si la línea de asunto es demasiado corta, no se puede analizar y se muestra un mensaje de error.

Se calculan varios indicadores y se muestra un conjunto de herramientas para ayudarle a:

* **Tasa abierta prevista**: Este gráfico le proporciona una idea de la velocidad abierta que puede esperar para el correo electrónico con su asunto actual.
* **Longitud del sujeto**: Este indicador le permite ver si la longitud actual del sujeto es correcta o si tendría que ser más larga o más corta.
* **Palabras coloreadas**: Al probar el asunto, las palabras resaltadas en verde son las palabras que contribuyen en mayor medida a aumentar la predicción de velocidad abierta. Las palabras resaltadas en rojo son las palabras que contribuyen al menos a aumentar la predicción de velocidad abierta. Si agrega o elimina palabras del sujeto, las palabras resaltadas cambiarán.
* **Sugerencias y sugerencias de palabras**: En la parte inferior de la ventana, se muestran varias categorías relevantes para el modelo seleccionado. Estas categorías se ordenan por orden de importancia y permiten ver si el asunto contiene palabras asociadas a él mediante un símbolo de comprobación. Cada categoría contiene un conjunto de palabras sugeridas que pueden utilizarse en su tema para hacerla más relevante e incrementar la velocidad abierta. Estas palabras son las palabras que se utilizan con más frecuencia en una categoría determinada.

>[!NOTE]
>
>Los campos de personalización y de puntuación se eliminan del análisis del sujeto. En el caso de texto dinámico o condicional, todas las variantes se consideran una línea de asunto.

![](assets/predictive_subject_line_example.png)

### Importación de modelos {#importing-models}

De forma predeterminada, no hay modelo que se ejecute en el servidor de Adobe Campaign. Existen dos maneras de obtener un modelo y activar la función:

* Puede capacitar a un modelo local a partir de los datos de los mensajes de correo electrónico anteriores:

   * Si ya utiliza Adobe Campaign, el modelo local se capacitará automáticamente en los mensajes que ya haya enviado.
   * Si es nuevo en Adobe Campaign, puede extraer un archivo CSV del sistema o ESP anterior que contenga 4 columnas: fecha, asunto, enviado, se abre. Para ello, vaya a **[!UICONTROL Administration]** &gt; **[!UICONTROL Channels]** &gt; **[!UICONTROL Email]** &gt; **[!UICONTROL Subject Line Import]** y siga las instrucciones proporcionadas en las pantallas sucesivas. Una vez completada la carga del asunto, importe un modelo local como se describe a continuación. El modelo local se capacita automáticamente con los datos cargados.
   * Si es nuevo en Adobe Campaign y no puede obtener un archivo CSV como se ha descrito anteriormente, puede utilizar un modelo preformado o esperar hasta que tenga suficientes datos de entrega en el sistema para entrenar un modelo local. El sistema determinará automáticamente si el conjunto de datos actual contiene datos suficientes para reconocer patrones y capacitar al modelo.

      >[!NOTE]
      >
      >No hay un número definido de líneas de asunto necesarias para formar su propio modelo. Para poder entrenarlo, es necesario variar las líneas de asunto y no tener duplicados. Si no hay suficientes datos para procesar, el sistema no podrá entrenar el modelo. Solo puede tener un modelo capacitado en su instancia.
   Para formar un modelo local, descargue subjectLineTraining.xml desde [aquí](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) y utilice la función [de importación](../../automating/using/managing-packages.md) de paquetes para cargarla en su instancia de Adobe Campaign. Un flujo de trabajo técnico automáticamente realizará la capacitación.

   La primera vez que desee entrenar un modelo, un administrador puede forzar **[!UICONTROL SubjectLine Training workflow]** que comience desde **[!UICONTROL Administration]** el menú &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Workflows]** .

   Una vez que se ha cargado y formado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

   A continuación, el flujo de trabajo técnico seguirá formando automáticamente el modelo todas las semanas.

* Puede importar modelos precapacitados específicos de determinadas industrias (médicas, etc.) mediante [la función de importación](../../automating/using/managing-packages.md) de paquetes. Estos modelos están disponibles [aquí](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) y no pueden capacitarse.

   Una vez que se ha cargado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

>[!NOTE]
>
>La importación y generación de modelos capacitados solo puede realizarla un administrador.

Los modelos disponibles para utilizar son:

* Industria cosmética: subjectInsightCosmetic.xml
* Industria de supermercado: subjectInsightSupermarket.xml
* Industria médica: subjectInsightMedical.xml
* Modelo que se va a capacitar: Subjectlinetraining. xml.

**Tema relacionado:**

* [Optimización de líneas de asunto con predicciones de Adobe Sensei](https://helpx.adobe.com/campaign/kb/simplify-campaign-management.html#Createcompellingcontenttailoredtoeveryindividual)
