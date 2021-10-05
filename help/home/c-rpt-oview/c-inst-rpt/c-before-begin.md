---
description: Para que algunas de las características de Report Server funcionen, debe proporcionar y configurar hardware o software antes de instalar.
title: Antes de empezar
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
exl-id: 5c8bb4c3-fe76-4b4e-960d-113a9927ad59
source-git-commit: 79981e92dd1c2e552f958716626a632ead940973
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 1%

---

# Antes de empezar{#before-you-begin}

Para que algunas de las características de Report Server funcionen, debe proporcionar y configurar hardware o software antes de instalar.

## Requisitos básicos del servidor de informes {#section-e891eaee79fe4fa98e658426dc3b2777}

Los informes que se muestran pueden presentar en forma de imágenes .PNG o hojas de cálculo .XLS colocadas en un sistema de archivos o como correos electrónicos. Los requisitos de hardware son idénticos al cliente [data workbench](https://experienceleague.adobe.com/docs/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements).

Los siguientes requisitos existen para el servidor de informes:

* Acceso al sistema de archivos para la salida de datos (recurso compartido de red o unidad local).
* Acceso al servidor SMTP configurado.
* Microsoft Excel 2010 de 64 bits o superior instalado en el servidor [!DNL Report]. Consulte [Consideraciones para la automatización en el lado del servidor de Office](https://support.microsoft.com/kb/257757) para obtener información adicional.

## Requisitos adicionales {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Instale un adaptador de gráficos adecuado.** Para procesar correctamente los informes, el equipo en el que instale  [!DNL Report] Server debe tener instalado un adaptador de gráficos adecuado.

* **Instale Microsoft Excel para generar informes como archivos de Excel.** Para generar y distribuir informes como archivos de Excel de Microsoft (  [!DNL .xls] o  [!DNL .xlsx]), el equipo en el que instale el servidor de informes debe tener instalada y registrada la versión apropiada de Microsoft Excel de 64 bits. Si Excel no se ha registrado y Report Server intenta acceder a él por primera vez, se mostrará un cuadro de diálogo de registro. Si no está seguro de si la copia está registrada, inicie Excel manualmente y si aparece un cuadro de diálogo de registro, complete el proceso de registro.

   >[!NOTE]
   >
   >Cuando se generan informes como archivos de Excel, se abre una nueva instancia de Excel. Para obtener más información sobre este proceso, consulte [https://support.microsoft.com/kb/257757](https://support.microsoft.com/kb/257757).

* **Proporcionar acceso a un servidor SMTP para distribuir los informes por correo electrónico.** Si desea distribuir informes por correo electrónico, Report Server debe poder conectarse a un servidor SMTP y se deben abrir los puertos adecuados para el servicio de reenvío de correo electrónico.
