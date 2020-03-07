---
description: Para que algunas de las características del servidor de informes funcionen, debe proporcionar y configurar hardware o software antes de realizar la instalación.
solution: Analytics
title: Antes de empezar
topic: Data workbench
uuid: cb464fb6-3109-4eff-9c95-f0cf1f8a8c66
translation-type: tm+mt
source-git-commit: 2e4991206394ca0c463210990ea44dfb700341a5

---


# Antes de empezar{#before-you-begin}

Para que algunas de las características del servidor de informes funcionen, debe proporcionar y configurar hardware o software antes de realizar la instalación.

## Requisitos básicos del servidor de informes {#section-e891eaee79fe4fa98e658426dc3b2777}

Los informes que se generan pueden tener la forma de imágenes .PNG o hojas de cálculo .XLS ubicadas en un sistema de archivos o como correos electrónicos. Los requisitos de hardware son idénticos a los del cliente [del área de trabajo de](https://docs.adobe.com/content/help/en/data-workbench/using/install/c-data-workbench-client-install.html#Data_Workbench_Client_Minimum_System_Requirements)datos.

Existen los siguientes requisitos para el servidor de informes:

* Acceso al sistema de archivos para la salida de datos (recurso compartido de red o unidad local).
* Acceso al servidor SMTP configurado.
* Microsoft Excel 2010 de 64 bits o superior instalado en [!DNL Report] Server. Consulte [Consideraciones para la automatización de Office](http://support.microsoft.com/kb/257757) en el servidor para obtener información adicional.

## Requisitos adicionales {#section-f53d4388656a4dfc90aefe29dfabef89}

* **Instale un adaptador de gráficos adecuado.** Para procesar correctamente los informes, el equipo en el que instale [!DNL Report] Server debe tener instalado un adaptador de gráficos adecuado.

* **Instale Microsoft Excel para generar informes como archivos de Excel.** Para generar y distribuir informes como archivos de Microsoft Excel ( [!DNL .xls] o [!DNL .xlsx]), el equipo en el que instale el servidor de informes debe tener instalada y registrada la versión adecuada de Microsoft Excel de 64 bits. Si no se ha registrado Excel y el servidor de informes intenta acceder a él por primera vez, Excel mostrará un cuadro de diálogo de registro. Si no está seguro de si la copia está registrada, inicie Excel manualmente y, si aparece un cuadro de diálogo de registro, complete el proceso de registro.

   >[!NOTE]
   >
   >Cuando se generan informes como archivos de Excel, se abre una nueva instancia de Excel. Para obtener más información sobre este proceso, consulte [http://support.microsoft.com/kb/257757](http://support.microsoft.com/kb/257757).

* **Proporcione acceso a un servidor SMTP para distribuir informes por correo electrónico.** Si desea distribuir informes por correo electrónico, el servidor de informes debe poder conectarse a un servidor SMTP y se deben abrir los puertos correspondientes al servicio de reenvío de correo electrónico.

