---
description: En esta sección se explica cómo crear claves principales (ID de seguimiento) para conjuntos de datos del área de trabajo de datos para diseño e implementación de esquemas.
title: 'Procesamiento de datos: Generación de clave principal'
uuid: 7a12950e-6ac0-47d5-b4a8-0b50c48b04fa
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Procesamiento de datos: Generación de clave principal{#data-processing-building-primary-key}

En esta sección se explica cómo crear claves principales (ID de seguimiento) para conjuntos de datos del área de trabajo de datos para diseño e implementación de esquemas.

## Explicación de la ID de seguimiento {#section-24683031044a4af49988655ccb9a45fd}

Después de leer y descodificar los datos en DWB (mediante descodificadores), el primer paso es definir el Id. de seguimiento y la marca de tiempo. El ID de seguimiento es un identificador que identifica de forma exclusiva un registro de cliente. Puede ser cualquier campo de la fuente, como ID de correo electrónico, Número de seguridad social, ID de cookie, etc. El cliente decide el campo que se utilizará como ID de seguimiento durante la sesión de detección. La ID de seguimiento y la marca de hora son campos obligatorios que deben definirse para cada registro.

Normalmente, para los datos en línea, el ID de la cookie (combinación de *x-visid_high* y* x-visid_low*) se utiliza como mecanismo predeterminado para la identificación del cliente único. Sin embargo, esto se puede cambiar según los requisitos del cliente. La fecha y la hora en que se produce la solicitud (o evento) es la marca de tiempo *x*. Todos los registros de DWB se agrupan por *trackingid* y se ordenan por marca de tiempo. El archivo de campo requerido [!DNL Definitions.cfg] es un archivo de inclusión de conjunto de datos de procesamiento de registros que define los campos obligatorios: *x-trackingid* y *x-timestamp*.

Nota: *x-trackingid *en DWB es un campo integrado y este nombre no debe usarse para ningún otro campo.

**Ejemplo 1**: Creación de *x-trackingid* mediante un ID de cookie (cuando solo se utilizan datos en línea)

Para crear el *x-trackingid *en DWB mediante el ID de cookie, utilice la función Hash para crear el *x-trackingid* en el [!DNL foundation.cfg] archivo (se recomienda definir el ID de seguimiento en [!DNL foundation.cfg] pero se puede definir en cualquier otro archivo de configuración en la [!DNL Dataset > log processing] carpeta) como se muestra a continuación:

![](assets/dwb_impl_primary_key1.png)

**Ejemplo 2**: Creación de *x-trackingid* mediante ID de correo electrónico (cuando los datos en línea y sin conexión están disponibles)

Supongamos que los datos en línea y sin conexión están disponibles (por ejemplo, este ejemplo) y el ID de correo electrónico está disponible en ambas fuentes de datos. Dado que el ID de correo electrónico identifica exclusivamente a un cliente, se utilizará para crear el *x-trackingid*.

Utilice la función Hash para crear el *trackingId* como se muestra:

![](assets/dwb_impl_primary_key2.png)

