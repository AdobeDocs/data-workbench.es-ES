---
description: El archivo Internal.cfg aplicado en el Administrador de perfiles evita que los usuarios realicen cambios en los perfiles personalizados mediante los administradores de perfil, Dimension, informes, espacios de trabajo, métricas y filtros.
title: Bloqueo de perfiles en la estación de trabajo
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
exl-id: 2604ceea-0e55-4ae7-a286-e5257e974a64
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 5%

---

# Bloqueo de perfiles en la estación de trabajo{#locking-profiles-in-the-workstation}

{{eol}}

El archivo Internal.cfg aplicado en el Administrador de perfiles evita que los usuarios realicen cambios en los perfiles personalizados mediante los administradores de perfil, Dimension, informes, espacios de trabajo, métricas y filtros.

Puede evitar que los archivos de perfil se modifiquen y sobrescriban al utilizar los administradores guardando el **[!DNL Internal.cfg]** a su perfil personalizado en el Administrador de perfiles. Este archivo de configuración evita que los usuarios sobrescriban varios archivos al trabajar en los administradores (a los que se accede desde el **Administrador** > **Perfil** ).

**Bloqueo de perfiles en el Administrador de perfiles**

1. En el espacio de trabajo, haga clic con el botón derecho **Administrador** > **Administrador de perfiles**.

1. En el **Administrador de perfiles**, haga clic con el botón derecho **[!DNL Context > Internal.cfg]** y **Convertir en local**.

1. Haga clic con el botón derecho en la marca de verificación de **Usuario** y guardar en un `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Nota**: Solo se evitan los cambios realizados por los administradores en los archivos de perfil al guardar la variable **[!DNL Internal.cfg]** a un perfil personalizado en el Administrador de perfiles. Puede seguir guardando espacios de trabajo en el servidor desde la superficie de trabajo utilizando la variable **Guardar en servidor** comando.
