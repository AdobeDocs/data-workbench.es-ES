---
description: Configure el archivo insight.zbin para establecer el idioma de la aplicación cliente.
title: Configuración de idiomas localizados
uuid: 97baf281-32fd-4df0-81a6-c2c7126b053c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración de idiomas localizados{#setting-up-localized-languages}

Configure el archivo insight.zbin para establecer el idioma de la aplicación cliente.

## Actualizar los componentes del servidor del área de trabajo de datos {#section-5d07a081befc4eaa8fdf7fea904e0d48}

El administrador debe completar primero estas tareas para actualizar estos componentes del servidor:

1. **Actualización al servidor del área de trabajo de datos 6.x.** Debe actualizar el servidor del área de trabajo de datos para la localización mediante la actualización del [!DNL base\localization\*.zbin] archivo. Este [!DNL insight.zbin] archivo se copiará en el cliente.

   Se incluye un [!DNL insight.zbin] archivo en la carpeta de instalación junto al [!DNL insight.exe] archivo. Si se conecta a un servidor que no le proporciona [!DNL .zbin] archivos específicos de idioma, el área de trabajo de datos procederá a utilizar este archivo.

   El [!DNL insight.zbin] archivo de copia de seguridad se puede proporcionar en cualquier idioma. Como resultado, si utiliza el área de trabajo de datos en chino y se conecta a un servidor que no admite este idioma, el cliente del área de trabajo de datos seguirá estando en chino, incluso si el servidor cambia el perfil base y elimina [!DNL .zbin] los archivos de la [!DNL Base/Localization] carpeta.

1. **Actualice el servidor de informes del área de trabajo de datos.** La carpeta raíz [!DNL insight.zbin] del servidor de informes del área de trabajo de datos estará en inglés de forma predeterminada. Como administrador, se le solicitará que seleccione y copie el [!DNL .zbin] archivo del paquete actualizado del servidor de informes y lo coloque en el directorio raíz del servidor de informes del área de trabajo de datos. Al igual que el cliente, el servidor de informes también requiere los argumentos adecuados para el idioma seleccionado, como [!DNL Insight.exe -zh-cn]

   1. Detenga los servicios del servidor de informes.
   1. Copie la [!DNL Localization] carpeta del nuevo paquete del servidor de informes.
   1. Desde la [!DNL Localization] carpeta, copie el [!DNL Insight.zbin] archivo y colóquelo en el directorio raíz del servidor de informes en el que [!DNL Insight.exe] se encuentra.

   1. Agregue los argumentos necesarios, como [!DNL insight.exe -zh-cn]
   1. Reinicie el servidor de informes.

## Actualizar el cliente del área de trabajo de datos {#section-9653d3fcaf2a4337a97b685857e7aeac}

Después de actualizar el servidor, siga estos pasos para actualizar cada cliente.

1. Para asegurarse de que el cliente no se actualiza desde el servidor durante esta actualización, establezca su [!DNL Insight.cfg] argumento en False.

   ```
   Update Software = bool: false
   ```

1. Reinicie el cliente.
1. Vaya al perfil Software y Docs (perfil SoftDocs) y descargue el archivo requerido **[!UICONTROL insight.zbin]** del paquete de cliente: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Mueva el [!DNL insight.zbin] archivo a la carpeta en la que [!DNL insight.exe] se encuentra.

1. Para asegurarse de que los archivos cliente se actualizan desde el servidor, cambie el argumento del [!DNL Insight.cfg] archivo a True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Su cliente se sincronizará con el servidor y verá un mensaje que indica que se está actualizando. Al finalizar la descarga, recibirá un mensaje preguntándole si desea reiniciar su cliente.

1. Haga clic en **Aceptar** para reiniciar el cliente.

Si recibe el siguiente mensaje, significa que el [!DNL zbin] archivo no se colocó en la misma ubicación que el [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Pantallas de bienvenida localizadas**

El área de trabajo de datos busca los siguientes archivos de pantalla de bienvenida:

* Inglés (predeterminado): [!DNL Base/Images/<version_product> Splash.png]
* Chino (cuando comenzó con -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Si se solicita una pantalla de bienvenida pero falta, el área de trabajo de datos accederá a la pantalla de bienvenida en inglés de forma predeterminada.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->

