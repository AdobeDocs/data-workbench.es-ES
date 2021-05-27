---
description: Al crear un subconjunto, debe especificar un nivel.
title: Selección de un nivel
uuid: 18c2bee7-a70f-4510-978f-830b56780f47
exl-id: 39d8407c-e2ec-4080-8918-26cafbf988df
source-git-commit: d9df90242ef96188f4e4b5e6d04cfef196b0a628
workflow-type: tm+mt
source-wordcount: '149'
ht-degree: 4%

---

# Selección de un nivel{#select-a-level}

Al crear un subconjunto, debe especificar un nivel.

Un nivel es cualquier dimensión contable. Por ejemplo, si está trabajando con datos de sitios web, si selecciona el elemento Tue de la dimensión Día de la semana y crea un subconjunto, debe seleccionar el nivel que desee ver: Vista de página, Sesión o Visitante.

* **Día de la semana=&quot;Valor&quot; por vista de página:** el nivel de vista de página muestra solo las vistas de página que se produjeron un martes.

   ![](assets/vis_Subset_byPageView.png)

* **Día de la semana=&quot;Mar&quot; por sesión:**  el nivel de sesión muestra solo las sesiones que se produjeron un martes.

   ![](assets/vis_Subset_bySession.png)

* **Día de la semana=&quot;Mar&quot; por visitante:** el nivel de visitante muestra todos los visitantes que llegaron al sitio los martes, pero también muestra otros días en los que llegaron al sitio.

   ![](assets/vis_Subset_byVisitor.png)
