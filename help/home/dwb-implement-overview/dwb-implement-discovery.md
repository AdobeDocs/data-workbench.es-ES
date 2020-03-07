---
description: Recopile y describa las preguntas comerciales apropiadas para su entorno de mercadotecnia al implementar el Área de trabajo de datos.
title: Descubrimiento y requisitos del área de trabajo de datos
uuid: 436f0c32-b4e2-41dd-a8e9-531e0a195276
translation-type: tm+mt
source-git-commit: 6443bdf8856ba51252685fa0c1ed65f831142956

---


# Descubrimiento y requisitos del área de trabajo de datos{#data-workbench-discovery-and-requirements}

Recopile y describa las preguntas comerciales apropiadas para su entorno de mercadotecnia al implementar el Área de trabajo de datos.

Esta sección le permite recopilar entradas sobre las preguntas y tareas necesarias para diseñar soluciones en el Área de trabajo de datos (DWB), que pueden abordar estas preguntas de manera precisa, inequívoca y sin depender de la tecnología, proporcionando referencias a la terminología comercial y a la solución Adobe Analytics Premium. Esta sección proporciona información sobre estos objetivos y los requisitos asociados.

## Fase 1: Objetivos y objetivos clave del negocio {#section-bb8f3d6071bf48d9a546ac2b80341e1d}

Las siguientes tablas le indican que identifique su base de clientes y analice la construcción de su implementación de DWB.

* Explicación de la base de clientes
* Explicación del caso empresarial específico (por ejemplo, eficacia del autoservicio y otros canales de datos/fuentes de datos sin conexión)

**Comprender la base de clientes**

Comprender por qué los clientes utilizan su sitio, los desafíos que enfrenta y cómo DWB lo ayudará en base a su modelo comercial. Por ejemplo: cómo medir, monitorear y analizar los clientes para que vendan otros productos y servicios, obtener la lista de usuarios activos y la penetración de cuentas, y otros objetivos.

| ID | Pregunta comercial/Requisito | Prioridad | Fase | Dependencias |
|---|---|---|---|---|
| 1a | Pregunta comercial específica 1 | Alto/Medio/Bajo | 1 | Clave común, dependiente de alguna otra clave, etc. |
| 1b | Pregunta comercial específica 2 | Alto | 1 | Cualquier dependencia |

Construcción de análisis

<table id="table_6CA959E521964E27804BB2A65EC4BBDE"> 
 <tbody> 
  <tr> 
   <td colname="col1">Fuentes de datos de análisis de espacio de trabajo</td> 
   <td colname="col2"> Agregar nombre de espacio de trabajo </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas y dimensiones del espacio de trabajo necesarias </p> </td> 
   <td colname="col2"> <p>Identificar dimensiones: </p> <p>Identificar métricas: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtros, indicadores y herramientas de espacio de trabajo necesarios </td> 
   <td colname="col2"> <p>Identificar segmentos: </p> <p>Identifique las herramientas: </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ¿Qué acciones se pueden derivar de este análisis? </td> 
   <td colname="col2"> Comprenda las tareas y el contenido con espacios de trabajo DWB específicos. </td> 
  </tr> 
 </tbody> 
</table>

## Fase 2: Explicación de casos comerciales específicos {#section-309d7ec6f631458c9c9e6bd2cef2fa4c}

Comprender otras fuentes y canales de datos y conocer cómo se relacionarán con los casos comerciales.

<table id="table_733CCD9F4E9048C2865758B8E8D027DC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> ID </th> 
   <th colname="col2" class="entry"> Preguntas y requisitos comerciales </th> 
   <th colname="col3" class="entry"> Prioridad </th> 
   <th colname="col04" class="entry"> Fase </th> 
   <th colname="col4" class="entry"> Dependencias </th> 
   <th colname="col5" class="entry"> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 2a </td> 
   <td colname="col2"> Requisito comercial específico 1 </td> 
   <td colname="col3"> <p>Alto/Medio/Bajo </p> </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Clave común, dependiente de otra clave, indicador/identificador de cuenta, etc. </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 2b </td> 
   <td colname="col2"> <p>Requisito comercial específico 2 </p> </td> 
   <td colname="col3"> Alto/Medio/Bajo </td> 
   <td colname="col04"> 1 </td> 
   <td colname="col4"> <p>Cualquier dependencia </p> </td> 
   <td colname="col5"> </td> 
  </tr> 
 </tbody> 
</table>

**Construcción de análisis**

<table id="table_680C5D257CBF42519EFB8B96A00543C5"> 
 <tbody> 
  <tr> 
   <td colname="col1">Fuentes de datos de análisis de espacio de trabajo
     </td> 
   <td colname="col2">
     Nombre de espacio de trabajo de muestra </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Métricas y dimensiones del espacio de trabajo necesarias </p> </td> 
   <td colname="col2"> <p>Dimensiones: Defina las dimensiones requeridas. </p> <p>Métricas: Defina las métricas necesarias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Filtros, indicadores y herramientas de espacio de trabajo necesarios </td> 
   <td colname="col2"> <p>Segmentos: Identifique los segmentos de clientes. </p> <p>Herramientas: Seleccione las herramientas necesarias. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> ¿Qué acciones se pueden derivar de este análisis? </td> 
   <td colname="col2"> Qué comprender desde este espacio de trabajo </td> 
  </tr> 
 </tbody> 
</table>

**Fuentes de datos**

| Fuentes de datos | Prioridad | ¿Con qué frecuencia se reciben los datos? |
|---|---|---|
| Grupo de informes Nombre del sitio 1 (RSID) | 1 | Por hora |
| Nombre del sitio 2 (si existe) (RSID) | 1 | Por hora |
| Fuente de datos 1 (si procede) | 2 | Diaria? |
| Fuente de datos 2 (si procede) | 3 | Diaria? |
