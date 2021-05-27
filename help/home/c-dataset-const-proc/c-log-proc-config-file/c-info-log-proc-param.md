---
description: Enlaces a información adicional sobre parámetros específicos en el archivo Log Processing.cfg.
title: Parámetros de procesamiento de registros
uuid: 97b25665-f588-4f44-8f71-2382600d1b6f
exl-id: f373e954-6827-4afa-9557-73e0a884a602
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '717'
ht-degree: 2%

---

# Parámetros de procesamiento de registros{#log-processing-parameters}

Enlaces a información adicional sobre parámetros específicos en el archivo Log Processing.cfg.

<!--
c_data_filters.xml
-->

## Filtros de datos {#data-filters}

Los filtros definidos en el archivo [!DNL Log Processing.cfg] incluyen lo siguiente:

* Hora de finalización
* Umbral hash
* Hora de inicio

El filtrado definido por estos parámetros se produce después de que las entradas de registro abandonen los descodificadores y después de las transformaciones, pero antes de su evaluación por [!DNL Log Entry Condition]. En general, al cambiar cualquiera de estos parámetros se producen cambios en la composición del conjunto de datos.

La técnica recomendada para usar fuentes de datos [!DNL Sensor] para construir un conjunto de datos que cubra un período de tiempo específico es usar los parámetros Hora de inicio y Hora de finalización para el conjunto de datos.

Se prefiere utilizar los parámetros Hora de inicio y Hora de finalización en lugar de otras técnicas, como mover archivos de registro para separarlos por directorio. Al establecer las horas de inicio y finalización del conjunto de datos, el servidor de Data Workbench utiliza automáticamente solo las entradas de registro que se produjeron dentro del intervalo determinado. Suponiendo que la hora de finalización esté en el pasado, el servidor de Data Workbench suele actualizar el conjunto de datos utilizando el mismo conjunto de entradas de registro, incluso si el conjunto de datos se actualiza, por ejemplo, añadiendo una nueva transformación.

<!--
c_log_entry_con.xml
-->

## Entrada de registro

En esencia, es un proceso de filtrado en las entradas de registro disponibles. Si el [!DNL Log Entry Condition] devuelve un valor false, la entrada de registro se filtra fuera del conjunto disponible de entradas de registro.

La [!DNL Log Entry Condition] se describe mediante el uso de operaciones de condición (consulte [Conditions](../../../home/c-dataset-const-proc/c-conditions/c-abt-cond.md)) y puede utilizar cualquiera de los campos de entrada recopilados por [!DNL Sensor] (consulte la *Guía de Data Workbench [!DNL Sensor]* ) o cualquier campo ampliado producido por transformaciones contenidas en el archivo [!DNL Log Processing.cfg] para definir las condiciones de prueba. [!DNL Log Entry] se aplican durante el procesamiento del registro y, opcionalmente, se pueden aplicar durante la transformación.

Este ejemplo muestra el uso de [!DNL log entry condition] para los datos del sitio web. Puede utilizar [!DNL Log Entry Condition] para crear conjuntos de datos que se centren en una parte específica del sitio web o en visitantes que realicen alguna acción específica en el sitio.

El [!DNL Log Entry Condition] de este ejemplo crea un conjunto de datos que incluye solo las entradas de registro que forman parte del almacén del sitio. Al utilizar [!DNL RECondition test] con el patrón coincidente [!DNL "/store/.*"] y el campo [!DNL cs-uri-stem] como entrada para la expresión regular, solo se incluyen en el conjunto de datos las páginas web que comienzan con la cadena [!DNL "/store/"].

![](assets/cfg_LogProcessing_LogEntryCondition.png)

<!--
c_key_split.xml
-->

## División clave {#key-split}

El número de ID de seguimiento en el conjunto de datos aumenta artificialmente, pero el número total de entradas de registro procesadas por el servidor de Data Workbench no aumenta artificialmente, por lo que se preserva el número total de eventos contables en el conjunto de datos. Una vez divididos los datos de un solo elemento, los datos se asocian para siempre con dos ID de seguimiento diferentes y no se pueden relacionar.

Por ejemplo, si trabaja con datos web, cada ID de seguimiento representa un visitante único. Si habilita la división de claves, los visitantes del conjunto de datos con grandes cantidades de datos de evento se dividen en varios visitantes. Aunque el número de visitantes en el conjunto de datos aumenta artificialmente, el número total de eventos contables, como vistas de página o reservas, no aumenta artificialmente. Una vez divididos, los datos de los subvisitantes no pueden relacionarse.

La división de claves utiliza un algoritmo probabilístico. Como resultado, existe un equilibrio entre el uso de memoria, la probabilidad de fallo, el umbral de división de claves ( [!DNL Split Key Bytes]) y el tamaño del conjunto de datos. Con la configuración recomendada (como se indica a continuación), la tasa de errores es baja. De los elementos cuyos datos de evento superen el umbral de división de claves, aproximadamente 1 de cada 22.000 (normalmente menos de 1 por conjunto de datos) tendrán algunos de sus datos truncados en lugar de divididos.

Los valores recomendados para cada parámetro (sin y con división de claves) se muestran en la siguiente tabla.

| Parámetro | Sin división de claves | División clave |
|---|---|---|
| Bytes de clave máxima del grupo | 1e6 | 2e6 |
| Dividir espacio del bloque de claves | 6e6 | 6e6 |
| Bytes de clave divididos | 0 | 1e6 |
| Proporción de espacio de clave dividida | 10 | 10 |

[!DNL Group Maximum Key Bytes] especifica la cantidad máxima de datos de evento que se pueden procesar para un único ID de seguimiento. Los datos que exceden este límite se filtran del proceso de construcción del conjunto de datos. [!DNL Split Key Bytes] representa el número de bytes en los que se divide un único ID de seguimiento en varios elementos. Los elementos se dividen en aproximadamente este número de bytes según una distribución de probabilidad. [!DNL Split Key Space Ratio] y  [!DNL Split Key Bucket Space] controlar la utilización de la memoria y la velocidad de fallo de la división de claves.

>[!NOTE]
>
>[!DNL Group Maximum Key Bytes],  [!DNL Split Key Bytes],  [!DNL Split Key Space Ratio], y  [!DNL Split Key Bucket Space] todos deben declararse para que la división de claves funcione correctamente. No cambie los valores de estos parámetros sin consultar el Adobe.
