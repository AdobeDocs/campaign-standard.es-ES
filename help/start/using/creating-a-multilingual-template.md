---
title: Creación de una plantilla multilingüe
description: Obtenga información sobre cómo definir y ejecutar entregas multilingües por correo electrónico/SMS a través de una única entrega basada en el idioma preferido de los clientes segmentados automáticamente. Informar sobre el rendimiento de cada entrega en función del idioma y de los niveles individuales.
page-status-flag: nunca activado
uuid: 7a2cd5f7-c0fc-4825-a770-a62816c66b3f
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: start
content-type: referencia
topic-tags: administrar plantillas
discoiquuid: 064c5c4a-f579-4bab-adf3-51c92eb4518f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 00fc2e12669a00c788355ef4e492375957cdad2e

---


# Creación de una plantilla multilingüe{#creating-a-multilingual-template}

Una plantilla multilingüe es una plantilla específica para administrar mensajes multilingües.

Este tipo de plantilla está disponible para mensajes **de correo** electrónico y SMS y se puede utilizar en modo independiente, en un flujo de trabajo o en una entrega recurrente.

En las plantillas de funciones multilingües, la administración de idiomas se basa en variantes. **Cada variante representa un idioma.**

Adobe Campaign Standard puede configurar un máximo de 40 variantes.

Adobe Campaign incluye un idioma predeterminado que se establece en EN. El idioma predeterminado se puede cambiar a otra variante, pero nunca se debe eliminar.

Durante la creación de la plantilla, puede agregar el número de variantes correspondiente al número de idiomas necesarios en el mensaje.

Para crear plantillas de correo electrónico o SMS, siga los pasos:

1. Duplique una plantilla multilingüe existente (SMS o Correo electrónico).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >También puede modificar una plantilla estándar existente en una plantilla multilingüe haciendo clic en el botón **[!UICONTROL Initialize content variant]** de las propiedades de la plantilla.

1. Modifique las propiedades para personalizar la etiqueta, el seguimiento, etc.
1. Modifique el número de variantes deseadas haciendo clic en el mosaico de variantes. Se muestra la ventana Variantes

   ![](assets/multi_template_variants.png)

   Puede agregar o quitar variantes. Para agregar una variante, complete la **[!UICONTROL New content variant]** ventana.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >No elimine la variante "predeterminada" ya que es la variante enviada a los perfiles sin un parámetro de idioma preferido completado.

1. Personalice la variante de etiqueta si es necesario y haga clic en Confirmar.
1. También puede agregar directamente el contenido para cada variante.

Ya está listo para crear un mensaje de correo electrónico o SMS basado en esta plantilla multilingüe.

**Temas relacionados:**

* [Creación de un correo electrónico multilingüe](../../channels/using/creating-a-multilingual-email.md)
* [Creación de perfiles](../../audiences/using/creating-profiles.md)

