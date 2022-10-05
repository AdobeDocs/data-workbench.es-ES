---
description: Información sobre la supervisión del conjunto de datos y la adición de nuevas ubicaciones para el almacenamiento de datos del conjunto de datos.
title: Monitorización del espacio de datos del conjunto de datos
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
exl-id: eb34d5fe-73c6-461f-8bb0-85833d8f824f
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 2%

---

# Monitorización del espacio de datos del conjunto de datos{#monitoring-dataset-data-space}

{{eol}}

Información sobre la supervisión del conjunto de datos y la adición de nuevas ubicaciones para el almacenamiento de datos del conjunto de datos.

**Frecuencia recomendada:** Cada 5-10 minutos

De forma predeterminada, [!DNL Insight Server] escribe su conjunto de datos en el [!DNL temp.db] en la misma unidad que el [!DNL Insight Server] archivos de programa de la unidad de procesamiento de datos. Cantidad de datos del conjunto de datos por [!DNL Insight Server] la máquina se limita a lo siguiente, lo que ocurra primero:

* 500 millones de registros de entrada de datos a ese conjunto de datos
* Se almacenan 500 GB de datos del conjunto de datos
* Un (1) MB de datos del conjunto de datos almacenados por cualquier dimensión de nivel raíz (por ejemplo, 5000 registros por visitante a un promedio de 200 bytes por registro)

Si desea [!DNL Insight Server] para mantener el conjunto de datos en una unidad diferente, o si la cantidad de datos que espera recopilar requiere el uso de varias unidades, debe actualizar el archivo de configuración Archivos de disco ( [!DNL Disk Files.cfg]) para especificar dónde desea [!DNL Insight Server] para escribir el [!DNL temp.db] archivos. La variable [!DNL Disk Files.cfg] El archivo enumera los archivos de disco (un vector de cadenas) y especifica la ubicación de los datos del conjunto de datos utilizados por [!DNL Insight Server] durante el reprocesamiento y la operación. Normalmente hay un archivo por unidad física.

>[!NOTE]
>
>El contenido del [!DNL Disk Files.cfg] puede que se haya modificado durante la instalación [!DNL Insight Server]. Para obtener más información, consulte [Configuración de la ubicación del conjunto de datos (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Para agregar nuevas ubicaciones para el almacenamiento de datos del conjunto de datos**

1. En [!DNL Insight], en el [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la pestaña **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón derecho en el icono de la variable [!DNL Insight Server] desea configurar y hacer clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic en **[!UICONTROL Components]** para ver su contenido. La variable [!DNL Disk Files.cfg] se encuentra dentro de este directorio.
1. Haga clic con el botón derecho en la marca de verificación de la *nombre del servidor* para [!DNL Disk Files.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la variable [!DNL Temp] para [!DNL Disk Files.cfg].
1. Haga clic con el botón derecho en la marca de verificación recién creada en la [!DNL Temp] y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En el [!DNL Disk Files.cfg] ventana, haga clic en **[!UICONTROL component]** para ver su contenido.

   ![Información sobre los pasos](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >El parámetro Detect Disk Corruption está establecido en true de forma predeterminada. El parámetro Tamaño de caché de disco (MB) controla la cantidad de memoria que [!DNL Insight Server] utiliza para aumentar la velocidad de acceso al disco y está establecido en 128 de forma predeterminada. Póngase en contacto con Adobe antes de cambiar cualquiera de estos parámetros.

1. Para cambiar los archivos de disco en el [!DNL Insight Server] máquina, clic con el botón derecho **[!UICONTROL Disk Files]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Para eliminar un archivo de disco, haga clic con el botón derecho en el número de archivo de disco y haga clic en **[!UICONTROL Remove]**.

1. Para el nuevo archivo de disco, introduzca el directorio y el nombre del archivo que va a utilizar [!DNL Insight Server] durante el reprocesamiento y la operación.

   ![Información sobre los pasos](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >El parámetro Detect Disk Corruption está establecido en true de forma predeterminada. El parámetro Tamaño de caché de disco (MB) controla la cantidad de memoria que [!DNL Insight Server] utiliza para aumentar la velocidad de acceso al disco y está establecido en 128 de forma predeterminada. Póngase en contacto con Adobe antes de cambiar cualquiera de estos parámetros.

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En el [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL Temp] y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.
