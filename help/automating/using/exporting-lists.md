---
solution: Campaign Standard
product: campaign
title: Exportación de listas
description: 'Adobe Campaign permite exportar los datos mostrados como listas desde una pantalla de información general directamente en un archivo para su uso futuro. '
audience: automating
content-type: reference
topic-tags: importing-and-exporting-data
translation-type: tm+mt
source-git-commit: 501f52624ce253eb7b0d36d908ac8502cf1d3b48
workflow-type: tm+mt
source-wordcount: '423'
ht-degree: 5%

---


# Exportación de listas{#exporting-lists}

Adobe Campaign le permite exportar sus listas directamente en un archivo para su uso futuro. Exportar una lista en un archivo genera una entrada de registro en el **[!UICONTROL Export audits]** menú. Para obtener más información sobre las auditorías de exportación, consulte la sección [Auditoría de exportaciones](../../administration/using/auditing-export-logs.md).

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Options]** menu.

La lista de exportación está disponible en todas las pantallas que tienen una vista de modo de **Lista** para los usuarios con la **[!UICONTROL EXPORT (export)]** función.

1. Vaya a la pantalla de **Lista** seleccionada. Por ejemplo, la pantalla de información general del perfil de prueba ( **[!UICONTROL Profiles & audiences]** > **[!UICONTROL Test profiles]** ).
1. Compruebe que la pantalla está en modo de **Lista** .

   ![](assets/export_list_mode_switch.png)

1. Organice las columnas de la lista en el orden en que desee exportarlas con el **[!UICONTROL Configure list]** botón situado en la esquina superior derecha. Además de las columnas configuradas, también se exportará la clave principal del recurso.
1. Si lo desea, puede aplicar un filtro. Para ello, haga clic en el botón de la esquina superior izquierda para mostrar el panel de búsqueda.

   Si realiza una exportación desde una lista que contiene distintos recursos, debe aplicar sus filtros para que solo se muestre un tipo de recurso en la lista.

1. Si lo desea, ordene las columnas seleccionadas.
1. Seleccione el botón de exportación ![](assets/exportlistbutton.png).

   Aparecerá una ventana emergente para confirmar la exportación. Una vez confirmada la exportación, el archivo se descarga automáticamente en el equipo.

El archivo se genera en formato CSV con la extensión .TXT. Su nombre depende del recurso exportado y de la fecha de exportación. Por ejemplo: el nombre profileBase_20150426_120253.txt se aplicaría a una exportación de perfil realizada el 26 de abril de 2015 a las 12:02:53. Está codificado en formato UTF-8.

Los valores numéricos y las fechas tienen en cuenta la hora local (configuración regional) del usuario que realiza la exportación. Por ejemplo: DD-MM-AAAA o MM-DD-AAAA.

Para llevar a cabo una exportación que sea mayor que ésta, debe crear un flujo de trabajo dedicado. Refer to the [Extract file](../../automating/using/extract-file.md) section.

**Ejemplo**

El ejemplo siguiente es una exportación realizada desde la lista de perfil definida a continuación:

* Columnas mostradas (en orden): Apellido, Nombre, Fecha de nacimiento, Dirección de correo electrónico.
* Los nombres se ordenan en orden alfabético.

![](assets/export_list_example1.png)

El archivo generado se presenta de la siguiente manera (para los diez primeros registros):

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
* [Configuración del vídeo de lista](https://docs.adobe.com/content/help/en/campaign-learn/campaign-standard-tutorials/getting-started/configure-a-list.html)
