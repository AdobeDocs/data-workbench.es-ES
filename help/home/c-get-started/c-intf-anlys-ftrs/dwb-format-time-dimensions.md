---
description: Configure las dimensiones de tiempo para que se muestren correctamente en la configuración regional.
title: Localización de dimensiones de tiempo
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
exl-id: 950fe70b-a687-4b9c-b29f-555139740809
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 2%

---

# Localización de dimensiones de tiempo{#localizing-time-dimensions}

{{eol}}

Configure las dimensiones de tiempo para que se muestren correctamente en la configuración regional.

Puede configurar el formato mostrado de las dimensiones de tiempo en función de la configuración regional en la variable **[!DNL Standard Time Dimensions.cfg]** archivo (ubicado de forma predeterminada en **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimension.cfg]**).

Por ejemplo, en Norteamérica puede expresar la fecha del 3 de mayo de 2015 como 15/5 o **`%m/%d/%y`**. Sin embargo, en otras partes del mundo esto podría interpretarse como `%d/%m/%y`, o 5 de marzo de 2015 debido a una ambigüedad en los valores. Para evitar esta situación, es posible que un administrador desee cambiar el formato mostrado para que coincida con las expectativas de los usuarios en una configuración regional.

## 1. Anular los Dimension de tiempo predeterminados en Standard Time Dimension.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Para habilitar esta función, el administrador debe anular los valores predeterminados editando las dimensiones temporales existentes o creando nuevas dimensiones temporales con parámetros adicionales.

A continuación se muestra un ejemplo de dimensión de tiempo modificada.

La variable **Formato** los valores de semana, hora, día, mes y hora del día se establecen como predeterminados en el ejemplo.

>[!NOTE]
>
>Si se omiten estas líneas, el comportamiento de la Data Workbench no cambia y la dimensión se compila con los valores predeterminados.

```
Transformation Include = TransformationInclude:  
  Extended Dimensions = vector: 1 items 
    0 = TimeDimensions:  
      Comments = Comment: 0 items 
      Dimensions = map:  
        Day = string: Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Hour of Day = string: Hour of Day 
        Month = string: Month 
        Week = string: Week 
      Hidden = bool: false 
      Input Time (1970 epoch) = string: x-unixtime 
      Week Format = string:  
  %m/%d/%y
      Hour Format = string:  
  %x %H:%M 
      Day Format = string:  
  %x
      Month Format = string:  
  %b '%y
      Hour Of Day Format = string:  
  %#H:%M
      Name = string: Visit Time 
      Parent = string: Visit 
      Week Start Day = string: Mon 
  Transformations = vector: 0 items
```

![](assets/6_4_time_format.png)

## 2. Configurar el archivo meta.cfg {#section-5e077d3298dd48fda7f7bb16af9ea00c}

Además, es necesario que el administrador del paquete añada estos parámetros y sus valores predeterminados a la **[!DNL meta.cfg]** archivo. Esto permite la edición desde la estación de trabajo.

Aquí hay un extracto de un **[!DNL meta.cfg]** archivo.

```
dimensions = vector: 6 items 
  0 = Template: 
    ...
  ...
  5 = Template: 
    name = string: Time Dimensions 
    value = TimeDimensions: 
      Name = string:  
      Comments = Comment: 0 items 
      Hidden = bool: false 
       
  Week Format = string: %d/%m/%y 
       Hour Format = string: %x %H:%M 
       Day Format = string: %x 
       Month Format = string: %b '%y 
       Hour Of Day Format = string: %#H:%M</b> 
      Input Time (1970 epoch) = string:  
      Parent = string:  
      Week Start Day = string: Mon 
      Dimensions = map: 
        Hour of Day = string: Hour of Day 
        Day of Week = string: Day of Week 
        Hour = string: Hour 
        Day = string: Day 
        Week = string: Week 
        Month = string: Month
```

Este es un ejemplo de **[!DNL meta.cfg]** en la estación de trabajo:

![](assets/dwb_time_format.png)

A continuación, el administrador puede entrar en el **Administrador de archivos**, abra los archivos en los que están configuradas las dimensiones temporales (p. ej., **[!DNL Standard Time Dimensions.cfg]**) y edítelos utilizando en la estación de trabajo.
