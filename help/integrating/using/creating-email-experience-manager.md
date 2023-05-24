---
title: Creación de contenido de correo electrónico en Adobe Experience Manager.
description: Con la integración de Adobe Experience Manager AEM Adobe Campaign, puede crear contenido directamente en y usarlo más adelante en.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 72b99864-d9d9-4cf4-be06-dc5719a2e4f2
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 16%

---

# Importación de contenido de Adobe Experience Manager en un correo electrónico de Adobe Campaign {#creating-email-aem}

Con este documento, aprenderá a crear y administrar el contenido del correo electrónico en Adobe Experience Manager y, a continuación, a utilizarlo para sus campañas de marketing importándolo en sus correos electrónicos en Adobe Campaign Standard.

Los requisitos previos son:

* AEM Acceso a una instancia de configurada para la integración.
* Acceso a una instancia de Adobe Campaign configurada para la integración.
* Una plantilla de correo electrónico de Adobe Campaign AEM configurada para recibir contenido de.

## Acceso a correos electrónicos en Adobe Experience Manager {#email-content-aem}

Inicie sesión en la instancia de creación de Adobe Experience Manager y explore el sitio para acceder a la carpeta que contiene el contenido del correo electrónico.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Crear nuevo contenido de correo electrónico en Adobe Experience Manager {#creating-email-content-aem}

Hay disponibles varias plantillas específicas de Adobe Campaign. Debe utilizar una de estas plantillas, ya que contienen componentes predefinidos compatibles con Adobe Campaign.

De forma predeterminada, dos plantillas predefinidas le permiten crear contenido de correo electrónico para Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**: esta plantilla contiene un contenido estándar que puede personalizar. Puede elegir entre Correo electrónico de Adobe Campaign (AC6.1) y Correo electrónico de Adobe Campaign (ACS).
* **[!UICONTROL Importer Page]**: esta plantilla permite importar un archivo ZIP que contiene un archivo de HTML con contenido que luego se puede personalizar.

1. En Adobe Experience Manager, cree un nuevo **[!UICONTROL Page]**.

1. Seleccione el **[!UICONTROL Adobe Campaign Email]** plantilla. Consulte el siguiente vídeo para ver los pasos detallados.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Abra el nuevo contenido del correo electrónico.

1. En el **[!UICONTROL Page properties]**, configurado **[!UICONTROL Adobe Campaign]** como el **[!UICONTROL Cloud Service Configuration]**. Esto permite la comunicación entre el contenido y la instancia de Adobe Campaign.

   Para obtener más información, vea el siguiente vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Edición y envío de un correo electrónico {#editing-email-aem}

Puede editar el contenido del correo electrónico añadiendo componentes y recursos. Los campos personalizados se pueden utilizar para enviar un mensaje más relevante basado en los datos de los destinatarios en Adobe Campaign.

Para crear contenido de correo electrónico en Adobe Experience Manager:

1. Edite el asunto y la variable **[!UICONTROL Plain text]** versión del correo electrónico accediendo a la **[!UICONTROL Page properties]** > **[!UICONTROL Email]** Ficha de la barra de tareas.

1. Añadir **[!UICONTROL Personalization fields]** a través de **[!UICONTROL Text & Personalization]** componente. Cada componente corresponde a un uso específico: inserción de imágenes, adición de personalización, etc.

   Para obtener más información, vea el siguiente vídeo:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. Desde el **[!UICONTROL Workflow]** , seleccione la pestaña **[!UICONTROL Approve for Adobe Campaign]** flujo de trabajo de validación. No puede enviar un correo electrónico en Adobe Campaign si utiliza un contenido que no se haya aprobado.

1. Una vez definidos el contenido y los parámetros de envío, puede continuar con la aprobación, preparación y envío del correo electrónico en Adobe Campaign Standard.

   Para obtener más información, vea el siguiente vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
