---
title: Creación de contenido de correo electrónico en Adobe Experience Manager.
description: Con la integración de Adobe Experience Manager, puede crear contenido directamente en AEM y utilizarlo posteriormente en Adobe Campaign.
page-status-flag: never-activated
uuid: ed6c1b76-87f7-4d23-b5e2-0765297a905c
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-experience-manager
discoiquuid: 6c0c3c5b-b596-459e-87dd-a06bb7d633d2
translation-type: tm+mt
source-git-commit: 1321c84c49de6d9a318bbc5bb8a0e28b332d2b5d
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 16%

---


# Importación de contenido de Adobe Experience Manager en un correo electrónico de Adobe Campaign {#creating-email-aem}

Con este documento, aprenderá a crear y administrar el contenido del correo electrónico en Adobe Experience Manager y, a continuación, a usarlo para sus campañas de marketing importándolo en sus correos electrónicos a Adobe Campaign Standard.

Los requisitos previos son:

* Acceso a una instancia de AEM configurada para la integración.
* Acceso a una instancia de Adobe Campaign configurada para la integración.
* Plantilla de correo electrónico de Adobe Campaign configurada para recibir contenido AEM.

## Acceso a correos electrónicos en Adobe Experience Manager {#email-content-aem}

Inicie sesión en la instancia de creación de Adobe Experience Manager y navegue por el sitio para acceder a la carpeta que contiene el contenido del correo electrónico.

>[!VIDEO](https://video.tv.adobe.com/v/29996)

## Crear nuevo contenido de correo electrónico en Adobe Experience Manager {#creating-email-content-aem}

Hay disponibles varias plantillas específicas de Adobe Campaign. Debe utilizar una de estas plantillas, ya que contienen componentes predefinidos compatibles con Adobe Campaign.

De forma predeterminada, dos plantillas predefinidas le permiten crear contenido de correo electrónico para Adobe Campaign.

* **[!UICONTROL Adobe Campaign Email]**:: esta plantilla contiene un contenido estándar que puede personalizar. Puede elegir entre Correo electrónico de Adobe Campaign (AC6.1) y Correo electrónico de Adobe Campaign (ACS).
* **[!UICONTROL Importer Page]**:: esta plantilla le permite importar un archivo ZIP que contenga un archivo HTML con contenido que podrá personalizar.

1. En Adobe Experience Manager, cree un nuevo **[!UICONTROL Page]**.

1. Select the **[!UICONTROL Adobe Campaign Email]** template. Consulte el siguiente vídeo para ver los pasos detallados.
   >[!VIDEO](https://video.tv.adobe.com/v/29997)

1. Abra el nuevo contenido del correo electrónico.

1. En el **[!UICONTROL Page properties]**, establezca **[!UICONTROL Adobe Campaign]** como **[!UICONTROL Cloud Service Configuration]**. Esto permite la comunicación entre el contenido y la instancia de Adobe Campaign.

   Para obtener más información, vea el siguiente vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/29999)

## Edición y envío de un correo electrónico {#editing-email-aem}

Puede editar el contenido del correo electrónico agregando componentes y recursos. Se pueden utilizar campos de personalización para enviar un mensaje más relevante en función de los datos de los destinatarios en Adobe Campaign.

Para crear contenido de correo electrónico en Adobe Experience Manager:

1. Edite el asunto y la **[!UICONTROL Plain text]** versión del correo electrónico accediendo a la ficha **[!UICONTROL Page properties]** > **[!UICONTROL Email]** de la barra de tareas.

1. Añada **[!UICONTROL Personalization fields]** a través del **[!UICONTROL Text & Personalization]** componente. Cada componente corresponde a un uso específico: insertar imágenes, agregar personalización, etc.

   Para obtener más información, vea el siguiente vídeo:
   >[!VIDEO](https://video.tv.adobe.com/v/29998)

1. En la **[!UICONTROL Workflow]** ficha, seleccione el flujo de trabajo de **[!UICONTROL Approve for Adobe Campaign]** validación. No puede enviar un correo electrónico en Adobe Campaign si utiliza un contenido que no se haya aprobado.

1. Una vez definidos el contenido y los parámetros de envío, puede proceder a la aprobación, preparación y envío del correo electrónico en Adobe Campaign Standard.

   Para obtener más información, vea el siguiente vídeo:

   >[!VIDEO](https://video.tv.adobe.com/v/23721)
