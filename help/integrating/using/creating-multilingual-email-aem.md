---
title: Creación de un correo electrónico multilingüe con la integración de Adobe Experience Manager.
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 12%

---

# Creación de un correo electrónico multilingüe con la integración de Adobe Experience Manager {#creating-multilingual-email-aem}

Con este documento, aprenderá a crear un correo electrónico multilingüe con contenido de Adobe Experience Manager y copias de idioma.

Los requisitos previos son:

* Acceso a una instancia de AEM configurada para la integración.
* Acceso a una instancia de Adobe Campaign configurada para la integración.
* Plantilla de correo electrónico multilingüe de Adobe Campaign configurada para recibir contenido de AEM.

## Crear nuevo contenido de correo electrónico en Adobe Experience Manager {#creating-email-content-aem}

1. En la página de inicio de Adobe Experience Manager, seleccione **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Seleccione en qué carpeta desea crear su página, haga clic en **[!UICONTROL Create]** y luego en **[!UICONTROL Page]**. Aquí creamos nuestra página en la carpeta en_us, que será nuestro idioma predeterminado.

   ![](assets/aem_acs_2.png)

1. Seleccione la plantilla **[!UICONTROL Adobe Campaign Email (ACS)]**.

1. Complete las propiedades del correo electrónico y haga clic en **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Abra el nuevo contenido del correo electrónico y personalícelo según sea necesario. Para obtener más información, consulte esta [página](../../integrating/using/creating-email-experience-manager.md#editing-email-aem).

   ![](assets/aem_acs_4.png)

1. En la ficha **[!UICONTROL Workflow]**, seleccione el flujo de trabajo de validación **[!UICONTROL Approve for Adobe Campaign]**. No puede enviar un correo electrónico en Adobe Campaign si utiliza un contenido que no se haya aprobado.

   ![](assets/aem_acs_7.png)

1. Haga clic en **[!UICONTROL Complete]** y luego en **[!UICONTROL Newsletter review]** desde la ventana de **[!UICONTROL Complete work item]**.

1. Haga clic en **[!UICONTROL Complete]**, luego en **[!UICONTROL Newsletter approval]**. Una vez definidos el contenido y los parámetros de envío, puede continuar con la aprobación, preparación y envío del correo electrónico en Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Creación de copias de idioma {#creating-language-copies}

Después de diseñar el contenido del correo electrónico, ahora debe crear las copias de idioma que se sincronizarán con Adobe Campaign Standard como variantes.

1. Seleccione la página creada anteriormente, haga clic en **[!UICONTROL Create]** y luego en **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Seleccione el contenido de correo electrónico creado anteriormente que se traducirá a los idiomas elegidos y, a continuación, haga clic en **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. En la lista desplegable **[!UICONTROL Target language(s)]**, seleccione en qué idioma se traducirá el contenido y haga clic en **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Haga clic en **[!UICONTROL Create]**.

Se han creado las copias de idioma y ahora puede editar el contenido en función del idioma elegido.

>[!CAUTION]
>
>Cada copia de idioma debe aprobarse mediante el flujo de trabajo de validación **[!UICONTROL Approve for Adobe Campaign]**. No puede enviar un correo electrónico en Adobe Campaign si utiliza un contenido que no se haya aprobado.

![](assets/aem_acs_11.png)

## Creación de contenido multilingüe en Adobe Campaign Standard {#multilingual-acs}

1. En la página de inicio de Adobe Campaign Standard, haga clic en **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. Seleccione la plantilla de correo electrónico multilingüe de Adobe Campaign configurada para recibir contenido de Adobe Experience Manager. Para obtener más información sobre cómo crear una plantilla vinculada a su instancia de Adobe Experience Manager, consulte esta [página](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >En este caso, deberá duplicar la plantilla integrada **[!UICONTROL Multilingual email (mailMultiLang)]** para poder enviar su correo electrónico multilingüe.

   ![](assets/aem_acs_13.png)

1. Complete **[!UICONTROL Properties]** y **[!UICONTROL Audience]** de su correo electrónico y haga clic en **[!UICONTROL Create]**.

1. En **[!UICONTROL Edit properties]**, asegúrese de que su cuenta de Adobe Experience Manager esté configurada correctamente en la lista desplegable **[!UICONTROL Content]**.

   ![](assets/aem_acs_20.png)

1. Haga clic en **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Seleccione el contenido de Adobe Experience Manager que creó anteriormente y haga clic en **[!UICONTROL Confirm]**. El contenido de Adobe Experience Manager que se muestra aquí solo es contenido validado y se puede filtrar por sus **[!UICONTROL Label]** y **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >La copia de idioma elegida se establecerá como predeterminada; puede cambiarla más adelante en el bloque **[!UICONTROL Content variant]**.

   ![](assets/aem_acs_17.png)

1. Haga clic en **[!UICONTROL Create variants]** para vincular el contenido multilingüe. A continuación, Adobe Campaign Standard vinculará automáticamente las copias de otros idiomas a este contenido. Las variantes creadas tendrán el mismo idioma de etiqueta y código que las elegidas en Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Haga clic en el bloque **[!UICONTROL Content variant]** para cambiar la variante predeterminada si es necesario y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Si el contenido o las variantes se actualizan en Adobe Experience Manager, puede sincronizarlos directamente en Adobe Campaign Standard con el botón **[!UICONTROL Refresh AEM contents]**.

1. El correo electrónico está listo para enviarse. Para obtener más información, consulte esta [página](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >No podrá enviar un correo electrónico en Adobe Campaign si utiliza un contenido de AEM que no se haya aprobado.

Su audiencia recibirá su correo electrónico según el conjunto de **[!UICONTROL Preferred languages]** en su **[!UICONTROL Profiles]**. Para obtener más información sobre cómo editar perfiles e idiomas preferidos, consulte esta [página](../../audiences/using/editing-profiles.md).
