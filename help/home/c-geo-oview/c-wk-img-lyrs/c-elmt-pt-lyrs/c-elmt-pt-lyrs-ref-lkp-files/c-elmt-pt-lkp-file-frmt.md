---
description: Información sobre las columnas de capa de punto de elemento.
title: Formato del archivo de búsqueda de puntos de elemento
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
exl-id: da81da9e-0567-4f3a-bc0d-ab6c5e4a23b7
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 6%

---

# Formato del archivo de búsqueda de puntos de elemento{#element-point-lookup-file-format}

{{eol}}

Información sobre las columnas de capa de punto de elemento.

El archivo de búsqueda de capas de punto de elemento debe contener al menos las tres columnas siguientes:

* **[!DNL Key]columna:** Esta columna debe contener datos clave comunes, lo que permite al servidor de Data Workbench conectar los datos del archivo de búsqueda con los del conjunto de datos. La variable [!DNL Key] debe ser la primera columna del archivo de búsqueda. Cada fila de esta columna identifica un elemento de la dimensión.

* **[!DNL Longitude]columna:** Esta columna debe contener la longitud de cada punto de datos del [!DNL Key] para abrir el Navegador.

* **[!DNL Latitude]columna:** Esta columna debe contener la latitud de cada punto de datos del [!DNL Key] para abrir el Navegador.

* **[!DNL Name]columna:** (Opcional). Si desea especificar un nombre que se mostrará en el mapa para cada punto de datos, puede incluir un [!DNL Name] en el archivo de búsqueda.

Cada fila de la [!DNL Zip Points.txt] el archivo de búsqueda contiene un código postal en la primera columna seguido de longitud, latitud y nombre de ciudad asociado.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```
