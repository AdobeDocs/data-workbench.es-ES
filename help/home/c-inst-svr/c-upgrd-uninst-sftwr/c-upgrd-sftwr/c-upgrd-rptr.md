---
description: Instrucciones para actualizar Repeater mediante Insight o para actualizar copiando archivos.
solution: Analytics
title: Actualización del repetidor
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---


# Actualización del repetidor{#upgrading-repeater}

Instrucciones para actualizar Repeater mediante Insight o para actualizar copiando archivos.

Puede utilizar uno de los siguientes métodos para actualizar [!DNL Repeater] desde la plataforma 4.x o posterior:

* Si ha creado una conexión entre [!DNL Insight] y [!DNL Repeater] como se describe en [Creación de una conexión entre Insight y Repeater](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), puede utilizarla [!DNL Insight] para actualizar [!DNL Repeater]. Consulte [Actualización del repetidor con Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -O bien-

* Si no pudo o no creó una conexión entre [!DNL Insight] y [!DNL Repeater], debe copiar los archivos de actualización directamente en el [!DNL Repeater] equipo. Consulte [Actualización del repetidor mediante la copia de archivos](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Actualización del repetidor con Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. En el [!DNL Insight] equipo, copie la [!DNL bin] carpeta del paquete de [!DNL Insight Server] actualización en la [!DNL Temp] carpeta del directorio donde [!DNL Insight] está instalado.
1. Inicio [!DNL Insight].
1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón secundario en el icono del [!DNL Repeater] que desea actualizar y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga lo siguiente para cargar los archivos de actualización en el servidor:

   1. Busque la [!DNL bin] carpeta.
   1. Haga clic con el botón derecho en la marca de verificación de la [!DNL bin] carpeta en el directorio Temp y seleccione **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Verá un mensaje que indica que este paso sobrescribe los archivos con el mismo nombre que existen en el servidor. Haga clic en **[!UICONTROL Yes]** para continuar.

>[!NOTE]
>
>Si necesita cargar archivos adicionales para completar la [!DNL Repeater] actualización, Adobe le proporcionará instrucciones para hacerlo.

Después de cargar los archivos de actualización en el [!DNL Repeater] equipo, [!DNL Repeater] se reinicia automáticamente y carga la nueva versión.

## Actualización del repetidor mediante la copia de archivos {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Abra el archivo de actualización proporcionado por Adobe. Lo más probable es que este archivo sea un [!DNL .zip] archivo para la actualización [!DNL Insight Server].
1. Vaya al directorio donde instaló [!DNL Repeater] (por ejemplo, [!DNL D:\Adobe\Repeater]).
1. Copie la [!DNL bin] carpeta dentro del [!DNL .zip] archivo y péguela en el directorio [!DNL Repeater] de instalación para sobrescribir la [!DNL bin] carpeta existente.

>[!NOTE]
>
>Si necesita cargar archivos adicionales para completar la [!DNL Insight Server] actualización, Adobe le proporcionará instrucciones para hacerlo.

Después de copiar los archivos de actualización en el [!DNL Repeater] equipo, se reinicia automáticamente y se carga la nueva versión [!DNL Repeater] .
