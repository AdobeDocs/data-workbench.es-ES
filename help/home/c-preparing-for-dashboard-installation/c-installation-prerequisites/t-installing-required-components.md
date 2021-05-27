---
description: Pasos para instalar los componentes de Microsoft necesarios.
title: Instalación de componentes necesarios
uuid: e23fba09-4684-4daf-8426-ea91169b3348
exl-id: d39cb14e-7cce-4088-8301-8ff566c0bde4
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 3%

---

# Instalación de componentes necesarios{#installing-required-components}

Pasos para instalar los componentes de Microsoft necesarios.

1. Instale Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Esto solo debe instalarse después de instalar y configurar el rol web de IIS.

1. Siga el asistente y elija los valores predeterminados donde se le pedirá que complete la instalación.
1. Una vez instalado, compruebe que el grupo de aplicaciones ASP.NET v.4.0 se agregó dentro del listado **[!UICONTROL Application Pools]** en IIS.
1. Instale la base de datos de Microsoft SQL Server.

   Utilice cualquier versión de SQL Server 2008 o 2008 R2 (se admite Express) con Herramientas de administración (Adobe recomienda SQL Server 2008 R2 SP1 - Express Edition). 1. Para una instalación genérica sin instancias de SQL Server existentes ejecutándose con antelación, seleccione la opción **[!UICONTROL Default Instance]** en la pantalla **[!UICONTROL Instance Configuration]**.
1. Para el resto de las opciones de configuración, siga el asistente y elija los valores predeterminados cuando se le pida que complete la instalación.
1. Instale Microsoft Web Deploy v2.0.

   Para la mayoría de las instalaciones, la instalación de **[!UICONTROL Typical]** está bien. Sin embargo, si planea realizar implementaciones remotas, deberá realizar una instalación completa (elija **[!UICONTROL Complete]**).

   Una vez instalados correctamente todos los requisitos previos, puede preparar los servidores de Data Workbench para comunicarse con el panel.
