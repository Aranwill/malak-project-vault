---
document_id: VAULT-ARCHITECTURE-INDEX-001
title: Índice de arquitectura
document_type: navigation
status: active
authority: derived
operational_authority: none
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-20
source_repository: Aranwill/jarvis
source_branch: main
baseline_reference: fdb3ee922efc796e53ade1fc3abe4125f4072bd0
tags:
  - malak
  - vault
  - architecture
  - navigation
---

# Índice de arquitectura

> [!warning] Naturaleza derivada
> Esta sección organiza representaciones arquitectónicas derivadas de Malāk.
>
> No reemplaza la documentación oficial del repositorio, no redefine la arquitectura y no posee autoridad operativa.

## Estado de referencia

- **Repositorio oficial:** `Aranwill/jarvis`
- **Rama oficial:** `main`
- **Baseline:** `fdb3ee922efc796e53ade1fc3abe4125f4072bd0`
- **Versión nominal:** `v0.6.0-alpha`
- **Último sprint cerrado:** Sprint 7.2 — Runtime Metric Sink Contract
- **Próximo sprint aprobado:** ninguno

La representación completa del estado vigente se encuentra en:

- [[02-current-baseline/CURRENT_BASELINE|Current Baseline]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto vigente de sesión]]
- [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Snapshot del repositorio]]

## Arquitectura actualmente documentada

Según el baseline vigente, Malāk dispone de fundamentos implementados relacionados con:

- Kernel;
- contratos conversacionales;
- Runtime LLM;
- proveedores de conversación;
- servicio conversacional;
- registro y ejecución de capabilities;
- Planner MVP;
- CLI;
- métricas y telemetría de runtime;
- contrato Runtime Metric Sink;
- biblioteca de conocimiento de ingeniería.

> [!important]
> Esta lista es un resumen derivado.
>
> La existencia, estructura y comportamiento real de cada componente deben verificarse en el repositorio oficial y en su documentación correspondiente.

## Relaciones principales conocidas

El baseline documenta actualmente relaciones generales entre:

- Kernel;
- Planner;
- Capability Registry;
- capabilities;
- Conversation Service;
- Conversation Provider;
- LLM Runtime;
- telemetría y métricas.

No se crea todavía un diagrama formal de estas relaciones.

Antes de generar un mapa arquitectónico deberá verificarse:

- qué componentes están efectivamente implementados;
- qué contratos los vinculan;
- qué flujo pertenece al Kernel;
- qué flujo pertenece al subsistema conversacional;
- qué elementos son actuales y cuáles son futuros;
- qué fuente oficial respalda cada relación.

## Principios arquitectónicos aplicables

- Kernel First.
- Capability First.
- Runtime Independence.
- Human in Control.
- Separación de responsabilidades.
- Cambios pequeños, trazables y reversibles.
- Ningún LLM constituye autoridad de seguridad.
- El Vault no modifica ni controla la arquitectura operativa.
- La arquitectura futura no debe presentarse como implementación actual.

## Documentos relacionados

### Gobernanza

- [[00-governance/GOVERNANCE_INDEX|Índice de gobernanza]]
- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[00-governance/METADATA_SCHEMA|Esquema de metadatos]]

### Estado vigente

- [[02-current-baseline/CURRENT_BASELINE|Baseline actual]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]

### Validación y control

- [[06-security/SECURITY_INDEX|Índice de seguridad]]
- [[07-audits/AUDIT_INDEX|Índice de auditorías]]
- [[09-repository-snapshots/SNAPSHOT_INDEX|Índice de snapshots]]
- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro]]

## Mapas arquitectónicos derivados

### Mapas disponibles

- [[01-architecture/CURRENT_COMPONENTS_MAP|Mapa de componentes actuales]]

### Mapas pendientes

Los demás mapas arquitectónicos permanecen pendientes y deberán crearse únicamente ante una necesidad concreta.

Los futuros mapas podrán incluir, cuando exista una necesidad concreta:

- mapa de componentes implementados;
- mapa de contratos;
- límites del Kernel;
- flujo Kernel–Planner–Capability;
- subsistema conversacional;
- runtimes;
- métricas y telemetría;
- zonas de confianza;
- dependencias arquitectónicas.

Cada mapa deberá:

- identificar su baseline;
- citar sus fuentes;
- distinguir estado actual y arquitectura futura;
- evitar inferencias no aprobadas;
- declarar su naturaleza derivada;
- someterse a revisión humana antes de considerarse vigente.

## Restricciones

Esta sección no debe:

- inventar componentes;
- redefinir contratos;
- asumir relaciones no verificadas;
- representar iniciativas futuras como implementadas;
- modificar el roadmap;
- aprobar sprints;
- sustituir documentación oficial;
- habilitar automatizaciones sobre Malāk.

## Próximo paso posible

El primer mapa arquitectónico recomendado sería:

`CURRENT_COMPONENTS_MAP.md`

Su creación permanece pendiente y no constituye una tarea aprobada automáticamente.

Antes de crearlo deberá revisarse directamente el baseline y, cuando corresponda, el repositorio oficial.