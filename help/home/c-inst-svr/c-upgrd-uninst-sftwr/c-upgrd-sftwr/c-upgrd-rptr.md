---
description: Instrucciones para actualizar el repetidor con Insight o para actualizarlo copiando archivos.
title: Actualización del repetidor
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Actualización del repetidor{#upgrading-repeater}

Instrucciones para actualizar el repetidor con Insight o para actualizarlo copiando archivos.

Puede utilizar uno de los siguientes métodos para actualizar [!DNL Repeater] desde Platform 4.x o posterior:

* Si ha creado una conexión entre [!DNL Insight] y [!DNL Repeater] como se describe en [Creación de una conexión entre Insight y el repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), puede utilizar [!DNL Insight] para actualizar [!DNL Repeater]. Consulte [Actualización del repetidor con Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -O bien-

* Si no pudo crear o no creó una conexión entre [!DNL Insight] y [!DNL Repeater], debe copiar los archivos de actualización directamente en el equipo [!DNL Repeater]. Consulte [Actualización del repetidor copiando archivos](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Actualización del repetidor con Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. En el equipo [!DNL Insight], copie la carpeta [!DNL bin] del paquete de actualización [!DNL Insight Server] en la carpeta [!DNL Temp] del directorio donde está instalado [!DNL Insight].
1. Inicio [!DNL Insight].
1. En [!DNL Insight], en la pestaña [!DNL Admin] > [!DNL Dataset and Profile], haga clic en la miniatura **[!UICONTROL Servers Manager]** para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono del [!DNL Repeater] que desee actualizar y haga clic en **[!UICONTROL Server Files]**.
1. En [!DNL Server Files Manager], haga lo siguiente para cargar los archivos de actualización en el servidor:

   1. Busque la carpeta [!DNL bin] .
   1. Haga clic con el botón derecho en la marca de verificación de la carpeta [!DNL bin] en el directorio Temp y seleccione **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Verá un mensaje que indica que este paso sobrescribe los archivos del mismo nombre que existen en el servidor. Haga clic en **[!UICONTROL Yes]** para continuar.

>[!NOTE]
>
>Si necesita cargar archivos adicionales para completar la actualización de [!DNL Repeater], Adobe le proporcionará instrucciones para hacerlo.

Después de cargar los archivos de actualización en el equipo [!DNL Repeater], [!DNL Repeater] se reinicia automáticamente y carga la nueva versión.

## Actualización del repetidor copiando archivos {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Abra el archivo de actualización proporcionado por Adobe. Lo más probable es que este archivo sea [!DNL .zip] para actualizar [!DNL Insight Server].
1. Vaya al directorio donde instaló [!DNL Repeater] (por ejemplo, [!DNL D:\Adobe\Repeater]).
1. Copie la carpeta [!DNL bin] dentro del archivo [!DNL .zip] y péguela en el directorio de instalación [!DNL Repeater] para sobrescribir la carpeta [!DNL bin] existente.

>[!NOTE]
>
>Si necesita cargar archivos adicionales para completar la actualización de [!DNL Insight Server], Adobe le proporcionará instrucciones para hacerlo.

Después de copiar los archivos de actualización en el equipo [!DNL Repeater], [!DNL Repeater] se reinicia automáticamente y carga la nueva versión.
