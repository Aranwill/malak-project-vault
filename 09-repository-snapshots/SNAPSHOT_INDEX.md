---
document_id: VAULT-SNAPSHOT-INDEX-001
title: Índice de snapshots del repositorio
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-07-20
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

## Snapshot disponible

### 2026-07-20 — `main` — `fdb3ee9`

- [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Abrir snapshot]]
- **Repositorio:** `Aranwill/jarvis`
- **Rama:** `main`
- **HEAD:** `fdb3ee922efc796e53ade1fc3abe4125f4072bd0`
- **Versión nominal:** `v0.6.0-alpha`
- **Último sprint cerrado:** Sprint 7.2 — Runtime Metric Sink Contract

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