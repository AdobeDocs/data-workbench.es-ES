---
description: Área de trabajo de datos proporciona un asistente de configuración para instalar la aplicación de estación de trabajo (cliente).
title: Asistente para configuración de estaciones de trabajo
uuid: e2bf6606-e7ba-439f-b50c-118706ab5b7d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Asistente para configuración de estaciones de trabajo{#workstation-setup-wizard}

Área de trabajo de datos proporciona un asistente de configuración para instalar la aplicación de estación de trabajo (cliente).

## Instalación de la estación de trabajo mediante el Asistente para instalación {#section-58da9bb6196c46eab3b54146913fdcb8}

Inicie el archivo ejecutable del asistente de instalación y siga cada paso para instalar el programa cliente de estación de trabajo. Tras la instalación de la estación de trabajo, puede conectarse a servidores y perfiles.

1. Haga doble clic en el archivo ejecutable del instalador de la estación de trabajo.
1. Haga clic en **Sí** para permitir que el programa se instale en Windows.
1. Seleccione un **idioma** para el asistente de configuración.

   Se abrirá el asistente:

   ![](assets/6_4_workstation_wizard.png)

1. Haga clic en **Siguiente** en el cuadro de diálogo Asistente para **la configuración de Área de trabajo de** datos.

1. Seleccione para instalar una **nueva instalación** o para **actualizar o reparar** una instalación existente.

   **La nueva instalación** sobrescribe los archivos instalados anteriormente.

   **La actualización** actualiza la estación de trabajo a la versión más reciente o le permite reparar una instalación existente. Área de trabajo de datos comparará los archivos **Insight.exe** instalados y ejecutará el Asistente para la instalación de estaciones de trabajo si hay una versión más reciente del cliente disponible.

1. Seleccionar ubicación de instalación:

   **Normalmente** se instala en una carpeta y una ubicación predeterminadas.

   * Los archivos de programa se guardan de forma predeterminada en:

      ```
      C:\Program Files\Adobe\Adobe Analytics\Data Workbench
      ```

   * Los archivos de datos (perfiles, certificados, registros de seguimiento y archivos de usuario) se guardan de forma predeterminada en:

      ```
      C:\Users\<username>\AppData\Local\Adobe\Adobe Analytics\Data Workbench\
      ```

      >[!IMPORTANT]
      >
      >Inicialmente se instalará un archivo ***Insight.cfg*** genérico sin detalles del servidor. Se recomienda utilizar el archivo ***Insight.cfg*** recién instalado y personalizarlo en lugar de mover un archivo de una instalación anterior. Debido a que la ruta de instalación de la estación de trabajo ha cambiado, se recomienda la adición de fuentes, la eliminación de la carpeta *de* usuario y la eliminación de *TraceFileComponent *.

1. (opcional) Seleccione*** Personalizado** para elegir el paquete de idioma y la ubicación del programa y los archivos de datos.
1. Seleccione la ubicación de **los accesos directos en el menú** Inicio.

   ![](assets/6_4_workstation_wizard_folder.png)

   Haga clic en **No crear una carpeta** del menú Inicio para no instalar un acceso directo en el menú Inicio de Windows.

1. Haga clic en **Siguiente.** Se mostrará un resumen de las rutas y los idiomas de ubicación de archivos seleccionados. Haga clic en **Instalar.**

1. Busque el certificado **de Área de trabajo de datos**.

   Si el asistente de configuración no encuentra el certificado de Área de trabajo de datos durante la instalación, abrirá un cuadro de diálogo para buscar la ubicación del certificado (un archivo **.pem** ubicado de forma predeterminada en la carpeta **Certificados** del cliente) o haga clic en **Omitir** para buscar el certificado después de la instalación.

   Haga clic en **Instalar** después de localizar el certificado.

1. Una vez que se haya completado el asistente de configuración y se haya instalado el Área de trabajo de datos, haga clic en **Finalizar** para completar la configuración.

   >[!NOTE]
   >
   >La ubicación de registro predeterminada para el Asistente para configuración de estaciones de trabajo en **[!DNL C:\Users\`<userName>`\AppData\Local\Temp.]**

   Seleccione la casilla de verificación **Iniciar aplicación** para abrir el área de trabajo después de la configuración.

1. **Configurar conexiones** a servidores en **[!DNL Insight.cfg]** archivos.

   Tras la instalación de la estación de trabajo, se abrirá el espacio de trabajo Experiencia de configuración de estación de trabajo mejorada con información adicional sobre la [introducción de información](/help/home/c-get-started/c-insght-config-param.md) de conexión del servidor en el archivo *Insight.cfg* y una opción para seleccionar un perfil en la lista desplegable. También puede ver el estado de la conexión a los servidores.

   ![](assets/6_4_workstation_install_conf_conn.png)

## Carpetas de instalación {#section-b5ea5a3b3ecb4622aef713972f3f8ebd}

La estructura de carpetas de Área de trabajo de datos tiene dos ubicaciones de instalación:

* **Archivos** de programa El archivo **Insight.exe** y los archivos de cliente compatibles (**Insight.ini**) ahora se encuentran de forma predeterminada en

   ```
   C:\Program Files\Adobe\Analytics\DataWorkbench
   ```

* Carpeta **Appdata** .

   **Insight.cfg**, perfiles, certificados, registros de seguimiento y archivos de usuario ahora se encuentran de forma predeterminada en

   ```
   C:\Users\<Winuser>\AppData\Adobe\Analytics\DataWorkbench\ 
   ```

   Puede definir la ruta de la carpeta **Appdata** en el `Insight.ini` archivo:

   ```
   [InitialSettings] 
   AppDataFolder=C:\Users\mhiatt\AppData\Local\Adobe\Adobe Analytics\Data Workbench\ 
   Locale=en-us
   ```

## Desinstalación de la estación de trabajo {#section-5ce2e233fe4348469ef1b3c451dd5b70}

Área de trabajo de datos ahora incluye un ejecutable para desinstalar la estación de trabajo (ubicada de forma predeterminada en **`Program Files\Adobe\Adobe Analytics\Data Workbench\ unins000.exe`**).

Inicie y siga los pasos para eliminar los archivos de la estación de trabajo del área de trabajo de datos del disco duro.

>[!NOTE]
>
>Puede iniciar el ejecutable **unins000.exe** desde la carpeta, utilizando el método abreviado **Desinstalar Área de trabajo** de datos desde el menú Inicio o desde **[!UICONTROL Control Panel]** > **[!UICONTROL Program and Features]**.
