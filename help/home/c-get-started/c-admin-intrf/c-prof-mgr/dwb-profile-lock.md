---
description: El archivo Internal.cfg aplicado en el Administrador de perfiles evita que los usuarios realicen cambios en los perfiles personalizados mediante los administradores de perfiles, dimensiones, informes, espacios de trabajo, métricas y filtros.
title: Bloqueo de perfiles en la estación de trabajo
uuid: 6b65d7c1-dade-4c6e-9d59-09693e62f3f5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Bloqueo de perfiles en la estación de trabajo{#locking-profiles-in-the-workstation}

El archivo Internal.cfg aplicado en el Administrador de perfiles evita que los usuarios realicen cambios en los perfiles personalizados mediante los administradores de perfiles, dimensiones, informes, espacios de trabajo, métricas y filtros.

Puede evitar que los archivos de perfil se modifiquen y sobrescriban al usar los administradores guardando el **[!DNL Internal.cfg]** archivo en su perfil personalizado en el Administrador de perfiles. Este archivo de configuración evita que los usuarios sobrescriban varios archivos al trabajar en los administradores (a los que se accede desde el menú **Administración** > **Perfil** ).

**Bloqueo de perfiles en el Administrador de perfiles**

1. En el espacio de trabajo, haga clic con el botón secundario en **Administración** > Administrador **de perfiles**.

1. En el Administrador **de perfiles**, haga clic con el botón derecho **[!DNL Context > Internal.cfg]** y **Convertir en local**.

1. Haga clic con el botón derecho en la marca de verificación de la columna **Usuario** y guárdela en una `<custom profile>`.

![](assets/dwb_lock_profiles.png)

**Nota**: Solo se evitan los cambios realizados en los archivos de perfil por los administradores al guardarlos **[!DNL Internal.cfg]** en un perfil personalizado en el Administrador de perfiles. Todavía puede guardar espacios de trabajo en el servidor desde el escritorio mediante el comando **Guardar en servidor** .
