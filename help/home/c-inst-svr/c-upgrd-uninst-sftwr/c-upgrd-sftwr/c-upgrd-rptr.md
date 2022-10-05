---
description: Instrucciones para actualizar el repetidor con Insight o para actualizarlo copiando archivos.
title: Actualización del repetidor
uuid: 2027ed9e-9dd9-40f5-b7e9-2709f8745b5c
exl-id: f81fa79e-f660-48fd-b2ff-419961d49c55
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '317'
ht-degree: 1%

---

# Actualización del repetidor{#upgrading-repeater}

{{eol}}

Instrucciones para actualizar el repetidor con Insight o para actualizarlo copiando archivos.

Puede utilizar uno de los siguientes métodos para actualizar [!DNL Repeater] desde Platform 4.x o posterior:

* Si ha creado una conexión entre [!DNL Insight] y [!DNL Repeater] tal como se describe en [Creación de una conexión entre Insight y el repetidor](../../../../home/c-inst-svr/c-rptr-fntly/c-cnfg-rptr-fntly/t-crt-conn-ins-rptr.md#task-785bfe5f0e31484683e4345038add118), puede usar [!DNL Insight] para actualizar [!DNL Repeater]. Consulte [Actualización del repetidor con Insight](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-59c24448fd0f45c08abd0245ad746764).

   -o-

* Si no puede crear o no ha creado una conexión entre [!DNL Insight] y [!DNL Repeater], debe copiar los archivos de actualización directamente en el [!DNL Repeater] máquina. Consulte [Actualización del repetidor copiando archivos](../../../../home/c-inst-svr/c-upgrd-uninst-sftwr/c-upgrd-sftwr/c-upgrd-rptr.md#section-202f2209f6604f19a15d96b517ea1bc1).

## Actualización del repetidor con Insight {#section-59c24448fd0f45c08abd0245ad746764}

1. En el [!DNL Insight] equipo, copie el [!DNL bin] de [!DNL Insight Server] actualice el paquete al [!DNL Temp] en el directorio donde [!DNL Insight] está instalado.
1. Inicio [!DNL Insight].
1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de la variable [!DNL Repeater] desea actualizar y hacer clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga lo siguiente para cargar los archivos de actualización en el servidor:

   1. Busque la variable [!DNL bin] carpeta.
   1. Haga clic con el botón derecho en la marca de verificación de la variable [!DNL bin] en el directorio Temp y seleccione **[!UICONTROL Save Directory to]** > *&lt;**[!UICONTROL server name]**>*.

>[!NOTE]
>
>Verá un mensaje que indica que este paso sobrescribe los archivos del mismo nombre que existen en el servidor. Haga clic en **[!UICONTROL Yes]** para continuar.

>[!NOTE]
>
>Si necesita cargar archivos adicionales para completar su [!DNL Repeater] actualización, Adobe proporcionará instrucciones para hacerlo.

Después de cargar los archivos de actualización a la [!DNL Repeater] máquina, [!DNL Repeater] se reinicia automáticamente y carga la nueva versión.

## Actualización del repetidor copiando archivos {#section-202f2209f6604f19a15d96b517ea1bc1}

1. Abra el archivo de actualización proporcionado por Adobe. Lo más probable es que este archivo sea un [!DNL .zip] archivo para actualizar [!DNL Insight Server].
1. Vaya al directorio donde instaló [!DNL Repeater] (por ejemplo, [!DNL D:\Adobe\Repeater]).
1. Copie el [!DNL bin] dentro de la carpeta [!DNL .zip] y péguelo en su [!DNL Repeater] directorio de instalación para sobrescribir el directorio existente [!DNL bin] carpeta.

>[!NOTE]
>
>Si necesita cargar archivos adicionales para completar su [!DNL Insight Server] actualización, Adobe proporcionará instrucciones para hacerlo.

Después de copiar los archivos de actualización en el [!DNL Repeater] máquina, [!DNL Repeater] se reinicia automáticamente y carga la nueva versión.
