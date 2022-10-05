---
description: Exporte datos de Data Workbench a Adobe Target mediante TargetBulkUpload.exe desde la tabla de detalles.
title: Exportación a Adobe Target
uuid: 0eb99e6f-f0b5-495e-a3b6-df30f61378a7
exl-id: 41e885bb-182a-4983-98e8-65eec1da9fe9
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 2%

---

# Exportación a Adobe Target{#export-to-adobe-target}

{{eol}}

Exporte datos de Data Workbench a Adobe Target mediante TargetBulkUpload.exe desde la tabla de detalles.

La Data Workbench permite exportar archivos para integrarlos con Adobe Target como parte de un Adobe Experience Cloud integrado.

La variable **[!DNL TargetBulkUpload]** se encuentra en la variable *Servidor\Scripts* en los archivos de instalación del servidor. El ejecutable tiene lógica de reintentos, así como lógica adicional para optimizar el rendimiento.

Puede modificar el `TargetBulkUpload.cfg` archivo y muévalo a *Servidor/Administrador/Exportar* antes de ejecutar el script de carga. Por ejemplo, puede establecer un intervalo de tiempo de espera máximo en 720 minutos (predeterminado) para que la carga se agote después del período especificado.

**Funcionamiento**

Una vez que los datos se envían correctamente a Target, el estado de la carga se monitorea continuamente. Si la carga se realiza correctamente, se registra un mensaje de éxito. Si la carga falla o está pendiente, la supervisión continúa. Puede configurar el intervalo de tiempo de espera en la variable `TargetBulkUpload.cfg` archivo. Si la carga se atasca en Target, se registra un mensaje y se puede seguir monitorizando el estado.

Hay dos archivos de registro generados en el seguimiento para la exportación activada en [!DNL /server/Trace/]:

* `targetbulkuploadexportname.log`
* `targetbulkuploadexportname.log.completed`

La variable `targetbulkuploadexportname.log` tiene el estado detallado de todos los registros de varios lotes, el servidor Edge al que van a ir y el estado (correcto, fallido, perfil no encontrado, estado desconocido y atascado). En caso de que se descubra que algún lote está atascado, el lote no se procesa más. Hay disponible una URL por lotes atascada para rastrear el estado. Consulte el siguiente ejemplo de datos de la `targetbulkuploadexportname.log.completed` archivo:

```
1205057 total rows 
568740 successful 
62 failed 
28964 profile not found 
112169 unknown status 
492339 stuck status
```

El valor de estado atascado se incrementa con el tamaño total del lote atascado, independientemente de cuántas cargas se hayan realizado correctamente o no. El valor total de filas también se incrementa con el mismo número de tamaño de lote atascado.

>[!NOTE]
>
>Anteriormente, los datos de DWB se exportaban mediante la variable [!DNL ExportIntegration.exe]. Actualmente solo se utilizan las exportaciones MMP, CRS y S/FTP con este ejecutable. La integración de Adobe Target ahora utiliza la variable [!DNL TargetBulkUpload.exe] en Data Workbench.
