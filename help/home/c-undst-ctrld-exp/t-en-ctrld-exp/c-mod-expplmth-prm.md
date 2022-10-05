---
description: Modificación del parámetro ExpPartialMatch (opcional)
title: Modificación del parámetro ExpPartialMatch (opcional)
uuid: 15ed33cc-5ec8-45b2-a4eb-d1941962ca9d
exl-id: 8ad45368-85a4-4865-b66b-52c29c28799c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '82'
ht-degree: 18%

---

# Modificación del parámetro ExpPartialMatch (opcional){#modifying-the-exppartialmatch-parameter-optional}

{{eol}}

Si desea permitir que los experimentos controlados reasignen todo el sitio web o un subdirectorio completo del sitio web a otra ubicación, puede establecer el parámetro ExpPartialMatch en la variable [!DNL txlogd.conf] a &quot;on&quot;. El valor predeterminado es &quot;off&quot;.

A continuación se muestra un ejemplo del parámetro ExpPartialMatch:

[!DNL ExpPartialMatch off]

Tenga cuidado al configurar este parámetro en &quot;on&quot; porque puede resultar en una reasignación involuntaria de todo el sitio web.
