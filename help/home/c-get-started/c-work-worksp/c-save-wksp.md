---
description: De forma predeterminada, al cerrar un espacio de trabajo desbloqueado se guardan los cambios realizados en el espacio de trabajo.
title: Guardar un espacio de trabajo
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Guardar un espacio de trabajo{#save-a-workspace}

{{eol}}

De forma predeterminada, al cerrar un espacio de trabajo desbloqueado se guardan los cambios realizados en el espacio de trabajo.

Si el espacio de trabajo es un espacio de trabajo de servidor, los cambios se guardan solo localmente, a menos que guarde específicamente el espacio de trabajo actualizado en el servidor de Data Workbench. Para obtener más información sobre los espacios de trabajo bloqueados, consulte [Desbloquear un espacio de trabajo](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Guardar un espacio de trabajo localmente {#section-3f331c880f1a490c96844103c2432d61}

La ubicación de guardado predeterminada es la **Usuario\nombre de perfil\Workspaces\nombre de ficha** en el directorio de instalación de la Data Workbench. Por ejemplo, si está trabajando con el perfil Películas y guarda un espacio de trabajo localmente desde el [!UICONTROL Custom] , el espacio de trabajo se guarda en la pestaña **User\Movies\Workspaces\Custom** en el directorio de instalación de la Data Workbench.

**Para guardar cambios en un espacio de trabajo**

* En el espacio de trabajo, haga clic en **[!UICONTROL File]**, luego **[!UICONTROL Save]**.

**Para guardar un espacio de trabajo existente como nuevo espacio de trabajo**

1. En el [!DNL Worktop] , haga clic en la miniatura del espacio de trabajo que desea mostrar.
1. En el espacio de trabajo, haga clic en **[!UICONTROL File]** y haga clic en **[!UICONTROL Save Copy As]**.
1. En el [!DNL Save Workspace As] , especifique el nombre y la ubicación donde desea guardar el espacio de trabajo copiado y haga clic en **[!UICONTROL Save]**.

## Guardar un espacio de trabajo en el servidor de Data Workbench {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Solo los usuarios con los permisos adecuados pueden guardar espacios de trabajo en el servidor de Data Workbench. Para obtener más información, póngase en contacto con el administrador del sistema.

Guardar espacios de trabajo en el servidor de Data Workbench conectado también se denomina publicación de un espacio de trabajo, ya que pone el espacio de trabajo a disposición de otros usuarios. De forma predeterminada, los espacios de trabajo se guardan en la variable *nombre del perfil de trabajo*\Workspaces\*nombre de ficha* carpeta del servidor de Data Workbench. Por ejemplo, si está trabajando con el perfil Películas y guarda un espacio de trabajo en el servidor de Datas Workbench conectado desde el [!DNL Custom] , el espacio de trabajo se guarda en la carpeta Movies\Workspaces\Custom del servidor de Data Workbench.

**Para guardar un espacio de trabajo en el servidor de Data Workbench**

* En el [!DNL Worktop] , haga clic con el botón derecho en la miniatura del espacio de trabajo que desee guardar en el servidor de Datas Workbench y haga clic en **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
