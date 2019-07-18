---
title: Creación de un correo electrónico multilingües
seo-title: Creación de un correo electrónico multilingües
description: Creación de un correo electrónico multilingües
seo-description: Siga estos pasos para crear destinatarios multilingües de segmentación por correo electrónico con distintos idiomas preferidos.
page-status-flag: no activado nunca
uuid: e 90 f 4 ec 8-14 e 3-4304-b 5 fc-bce 0 ba 08 a 4 ef
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: canales
content-type: reference
topic-tags: mensajes de correo electrónico
discoiquuid: 79231445-1 d 51-499 a-adcf -0 c 0 f 6 db 1 cfa 3
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 855db33971afdf9f02bf1b00be67c9e3f50bee06

---


# Creating a multilingual email{#creating-a-multilingual-email}

Puede enviar un correo electrónico multilingüe a perfiles con distintos idiomas preferidos: cada perfil recibirá una variante del correo electrónico en su idioma preferido.

Para ello, compruebe que tiene una plantilla de correo electrónico multilingüe disponible. If not, learn how to create one in [this section](../../start/using/creating-a-multilingual-template.md).

La audiencia se basa en perfiles con una información de idioma preferida.

1. Create a new email based on a [multilingual template](../../start/using/creating-a-multilingual-template.md).

   ![](assets/multi_create1.png)

1. Defina las propiedades generales y la audiencia objetivo del correo electrónico, como para un correo electrónico estándar. Refer to the [Creating audiences](../../audiences/using/creating-audiences.md) section.
1. En el cuarto paso del asistente para creación, defina las opciones de variante. If the [multilingual template](../../start/using/creating-a-multilingual-template.md) already contains all the right parameters, you can directly click on the **[!UICONTROL Create]** button.

   ![](assets/multi_create4.png)

   If needed, add variants using the **[!UICONTROL Add an element]** button. **[!UICONTROL Default]** no debe eliminarse. When set to **[!UICONTROL default]**, [the profile's preferred language](../../audiences/using/creating-profiles.md) is used to choose the variant. You can also set the **[!UICONTROL Default]** variant to any other language.

1. Confirmar la creación de correo electrónico: se mostrará el tablero de correo electrónico.
1. Defina el contenido de correo electrónico de cada variante. Según la plantilla elegida, puede definir varios temas, varios nombres de remitente o varios contenidos diferentes. Utilice el menú desplegable para desplazarse entre las distintas variantes del elemento. For more information, consult the [content editor](../../designing/using/about-email-content-design.md) section.

   ![](assets/multi_selectcontent.png)

1. Pruebe y valide el mensaje. Refer to the [Sending proof](../../sending/using/managing-test-profiles-and-sending-proofs.md#sending-proofs) section.
1. Schedule the send with the **[!UICONTROL Send after confirmation option]**.
1. Una vez enviado el correo electrónico, puede acceder a sus registros e informes para medir el éxito de la campaña. For more on reporting, refer to [this section](../../reporting/using/about-dynamic-reports.md).

