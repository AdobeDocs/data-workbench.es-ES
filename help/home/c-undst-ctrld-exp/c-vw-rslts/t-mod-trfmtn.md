---
description: Ahora que el campo x-experience está disponible, debe crear una dimensión ampliada para incluir el campo x-experience en el conjunto de datos, lo que le permite ver los resultados en Insight.
solution: Insight,Analytics
title: Modificación de Transformation.cfg
topic: Data workbench
uuid: c17e48db-8fd9-4640-b621-6963bb8223d7
translation-type: tm+mt
source-git-commit: 72761a57e4bb9f230581b2cd37bff04ba7be8e37

---


# Modificación de Transformation.cfg{#modifying-transformation-cfg}

Ahora que el campo x-experience está disponible, debe crear una dimensión ampliada para incluir el campo x-experience en el conjunto de datos, lo que le permite ver los resultados en Insight.

Para ello, debe agregar una nueva dimensión al [!DNL Transformation.cfg] archivo.

Si planea ejecutar varios experimentos, también debe agregar una nueva transformación Dividir al [!DNL Transformation.cfg] archivo. Esta transformación Dividir separa los distintos nombres de experimento y grupo para que la información sea más fácil de interpretar. Para evitar volver a procesar los datos si necesita agregar más experimentos en una fecha posterior, Adobe recomienda agregar la transformación Dividir aunque no tenga previsto ejecutar varios experimentos.

El siguiente procedimiento incluye la creación de la nueva transformación Split y la dimensión ampliada. Si no desea agregar la transformación Dividir, simplemente omita los pasos 5-7.

**Para modificar Transformation.cfg**

1. En [!DNL Insight], abra la [!DNL Profile Manager] ficha haciendo clic con el botón secundario en un espacio de trabajo y haciendo clic en **[!UICONTROL Admin]** > **[!UICONTROL Profile Manager]**, o bien, abriendo el espacio de trabajo Administración de perfiles en la [!DNL Admin] ficha.
1. En el [!DNL Profile Manager], haga clic **[!UICONTROL Dataset]** para mostrar su contenido.
1. Haga clic con el botón secundario en la marca de verificación situada junto a [!DNL Transformation.cfg] y haga clic en **[!UICONTROL Make Local]**. En la [!DNL User] columna aparece una marca de verificación para este archivo.
1. Haga clic con el botón secundario en la marca de verificación recién creada y haga clic en **[!UICONTROL Open]** > **[!UICONTROL in Insight]**. Aparecerá la [!DNL Transformation.cfg] ventana.
1. Haga clic en **[!UICONTROL Transformation]** para mostrar su contenido.
1. Haga clic con el botón derecho **[!UICONTROL Transformations]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL Split]**.
1. Complete la nueva división en la transformación de coma, como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/New_split_transformation.png)

   >[!NOTE]
   >
   >Puede introducir cualquier valor en el campo Nombre.

1. Haga clic con el botón derecho **[!UICONTROL Extended Dimensions]** y haga clic en **[!UICONTROL Add new]** > **[!UICONTROL ManyToMany]**.
1. Complete la nueva dimensión como se muestra en el siguiente ejemplo:

   ![Información sobre los pasos](assets/New_Dimension_controlled_experiment_groups.png)

   >[!NOTE]
   >
   >* Puede introducir cualquier valor en el campo Nombre.
   >* Si no se incluye la transformación Dividir, debe escribir &quot;x-experience&quot; en el [!DNL Input] campo.


1. Haga clic con el botón secundario **[!UICONTROL (modified)]** en la parte superior de la ventana y haga clic en **[!UICONTROL Save]**.
1. En la [!DNL Profile Manager], haga clic con el botón secundario en la marca de verificación de [!DNL Transformation.cfg] la [!DNL User] columna y, a continuación, haga clic en **[!UICONTROL Save to]** > **[!UICONTROL profile name]** para guardar los cambios realizados localmente en el perfil de trabajo.

   >[!NOTE]
   >
   >El conjunto de datos comienza a retransformarse inmediatamente.

   Para obtener más información sobre [!DNL Transformation.cfg] y dimensiones extendidas, consulte la Guía *de configuración de* Dataset.
