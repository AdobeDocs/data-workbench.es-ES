---
description: Las visualizaciones de tablas de latencia son tablas que incluyen una dimensión de latencia, que es un tipo de dimensión derivada que mide el tiempo transcurrido desde que se produjo un evento en particular.
title: Tablas de latencia
uuid: 8081540c-f96c-424e-802d-05d1be5a728d
exl-id: 22f6d52f-e1c2-430a-9e69-3440be0ecdea
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 1%

---

# Tablas de latencia{#latency-tables}

{{eol}}

Las visualizaciones de tablas de latencia son tablas que incluyen una dimensión de latencia, que es un tipo de dimensión derivada que mide el tiempo transcurrido desde que se produjo un evento en particular.

Para definir el evento, realice selecciones dentro de una o varias visualizaciones y establezca dichas selecciones como el evento mediante la opción de menú contextual Definir evento . Las tablas de latencia son especialmente útiles para realizar el seguimiento de la actividad relacionada con una campaña o con un orden de cliente concreto en el que está buscando una correlación horaria.

En [!DNL Site], las tablas de latencia proporcionan información sobre las sesiones de visitante que se produjeron siete días antes o después del evento, pero se pueden configurar tablas de latencia para proporcionar información sobre diferentes dimensiones de tiempo y recuento. Consulte [Configuración de tablas de latencia](../../../home/c-get-started/c-intf-anlys-ftrs/c-config-ltcy-tbls/c-config-ltcy-tbls.md#concept-7175c3defec64556994f0dfcccb7d15c).

Los elementos de la dimensión principal, como una sesión, que forman parte del evento específico seleccionado, tienen una latencia de cero. Todos los demás elementos son latencias asignadas que reflejan la distancia (en la dimensión de tiempo adecuada) respecto al evento.

El siguiente ejemplo ilustra cómo se puede usar la tabla de latencia.

**Identificar eventos de valor en relación con una campaña**

Supongamos que desea realizar un seguimiento de la actividad de los clientes durante los siete días anteriores y posteriores a la respuesta a una campaña publicitaria determinada. Para ver la latencia de una campaña publicitaria en particular, establecería la campaña de interés como el evento para la tabla de latencia.

La latencia en el espacio de trabajo siguiente se basa en la selección de Campaign 11566 (las sesiones en respuesta a esta campaña).

![](assets/vis_Latency.png)

Una latencia de &quot;+0 días&quot; identifica las sesiones en respuesta a Campaign 11566, así como todas las demás sesiones para los mismos clientes que se produjeron el mismo día.

Una latencia de &quot;-2 días&quot; identifica las sesiones de los mismos clientes que se produjeron dos días antes de que los clientes respondieran a la campaña.

Una latencia de &quot;+7 días&quot; identifica las sesiones de los mismos clientes que se produjeron siete días después de responder a la campaña.

Además de los procedimientos enumerados en las secciones siguientes, puede realizar todas las tareas que se pueden realizar en una tabla, como ordenar elementos, enmascarar elementos, agregar una leyenda de serie, exportar datos, etc. Para obtener más información, consulte [Tablas](../../../home/c-get-started/c-analysis-vis/c-tables/c-tables.md#concept-c632cb8ad9724f90ac5c294d52ae667f).

## Crear una tabla de latencia {#section-31a03031d9854ef7acc2462d4f37678d}

Para crear una tabla de latencia, comience haciendo una selección y, a continuación, estableciendo esa selección como el evento para el que desea rastrear la latencia.

1. Haga clic con el botón derecho en un espacio de trabajo y abra las visualizaciones deseadas, que deben estar basadas en la dimensión contable utilizada para configurar la tabla de latencia.

   Por ejemplo, en [!DNL Site] las visualizaciones deberían estar basadas en sesiones.

1. Abra una tabla de latencia en blanco.
1. Realice una selección en el espacio de trabajo.
1. Haga clic con el botón derecho en la tabla de latencia y haga clic en **[!UICONTROL Set Event]**.

![](assets/vis_Latency_SetEvent.png)

>[!NOTE]
>
>Los eventos que seleccione no se conservan a menos que guarde las selecciones como una dimensión de latencia. Para ver los pasos, consulte [Reutilización de un Dimension de latencia](../../../home/c-get-started/c-analysis-vis/c-lat-tbls.md#section-29c6483bf9ba476fb1c24ad1df253f46).

## Reutilización de una tabla de latencia {#section-05f741169d204213b6537dce553e4f73}

Si desea volver a utilizar la misma tabla de latencia, puede guardar la tabla de latencia localmente o si tiene los permisos adecuados, puede guardarla en el servidor para que puedan acceder todos los usuarios de un perfil en particular.

**Guardar la tabla de latencia para usarla en otros espacios de trabajo**

1. Haga clic con el botón derecho en el borde superior de la visualización y haga clic en **[!UICONTROL Save]**. La variable [!DNL Save] se abre. La ubicación de guardado predeterminada es User\*profile name*\Work folder.
1. En el [!DNL File name] , escriba un nombre descriptivo para la visualización y haga clic en **[!UICONTROL Save]**.

**Para recuperar la tabla de latencia guardada**

1. Haga clic con el botón derecho en el espacio de trabajo y haga clic en **[!UICONTROL Open]** > **[!UICONTROL File]**. La variable [!DNL Open Visualization] se abre.
1. Vaya a la tabla de latencia que guardó.
1. Seleccione el archivo de visualización de tabla de latencia ( [!DNL *.vw]) y haga clic en **[!UICONTROL Open]**.

## Reutilización de una dimensión de latencia {#section-29c6483bf9ba476fb1c24ad1df253f46}

Si desea utilizar de nuevo la misma dimensión de latencia, puede guardar la dimensión de latencia localmente o si tiene los permisos adecuados, puede guardarla en el servidor para que puedan acceder todos los usuarios de un perfil en particular.

Las dimensiones de latencia que cree se guardarán en el directorio de Dimension del perfil y estarán disponibles en el [!DNL Change Dimension] lista desplegable dentro de la Data Workbench.

**Para guardar la dimensión de latencia para usarla en otros espacios de trabajo**

1. Haga clic con el botón derecho en el [!DNL Latency] etiqueta de columna o uno de sus elementos y haga clic en **[!UICONTROL Save Dimension]**. La variable [!DNL Save Dimension As] se abre.
1. Seleccione o cree el subdirectorio correspondiente dentro del directorio de Dimension.
1. En el [!DNL File name] , escriba un nombre descriptivo para la dimensión (por ejemplo, [!DNL Latency for Campaign 11565.dim]) y haga clic en **[!UICONTROL Save]**.

**Para recuperar la dimensión de latencia guardada**

1. Haga clic con el botón derecho en el espacio de trabajo y haga clic en **[!UICONTROL Open]** > **[!UICONTROL File]**. La variable [!DNL Open Visualization] se abre.
1. Vaya a la visualización de latencia que guardó en la carpeta Usuario\*nombre de perfil*\Dimension.
1. Seleccione el archivo de dimensión de latencia ( [!DNL *.dim]) y haga clic en **[!UICONTROL Open]**.

## Exportación a Microsoft Excel {#section-3dffa5c3aab14cdaa40c78b81b08fe53}

Para obtener información sobre la exportación de ventanas, consulte [Exportación de datos de ventana](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).

## Exportación a un archivo TSV {#section-fd921f351c994ed0a94f63d3bd5b5a87}

Para obtener información sobre la exportación de ventanas, consulte [Exportación de datos de ventana](../../../home/c-get-started/c-wk-win-wksp/c-exp-win-data.md#concept-8df61d64ed434cc5a499023c44197349).
