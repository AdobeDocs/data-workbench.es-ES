---
description: Pasos para descargar e instalar el certificado digital.
title: Procedimientos de instalación de certificados digitales
uuid: 14749a68-96cb-4cf4-819e-07df065e4016
exl-id: a8ae8d23-8db8-44d9-8c45-e552da81c384
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 33%

---

# Procedimientos de instalación de certificados digitales{#digital-certificate-installation-procedures}

Pasos para descargar e instalar el certificado digital.

1. Abra el explorador web y vaya a [https://aap.adobe.com](https://aap.adobe.com).

   >[!NOTE]
   >
   >Es posible que el explorador le pida que presente un certificado digital en este momento. Si es así, haga clic en **[!UICONTROL Cancel]** para cerrar el cuadro de diálogo.

1. En la pantalla de inicio de sesión, introduzca el Nombre de cuenta y la Contraseña que recibió del Adobe y, a continuación, haga clic en **[!UICONTROL login]**.
1. Busque el certificado emitido para su instancia de [!DNL Report] Server (*Your Name*.pem) y haga clic en el icono ![](assets/btn_save_certificatedownload.PNG) asociado a ese certificado.
1. Cuando se le pregunte si desea guardar el certificado, haga clic en **[!UICONTROL Save]**.
1. Descargue el archivo en la carpeta Certificados del directorio donde instaló [!DNL Report Server].

   Esta carpeta ya contiene un archivo de certificado denominado [!DNL trust_ca_cert.pem]. Ambos archivos de certificado siempre deben estar presentes para que [!DNL Report] Server funcione.
