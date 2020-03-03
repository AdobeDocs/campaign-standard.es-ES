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
source-git-commit: 7e61796376a14c279d38107905275172be0dd12d

---

# Prueba de la línea de asunto de un correo electrónico {#testing-a-subject}

Para probar la línea de asunto, siga los pasos a continuación:

1. Cree o abra su correo electrónico.
1. Abra el contenido e introduzca el asunto del correo electrónico en el campo de entrada correspondiente.
1. Haga clic en el **[!UICONTROL Test subject]** botón para acceder a la **[!UICONTROL Test your subject line]** ventana. Aún puede editar el asunto desde esta ventana.
1. Seleccione el modelo correcto que se debe tener en cuenta para la predicción de velocidad abierta. Existen varios modelos disponibles, cada uno de ellos correspondiente a una industria específica.
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

* Puede formar un modelo local a partir de los datos de los mensajes de correo electrónico anteriores:

   * Si ya está utilizando Adobe Campaign, el modelo local recibirá automáticamente formación sobre los mensajes que ya ha enviado.
   * Si es nuevo en Adobe Campaign, puede extraer un archivo CSV del sistema o ESP anterior que contenga 4 columnas: fecha, asunto, abre, enviado. Para ello, vaya a **[!UICONTROL Administration]** > **[!UICONTROL Channels]** > **[!UICONTROL Email]** > **[!UICONTROL Subject Line Import]** y siga las instrucciones que aparecen en las pantallas sucesivas. Una vez completada la carga del asunto, importe un modelo local como se describe a continuación. El modelo local se capacita automáticamente con los datos cargados.
   * Si es nuevo en Adobe Campaign y no puede obtener un archivo CSV como se describe anteriormente, puede utilizar un modelo preentrenado o esperar hasta que tenga suficientes datos de entrega en el sistema para entrenar un modelo local. El sistema determinará automáticamente si el conjunto de datos actual contiene datos suficientes para reconocer patrones y para entrenar el modelo.

      >[!NOTE]
      >
      >No hay un número definido de líneas de asunto necesarias para entrenar su propio modelo. Para poder capacitarlo, las líneas de asunto deben ser variadas y no tener duplicados. Si no hay suficientes datos para procesar, el sistema no podrá entrenar al modelo. Sólo puede tener un modelo entrenado en su instancia.
   Para formar un modelo local, descargue subjectLineTraining.xml desde [aquí](https://support.neolane.net/webApp/downloadCenter?__userConfig=psaDownloadCenter) y utilice la función de importación [de](../../automating/using/managing-packages.md) paquetes para cargarlo en la instancia de Adobe Campaign. Un flujo de trabajo técnico hará automáticamente la formación.

   La primera vez que desee formar un modelo, un administrador puede forzar el **[!UICONTROL SubjectLine Training workflow]** inicio desde el menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Workflows]** .

   Una vez cargado y entrenado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

   A continuación, el flujo de trabajo técnico seguirá formando automáticamente a su modelo cada semana.

* Puede importar modelos preformados específicos de determinadas industrias (médicas, etc.) mediante la función de importación [de](../../automating/using/managing-packages.md) paquetes. Para acceder a estos modelos, haga clic [aquí](https://support.neolane.net/webApp/extranetLogin) y vaya al Centro de **[descarga]**. Estos modelos no se pueden formar.

   Una vez cargado un modelo, la función se activa automáticamente y aparece una nueva opción junto al campo de línea de asunto de los mensajes.

>[!NOTE]
>
>La importación y generación de modelos formados sólo puede realizarla un administrador.

Los modelos disponibles para su uso son:

* Industria cosmética: subjectInsightCosmetic.xml
* Supermercado: subjectInsightSupermarket.xml
* Industria médica: subjectInsightMedical.xml
* Modelo de formación: subjectlineTraining.xml.
