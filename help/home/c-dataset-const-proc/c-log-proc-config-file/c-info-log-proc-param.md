---
description: Vínculos a información adicional sobre parámetros específicos en el archivo Log Processing.cfg.
solution: Analytics
title: Parámetros de procesamiento de registros
topic: Data workbench
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
translation-type: tm+mt
source-git-commit: 27600561841db3705f4eee6ff0aeb8890444bbc9

---


# Parámetros de procesamiento de registros{#log-processing-parameters}

Vínculos a información adicional sobre parámetros específicos en el archivo Log Processing.cfg.

<!--
c_data_filters.xml
-->

## Filtros de datos {#data-filters}

Los filtros definidos en el [!DNL Log Processing.cfg] archivo incluyen lo siguiente:

* Hora de finalización
* Umbral de hash
* Hora de inicio

El filtrado definido por estos parámetros se produce después de que las entradas de registro abandonen los descodificadores y después de las transformaciones, pero antes de que los [!DNL Log Entry Condition]evalúen. En general, al cambiar cualquiera de estos parámetros se producen cambios en la composición del conjunto de datos.

La técnica recomendada para utilizar fuentes de datos [!DNL Sensor] para construir un conjunto de datos que abarque un período de tiempo específico es utilizar los parámetros Hora de inicio y Hora de finalización para el conjunto de datos.

Se prefiere utilizar los parámetros Hora de inicio y Hora de finalización en lugar de otras técnicas, como mover archivos de registro para separarlos por directorio. Al establecer las horas de inicio y finalización para el conjunto de datos, el servidor del área de trabajo de datos utiliza automáticamente sólo las entradas de registro que se produjeron dentro del intervalo determinado. Suponiendo que la hora de finalización ya no existe, el servidor del área de trabajo de datos suele actualizar el conjunto de datos con el mismo conjunto de entradas de registro, aunque el conjunto de datos se actualice, por ejemplo, agregando una nueva transformación.

<!--
c_log_entry_con.xml
-->

## Entrada de registro

En esencia, es un proceso de filtrado en las entradas de registro disponibles. Si el valor [!DNL Log Entry Condition] devuelve false, la entrada de registro se filtra fuera del conjunto de entradas de registro disponibles.

El [!DNL Log Entry Condition] se describe mediante el uso de operaciones de condición (consulte [Condiciones](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) y puede utilizar cualquiera de los campos de entrada recopilados por [!DNL Sensor] (consulte la *Guía[!DNL Sensor]del Área de Trabajo de Datos) o cualquier campo ampliado producido por transformaciones contenidas en el* [!DNL Log Processing.cfg] archivo para definir las condiciones de prueba. [!DNL Log Entry] se aplican durante el procesamiento del registro y, opcionalmente, se pueden aplicar durante la transformación.

En este ejemplo se muestra el uso de [!DNL log entry condition] para los datos del sitio web. Puede usar el [!DNL Log Entry Condition] para crear conjuntos de datos que se centren en una porción específica del sitio web o en visitantes que realicen alguna acción específica en el sitio.

El [!DNL Log Entry Condition] en este ejemplo crea un conjunto de datos que incluye solo las entradas de registro que forman parte del almacén del sitio. Al utilizar el [!DNL RECondition test] patrón coincidente [!DNL "/store/.*"] y el [!DNL cs-uri-stem] campo como entrada para la expresión regular, solo se incluyen en el conjunto de datos las páginas Web que comienzan con la cadena [!DNL "/store/"] .

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## División de clave {#key-split}

El número de ID de seguimiento en el conjunto de datos aumenta artificialmente, pero el número total de entradas de registro procesadas por el servidor del área de trabajo de datos no aumenta artificialmente, preservando así el número total de eventos contables en el conjunto de datos. Después de dividir los datos de un solo elemento, los datos se asocian para siempre con dos ID de seguimiento diferentes y no pueden relacionarse.

Por ejemplo, si trabaja con datos web, cada ID de seguimiento representa a un visitante único. Si habilita la división de claves, los visitantes del conjunto de datos con grandes cantidades de datos de eventos se dividen en varios visitantes. Aunque la cantidad de visitantes en el conjunto de datos aumenta artificialmente, la cantidad total de eventos contables, como las vistas de páginas o las reservaciones, no aumenta artificialmente. Una vez que se produce la división, los datos de los subvisitantes no pueden relacionarse.

La división de claves utiliza un algoritmo probabilístico. Como resultado, hay un equilibrio entre el uso de memoria, la probabilidad de falla, el umbral de división de claves ( [!DNL Split Key Bytes]) y el tamaño del conjunto de datos. Con la configuración recomendada (como se indica a continuación), la tasa de errores es baja. De los elementos cuyos datos de eventos exceden el umbral de división clave, aproximadamente 1 de cada 22.000 (generalmente menos de 1 por conjunto de datos) tendrá algunos de sus datos truncados en lugar de divididos.

Los valores recomendados para cada parámetro (sin y con división de claves) se muestran en la tabla siguiente.

| Parámetro | Sin división de claves | División de claves |
|---|---|---|
| Bytes de clave máxima del grupo | 1e6 | 2e6 |
| Dividir espacio del bloque de claves | 6e6 | 6e6 |
| Dividir bytes clave | 0 | 1e6 |
| Proporción de espacio clave dividida | 10 | 10 |

[!DNL Group Maximum Key Bytes] especifica la cantidad máxima de datos de eventos que se pueden procesar para un único ID de seguimiento. Los datos que excedan este límite se filtran del proceso de construcción del conjunto de datos. [!DNL Split Key Bytes] representa el número de bytes en los que un único ID de seguimiento se divide en varios elementos. Los elementos se dividen en aproximadamente este número de bytes según una distribución de probabilidad. [!DNL Split Key Space Ratio] y [!DNL Split Key Bucket Space] controlar la utilización de la memoria y la velocidad de fallo de la división de claves.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes], [!DNL Split Key Bytes], [!DNL Split Key Space Ratio], y [!DNL Split Key Bucket Space] todo debe declararse para que la división de claves funcione correctamente. No cambie los valores de estos parámetros sin consultar a Adobe.

