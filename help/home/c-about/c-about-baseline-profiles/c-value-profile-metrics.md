---
description: nulo
solution: Analytics
title: Métricas de perfil de valor
topic: Data workbench
uuid: 68951e33-013a-466b-b0f3-839eaef89cb5
translation-type: tm+mt
source-git-commit: aec1f7b14198cdde91f61d490a235022943bfedb

---


# Métricas de perfil de valor{#value-profile-metrics}

| Métrica | Fórmula | Nivel | Descripción |
|---|---|---|---|
| Conversión | [!DNL[Sesiones no Session_Value=#0]/Sesiones] | Sesión | El porcentaje de sesiones que generaron valor comercial (tal como se define en el modelo de valor comercial). |
| Pct del valor | [!DNL Value/total(Value)] | Sesión | El porcentaje del valor global que se generó a partir del conjunto seleccionado de sesiones. |
| Valor | [!DNL sum(Session_Value, Session)*0.01] | Sesión | El valor comercial total generado, en dólares (tal como se define en el Modelo de valores comerciales). |
| Eventos de valor | [!DNL[Sesiones no Session_Value=#0]] | Sesión | Recuento de sesiones que generaron valor comercial (tal como se define en el Modelo de valores comerciales). |
| Eventos de valor por visitante | [!DNL (Value_Events/Visitors) by Visitor] | API | El número promedio de sesiones para cada visitante que generó valor comercial (tal como se define en el Modelo de valores comerciales). |
| Valor por visitante | [!DNL (Value/Visitors) by Visitor] | API | El valor comercial promedio generado, en dólares, por cada visitante. |
