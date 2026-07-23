---
document_id: VAULT-SYNC-FOUNDATION-001
title: Vault Synchronization Agent Foundation
document_type: architecture
status: accepted
authority: approved_architecture
operational_authority: none
version: 1.0
created: 2026-07-21
last_reviewed: 2026-07-22
source_repository: Aranwill/jarvis
source_branch: main
source_commit: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
vault_repository: Aranwill/malak-project-vault
vault_branch: main
vault_base_commit: 52976e771ad8307badbc0ac37a78a771e6df51fc
implementation_approved: true
phase_1_status: completed
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

Definir y documentar una fundación externa para observar `Aranwill/jarvis/main`, detectar drift documental y generar evidencia verificable para el Malāk Project Vault sin otorgar autoridad operativa al agente ni al Vault.

La iniciativa busca reducir:

- referencias de baseline desactualizadas;
- contradicciones documentales;
- pérdida de contexto entre sesiones;
- trabajo manual repetitivo;
- riesgo de interpretar evidencia derivada como fuente de verdad.

La fuente de verdad operativa continúa siendo:

```text
Aranwill/jarvis
rama main
```

El Vault permanece como una capa documental derivada, externa y sin autoridad operativa.

## 2. Naturaleza

```text
Naturaleza: tooling documental externo
Ubicación: fuera del runtime de Malāk
Estado arquitectónico: accepted
Fase 1: implementada y cerrada
Autoridad operativa: none
Kernel afectado: no
Runtime afectado: no
```

No forma parte de:

- Kernel;
- Planner;
- Capability Registry;
- ConversationService;
- LLMRuntime;
- CLI;
- runtime de Malāk;
- Security Control Plane.

La arquitectura aprobada se limita a la Fase 1.

Las fases posteriores permanecen no aprobadas.

## 3. Ubicación y separación

Workspace externo verificado:

```text
D:\Ollama\malak-vault-sync-agent
```

Repositorios observados:

```text
D:\Ollama\jarvis
D:\Ollama\malak-project-vault
```

La separación física y lógica preserva:

- independencia respecto del Kernel;
- independencia respecto del runtime;
- permisos mínimos;
- reversibilidad;
- aislamiento de fallos;
- ausencia de autoridad sobre los repositorios observados.

## 4. Baseline final de la Fase 1

```text
Rama: main
HEAD: 954659b
Último commit: docs(baseline): record phase 1 completion
Commit anterior: 7ff4880 fix(audit): align canonical run id contract
Working tree: limpio
```

Baseline formal:

```text
docs/PHASE_1_FINAL_BASELINE.md
```

Validaciones finales:

```text
Suite completa: 148 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
Malāk intacto: sí
Vault intacto: sí
last_applied_commit: null
Hashes SHA-256 verificados: sí
```

## 5. Arquitectura implementada en Fase 1

La arquitectura efectiva de la Fase 1 está compuesta por:

- configuración externa;
- inspección Git de solo lectura;
- controlador de ejecución manual;
- runner determinista;
- lock de ejecución;
- polling externo;
- estado persistente local;
- recolector de evidencia;
- manifiesto de evidencia;
- comparador determinista;
- clasificador de cambios;
- resolvedor determinista de documentos candidatos;
- allowlist y denylist;
- validadores de rutas;
- validadores Markdown;
- validadores YAML;
- validadores de enlaces;
- validadores de hashes;
- validadores de metadatos;
- controles TOCTOU;
- sanitización de evidencia;
- límites de tamaño y alcance;
- generador de informes de auditoría;
- validación end-to-end;
- verificación de invariantes de no modificación.

## 6. Flujo implementado en Fase 1

```text
detectar
→ comparar
→ clasificar
→ resolver documentos candidatos
→ aplicar allowlist y denylist
→ validar
→ generar evidencia
→ generar informe de auditoría
→ verificar hashes
→ comprobar invariantes
→ finalizar sin aplicar cambios
```

El flujo termina sin escritura sobre Malāk ni sobre el Vault.

La Fase 1 no prepara cambios, no crea ramas, no crea commits y no abre pull requests.

## 7. Modelo de autoridad

```text
Agente:
observa, compara, clasifica, valida y genera evidencia

LLM:
no utilizado en la Fase 1

Humano:
revisa, decide, aprueba y autoriza cualquier ampliación
```

La arquitectura preserva:

- Human in Control;
- denegación por defecto;
- mínimo privilegio;
- separación entre observación y decisión;
- trazabilidad;
- reversibilidad;
- ausencia de autoridad autónoma.

## 8. Límites obligatorios verificados

Durante la Fase 1:

- `Aranwill/jarvis/main` permaneció en modo de solo lectura;
- no se modificaron archivos de Malāk;
- no se ejecutó configuración de Malāk;
- no se crearon ramas en Malāk;
- no se crearon commits en Malāk;
- no se ejecutó push sobre Malāk;
- no se modificaron archivos del Vault;
- no se crearon ramas en el Vault;
- no se crearon commits en el Vault;
- no se abrieron pull requests;
- no se aprobaron ni mergearon pull requests;
- no se cerraron decisiones automáticamente;
- no se modificaron snapshots históricos;
- no se utilizó LLM;
- no se implementó servidor HTTP;
- no se implementaron webhooks;
- no se implementó daemon permanente;
- no se adquirió autoridad documental;
- no se adquirió autoridad operativa.

Todos los comandos Git operativos auditados fueron clasificados como read-only.

## 9. Clasificación implementada

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

Las contradicciones críticas se reportan y bloquean la operación afectada.

El agente no resuelve contradicciones de autoridad, gobernanza, arquitectura o seguridad.

## 10. Política aplicable

La arquitectura debe cumplir obligatoriamente:

- [[00-governance/VAULT_SYNC_AGENT_POLICY|Política obligatoria del Vault Synchronization Agent]].

La política continúa preservando:

- solo lectura sobre Malāk;
- autoridad operativa `none`;
- snapshots inmutables;
- revisión humana;
- ausencia de auto-merge;
- ausencia de cierre automático de decisiones;
- prohibición de ampliar alcance sin aprobación explícita.

## 11. Relación con Session Context Generator

Vault Synchronization Agent Foundation:

- obtiene evidencia;
- valida evidencia;
- detecta drift;
- clasifica cambios;
- identifica documentos candidatos;
- genera informes.

Session Context Generator, si se aprueba en el futuro:

- solo podrá producir una propuesta de contexto;
- deberá consumir evidencia ya validada;
- no decidirá el baseline;
- no modificará documentos oficiales;
- no cerrará decisiones;
- no adquirirá autoridad operativa.

Esta relación permanece futura y no aprobada para implementación.

## 12. Estado de gates

```text
Gate 0 — relevamiento de solo lectura: cerrado
Gate 1 — workspace y configuración: cerrado
Gate 2 — inspección Git de solo lectura: cerrado
Gate 3 — estado persistente local: cerrado
Gate 4 — paquete de evidencia: cerrado
Gate 5 — resolución de documentos candidatos: cerrado
Gate 6 — validadores deterministas: cerrado
Gate 7 — informe de auditoría: cerrado
Gate 8 — runner, lock y polling externo: cerrado
Gate 9 — validación final: cerrado
```

Fase 1:

```text
cerrada formalmente
```

El cierre de Gate 9 no autoriza una fase posterior.

## 13. Componentes futuros no implementados

Los siguientes componentes permanecen fuera de la Fase 1:

- Document Renderers con escritura;
- Controlled Vault Branch Writer;
- Commit Generator;
- Draft PR Preparer;
- integración con GitHub para escritura;
- apertura automática de PR draft;
- scheduler operativo;
- servicio permanente;
- daemon;
- webhooks;
- event-driven detection;
- LLM-assisted Documentation;
- modificación automática del baseline;
- cierre automático de decisiones;
- escritura sobre documentos normativos.

Estos elementos no deben presentarse como arquitectura implementada.

## 14. Fases futuras

Secuencia conceptual:

1. Fase 1 — Read-only Drift Detector: completada.
2. Fase 2 — Deterministic Change Planner: no aprobada.
3. Fase 3 — Controlled Vault Branch Writer: no aprobada.
4. Fase 4 — Draft PR Preparer: no aprobada.
5. Fase 5 — Event-driven Detection: no aprobada.
6. Fase 6 — LLM-assisted Documentation: no aprobada.

La numeración es conceptual y no autoriza implementación automática.

Cualquier fase posterior requerirá:

1. necesidad concreta;
2. decisión independiente;
3. alcance explícito;
4. fuera de alcance;
5. evaluación de riesgos;
6. permisos mínimos;
7. rollback;
8. criterios de aceptación;
9. validación arquitectónica;
10. aprobación humana explícita.

## 15. Estado remoto del agente

```text
Remoto configurado: no
URL remota: ninguna
Upstream de main: no
Working tree: limpio
HEAD: 954659b
Respaldo remoto: pendiente de decisión humana
Push ejecutado: no
```

La creación de un remoto y cualquier push futuro constituyen una tarea administrativa separada.

## 16. Evidencia de cierre

El cierre técnico de Fase 1 está documentado en:

- [[07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE|Informe de cierre de la Fase 1 del Vault Synchronization Agent]].

El informe registra:

- baseline final;
- gates cerrados;
- validaciones;
- invariantes;
- hashes SHA-256;
- estado remoto;
- riesgos residuales;
- fuera de alcance;
- autoridad operativa `none`.

## 17. Criterios de aceptación cumplidos

- arquitectura externa al runtime;
- Malāk en modo de solo lectura;
- Vault sin autoridad operativa;
- políticas deterministas;
- denegación por defecto;
- snapshots inmutables;
- evidencia reproducible;
- informe obligatorio;
- LLM no utilizado;
- cero modificaciones en `Aranwill/jarvis`;
- cero modificaciones automáticas en el Vault;
- Gates 0 a 9 cerrados;
- suite completa en verde;
- `compileall` correcto;
- `git diff --check` correcto;
- validación end-to-end `pass`;
- `last_applied_commit: null`.

## 18. Riesgos residuales

Continúan vigentes:

- confundir observación con autoridad;
- interpretar evidencia como aprobación;
- iniciar una fase posterior por continuidad;
- conceder permisos de escritura prematuramente;
- publicar evidencia sensible;
- respaldar remotamente el agente sin revisar secretos y artefactos;
- presentar componentes futuros como implementados;
- incorporar el agente al baseline operativo de Malāk;
- interpretar `pass` como autorización autónoma.

## 19. Regla de cierre

```text
Fase 1: completada
Autoridad operativa: none
Fases posteriores: no aprobadas
```

La arquitectura aprobada de Fase 1 queda cerrada.

Cualquier cambio futuro deberá registrarse mediante una nueva decisión, un nuevo alcance y una nueva aprobación humana.
