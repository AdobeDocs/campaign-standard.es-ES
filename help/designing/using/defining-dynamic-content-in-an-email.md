---
title: Definición de contenido dinámico en un mensaje de correo electrónico
seo-title: Definición de contenido dinámico en un mensaje de correo electrónico
description: Definición de contenido dinámico en un mensaje de correo electrónico
seo-description: Siga estos pasos para mostrar contenido diferente dinámicamente en un mensaje de correo electrónico según las condiciones definidas a través del editor de expresiones de Adobe Campaign.
page-status-flag: no activado nunca
uuid: b 1 c 5013 f -3201-4239-8202-511 a 6902 d 604
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: diseñar
content-type: reference
topic-tags: definir-condicional-content
discoiquuid: d 0 d 009 a 5-6022-433 e-acdf -2 b 51 a 243 a 5 c 9
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: b7df681c05c48dc1fc9873b1339fbc756e5e0f5f

---


# Defining dynamic content in an email{#defining-dynamic-content-in-an-email}

En un mensaje de correo electrónico, puede definir contenido diferente que se mostrará dinámicamente a los destinatarios según las condiciones definidas mediante el editor de expresiones. Por ejemplo, a partir del mismo mensaje de correo electrónico, puede asegurarse de que cada perfil recibe un mensaje diferente según su intervalo de edad.

Defining dynamic content is different from [defining visibility conditions](../../designing/using/defining-a-visibility-condition.md).

1. Seleccione un fragmento, un componente o un elemento. En este ejemplo, seleccione una imagen.
1. Click the **[!UICONTROL Dynamic content]** icon from the contextual toolbar.

   ![](assets/dynamic_content_2.png)

   The **[!UICONTROL Dynamic content]** section appears in the palette on the left.

   ![](assets/dynamic_content_3.png)

   De forma predeterminada, esta sección contiene dos elementos: la variante predeterminada y una nueva variante.

   >[!NOTE]
   >
   >El contenido siempre debe tener una variante predeterminada. No se puede eliminar.

1. Click the **[!UICONTROL Edit]** button to define the display conditions for the first alternative variant.

   ![](assets/dynamic_content_4.png)

1. Especifique una etiqueta y seleccione los campos que desee definir como condiciones. For example, from the **[!UICONTROL General]** node, select the **[!UICONTROL Age]** field

   ![](assets/dynamic_content_5.png)

1. Defina las condiciones de filtrado. Por ejemplo, desea que se muestre otro contenido a las personas que tengan edades comprendidas entre 18 y 25 años.

   ![](assets/dynamic_content_6.png)

1. Una vez configuradas todas las condiciones, defina el orden de prioridad en el que se aplicará la condición y guarde los cambios.

   ![](assets/dynamic_content_7.png)

   El contenido se mostrará en la paleta en orden de prioridad, de arriba a abajo. For more on priorities, refer to [this section](../../designing/using/defining-dynamic-content-in-an-email.md#order-of-priority).

1. Cargue una imagen nueva para la variante que acaba de definir.

   ![](assets/dynamic_content_8.png)

   Los destinatarios de edades comprendidas entre 18 y 25 años verán la nueva imagen.

   ![](assets/dynamic_content_10.png)

1. Click **[!UICONTROL Add a condition]** to add a new content and its linked rule.

   ![](assets/dynamic_content_9.png)

   Por ejemplo, puede agregar una imagen diferente para que se muestre a personas con edades comprendidas entre 26 y 35 años.

1. Proceda de forma similar para cualquier otro elemento del mensaje de correo electrónico que desee mostrar dinámicamente. Puede ser texto, botón, fragmento, etc. Guarde los cambios.

>[!CAUTION]
>
>Una vez que haya preparado el mensaje y antes de enviarlo, pruébelo usando una prueba. Si no lo hace, puede que algunos errores no se detecten y que el correo electrónico no se envíe.

**Temas relacionados:**

* [Envío de pruebas](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs)
* [Edición de expresiones avanzadas](../../automating/using/editing-queries.md#about-query-editor)

## Order of priority {#order-of-priority}

En el editor de expresiones, cuando se define un contenido dinámico, el orden de prioridad es el siguiente.

1. You define two different dynamic contents with **two different conditions**, for example:

   **Condición 1:** el sexo del perfil es masculino,

   **Condición 2:** el perfil tiene entre 20 y 30 años.

   ![](assets/delivery_content_61.png)

   Algunos perfiles de la base de datos se corresponden con las dos condiciones, pero solo se puede enviar un correo electrónico con un contenido dinámico.

1. Por lo tanto, debe definir la prioridad para el contenido dinámico. A condition with an order of priority of **1** (and therefore the corresponding dynamic content) will be sent to a profile even if another condition whose priority order is **2** or **3** is also met by this profile.

   ![](assets/delivery_content_62.png)

Solo puede definir un orden de prioridad por contenido dinámico.
