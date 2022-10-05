---
description: En esta sección se explica cómo crear claves principales (ID de seguimiento) para conjuntos de datos de Data Workbench para el diseño y la implementación de esquemas.
title: 'Procesamiento de datos: generación de clave principal'
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
exl-id: 9937038f-d011-4946-8a5b-cc724b611ae5
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 2%

---

# Procesamiento de datos: generación de clave principal{#data-processing-building-primary-key}

{{eol}}

En esta sección se explica cómo crear claves principales (ID de seguimiento) para conjuntos de datos de Data Workbench para el diseño y la implementación de esquemas.

## Explicación del ID de seguimiento {#section-24683031044a4af49988655ccb9a45fd}

Después de leer y descodificar los datos en DWB (mediante descodificadores), el primer paso es definir el ID de seguimiento y la marca de tiempo. El ID de seguimiento es un identificador que identifica de forma exclusiva un registro de cliente. Puede ser cualquier campo de la fuente, como el ID de correo electrónico, el número de la seguridad social, el ID de cookie, etc. El cliente decide el campo que se utilizará como ID de seguimiento durante la sesión de detección. El ID de seguimiento y la marca de tiempo son campos obligatorios y deben definirse para cada registro.

Normalmente, para datos en línea, ID de cookie (combinación de *x-visid_high* y* x-visid_low*) se utiliza como mecanismo predeterminado para la identificación única del cliente, sin embargo, esto se puede cambiar según los requisitos del cliente. La fecha y la hora a las que se produce la solicitud (o el evento) es la *x-timestamp*. Todos los registros de DWB se agrupan por *trackingid* y ordenadas por marca de tiempo. El campo requerido [!DNL Definitions.cfg] es un archivo de inclusión de conjunto de datos de procesamiento de registros que define los campos obligatorios : *x-trackingid* y *x-timestamp*.

Nota: *x-trackingid *en DWB es un campo integrado y este nombre no debe utilizarse para ningún otro campo.

**Ejemplo 1**: Creación *x-trackingid* uso del ID de cookie (cuando solo se utilizan datos en línea)

Para crear el *x-trackingid *en DWB mediante el ID de cookie, utilice la función Hash para crear la variable *x-trackingid* en el [!DNL foundation.cfg] (se recomienda definir el ID de seguimiento en [!DNL foundation.cfg] pero puede definirse en cualquier otro archivo de configuración en [!DNL Dataset > log processing] como se muestra:

![](assets/dwb_impl_primary_key1.png)

**Ejemplo 2**: Creación *x-trackingid* uso del ID de correo electrónico (cuando hay datos disponibles tanto en línea como sin conexión)

Suponiendo que los datos sin conexión y en línea estén disponibles (por este ejemplo), y que el ID de correo electrónico esté disponible en ambas fuentes de datos. Dado que el ID de correo electrónico identifica de forma exclusiva a un cliente, se utilizará para crear la variable *x-trackingid*.

Utilice la función hash para crear la variable *trackingId* como se muestra:

![](assets/dwb_impl_primary_key2.png)
