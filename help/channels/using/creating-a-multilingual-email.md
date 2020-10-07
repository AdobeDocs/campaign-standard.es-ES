---
title: Creación de un correo electrónico multilingüe
description: Siga estos pasos para crear destinatarios de segmentación por correo electrónico multilingües con diferentes idiomas preferidos.
page-status-flag: never-activated
uuid: e90f4ec8-14e3-4304-b5fc-bce0ba08a4ef
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: channels
content-type: reference
topic-tags: email-messages
discoiquuid: 79231445-1d51-499a-adcf-0c0f6db1cfa3
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '292'
ht-degree: 25%

---


# Creación de un correo electrónico multilingüe{#creating-a-multilingual-email}

Puede enviar un correo electrónico multilingüe a perfiles con diferentes idiomas preferidos: cada perfil recibirá una variante del correo electrónico en su idioma preferido.

Para ello, compruebe que dispone de una plantilla de correo electrónico multilingüe. Si no es así, aprenda a crear uno en [esta sección](../../channels/using/multilingual-messages-template.md).

La audiencia se basa en perfiles con una información lingüística preferida completa.

1. Cree un nuevo correo electrónico basado en una plantilla [](../../channels/using/multilingual-messages-template.md)multilingüe.

   ![](assets/multi_create1.png)

1. Defina las propiedades generales y la audiencia de destino del mensaje de correo electrónico, igual que para un correo electrónico estándar. Consulte la sección [Creación de audiencias](../../audiences/using/creating-audiences.md).
1. En el cuarto paso del asistente de creación, defina las opciones de variante. Si la plantilla [](../../channels/using/multilingual-messages-template.md) multilingüe ya contiene todos los parámetros correctos, puede hacer clic directamente en el **[!UICONTROL Create]** botón.

   ![](assets/multi_create4.png)

   Si es necesario, agregue variantes con el **[!UICONTROL Add an element]** botón. **[!UICONTROL Default]** no debe eliminarse la variante. Cuando se establece en **[!UICONTROL default]**, se utiliza [el idioma](../../audiences/using/creating-profiles.md) preferido del perfil para elegir la variante. También puede establecer la **[!UICONTROL Default]** variante en cualquier otro idioma.

1. Confirmar creación de correo electrónico: se mostrará el panel de correo electrónico.
1. Defina el contenido del correo electrónico de cada variante. En función de la plantilla que haya elegido, puede definir varios asuntos, varios nombres de remitente o varios contenidos diferentes. Utilice el menú desplegable para desplazarse entre las distintas variantes del elemento. Para obtener más información, consulte la sección del [editor de contenido](../../designing/using/designing-content-in-adobe-campaign.md).

   ![](assets/multi_selectcontent.png)

1. Pruebe y valide el mensaje. Consulte la sección [Enviar prueba](../../sending/using/sending-proofs.md) .
1. Programe el envío con el **[!UICONTROL Send after confirmation option]**.
1. Una vez enviado el correo electrónico, puede acceder a sus registros e informes para medir el éxito de la campaña. Para obtener más información sobre la creación de informes, consulte [esta sección](../../reporting/using/about-dynamic-reports.md).

**Temas relacionados:**

* [Alcance de audiencias multilingües mediante un flujo de trabajo](https://helpx.adobe.com/es/campaign/kb/simplify-campaign-management.html#Engageyourcustomersateverystep)
