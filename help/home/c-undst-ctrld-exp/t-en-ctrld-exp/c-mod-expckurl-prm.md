---
description: El parámetro ExpCookieURL se puede usar para probar que el experimento controlado funciona correctamente.
solution: Analytics
title: Modificación del parámetro ExpCookieURL (opcional)
uuid: 0c160c26-f9de-4e41-a05d-bf7bb32395bb
exl-id: fe3dadab-890d-4426-b6f5-8ffd1cd38c69
source-git-commit: 31f775478b0f0d968310ed10a43ad46791319ee9
workflow-type: tm+mt
source-wordcount: '146'
ht-degree: 6%

---

# Modificación del parámetro ExpCookieURL (opcional){#modifying-the-expcookieurl-paramter-optional}

El parámetro ExpCookieURL se puede usar para probar que el experimento controlado funciona correctamente.

Este parámetro define la dirección URL de una página virtual que, cuando se le solicita, le sitúa en un experimento y grupo especificados y luego le redirige a la raíz del sitio web. Desde ese punto hasta el final del experimento, usted forma parte del experimento y grupo especificados.

La página predeterminada de este parámetro es [!DNL setcookie.htm], pero puede usar cualquier URL virtual válida.

>[!NOTE]
>
>Debe ser una dirección URL virtual y no debe ser una página real ni un fragmento de contenido existente. No debe haber ningún archivo en el servidor web en la ruta especificada con el nombre especificado.

A continuación se muestra un ejemplo del parámetro ExpCookieURL :

[!DNL ExpCookieURL /setcookie.htm]
