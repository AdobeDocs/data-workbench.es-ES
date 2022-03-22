---
description: Después de la instalación, el certificado digital emitido por Adobe actúa como una clave que le permite ejecutar el servidor de informes.
title: Volver a validar el certificado digital (información general)
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
exl-id: 810e3057-26a9-413c-b77c-525035d37756
source-git-commit: 235b8816c7397ac1ab71df650a1d4c2d681b3b2d
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 10%

---

# Volver a validar el certificado digital{#re-validating-the-digital-certificate}

Después de la instalación, el certificado digital emitido por Adobe actúa como una clave que le permite ejecutar el servidor de informes.

**Frecuencia recomendada:** Según sea necesario

Para funcionar correctamente, un certificado digital debe estar actualizado.

Para mantenerse actualizado, el certificado digital debe volver a validarse de forma regular (normalmente, cada 30 días, pero esto puede variar según el acuerdo con el Adobe). Si el equipo tiene acceso a Internet, el proceso de validación es completamente transparente. [!DNL Report Server] se conecta automáticamente al servidor de licencias de Adobe y vuelve a validar el certificado cuando es necesario. Si el equipo no tiene acceso a Internet, debe descargar un certificado nuevo y validado del servidor de licencias de Adobe e instalarlo en el equipo siguiendo los pasos que se indican en [Descarga e instalación del certificado digital](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76).
