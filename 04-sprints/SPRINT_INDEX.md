---
document_id: VAULT-SPRINT-INDEX-001
title: Índice de sprints
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-08-16
tags:
  - malak
  - vault
  - sprints
  - navigation
---

# Índice de sprints

> [!warning] Autoridad documental
> Este índice es una representación derivada del trabajo registrado para Malāk.
>
> Un sprint solamente puede considerarse aprobado, activo o cerrado cuando exista evidencia suficiente en las fuentes correspondientes y una decisión humana explícita.

## Referencia operativa

- **Repositorio oficial:** `Aranwill/jarvis`
- **Rama oficial:** `main`

Este índice no mantiene manualmente cuál es el último sprint cerrado, cuál está
activo, HEAD, suite, incremento actual ni autorización del sprint posterior.

Cuando esos datos deban representarse en el Vault, pertenecen a
`MALAK_OPERATIONAL_STATE`.

El cierre, aprobación o activación de un sprint sólo puede establecerse mediante
las fuentes oficiales y la gobernanza humana correspondiente.
## Navegación

- [[02-current-baseline/CURRENT_BASELINE|Referencia de baseline]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]
- [[templates/SPRINT_CLOSE_TEMPLATE|Plantilla de cierre de sprint]]
- [[04-sprints/SPRINT-7.3-CLOSURE|Cierre del Sprint 7.3]]
- [[04-sprints/SPRINT-7.4-CLOSURE|Registro de cierre gobernado de Sprint 7.4]]

## Clasificación documental

### Propuestos

Un sprint propuesto:

- no posee autorización de implementación;
- puede ser revisado, modificado, diferido o rechazado;
- debe permanecer claramente diferenciado de un sprint aprobado.

### Aprobados

Un sprint aprobado debe tener:

- objetivo explícito;
- alcance limitado;
- exclusiones;
- criterios de aceptación;
- validaciones previstas;
- aprobación humana identificable.

### Activos

Un sprint activo debe indicar:

- baseline de inicio;
- estado de implementación;
- pruebas realizadas;
- cambios documentales;
- riesgos o bloqueos;
- trabajo pendiente.

### Cerrados

Un sprint cerrado debe registrar:

- resultado final;
- commits o pull requests relacionados;
- pruebas y validaciones;
- desviaciones respecto del alcance;
- baseline resultante;
- pendientes trasladados;
- aprobación de cierre.

## Reglas permanentes

- No iniciar un sprint sin aprobación explícita.
- No utilizar el roadmap como autorización.
- No mezclar múltiples capacidades independientes en un solo sprint.
- Mantener cambios pequeños, trazables y reversibles.
- Validar código, arquitectura y documentación antes del cierre.
- No modificar snapshots históricos para reflejar estados posteriores.
- El cierre de un sprint no autoriza automáticamente el siguiente.

## Registros históricos de sprint

Los siguientes bloques conservan el estado documentado en sus respectivas
etapas. No representan el estado operativo vigente del proyecto.


### Registro histórico — Sprint 7.3 — Conversation Provider Boundary Stabilization

- **Estado:** cerrado
- **Repositorio:** `Aranwill/jarvis`
- **Rama integrada:** `main`
- **Pull request:** PR #13
- **Merge commit:** `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`
- **Pruebas post-merge:** 74 aprobadas
- **Registro de cierre:** [[04-sprints/SPRINT-7.3-CLOSURE|Cierre del Sprint 7.3]]

Resultado principal:

- `RuntimeConversationProvider` reemplaza la denominación ambigua anterior;
- `ConversationProviderRegistry` normaliza nombres y rechaza registros inválidos;
- `ConversationProviderNotFoundError` encapsula la ausencia de providers;
- `ConversationService` mantiene una responsabilidad mínima;
- Kernel, Planner y `Capability` no fueron modificados;
- no existe integración formal entre `Kernel.receive` y `ConversationService`;
- este registro histórico no autoriza un sprint posterior.

### Registro histórico — Sprint 7.4 — Consolidación de logs, métricas y auditoría

- **Estado:** en progreso — implementación técnica mergeada
- **Repositorio:** `Aranwill/jarvis`
- **Rama integrada:** `feature/sprint-7.4-logs-metrics-audit`
- **Pull request:** PR #14
- **Merge commit:** `7cd7fcc811df01555837319ec4cac0a93ef94fff`
- **Incremento 7:** completado, validado y mergeado
- **Incremento 8:** en ejecución
- **Registro:** [[04-sprints/SPRINT-7.4-CLOSURE|Registro de cierre gobernado del Sprint 7.4]]

Resultado técnico:

- eventos operativos separados de las métricas y de la auditoría;
- `OperationalEvent` y `OperationalEventSink`;
- stores operativos en memoria y JSONL;
- correlación mediante `request_id` generado exclusivamente en la CLI;
- Kernel, Planner, `ConversationService` y contratos conversacionales intactos;
- 94 pruebas específicas y 121 pruebas totales;
- ningún hallazgo bloqueante;
- sin dependencias externas.

Condición de cierre:

- completar la actualización gobernada del Vault;
- commitear y mergear la actualización;
- reconciliar posteriormente `docs/project/sprints/SPRINT-7.4.md`
  en `Aranwill/jarvis/main`;
- no declarar el sprint formalmente cerrado antes de esa reconciliación.

## Reconstrucción histórica

No se agregan retrospectivamente otros sprints cerrados sin una tarea documental específica y basada en evidencia.

La incorporación futura de registros anteriores deberá:

- verificarse contra el repositorio oficial;
- distinguir evidencia histórica de estado operativo mutable;
- evitar reconstrucciones inferidas;
- contar con aprobación explícita.
