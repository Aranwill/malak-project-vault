---
id: VAULT-CONCEPTUAL-FOUNDATIONS
title: Conceptual Foundations Index
type: knowledge_index
status: active
authority_level: derived_reference
authority_rank: 8
version: 1.0
created: 2026-08-14
last_reviewed: 2026-08-14
source_of_truth: Aranwill/jarvis
derived: true
operational_context: false
retrieval_enabled: true
retrieval_scope: active
---

# Conceptual Foundations Index

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
- Engineering Intelligence runtime;
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

## 5. Índice de relaciones

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
```

Estas relaciones son de navegación conceptual y no equivalen a dependencias
de implementación aprobadas.

---

## 6. Reglas de mantenimiento

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

## 7. Estado

```text
Documento: índice derivado
Autoridad: derivada
Source of truth: Aranwill/jarvis
Baseline de Malāk modificado: no
Sprint autorizado: ninguno
```
