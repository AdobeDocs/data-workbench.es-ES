---
description: Cada DPU desde la que se va a visualizar el tablero debe tener una licencia de Query API.
title: Verificación de la habilitación de la API de consulta
uuid: deedd1a4-c476-49f6-9278-556d914d2b93
exl-id: 3dde2958-0f99-45f8-b65b-207a92362292
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 5%

---

# Verificación de la habilitación de la API de consulta{#verifying-query-api-enablement}

Cada DPU desde la que se va a visualizar el tablero debe tener una licencia de Query API.

A continuación se ofrecen algunas instrucciones sobre cómo validar que la API de consulta está instalada y habilitada.

1. Busque el certificado del servidor de Data Workbench.
1. Abra este certificado en un editor de texto.
1. Asegúrese de que la línea `Product = Query API` existe en el certificado.
1. En la carpeta **[!UICONTROL Trace]**, abra [!DNL InsightServer64.log] en un editor de texto.
1. En las últimas entradas del registro de inicio, asegúrese de que aparece la línea `Enabling Query API (licensed)`.

* Si la API de consulta no está habilitada, verá la entrada `Not enabling Query API (not licensed)`.
* Si no ve ninguna entrada de registro o sospecha que el servidor de Data Workbench se ha reiniciado desde que se agregó la API de consulta, reinicie de nuevo el servidor de Data Workbench y compruebe el registro.

   Si no puede validar que la API de consulta está habilitada, póngase en contacto con Adobe ClientCare para obtener ayuda.
