---
description: Los filtros de perfil limitan el alcance de los datos disponibles en un conjunto de datos.
title: Filtros de perfil integrados
uuid: d6854d2c-4643-476e-8a44-f188e18cb115
exl-id: bb167487-415d-44a8-9a0a-9a76d90ba5c0
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 1%

---

# Filtros de perfil integrados{#built-in-profile-filters}

Los filtros de perfil limitan el alcance de los datos disponibles en un conjunto de datos.

Además de los filtros de transformación y procesamiento de registros que se pueden aplicar antes o durante la creación de un conjunto de datos, hay otros filtros de perfil disponibles que afectan al alcance de los datos disponibles para su selección desde un conjunto de datos. Esta sección describe únicamente el último tipo de filtros especiales.

Los siguientes filtros de perfil están disponibles para el usuario después de crear un conjunto de datos:

* Filtro de subconfiguración de datos
* Filtro de sesión interrumpido

>[!NOTE]
>
>Se pueden crear y aplicar filtros adicionales mediante su presencia en el directorio Filters de un perfil.

## Subconjunto de datos {#section-0defb44315d94254ab6e629ec3d6f420}

Un subconjunto de datos actúa como filtro de datos al permitirle seleccionar solo los elementos de dimensión de datos que le interesen.

La creación de subconjuntos de datos disminuye el tiempo necesario para calcular las respuestas exactas a las consultas. Si el subconjunto de datos especificado es lo suficientemente pequeño, la Data Workbench puede recuperar todos los datos necesarios de Insight Server y responder preguntas sobre el subconjunto de forma rápida y precisa. Esto resulta especialmente útil si sabe que, por ejemplo, analizar un día de datos o sesiones de un referente en particular requerirá varias horas.

Los usuarios pueden crear subconjuntos de datos ellos mismos o acceder a subconjuntos de datos definidos en un perfil heredado o en funcionamiento. Cuando un usuario crea un subconjunto del conjunto de datos (seleccionando los datos deseados en Insight y luego haciendo clic con el botón derecho en el espacio de trabajo y haciendo clic en Datos > Subconjunto), se crea un archivo Subconjunto.filtro de datos en la carpeta Filtros del directorio de perfiles de usuario. Este filtro define el subconjunto de datos que ha seleccionado y guarda el subconjunto para su uso futuro.

>[!NOTE]
>
>Puede crear varios subconjuntos de datos y conmutarlos para que vean distintas partes de los datos. Recuerde desactivar la subconfiguración de datos cuando desee ver todos los datos. De lo contrario, los valores de las métricas no serán representativos de todos los datos del conjunto de datos.

## Filtro de sesión roto {#section-1608e97da6464b11aea27cbb7f3160e4}

El filtro de sesión interrumpida es una fórmula de métrica que se puede modificar fácilmente para satisfacer cualquier requisito de filtrado. En los perfiles predeterminados del sitio, el filtro de sesión interrumpida está configurado para incluir a todos los visitantes que tengan un indicador visitado establecido en 1. El valor 1 indica la presencia de una cookie de seguimiento para ese visitante.

A continuación, se muestra el texto del archivo Filter.filter predeterminado de sesión rota proporcionado por Adobe en el paquete de versión para los perfiles del sitio.

```
entity = derived_filter:
   formula = string: Visitorized_Flag="1"
   model = ref: wdata/model
```

De forma predeterminada, los espacios de trabajo tienen el filtro Sesión rota aplicado tanto a su selección como a sus puntos de referencia, y se puede alternar haciendo clic con el botón derecho en el espacio de trabajo y haciendo clic en Datos > Filtro de sesión roto.

Se puede hacer referencia al Filtro de sesión interrumpido en expresiones de filtro como Broken_Session_Filter, aunque no esté habilitado para el espacio de trabajo actual. Consulte [expresiones de filtro](https://docs.adobe.com/content/help/en/data-workbench/using/client/t-open-ins.html#Syntax_for_Identifiers) para obtener más información.
