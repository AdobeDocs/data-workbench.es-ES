---
description: Ahora que el campo x-experimentar está disponible, debe crear una dimensión ampliada para incluir el campo x-experimentar en el conjunto de datos, lo que le permite ver sus resultados en Insight.
solution: Analytics
title: Modificación de Transformation.cfg
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
exl-id: a9c89789-8290-4a24-91c1-ca1c5b7b437a
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 2%

---

# Modificación de Transformation.cfg{#modifying-transformation-cfg}

{{eol}}

Ahora que el campo x-experimentar está disponible, debe crear una dimensión ampliada para incluir el campo x-experimentar en el conjunto de datos, lo que le permite ver sus resultados en Insight.

Para ello, debe añadir una nueva dimensión al [!DNL Transformation.cfg] archivo.

Si planea ejecutar varios experimentos, también debe agregar una nueva transformación Dividir a la variable [!DNL Transformation.cfg] archivo. Esta transformación Split separa los diferentes nombres de experimento y de grupo para que la información sea más fácil de interpretar. Para evitar volver a procesar los datos si necesita añadir más experimentos en una fecha posterior, Adobe recomienda añadir la transformación Dividir aunque actualmente no esté planeando ejecutar varios experimentos.

El siguiente procedimiento incluye la creación de la nueva transformación Split y la dimensión ampliada. Si no desea añadir la transformación Split , simplemente omita los pasos 5-7.

**Para modificar Transformation.cfg**

1. En [!DNL Insight], abra el [!DNL Profile Manager] haciendo clic con el botón derecho en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, o abriendo el espacio de trabajo de administración de perfiles en el [!DNL Admin] pestaña .
1. En el [!DNL Profile Manager], haga clic en **[!UICONTROL Dataset]** para mostrar su contenido.
1. Haga clic con el botón derecho en la marca de verificación situada junto a [!DNL Transformation.cfg] y haga clic en **[!UICONTROL Make Local]**. Aparece una marca de verificación para este archivo en la variable [!DNL User] para abrir el Navegador.
1. Haga clic con el botón derecho en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. La variable [!DNL Transformation.cfg] se abre.
1. Haga clic en **[!UICONTROL Transformation]** para mostrar su contenido.
1. Clic con el botón derecho **[!UICONTROL Transformations]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Complete la nueva división en la transformación de coma como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Puede introducir cualquier valor en el campo Nombre.

1. Clic con el botón derecho **[!UICONTROL Extended Dimensions]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Complete la nueva dimensión como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Puede introducir cualquier valor en el campo Nombre.
   >* Si no se incluye la transformación Split , debe escribir &quot;x-experimentar&quot; en la [!DNL Input] campo .


1. Clic con el botón derecho **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En el [!DNL Profile Manager], haga clic con el botón derecho en la marca de verificación de [!DNL Transformation.cfg] en el [!DNL User] y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]** para guardar los cambios realizados localmente en el perfil de trabajo.

   >[!NOTE]
   >
   >El conjunto de datos comienza a retransformarse inmediatamente.

   Para obtener más información, consulte [!DNL Transformation.cfg] y dimensiones extendidas, consulte la *Guía de configuración de conjuntos de datos*.
