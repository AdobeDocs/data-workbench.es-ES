---
description: El Área de trabajo de datos de Adobe proporciona herramientas y procesos para preparar los datos a fin de cumplir con las Normas generales de protección de datos (RGPD).
solution: Analytics
title: Compatibilidad del área de trabajo de datos con GDPR
topic: Data workbench
translation-type: tm+mt
source-git-commit: 279e71f3da3f0ebc29091e88b87666a22a36a8d6
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 2%

---


# Compatibilidad del área de trabajo de datos con GDPR

El Área de trabajo de datos de Adobe proporciona herramientas y procesos para preparar los datos para cumplir con el [!DNL General Data Protection Regulations] (RGPD).

Al igual que todas las soluciones de Adobe Analytics, el Área de trabajo de datos admite el RGPD al proporcionar limpieza, eliminar y etiquetar variables analíticas al procesar la fuente de datos de Adobe Analytics. Para admitir implementaciones de RGPD, Adobe le permite configurar procesos para RGPD según los permisos de su compañía según lo establecido en su acuerdo con Adobe. Consulte [Adobe Analytics y GDPR para obtener más información](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

El reglamento del RGPD identifica las funciones y obligaciones de las diferentes partes responsables de la habilitación del RGPD (véase [RGPD y Su empresa](https://www.adobe.com/es/privacy/general-data-protection-regulation.html)).

* Su organización actúa como controlador **de** datos para determinar el contexto y la retención de datos personales en función de sus necesidades y limitaciones. A continuación, Adobe procesa y almacena estos datos en su nombre.
* Adobe actúa como procesador **de** datos para proporcionar el software y los servicios necesarios para implementar los requisitos de RGPD según su acuerdo con Adobe.
* Tras la integración de Área de trabajo de datos con el servicio de RGPD y según los estándares de RGPD, los visitantes a un sitio (los sujetos **de** datos) pueden ejercer su &quot;derecho al olvido&quot; por parte de Adobe, el procesador de datos. Para lograr el derecho al olvido, usted como controlador de datos puede cargar ID de visitante cuestionados a Adobe desde una interfaz de usuario o API. Consulte la documentación del flujo de trabajo [de GDPR de](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) Adobe Analytics para obtener más información, incluida la sección [enviar solicitudes](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html) de acceso y eliminación.

>[!NOTE]
>
>Para otras fuentes de datos, su organización será responsable de limpiar los ID de visitante cuestionados de otras fuentes de registro, como CRM, POS, IVR y otras fuentes de datos sin procesar. Se dispondrá de paquetes de servicios con ámbito personalizado para proporcionar asistencia a las organizaciones _proporcionando un conjunto completo de archivos de reemplazo para cada fuente_ de datos que los retenedores de servicios en curso deben admitir o mantener.

## Actualización de la implementación de DWB para GDPR

El consultor le asesorará sobre el paquete de servicios adecuado para lograr que las implementaciones existentes sean compatibles. Póngase en contacto con el administrador de éxito del cliente (CSM) para obtener más información.

Si es necesario:

* [Actualice a la versión](https://docs.adobe.com/content/help/es-ES/data-workbench/using/release-notes/release-notes.html) más reciente de Área de trabajo de datos. Para lograr la máxima seguridad, se agregaron nuevos certificados y funciones de seguridad en las versiones de DWB 6.7 necesarias para la integración de GDPR.
* Si utiliza registros de evento heredados de análisis de TSV, actualice a la fuente [de datos de](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2)Avro.
* Si utiliza un UCP heredado (proceso de cliente unificado) con Transform para actualizar los registros existentes, actualice al proceso actual. El proceso actualizado genera directamente un archivo de búsqueda maestro para asignar los ID de visitante entre fuentes.
* Estandarizar el flujo de datos para dar cabida al servicio de RGPD.
* Establezca un paquete de servicios de ámbito personalizado para administrar otras fuentes de registro como CRM, POS, IVR y otras fuentes de datos sin procesar.
* Confirme un período de retención de datos predeterminado de 25 meses o más en el contrato de Analytics.
