---
description: Pasos para instalar los componentes necesarios de Microsoft.
solution: Analytics
title: Instalación de componentes necesarios
topic: Data workbench
uuid: e23fba09-4684-4daf-8426-ea91169b3348
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Instalación de componentes necesarios{#installing-required-components}

Pasos para instalar los componentes necesarios de Microsoft.

1. Instale Microsoft .NET Framework v4.0.

   >[!NOTE]
   >
   >Esto solo debe instalarse después de instalar y configurar el rol web de IIS.

1. Siga el asistente y elija los valores predeterminados cuando se le solicite que complete la instalación.
1. Una vez instalado, compruebe que el grupo de aplicaciones ASP.NET v.4.0 se haya agregado dentro del **[!UICONTROL Application Pools]** listado en IIS.
1. Instale la base de datos de Microsoft SQL Server.

   Utilice cualquier versión de SQL Server 2008 o 2008 R2 (se admite Express) con Herramientas de administración (Adobe recomienda SQL Server 2008 R2 SP1 - Express Edition). 1. Para una instalación genérica sin instancias de SQL Server existentes ejecutándose con antelación, seleccione la **[!UICONTROL Default Instance]** opción en la **[!UICONTROL Instance Configuration]** pantalla.
1. Para el resto de las opciones de configuración, siga el asistente y elija los valores predeterminados cuando se le pregunte si desea completar la instalación.
1. Instale Microsoft Web Deploy v2.0.

   Para la mayoría de las instalaciones, la **[!UICONTROL Typical]** instalación está bien. Sin embargo, si planea realizar implementaciones remotas, deberá realizar una instalación completa (elija **[!UICONTROL Complete]**).

   Una vez instalados correctamente todos los requisitos previos, estará listo para preparar los servidores del área de trabajo de datos para comunicarse con el tablero.
