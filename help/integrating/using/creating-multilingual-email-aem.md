---
title: Creación de un correo electrónico multilingüe con la integración de Adobe Experience Manager.
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 0f66fe2b-22b1-49d7-a080-29b00941a2cc
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 15%

---

# Creación de un correo electrónico multilingüe con la integración de Adobe Experience Manager {#creating-multilingual-email-aem}

Con este documento, aprenderá a crear un correo electrónico multilingüe con contenido de Adobe Experience Manager y copias de idioma.

Los requisitos previos son:

* Acceso a una instancia de AEM configurada para la integración.
* Acceso a una instancia de Adobe Campaign configurada para la integración.
* Una plantilla de correo electrónico multilingüe de Adobe Campaign configurada para recibir AEM contenido.

## Crear nuevo contenido de correo electrónico en Adobe Experience Manager {#creating-email-content-aem}

1. En la página de inicio de Adobe Experience Manager, seleccione **[!UICONTROL Site]**.

   ![](assets/aem_acs_1.png)

1. Seleccione en qué carpeta desea crear la página y haga clic en **[!UICONTROL Create]** y luego en **[!UICONTROL Page]**. Aquí, creamos nuestra página en la carpeta en_us , que será nuestro idioma predeterminado.

   ![](assets/aem_acs_2.png)

1. Seleccione la plantilla **[!UICONTROL Adobe Campaign Email (ACS)]** .

1. Complete las propiedades del correo electrónico y haga clic en **[!UICONTROL Create]**.

   ![](assets/aem_acs_3.png)

1. Abra el nuevo contenido del correo electrónico y personalícelo según sea necesario. Para obtener más información, consulte esta [página](../../integrating/using/creating-email-experience-manager.md#editing-email-aem).

   ![](assets/aem_acs_4.png)

1. En la pestaña **[!UICONTROL Workflow]** , seleccione el flujo de trabajo de validación **[!UICONTROL Approve for Adobe Campaign]** . No puede enviar un correo electrónico en Adobe Campaign si utiliza un contenido que no se haya aprobado.

   ![](assets/aem_acs_7.png)

1. Haga clic en **[!UICONTROL Complete]** y luego en **[!UICONTROL Newsletter review]** en la ventana **[!UICONTROL Complete work item]**.

1. Haga clic en **[!UICONTROL Complete]**, luego en **[!UICONTROL Newsletter approval]**. Una vez definidos los parámetros de contenido y envío, puede proceder a la aprobación, preparación y envío del correo electrónico en Adobe Campaign Standard.

   ![](assets/aem_acs_8.png)

## Creación de copias de idioma {#creating-language-copies}

Después de diseñar el contenido del correo electrónico, debe crear las copias de idioma que se sincronizarán con Adobe Campaign Standard como variantes.

1. Seleccione la página creada anteriormente, haga clic en **[!UICONTROL Create]** y luego en **[!UICONTROL Language Copy]**.

   ![](assets/aem_acs_5.png)

1. Seleccione el contenido de correo electrónico creado anteriormente que se traducirá a los idiomas elegidos y haga clic en **[!UICONTROL Next]**.

   ![](assets/aem_acs_6.png)

1. En la lista desplegable **[!UICONTROL Target language(s)]**, seleccione en qué idioma se traducirá el contenido y haga clic en **[!UICONTROL Next]**.

   ![](assets/aem_acs_9.png)

1. Haga clic en **[!UICONTROL Create]**.

Se han creado las copias de idioma, ahora puede editar el contenido en función del idioma elegido.

>[!CAUTION]
>
>Cada copia de idioma debe aprobarse mediante el flujo de trabajo de validación **[!UICONTROL Approve for Adobe Campaign]** . No puede enviar un correo electrónico en Adobe Campaign si utiliza un contenido que no se haya aprobado.

![](assets/aem_acs_11.png)

## Creación de contenido multilingüe en Adobe Campaign Standard {#multilingual-acs}

1. En la página de inicio de Adobe Campaign Standard, haga clic en **[!UICONTROL Create an email]**.

   ![](assets/aem_acs_12.png)

1. Seleccione la plantilla de correo electrónico multilingüe de Adobe Campaign configurada para recibir contenido de Adobe Experience Manager. Para obtener más información sobre cómo crear una plantilla vinculada a su instancia de Adobe Experience Manager, consulte esta [página](../../integrating/using/configure-experience-manager.md#config-acs).

   >[!NOTE]
   >
   >En este caso, deberá duplicar la plantilla integrada **[!UICONTROL Multilingual email (mailMultiLang)]** para poder enviar el correo electrónico multilingüe.

   ![](assets/aem_acs_13.png)

1. Rellene los campos **[!UICONTROL Properties]** y **[!UICONTROL Audience]** del correo electrónico y haga clic en **[!UICONTROL Create]**.

1. En **[!UICONTROL Edit properties]**, asegúrese de que la cuenta de Adobe Experience Manager esté correctamente configurada en la lista desplegable **[!UICONTROL Content]**.

   ![](assets/aem_acs_20.png)

1. Haga clic en **[!UICONTROL Language copy creation]**.

   ![](assets/aem_acs_16.png)

1. Seleccione el contenido de Adobe Experience Manager creado anteriormente y haga clic en **[!UICONTROL Confirm]**. El contenido de Adobe Experience Manager mostrado aquí solo es contenido validado y puede filtrarse en sus **[!UICONTROL Label]** y **[!UICONTROL Path]**.

   >[!NOTE]
   >
   >La copia de idioma elegida se establecerá como predeterminada; más adelante, puede cambiarla en el bloque **[!UICONTROL Content variant]** .

   ![](assets/aem_acs_17.png)

1. Haga clic en **[!UICONTROL Create variants]** para vincular el contenido multilingüe. Adobe Campaign Standard vinculará automáticamente las copias en otros idiomas a este contenido. Las variantes creadas tendrán la misma etiqueta y el mismo lenguaje de código que las seleccionadas en Adobe Experience Manager.

   ![](assets/aem_acs_18.png)

1. Haga clic en el bloque **[!UICONTROL Content variant]** para cambiar la variante predeterminada si es necesario y haga clic en **[!UICONTROL Confirm]**.

   ![](assets/aem_acs_19.png)

1. Si el contenido o las variantes se actualizan en Adobe Experience Manager, puede sincronizarlo directamente en Adobe Campaign Standard con el botón **[!UICONTROL Refresh AEM contents]**.

1. El correo electrónico ya está listo para enviarse. Para obtener más información, consulte esta [página](../../sending/using/get-started-sending-messages.md).

   >[!NOTE]
   >
   >No podrá enviar un correo electrónico en Adobe Campaign si utiliza un contenido AEM que no se haya aprobado.

Su audiencia recibirá su correo electrónico según el **[!UICONTROL Preferred languages]** configurado en su **[!UICONTROL Profiles]**. Para obtener más información sobre cómo editar perfiles y idiomas preferidos, consulte esta [página](../../audiences/using/editing-profiles.md).
