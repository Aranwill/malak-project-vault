---
document_id: VAULT-SPRINT-INDEX-001
title: Índice de sprints
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-07-21
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

## Estado actual

- **Último sprint cerrado:** Sprint 7.3 — Conversation Provider Boundary Stabilization
- **Pull request integrado:** PR #13
- **Baseline resultante:** `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`
- **Suite validada:** 74 pruebas aprobadas
- **Próximo sprint aprobado:** ninguno
- **Repositorio oficial:** `Aranwill/jarvis`
- **Rama oficial:** `main`

El cierre del Sprint 7.3 no autoriza el inicio automático de Sprint 7.4 ni de ninguna otra propuesta.

## Navegación

- [[02-current-baseline/CURRENT_BASELINE|Baseline vigente]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]
- [[templates/SPRINT_CLOSE_TEMPLATE|Plantilla de cierre de sprint]]

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

## Sprints registrados

### Sprint 7.3 — Conversation Provider Boundary Stabilization

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
- no existe un próximo sprint aprobado.

## Reconstrucción histórica

No se agregan retrospectivamente otros sprints cerrados sin una tarea documental específica y basada en evidencia.

La incorporación futura de registros anteriores deberá:

- verificarse contra el repositorio oficial;
- distinguir evidencia histórica de estado vigente;
- evitar reconstrucciones inferidas;
- contar con aprobación explícita.
