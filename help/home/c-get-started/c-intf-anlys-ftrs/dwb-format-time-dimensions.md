---
description: Configure las dimensiones de tiempo para que se muestren correctamente en la configuración regional.
title: Localización de dimensiones de tiempo
uuid: a2098522-bf05-4680-9b78-6fb284695a0a
translation-type: tm+mt
source-git-commit: 25366087936dfa5e31c5921aac400535ec259f2e

---


# Localización de dimensiones de tiempo{#localizing-time-dimensions}

Configure las dimensiones de tiempo para que se muestren correctamente en la configuración regional.

Puede configurar el formato mostrado de las dimensiones de tiempo en función de la configuración regional en el **[!DNL Standard Time Dimensions.cfg]** archivo (ubicado de forma predeterminada en **[!DNL Server/Profiles/`<my profile>`/Dataset/Transformation/Time/Standard Time Dimensions.cfg]**).

Por ejemplo, en Norteamérica puede expresar la fecha 3 de mayo de 2015 como 5/3/15 o **`%m/%d/%y`**. Sin embargo, en otras partes del mundo esto podría interpretarse como `%d/%m/%y`, o el 5 de marzo de 2015, debido a una ambigüedad en los valores. Para evitar esta situación, es posible que un administrador desee cambiar el formato mostrado para que coincida con las expectativas de los usuarios de una configuración regional.

## 1. Omitir dimensiones de tiempo predeterminadas en dimensiones de tiempo estándar.cfg {#section-7d0b24657bef4b15abb3cbea66cb617f}

Para habilitar esta función, el administrador debe anular los valores predeterminados editando las dimensiones de tiempo existentes o creando nuevas dimensiones de tiempo con parámetros adicionales.

A continuación se muestra un ejemplo de una dimensión de tiempo modificada.

Los valores de **Formato** para Semana, Hora, Día, Mes y Hora del Día se establecen en los valores predeterminados del ejemplo.

>[!NOTE]
>
>Si se omiten estas líneas, el comportamiento del área de trabajo de datos no cambiará y la dimensión se compilará con los valores predeterminados.

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

Además, es necesario que el administrador del paquete agregue estos parámetros y sus valores predeterminados al **[!DNL meta.cfg]** archivo del perfil. Esto permite la edición desde la estación de trabajo.

Aquí hay un extracto de un **[!DNL meta.cfg]** archivo configurado.

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

A continuación se muestra un ejemplo de un **[!DNL meta.cfg]** archivo en la estación de trabajo:

![](assets/dwb_time_format.png)

A continuación, el administrador puede entrar en el Administrador **de** archivos, abrir los archivos donde se configuran las dimensiones de tiempo (por ejemplo, **[!DNL Standard Time Dimensions.cfg]**) y editarlos en la estación de trabajo.
