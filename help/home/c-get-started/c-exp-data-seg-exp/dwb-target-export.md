---
description: Exporte datos del Área de trabajo de datos a Adobe Target mediante TargetBulkUpload.exe desde la tabla de detalles.
title: Exportar a Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Exportar a Adobe Target{#export-to-adobe-target}

Exporte datos del Área de trabajo de datos a Adobe Target mediante TargetBulkUpload.exe desde la tabla de detalles.

Área de trabajo de datos permite exportar archivos para integrarlos con Adobe Target como parte de una Adobe Experience Cloud integrada.

El **[!DNL TargetBulkUpload]** archivo se encuentra en la carpeta *Server\Scripts* de los archivos de instalación del servidor. El ejecutable tiene lógica de reintentos, así como lógica adicional para optimizar el rendimiento.

Puede modificar el `TargetBulkUpload.cfg` archivo y moverlo a la carpeta *Server/Admin/Export* antes de ejecutar la secuencia de comandos de carga. Por ejemplo, puede establecer un intervalo de tiempo de espera máximo en 720 minutos (predeterminado) para que la carga se agote después del período especificado.

**Cómo funciona**

Una vez que los datos se envían correctamente a Target, el estado de la carga se monitorea continuamente. Si la carga se realiza correctamente, se registra un mensaje de éxito. Si la carga falla o está pendiente, la supervisión continúa. Puede configurar el intervalo de tiempo de espera en el `TargetBulkUpload.cfg` archivo. Si la carga se queda atascada en Target, se registra un mensaje y se puede seguir el estado.

Hay dos archivos de registro generados en el seguimiento para la exportación desencadenada en [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

El `targetbulkuploadexportname.log` archivo tiene el estado detallado de todos los registros de varios lotes, el servidor Edge al que van a ir y el estado (correcto, fallido, perfil no encontrado, estado desconocido y atascado). Si se detecta que un lote está atascado, el lote no se procesa más. Hay disponible una URL por lotes atascada para rastrear el estado. Consulte los siguientes datos de ejemplo del `targetbulkuploadexportname.log.completed` archivo:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

El valor de estado atascado se incrementa con el tamaño total del lote atascado, independientemente de cuántas cargas se hayan realizado correctamente o no. El valor total de filas también se incrementa en el mismo número de tamaño de lote atascado.

>[!NOTE]
>
>Anteriormente, los datos de DWB se exportaban mediante el [!DNL ExportIntegration.exe]. Actualmente solo se utilizan las exportaciones de MMP, CRS y S/FTP con este archivo ejecutable. La integración de Adobe Target ahora utiliza el [!DNL TargetBulkUpload.exe] en Área de trabajo de datos.

