---
description: El parámetro ExpCookieURL se puede usar para probar que el experimento controlado funciona correctamente.
solution: Analytics,Analytics
title: Modificación del parámetro ExpCookieURL (opcional)
topic: Data workbench
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
translation-type: tm+mt
source-git-commit: 34cdcfc83ae6bb620706db37228e200cff43ab2c
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---


# Modificación del parámetro ExpCookieURL (opcional){#modifying-the-expcookieurl-paramter-optional}

El parámetro ExpCookieURL se puede usar para probar que el experimento controlado funciona correctamente.

Este parámetro define la dirección URL de una página virtual que, cuando se le solicita, lo coloca en un experimento y grupo especificados y, a continuación, lo redirige a la raíz del sitio web. Desde ese punto hasta el final del experimento, usted forma parte del experimento y grupo especificados.

La página predeterminada para este parámetro es [!DNL setcookie.htm], pero puede utilizar cualquier dirección URL virtual válida.

>[!NOTE]
>
>Debe ser una dirección URL virtual y no debe ser una página real ni una parte del contenido existente. No debe haber ningún archivo en el servidor web en la ruta de acceso especificada con el nombre especificado.

A continuación se muestra un ejemplo del parámetro ExpCookieURL:

[!DNL ExpCookieURL /setcookie.htm]
