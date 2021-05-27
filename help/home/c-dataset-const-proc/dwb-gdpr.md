---
description: La Data Workbench de Adobe proporciona herramientas y procesos para preparar sus datos para cumplir con las Regulaciones Generales de Protección de Datos (RGPD).
title: Compatibilidad de Data Workbench con el RGPD
exl-id: fdc43567-0c57-4851-9073-e295258a8074
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 4%

---

# Compatibilidad de Data Workbench con el RGPD

La Data Workbench de Adobe proporciona herramientas y procesos para preparar sus datos para cumplir con el [!DNL General Data Protection Regulations] (RGPD).

Al igual que todas las soluciones de Adobe Analytics, Data Workbench es compatible con el RGPD ya que proporciona limpieza, eliminación y etiquetado de variables de análisis al procesar la fuente de datos de Adobe Analytics. Para admitir implementaciones de RGPD, Adobe le permite configurar procesos para el RGPD de acuerdo con los permisos de su empresa según se establecen en el acuerdo con Adobe. Consulte [Adobe Analytics y RGPD para obtener información adicional](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/an-gdpr-overview.html).

El reglamento del RGPD identifica las funciones y obligaciones de las diferentes partes responsables de la habilitación del RGPD (consulte [RGPD y su empresa](https://www.adobe.com/es/privacy/general-data-protection-regulation.html)).

* Su organización actúa como **controlador de datos** para determinar el contexto y la retención de datos personales en función de sus necesidades y restricciones. A continuación, Adobe procesa y almacena estos datos en su nombre.
* Adobe actúa como el **procesador de datos** para proporcionar el software y los servicios necesarios para implementar los requisitos del RGPD según su acuerdo con el Adobe.
* Después de integrar la Data Workbench con el servicio RGPD y según los estándares del RGPD, los visitantes de un sitio (los **interesados**) pueden ejercer su &quot;derecho al olvido&quot; mediante Adobe, el procesador de datos. Para lograr el derecho al olvido, usted como responsable del tratamiento de datos puede cargar los ID de visitante cuestionados a la Adobe desde una interfaz de usuario o API. Consulte la documentación [Flujo de trabajo del RGPD de Adobe Analytics](https://docs.adobe.com/help/en/analytics/admin/data-governance/an-gdpr-workflow.html) para obtener más información, incluida la sección [enviar solicitudes de acceso y eliminación](https://docs.adobe.com/content/help/en/analytics/admin/data-governance/gdpr-submit-access-delete.html).

>[!NOTE]
>
>Para otras fuentes de datos, su organización se encargará de limpiar los ID de visitante con desafío de otras fuentes de registro, como CRM, POS, IVR y otras fuentes de datos sin procesar. Los paquetes de servicios personalizados estarán disponibles para proporcionar soporte a las organizaciones _proporcionando un conjunto completo de archivos de reemplazo para cada fuente de datos_ que los retenedores de servicio en curso necesitan para soportar o mantener.

## Actualización de DWB para la implementación del RGPD

Los asesores le asesorarán sobre el paquete de servicios apropiado para que las implementaciones existentes cumplan con las normas. Póngase en contacto con el administrador de éxito de los clientes (CSM) para obtener más información.

Si es necesario:

* [Actualice a la última ](https://docs.adobe.com/content/help/es-ES/data-workbench/using/release-notes/release-notes.html) versión de Data Workbench. Para la máxima seguridad, se agregaron nuevos certificados y funciones de seguridad en las versiones de DWB 6.7 que son necesarias para la integración del RGPD.
* Si utiliza registros de eventos de TSV Analytics heredados, actualice a la [fuente de datos Avro](https://docs.adobe.com/content/help/en/data-workbench/using/dataset/log-proc-config-file/c-log-sources.html#section-9a824b4c3d5549e7952a7111232035b2).
* Si utiliza un UCP heredado (proceso de cliente unificado) con Transform para actualizar los registros existentes, actualice al proceso actual. El proceso actualizado genera directamente un archivo maestro de búsqueda para asignar los ID de visitante entre fuentes.
* Estandarizar el flujo de datos para dar cabida al servicio RGPD.
* Establezca un paquete de servicios de ámbito personalizado para administrar otras fuentes de registro como CRM, POS, IVR y otras fuentes de datos sin procesar.
* Confirme el período de retención de datos predeterminado de 25 meses o más en el contrato de Analytics.
