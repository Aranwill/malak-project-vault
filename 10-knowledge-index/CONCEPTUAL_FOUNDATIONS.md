---
id: VAULT-CONCEPTUAL-FOUNDATIONS
title: Conceptual Foundations Index
type: knowledge_index
status: active
authority_level: derived_reference
authority_rank: 8
version: 1.1
created: 2026-08-14
last_reviewed: 2026-09-09
source_of_truth: Aranwill/jarvis
derived: true
operational_context: false
retrieval_enabled: true
retrieval_scope: active
---

# Conceptual Foundations Index

<!-- MALAK_VAULT_SYNC:START -->
## Proyección automática de sincronización

> [!warning] Estado derivado pendiente de revisión
> Este bloque fue generado de forma determinista a partir de
> `Aranwill/jarvis/main`. No aprueba decisiones, no cierra
> sprints y no reemplaza la revisión humana del documento.

- **Run ID:** `20260920T194351775984Z_5c942d27_76dfefa3`
- **HEAD oficial observado:** `5c942d27ea610873182ded77b85d0364bfbe15a0`
- **Commit previamente observado:** `79319eef23cdd1490531d01de914712811135d9d`
- **Generado:** `2026-09-20T19:43:51.775984+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.11.md`
- **Título declarado:** Sprint 7.11 — Reproducible Validation Pipeline Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible

### Commits oficiales observados

- 5c942d27ea610873182ded77b85d0364bfbe15a0	Merge pull request #170 from Aranwill/test/e2-structural-observability-v0-red-20260920
- ac4438e1094871a974275f3fb6a0f441e7016d5b	docs: registrar autorización GREEN de observabilidad estructural E2 V0
- 08f6de84e255d536f74c1f3cfc140e4eee3ea9d4	feat: exponer observabilidad determinista de evidencia en E2
- c609c0540cb5c602521d9457e47432b132bedf0b	test: normalizar EOF de observabilidad estructural E2
- 22b86a3c417f63ab72254ff24be1fbff97b058c8	test: agregar RED de observabilidad estructural en E2
- c0b25ab1a6e2494276b359fcfa6e53de232a8cec	docs: registrar autorización RED de observabilidad estructural E2 V0
- 9512f79f40bd67678bb11f66e8e6e14bbc1e76d6	Merge pull request #169 from Aranwill/docs/e2-structural-observability-v0-g0-g1-20260920
- e1673a34c345b7396121afc150cc479cbc25b9b9	docs: compactar diseño de observabilidad estructural E2 V0
- bd41999717f5b0e8f39712a9d168cfc2e7a86672	docs: admitir observabilidad de evidencia estructural en E2 V0

### Evidencia que originó esta proyección

- `baseline-source-change` por `docs/project/sprints/proposals/MALAK-E2-STRUCTURAL-EVIDENCE-OBSERVABILITY-V0-G0-G1-DESIGN.md`
<!-- MALAK_VAULT_SYNC:END -->

<!-- MALAK_OPERATIONAL_STATE:START -->
## Estado operativo derivado

> Estado machine-owned derivado de la fuente oficial.
> No concede autoridad ni reemplaza decisiones humanas.

- **HEAD oficial:** `5c942d27ea610873182ded77b85d0364bfbe15a0`
- **Ficha de sprint vigente:** `docs/project/sprints/SPRINT-7.11.md`
- **Titulo declarado:** Sprint 7.11 — Reproducible Validation Pipeline Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible
<!-- MALAK_OPERATIONAL_STATE:END -->

## 1. Propósito

Este documento mantiene una vista derivada y compacta de referencias
conceptuales conservadas en el repositorio oficial de Malāk.

Su función es facilitar:

- navegación;
- recuperación;
- continuidad entre sesiones;
- relación entre conceptos;
- trazabilidad hacia la fuente oficial;
- identificación de material que requiere revalidación futura.

Este documento no reemplaza los archivos conceptuales originales.

Principio:

> **Vault record != source of truth**

El repositorio oficial de Malāk conserva la autoridad documental primaria.

---

## 2. Reglas de autoridad

Los registros de este índice son derivados.

No podrán:

- aprobar sprints;
- modificar el baseline;
- cerrar decisiones;
- cambiar el roadmap;
- modificar Blueprint;
- modificar Constitución Cognitiva;
- modificar Gobernanza;
- convertir una propuesta conceptual en implementación;
- elevar por sí mismos el nivel de autoridad de un documento.

Cuando exista discrepancia entre este índice y el repositorio oficial,
prevalece la fuente oficial vigente.

---

## 3. Malāk Cognitive Dataset Foundation

### Identidad

```text
Nombre:
Malāk Cognitive Dataset Foundation

Estado:
concept

Autoridad:
non_normative

Rol:
working_reference
```

### Fuente oficial

```text
Repositorio:
Aranwill/jarvis

Ruta:
docs/project/concepts/MALAK_COGNITIVE_DATASET_FOUNDATION.md
```

### Propósito resumido

Preservar el diseño conceptual inicial para definir, evaluar y eventualmente
adaptar el comportamiento cognitivo de Malāk sin asumir que el entrenamiento
de pesos sea necesario.

Principio central:

> **Primero definir qué significa pensar y responder como Malāk; después decidir
> si es necesario entrenar un modelo para conseguirlo.**

### Separación principal

```text
Knowledge Dataset
!=
Cognitive Dataset
```

El conocimiento cambiante deberá mantenerse preferentemente en:

```text
Project Vault
AKS
RAG
Self Model
Memory
Task State
Evidence
```

El comportamiento cognitivo estable podrá evaluarse mediante:

```text
Cognitive Specification
Evaluation Dataset
Prompt / Context Conditioning
Targeted Training
SFT / LoRA / Preference Optimization
```

solo cuando exista evidencia de necesidad.

### Áreas conceptuales principales

- cognitive reasoning;
- architecture reasoning;
- evidence handling;
- uncertainty;
- planning;
- tool use;
- self model;
- conversation;
- governance awareness;
- specialist synthesis;
- long-horizon behavior;
- failure behavior;
- Genesis Dataset.

### Principios asociados

- Knowledge y Cognition deben permanecer separados.
- La cognición puede proponer; la autoridad decide.
- Un modelo no constituye por sí solo la identidad de Malāk.
- El dataset debe tener provenance, versionado, evaluación y revisión humana.
- La evidencia de mejora debe preceder cualquier adaptación de pesos.
- La capacidad de aprender no implica autoridad para cambiar.
- Conversaciones provenientes de contextos o cuentas externas al proyecto no
  deberán incorporarse automáticamente a un dataset personal de Malāk.

### Relación con otras iniciativas

```text
Cognitive Dataset Foundation
├── Malāk Cognitive Identity & Core Foundation
├── Model Governance
├── Model Registry
├── AKS
├── Project Vault
├── Self Model
├── Memory
├── Engineering Intelligence
└── Independent Validation
```

Estas relaciones no constituyen dependencias de implementación inmediata.

### Estado operacional

```text
Implementación: no iniciada
Sprint autorizado: ninguno
Baseline modificado: no
```

### Regla de revalidación

Antes de convertir este concepto en diseño operativo se deberá revisar:

1. baseline vigente;
2. Blueprint;
3. Constitución Cognitiva;
4. Gobernanza;
5. roadmap;
6. decisiones pendientes;
7. estado real de Cognitive Core, Memory, AKS y Model Registry;
8. evidencia E2E disponible;
9. métricas y benchmarks reales;
10. necesidad demostrada de adaptación del modelo.

---

## 4. Governed Swarm and Long-Horizon Reference

### Identidad

```text
Nombre:
Governed Swarm and Long-Horizon Reference

Estado:
concept

Autoridad:
non_normative

Rol:
conceptual_reference
```

### Fuente oficial

```text
Repositorio:
Aranwill/jarvis

Ruta:
docs/project/concepts/GOVERNED_SWARM_LONG_HORIZON_REFERENCE.md
```

### Propósito resumido

Preservar el mapeo conceptual del material relacionado con:

- agentes gobernados;
- Mission Orchestration;
- Dynamic Execution Graph;
- Completion Contracts;
- Agent Leases;
- Persistent Task State;
- checkpoints;
- Execution Ledger;
- Shared Task Board;
- Cognitive Core;
- Engineering Intelligence;
- Digital Twin;
- Cognitive Reference Library.

El documento no crea una iniciativa agentic paralela.

### Relación principal con IDEA-024

La mayor parte de la composición de agentes y Mission Orchestration permanece
representada por:

```text
IDEA-024
Governed Agent Composition & Mission Orchestration Foundation
```

Principio:

> **Malāk dirige el enjambre; el enjambre no gobierna Malāk.**

### Preferencia de complejidad

Cuando produzca calidad equivalente deberá preferirse:

```text
deterministic procedure
        >
single capability
        >
single specialized agent
        >
multi-agent composition
```

La capacidad de ejecutar múltiples agentes no constituye justificación para
crear una flota permanente.

### Conceptos preservados

#### Completion Contracts

Una misión no termina porque un agente declare que terminó.

Debe finalizar cuando sus criterios de aceptación puedan demostrarse mediante
evidencia autorizada.

#### Long-Horizon Task State

La continuidad de tareas largas deberá residir fuera del contexto del modelo.

Principio:

> **La continuidad pertenece al sistema, no a la ventana de contexto de un
> modelo.**

#### Agent Leases

Los permisos temporales deberán, si resultan necesarios, integrarse con:

```text
Secure Context Manager
Identity & Trust Framework
Security Control Plane
```

y no crear una autoridad paralela.

#### Execution Graph

Se conserva como concepto futuro condicionado a necesidad operacional real.

No constituye requisito actual.

#### Execution Ledger

Podrá registrar ejecución de misiones complejas en el futuro, pero no deberá
absorber ni reemplazar:

```text
Runtime Metrics
Operational Events
Security Audit
```

#### Shared Task Board

Se considera preferentemente una proyección de Task State, evitando duplicar
estado.

#### Cognitive Core

Puede actuar como interlocutor e integrador cognitivo futuro.

No deberá poseer autoridad operacional.

```text
Cognitive Core
!=
Authority
```

#### Engineering Intelligence

Deberá emerger de capacidades existentes y futuras en lugar de convertirse en
un mega-sistema independiente.

El baseline `Aranwill/jarvis@c48b72b7` materializó inicialmente E0–E3. El
baseline actual `Aranwill/jarvis@14122dd2` extiende esa vertical con E4 sin
crear un mega-sistema:

```text
E0 Repository Read          INTEGRATED
E1 Governed Knowledge Read  INTEGRATED
E2 Engineering Inspect      INTEGRATED
E3 Engineering Analyze      INTEGRATED
E4 Engineering Propose      INTEGRATED
E5 CLI Integration          DEFERRED / NOT AUTHORIZED
```

E0–E4 permiten observar un snapshot Git exacto, recuperar conocimiento
clasificado, inspeccionar evidencia, producir análisis grounded y generar
propuestas bounded para revisión humana. La propuesta no constituye decisión,
autorización, Implementation Packet ni ejecución. No existe wiring productivo de
ingeniería en Planner/CLI, ni writes, tools, agents, self-modification o authority
effect.

Principio:

> **La autoobservación produce conocimiento; el conocimiento produce
> propuestas; solo la gobernanza produce cambios.**

#### Digital Twin

Permanece en estado conceptual equivalente a `OBSERVE`.

Antes de crear un subsistema específico deberán evaluarse proyecciones
derivadas de Repository + AKS + Vault + Runtime Evidence.

### Separaciones obligatorias

```text
Context
!=
Task State
!=
Memory
!=
Knowledge
!=
Evidence
```

### Restricciones principales

Este concepto no autoriza actualmente:

- Agent Swarm;
- Mission Controller;
- Agent Factory;
- agentes permanentes;
- Execution Graph;
- Graph Health Monitor;
- Task Board independiente;
- Execution Ledger universal;
- Cognitive Core;
- Digital Twin;
- un runtime genérico/autónomo de Engineering Intelligence por encima de las primitives bounded E0–E4;
- recursión ilimitada;
- deliberación multiagente por defecto;
- retries infinitos;
- creación libre de agentes;
- GraphRAG;
- acceso libre a Internet;
- modificación autónoma de políticas o documentos fundacionales.

### Dependencias futuras

Antes de diseñar agentic orchestration en detalle deberá existir suficiente
madurez en:

```text
Security Control Plane
Secure Context / Identity
Sandbox
Evidence
Resource Governance
Model Governance
AKS / Knowledge Governance
Independent Validation
Operational Metrics
Basic capability contracts
Execution contracts
```

### Relación con el E2E

El orden preferido permanece:

```text
single governed E2E
        ↓
real evidence
        ↓
measurement
        ↓
identify limitations
        ↓
introduce only necessary complexity
```

### Estado operacional

```text
Implementación: no iniciada
Sprint autorizado: ninguno
Baseline modificado: no
```

---

## 5. Governed Ephemeral Agent Execution, Evidence and Candidate Evaluation Reference

### Identidad

```text
Nombre:
Governed Ephemeral Agent Execution, Evidence and Candidate Evaluation Reference

Estado:
concept

Autoridad:
non_normative

Rol:
conceptual_reference
```

### Fuente oficial

```text
Repositorio:
Aranwill/jarvis

Ruta:
docs/project/concepts/GOVERNED_EPHEMERAL_AGENT_EXECUTION_EVIDENCE_REFERENCE.md
```

### Propósito resumido

Preservar la referencia conceptual para una futura ejecución agentic temporal,
aislada, observable y descartable, con contexto mínimo, evidencia externa,
lifecycle explícito de recursos y evaluación gobernada de candidatos.

Esta referencia no crea una iniciativa nueva. Conserva una intersección entre:

```text
IDEA-001
Sandbox Containment & Evaluation Evidence Foundation

IDEA-003
Resource Governance Foundation

IDEA-020
Sovereign Agent Fleet Control & Vertical Scaling

IDEA-024
Governed Agent Composition & Mission Orchestration Foundation
```

### Separación con Governed Swarm

```text
Governed Swarm
→ orchestration / missions / long-horizon work

Ephemeral Agent Execution
→ sandbox / least context / evidence / lifecycle / candidate evaluation
```

La referencia de ejecución efímera no sustituye ni absorbe Governed Swarm.

### Principios preservados

- `Least Privilege` debe complementarse con `Least Context`.
- La evidencia canónica no debe depender únicamente del agente evaluado.
- `Agent output != Evidence`.
- `Score != Truth`.
- `Score != Safety`.
- `Score != Authority`.
- Los candidatos deben validarse antes de cualquier ranking.
- La terminación debe revocar autoridad temporal y liberar recursos cuando
  corresponda.
- La evidencia puede justificar una propuesta; no concede autoridad.
- La inteligencia puede proponer; la autoridad decide.

### Lifecycle conceptual

```text
CREATE
→ ASSIGN MINIMUM CONTEXT
→ ISSUE TEMPORARY AUTHORITY
→ EXECUTE
→ COLLECT EXTERNAL EVIDENCE
→ VALIDATE
→ REVOKE TEMPORARY AUTHORITY
→ RELEASE RESOURCES
→ DESTROY OR QUARANTINE SANDBOX
→ RETAIN AUTHORIZED EVIDENCE
```

### Restricciones principales

Este concepto no autoriza actualmente:

- Agent Swarm;
- agentes permanentes;
- Mission Controller;
- Agent Factory;
- múltiples sandboxes por defecto;
- scoring universal;
- deliberación o recursión agentic ilimitada;
- acceso libre a Internet;
- modificación del Kernel;
- auto-merge;
- auto-deploy;
- autoaprobación;
- modificación autónoma de políticas o gobernanza.

### Estado operacional

```text
Implementación: no iniciada
Sprint autorizado: ninguno
Baseline modificado: no
```

Antes de derivar implementación deberá revalidarse contra baseline, Blueprint,
Constituciones, Gobernanza, seguridad, Resource Governance, Model Governance,
Sandbox, Evidence e Independent Validation.

---

## 6. Malāk Research Horizon Map

### Identidad

```text
Nombre:
Malāk Research Horizon Map

Estado:
concept

Autoridad:
non_normative

Rol:
research_horizon_reconciliation
```

### Fuente oficial

```text
Repositorio:
Aranwill/jarvis

Ruta:
docs/project/concepts/MALAK_RESEARCH_HORIZON_MAP.md
```

### Propósito resumido

Preservar el DIFF entre investigación reciente, visión futura y conceptos ya
existentes de Malāk para distinguir qué está alineado, qué requiere refuerzo y
qué constituye todavía un gap conceptual real.

El mapa no crea una segunda arquitectura, no reemplaza `ideas.md`, Long Horizon,
la política de seguridad ni el roadmap. Su función principal es evitar dos
fallos opuestos:

```text
olvidar investigación ya realizada
        !=
convertir investigación en autorización
```

### Taxonomía de reconciliación

```text
ALIGNED
REINFORCE_EXISTING
GAP_CANDIDATE
WATCH
IRRELEVANT
CONFLICTS_WITH_VISION
```

Un `GAP_CANDIDATE` puede originar análisis posterior, pero no equivale a
arquitectura aprobada, roadmap, sprint ni implementación.

### Líneas principales preservadas

Ya representadas suficientemente y que no deben duplicarse:

- Durable Cognitive Execution;
- Governed Self-Improvement;
- Resource Governance;
- Deception / Honeypots / Adversarial Evaluation;
- Incident Forensics / Attack Path.

Refuerzos o gaps que deben revalidarse antes de diseñar futuras superficies:

- Prompt & Context Trust Boundary — `REINFORCE_EXISTING`;
- Memory & Knowledge Trust / Poisoning — `GAP_CANDIDATE`;
- AI Supply-Chain Trust — `GAP_CANDIDATE`;
- Agent Identity & Delegation — `GAP_CANDIDATE`;
- Compromise Containment & Trust Revocation — `GAP_CANDIDATE`;
- Data Classification & Disclosure Control — `GAP_CANDIDATE`;
- Governed Procedural Learning — `REINFORCE_EXISTING`.

Líneas en observación:

- Governed Interoperability MCP/A2A — `WATCH`;
- Multimodal Perception Boundary — `WATCH`;
- World models — `WATCH`.

Conflicto explícito con la visión:

- Autonomous self-modification — `CONFLICTS_WITH_VISION`.

### Invariantes de continuidad

```text
research gap != implementation approved
security requirement != implemented capability
concept != baseline
roadmap != authorization
learning != self-authorization
```

La mejora gobernada permanece permitida como investigación, experimentación
aislada, evidencia y propuesta; la autoaprobación, auto-merge, auto-deploy y
modificación autónoma del baseline permanecen prohibidos.

### Relación con seguridad

El Research Horizon se interpreta junto con la política oficial:

```text
Aranwill/jarvis/SECURITY.md
```

La política de seguridad puede convertir algunas propiedades del horizonte en
requisitos transversales obligatorios sin afirmar que sus mecanismos futuros ya
están implementados.

### Estado operacional

```text
Documento: referencia conceptual
Implementación directa: no autorizada
Sprint autorizado por este documento: ninguno
Baseline modificado: no
```

---

## 7. Índice de relaciones

```text
Malāk Cognitive Dataset Foundation
        |
        +--> Cognitive Identity & Core
        +--> Model Governance
        +--> Model Registry
        +--> AKS
        +--> Project Vault
        +--> Self Model
        +--> Memory
        +--> Engineering Intelligence
        +--> Independent Validation

Governed Swarm and Long-Horizon Reference
        |
        +--> IDEA-024
        +--> Security Control Plane
        +--> Secure Context Manager
        +--> Resource Governance
        +--> Model Governance
        +--> AKS / Knowledge Governance
        +--> Sandbox
        +--> Evidence
        +--> Independent Validation
        +--> Engineering Intelligence

Governed Ephemeral Agent Execution Reference
        |
        +--> IDEA-001
        +--> IDEA-003
        +--> IDEA-020
        +--> IDEA-024
        +--> Security Control Plane
        +--> Secure Context / Identity
        +--> Resource Governance
        +--> Model Governance
        +--> Sandbox
        +--> Evidence
        +--> Independent Validation

Malāk Research Horizon Map
        |
        +--> SECURITY.md
        +--> ideas.md
        +--> Governed Swarm / Long Horizon
        +--> Governed Ephemeral Agent Execution
        +--> Memory / Knowledge Governance candidates
        +--> Model / Artifact Governance candidates
        +--> Security Control Plane
        +--> future admission reviews
```

Estas relaciones son de navegación conceptual y no equivalen a dependencias
de implementación aprobadas.

---

## 8. Reglas de mantenimiento

Cuando una referencia conceptual oficial cambie:

1. verificar el nuevo HEAD de `Aranwill/jarvis/main`;
2. identificar el documento fuente afectado;
3. revisar si cambió su estado, autoridad o alcance;
4. actualizar únicamente el resumen derivado necesario;
5. conservar provenance hacia la fuente oficial;
6. no inferir aprobación o implementación;
7. no modificar snapshots históricos;
8. registrar evidencia de sincronización;
9. requerir revisión humana para toda propuesta de actualización del Vault.

Si un documento conceptual es superseded, rechazado o convertido en decisión
formal, este índice deberá reflejar ese cambio sin borrar la trazabilidad
histórica.

---

## 9. Estado

```text
Documento: índice derivado
Autoridad: derivada
Source of truth: Aranwill/jarvis
Baseline de Malāk modificado: no
Sprint autorizado: ninguno
```
