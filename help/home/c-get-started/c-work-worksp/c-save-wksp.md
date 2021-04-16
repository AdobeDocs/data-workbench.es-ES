---
description: De forma predeterminada, al cerrar un espacio de trabajo desbloqueado se guardan los cambios realizados en el espacio de trabajo.
title: Guardar un espacio de trabajo
uuid: 166f9ef8-c2c4-4dfc-8d7d-453650bee6b8
exl-id: 0f1052f5-496c-443e-b29d-5973c16ef527
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '334'
ht-degree: 1%

---

# Guardar un espacio de trabajo{#save-a-workspace}

De forma predeterminada, al cerrar un espacio de trabajo desbloqueado se guardan los cambios realizados en el espacio de trabajo.

Si el espacio de trabajo es un espacio de trabajo de servidor, los cambios se guardan solo localmente, a menos que guarde específicamente el espacio de trabajo actualizado en el servidor de Data Workbench. Para obtener más información sobre los espacios de trabajo bloqueados, consulte [Desbloqueo de un espacio de trabajo](../../../home/c-get-started/c-work-worksp/c-unlock-wksp.md#concept-18ada952aecf45c79a806b31b294023e).

## Guardar un espacio de trabajo localmente {#section-3f331c880f1a490c96844103c2432d61}

La ubicación de almacenamiento predeterminada es la carpeta **User\profile name\Workspaces\tab name** dentro del directorio de instalación de la Data Workbench. Por ejemplo, si está trabajando con el perfil Películas y guarda un espacio de trabajo localmente desde la pestaña [!UICONTROL Custom] , el espacio de trabajo se guarda en la carpeta **User\Movies\Workspaces\Custom** del directorio de instalación de la Data Workbench.

**Para guardar cambios en un espacio de trabajo**

* En el espacio de trabajo, haga clic en **[!UICONTROL File]** y luego en **[!UICONTROL Save]**.

**Para guardar un espacio de trabajo existente como nuevo espacio de trabajo**

1. En la ficha [!DNL Worktop] que desee, haga clic en la miniatura del espacio de trabajo que desee mostrar.
1. En el espacio de trabajo, haga clic en **[!UICONTROL File]** y, a continuación, haga clic en **[!UICONTROL Save Copy As]**.
1. En el cuadro de diálogo [!DNL Save Workspace As], especifique el nombre y la ubicación donde desea guardar el espacio de trabajo copiado y haga clic en **[!UICONTROL Save]**.

## Guardar un espacio de trabajo en el servidor de Data Workbench {#section-65a23da852ee4186880e002f7c87ea81}

>[!NOTE]
>
>Solo los usuarios con los permisos adecuados pueden guardar espacios de trabajo en el servidor de Data Workbench. Para obtener más información, póngase en contacto con el administrador del sistema.

Guardar espacios de trabajo en el servidor de Data Workbench conectado también se denomina publicación de un espacio de trabajo, ya que pone el espacio de trabajo a disposición de otros usuarios. De forma predeterminada, los espacios de trabajo se guardan en la carpeta *working profile name*\Workspaces\*tab name* del servidor de Data Workbench. Por ejemplo, si está trabajando con el perfil Películas y guarda un espacio de trabajo en el servidor de Datas Workbench conectado desde la pestaña [!DNL Custom] , el espacio de trabajo se guarda en el directorio Movies\Workspaces\Custom folder of the Data Workbench server.

**Para guardar un espacio de trabajo en el servidor de Data Workbench**

* En la ficha [!DNL Worktop] que desee, haga clic con el botón derecho en la miniatura del espacio de trabajo que desee guardar en el servidor de Data Workbench y haga clic en **[!UICONTROL Save to server]**.

![](assets/mnu_workspaceManager_SaveToServerwksp.png)
