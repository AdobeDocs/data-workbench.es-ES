---
description: Se ha creado un conjunto de perfiles estándar para cada aplicación para permitir que uno o más de los perfiles se instalen en un momento determinado.
title: Perfiles de línea de base
uuid: ff76ff7e-ccde-4d99-9109-8612a4a83183
exl-id: f1bd5c1d-5f79-4b8c-9928-97169d553631
source-git-commit: 4ab43bfbad96096fb2cebd77a8be8fa6d49fa7dc
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 0%

---

# Perfiles de línea de base{#baseline-profiles}

{{eol}}

Se ha creado un conjunto de perfiles estándar para cada aplicación para permitir que uno o más perfiles se instalen en un momento determinado.

Estos perfiles de línea de base incluyen definiciones de métricas, dimensiones, filtros, informes, espacios de trabajo y tableros estándar. Adobe actualiza continuamente estos perfiles y los pone a disposición de sus licenciatarios a través de su programa de Soporte de Software. Además, los usuarios de aplicaciones de Adobe pueden definir perfiles adicionales y utilizarlos con o en lugar de los perfiles proporcionados por el Adobe.

El sistema de administración de perfiles permite anular las configuraciones de un perfil por perfiles de nivel superior. Utilice esta función cuando desee anular cualquiera de las definiciones incorporadas en estos perfiles una vez instalados. La instalación de nuevas versiones de estos perfiles sobrescribirá las versiones anteriores. Como resultado, cualquier cambio realizado en estos perfiles directamente se sobrescribiría cuando se instalaran los nuevos perfiles.

Los perfiles para mercados verticales o tipos específicos de empresas o industrias también pueden estar disponibles en Adobe ClientCare. A continuación se describen los perfiles de línea de base:

* La variable **Perfil base** incluye archivos de configuración que se envían con Insight Server. El usuario o el administrador no deben modificar el perfil base. Cualquier modificación realizada en el perfil Base está sujeta a sobrescritura cuando el Adobe publica una versión siguiente de Insight Server u otra aplicación de software.
* La variable **Perfil de tráfico** incluye un conjunto de métricas, dimensiones y filtros fundamentales para el análisis web. También incluye plantillas de espacios de trabajo, informes y tableros que facilitan el análisis, la creación de informes y la comprensión general de las tendencias y los patrones generales de las actividades del sitio en Internet. Este perfil funciona de forma predeterminada con una instalación de línea de base de Site.
* La variable **Perfil de valor** incluye un conjunto de métricas y dimensiones, así como espacios de trabajo de plantilla, informes y tableros asociados con el modelo integrado de conversión y valor comercial del sitio. Este perfil permite a los usuarios identificar eventos de valor en el sitio y asociar un valor monetario a esos eventos.

   Este perfil amplía las capacidades de análisis del sitio al proporcionar un modelo de valor comercial, un método avanzado para medir y rastrear la cantidad de valor generado por el sitio. Los eventos de valor y su valor relativo se definen mediante una sencilla interfaz de arrastrar y soltar dentro del sitio. El sitio utiliza estas definiciones para calcular el valor comercial generado por cada sesión, y esta información se utiliza a su vez para definir métricas como valor, eventos de valor, conversión, etc. Estas métricas le permiten responder a preguntas como:

   * ¿Cuál es la ruta más rentable a través del sitio?
   * ¿Qué referente o campaña ha generado el mayor valor?
   * ¿Cuál es el número promedio de compras en el sitio por día? (¿Cuántos eventos de valor se producen por día de media?)

   Después de definir un Modelo de valor empresarial en el sitio, puede utilizar las métricas y dimensiones de valor en el análisis.

* La variable **Perfil de marketing** incluye un conjunto de métricas y dimensiones y espacios de trabajo de plantilla, informes y tableros asociados con el análisis de campañas de marketing en Internet, incluidos el análisis de búsqueda y el análisis de referente ampliado.

Adobe también proporciona los siguientes perfiles opcionales para utilizar:

* La variable **Perfil de geolocalización de IP** incluye dimensiones y archivos de capa relacionados con el análisis de las ubicaciones de los visitantes en función de los datos de geolocalización de IP proporcionados a Adobe por Quova, Inc. e incorporados a Data Workbench.
* El perfil de inteligencia geográfica de IP incluye dimensiones y archivos de capa relacionados con el análisis de la ubicación del visitante en función de los datos de inteligencia geográfica de IP proporcionados a Adobe por Digital Envoy, Inc., e incorporados a Data Workbench.

Para obtener información sobre los perfiles IP-Geo-location e IP Geo-Intelligence, póngase en contacto con el personal de soporte de Adobe. Las secciones siguientes describen las métricas y dimensiones definidas en cada uno de los perfiles de línea de base.
