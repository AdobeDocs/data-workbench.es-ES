---
description: El tablero requiere ciertos permisos de solo lectura para poder acceder a los datos de Data Workbench y mostrarlos. No se necesitan privilegios de escritura.
title: Configuración del control de acceso
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
exl-id: a9ff61bb-c519-4205-8fa8-bfd1986fcd60
translation-type: tm+mt
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 6%

---

# Configuración del control de acceso{#configuring-access-control}

El tablero requiere ciertos permisos de solo lectura para poder acceder a los datos de Data Workbench y mostrarlos. No se necesitan privilegios de escritura.

La configuración del control de acceso implica editar el archivo [!DNL Access Control.cfg] en la(s) FSU y agregar un nuevo grupo para conceder permiso al tablero de Data Workbench:

1. Edite el archivo [!DNL AccessControl.cfg] (preferiblemente utilizando la estación de trabajo de Data Workbench).
1. Cree un nuevo grupo denominado *Acceso al tablero de Insight*.
1. En los miembros de este grupo, añada el CN adecuado que se le haya proporcionado con este fin (Ejemplo: CN:INSIGHT-USER01). Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener este CN.
1. En el acceso de solo lectura de este grupo, modifique la lista para reflejar lo siguiente:

* /Perfiles/$
* /Perfiles/
* /Direcciones
* /Estado/
* /Usuarios/$

1. Elimine cualquier elemento de la sección de acceso de lectura y escritura, ya que no se necesitan permisos de escritura para el tablero.
1. Guarde los cambios en el archivo [!DNL AccessControl.cfg] en el servidor para que los permisos surtan efecto.
