---
description: Los datos que desee exportar deben definirse como una dimensión dentro del perfil.
title: Creación de dimensiones para usarlas con la exportación de segmentos
uuid: 7fdc043e-b2c5-4eac-adf4-bf60df6a3953
exl-id: 0f16c242-10f6-4014-b848-ea001e9d085c
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 8%

---

# Creación de dimensiones para usarlas con la exportación de segmentos{#create-dimensions-for-use-with-segment-export}

Los datos que desee exportar deben definirse como una dimensión dentro del perfil.

Si la dimensión no existe en el perfil, debe crearla. Puede crear dimensiones mediante cualquiera de los métodos siguientes:

* Agregue una dimensión al archivo [!DNL Transformation.cfg]. Consulte la *Guía de configuración del conjunto de datos*.

* Cree un nuevo archivo [!DNL .dim]. Consulte [Creación y edición de Dimension derivados](../../../home/c-get-started/c-admin-intrf/c-prof-mgr/c-dvrd-dim.md#concept-ece3c3ea8cdf4fc796680173993bff93).

* Realice selecciones en una visualización, como un mapa de procesos o un segmento, y guarde las selecciones como una dimensión. Consulte [Guardar Dimension de mapas de proceso](../../../home/c-get-started/c-analysis-vis/c-proc-maps/t-dim-proc-maps.md#task-44d9e555d4a944e6aa81993eef703051) y [Creación de Dimension de segmento](../../../home/c-get-started/c-analysis-vis/c-seg/c-create-seg-dim.md#concept-70b363edcad14185ba8051646ad3d44e).

Para exportar un campo de datos, como ID de seguimiento o Dirección de correo electrónico (que puede tener muchos elementos), es necesario crear una dimensión denormalizada que almacene las cadenas de datos sin procesar.

Para obtener más información sobre las dimensiones denormalizadas, consulte la *Guía de configuración de conjuntos de datos*.
