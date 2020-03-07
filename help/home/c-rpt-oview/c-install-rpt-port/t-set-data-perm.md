---
description: Para habilitar el portal de informes para escribir en la base de datos que contiene la información necesaria para autenticar usuarios, debe establecer los permisos adecuados para la base de datos.
solution: Analytics
title: Definir permisos para la base de datos
topic: Data workbench
uuid: 747d1adc-bfc9-4f54-a2b1-ae5e12dd82a2
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Definir permisos para la base de datos{#set-permissions-for-the-database}

Para habilitar el portal de informes para escribir en la base de datos que contiene la información necesaria para autenticar usuarios, debe establecer los permisos adecuados para la base de datos.

1. En el equipo en el que se está ejecutando IIS, vaya a \*PortalName*\data\users.mdb.
1. Haga clic con el botón derecho en el **[!UICONTROL users.mdb]** archivo y seleccione **[!UICONTROL Properties]**.
1. En la [!DNL Security] ficha Grupos o nombres de usuario, haga clic en **[!UICONTROL Users]**.
1. En [!DNL Permission for User], en la fila Escritura, seleccione **[!UICONTROL Allow]**.
1. Haga clic en **[!UICONTROL OK]** y cierre el cuadro de [!DNL Properties] diálogo.
