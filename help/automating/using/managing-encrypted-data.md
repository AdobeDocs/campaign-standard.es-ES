---
title: Administración de datos cifrados
description: Obtenga información sobre cómo administrar datos cifrados.
page-status-flag: never-activated
uuid: d909d26a-cf50-46af-ae09-f0fd7258ca27
contentOwner: sauviat
products: SG_CAMPAIGN/STANDARD
audience: automating
content-type: reference
topic-tags: workflow-general-operation
discoiquuid: 75b83165-dcbd-4bb7-b703-ed769f489b16
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 44d6126023e9411477ccd7ffc07ecde806e7976d
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---


# Administración de datos cifrados {#managing-encrypted-data}

En algunos casos, es posible que los datos que desea importar los servidores de Campaña deban cifrarse, por ejemplo, si contienen datos PII.

Para poder importar o exportar archivos cifrados, primero debe ponerse en contacto con el Servicio de atención al cliente de Adobe para que le proporcionen a su instancia los comandos de cifrado y descifrado necesarios.

Para ello, envíe una solicitud que indique:

* La **etiqueta** que se mostrará en la interfaz de Campaña para utilizar el comando. Por ejemplo, &quot;Cifrar archivo&quot;.
* El **comando** que se va a instalar en la instancia.
Por ejemplo, para descifrar un archivo con PGP, el comando será:

   ```
   <path-to_pgp_if-not_global_or_server/>pgp.exe --decrypt --input nl6/var/vp/import/filename.pgp --passphrase "your password" --recipient recipient @email.com --verbose --output nl6/var/vp/import/filename
   ```

Una vez procesada la solicitud, los comandos de cifrado/descifrado estarán disponibles en el **[!UICONTROL Pre-processing stage]** campo desde las **[!UICONTROL Load file]** actividades y **[!UICONTROL Extract file]** . Puede utilizarlos para descifrar o cifrar los archivos que desea importar o exportar.

![](assets/preprocessing-encryption.png)

**Temas relacionados:**

* [Cargar archivo](../../automating/using/load-file.md)
* [Extraer archivo](../../automating/using/extract-file.md)
