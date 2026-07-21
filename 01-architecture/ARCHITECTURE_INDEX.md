---
document_id: VAULT-ARCHITECTURE-INDEX-001
title: Índice de arquitectura
document_type: navigation
status: active
authority: derived
operational_authority: none
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-21
source_repository: Aranwill/jarvis
source_branch: main
baseline_reference: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
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
- **Baseline:** `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`
- **Versión nominal:** `v0.6.0-alpha`
- **Último sprint cerrado:** Sprint 7.3 — Conversation Provider Boundary Stabilization
- **Pull request integrado:** PR #13
- **Suite validada:** 74 pruebas aprobadas
- **Próximo sprint aprobado:** ninguno

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
- los contratos y runtimes implementados;
- los límites entre estado actual y arquitectura futura.

Las dos rutas permanecen separadas. El cierre del Sprint 7.3 no autoriza ni propone una integración entre `Kernel.receive` y `ConversationService`.

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

El mapa inicial de componentes ya existe y permanece como representación derivada del baseline.

Cualquier mapa adicional requiere:

- una necesidad documental concreta;
- verificación directa contra `Aranwill/jarvis/main`;
- alcance explícito;
- revisión humana;
- aprobación antes de su incorporación.

No existe actualmente un nuevo mapa arquitectónico aprobado.