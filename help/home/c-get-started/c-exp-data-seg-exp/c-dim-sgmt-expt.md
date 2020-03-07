---
description: Cualquier dato que desee exportar debe definirse como una dimensión dentro del perfil.
solution: Analytics
title: Crear dimensiones para usarlas con la exportación de segmentos
topic: Data workbench
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Crear dimensiones para usarlas con la exportación de segmentos{#create-dimensions-for-use-with-segment-export}

Cualquier dato que desee exportar debe definirse como una dimensión dentro del perfil.

Si la dimensión no existe en el perfil, debe crearla. Puede crear dimensiones mediante cualquiera de los siguientes métodos:

* Agregue una dimensión al [!DNL Transformation.cfg] archivo. Consulte la Guía *de configuración de Dataset*.

* Create a new [!DNL .dim] file. Consulte [Creación y edición de dimensiones derivadas](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Realice selecciones en una visualización, como un mapa de procesos o un segmento, y guarde las selecciones como una dimensión. Consulte [Guardar dimensiones desde mapas](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) de proceso y [Creación de dimensiones](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e)de segmento.

La exportación de un campo de datos como ID de seguimiento o Dirección de correo electrónico (que puede tener muchos elementos) requiere que cree una dimensión denormalizada que almacene las cadenas de datos sin procesar.

Para obtener más información sobre las dimensiones denormalizadas, consulte la Guía *de configuración de* Dataset.
