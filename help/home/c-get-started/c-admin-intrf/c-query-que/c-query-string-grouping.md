---
description: La agrupación de cadenas de consulta permite integrar un gran número de campos juntos.
title: Agrupación de cadenas de consulta
uuid: 7dc5ba71-984f-4899-99d2-f79b57fb616d
exl-id: 4052cf7e-abdf-4e16-9f42-521c4e719786
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 4%

---

# Agrupación de cadenas de consulta{#query-string-grouping}

{{eol}}

La agrupación de cadenas de consulta permite integrar un gran número de campos juntos.

La agrupación de cadenas de consulta es específica para cada perfil, pero funciona bien en las transformaciones, como se muestra en este ejemplo:

1. Cree los pares que desee empaquetar añadiendo un archivo de configuración personalizado ( [!DNL E:\...\Dataset\Log Processing\SC Fields.cfg]) y, a continuación, añadir el tipo de transformación *BuildNameValuePair* como parámetro.

   ```
   2 = BuildNameValuePair:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to build)
             Name = string: Custom Events 
             Output = string: x-event-list       
   ```

1. Cree un nuevo archivo para extraer los datos condensados en los campos que desee utilizar agregando un archivo de configuración personalizado ( [!DNL E:\...\Dataset\Transformation\SC Fields Transformation.cfg]) y, a continuación, añadir el tipo de transformación *ExtractNameValuePairs* como parámetro.

   ```
   2 = ExtractNameValuePairs:  
         Comments = Comment: 0 items 
         Condition = AndCondition: 0 items 
         Delimiter = string:  
         Input Field = string: x-event-list 
         Name = string: Custom Events 
         Output Columns = vector: 1 items 
           0 = Column:  
             Column Name = string: e100 
             Field Name = string: x-cust100 
             ...  
     (all the fields you wish to extract) 
             Name = string: Custom Events 
             Output = string: x-event-list   
   ```

## Otros usos {#section-cc5d2b0c9e194fc88a5a18a06ef22f5e}

Si tiene muchos campos con evars, props y variables personalizadas, durante el procesamiento del registro puede crear un par de valor name para combinar los campos de un informe. Por ejemplo, puede crear pares de nombre-valor en campos combinados para reducir el [!DNL tempDB] tamaño del archivo.

![](assets/query_string_grouping.png)
