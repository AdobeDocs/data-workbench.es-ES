---
description: Información sobre la supervisión de conjuntos de datos y la adición de nuevas ubicaciones para el almacenamiento de datos de conjuntos de datos.
solution: Insight
title: Monitoreo del espacio de datos del conjunto de datos
uuid: 0b7b95e7-b1bb-49cf-b465-fdbdc4ee214e
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Monitoreo del espacio de datos del conjunto de datos{#monitoring-dataset-data-space}

Información sobre la supervisión de conjuntos de datos y la adición de nuevas ubicaciones para el almacenamiento de datos de conjuntos de datos.

**Frecuencia recomendada:** Cada 5-10 minutos

De forma predeterminada, [!DNL Insight Server] escribe su conjunto de datos en el [!DNL temp.db] archivo en la misma unidad que los archivos de [!DNL Insight Server] programa de la unidad de procesamiento de datos. La cantidad de datos de conjunto de datos por [!DNL Insight Server] máquina se limita a lo siguiente, lo que suceda primero:

* 500 millones de registros de entrada de datos a ese conjunto de datos
* Se almacenan 500 GB de datos de conjunto de datos
* Un (1) MB de datos almacenados por cada dimensión de nivel raíz (por ejemplo, 5000 registros por visitante a un promedio de 200 bytes por registro)

Si desea [!DNL Insight Server] mantener el conjunto de datos en una unidad diferente, o si la cantidad de datos que espera recopilar requiere el uso de varias unidades, debe actualizar el archivo de configuración Archivos de disco ( [!DNL Disk Files.cfg]) para especificar dónde desea [!DNL Insight Server] escribir los [!DNL temp.db] archivos. El [!DNL Disk Files.cfg] archivo enumera los archivos de disco (un vector de cadenas) y especifica la ubicación de los datos del conjunto de datos que se utilizan [!DNL Insight Server] durante el reprocesamiento y la operación. Normalmente hay un archivo por unidad física.

>[!NOTE]
>
>Es posible que el contenido del [!DNL Disk Files.cfg] archivo se haya modificado durante la instalación [!DNL Insight Server]. Para obtener más información, consulte [Configuración de la ubicación del conjunto de datos (temp.db)](../../../../home/c-inst-svr/c-install-ins-svr/t-install-proc-inst-svr-dpu/t-cfg-loc-dtst.md#task-f645eefecb154e679acbb480a07c1f0e).

**Para agregar nuevas ubicaciones para el almacenamiento de datos de conjuntos de datos**

1. En [!DNL Insight], en la ficha [!DNL Admin] > [!DNL Dataset and Profile] , haga clic en la **[!UICONTROL Servers Manager]** miniatura para abrir el espacio de trabajo del Administrador de servidores.
1. Haga clic con el botón secundario en el icono del [!DNL Insight Server] que desee configurar y haga clic en **[!UICONTROL Server Files]**.
1. En el [!DNL Server Files Manager], haga clic **[!UICONTROL Components]** para ver su contenido. El [!DNL Disk Files.cfg] archivo se encuentra dentro de este directorio.
1. Haga clic con el botón secundario en la marca de verificación de la columna del nombre *del* servidor [!DNL Disk Files.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación en la [!DNL Temp] columna para [!DNL Disk Files.cfg].
1. Haga clic con el botón secundario en la marca de verificación recién creada en la [!DNL Temp] columna y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**.
1. En la [!DNL Disk Files.cfg] ventana, haga clic en **[!UICONTROL component]** para ver su contenido.

   ![Información sobre los pasos](assets/cfg_diskfiles_examplevalues.png)

   >[!NOTE]
   >
   >El parámetro Detect Disk Corruption se establece en true de forma predeterminada. El parámetro Tamaño de caché de disco (MB) controla la cantidad de memoria que [!DNL Insight Server] utiliza para aumentar la velocidad de acceso al disco y se establece en 128 de forma predeterminada. Póngase en contacto con Adobe antes de cambiar cualquiera de estos parámetros.

1. Para cambiar los archivos de disco del [!DNL Insight Server] equipo, haga clic con el botón derecho **[!UICONTROL Disk Files]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Disk File]**.

   Para eliminar un archivo de disco, haga clic con el botón secundario en el número de archivo de disco y haga clic en **[!UICONTROL Remove]**.

1. Para el nuevo archivo de disco, introduzca el directorio y el nombre del archivo que se va a utilizar [!DNL Insight Server] durante el reprocesamiento y la operación.

   ![Información sobre los pasos](assets/cfg_diskfiles_exampleNewValues.png)

   >[!NOTE]
   >
   >El parámetro Detect Disk Corruption se establece en true de forma predeterminada. El parámetro Tamaño de caché de disco (MB) controla la cantidad de memoria que [!DNL Insight Server] utiliza para aumentar la velocidad de acceso al disco y se establece en 128 de forma predeterminada. Póngase en contacto con Adobe antes de cambiar cualquiera de estos parámetros.

1. Guarde los cambios en el servidor haciendo lo siguiente:

   1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.

   1. En la [!DNL Server Files Manager], haga clic con el botón derecho en la marca de verificación del archivo en la [!DNL Temp] columna y seleccione **[!UICONTROL Save to]** > *&lt;**[!UICONTROL server name]**>*.

