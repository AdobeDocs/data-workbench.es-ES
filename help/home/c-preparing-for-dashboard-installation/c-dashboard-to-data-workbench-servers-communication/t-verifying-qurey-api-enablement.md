---
description: Cada DPU desde la que se visualiza el tablero debe tener una licencia de Query API.
solution: Analytics
title: Verificación de la habilitación de la API de consulta
topic: Data workbench
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Verificación de la habilitación de la API de consulta{#verifying-query-api-enablement}

Cada DPU desde la que se visualiza el tablero debe tener una licencia de Query API.

A continuación encontrará algunas instrucciones sobre cómo validar que la API de consulta está instalada y habilitada.

1. Busque el certificado del servidor del área de trabajo de datos.
1. Abra este certificado en un editor de texto.
1. Asegúrese de que la línea `Product = Query API` existe en el certificado.
1. En la **[!UICONTROL Trace]** carpeta, abra el archivo [!DNL InsightServer64.log] en un editor de texto.
1. En las últimas entradas del registro de inicio, asegúrese de que `Enabling Query API (licensed)` aparece la línea.

* Si la API de consulta no está habilitada, verá la entrada `Not enabling Query API (not licensed)`.
* Si no ve ninguna entrada de registro o sospecha que el servidor del área de trabajo de datos se ha reiniciado desde que se agregó la API de consulta, reinicie el servidor del área de trabajo de datos de nuevo y compruebe el registro.

   Si no puede validar que la API de consulta está habilitada, póngase en contacto con Adobe ClientCare para obtener ayuda.
