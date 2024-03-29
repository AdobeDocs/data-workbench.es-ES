---
description: Las tareas administrativas para la funcionalidad del repetidor son muy similares a las de Insight Server.
title: Repetidor de administración
uuid: 4fbfce3a-2610-4dcd-a585-cb7ee07b90db
exl-id: 5c7a4f95-be4b-4c2c-8dea-19037ba0b5cc
source-git-commit: b1dda69a606a16dccca30d2a74c7e63dbd27936c
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 12%

---

# Repetidor de administración{#administering-repeater}

{{eol}}

Las tareas administrativas para la funcionalidad del repetidor son muy similares a las de Insight Server.

Se aplicarán las siguientes tareas administrativas: excepciones o cambios que debe realizar para que la variable [!DNL Insight Server] La DPU puede utilizarse con el servidor repetidor y se anotan después de cada paso.

* [Volver a validar el certificado digital](../../../home/c-inst-svr/c-admin-inst-svr/c-reval-dgtl-cert.md#concept-f0020a6f0d6f477099b7a8f0b6e2944c)
* [Confirmación de que el servicio se está ejecutando](../../../home/c-inst-svr/c-admin-inst-svr/c-cfrm-svc-rng.md#concept-15b046e92d254bbd95dec829abc76677) En la lista de servicios del panel de control de Servicios, busque &quot;Repetidor&quot;.

* [Configuración del control de acceso](../../../home/c-inst-svr/c-admin-inst-svr/c-config-acs-ctrl/c-config-acs-ctrl.md#concept-ac385e870dbe4b57a72bf7266b60f93d)
* [Monitorización del espacio en disco](../../../home/c-inst-svr/c-admin-inst-svr/c-mntr-disk-spc/c-mntr-disk-spc.md#concept-a83447e44f4e47aba282328be395a0d4) Los tipos de datos que se aplican al servidor repetidor son datos de evento, sistema operativo y sistema. Si utiliza el servidor repetidor para el almacenamiento de copia de seguridad y es necesario disponer de más espacio de almacenamiento de datos en el equipo, puede mover todos los archivos de registro del día más actual a otro equipo o medio de almacenamiento de datos (unidad zip, cinta, etc.). Para mover los datos no es necesario detener el servicio repetidor.

   >[!NOTE]
   >
   >Debe verificar la integridad de las copias de seguridad de su [!DNL .vsl] antes de eliminar cualquiera de ellos del repetidor.

* [Configuración de alertas administrativas](../../../home/c-inst-svr/c-admin-inst-svr/t-config-adm-alrts.md#task-0858f588da4941aa9d4952f6592681aa)
* [Supervisión de los eventos administrativos](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adm-evts.md#task-4c78325b3e6e4dde8fa94c1896e19e34)
* [Supervisión de registros de auditoría](../../../home/c-inst-svr/c-admin-inst-svr/t-mntr-adt-lgs.md#task-5dd9830424fe440ea1369215a1aca231)
* [Configuración de comunicaciones](../../../home/c-inst-svr/c-admin-inst-svr/t-config-com.md#task-471305ecf7a644789a288f93c42514ec)
* [Reinicio del servicio](../../../home/c-inst-svr/c-admin-inst-svr/t-rest-svc.md#task-97f97f1019bc440080ab2fddfdc04c74)  [!DNL Repeater] está diseñada para ejecutarse de forma continua. Si reinicia el equipo, el repetidor se reinicia automáticamente. Si necesita iniciar y detener el repetidor manualmente, puede hacerlo usando el panel de control de Servicios en Windows.
