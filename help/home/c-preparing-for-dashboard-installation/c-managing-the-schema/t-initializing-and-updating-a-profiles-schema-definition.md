---
description: Inicialización y actualización de la definición de esquema de un perfil
title: Inicialización y actualización de la definición de esquema de un perfil
uuid: 38e47ded-340e-4f65-b06c-f2e2254f0863
exl-id: e8190909-4416-4d4a-8901-130d01906773
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 7%

---

# Inicialización y actualización de la definición de esquema de un perfil{#initializing-and-updating-a-profile-s-schema-definition}

{{eol}}

1. Abra el **[!UICONTROL Schema Builder]** para el perfil que desea configurar.
1. A **[!UICONTROL Loading]** se mostrará mientras se recupera el esquema del perfil de Insight. El tiempo para cargar el esquema depende de la complejidad del perfil que se esté cargando.
1. Cuando termine, verá un resumen de las diferencias entre los **[!UICONTROL Insight Schema]** en el panel izquierdo y en la **[!UICONTROL Dashboard Schema]** en el panel derecho. Este resumen aparece en la parte inferior izquierda del **[!UICONTROL Schema Builder]** ventana.

   >[!NOTE]
   >
   >Al configurar el esquema por primera vez, cada métrica, dimensión y filtro se enumerarán de forma diferente al esquema del panel. Esto se debe a que los objetos de esquema del panel no existen en este momento.

   ![](assets/schema_builder2.png)

1. Haga clic en el **[!UICONTROL Synchronize with Schema]** para sincronizar todas las métricas, dimensiones y filtros de la vista Esquema de perspectiva con la vista Esquema de tablero.
1. Cuando termine, debería ver un mensaje que indique que no se han encontrado diferencias:

   ![](assets/diff_found.png)

1. Si hay algún error con el esquema del panel (como métricas y dimensiones duplicadas), debe corregirlo manualmente antes de poder guardar.

   >[!NOTE]
   >
   >Puede eliminar selectivamente cualquier métrica, dimensión o filtro del **[!UICONTROL Dashboard Schema]** que no desea que aparezcan para los usuarios finales del tablero. Recibirá una advertencia que indica que los elementos no están presentes en el esquema del panel, pero que no impedirá que los guarde.

1. Cuando esté listo, haga clic en **[!UICONTROL Save]** para guardar los cambios en el esquema del panel.
1. El sistema de tableros utilizará esta definición de esquema para rellenar las dimensiones, métricas y filtros disponibles para los usuarios finales de la interfaz de tablero.
