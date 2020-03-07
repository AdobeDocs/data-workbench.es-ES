---
description: El tablero requiere ciertos permisos de sólo lectura para poder acceder a los datos del área de trabajo de datos y mostrarlos. No se requieren privilegios de escritura.
solution: Analytics
title: Configuración del control de acceso
topic: Data workbench
uuid: 600b6799-547d-46da-9027-4f64943e2ccd
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Configuración del control de acceso{#configuring-access-control}

El tablero requiere ciertos permisos de sólo lectura para poder acceder a los datos del área de trabajo de datos y mostrarlos. No se requieren privilegios de escritura.

La configuración del control de acceso implica la edición del [!DNL Access Control.cfg] archivo en la(s) FSU(s) y la adición de un nuevo grupo para otorgar permiso al tablero del área de trabajo de datos:

1. Edite el [!DNL AccessControl.cfg] archivo (preferiblemente con la estación de trabajo del área de trabajo de datos).
1. Cree un nuevo grupo denominado *Insight Dashboard Access*.
1. En los miembros de este grupo, agregue el CN adecuado que se le ha proporcionado con este fin (ejemplo: CN:INSIGHT-USER01). Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener este CN.
1. En el acceso de solo lectura de este grupo, modifique la lista para que refleje lo siguiente:

* /Profiles/$
* /Profiles/
* /Direcciones
* /Estado/
* /Usuarios/$

1. Elimine cualquier elemento de la sección de acceso de lectura y escritura, ya que no se requieren permisos de escritura para el tablero.
1. Guarde los cambios en el [!DNL AccessControl.cfg] archivo en el servidor para que los permisos surtan efecto.
