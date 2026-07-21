---
document_id: VAULT-SYNC-FOUNDATION-001
title: Vault Synchronization Agent Foundation
document_type: architecture-proposal
status: under_review
authority: proposal
operational_authority: none
version: 0.1
created: 2026-07-21
last_reviewed: 2026-07-21
source_repository: Aranwill/jarvis
source_branch: main
source_commit: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
vault_repository: Aranwill/malak-project-vault
vault_branch: main
vault_base_commit: e3c2786a22ee9a3584a8e4acc589e14fc891b938
implementation_approved: false
runtime_component: false
kernel_component: false
tags:
  - malak
  - vault
  - obsidian
  - synchronization
  - architecture
---

# Vault Synchronization Agent Foundation

## 1. Propósito

Definir una fundacion externa para mantener actualizado el Vault usado por Obsidian con los cambios verificados de `Aranwill/jarvis/main`.

La iniciativa reduce drift documental, referencias de baseline desfasadas, contradicciones y trabajo manual, sin otorgar autoridad operativa al Vault.

## 2. Naturaleza

```text
Naturaleza: tooling documental externo
Ubicacion: fuera del runtime de Malāk
Estado: under_review
Implementación: no aprobada
Autoridad operativa: ninguna
```

No forma parte de Kernel, Planner, Capability Registry, ConversationService, LLMRuntime, CLI ni Security Control Plane.

## 3. Flujo

```text
detectar
→ comparar
→ clasificar
→ validar
→ proponer
→ preparar cambios
→ generar informe de auditoría
→ validar nuevamente
→ abrir PR draft
→ revisión y merge humano
```

## 4. Componentes conceptuales

- Trigger Controller.
- Evidence Collector.
- Evidence Manifest.
- Deterministic Comparator.
- Change Classifier.
- Authority Policy Gate.
- Document Renderers.
- Validation Pipeline.
- Audit Report Generator.
- Draft PR Preparer.
- Human Review.

## 5. Limites

El repositorio oficial será siempre de solo lectura.

El Vault solo podrá modificarse en una rama nueva y mediante rutas autorizadas. El agente no podrá aprobar ni mergear la PR resultante.

Los snapshots existentes seran inmutables. Las contradicciones criticas y los tipos desconocidos se bloquearan por defecto.

## 6. Clasificación minima

```text
CURRENT_STATE
HISTORICAL_IMMUTABLE
APPROVED_DECISION
OPEN_PROPOSAL
ROADMAP_ITEM
CLOSURE_EVIDENCE
INDEX_REFERENCE
ARCHITECTURAL_CONTRADICTION
SECURITY_CONTRADICTION
UNKNOWN
```

`UNKNOWN` implica denegación por defecto.

## 7. Política aplicable

La iniciativa deberá cumplir obligatoriamente:

- [[00-governance/VAULT_SYNC_AGENT_POLICY|Política obligatoria del Vault Synchronization Agent]].

## 8. Relación con Session Context Generator

Vault Synchronization Foundation obtiene y valida evidencia, detecta drift y prepara cambios.

Session Context Generator solo podrá generar una propuesta de contexto de sesion a partir de evidencia ya validada. No decidira el baseline ni modificara otros documentos.

Esta relación permanece `under_review`.

## 9. Fases

1. Governance & Architecture Specification.
2. Read-only Drift Detector.
3. Deterministic Change Planner.
4. Controlled Vault Branch Writer.
5. Draft PR Preparer.
6. Event-driven Detection.
7. LLM-assisted Documentation.

Las fases no estan aprobadas automaticamente.

## 10. Criterios de aceptacion

- arquitectura externa al runtime;
- Malāk en modo de solo lectura;
- Vault sin autoridad operativa;
- politicas deterministas;
- denegación por defecto;
- snapshots inmutables;
- informe obligatorio;
- LLM sin autoridad;
- PR draft obligatoria;
- merge exclusivamente humano;
- cero modificaciones en `Aranwill/jarvis`.
