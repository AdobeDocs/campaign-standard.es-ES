---
title: Resolución de problemas de integración
description: Obtenga información sobre cómo solucionar problemas al compartir recursos.
audience: integrating
content-type: reference
topic-tags: working-with-campaign-and-audience-manager-or-people-core-service
feature: Triggers
old-role: Data Architect
role: Developer
level: Intermediate
exl-id: 5882ada6-dff4-4fd1-a433-0eb31570f73c
source-git-commit: b3f3309a252971dc527d44913b7918abeea704d9
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 18%

---

# Solución de problemas{#troubleshooting}

Se pueden encontrar errores al utilizar la integración con Audience Manager o el servicio principal Personas.

En este caso, asegúrese de que los siguientes elementos están correctamente configurados:

* **Cuentas externas**

  En **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL External accounts]**, asegúrese de que las siguientes cuentas externas de S3 estén configuradas correctamente. Los servidores S3 mencionados deberían haberse configurado durante el aprovisionamiento.

   * **[!UICONTROL importSharedAudience]**: cuenta S3 dedicada a la importación de audiencias.
   * **[!UICONTROL exportSharedAudience]**: cuenta S3 dedicada a la exportación de audiencias.

* **Fuentes de datos compartidas**

  En **[!UICONTROL Administration]** > **[!UICONTROL Application settings]** > **[!UICONTROL Shared Data Sources]**, compruebe que el origen de datos compartido esté configurado correctamente.

  **[!UICONTROL Priority]** se usa cuando se han definido varios orígenes de datos. La prioridad decide qué fuente de datos se utilizará para hacer coincidir el alias recibido en el orden definido. **[!UICONTROL Priority]** solo es necesario para la implementación de Déclencheur.

  Compruebe que la clave de reconciliación sea correcta. Es el valor cifrado/con hash de este campo el que se utiliza para exportar e importar audiencias.

  En caso de hash o cifrado del ID declarado, compruebe que se utilizan los mismos parámetros/algoritmos de cifrado en el sitio web.

  Solo se admite un algoritmo de cifrado: AES en modo CBC con un tamaño de clave de 128, 192 o 256 bits, con relleno PKCS.

  Si se selecciona el algoritmo de cifrado AES, se deben configurar correctamente los siguientes campos adicionales:

   * **Clave de cifrado** para AES
   * **Cifrado IV** (vector de inicialización) para AES
   * **Canal** (correo electrónico/SMS/otro): este campo permite descifrar directamente direcciones de correo electrónico y números de SMS. Asegúrese de que la clave de reconciliación coincida con la configuración del campo **Canal**. Si selecciona &quot;Otro&quot;, este descifrado específico no se producirá y la clave de reconciliación se utilizará para reconciliar los datos.

  Es posible que las audiencias de Experience Cloud no se compartan porque el flujo de trabajo técnico se ha detenido o pausado. Para obtener acceso al flujo de trabajo **[!UICONTROL Import shared audience]**, haga clic directamente en la opción **[!UICONTROL Show ImportShared Audience workflow]** del origen de datos.

Al importar un público o compartirlo mediante el servicio principal Personas, puede que falten algunos datos. Solo se transfieren los registros cuya ID (“ID de visitante” o “ID declarada”) se haya podido reconciliar con la dimensión del perfil. Las ID de los segmentos del servicio principal Personas que no reconozca Adobe Campaign no se importan.
