---
title: Perfil de cliente integrado
description: 'Rastree la interacción de cada cliente en una sola vista: el perfil de cliente integrado de Adobe Campaign se actualiza durante todo el ciclo de vida del cliente.'
audience: audiences
content-type: reference
topic-tags: managing-profiles
context-tags: marketingHistory,main
feature: Profiles
role: User
level: Beginner
exl-id: cf3c6408-7fa0-423a-b34b-f4fee771fb47
TQID: 'https://experienceleague.adobe.com/a-v47cX0DxN6dzLQs-r4e2yMajLD6GHIVXXEX9Ol-lY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: b12f6872-9271-4369-85e5-86969a0b99a2
    internal-label: APIs
  - id: afa4204e-6d08-4e29-bc35-26aafb656d48
    internal-label: Profiles and audiences
subfeature_v2:
  - id: f529d0bd-1401-4c88-9833-43228cc1d40f
    internal-label: Profiles
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
level_v2:
  - id: e8ccd51f-da0d-4e3b-939b-e30d5ebb1ea5
    internal-label: Beginner
topic_v2:
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 41%
---
# Perfil de cliente integrado{#integrated-customer-profile}

Hay disponible un perfil de cliente integrado para cada contacto de la base de datos. Este historial de marketing combina toda la información de comercialización relevante relativa al contacto con un cliente en una sola vista. A continuación, puede acceder a todos los comportamientos digitales, transacciones en línea y sin conexión en una ubicación central: información de contacto, correos electrónicos recibidos, registros de seguimiento, suscripciones y cancelaciones de suscripciones, etc.

Para acceder al perfil integrado del cliente, siga estos pasos:

1. En la página de inicio de Adobe Campaign, haga clic en la tarjeta **[!UICONTROL Customer profiles]** o en la ficha **Perfiles** para mostrar la lista de perfiles.

1. Para buscar un perfil basado en un campo específico, abra el panel de búsqueda y, a continuación, seleccione el campo en el que desea realizar la búsqueda.


   ![](assets/profile-search.png)

1. Especifique el valor que desea buscar y, a continuación, pulse Intro.

   >[!NOTE]
   >
   >Tenga en cuenta que las búsquedas se pueden realizar en función de los campos de correo electrónico, nombre y apellidos, así como de los campos personalizados que se han añadido al ampliar el recurso.
   >
   >Las búsquedas distinguen entre mayúsculas y minúsculas y solo se realizan en prefijos. Por ejemplo, no podrá buscar un perfil con las últimas letras de su apellido.

1. Seleccione un contacto para abrir su perfil.

   ![](assets/mkt_hist_access.png)

Luego puede acceder al **historial de marketing** de este contacto.

La información clave sobre el perfil se recopila en esta página, así como la lista de eventos.

Haga clic en un evento de la lista para abrirlo: puede acceder a los mensajes que se han enviado o a los servicios a los que se ha suscrito el perfil.

![](assets/mkt_hist_view.png)

>[!NOTE]
>
>También se puede acceder a historial de marketing mediante la API de Adobe Campaign Standard. Para obtener más información, consulte la [documentación específica](../../api/using/interacting-with-marketing-history.md).
