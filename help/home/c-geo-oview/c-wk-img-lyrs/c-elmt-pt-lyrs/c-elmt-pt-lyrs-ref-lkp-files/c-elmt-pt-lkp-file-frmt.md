---
description: Información sobre las columnas de la capa de puntos del elemento.
solution: Analytics
title: Formato del archivo de búsqueda de puntos de elemento
topic: Data workbench
uuid: 3480b9f3-35cd-40b7-aac9-15a3e2f19c1c
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Formato del archivo de búsqueda de puntos de elemento{#element-point-lookup-file-format}

Información sobre las columnas de la capa de puntos del elemento.

El archivo de búsqueda de capas de puntos de elemento debe contener al menos las tres columnas siguientes:

* **[!DNL Key]columna:**Esta columna debe contener datos de clave comunes, lo que permite al servidor del área de trabajo de datos conectar los datos del archivo de búsqueda con los del conjunto de datos. La[!DNL Key]columna debe ser la primera columna del archivo de búsqueda. Cada fila de esta columna identifica un elemento de la dimensión.

* **[!DNL Longitude]columna:**Esta columna debe contener la longitud de cada punto de datos de la[!DNL Key]columna.

* **[!DNL Latitude]columna:**Esta columna debe contener la latitud de cada punto de datos de la[!DNL Key]columna.

* **[!DNL Name]columna:**(Opcional). Si desea especificar un nombre que se mostrará en el mapa para cada punto de datos, puede incluir una[!DNL Name]columna en el archivo de búsqueda.

Cada fila del archivo de [!DNL Zip Points.txt] búsqueda contiene un código postal en la primera columna seguido de la longitud, la latitud y el nombre de ciudad asociado.

```
tude, and associated city name.
ZIP_CODE LATITUDE LONGITUDE NAME
00210 +43.005895 -071.013202 PORTSMOUTH, NH
00211 +43.005895 -071.013202 PORTSMOUTH, NH
...
```

