---
title: '" Ejemplo: Personalización de correo electrónico "'
seo-title: '" Ejemplo: Personalización de correo electrónico "'
description: '" Ejemplo: Personalización de correo electrónico "'
seo-description: Vea un ejemplo completo de personalización de un correo electrónico con contenido dinámico y texto según las edades de los perfiles.
page-status-flag: no activado nunca
uuid: 3 d 30213 c -474 f -4 e 5 f -8688-9260 ea 2 e 2583
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: personalizar contenido
discoiquuid: d 1 b 618 ac-a 842-41 e 8-9 ba 6-7 a 50 f 7315 b 02
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a12df43de55dedf388a397fbf4670d99e3ea7f3d

---


# Example: Email personalization{#example-email-personalization}

En este ejemplo, un miembro del equipo de mercadotecnia ha creado un correo electrónico para informar a algunos de sus clientes de que existe una oferta especial solo para ellos. El miembro del equipo decidió personalizar el correo electrónico según las respectivas edades de los clientes. Los clientes de edades comprendidas entre 18 y 27 años recibirán un correo electrónico con una imagen y un eslogan diferente a los que recibirán los clientes anteriores a 27.

El correo electrónico se crea de la siguiente manera:

* El contenido dinámico se aplica a la imagen y estos contenidos dinámicos se configuran según el intervalo de edad.

   ![](assets/delivery_content_43.png)

   Adding and configuring dynamic content is detailed in the [Defining dynamic content in an email](../../designing/using/defining-dynamic-content-in-an-email.md) section.

* Los campos de personalización y el contenido dinámico se aplican al texto. Según el rango de edad del perfil, el mensaje de correo electrónico comienza con el nombre del perfil o con el título y apellido del perfil.

   ![](assets/delivery_content_44.png)

   Adding and configuring the personalization fields is detailed in the [Inserting a personalization field](../../designing/using/inserting-a-personalization-field.md) section.

## Configuring images {#configuring-images}

En este ejemplo, el contenido dinámico aplicado a las imágenes se configura de la siguiente manera:

**Para objetivos de 18 a 27 años:**

1. Select the dynamic content in the **[!UICONTROL Properties]** palette and click the **[!UICONTROL Edit]** button.

   ![](assets/delivery_content_48.png)

1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.

   ![](assets/delivery_content_49.png)

1. Select the **Greater than or equal to** operator then enter **18** to create the **older than 18** expression.

   ![](assets/delivery_content_50.png)

1. Add a new **[!UICONTROL Age]** condition.

   Select the **Less than or equal to** operator followed by 27 in the value field to create the **younger than 27** expression.

   ![](assets/delivery_content_51.png)

1. Confirme los cambios.

**Para segmentar perfiles con edades comprendidas entre 27 y superiores:**

1. Seleccione el contenido dinámico de la paleta y edítelo.
1. Edit the label then select the **[!UICONTROL Age]** field from the **[!UICONTROL Profile]** node.
1. Add the **Greater than** operator followed by 27 in the value field to create the **older than 27** expression.

   ![](assets/delivery_content_52.png)

1. Confirme los cambios.

El contenido dinámico se configura correctamente.

## Configuring text {#configuring-text}

En este ejemplo, el contenido dinámico aplicado a los textos se configura de la siguiente manera:

**Para destinar perfiles de entre 18-27:**

1. Seleccione el componente de estructura que desee y agregue un contenido dinámico.
1. Edite el contenido dinámico y configure las expresiones de objetivo. Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.

   ![](assets/delivery_content_53.png)

1. In the list that appears, select the **[!UICONTROL First name]** field and confirm.

   ![](assets/delivery_content_54.png)

1. Su campo de personalización se inserta perfectamente en el contenido dinámico seleccionado.

**Para segmentar perfiles con edades comprendidas entre 27 y superiores:**

1. Seleccione el componente de estructura que desee y agregue un contenido dinámico.
1. Edite el contenido dinámico y configure las expresiones de objetivo. Refer to [Configuring images](../../designing/using/example--email-personalization.md#configuring-images).
1. In the structure component, at the desired position, click the **[!UICONTROL Personalize]** icon from the contextual toolbar and select **[!UICONTROL Insert personalization field]**.
1. Select **[!UICONTROL Title]** from the drop-down list.
1. Proceed similarly to add the **[!UICONTROL Last name]** field.

   ![](assets/delivery_content_56.png)

Los campos de personalización deberían estar perfectamente insertados en el contenido dinámico elegido.

## Previewing emails {#previewing-emails}

Previewing allows you to check that the personalization fields and the dynamic contents are configured correctly before sending the **[!UICONTROL Proofs]**. Durante la vista previa, puede seleccionar diferentes perfiles de prueba correspondientes a los destinos de correo electrónico.

Sin perfiles de prueba, el correo electrónico que aparece de forma predeterminada es:

![](assets/delivery_content_45.png)

El correo electrónico no tiene campos de personalización en el eslogan y se utiliza la imagen predeterminada.

El primer perfil de prueba corresponde a un cliente comprendido entre 18 y 27. Al seleccionar este perfil, aparece el siguiente mensaje de correo electrónico:

![](assets/delivery_content_46.png)

El campo de personalización correspondiente a la expresión de 18-27 años, específicamente el nombre del perfil, se configura correctamente y la imagen también se ha modificado según el perfil.

El segundo perfil corresponde a un cliente superior a 27 y genera el siguiente correo electrónico:

![](assets/delivery_content_47.png)

La imagen ha cambiado gracias al contenido dinámico y el eslogan que aparece es el eslogan más formal definido para este público objetivo.

**Temas relacionados:**

* [Creación de audiencias](../../audiences/using/creating-audiences.md)
* [Preparación del envío](../../sending/using/preparing-the-send.md)

