---
description: nulo
solution: Analytics
title: Inicialización y actualización de la definición de esquema de un perfil
topic: Data workbench
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Inicialización y actualización de la definición de esquema de un perfil{#initializing-and-updating-a-profile-s-schema-definition}

1. Abra el **[!UICONTROL Schema Builder]** perfil que desee configurar.
1. Se mostrará un **[!UICONTROL Loading]** mensaje mientras se recupera el esquema del perfil de Insight. La duración de la carga del esquema depende de la complejidad del perfil que se esté cargando.
1. Cuando esté completo, verá un resumen de las diferencias entre el **[!UICONTROL Insight Schema]** panel izquierdo y el **[!UICONTROL Dashboard Schema]** panel derecho. Este resumen aparecerá en la parte inferior izquierda de la **[!UICONTROL Schema Builder]** ventana.

   >[!NOTE]
   >
   >Al configurar el esquema por primera vez, cada métrica, dimensión y filtro se enumerará de forma diferente al esquema del tablero. Esto se debe a que los objetos de esquema del tablero no existen en este momento.

   ![](assets/schema_builder2.png)

1. Haga clic en el **[!UICONTROL Synchronize with Schema]** botón para sincronizar todas las métricas, dimensiones y filtros desde la vista Esquema de perspectiva con la vista Esquema de tablero.
1. Cuando esté completo, debería ver un mensaje que indique que no se han encontrado diferencias:

   ![](assets/diff_found.png)

1. Si hay algún error con el esquema del tablero, como métricas y dimensiones duplicadas, debe corregirlas manualmente antes de poder guardarlas.

   >[!NOTE]
   >
   >Puede eliminar de forma selectiva cualquier métrica, dimensión o filtro del tablero **[!UICONTROL Dashboard Schema]** que no desee que aparezcan los usuarios finales del tablero. Recibirá una advertencia indicando que los elementos no están presentes en el esquema del tablero, pero no impedirá que los guarde.

1. Cuando esté listo, haga clic en **[!UICONTROL Save]** para guardar los cambios en el esquema del tablero.
1. El sistema de tableros utilizará esta definición de esquema para rellenar las dimensiones, métricas y filtros disponibles para los usuarios finales de la interfaz de tablero.
