---
description: La barra lateral proporciona acceso a las funciones que se utilizan con regularidad y conserva las visualizaciones a medida que se desplaza entre espacios de trabajo.
solution: Analytics
title: Configurar la barra lateral
topic: Data workbench
uuid: 0d2f0b9a-56a9-4f27-aaa6-1f9bf7fcab2d
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configurar la barra lateral{#configure-the-sidebar}

La barra lateral proporciona acceso a las funciones que se utilizan con regularidad y conserva las visualizaciones a medida que se desplaza entre espacios de trabajo.

Los administradores pueden personalizar una barra lateral para adaptarla a distintos grupos de usuarios y, a continuación, implementar la barra lateral con un perfil.

La barra lateral es ideal para ayudarle a realizar un seguimiento de los filtros y las anulaciones locales. Si prefiere no usar la barra lateral, puede ocultarla.

## Agregar visualizaciones a la barra lateral {#section-666f70a405db4f8d8eaffa567ffcac06}

1. Inicie Área de trabajo de datos.
1. En la barra lateral, haga clic en **[!UICONTROL Add]** > *&lt;**[!UICONTROL item]**>*. For example, [!DNL Selections Panel], [!DNL Filters Panel], or [!DNL Table].

   Los siguientes paneles de la barra lateral están disponibles en la instalación estándar de Área de trabajo de datos. Puede que haya más elementos disponibles en su perfil específico:

   * **Panel Selecciones:** Permite comprender qué selecciones están activas en el espacio de trabajo actual. Las [!DNL Selections Panel] actualizaciones se realizan cada vez que se realiza una nueva selección. Puede borrar las selecciones haciendo clic en **[!UICONTROL x]**. Consulte [Realizar selecciones en visualizaciones](../../home/c-get-started/c-vis/c-sel-vis/c-sel-vis.md#concept-012870ec22c7476e9afbf3b8b2515746) para obtener información sobre cómo seleccionar datos.
   * **Panel Filtros:** Facilita la carga y aplicación de filtros guardados. Puede cargar varios filtros y habilitar o deshabilitar cada uno de forma independiente haciendo clic en la casilla de verificación situada junto a él. Consulte Editores [de filtros](../../home/c-get-started/c-analysis-vis/c-filter-editors/c-filter-editors.md#concept-2f343ecbed8240f18b0c1f1eccef11e3).
   * **Panel de anulación local:** Este panel muestra las métricas, dimensiones y filtros presentes en el perfil que se han modificado en su copia personal del perfil. Esto le ayuda a alertar sobre posibles diferencias entre la forma en que aparecen los datos en el cliente y en la de otros usuarios. Cuando guarda los cambios en una métrica, dimensión o filtro en el servidor, la anulación se elimina del [!DNL Local Overrides panel]. Si hace clic en una anulación y, a continuación, hace clic en **[!UICONTROL Revert to Server]**, se elimina la anulación local y el elemento vuelve a la versión compartida.
   * **Leyenda de métrica:** Agrega una leyenda de métrica. [!DNL Metric legends] le permite ver las métricas de línea de base relacionadas con su perfil y las estadísticas relacionadas con el conjunto de datos (o con la selección actual, si se ha realizado una). Consulte Leyendas [de métricas](../../home/c-get-started/c-analysis-vis/c-legends/c-metric-leg.md#concept-e7195bc8f7844ae295bda3a88b028d5b).
   * **Leyenda de color:** Agrega una leyenda de color. Las visualizaciones de código de color se pueden usar en casi todas las métricas, como Conversión y retención, y se pueden usar en casi todas las [!DNL Workspace]. Vincular las métricas comerciales al color facilita la detección de anomalías, excepciones y tendencias. Consulte Leyendas [de color](../../home/c-get-started/c-analysis-vis/c-legends/c-color-leg.md#concept-f84d51dc0d6547f981d0642fc2d01358).
   * **Anotación de texto:** Agrega un panel de notas. [!DNL Text annotations] son ventanas en las que puede introducir texto arbitrario para agregar información descriptiva o comentarios a un [!DNL Workspace]. Consulte [Uso de anotaciones](../../home/c-get-started/c-analysis-vis/c-annots/c-text-annots.md#concept-55b4aa3e0c58470b8e3c9d452e12a777)de texto.
   * **Tabla:** Agrega una tabla. Una tabla puede mostrar una o más métricas en una o más dimensiones de datos. Consulte [Tablas](../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).
   * **Abrir:** Abre un archivo guardado.

## Abrir un panel de la barra lateral {#section-cbc8e57491854274a577d47a48c306b8}

Puede abrir un archivo de visualización de la barra lateral desde una ubicación guardada o desde el portapapeles.

1. En la barra lateral, haga clic en **[!UICONTROL Add]** > **[!UICONTROL Open]**.
1. Haga clic en **[!UICONTROL File]** para localizar el [!DNL .vw] archivo del panel que desea agregar o haga clic en **[!UICONTROL Last Closed Window]**, que extrae la visualización del portapapeles.

   Además, puede hacer clic en **[!UICONTROL From Clipboard]** para pegar una visualización que se haya copiado en el portapapeles. Consulte [Copia de un panel](../../home/c-get-started/c-config-sidebar.md#section-720ae057632a4b8dbb94412e06a370b1)de la barra lateral.

## Copia de un panel de la barra lateral {#section-720ae057632a4b8dbb94412e06a370b1}

1. Haga clic con el botón secundario en el borde superior del panel y, a continuación, haga clic en **[!UICONTROL Copy]** > **[!UICONTROL Window]**.
1. Para pegar el panel, haga clic en **[!UICONTROL Add]** > **[!UICONTROL Open]** > **[!UICONTROL From Clipboard]**.

## Guardar un panel de la barra lateral {#section-fb19936b12704fb0a4c592abb579db1d}

En un panel de la barra lateral, haga clic con el botón derecho en la barra de título y haga clic en **[!UICONTROL Save]**.

Del mismo modo, puede abrir una visualización de barra lateral guardada. Área de trabajo de datos guarda la visualización como un [!DNL .vw] archivo en la ubicación especificada.

## Revertir a la barra lateral predeterminada {#section-4d14b8771ad747bba799876267f24831}

En la barra lateral, haga clic en **[!UICONTROL Options]** > **[!UICONTROL Revert]**.

Al cerrar Área de trabajo de datos, el sistema guarda la configuración de la barra lateral actual en el [!DNL sidebar.vw] archivo del perfil de usuario. Al abrir Área de trabajo de datos, el sistema carga el [!DNL sidebar.vw] archivo desde el perfil de usuario, en lugar de un perfil principal.

Puede volver a una barra lateral predeterminada o guardada anteriormente, que elimina la barra lateral del perfil del usuario y vuelve a cargar la barra lateral del perfil principal. Los administradores pueden reemplazar la barra lateral predeterminada (principal) por una barra lateral local cargándola desde la [!DNL Profile Manager].

## Personalizar el archivo del panel Más estados {#section-8d502f3b59cc4331966edec05e896ce1}

Los administradores del sistema pueden crear fórmulas en el [!DNL More Status Panel.vw]. Esto coloca palabras contextuales alrededor de los valores de métrica y dimensión, y muestra los resultados en la barra [!DNL More Status panel] lateral.

Para mostrar el [!DNL More Status panel] en la barra lateral, haga clic en las flechas que se muestran en el siguiente ejemplo.

![](assets/more_status_panel_arrows.png)

El siguiente procedimiento muestra un ejemplo sencillo de cómo crear un estado personalizado que indica cuántos días hay en un conjunto de datos:

1. En la [!DNL Profile Manager], haga clic en **[!UICONTROL Barra lateral\]**.

1. En la [!DNL Base_5_3*] columna, realice una copia local del [!DNL More Status Panel.vw] archivo.

   Para ello, haga clic con el botón secundario en la marca de verificación del archivo y haga clic en **[!UICONTROL Make Local]**.

1. Abra el [!DNL More Status Panel.vw] archivo en el [!DNL .vw] Bloc de notas [!DNL Editor] .

   ![](assets/more_status_panel_file.png)

1. Complete los [!DNL Context] campos y [!DNL Items] en la [!DNL Editor]. Consulte Sintaxis [del lenguaje de](../../home/c-get-started/c-qry-lang-syntx/c-qry-lang-syntx.md#concept-15d1d3f5164a47d49468c5acb7299d9f) consulta para obtener instrucciones sobre la sintaxis.

1. Guarde el archivo.

   Los valores del ejemplo anterior dan como resultado una fórmula de estado que se muestra de la siguiente manera:

   ![](assets/more_status_panel.png)

