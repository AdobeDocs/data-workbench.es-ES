---
description: Configure el archivo insight.zbin para establecer el idioma de la aplicación cliente.
title: Configuración de Localized Languages insight.zbin
uuid: 7735e183-7ba3-4e11-bfe2-7f87e4c55fc8
exl-id: bb57887f-f213-48a4-9a10-8da7ea33eda5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 1%

---

# Configuración de idiomas localizados{#setting-up-localized-languages}

{{eol}}

Configure el archivo insight.zbin para establecer el idioma de la aplicación cliente.

## Actualización de los componentes del servidor de Data Workbench {#section-5d07a081befc4eaa8fdf7fea904e0d48}

El administrador debe completar primero estas tareas para actualizar estos componentes de servidor:

1. **Actualización al servidor de Data Workbench 6.x.** Debe actualizar el servidor de Data Workbench para la localización mediante la actualización de la variable [!DNL base\localization\*.zbin] archivo. Esta [!DNL insight.zbin] a continuación, se copiará al cliente.

   Un [!DNL insight.zbin] se incluye en la carpeta de instalación junto a la [!DNL insight.exe] archivo. Si se conecta a un servidor que no le proporcione un idioma específico [!DNL .zbin] archivos, el área de trabajo de datos procederá a utilizar este archivo.

   La copia de seguridad [!DNL insight.zbin] puede proporcionarse en cualquier idioma. Como resultado, si utiliza Data Workbench en chino y se conecta a un servidor que no admite este idioma, el cliente de Data Workbench seguirá en chino, aunque el servidor cambie su perfil base y elimine el [!DNL .zbin] los archivos de [!DNL Base/Localization] carpeta.

1. **Actualice el servidor de informes de Data Workbench.** La variable [!DNL insight.zbin] en la carpeta raíz del servidor de informes de data workbench estará en inglés de forma predeterminada. Como administrador, debe seleccionar y copiar el [!DNL .zbin] del paquete de servidor de informes actualizado y colóquelo en el directorio raíz del servidor de informes de Data Workbench. Al igual que el cliente, el servidor de informes también requiere los argumentos adecuados para el idioma seleccionado, como [!DNL Insight.exe -zh-cn]

   1. Detenga los servicios del servidor de informes.
   1. Copie el [!DNL Localization] del nuevo paquete del servidor de informes.
   1. En el [!DNL Localization] carpeta, copie la [!DNL Insight.zbin] y colóquelo en el directorio raíz del servidor de informes donde [!DNL Insight.exe] está localizado.

   1. Añada los argumentos necesarios, como [!DNL insight.exe -zh-cn]
   1. Reinicie el servidor de informes.

## Actualizar el cliente de Data Workbench {#section-9653d3fcaf2a4337a97b685857e7aeac}

Después de actualizar el servidor, siga estos pasos para actualizar cada cliente.

1. Para asegurarse de que el cliente no se actualiza desde el servidor durante esta actualización, configure su [!DNL Insight.cfg] como False.

   ```
   Update Software = bool: false
   ```

1. Reinicie el cliente.
1. Vaya al perfil Software y Docs (perfil SoftDocs) y descargue el **[!UICONTROL insight.zbin]** del paquete cliente: [!DNL Software\Insight Client\Insight_6.1.zip]

1. Mover el [!DNL insight.zbin] a la carpeta donde [!DNL insight.exe] está localizado.

1. Para asegurarse de que los archivos cliente ahora se actualizan desde el servidor, cambie la variable [!DNL Insight.cfg] argumento de archivo en True:

   ```
   Update Software = bool: true
   ```

   I

   >[!NOTE]
   >
   >Su cliente se sincronizará con el servidor y verá un mensaje que indica que se está actualizando. Al final de la descarga, recibirá un mensaje en el que se le preguntará si desea reiniciar el cliente.

1. Haga clic en **OK** para reiniciar el cliente.

Si recibe el siguiente mensaje, significa que [!DNL zbin] no se colocó en la misma ubicación que el [!DNL Insight.exe].

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
