---
document_id: VAULT-SNAPSHOT-INDEX-001
title: Índice de snapshots del repositorio
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-07-25
tags:
  - malak
  - vault
  - snapshots
  - repository
  - navigation
---

# Índice de snapshots del repositorio

> [!important] Naturaleza histórica
> Los snapshots representan estados históricos verificados del repositorio oficial.
>
> Son derivados, inmutables y no constituyen una fuente operativa alternativa.

## Snapshot disponibles

### 2026-07-20 — `main` — `fdb3ee9`

- [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Abrir snapshot]]
- **Repositorio:** `Aranwill/jarvis`
- **Rama:** `main`
- **HEAD:** `fdb3ee922efc796e53ade1fc3abe4125f4072bd0`
- **Versión nominal:** `v0.6.0-alpha`
- **Último sprint cerrado:** Sprint 7.2 — Runtime Metric Sink Contract

### 2026-07-21 — `main` — `fd4da3d`

- [[09-repository-snapshots/2026-07-21_MAIN_FD4DA3D|Abrir snapshot]]
- **Repositorio:** `Aranwill/jarvis`
- **Rama:** `main`
- **HEAD:** `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`
- **Versión nominal:** `v0.6.0-alpha`
- **Último sprint cerrado:** Sprint 7.3 — Conversation Provider Boundary Stabilization
- **Pull request integrado:** PR #13
- **Suite validada:** 74 pruebas aprobadas
- **Próximo sprint aprobado:** ninguno

### 2026-07-25 — `main` — `7cd7fcc`

- [[09-repository-snapshots/2026-07-25_MAIN_7CD7FCC|Abrir snapshot]]
- **Repositorio:** `Aranwill/jarvis`
- **Rama:** `main`
- **HEAD:** `7cd7fcc811df01555837319ec4cac0a93ef94fff`
- **Versión nominal:** `v0.6.0-alpha`
- **Pull request integrado:** PR #14
- **Sprint 7.4:** implementación técnica mergeada; cierre formal pendiente
- **Incremento 7:** completado, validado y mergeado
- **Incremento 8:** en ejecución documental gobernada
- **Suite integral documentada:** 121 pruebas sobre `5b951918006c464745e1eb1e3816bde619fad8b1`
- **Evidencia del agente:** `20260725T032607612120Z_7cd7fcc8_49858c60`

## Reglas de creación

Un snapshot nuevo debe:

- corresponder a un estado verificable del repositorio oficial;
- registrar el hash completo de `HEAD`;
- registrar rama, fecha y estado de validación;
- diferenciar hechos observados de interpretaciones;
- utilizar un nombre estable;
- enlazar las fuentes relevantes;
- crearse como documento nuevo.

## Inmutabilidad

Un snapshot existente no debe modificarse para reflejar:

- commits posteriores;
- nuevos resultados de pruebas;
- cambios del roadmap;
- nuevas decisiones;
- correcciones retrospectivas silenciosas.

Cuando un snapshot necesite una aclaración, deberá generarse un documento complementario o uno nuevo.

## Convención de nombre

```text
AAAA-MM-DD_RAMA_HASH-CORTO.md
```
