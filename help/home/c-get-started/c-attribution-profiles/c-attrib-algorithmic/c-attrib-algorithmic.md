---
description: La atribución de mejor ajuste es un método de aprendizaje automático para asignar valores de atribución a través de los diferentes canales de un evento de conversión exitoso. La Data Workbench evalúa automáticamente las contribuciones al éxito en una ventana de tiempo por canal y, a continuación, crea un modelo de atribución basado en los patrones de interacción reales de los clientes.
title: Atribución de mejor ajuste
uuid: 0c51beb3-8f74-4f8e-9722-0c885140c8ce
exl-id: 225a54d0-370c-4274-8a87-dc287bbb8201
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '1141'
ht-degree: 0%

---

# Atribución de mejor ajuste{#best-fit-attribution}

{{eol}}

La atribución de mejor ajuste es un método de aprendizaje automático para asignar valores de atribución a través de los diferentes canales de un evento de conversión exitoso. La Data Workbench evalúa automáticamente las contribuciones al éxito en una ventana de tiempo por canal y, a continuación, crea un modelo de atribución basado en los patrones de interacción reales de los clientes.

**[!UICONTROL Best Fit Attribution]** permite comparar las interacciones o los toques que han contribuido a una venta correcta, al registro por correo electrónico u otros indicadores de rendimiento. El análisis de atribución asigna peso automáticamente a los toques más importantes y proporciona un modelo de atribución por canal en función de sus datos y según sus protocolos internos y de mercado.

![](assets/attrib_windows_5.png)

Por ejemplo, si un cliente visita su sitio a través de una búsqueda orgánica, luego se involucra con una campaña y luego se registra en un correo electrónico, [atribución basada en reglas](/help/home/c-get-started/c-attribution-profiles/c-rules-attrib/c-rules-attrib.md) identificaría el primer contacto o el último contacto, o distribuiría uniformemente la atribución de éxito entre todos los puntos de contacto mediante modelos de atribución preestablecidos. Cuando el usuario define la atribución basada en reglas, los atributos Mejor ajuste establecen valores mediante un algoritmo calculando la probabilidad de una conversión como una función de los puntos de contacto observados.

>[!NOTE]
>
>Para ejecutar **Atribución de mejor ajuste** en Data Workbench, debe actualizar el certificado del servidor ( [!DNL .pem file]) para admitir Adobe Analytics Premium. También debe agregar **Premium** a su [!DNL Profile.cfg] para el cliente y reciba nuevos certificados de Adobe ClientCare para el servidor y el servidor de informes.

## Configuración básica {#section-db597eaee462412ea7280d1426366c61}

Consulte [Generar una atribución de mejor ajuste](../../../../home/c-get-started/c-attribution-profiles/c-attrib-algorithmic/c-attrib-building.md#concept-fede6fc4f592475fa8b351b1765a522d) para obtener instrucciones paso a paso.

**Establecer la métrica de éxito**
Defina una métrica que represente un evento de éxito.

![](assets/attrib_windows_1.png)

La métrica de éxito suele ser *Pedidos*, aunque puede aprovechar la Data Workbench para definir una métrica de éxito muy compleja junto con la ventana de éxito.

**Establecer la métrica Táctil** (opcional)

Identifique las interacciones para rastrear que llevaron a una conversión exitosa y luego establezca la métrica Táctil sobre la cual se calculará la atribución.

>[!NOTE]
>
>La configuración de una métrica táctil solo es necesaria si la utiliza para derivar métricas de canal de elementos Dimension de arrastrar y soltar en lugar de utilizar métricas de canal existentes.

Si no tiene una métrica definida para campañas o canales, pero tiene dimensiones que representan canales, la atribución de mejor ajuste puede crearlas automáticamente en función de la métrica de contacto.

Por ejemplo, con la métrica táctil configurada como *Visitas* y a una dimensión denominada *Tipo de medio* con elementos que incluyen *Correo electrónico*, *Comunicado de prensa*, *Imprimir publicidad* y *Medios sociales*, la visualización generará métricas de canal del formulario [!DNL Hits where Media Type = Email] cuando arrastra y suelta los elementos en la visualización.

![](assets/attrib_windows_2.png)

A continuación, la métrica Táctil determina la asignación de puntuaciones de atribución para identificar las interacciones de marketing que se consideran influyentes para el éxito, lo que le permite calificar los toques de marketing para la población identificada en la ventana Éxito. Puede establecer métricas como *Vistas de páginas* o *Visitas* o usar métricas táctiles personalizadas específicas de sus necesidades.

En muchos casos, la ventana de contacto debe incluir la ventana de éxito para evaluar un largo tiempo de espera en el ciclo de ventas.

**Establezca la métrica Ingresos .**

Puede optar por identificar los ingresos entre puntos de contacto estableciendo una métrica de ingresos adecuada. Si se especifica, el modelo mostrará la distribución de los ingresos a través de los canales de entrada. ![](assets/attrib_windows_6.png)

Puede establecer una métrica de ingresos con tipos de datos de moneda para asignar el éxito a todos los puntos de contacto principales definidos y analizados. Esta métrica desglosa los ingresos de ventas finales y asigna según la ponderación asignada por el algoritmo.

**Establezca las ventanas de éxito y táctil.**

La ventana Éxito define la población que se va a examinar y el periodo para los eventos de éxito, lo que permite indicar las ventanas de tiempo y amplitud de población que se deben tener en cuenta para el análisis mediante una selección de espacio de trabajo. La variable **Correcto** define el periodo y la población que se deben examinar para los eventos de éxito. La variable **Táctil** especifica el período de tiempo histórico que se debe examinar para las interacciones de canal que preceden a los eventos de éxito.

>[!NOTE]
>
>La configuración de una métrica táctil solo es necesaria si está intentando crear métricas de éxito automáticamente arrastrando elementos de dimensión a la visualización.

Puede establecer un día, mes, año o cualquier lapso de tiempo disponible para restringir la evaluación de eventos de éxito y de contacto a lo largo del ciclo de ventas o para audiencias específicas que entren en el sitio. La creación de ventanas para limitar la atribución permite centrar el análisis en los períodos de tiempo relevantes para sus necesidades específicas.

![](assets/attrib_windows_4.png)

En muchos casos, es recomendable que la ventana de contacto incluya la ventana de éxito para que pueda ampliar el análisis a lo largo de un largo periodo de tiempo en función de su ventana de ventas. O puede rastrear y analizar los toques independientemente del evento de éxito.

**Seleccione los Canales.**

Al introducir canales, tiene dos opciones.

**Agregar la métrica táctil y agregar elementos de Dimension a los canales**

En muchos casos, es recomendable desglosar los puntos de contacto principales por elementos de dimensión para definir canales específicos. En función de los valores del elemento, la atribución de mejor ajuste seleccionará automáticamente los de mayor rendimiento y los clasificará según el porcentaje y los mostrará en una visualización de gráfico.

![](assets/attrib_windows_7.png)

Se creará un modelo de atribución dibujando a los visitantes que interactuaron durante la ventana de éxito y examinando el canal Tocos durante la ventana Táctil que produjo o no un evento exitoso.

## Desglose por canales {#section-a30592b84bc84f57bd2b988824e852d4}

Al introducir canales, tiene dos opciones:

* Agregue un **Métrica táctil** y, a continuación, agregue **Elementos de Dimension** para los canales.

   **o**

* Cree métricas que filtren para los elementos de canal que desee evaluar.

**Opción 1: Agregar una métrica táctil y agregar elementos Dimension para los canales**.

Este es el enfoque más fácil. Atribución de mejor ajuste crea las métricas automáticamente para evaluar la atribución. En el ejemplo siguiente, la métrica táctil es ***Visitas*** y los canales son: ***Mostrar campañas***, ***Campañas de correo electrónico*** y ***Campañas SEM***.

Con este método, la atribución de mejor ajuste crea una métrica en segundo plano para evaluar la atribución en los canales (pero nunca ve la métrica generada automáticamente y no se guardan). En el ejemplo siguiente, se crean tres métricas donde las visitas se filtran para cada uno de los tres canales (por ejemplo, *Mostrar campañas*, *Campañas de correo electrónico* y *Campañas SEM*). Esto es más fácil porque permite que la Atribución de mejor ajuste cree las métricas por usted.

![](assets/attrib_touch_add_dims.png)

**Opción 2: Crear una métrica**.

En la segunda opción, se crean y guardan las métricas de los canales que se desea evaluar filtrando un canal específico. A continuación se muestra un ejemplo de una métrica de este tipo.

![](assets/attrib_create_metric.png)

A continuación, en lugar de introducir elementos de Dimension y métricas táctiles para los canales, puede hacer clic en la barra de menús de la visualización y seleccionar **Entradas** > **Agregar canal** y, a continuación, seleccione las métricas que ha creado.

![](assets/attrib_results_2.png)

Consulte el ejemplo del segundo método a continuación. Se puede ver que los resultados de ambas opciones son idénticos.
