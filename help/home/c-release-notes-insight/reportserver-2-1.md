---
description: Actualización de seguridad para el portal de informes de Área de trabajo de datos.
title: DWB Report Portal 2.1
uuid: de8266f4-1f7b-4bfd-94e7-16bddb336db3
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# DWB Report Portal 2.1{#dwb-report-portal}

Actualización de seguridad para el portal de informes de Área de trabajo de datos.

**Actualización de seguridad importante**

El portal de informes ahora cuenta con algoritmos de hash más sólidos con compatibilidad con sales. Si está actualizando a Report Portal 2.1, agregue un nuevo campo de texto, PasswordSalt con un tamaño de campo de 20 caracteres en la base de datos users.mdb. Este campo es necesario para almacenar la contraseña.
