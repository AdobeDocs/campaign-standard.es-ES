---
title: Creación de un correo electrónico multilingüe
description: Siga estos pasos para crear un correo electrónico multilingüe dirigido a destinatarios con diferentes idiomas preferidos.
audience: channels
content-type: reference
topic-tags: email-messages
feature: Email
role: User
level: Intermediate
exl-id: fcf192cb-f2d5-4340-bc2f-add0c195ad4e
source-git-commit: d234d7fab039b602eff06c03ba0d8f7ce2a0cf3f
workflow-type: tm+mt
source-wordcount: '278'
ht-degree: 24%

---

# Creación de un correo electrónico multilingüe{#creating-a-multilingual-email}

Puede enviar un correo electrónico multilingüe a perfiles con diferentes idiomas preferidos: cada perfil recibe una variante del correo electrónico en su idioma preferido.

Para ello, compruebe que dispone de una plantilla de correo electrónico multilingüe. Si no es así, aprenda a crear uno en [esta sección](../../channels/using/multilingual-messages-template.md).

La audiencia se basa en perfiles con información de idioma preferido rellenada.

1. Cree un nuevo correo electrónico basado en una [plantilla multilingüe](../../channels/using/multilingual-messages-template.md).

   ![](assets/multi_create1.png)

1. Defina las propiedades generales y la audiencia de destino del mensaje de correo electrónico, igual que para un correo electrónico estándar. Consulte la sección [Creación de audiencias](../../audiences/using/creating-audiences.md).

1. En el cuarto paso del asistente de creación, defina las opciones de variante. Si la [plantilla multilingüe](../../channels/using/multilingual-messages-template.md) ya contiene todos los parámetros correctos, puede hacer clic directamente en el botón **[!UICONTROL Create]**.

   ![](assets/multi_create4.png)

   Si es necesario, agregue variantes con el botón **[!UICONTROL Add an element]**. La variante **[!UICONTROL Default]** no se debe eliminar. Cuando se establece en **[!UICONTROL default]**, [el idioma preferido del perfil](../../audiences/using/creating-profiles.md) se usa para elegir la variante. También puede establecer la variante **[!UICONTROL Default]** en cualquier otro idioma.

1. Confirme la creación del correo electrónico: a continuación, se muestra el panel de correo electrónico.
1. Defina el contenido del correo electrónico para cada variante. En función de la plantilla que haya elegido, puede definir varios asuntos, varios nombres de remitente o varios contenidos diferentes. Utilice el menú desplegable para desplazarse entre las distintas variantes del elemento. Para obtener más información, consulte la sección del [editor de contenido](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Prueba y validación del mensaje. Consulte la sección [Envío de prueba](../../sending/using/sending-proofs.md).
1. Programe el envío con **[!UICONTROL Send after confirmation option]**.
1. Una vez enviado el correo electrónico, puede acceder a sus registros e informes para medir el éxito de la campaña. Para obtener más información sobre la creación de informes, consulte [esta sección](../../reporting/using/about-dynamic-reports.md).

