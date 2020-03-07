---
description: Puede crear fácilmente una definición de exportación de segmentos desde la visualización de tabla de detalles en el cliente del área de trabajo de datos.
solution: Analytics
title: Exportación de segmentos
topic: Data workbench
uuid: 85c8aa72-23fe-424b-9580-6759dc8f8681
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportación de segmentos{#segment-export}

Puede crear fácilmente una definición de exportación de segmentos desde la visualización de tabla de detalles en el cliente del área de trabajo de datos.

Además, [!DNL Segment Exports] combina automáticamente sus resultados en un único servidor, en lugar de producir resultados parciales en cada DPU que debe combinar mediante un proceso externo. Puede crear un archivo de exportación de segmentos, guardarlo en el [!DNL Profile Manager]y cargar el archivo de salida en un servidor de su elección.

**Para configurar el servidor de exportación de segmentos**

La [!DNL Segment Export] función crea un único archivo de salida en el servidor de exportación de segmentos, en lugar de archivos de salida independientes creados en cada DPU. El servidor de exportación de segmentos suele estar configurado para ejecutarse en la FSU.

En el directorio Dataset\ de la [!DNL Profile Manager], abra el [!DNL Segment Export.cfg] en Workstation y especifique la dirección del servidor. (Su dirección puede ser una dirección IP o un nombre de dominio completo):

![](assets/segment_export_cfg.png)

Es una dirección IP del servidor de Área de trabajo de datos que recibe los resultados de la exportación de segmentos. Ésta es una configuración única. Si el [!DNL Segment Export.cfg] no está presente, las exportaciones no se ejecutan.

**Para configurar directorios de exportación**

Por motivos de seguridad, los archivos ejecutables o por lotes que se ejecutan después de exportar un segmento deben residir en el directorio Scripts\ configurable del servidor de exportación de segmentos.

La salida [!DNL .part] y la salida final deben residir en el directorio de exportación configurable. El comando que se va a ejecutar existe en los argumentos Comando y Comando. Las instancias del %file% en los argumentos de comando se reemplazarán por la ruta del archivo de salida.

>[!NOTE]
>
>La carpeta \Exportaciones, nueva a Área de trabajo de datos 5.4, se crea automáticamente. Los directorios de exportación anteriores configurados antes de la versión 5.4 requerían un prefijo Exportar\ antes del nombre de archivo para cada exportación de segmentos. Agregar este prefijo ahora es redundante.

1. En [!DNL Communications.cfg] el servidor de destino de [!DNL Segment Exports], agregue SegmentExportServer a la lista de servidores. (Ejemplo mostrado en rojo).

   ![](assets/communications_cfg_example.png)

   Directorio de exportaciones: Especifica dónde colocar [!DNL .part] y generar los archivos. Puede ser un directorio compartido.

   Directorio de secuencias de comandos: Especifica el directorio desde el que se ejecutan todos los archivos ejecutables o por lotes.

1. [!DNL Access Control.cfg], en el mismo servidor, agregue acceso de lectura y escritura al URI /SegmentExportServer/ al grupo de acceso de servidores de clúster:

   ![](assets/accesscontrol_cfg_example.png)

1. Cambie [!DNL .export] los archivos:

   ![](assets/segment_export_query_example.png)

1. Para cada perfil, el [!DNL Segment Export.cfg] se encuentra en el directorio Dataset\, con el siguiente contenido:

   ```
   Segment Export = SegmentExport:
   Segment Export Server = serverInfo:
   Port = int: 80
   Address = string: 192.168.5.128 (for example) Use SSL = bool: false
   ```

1. Asegúrese de que existen los directorios a los que se hace referencia en Directorio de exportación y Directorio de secuencias de comandos.

   Sólo los archivos ejecutables y por lotes del directorio Scripts pueden ejecutarse como el comando de una exportación de segmentos.

**Para crear un archivo de exportación de segmentos**

1. En un espacio de trabajo, cree una tabla de detalles que muestre subconjuntos de datos (Visualización > Tabla de detalles) y agregue atributos.
1. Si lo desea, realice selecciones en el espacio de trabajo. (Las selecciones o filtros se aplican a la exportación).

   ![](assets/create_segment_export_file.png)

1. En el encabezado Tabla de detalles, haga clic con el botón derecho y seleccione **[!UICONTROL Create Segment Export File]**.
1. En [!DNL Save as], escriba un nombre para el [!DNL .export] archivo.
1. En el [!DNL .export] archivo, configure los parámetros según sea necesario.

   Las selecciones o filtros del espacio de trabajo se incorporan al archivo de exportación.

1. Save the [!DNL .export] file.

   El archivo guardado se muestra en la pantalla [!DNL Profile Manager] para que lo guarde en el servidor. Cuando guarda el archivo en el servidor, comienza la exportación.

