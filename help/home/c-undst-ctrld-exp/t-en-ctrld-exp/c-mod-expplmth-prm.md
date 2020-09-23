---
description: 'null'
solution: Analytics,Analytics
title: Modificación del parámetro ExpPartialMatch (opcional)
topic: Data workbench
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 14%

---


# Modificación del parámetro ExpPartialMatch (opcional){#modifying-the-exppartialmatch-parameter-optional}

Si desea habilitar los experimentos controlados para reasignar todo el sitio web o un subdirectorio completo del sitio web a otra ubicación, puede establecer el parámetro ExpPartialMatch del [!DNL txlogd.conf] archivo en &quot;on&quot;. El valor predeterminado es &quot;off&quot;.

A continuación se muestra un ejemplo del parámetro ExpPartialMatch:

[!DNL ExpPartialMatch off]

Tenga mucho cuidado al configurar este parámetro en &quot;on&quot; porque puede resultar en una reasignación involuntaria de todo el sitio web.
