---
description: Ahora que el campo x-experimentar está disponible, debe crear una dimensión ampliada para incluir el campo x-experimentar en el conjunto de datos, lo que le permite ver sus resultados en Insight.
solution: Analytics,Analytics
title: Modificación de Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Modificación de Transformation.cfg{#modifying-transformation-cfg}

Ahora que el campo x-experimentar está disponible, debe crear una dimensión ampliada para incluir el campo x-experimentar en el conjunto de datos, lo que le permite ver sus resultados en Insight.

Para ello, debe añadir una nueva dimensión al archivo [!DNL Transformation.cfg] .

Si planea ejecutar varios experimentos, también debe agregar una nueva transformación Split al archivo [!DNL Transformation.cfg]. Esta transformación Split separa los diferentes nombres de experimento y de grupo para que la información sea más fácil de interpretar. Para evitar volver a procesar los datos si necesita añadir más experimentos en una fecha posterior, Adobe recomienda añadir la transformación Dividir aunque actualmente no esté planeando ejecutar varios experimentos.

El siguiente procedimiento incluye la creación de la nueva transformación Split y la dimensión ampliada. Si no desea añadir la transformación Split , simplemente omita los pasos 5-7.

**Para modificar Transformation.cfg**

1. En [!DNL Insight], abra [!DNL Profile Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, o abriendo el espacio de trabajo Administración de perfiles en la pestaña [!DNL Admin] .
1. En [!DNL Profile Manager], haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.
1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Transformation.cfg] y haga clic en **[!UICONTROL Make Local]**. En la columna [!DNL User] aparece una marca de verificación para este archivo.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparece la ventana [!DNL Transformation.cfg].
1. Haga clic en **[!UICONTROL Transformation]** para mostrar su contenido.
1. Haga clic con el botón derecho en **[!UICONTROL Transformations]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Complete la nueva división en la transformación de coma como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Puede introducir cualquier valor en el campo Nombre.

1. Haga clic con el botón derecho en **[!UICONTROL Extended Dimensions]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Complete la nueva dimensión como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Puede introducir cualquier valor en el campo Nombre.
   >* Si no se ha incluido la transformación Split , debe escribir &quot;x-experimentar&quot; en el campo [!DNL Input].


1. Haga clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Transformation.cfg] en la columna [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]** para guardar los cambios realizados localmente en el perfil de trabajo.

   >[!NOTE]
   >
   >El conjunto de datos comienza a retransformarse inmediatamente.

   Para obtener más información sobre [!DNL Transformation.cfg] y las dimensiones extendidas, consulte la *Guía de configuración del conjunto de datos*.
