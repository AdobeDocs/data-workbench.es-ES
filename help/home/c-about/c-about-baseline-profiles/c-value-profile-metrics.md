---
description: 'null'
solution: Analytics
title: Métricas del perfil de valores
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: 662bf8fdff196814e5a11c1f5e1ae12d4d57e1db
workflow-type: tm+mt
source-wordcount: '118'
ht-degree: 16%

---


# Métricas del perfil de valores{#value-profile-metrics}

| Métrica | Fórmula | Nivel | Descripción |
|---|---|---|---|
| Conversión  | `Sessions[not Session_Value=#0]/Sessions` | Sesión | El porcentaje de sesiones que generaron valor comercial (tal como se define en el modelo de valor comercial). |
| Pct del valor | `Value/total(Value)` | Sesión | El porcentaje del valor global que se generó a partir del conjunto seleccionado de sesiones. |
| Valor | `sum(Session_Value, Session)*0.01` | Sesión | El valor comercial total generado, en dólares (tal como se define en el Modelo de valores comerciales). |
| Eventos de valor | `Sessions[not Session_Value=#0]` | Sesión | Recuento de sesiones que generaron valor comercial (tal como se define en el Modelo de valores comerciales). |
| Eventos de valor por Visitante | `(Value_Events/Visitors) by Visitor` | Visitante | El número promedio de sesiones para cada visitante que generó valor comercial (tal como se define en el Modelo de valores comerciales). |
| Valor por Visitante | `(Value/Visitors) by Visitor` | Visitante | El valor empresarial promedio generado, en dólares, por cada visitante. |
