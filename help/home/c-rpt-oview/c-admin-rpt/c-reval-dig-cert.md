---
description: Después de la instalación, el certificado digital emitido por Adobe actúa como una clave que le permite ejecutar el servidor de informes.
solution: Analytics
title: Volver a validar el certificado digital
topic: Data workbench
uuid: 6c8533df-f459-41eb-84ac-344bad9fecdc
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Volver a validar el certificado digital{#re-validating-the-digital-certificate}

Después de la instalación, el certificado digital emitido por Adobe actúa como una clave que le permite ejecutar el servidor de informes.

**Frecuencia recomendada:** Según sea necesario

Para funcionar correctamente, un certificado digital debe estar actualizado.

Para mantenerse actualizado, el certificado digital debe ser revalidado de forma regular (generalmente, cada 30 días, pero esto puede variar según el acuerdo con Adobe). Si el equipo tiene acceso a Internet, el proceso de revalidación es completamente transparente. [!DNL Report Server] se conecta automáticamente al servidor de licencias de Adobe y vuelve a validar el certificado cuando es necesario. Si el equipo no tiene acceso a Internet, debe descargar un certificado nuevo y validado del servidor de licencias de Adobe e instalarlo en el equipo siguiendo los pasos que se indican en [Descarga e instalación del certificado](../../../home/c-rpt-oview/c-inst-rpt/c-install-dig-cert/c-install-dig-cert.md#concept-5a61fc67df3643598c7c403962075f76)digital.
