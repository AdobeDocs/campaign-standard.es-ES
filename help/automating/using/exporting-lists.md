---
title: Exportación de listas
seo-title: Exportación de listas
description: Exportación de listas
seo-description: 'Adobe Campaign permite exportar los datos mostrados como listas desde una pantalla de información general directamente en un archivo para usarlos en el futuro. '
page-status-flag: no activado nunca
uuid: c 64 fe 706-bd 6 e -4746-958 e-f 94226 f 4 e 2 cb
contentOwner: sauviat
products: SG_ CAMPAIGN/STANDARD
audience: automatizar
content-type: reference
topic-tags: importar y exportar datos
discoiquuid: 12 c 874 da -435 f -44 b 6-a 3 c 8-873301 e 177 cc
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 36727e82d3aa73add6116fa2916752ff0e407d9d

---


# Exporting lists{#exporting-lists}

Adobe Campaign permite exportar las listas directamente en un archivo para usarlas en el futuro. Exporting a list in a file generates a log entry in the **[!UICONTROL Export audits]** menu. For more information on export audits, refer to the [Auditing exports](../../administration/using/auditing-export-logs.md) section.

The export list option allows you to export a maximum of 100,000 lines by default and defined by the **Nms_ExportListLimit** option. This option can be managed by the functional administrator, under the **[!UICONTROL Administration]** &gt; **[!UICONTROL Application settings]** &gt; **[!UICONTROL Options]** menu.

Export list is available in all the screens that have a **List** mode view, for users with the **[!UICONTROL EXPORT (export)]** role.

1. Go to your chosen **List** screen. For example, the test profile overview screen ( **[!UICONTROL Profiles & audiences]** &gt; **[!UICONTROL Test profiles]** ).
1. Check that the screen is in **List** mode.

   ![](assets/export_list_mode_switch.png)

1. Organize the columns in the list in the order that you want to export them using the **[!UICONTROL Configure list]** button, in the top right corner. Además de las columnas configuradas, también se exportará la clave principal del recurso.
1. Si lo desea, puede aplicar un filtro. Para ello, haga clic en el botón situado en la esquina superior izquierda para mostrar el panel de búsqueda.

   Si realiza una exportación de una lista que contiene diferentes recursos, debe aplicar los filtros para que solo aparezca un tipo de recurso en la lista.

1. Si lo desea, ordene las columnas elegidas.
1. Select the export button ![](assets/exportlistbutton.png).

   Aparecerá una ventana emergente para confirmar la exportación. Una vez que haya confirmado la exportación, el archivo se descarga automáticamente en el equipo.

El archivo se genera en formato CSV, a menos que la exportación se realice en iOS, en cuyo caso el archivo generado está en formato TXT. Recibe el nombre según el recurso exportado y la fecha de exportación. Por ejemplo: el nombre profilebase_ 20150426_ 120253. csv se aplicaría a una exportación de perfiles llevada a cabo el 26 de abril de 2015 a las 12:02:53. Se codifica en formato UTF -8.

Los valores numéricos y las fechas tienen en cuenta la hora local (configuración regional) del usuario que realiza la exportación. Por ejemplo: DD-MM-AAAA o MM-DD-AAAA.

Para realizar una exportación más grande que esto, debe crear un flujo de trabajo dedicado. Refer to the [Extract file](../../automating/using/extract-file.md) section.

**Ejemplo**

El siguiente ejemplo es una exportación realizada de la lista de perfiles definida a continuación:

* Columnas mostradas (en orden): Apellidos, Nombre, Fecha de nacimiento, Dirección de correo electrónico.
* Los nombres se ordenan ordenados alfabéticamente.

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
* [Configuración de vídeo de lista](https://helpx.adobe.com/campaign/kt/acs/using/acs-configuring-a-list-feature-video-setup.html)

