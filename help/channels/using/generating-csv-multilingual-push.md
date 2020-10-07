---
title: Generación de un archivo CSV para notificaciones push multilingües con Campaign Standard
description: La carga de un archivo CSV para generar contenido para envío es una función que se utiliza para admitir las notificaciones Push multilingües.
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
source-wordcount: '1127'
ht-degree: 0%

---


# Generación de un archivo CSV para notificaciones push multilingües{#generating-csv-multilingual-push}

La carga de un archivo CSV para generar contenido para envío es una función que se utiliza para admitir las notificaciones Push multilingües. El formato del archivo CSV debe atenerse a determinadas directrices para que la carga del archivo sea correcta y, por lo tanto, pueda crear un envío. Las siguientes secciones describen el formato de archivo y sus consideraciones.

## Formato de archivo {#file-format}

La inserción multilingüe requiere 14 columnas en el archivo CSV:

1. título
1. messageBody
1. sonido
1. adge
1. deeplinkURI
1. categoría
1. iosMediaAttachmentURL
1. androidMediaAttachmentURL
1. isContentAvailable
1. isMutableContent
1. customFields
1. locale
1. language
1. silentPush

Compruebe el ejemplo de CSV haciendo clic en el **[!UICONTROL Download a sample file]** en la **[!UICONTROL Manage Content Variants]** ventana. For more on this, refer to the this [section](../../channels/using/creating-a-multilingual-push-notification.md).

* **title, messageBody, sound, badge, deeplinkURI, categoría, iosMediaAttachmentURL, androidMediaAttachmentURL**: contenido de carga útil push regular. Debe proporcionar esta información de una manera similar a cuando se crean envíos push.
* **Campos** personalizados:  utilice el formato JSON para los campos personalizados, p. ej. `{"key1":"value1","key2":"value2"}`. Consulte el archivo de ejemplo anterior para ver un ejemplo de campos personalizados.
* **isContentAvailable**: marca para la comprobación de contenido disponible, el valor 1 implica verdadero, el valor 0 implica falso. El valor predeterminado es 0. Si deja esta columna en blanco, el valor se considerará 0.
* **isMutableContent**: para Contenido mutable, el valor 1 implica verdadero, el valor 0 implica falso. El valor predeterminado es 0. Si deja esta columna en blanco, el valor se considerará 0.
* **configuración regional**: locale es el campo para las variantes de idioma, por ejemplo: &quot;es_es&quot; para EE.UU.-inglés y &quot;fr_fr&quot; para Francia-francés.
* **idioma**: nombre del idioma asociado con la configuración regional. Por ejemplo, si la configuración regional es &quot;en_us&quot;, el nombre del idioma debe ser &quot;Inglés-Estados Unidos&quot;.
* **silentPush**: para el tipo de notificación push. Si es una notificación push regular, el valor debe ser 0. Si es una notificación push silenciosa, el valor debe ser 1. El valor predeterminado es 0. Si deja esta columna en blanco, el valor se considerará 0.

## Restricciones y directrices para la creación del archivo csv {#constraints-guideline-csv}

**El nombre de cada columna es fijo**.
Debe incluir el nombre de cada columna en el archivo CSV, si no utiliza ninguna columna para el contenido, déjela en blanco.

**Las columnas &quot;configuración regional&quot; y &quot;idioma&quot; son obligatorias y el valor es único para cada fila.**
Un valor en blanco para esta columna provocará un error en la carga del archivo.

**El orden de las columnas importa**. El orden de las columnas del archivo cargado debe seguir el mismo formato que el archivo de ejemplo.

**Cita el contenido** de la columna. Dado que se trata de un archivo CSV (es decir, valores separados por comas), se debe citar cualquier contenido de columna que incluya comas (,). Por ejemplo: &quot;¡Hola, Tom!&quot;

**La codificación UTF-8 es necesaria para los caracteres internacionales.**

**Si genera el archivo por texto sin formato, separe cada columna por &quot;,&quot;.**

**Diferencia de variante.** Si utiliza audiencias de bloque de contenido y destinatario con idiomas específicos, deberá realizar la lista de todos los idiomas objetivo en el archivo CSV o se producirá un error al enviar el envío.

## Inserción del campo de personalización en el archivo csv {#personalization-field-csv}

Si desea utilizar campos de personalización, debe incluir <span> etiquetas en el archivo.

Para insertar el campo de personalización &quot;firstName&quot; en messageBody, el mensaje debe ser:

```
 "Hello <span class="nl-dce-field nl-dce-done"  data-nl-expr="/context/profile/firstName">First name</span>, this is message".
```

El campo &quot;firstName&quot; está representado por:

```
 <span class="nl-dce-field nl-dce-done" data-nl-expr="/context/profile/firstName">First name</span>
```

En el lapso hay dos atributos obligatorios:

* Una es la clase que es estática. Independientemente del campo de personalización que planee utilizar, siempre será class=&quot;nl-dce-field nl-dce-done&quot;.

* Otra es data-nl-expr, que es la ruta del campo de personalización. Por ejemplo, si inserta el campo de personalización &quot;firstName&quot; desde la interfaz de usuario, la ruta de navegación será **[!UICONTROL Context (context)]** > **[!UICONTROL Profile (profile)]** > **[!UICONTROL First name (firstName)]** (como se muestra en la imagen siguiente). En este caso, la ruta será

   ```
   /context/profile/firstName. data-nl-expr="/context/profile/firstName".
   ```

![](assets/multilingual_push_2.png)

## Configuración regional y nombres de idioma {#locale-language-names}

Se admiten los siguientes idiomas:

| locale | language |
|:-:|:-:|
| af_za | Afrikaans - Sudáfrica |
| sq_al | Albanés - Albania |
| ar_dz | Árabe (Argelia) |
| ar_bh | Árabe - Bahréin |
| ar_iq | Árabe - Iraq |
| ar_il | Árabe - Israel |
| ar_jo | Árabe - Jordania |
| ar_kw | Árabe - Kuwait |
| ar_lb | Árabe - Líbano |
| ar_ma | Árabe - Marruecos |
| ar_om | Árabe - Omán |
| ar_qa | Árabe - Qatar |
| ar_sa | Árabe - Arabia Saudita |
| ar_sy | Árabe - Siria |
| ar_tn | Árabe - Túnez |
| ar_ae | Árabe (Emiratos Árabes Unidos) |
| ar_ye | Árabe - Yemen |
| hy_am | Armenio - Armenia |
| az_az | Azerí - Azerbaiyán |
| be_by | Bielorrusia - Bielorrusia |
| bs_ba | Bosnio - Bosnia |
| bg_bg | Búlgaro - Bulgaria |
| ca_es | Catalán - España |
| zh_cn | Chino (simplificado) - China |
| zh_sg | Chino (simplificado) - Singapur |
| zh_hk | Chino (tradicional) - RAE de Hong Kong de China |
| zh_tw | Chino (tradicional) - Región de Taiwán |
| hr_hr | Croata - Croacia |
| cs_cz | Checo - Checo |
| da_dk | Danés - Dinamarca |
| nl_be | Holandés - Bélgica |
| nl_nl | Holandés - Países Bajos |
| en_au | Inglés - Australia |
| en_bz | Inglés - Belice |
| en_ca | Inglés - Canadá |
| en_in | Inglés - India |
| en_ie | Inglés - Irlanda |
| en_jm | Inglés - Jamaica |
| en_nz | Inglés - Nueva Zelanda |
| en_ph | Inglés (Filipinas) |
| en_za | Inglés - Sudáfrica |
| en_tt | Inglés - Trinidad y Tobago |
| en_gb | Inglés - Reino Unido |
| en_us | Inglés - Estados Unidos |
| en_zw | Inglés - Zimbabwe |
| et_ee | Estonio - Estonia |
| fi_fi | Finlandés - Finlandia |
| fr_be | Francés - Bélgica |
| fr_ca | Francés - Canadá |
| fr_fr | Francés - Francia |
| fr_lu | Francés - Luxemburgo |
| fr_ch | Francés - Suiza |
| de_at | Alemán - Austria |
| de_de | Alemán - Alemania |
| de_lu | Alemán - Luxemburgo |
| de_ch | Alemán - Suiza |
| el_cy | Griego - Chipre |
| el_gr | Griego - Grecia |
| gu_in | Gujarati (India) |
| he_il | Hebreo - Israel |
| hi_in | Hindi - India |
| hu_hu | Húngaro - Hungría |
| is_is | Islandés - Islandia |
| id_id | Indonesio - Indonesia |
| it_it | Italiano - Italia |
| it_ch | Italiano - Suiza |
| ja_jp | Japonés - Japón |
| kn_in | Kannada - India |
| kk_kz | Kazajistán |
| ko_kr | Coreano - Corea del Sur |
| lv_lv | Letón - Letonia |
| lt_lt | Lituano - Lituania |
| mk_mk | Macedonio - Macedonia |
| ms_my | Malayo - Malasia |
| mr_in | Marathi - India |
| no_no | Noruego - Noruega |
| pl_pl | Polaco - Polonia |
| pt_br | Portugués - Brasil |
| pt_pt | Portugués - Portugal |
| pa_in | Punjabi - India |
| ro_md | Rumano - Moldavia |
| ro_ro | Rumano - Rumania |
| ru_kz | Ruso - Kazajistán |
| ru_ru | Ruso - Rusia |
| ru_ua | Ruso - Ucrania |
| a_in | Sanskrit - India |
| sr_ba | Serbio - Bosnia |
| sr_rs | Serbio - Serbia |
| sk_sk | Eslovaco - Eslovaquia |
| sl_si | Esloveno - Eslovenia |
| es_ar | Español (Argentina) |
| es_bo | Español (Bolivia) |
| es_cl | Español (Chile) |
| es_co | Español (Colombia) |
| es_cr | Español (Costa Rica) |
| es_do | Español (República Dominicana) |
| es_ec | Español (Ecuador) |
| es_sv | Español - El Salvador |
| es_gt | Español (Guatemala) |
| es_hn | Español (Honduras) |
| es_mx | Español (México) |
| es_ni | Español (Nicaragua) |
| es_pa | Español (Panamá) |
| es_py | Español (Paraguay) |
| es_pe | Español (Perú) |
| es_pr | Español - Puerto Rico |
| es_es | Español (España) |
| es_uy | Español (Uruguay) |
| es_ve | Español (Venezuela) |
| sw_ke | Swahili - Kenia |
| sv_fi | Sueco - Finlandia |
| sv_se | Sueco - Suecia |
| ta_in | Tamil - India |
| tt_ru | Tatar - Ruso |
| te_in | Telugu - India |
| th_th | Thai - Tailandia |
| tr_cy | Turco - Chipre |
| tr_tr | Turco - Turquía |
| uk_ua | Ucraniano - Ucraniano |
| ur_in | Urdu - India |
| ur_pk | Urdu - Pakistán |
| vi_vn | Vietnamita - Vietnam |
