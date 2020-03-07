---
description: Exportación de segmentos mediante el asistente para exportación de segmentos
title: Asistente para exportación de segmentos
uuid: 705bdf00-54e5-4992-8978-91afda8c7543
translation-type: tm+mt
source-git-commit: cb3ca4b3b993f5f04f6b6cee25850600ff3d8986

---


# Segment export wizard{#segment-export-wizard}

Exportación de segmentos mediante el asistente para exportación de segmentos

El asistente de exportación de segmentos proporciona un proceso paso a paso para configurar y exportar segmentos en lugar de [exportar segmentos desde una tabla](https://docs.adobe.com/content/help/en/data-workbench/using/client/export-data/c-sgmt-expt.html)de detalles.

## Exportación de segmentos mediante el asistente {#section-b30f2699dbc7490bad18512b91cb0cb3}

Para abrir el asistente, haga clic con el botón derecho en un espacio de trabajo y seleccione **Administrador** > **Asistentes** > Asistente para la exportación **de segmentos**.

>[!NOTE]
>
>Solo se capturarán los segmentos aplicados antes de abrir el asistente. Además, las exportaciones de segmentos creadas desde el asistente no pueden generar comandos externos.

1. Seleccione los distintos niveles principales de las dimensiones y métricas que desee agregar a la exportación.

   Los niveles mostrados dependen del perfil seleccionado. Puede seleccionar varios niveles de dimensión en función del perfil.

   ![](assets/seg_wizard_1.png)

1. Haga clic en **Siguiente**.
1. Seleccione la dimensión y las métricas para los niveles seleccionados.

   Por ejemplo, después de seleccionar Vista de página como nivel principal, puede seleccionar las dimensiones y métricas secundarias disponibles para exportar.

1. Haga clic en **Siguiente**.

   ![](assets/seg_wizard_2.png)

   ![](assets/seg_wizard_2_1.png)

1. Seleccione el formato de exportación e introduzca un nombre para el archivo de exportación.

   ![](assets/seg_wizard_3.png)

   Los tipos CSV, TSV, Exportación de segmentos y Exportación de segmentos con encabezados no necesitan ninguna configuración adicional. Sin embargo, Profiles and Audience Export, Custom Record Service y Adobe Target Export deben configurarse en el paso 3. Por ejemplo, consulte los campos de configuración de Profiles and Audience Export. Configure estos tipos de exportación y haga clic en **Siguiente**.

   ![](assets/seg_wizard_3_1.png)

   ![](assets/seg_wizard_3_2.png)

   ![](assets/seg_wizard_3_3.png)

1. Configure el tipo de exportación seleccionado.

   Encabezado: si Encabezado es Verdadero, asigne un nombre al campo Archivo **de** salida.

   Campo de escape (Escape Field): se establece como **True** o **False**.

   Orden de campos (Order of Fields): permite seleccionar un campo y desplazarse hacia arriba o hacia abajo para definir el orden en el archivo de exportación.

   ![](assets/seg_wizard_4.png)

   Haga clic en **Siguiente**.

1. Ver el nivel y los filtros aplicados en este cuadro de diálogo. Haga clic en **Siguiente**. ![](assets/seg_wizard_5.png)

1. Si se selecciona **CSV**, **TSV**, Exportación **** de segmentos o Exportación **de segmentos con encabezado** , hay tres opciones:

   Exportación genérica: el servidor generará el archivo de salida en la carpeta Servidor/Exportar.

   ![](assets/seg_wizard_6.png)

   Exportación de FTP: el archivo de salida se transferirá al servidor seleccionado. (La lista del servidor se seleccionará del archivo FTPServerInfo.cfg).

   ![](assets/seg_wizard_6_1.png)

   Exportación de SFTP: el archivo de salida se transferirá de forma segura al servidor seleccionado.

1. Haga clic en **Siguiente**

   **Nota:** Si el tipo de exportación seleccionado es **Profiles and Audience Export**, **Custom Record Service** y **Adobe Target Export**, el texto será estático según la exportación seleccionada.

1. Configure los parámetros de programación.

   **Una toma** se puede establecer en True o False.

   **La programación** avanzada se puede activar o desactivar haciendo clic en el botón Configuración de programación avanzada.

   ![](assets/seg_wizard_7.png)

   Al igual que la exportación desde la tabla de detalles, One Shot desaparecerá si la configuración avanzada está activada. Haga clic en **Siguiente**.

1. Obtenga una vista previa del archivo de exportación y, a continuación, haga clic en **Ejecutar exportación**.

   ![](assets/seg_wizard_8.png)

   ![](assets/seg_wizard_8_1.png)

Los siguientes tipos de exportación están disponibles mediante el asistente:

**Tipos de exportación de segmentos**

* Genéricas
* FTP
* SFTP

**Exportación de segmentos con encabezado**

* Genéricas
* FTP
* SFTP

**Exportación de CSV**

* Genéricas
* FTP
* SFTP

**Exportación de TSV**

* Genéricas
* FTP
* SFTP

