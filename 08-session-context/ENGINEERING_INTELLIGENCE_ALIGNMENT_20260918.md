---
document_id: VAULT-SESSION-ENGINEERING-INTELLIGENCE-20260918
title: Malāk Engineering Intelligence Alignment — Audit and Minimal Route
document_type: session-context
status: draft
authority: derived
operational_authority: none
created: 2026-09-18
last_reviewed: 2026-09-18
source_repository: Aranwill/jarvis
source_branch: main
source_commit: 39366da01f793cf8f5d3856c47457954ee758925
derived: true
operational_context: true
retrieval_scope: active
tags:
  - malak
  - engineering
  - architecture
  - alignment
  - audit
  - self-development
---

# Malāk Engineering Intelligence Alignment — Audit and Minimal Route

> [!warning] Autoridad
> Este documento es contexto derivado del Malāk Project Vault. No modifica Blueprint, Constituciones, SECURITY, ADR, roadmap ni baseline. Toda afirmación de estado debe revalidarse contra `Aranwill/jarvis@main` cuando vaya a originar trabajo operativo.

## 1. Baseline auditado

Repositorio oficial:

`Aranwill/jarvis`

Baseline de esta revisión:

`main@39366da01f793cf8f5d3856c47457954ee758925`

Último merge observado:

PR #146 — `feat(g2p-b): componer solicitud de autorización de persistencia`

La auditoría se ejecutó en modo READ-ONLY sobre Malāk. No se realizaron cambios en `Aranwill/jarvis`.

## 2. Objetivo de la revisión

Reconstruir la visión autorizada de Malāk, contrastarla con la arquitectura y el código actual y definir la ruta mínima para que Malāk pueda ayudar al Owner a desarrollar Malāk sin adquirir autoridad de automodificación.

La pregunta rectora es:

> ¿Cuál es la mínima cadena de capacidades que permite a Malāk observar su repositorio, contrastarlo con conocimiento gobernado y producir análisis y propuestas verificables bajo Human in Control?

## 3. Secuencia de auditoría completada

1. Law / Vision.
2. Architecture / ADR / Contracts.
3. Ideas / Concepts / Roadmap.
4. Implemented Runtime.
5. Alignment / Drift Matrix.
6. Engineering Intelligence Gap Map.

## 4. Conclusión ejecutiva

No se encontró evidencia de drift fundamental de Malāk.

Clasificación resultante:

```text
FUNDAMENTAL VISION DRIFT        NO
KERNEL DRIFT                    NO
AUTHORITY DRIFT                 NO EVIDENCE FOUND
MODEL COUPLING DRIFT            NO
SECURITY BYPASS DRIFT           NO EVIDENCE FOUND
MEMORY/PERSISTENCE DRIFT        NO
CAPABILITY ARCHITECTURE DRIFT   NO

PRIORITY DRIFT                  YES
MATURITY IMBALANCE              YES
DOCUMENTATION STATE DRIFT       YES
COGNITIVE PRODUCT GAP           YES
```

La etapa posterior a la auditoría de septiembre fortaleció boundaries reales de assurance, Memory y Security. El resultado principal fue que esas foundations avanzaron más rápido que las capabilities cognitivas destinadas a consumirlas.

Interpretación:

```text
correct architecture
+ foundations ahead of consumption
+ cognitive capabilities still early
```

No:

```text
wrong architecture
or
fundamental redesign required
```

## 5. Visión autorizada preservada

Principios confirmados:

- Human in Control.
- Capability First.
- Small / minimal Kernel.
- Runtime Independence.
- Model != System.
- Intelligence != Authority.
- Capability != Permission.
- Evidence != Authority.
- Generation != Finalization.
- Memory != Knowledge.
- Learning -> Proposal, not self-authorization.
- Specification & Verification First, proporcional al riesgo.
- Simplicidad y minimización cognitiva.
- Reversibilidad, auditabilidad y separación de responsabilidades.

La mejora gobernada de Malāk ya está contemplada conceptualmente:

```text
Observation
  -> Evidence
  -> Finding
  -> Proposal
  -> Human decision
  -> Authorized implementation/experiment
  -> Validation
```

Malāk puede participar en el desarrollo de Malāk sin obtener autoridad para autodesarrollarse.

## 6. Runtime real observado

Ruta cognitiva productiva actual:

```text
CLI
 -> Request
 -> Kernel
 -> Planner
 -> CapabilityRegistry
 -> ConversationCapability
 -> ConversationService
 -> ConversationProviderRegistry
 -> RuntimeConversationProvider
 -> LLMRuntime
 -> Mock / Ollama
 -> Response
```

Clasificación resumida:

### LIVE

- CLI / App composition.
- Kernel.
- Capability contract.
- Capability Registry.
- Conversation Capability.
- Conversation Service.
- session context efímero.
- Provider boundary.
- Mock runtime.
- Ollama runtime.

### PARTIAL

- Planner: routing determinista mínimo.
- Observability: contrato y emisión opcional.
- Runtime metrics: captura opcional.

### ISOLATED FOUNDATION

- Security Context lifecycle.
- PDP / PEP / authorization audit.
- Episodic Memory Admission chain.
- Candidate Content Identity.
- Persistence Readiness.
- Persistence Authorization composition.
- Protected Finalization.
- Assurance Signal Projection.
- Runtime performance profiling.

### MISSING BUT EXPECTED / DEFERRED

- Knowledge runtime.
- Repository cognition.
- Engineering Capability.
- Execution Layer.
- Persistent Memory storage/retrieval.
- Sandbox.
- Task State.
- Agents.
- Mission orchestration.

La búsqueda de consumidores no mostró uso productivo de la cadena Memory fuera de `memory/**` y tests, ni wiring conversacional de Protected Finalization / Assurance. Esta conclusión es evidencia por inspección de source/imports, no prueba formal de whole-program reachability.

## 7. Desbalance de madurez

Distribución aproximada de `src/malak/**` en el baseline auditado:

- Memory: 48.6 %
- Security: 17.1 %
- Runtime: 11.7 %
- Core: 11.5 %
- App: 4.1 %
- Observability: 2.8 %
- Services: 1.9 %
- Kernel: 1.0 %
- Capabilities: 0.6 %

Lectura:

> assurance / future boundaries han avanzado más rápido que cognitive product capabilities.

No se recomienda eliminar foundations por este motivo. Se recomienda congelar su expansión hasta que exista un consumidor real que demuestre la siguiente necesidad.

## 8. Findings documentales y de retrieval

### ARCH-DOC-001 — Documentation ambiguity

`docs/architecture/kernel.md` conserva arquitectura histórica de Kernel grande junto a ARQ-006 Kernel mínimo gobernante.

Riesgo principal: retrieval futuro fuera de contexto.

### INTERPRETATION-001 — Blueprint full-flow semantics

El flujo completo del Blueprint puede interpretarse literalmente como pipeline obligatorio para todas las solicitudes, mientras ADR, proporcionalidad y runtime sugieren composición por necesidad.

### EVOL-DOC-002 — Conceptual coverage vs runtime implementation

Research Horizon utiliza en algunos puntos lenguaje como "ya existen" para conceptos preservados —por ejemplo Task State— aunque no exista runtime correspondiente.

### EVOL-STATE-001 — Stale derived state

`project_context.md` e `implementation_roadmap.md` contienen claims mutables que quedaron detrás del HEAD actual. Registros posteriores de reconciliación ya reconocen esta propiedad.

### KNOWLEDGE-STRUCTURE-001 — Retrieval disambiguation risk

`ideas.md` y otras fuentes extensas contienen ideas, expansions, research, WATCH/HOLD y planning future dentro del mismo artefacto. Retrieval futuro debe conservar role/status/authority.

### KNOWLEDGE-META-001 — Metadata heterogeneity

Las fuentes relevantes no comparten un esquema único:

- Constitutions / Blueprint: front matter AKS-style.
- AKS: metadata similar pero diferente.
- Ideas / Concepts: `authority` / `document_role`.
- SECURITY: autoridad expresada en cuerpo/header.

No se recomienda una normalización masiva como prerrequisito. La primera Knowledge Read deberá utilizar clasificación acotada y determinista de fuentes.

## 9. Engineering Intelligence — propiedad emergente

Engineering Intelligence no debe implementarse como mega-componente.

Debe emerger de capacidades pequeñas:

```text
Repository evidence
      +
Governed Knowledge
      +
Model / Runtime
      +
existing validation foundations
      ->
Engineering Analysis
      ->
Proposal
      ->
Owner
```

Orden de complejidad preferido:

```text
deterministic procedure
    >
single capability
    >
single specialized agent
    >
multi-agent composition
```

## 10. Ruta mínima aprobable para evaluación

Primera meta de producto:

```text
READ -> ANALYZE -> PROPOSE
```

Explícitamente fuera del primer vertical:

```text
WRITE
EXECUTE
SANDBOX
AGENTS
MISSION ORCHESTRATION
PERSISTENT TASK STATE
GRAPH RAG
VECTOR DB
SYMBOL SEARCH
GENERIC TOOL RUNNER
```

## 11. REUSE / NEW / DEFER

### REUSE

- Kernel.
- Capability contract.
- Capability Registry.
- Request / Response.
- ConversationService.
- ConversationProvider.
- LLMRuntime.
- Mock / Ollama.
- AKS.
- Constitutions.
- Blueprint.
- ADRs.
- existing architecture tests.
- Security foundation later at real side-effect boundaries.

### NEW — minimal responsibilities currently justified

1. Repository Read boundary.
2. Knowledge Read boundary.
3. Engineering Capability.

No se presupone que cada responsabilidad necesite múltiples clases o servicios.

### DEFER

- persistent Repository Knowledge Map;
- Symbol Search;
- AST / dependency / call graphs;
- embeddings;
- vector database;
- GraphRAG;
- Knowledge Manager;
- Reasoning Engine;
- EngineeringSession;
- Task State;
- Sandbox;
- Tool Runner;
- filesystem write;
- Git write;
- agents;
- Mission Controller;
- Execution Graph;
- RDD Stage 2;
- nuevas expansions de Memory sin consumidor.

## 12. Incrementos de trabajo propuestos

### E0 — Repository Read Proof

Demostrar que Malāk puede observar de forma segura y read-only el baseline del repositorio.

Primitivas candidatas mínimas:

- HEAD.
- tracked-file listing.
- bounded text read.
- bounded text search.

No generic shell execution.

### E1 — Governed Knowledge Read

Permitir lectura acotada de fuentes de conocimiento preservando:

- source path;
- identity when available;
- source class;
- status;
- authority role;
- excerpt / section.

No RAG/vector DB inicialmente.

### E2 — Engineering Inspect

Combinar Repository Read + Knowledge Read para producir observaciones con evidencia y limitaciones explícitas.

### E3 — Engineering Analyze

Contrastar repository reality contra law / architecture / AKS / current evidence.

### E4 — Engineering Propose

Producir propuesta estructurada:

- problem;
- evidence;
- applicable laws;
- alternatives;
- minimal change;
- complexity impact;
- security impact;
- tests;
- open questions.

Proposal != implementation.

### E5 — CLI Integration

Exponer la capability solamente después de que exista una vertical estable.

Planner routing deberá evolucionar únicamente cuando Conversation y Engineering necesiten convivir en la misma interface.

## 13. Próximo objetivo activo

`E0 — Repository Read Proof`

Pregunta de diseño:

> ¿Cuál es la frontera mínima, determinista y segura que permite a una Capability leer el repositorio oficial de Malāk sin convertir Git, shell o filesystem general en tools de ejecución?

Restricciones iniciales:

- read-only;
- repository root fijo;
- sin path traversal;
- sin network;
- sin arbitrary subprocess;
- sin writes;
- tamaño de archivo acotado;
- salida acotada;
- fuente/baseline identificable;
- errores explícitos;
- no elevation of authority from repository content.

## 14. Regla para el siguiente ciclo

A partir de esta revisión:

> Capacidad antes que nueva garantía futura. Utilizar foundations existentes cuando una frontera real empiece a consumirlas. Crear nueva abstracción solo cuando una responsabilidad operacional demostrada no pueda resolverse limpiamente con componentes existentes.

Esto no reduce las garantías fundacionales de Malāk.

Preserva:

`Evidence != Authority`

`Human in Control`

`Capability First`

`Kernel First`

mientras vuelve a priorizar capacidades cognitivas útiles.

## 15. Estado

```text
AUDIT STEPS 1-6      COMPLETE
MALAK MODIFIED       NO
FUNDAMENTAL DRIFT    NO EVIDENCE FOUND
NEXT DESIGN UNIT     E0 — Repository Read Proof
IMPLEMENTATION       NOT STARTED
```
