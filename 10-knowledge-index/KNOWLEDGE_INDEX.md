---
id: MALAK-KNOWLEDGE-INDEX
title: Malāk Knowledge Index
type: knowledge-index
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-08-16
source_of_truth: repository
source_repository: Aranwill/jarvis
source_branch: main
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
---

# Malāk Knowledge Index

<!-- MALAK_VAULT_SYNC:START -->
## Proyección automática de sincronización

> [!warning] Estado derivado pendiente de revisión
> Este bloque fue generado de forma determinista a partir de
> `Aranwill/jarvis/main`. No aprueba decisiones, no cierra
> sprints y no reemplaza la revisión humana del documento.

- **Run ID:** `20260904T161131930041Z_08abcdd7_55b6fffd`
- **HEAD oficial observado:** `08abcdd7f458c2f2f3569df8f04379aebda73de8`
- **Commit previamente observado:** `43041f920a1b8063491e6d5cabcb1fd887bdc7a8`
- **Generado:** `2026-09-04T16:11:31.930041+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.10.md`
- **Título declarado:** Sprint 7.10 — Conversation Session Isolation Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible

### Commits oficiales observados

- 08abcdd7f458c2f2f3569df8f04379aebda73de8	Merge pull request #59 from Aranwill/docs/sprint-7.10-post-merge-closure
- 28eeb9a955155239b251b001f3ab822cb5f2c5b3	docs(agents): require evidence-first gated implementation planning
- 9f184de85d5b77be6d9833983dac3aafd5d52d6b	docs(project): finalize sprint 7.10 post-merge state
- 270e39b599a7bb3e7e6611e34dd644d0b7004d88	Merge pull request #58 from Aranwill/feat/sprint-7.10-session-isolation
- 07b559c2ac7702291ff9adf47d08d3a0e00dc506	docs(project): close sprint 7.10 session isolation
- 07352239ef7c90798885abf59c981107f6ca09c8	feat(conversation): isolate in-memory context by session
- a0209a44b5bf6c6c0d1c991eb1e8a26c8a6ba5f3	refactor(capability): preserve request metadata across execution boundary

### Evidencia que originó esta proyección

- `baseline-source-change` por `AGENTS.md`
- `baseline-source-change` por `docs/project/implementation_roadmap.md`
- `baseline-source-change` por `docs/project/project_context.md`
- `baseline-source-change` por `docs/project/sprints/SPRINT-7.10.md`
<!-- MALAK_VAULT_SYNC:END -->

<!-- MALAK_OPERATIONAL_STATE:START -->
## Estado operativo derivado

> Estado machine-owned derivado de la fuente oficial.
> No concede autoridad ni reemplaza decisiones humanas.

- **HEAD oficial:** `08abcdd7f458c2f2f3569df8f04379aebda73de8`
- **Ficha de sprint vigente:** `docs/project/sprints/SPRINT-7.10.md`
- **Titulo declarado:** Sprint 7.10 — Conversation Session Isolation Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible
<!-- MALAK_OPERATIONAL_STATE:END -->

## 1. Propósito

Este documento es el índice maestro de navegación del Malāk Project Vault.

Su función es:

- facilitar el acceso al conocimiento activo e histórico;
- conectar gobernanza, baseline, roadmap y decisiones;
- reducir búsquedas manuales;
- preparar relaciones documentales para Obsidian;
- servir como base futura para índices temáticos;
- preservar la diferencia entre fuentes oficiales y artefactos derivados.

Este índice no reemplaza los documentos enlazados ni les concede autoridad adicional.

El índice organiza navegación, relaciones, autoridad documental y referencias
históricas. No mantiene una segunda copia manual del estado operativo mutable.

Cuando deban representarse en el Project Vault, HEAD, sprint estructurado,
conteos de tests, working tree, baseline mutable y demás datos deterministas de
estado pertenecen exclusivamente al bloque machine-managed
`MALAK_OPERATIONAL_STATE`.

---

## 2. Punto de entrada de sesión

- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto operativo de sesión]]
- [[02-current-baseline/CURRENT_BASELINE|Referencia de baseline]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]

Orden recomendado al iniciar una sesión:

1. contexto de sesión;
2. referencia de baseline;
3. decisiones pendientes;
4. roadmap;
5. verificación directa del repositorio oficial.

---

## 3. Gobernanza del Vault

- [[00-governance/VAULT_GOVERNANCE|Gobernanza del Vault]]
- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[00-governance/CONTENT_LIFECYCLE|Ciclo de vida del contenido]]

Estas fuentes determinan:

- qué función cumple el Vault;
- qué contenido puede ingresar;
- qué documento prevalece ante contradicciones;
- cómo se clasifican borradores, propuestas y documentos vigentes;
- qué contenido puede utilizarse en contexto operativo;
- qué contenido podrá recuperarse mediante el futuro RAG.

---

## 4. Referencia de baseline

- [[02-current-baseline/CURRENT_BASELINE|Malāk Current Baseline]]

El índice no mantiene manualmente HEAD, último sprint cerrado, suite vigente,
estado de validación ni autorización del siguiente sprint.

Cuando esos datos deban representarse en el Vault, pertenecen a
`MALAK_OPERATIONAL_STATE`.

Los cierres y resultados concretos de sprints anteriores permanecen accesibles
mediante sus fichas, documentos de cierre, auditorías y registros históricos.

## 5. Roadmap

- [[03-roadmap/IMPLEMENTATION_ROADMAP|Malāk Implementation Roadmap]]

Regla:

> La presencia de una iniciativa en el roadmap no constituye autorización para implementarla.

Criterios de lectura:

- los sprints cerrados se consultan en sus artefactos oficiales e históricos;
- el índice no determina manualmente cuál es el sprint vigente ni el último cerrado;
- las iniciativas futuras requieren revisión y aprobación explícita;
- el cierre de un sprint no autoriza automáticamente el siguiente;
- una idea capturada no forma parte del roadmap aprobado por el solo hecho de existir;
- no debe inferirse una integración arquitectónica por proximidad documental.

El estado estructurado de sprint y demás datos operativos variables pertenecen a
`MALAK_OPERATIONAL_STATE` cuando deban representarse en el Vault.

---
## 6. Registro de decisiones

- [[05-decisions/PENDING_DECISIONS|Malāk Pending Decisions]]

Categorías documentadas:

### Prioridad alta

Las prioridades vigentes deben consultarse en el registro de decisiones y no inferirse desde un sprint histórico.

### Prioridad media

- política de sincronización con Obsidian;
- esquema de metadatos del Vault.

### Decisiones cerradas recientes

- redefinición del Sprint 7.3;
- relación entre Kernel y `ConversationService`;
- selección y cierre formal de Sprint 7.4;
- aprobación, implementación y cierre de Sprint 7.5 — Security Control Plane Foundation;
- aprobación e implementación de la Fase 1 del Vault Synchronization Agent (`DEC-PEND-013`);
- cierre técnico y validación final de la Fase 1;
- separación entre métricas, eventos operativos y auditoría (`DEC-PEND-003`).

### Diferidas

- Session Context Generator;
- RAG externo;
- auditor externo;
- Ruff y mypy.

---

## 7. Plantillas operativas

- [[templates/SESSION_CLOSE_TEMPLATE|Plantilla de cierre de sesión]]
- [[templates/SPRINT_CLOSE_TEMPLATE|Plantilla de cierre de sprint]]

Las plantillas deben copiarse antes de utilizarlas.

No deben completarse directamente sobre el archivo original.

---

## 8. Arquitectura

Carpeta:

[[01-architecture/ARCHITECTURE_INDEX|Índice de arquitectura]]

Estado:

Índice de navegación creado.

Existe un mapa derivado de navegación:

- [[01-architecture/CURRENT_COMPONENTS_MAP|Mapa de componentes actuales]]

El mapa representa:

- el flujo Kernel–Planner–Capability;
- la ruta conversacional integrada mediante `ConversationCapability`;
- la frontera de eventos operativos integrada en la CLI;
- la separación entre métricas, eventos operativos y auditoría.

El subsistema conversacional está integrado de forma indirecta y desacoplada:
la CLI enruta mediante `Kernel.receive()`, mientras `ConversationCapability`
adapta el contrato de Capability hacia `ConversationService`. El Kernel no
depende directamente de servicios, providers ni runtimes concretos.

Contenido futuro previsto:

- mapa de componentes;
- mapa de contratos;
- límites del Kernel;
- relación Kernel–Planner–Capability;
- subsistema conversacional;
- runtime;
- métricas;
- zonas de confianza;
- dependencias arquitectónicas.

Toda representación deberá:

- derivarse de fuentes oficiales;
- identificar su procedencia;
- respetar la jerarquía documental;
- diferenciar implementación documentada y arquitectura futura;
- evitar reinterpretaciones no aprobadas.

No deben crearse diagramas o mapas sin una necesidad concreta.

### Referencias conceptuales

- [[10-knowledge-index/CONCEPTUAL_FOUNDATIONS|Índice de fundamentos conceptuales]]

Esta proyección permite recuperar de forma compacta referencias conceptuales
activas como:

- Malāk Cognitive Dataset Foundation;
- Governed Swarm and Long-Horizon Reference;
- Governed Ephemeral Agent Execution, Evidence and Candidate Evaluation Reference.

Estas referencias son derivadas y no normativas. Su presencia en el Vault no
autoriza implementación, no modifica el baseline y no autoriza ningún sprint.

---

## 9. Sprints

Carpeta:

[[04-sprints/SPRINT_INDEX|Índice de sprints]]

Estado:

Índice de navegación creado.

El cierre del Sprint 7.3 se encuentra registrado en:

- [[04-sprints/SPRINT-7.3-CLOSURE|Cierre del Sprint 7.3]]

El estado de cierre gobernado de Sprint 7.4 se registra en:

- [[04-sprints/SPRINT-7.4-CLOSURE|Registro de cierre gobernado del Sprint 7.4]]

La reconstrucción retrospectiva de sprints anteriores continúa pendiente y requiere una tarea documental separada.

Podrá contener:

- resúmenes de sprints cerrados;
- evidencia de validación;
- relación entre sprint y baseline;
- referencias a PR;
- referencias a commits;
- resultados de tests;
- documentación de cierre.

No reemplazará:

- las fichas oficiales del repositorio;
- el historial Git;
- los PR;
- los documentos de release.

Registro histórico de sprints:

El índice no mantiene una tabla acumulativa propia de sprints cerrados. Los
cierres deben navegarse mediante `SPRINT_INDEX`, las fichas oficiales, los
documentos de cierre y los snapshots históricos correspondientes.

Esto evita que una segunda lista manual quede desfasada respecto de la fuente
oficial o de `MALAK_OPERATIONAL_STATE`.
