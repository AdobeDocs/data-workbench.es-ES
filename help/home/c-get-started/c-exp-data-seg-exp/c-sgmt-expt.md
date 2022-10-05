---
description: Puede crear fácilmente una definición de Exportación de segmentos desde la visualización de Tabla de detalles en el cliente de Data Workbench.
title: Exportación de segmentos
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
exl-id: 49998b46-f3a6-43a3-a76e-468894b27ee4
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Exportación de segmentos{#segment-export}

{{eol}}

Puede crear fácilmente una definición de Exportación de segmentos desde la visualización de Tabla de detalles en el cliente de Data Workbench.

Además, [!DNL Segment Exports] combinar automáticamente sus resultados en un único servidor, en lugar de producir resultados parciales en cada DPU que debe combinar mediante un proceso externo. Puede crear un archivo de exportación de segmentos y guardarlo en el [!DNL Profile Manager]y cargue el archivo de salida en un servidor de su elección.

**Para configurar el servidor de exportación de segmentos**

La variable [!DNL Segment Export] crea un único archivo de salida en el servidor de exportación de segmentos, en lugar de archivos de salida independientes creados en cada DPU. El servidor de exportación de segmentos suele estar configurado para ejecutarse en la FSU.

En el directorio Dataset\ de la [!DNL Profile Manager], abra el [!DNL Segment Export.cfg] en Workstation, y especifique la dirección de su servidor. (Su dirección puede ser una IP o un nombre de dominio completo):

![](assets/segment_export_cfg.png)

Esta es la IP del servidor de Data Workbench que recibe los resultados de la exportación del segmento. Esta es una configuración única. Si la variable [!DNL Segment Export.cfg] no está presente, las exportaciones no se ejecutan.

**Para configurar directorios de exportación**

Por motivos de seguridad, los archivos ejecutables o por lotes que se ejecuten después de una exportación de segmentos deben residir en el directorio Scripts\ configurable del servidor de exportación de segmentos.

La variable [!DNL .part] y la salida final deben residir en el directorio de Exportaciones configurables. El comando que se va a ejecutar existe en los argumentos Comando y Comando. Las instancias del %file% en los argumentos de comando se reemplazarán por la ruta del archivo de salida.

>[!NOTE]
>
>Como novedad en la Data Workbench 5.4, la carpeta \Exportaciones se crea automáticamente. Los directorios de exportación anteriores configurados antes de la versión 5.4 requerían un prefijo Export\ antes del nombre de archivo para cada exportación de segmento. Añadir este prefijo ahora es redundante.

1. En [!DNL Communications.cfg] en el servidor de destino para [!DNL Segment Exports], agregue SegmentExportServer a la lista de servidores. (Ejemplo mostrado en rojo).

   ![](assets/communications_cfg_example.png)

   Directorio de exportaciones: Especifica dónde colocar [!DNL .part] y archivos de salida. Puede ser un directorio compartido.

   Directorio de scripts: Especifica el directorio desde el que se ejecutan todos los archivos ejecutables o por lotes.

1. [!DNL Access Control.cfg], en el mismo servidor, agregue acceso de lectura y escritura al URI /SegmentExportServer/ al grupo de acceso de los servidores de clúster:

   ![](assets/accesscontrol_cfg_example.png)

1. Cambie el [!DNL .export] archivos:

   ![](assets/segment_export_query_example.png)

1. Para cada perfil, la variable [!DNL Segment Export.cfg] se encuentra en el directorio Dataset\, con el siguiente contenido:

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Asegúrese de que existen los directorios a los que se hace referencia en Directorio de exportaciones y Directorio de scripts.

   Solo los archivos ejecutables y por lotes del directorio Scripts se pueden ejecutar como el comando de una exportación de segmentos.

**Para crear un archivo de exportación de segmentos**

1. En un espacio de trabajo, cree una Tabla de detalles que muestre subconjuntos de datos (Visualización > Tabla de detalles) y añada atributos.
1. Si lo desea, realice selecciones en el espacio de trabajo. (Las selecciones o filtros se aplican a la exportación).

   ![](assets/create_segment_export_file.png)

1. En el encabezado Tabla de detalles, haga clic con el botón derecho y seleccione **[!UICONTROL Create Segment Export File]**.
1. En [!DNL Save as], escriba un nombre para [!DNL .export] archivo.
1. En el [!DNL .export] configure los parámetros según sea necesario.

   Las selecciones o filtros del espacio de trabajo se incorporan al archivo de exportación.

1. Guarde el [!DNL .export] archivo.

   El archivo guardado se muestra en la sección [!DNL Profile Manager] para guardar en el servidor. Cuando guarda el archivo en el servidor, comienza la exportación.
