---
title: Resolución de problemas
description: Obtenga información sobre cómo solucionar problemas al compartir recursos.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
role: Data Architect
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: fcb5c4a92f23bdffd1082b7b044b5859dead9d70
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 18%

---

# Resolución de problemas{#troubleshooting}

Se pueden encontrar errores al utilizar la integración con Audience Manager o el servicio principal Personas.

En este caso, asegúrese de que los siguientes elementos estén correctamente configurados:

* **Cuentas externas**

   En **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, asegúrese de que las siguientes cuentas externas S3 están configuradas correctamente. Los servidores S3 mencionados deberían haberse configurado durante el aprovisionamiento.

   * **[!UICONTROL importSharedAudience]**: Cuenta S3 dedicada a la importación de audiencias.
   * **[!UICONTROL exportSharedAudience]**: Cuenta S3 dedicada a la exportación de audiencias.

* **Fuentes de datos compartidas**

   En **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, compruebe que la fuente de datos compartida esté correctamente configurada.

   **[!UICONTROL Priority]** se utiliza cuando tiene varias fuentes de datos definidas. Priority decide qué fuente de datos se utilizará para coincidir con el alias recibido en el orden definido. **[!UICONTROL Priority]** solo es necesario para la implementación de Déclencheur.

   Compruebe que la clave de reconciliación sea correcta. Es el valor hash/cifrado de este campo el que se utiliza para exportar e importar audiencias.

   En caso de hash o cifrado del ID declarado, compruebe que se utilicen en el sitio web los mismos parámetros o algoritmos de codificación.

   Solo se admite un algoritmo de codificación: AES en modo CBC con un tamaño de clave de 128, 192 o 256 bits, con relleno PKCS.

   Si se selecciona el algoritmo de codificación AES, se deben configurar correctamente los siguientes campos adicionales:

   * **Clave de cifrado** para AES
   * **Cifrado IV** (Vector de inicialización) para AES
   * **Canal** (Correo electrónico/SMS/Otros): Este campo permite descifrar directamente direcciones de correo electrónico y números SMS. Asegúrese de que la clave de reconciliación coincide con la configuración de la variable **Canal** campo . Si selecciona &quot;Otro&quot;, este descifrado específico no se producirá y la clave de reconciliación se utilizará para reconciliar los datos.

   Es posible que las audiencias del Experience Cloud no se compartan porque el flujo de trabajo técnico se ha detenido o pausado. Acceda a la **[!UICONTROL Import shared audience]** flujo de trabajo haciendo clic directamente en **[!UICONTROL Show ImportShared Audience workflow]** en la fuente de datos.

Al importar una audiencia o compartirla mediante el servicio principal Personas, puede que falten algunos datos. Solo se transfieren los registros cuya ID (“ID de visitante” o “ID declarada”) se haya podido conciliar con la dimensión del perfil. Las ID de los segmentos del servicio principal Personas que no reconozca Adobe Campaign no se importan.
