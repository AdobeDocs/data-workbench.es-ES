---
description: Directrices para especificar el formato de salida.
title: Formato de salida
uuid: 12086f14-bad1-4d27-82fb-533e877d0a04
exl-id: e695eaf4-ebe5-4dd1-8191-8045021d6411
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Formato de salida{#output-format}

{{eol}}

Directrices para especificar el formato de salida.

* Cada métrica o nombre de dimensión debe comenzar y terminar con un signo de porcentaje (%).

   * %XYZ% especifica el elemento de la dimensión XYZ correspondiente al elemento de Nivel. Se genera un error si la dimensión XYZ no es una a una ni una a varias con Level.
   * %=XYZ% especifica el valor de la fórmula de métrica o métrica XYZ para el elemento determinado de Nivel.

* Los nombres de Dimension que tengan dos palabras o más no requieren guiones bajos.
* Los nombres de métricas que tengan dos palabras o más requieren guiones bajos.

>[!NOTE]
>
>Si mantiene pulsada la tecla Ctrl y hace clic con el botón derecho en la variable [!DNL Output Format] campo, [!DNL Insert menu] aparece. Este menú contiene una lista de caracteres especiales (por ejemplo, Tab) que a menudo se utilizan como delimitadores.

Si desea exportar los datos de duración de la sesión del segmento, debe crear una nueva métrica basada en la métrica Duración de la sesión. La nueva métrica, que se utilizará únicamente con la variable [!DNL Output Format] de exportación de segmentos, permite a Microsoft Excel interpretar correctamente las sesiones que duran menos de una hora. Para crear una nueva métrica de duración de la sesión, abra el [!DNL Session Duration.metric] (desde el [!DNL Profile Manager]) e inserte un signo de almohadilla (#) en la cadena de hora: [!DNL ftime = string: %#H:%M:%S]

El signo de almohadilla hace que se añada un &quot;0&quot; inicial a duraciones de sesión inferiores a 1 hora. Como resultado, Excel interpreta 0:53:21 como 53 minutos y 21 segundos. Guarde la nueva métrica con un nombre diferente y cárguela en el perfil adecuado para que otros la utilicen haciendo clic con el botón derecho en la marca de verificación del archivo en la variable [!DNL User] y haga clic en **[!UICONTROL Save to]** > *&lt;**[!UICONTROL profile name]**>*.
