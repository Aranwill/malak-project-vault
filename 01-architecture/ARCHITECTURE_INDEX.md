---
document_id: VAULT-ARCHITECTURE-INDEX-001
title: Índice de arquitectura
document_type: navigation
status: active
authority: derived
operational_authority: none
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-25
source_repository: Aranwill/jarvis
source_branch: main
baseline_reference: 7cd7fcc811df01555837319ec4cac0a93ef94fff
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
- **Baseline:** `7cd7fcc811df01555837319ec4cac0a93ef94fff`
- **Versión nominal:** `v0.6.0-alpha`
- **Último sprint formalmente cerrado:** Sprint 7.3 — Conversation Provider Boundary Stabilization
- **Sprint integrado en progreso:** Sprint 7.4 — Consolidación de logs, métricas y auditoría
- **Pull request integrado:** PR #14
- **Suite integral documentada:** 121 pruebas sobre `5b951918006c464745e1eb1e3816bde619fad8b1`
- **Incremento 8:** en ejecución documental gobernada
- **Sprint posterior aprobado:** ninguno

La representación completa del estado vigente se encuentra en:

- [[02-current-baseline/CURRENT_BASELINE|Current Baseline]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto vigente de sesión]]
- [[09-repository-snapshots/SNAPSHOT_INDEX|Índice de snapshots del repositorio]]

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
- contrato `RuntimeMetricSink`;
- contrato `OperationalEvent`;
- contrato `OperationalEventSink`;
- stores operativos en memoria y JSONL;
- correlación conversacional generada exclusivamente en la CLI;
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

Existe un primer mapa arquitectónico derivado:

- [[01-architecture/CURRENT_COMPONENTS_MAP|Mapa de componentes actuales]]

El mapa distingue:

- el flujo Kernel–Planner–Capability;
- el subsistema conversacional de CLI;
- la frontera de eventos operativos;
- los stores operativos separados de las métricas;
- los contratos y runtimes implementados;
- los límites entre estado actual y arquitectura futura.

Las rutas permanecen separadas. Sprint 7.4 no incorporó una
integración entre `Kernel.receive` y `ConversationService`.

La observabilidad operativa no implementa auditoría de seguridad ni
semántica de autorización.

Toda relación representada debe continuar verificándose contra el repositorio oficial y su baseline vigente.

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

- mapa detallado de contratos;
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

## Estado de evolución documental

El mapa de componentes fue revalidado para el baseline `7cd7fcc` e
incorpora la frontera mínima de eventos operativos agregada por Sprint
7.4.

Cualquier mapa adicional requiere:

- una necesidad documental concreta;
- verificación directa contra `Aranwill/jarvis/main`;
- alcance explícito;
- revisión humana;
- aprobación antes de su incorporación.

No existe actualmente un nuevo mapa arquitectónico aprobado.

## Arquitectura externa documentada

- [[01-architecture/VAULT_SYNCHRONIZATION_AGENT_FOUNDATION|Vault Synchronization Agent Foundation]]

Estado arquitectónico:

```text
Fase 1 aceptada, implementada y cerrada
Extensión controlled-proposal aceptada
```

Estado operativo:

```text
tooling documental externo en modos dry-run y controlled-proposal
```

Autoridad operativa:

```text
none
```

La arquitectura implementada:

- permanece fuera del Kernel;
- permanece fuera del runtime;
- permanece fuera del Security Control Plane;
- no modifica `Aranwill/jarvis`;
- no escribe directamente en `main` del Vault;
- prepara propuestas solo en ramas aisladas y allowlisted;
- no utiliza LLM;
- no aprueba ni mergea pull requests;
- no modifica snapshots históricos;
- mantiene `last_applied_commit: null`.

Baseline final del agente:

```text
Rama: main
HEAD: 0feed6eae3d3919ea4867891c12eda5eea81c511
Suite completa: 230 passed
Resultado end-to-end: pass
```

La extensión independiente se registra en `DEC-RES-009` y no constituye
Fase 2.

Fase 2 y posteriores permanecen no aprobadas.

La existencia de esta arquitectura externa no modifica el baseline operativo de Malāk ni convierte al agente en parte del sistema cognitivo.
