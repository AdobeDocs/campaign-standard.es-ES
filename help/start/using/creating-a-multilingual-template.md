---
title: Creación de una plantilla multilingüe
seo-title: Creación de una plantilla multilingüe
description: Creación de una plantilla multilingüe
seo-description: Aprenda a definir y ejecutar entregas multilingües por correo electrónico o SMS a través de una entrega única basada en el idioma preferido de los clientes segmentados automáticamente. Informar sobre el rendimiento de cada entrega hasta los niveles de idioma y individuales.
page-status-flag: no activado nunca
uuid: 7 a 2 cd 5 f 7-c 0 fc -4825-a 770-a 62816 c 66 b 3 f
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: start
content-type: reference
topic-tags: administración de plantillas
discoiquuid: 064 c 5 c 4 a-f 579-4 bab-adf 3-51 c 92 eb 4518 f
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Creating a multilingual template{#creating-a-multilingual-template}

Una plantilla multilingüe es una plantilla específica para administrar mensajes multilingües.

This kind of template is available for **Email and SMS messages** and useable in standalone mode, within a workflow or in a recurring delivery.

En las plantillas de funciones multilingües, la administración de idioma se basa en las variantes. **Cada variante representa un idioma.**

Adobe Campaign Standard puede configurar un máximo de 40 variantes.

Adobe Campaign viene con un idioma predeterminado que se establece en EN. El idioma predeterminado puede cambiarse a otra variante pero nunca debe eliminarse.

Durante la creación de la plantilla, puede agregar la cantidad de variantes correspondientes al número de idiomas necesarios en el mensaje.

Para realizar la creación de SMS o plantillas de correo electrónico, siga los pasos:

1. Duplique una plantilla multilingüe existente (SMS o correo electrónico).

   ![](assets/multi_template_duplicate.png)

   >[!NOTE]
   >
   >You can also modify an existing standard template in a multilingual template by clicking on the **[!UICONTROL Initialize content variant]** button in the template properties.

1. Modifique las propiedades para personalizar la etiqueta, el seguimiento, etc.
1. Para modificar la cantidad de variantes deseadas, haga clic en el mosaico de variantes. Se muestra la ventana de variantes

   ![](assets/multi_template_variants.png)

   Puede agregar o eliminar variantes. To add a variant, complete the **[!UICONTROL New content variant]** window.

   ![](assets/multi_template_newvariant.png)

   >[!NOTE]
   >
   >No elimine la variante «default», ya que es la variante enviada a perfiles sin un parámetro de idioma preferido.

1. Personalice la variante de etiquetas si es necesario y haga clic en confirmar.
1. También puede agregar directamente el contenido de cada variante.

Ya está listo para crear un mensaje de correo electrónico o SMS basado en esta plantilla multilingüe.

**Temas relacionados:**

* [Creación de un correo electrónico multilingües](../../channels/using/creating-a-multilingual-email.md)
* [Creación de perfiles](../../audiences/using/creating-profiles.md)

