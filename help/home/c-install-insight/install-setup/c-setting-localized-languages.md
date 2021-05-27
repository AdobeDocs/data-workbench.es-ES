---
description: Configure el archivo insight.zbin para establecer el idioma de la aplicación cliente.
title: Configuración de idiomas localizados
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 1%

---

# Configuración de idiomas localizados{#setting-up-localized-languages}

Configure el archivo insight.zbin para establecer el idioma de la aplicación cliente.

## Actualización de los componentes del servidor de Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

El administrador debe completar primero estas tareas para actualizar estos componentes de servidor:

1. **Actualización al servidor de Data Workbench 6.x.** Debe actualizar el servidor de Data Workbench para la localización mediante la actualización del  [!DNL base\localization\*.zbin] archivo. Este archivo [!DNL insight.zbin] se copiará al cliente.

   Se incluye un archivo [!DNL insight.zbin] en la carpeta de instalación junto al archivo [!DNL insight.exe]. Si se conecta a un servidor que no le proporciona archivos [!DNL .zbin] específicos del idioma, el área de trabajo de datos procederá a utilizar este archivo.

   El archivo [!DNL insight.zbin] de copia de seguridad se puede proporcionar en cualquier idioma. Como resultado, si utiliza Data Workbench en chino y se conecta a un servidor que no admite este idioma, el cliente de Data Workbench seguirá en chino, incluso si el servidor cambia el perfil base y elimina los archivos [!DNL .zbin] de la carpeta [!DNL Base/Localization] .

1. **Actualice el servidor de informes de Data Workbench.** El valor  [!DNL insight.zbin] en la carpeta raíz del servidor de informes de Data Workbench estará en inglés de forma predeterminada. Como administrador, se le pedirá que seleccione y copie el archivo [!DNL .zbin] del paquete actualizado del servidor de informes y que lo coloque en el directorio raíz del servidor de informes de Data Workbench. Al igual que el cliente, el servidor de informes también requiere los argumentos adecuados para el idioma seleccionado, como [!DNL Insight.exe -zh-cn]

   1. Detenga los servicios del servidor de informes.
   1. Copie la carpeta [!DNL Localization] del nuevo paquete del servidor de informes.
   1. Desde la carpeta [!DNL Localization] , copie el archivo [!DNL Insight.zbin] y colóquelo en el directorio raíz del servidor de informes donde se encuentra [!DNL Insight.exe].

   1. Agregue los argumentos necesarios, como [!DNL insight.exe -zh-cn]
   1. Reinicie el servidor de informes.

## Actualizar el cliente de Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Después de actualizar el servidor, siga estos pasos para actualizar cada cliente.

1. Para asegurarse de que el cliente no se actualiza desde el servidor durante esta actualización, establezca el argumento [!DNL Insight.cfg] en False.

   ```
   Update Software = bool: false
   ```

1. Reinicie el cliente.
1. Vaya al perfil Software y Docs (perfil SoftDocs) y descargue el archivo **[!UICONTROL insight.zbin]** requerido del paquete del cliente: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Mueva el archivo [!DNL insight.zbin] a la carpeta donde se encuentra [!DNL insight.exe].

1. Para asegurarse de que los archivos cliente ahora se actualizan desde el servidor, cambie el argumento del archivo [!DNL Insight.cfg] a True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Su cliente se sincronizará con el servidor y verá un mensaje que indica que se está actualizando. Al final de la descarga, recibirá un mensaje en el que se le preguntará si desea reiniciar el cliente.

1. Haga clic en **OK** para reiniciar el cliente.

Si recibe el siguiente mensaje, significa que el archivo [!DNL zbin] no se colocó en la misma ubicación que el [!DNL Insight.exe].

```
Insight Terminated: The backup dictionary file insight.zbin 
is missing.
```

**Pantallas de bienvenida localizadas**

Data Workbench busca los siguientes archivos de pantalla de inicio:

* Inglés (predeterminado): [!DNL Base/Images/<version_product> Splash.png]
* Chino (cuando se inicia con -zh-cn): [!DNL Base/Images/<version_product> Splash zh-cn.png].

Si se solicita una pantalla de inicio pero falta, Data Workbench accederá a la pantalla de inicio en inglés de forma predeterminada.

<!-- <a id="section_91AE5EF234C14652A7B04082A22629AB"></a> -->
