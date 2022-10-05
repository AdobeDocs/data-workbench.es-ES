---
description: Para permitir que el portal de informes escriba en la base de datos que contiene la información necesaria para autenticar a los usuarios, debe establecer los permisos adecuados para la base de datos.
title: Definición de permisos para la base de datos
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
exl-id: 901cf702-633c-4660-b1bd-4937d0c3293c
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 10%

---

# Definición de permisos para la base de datos{#set-permissions-for-the-database}

{{eol}}

Para permitir que el portal de informes escriba en la base de datos que contiene la información necesaria para autenticar a los usuarios, debe establecer los permisos adecuados para la base de datos.

1. En el equipo en el que se ejecuta IIS, vaya a \*PortalName*\data\users.mdb.
1. Haga clic con el botón derecho en el **[!UICONTROL users.mdb]** y seleccione **[!UICONTROL Properties]**.
1. En el [!DNL Security] , en Grupos o nombres de usuario, haga clic en **[!UICONTROL Users]**.
1. En [!DNL Permission for User], en la fila Escritura , seleccione **[!UICONTROL Allow]**.
1. Haga clic en **[!UICONTROL OK]** y cierre el [!DNL Properties] para abrir el Navegador.
