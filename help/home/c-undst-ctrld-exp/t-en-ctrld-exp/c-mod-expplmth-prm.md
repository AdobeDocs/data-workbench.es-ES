---
description: Modificación del parámetro ExpPartialMatch (opcional)
title: Modificación del parámetro ExpPartialMatch (opcional)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# Modificación del parámetro ExpPartialMatch (opcional){#modifying-the-exppartialmatch-parameter-optional}

Si desea permitir que los experimentos controlados reasignen todo el sitio web o un subdirectorio completo del sitio web a otra ubicación, puede establecer el parámetro ExpPartialMatch en el archivo [!DNL txlogd.conf] en &quot;on&quot;. El valor predeterminado es &quot;off&quot;.

A continuación se muestra un ejemplo del parámetro ExpPartialMatch:

[!DNL ExpPartialMatch off]

Tenga cuidado al configurar este parámetro en &quot;on&quot; porque puede resultar en una reasignación involuntaria de todo el sitio web.
