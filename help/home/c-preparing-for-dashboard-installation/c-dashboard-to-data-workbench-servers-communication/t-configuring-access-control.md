---
description: El tablero requiere ciertos permisos de solo lectura para poder acceder a los datos de Data Workbench y mostrarlos. No se necesitan privilegios de escritura.
title: Configuración del control de acceso del panel
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
source-git-commit: 90b9fff995cb37a62024f454f009e9e0d7b927cd
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 2%

---

# Configuración del control de acceso del panel{#configuring-dashboard-access-control}

{{eol}}

El tablero requiere ciertos permisos de solo lectura para poder acceder a los datos de Data Workbench y mostrarlos. No se necesitan privilegios de escritura.

La configuración del control de acceso implica la edición de [!DNL Access Control.cfg] en las FSU y agregando un nuevo grupo para conceder permiso al tablero de Data Workbench:

1. Edite el [!DNL AccessControl.cfg] (preferiblemente utilizando la estación de trabajo de data workbench).
1. Cree un nuevo grupo con el nombre *Acceso a tablero de Insight*.
1. En los miembros de este grupo, añada el CN adecuado que se le haya proporcionado con este fin (Ejemplo: CN:INSIGHT-USER01). Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener este CN.
1. En el acceso de solo lectura de este grupo, modifique la lista para reflejar lo siguiente:

* /Perfiles/$
* /Perfiles/
* /Direcciones
* /Estado/
* /Usuarios/$

1. Elimine cualquier elemento de la sección de acceso de lectura y escritura, ya que no se necesitan permisos de escritura para el tablero.
1. Guarde los cambios en la [!DNL AccessControl.cfg] al servidor para que los permisos surtan efecto.
