---
title: Obtenga acceso a la integración de Adobe Campaign Standard con la aplicación de autoservicio de Dynamics 365
description: Integración de Adobe Campaign Standard con la aplicación de autoservicio de Dynamics 365
products: SG_CAMPAIGN/STANDARD
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-microsoft-dynamics-365
feature: Microsoft CRM Integration
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 44b59f56-99be-41ae-af8d-76272bb94d18
TQID: 'https://experienceleague.adobe.com/eSWqj-qyCQkrDNHl-7Pc6It5oBFHSBNG3-F0aoNiRYY'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: d5ef99fa-df0c-4153-bf94-105ad0724167
    internal-label: Integrations
subfeature_v2:
  - id: dd99420f-367d-4a14-bbc4-5140615992c2
    internal-label: Microsoft CRM integration
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
    internal-label: Intermediate
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 2%
---
# Acceso a la integración de Adobe Campaign Standard con la aplicación de autoservicio de Microsoft Dynamics 365

Esta configuración requiere que trabaje con un administrador de Experience Cloud (EC) para su organización. Estos son los pasos iniciales necesarios para darle acceso a la interfaz de la aplicación de integración de autoservicio. Una vez que tenga acceso a la herramienta, configurará las conexiones a los datos y el flujo de datos entre Adobe Campaign y Microsoft Dynamics 365.

>[!NOTE]
>
>Debe ponerse en contacto con su representante de Adobe y proporcionar la organización de Adobe Campaign Standard y los nombres de instancia. Se registrará un ticket para solicitar que la aplicación de integración esté habilitada para su organización.

## Añadir un perfil de producto

En esta sección aprenderá a conceder acceso a la integración de Adobe Campaign Standard con la aplicación de autoservicio de Microsoft Dynamics 365. Los usuarios que tengan acceso a su organización en Adobe Experience Cloud no tendrán acceso a la aplicación de autoservicio de integración, a menos que siga los pasos a continuación para concederles acceso.

>[!IMPORTANT]
>
> Estos pasos requieren la función **Administrator** en Experience Cloud para su organización.
>

1. Vaya a https://experience.adobe.com/ e inicie sesión en Adobe Experience Cloud.
1. Acceder a **Admin Console**.

   ![](assets/do-not-localize/d365-to-acs-access-3.png)

1. Haga clic en **[!UICONTROL Products]** para acceder a sus soluciones de Experience Cloud.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)


   >[!IMPORTANT]
   >
   >Los pasos restantes de esta sección se realizarán para cada una de las instancias de Campaign (desarrollo, texto, producción).
   >

1. Haga clic en la primera instancia para configurarla.

   ![](assets/do-not-localize/d365-to-acs-access-6.png)

   La página de instancia debe tener un aspecto similar al siguiente:

   ![](assets/do-not-localize/d365-to-acs-access-8.png)

1. Haga clic en el botón **[!UICONTROL New Profile]** y agregue una nueva entrada denominada: **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   * Si ve esta entrada en la lista, no es necesario que continúe. Haga clic en **Adobe Campaign Standard** en el menú de la izquierda y verifique las otras instancias de Campaign.

   * Asegúrese de reemplazar &quot;your-prod-instance-name&quot; con el nombre real de la instancia.

1. Puede dejar la lista desplegable **[!UICONTROL Permission Group]** con el valor predeterminado.

1. Si sus entradas tienen un aspecto similar al siguiente, haga clic en el botón **[!UICONTROL Done]**.

   ![](assets/do-not-localize/d365-to-acs-access-14.png)

   Se ha añadido el nuevo perfil de producto.

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

## Concesión del acceso a los usuarios {#add-users-to-profile}

En la página **[!UICONTROL Products]**, seleccione la instancia de Campaign y siga los pasos a continuación:

1. Haga clic en el nuevo perfil que creó anteriormente: **Campaign Standard - your-prod-instance-name - D365/ACS Integration**

   ![](assets/do-not-localize/d365-to-acs-access-15.png)

1. Haga clic en la pestaña **[!UICONTROL Developers]**.

   ![](assets/do-not-localize/d365-to-acs-access-18.png)

1. Haga clic en el botón **[!UICONTROL Add Developer]**

1. Introduzca el nombre o la dirección de correo electrónico del usuario que desea agregar.  Seleccione el resultado que coincida con el usuario.

   Si es la primera vez que se añade un usuario a la organización, introduzca los detalles.

1. Haga clic en **[!UICONTROL Save]** para confirmar.
