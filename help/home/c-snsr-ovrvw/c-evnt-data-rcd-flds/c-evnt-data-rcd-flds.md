---
description: Los archivos de registro (.vsl) contienen los campos de datos de evento que los sensores recopilan de los servidores y que el servidor de Data Workbench utiliza en el proceso de construcción del conjunto de datos.
title: Campos de registro de datos de evento (archivos .vsl)
uuid: ad9e773c-a128-4094-9e20-45a6de025c8f
exl-id: d48b593f-5a3a-4a4e-9a71-3b91024c9a48
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 2%

---

# Campos de registro de datos de evento{#event-data-record-fields}

{{eol}}

Los archivos de registro (.vsl) contienen los campos de datos de evento que los sensores recopilan de los servidores y que el servidor de Data Workbench utiliza en el proceso de construcción del conjunto de datos.

Los nombres de los campos generalmente siguen la convención de nomenclatura para el formato de archivo de registro ampliado W3C. Muchos de los campos tienen prefijos que indican el origen de la información contenida en el campo:

* &quot;cs&quot; indica la comunicación entre el cliente y el servidor
* &quot;sc&quot; indica la comunicación entre el servidor y el cliente
* &quot;s&quot; indica información del servidor
* &quot;c&quot; indica información del cliente
* &quot;x&quot; indica la información que crea un producto de Adobe
