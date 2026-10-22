---
title: Exportación de listas
description: Adobe Campaign permite exportar los datos mostrados como listas desde una pantalla de información general directamente en un archivo para su uso futuro.
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
feature: Workflows
old-role: Data Architect
role: Developer
level: Experienced
exl-id: b39ce1f6-0c5b-4270-86a1-b79c49cd199c
TQID: 'https://experienceleague.adobe.com/a-H7FC1xbixlkhdkCM4cxk7S9Hd3r3e2nD9pMOCHKuk'
product_v2:
  - id: dfc56824-e8b9-499e-85d4-21aedb507314
    internal-label: Campaign
  - id: f5407121-8933-4ac3-8e06-a9b692a4e88a
    internal-label: Campaign Standard
feature_v2:
  - id: a658c786-869b-4194-a780-2594d663adda
    internal-label: Data management
subfeature_v2:
  - id: fcb46c0f-76e1-48bc-9dd0-fcf9d97526cf
    internal-label: Workflows
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
topic_v2:
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: bb37e2bfbc52de1b0cc03f0f8e03985caff5e5b0
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 7%
---
# Exportación de listas{#exporting-lists}

Adobe Campaign le permite exportar las listas directamente en un archivo para uso futuro. Exportar una lista en un archivo genera una entrada de registro en el menú **[!UICONTROL Export audits]**. Para obtener más información sobre las auditorías de exportación, consulte la sección [Auditoría de exportaciones](../../administration/using/auditing-export-logs.md).

![](assets/do-not-localize/how-to-video.png) [Descubra cómo configurar una lista en vídeo](#video)

La opción de lista de exportación le permite exportar un máximo de 100 000 líneas de forma predeterminada y definida por la opción **Nms_ExportListLimit**. El administrador funcional puede administrar esta opción en el menú **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]**.

La lista de exportación está disponible en todas las pantallas que tienen una vista de modo **List** para los usuarios con el rol **[!UICONTROL EXPORT (export)]**.

1. Vaya a la pantalla **List** que haya elegido. Por ejemplo, la pantalla de información general del perfil de prueba ( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** ).
1. Compruebe que la pantalla esté en modo **List**.

   ![](assets/export_list_mode_switch.png)

1. Organice las columnas de la lista en el orden en que desee exportarlas con el botón **[!UICONTROL Configure list]**, en la esquina superior derecha. Además de las columnas configuradas, también se exporta la clave principal del recurso.
1. Si lo desea, puede aplicar un filtro. Para ello, haga clic en el botón en la esquina superior izquierda para mostrar el panel de búsqueda.

   Si realiza una exportación desde una lista que contiene diferentes recursos, debe aplicar los filtros para que solo se muestre un tipo de recurso en la lista.

1. Si lo desea, ordene las columnas seleccionadas.
1. Seleccione el botón de exportación ![](assets/exportlistbutton.png).

   Aparecerá una ventana emergente para confirmar la exportación. Una vez confirmada la exportación, el archivo se descarga automáticamente en el equipo.

El archivo se genera en formato CSV con una extensión .TXT. Se le asigna un nombre en función del recurso exportado y la fecha de exportación. Por ejemplo: el nombre profileBase_20150426_120253.txt se aplicaría a una exportación de perfiles realizada el 26 de abril de 2015 a las 12:02:53. Se codifica en formato UTF-8.

Los valores numéricos y las fechas tienen en cuenta la hora local (configuración regional) del usuario que realiza la exportación. Por ejemplo: DD-MM-AAAA o DD-MM-AAAA.

Para realizar una exportación de mayor tamaño, debe crear un flujo de trabajo dedicado. Consulte la sección [Extraer archivo](../../automating/using/extract-file.md).

**Ejemplo**

El siguiente ejemplo es una exportación realizada desde la lista de perfiles definida a continuación:

* Columnas mostradas (en orden): Apellido, Nombre, Fecha de nacimiento, Dirección de correo electrónico.
* Los nombres se ordenan en orden alfabético.

![](assets/export_list_example1.png)

El archivo generado se presenta de la siguiente manera (para los primeros diez registros):

```
Last name;First name;Birth date;Email;Zip code
Abalo;Patrick;11/11/1941 02:00:00;patrick.a@testmail.com;29200
Abasq;Joel;21/08/1977 02:00:00;abasq.joel@testmail.com;92160
Abernot;John;12/07/1963 01:00:00;john.abernot@testmail.com;78510
Abiven;Christian;16/03/1975 01:00:00;chris.a@mailtest.com;35000
Abouvier;Peter;02/07/1975 01:00:00;pabouvier@mailtest.com;94560
Accardi;Mike;22/06/1948 01:00:00;mike.accardi@mail.com;76400
Accremont;Frank;27/04/1947 01:00:00;accr.frank@mailtest.com;13500
Adam;Daniel;17/09/1953 01:00:00;danieladam@mail.com;17000
Adama;Pascal;22/01/1990 01:00:00;adapascal@mailtest.com;75012
Adama;Henry;22/09/1992 02:00:00;henry.adama@mail.com;64120
```

**Temas relacionados:**

* [Funciones](../../administration/using/list-of-roles.md)
* [Personalización de listas](../../start/using/customizing-lists.md)

## Tutorial en vídeo {#video}

Este vídeo muestra cómo configurar listas.

>[!VIDEO](https://video.tv.adobe.com/v/25288/?quality=12)

Hay disponibles [más vídeos de procedimientos para Campaign Standard aquí](https://experienceleague.adobe.com/docs/campaign-standard-learn/tutorials/overview.html?lang=es).
