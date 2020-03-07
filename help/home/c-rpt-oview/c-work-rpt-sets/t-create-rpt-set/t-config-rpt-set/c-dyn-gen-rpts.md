---
description: Puede generar informes de forma dinámica para los elementos de dimensión que especifique en un archivo de búsqueda o para un número determinado de elementos de dimensión, como para los usuarios con los 10 recuentos de orden más altos.
solution: Analytics
title: Generación dinámica de informes
topic: Data workbench
uuid: 87174fb5-e72f-4758-8e9d-1aaa784c1898
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Generación dinámica de informes{#dynamically-generating-reports}

Puede generar informes de forma dinámica para los elementos de dimensión que especifique en un archivo de búsqueda o para un número determinado de elementos de dimensión, como para los usuarios con los 10 recuentos de orden más altos.

>[!NOTE]
>
>Adobe desaconseja la creación de conjuntos de informes dinámicos para la generación diaria (o más frecuente) de informes. La generación dinámica de informes puede requerir muchos recursos si configura informes con consultas grandes o complejas.

* [Informes de elementos de dimensión de archivo de búsqueda](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-a5e8f38af06c42b4bfddec4bafbf03d6)
* [Informes de elementos de dimensión principales](../../../../../home/c-rpt-oview/c-work-rpt-sets/t-create-rpt-set/t-config-rpt-set/c-dyn-gen-rpts.md#section-d8d75a6dfadd407bb18d6f32d70ebf8f)

## Informes de elementos de dimensión de archivo de búsqueda {#section-a5e8f38af06c42b4bfddec4bafbf03d6}

Para configurar un conjunto de informes para que genere dinámicamente y (opcionalmente) distribuya informes para los elementos de una dimensión especificada en un archivo de búsqueda, especifique los siguientes parámetros en el [!DNL Report.cfg] archivo:

* [!DNL Dimension Name]
* [!DNL Lookup File]

Para obtener descripciones detalladas de estos parámetros, consulte Parámetros [de Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Para crear un conjunto de informes dinámico mediante un archivo de búsqueda**

1. Cree un archivo de búsqueda de dos columnas para una dimensión determinada. Este archivo debe contener dos columnas separadas por tabuladores, sin una fila de encabezado.

   * La columna 1 debe contener una lista de elementos de dimensión.
   * La columna 2 debe contener las direcciones de correo electrónico de los destinatarios del informe. Se envía un informe de un elemento determinado de la columna 1 a las direcciones de correo electrónico de la misma fila de la columna 2. Puede introducir varias direcciones de correo electrónico separándolas con comas (sin espacios).

      >[!NOTE]
      >
      >
      >    
      >    
      >    * Si los informes no se van a enviar por correo electrónico, la columna 2 puede estar vacía pero debe existir.
      >    * Este archivo puede contener líneas en blanco.




1. Opcional. Para habilitar el envío de informes por correo electrónico, debe hacer lo siguiente en la [!DNL Mail Report] sección del archivo [!DNL Report.cfg] para ese conjunto de informes en particular:

   * En el parámetro Servidor SMTP, enumere el servidor SMTP adecuado que se utilizará para distribuir informes por correo electrónico.
   * En el parámetro Destinatarios, muestre al menos una dirección de correo electrónico para permitir que los informes se distribuyan por correo electrónico. Los informes no se envían por correo a la dirección que aparece en la lista; este parámetro solo se configura para permitir que los informes se envíen por correo electrónico. Puede ser una dirección falsa, pero debe tener un formato permitido (por ejemplo, [!DNL jsmith@company.com]).

1. Guarde el archivo de búsqueda en la carpeta del conjunto de informes.
1. Abra el [!DNL Report.cfg] archivo del conjunto de informes.
1. En el parámetro Nombre de dimensión, escriba el nombre de la dimensión para la que desea generar dinámicamente un informe.
1. En el parámetro Archivo de búsqueda, escriba la ubicación y el nombre del archivo de búsqueda que contiene los elementos de dimensión que desea incluir en el informe y las direcciones de correo electrónico del destinatario.
1. Repita estos pasos para conjuntos de informes adicionales.

>[!NOTE]
>
>Los informes dinámicos no se envían por correo electrónico a los destinatarios hasta que se completa el conjunto de informes.

## Informes de elementos de dimensión principales {#section-d8d75a6dfadd407bb18d6f32d70ebf8f}

Para configurar un conjunto de informes para que genere informes de forma dinámica para los elementos de dimensión principales, contando según la métrica especificada, especifique los siguientes parámetros en el [!DNL Report.cfg] archivo:

* Nombre de la dimensión
* Métrica N principal
* Valor N superior
* (Opcional) Carga previa del filtro de consultas

Para obtener descripciones detalladas de estos parámetros, consulte Parámetros [de Report.cfg](../../../../../home/c-rpt-oview/c-rpt-param-ref/c-rpt-param.md#concept-838e59d72d3f4cb29ee15f5c7eb0ceff).

**Para crear un conjunto de informes dinámicos para los elementos principales**

1. Abra el [!DNL Report.cfg] archivo del conjunto de informes.
1. En el parámetro Nombre de dimensión, escriba el nombre de la dimensión para la que desea generar dinámicamente un conjunto de informes.
1. En el parámetro Métrica N superior, escriba el nombre de la métrica por la que desea ordenar la dimensión.
1. En el parámetro Valor N superior, escriba el número de elementos de dimensión que desee incluir en el conjunto de informes.
1. (Opcional) En el parámetro Preload Query Filter, escriba el nombre del filtro deseado.
1. Repita estos pasos para conjuntos de informes adicionales.
1. Para obtener información sobre el uso de una visualización dinámica de títulos con el informe, consulte la Guía *del usuario de Área de trabajo de* datos.

