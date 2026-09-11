---
id: MALAK-KNOWLEDGE-INDEX
title: Malāk Knowledge Index
type: knowledge-index
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.1
created: 2026-07-20
last_reviewed: 2026-09-09
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

- **Run ID:** `20260911T232318209174Z_c979f481_b2f9e3b0`
- **HEAD oficial observado:** `c979f481e2e5353c8953e41e56e9218c7b1d4c6f`
- **Commit previamente observado:** `5865da6a5e502fe71e35e2e38bc4cceaab9b3600`
- **Generado:** `2026-09-11T23:23:18.209174+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.11.md`
- **Título declarado:** Sprint 7.11 — Reproducible Validation Pipeline Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible

### Commits oficiales observados

- c979f481e2e5353c8953e41e56e9218c7b1d4c6f	Merge pull request #116 from Aranwill/docs/reconcile-implementation-roadmap-post-g2a-20260911
- e3870435e31aa18905ae3ba16e7d0fca007109c4	docs(state): reconcile implementation roadmap after G2A
- 7d295007de574f2f307328f3d9d26d768e0fb0a2	Merge pull request #115 from Aranwill/ci/ubuntu-windows-only-20260911
- 34566b59b400e52ad542818c3e47e8512e78e4d1	Merge pull request #114 from Aranwill/docs/reconcile-project-context-post-g2a-20260911
- 6fe89a762f3064168c76a0ad9ab4c5cf46e154da	ci: limitar validación a ubuntu y windows
- ec6ec2cd98b749ae334344b698bd2e334e87571a	docs(state): reconcile project context after G2A
- e45a3e3c0ebf657a513596aa74452413479c05d1	Merge pull request #111 from Aranwill/docs/assurance-signal-authority-g0-g1-20260911
- c2a0d69768c65f773c34b19dbb73d33a66fe7a98	docs(cognition): rebase assurance signal authority onto main
- ecb1315946f47534135bbdc73d94ccf88df0d8d6	feat(cognition): implementar G2A protected finalization foundation (#110)

### Evidencia que originó esta proyección

- `baseline-source-change` por `docs/project/implementation_roadmap.md`
- `baseline-source-change` por `docs/project/project_context.md`
- `baseline-source-change` por `docs/project/sprints/proposals/MALAK-ASSURANCE-SIGNAL-AUTHORITY-G0-G1-DESIGN.md`
- `baseline-source-change` por `docs/project/sprints/proposals/MALAK-PROGRESSIVE-COGNITIVE-ASSURANCE-RUNTIME-G0-INSPECTION.md`
- `baseline-source-change` por `docs/project/sprints/proposals/MALAK-PROGRESSIVE-COGNITIVE-ASSURANCE-RUNTIME-G1-DESIGN.md`
- `baseline-source-change` por `docs/project/sprints/proposals/MALAK-PROGRESSIVE-COGNITIVE-ASSURANCE-RUNTIME-G2A-IMPLEMENTATION-CANDIDATE-SPEC.md`
- `baseline-source-change` por `docs/project/sprints/proposals/MALAK-PROGRESSIVE-COGNITIVE-ASSURANCE-RUNTIME-SCOPE-FREEZE-CANDIDATE.md`
- `baseline-source-change` por `docs/project/status/MALAK-POST-AUDIT-REBASELINE-20260911.md`
<!-- MALAK_VAULT_SYNC:END -->

<!-- MALAK_OPERATIONAL_STATE:START -->
## Estado operativo derivado

> Estado machine-owned derivado de la fuente oficial.
> No concede autoridad ni reemplaza decisiones humanas.

- **HEAD oficial:** `c979f481e2e5353c8953e41e56e9218c7b1d4c6f`
- **Ficha de sprint vigente:** `docs/project/sprints/SPRINT-7.11.md`
- **Titulo declarado:** Sprint 7.11 — Reproducible Validation Pipeline Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible
<!-- MALAK_OPERATIONAL_STATE:END -->

## 1. Propósito

Este documento es el índice maestro de navegación del Malāk Project Vault.

Su función es:

- facilitar el acceso al conocimiento activo e histórico;
- conectar gobernanza, baseline, seguridad, roadmap, decisiones y referencias conceptuales;
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
- [[06-security/SECURITY_INDEX|Índice de seguridad]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]
- [[10-knowledge-index/CONCEPTUAL_FOUNDATIONS|Fundamentos conceptuales]]

Orden recomendado al iniciar una sesión ordinaria:

1. contexto de sesión;
2. referencia de baseline;
3. decisiones pendientes y roadmap cuando apliquen;
4. documento especializado del Vault;
5. verificación directa del repositorio oficial cuando se requiera autoridad o evidencia primaria.

Para una revisión orientada a definir la **próxima implementación**, el conjunto
de entrada debe ampliar explícitamente la navegación hacia:

```text
06-security/SECURITY_INDEX.md
10-knowledge-index/CONCEPTUAL_FOUNDATIONS.md
```

y verificar en `Aranwill/jarvis/main`:

```text
SECURITY.md
docs/project/concepts/MALAK_RESEARCH_HORIZON_MAP.md
docs/project/concepts/README.md
docs/project/concepts/** aplicables
documents/projects/jarvis/ideas.md
roadmap / baseline / decisiones / protocolo de construcción aplicables
```

Regla:

```text
security requirement != implemented capability
research gap != implementation authorization
```

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

## 4. Seguridad

- [[06-security/SECURITY_INDEX|Índice de seguridad]]

Fuente oficial de política:

```text
Aranwill/jarvis/SECURITY.md
```

La política activa de seguridad debe diferenciarse de conceptos futuros y de
mecanismos todavía no implementados. El índice derivado de seguridad facilita
navegación hacia Zero Trust, Security Control Plane, Secure Context, trust
boundaries, poisoning, supply-chain trust, delegation, compromise containment,
deception, forensics, disclosure y Resource Governance sin convertir esas
referencias en capacidades existentes.

---

## 5. Referencia de baseline

- [[02-current-baseline/CURRENT_BASELINE|Malāk Current Baseline]]

El índice no mantiene manualmente HEAD, último sprint cerrado, suite vigente,
estado de validación ni autorización del siguiente sprint.

Cuando esos datos deban representarse en el Vault, pertenecen a
`MALAK_OPERATIONAL_STATE`.

Los cierres y resultados concretos de sprints anteriores permanecen accesibles
mediante sus fichas, documentos de cierre, auditorías y registros históricos.

## 6. Roadmap

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
## 7. Registro de decisiones

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

## 8. Plantillas operativas

- [[templates/SESSION_CLOSE_TEMPLATE|Plantilla de cierre de sesión]]
- [[templates/SPRINT_CLOSE_TEMPLATE|Plantilla de cierre de sprint]]

Las plantillas deben copiarse antes de utilizarlas.

No deben completarse directamente sobre el archivo original.

---

## 9. Arquitectura y referencias conceptuales

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
- Governed Ephemeral Agent Execution, Evidence and Candidate Evaluation Reference;
- Malāk Research Horizon Map.

El Research Horizon conserva clasificaciones `ALIGNED`, `REINFORCE_EXISTING`,
`GAP_CANDIDATE`, `WATCH`, `IRRELEVANT` y `CONFLICTS_WITH_VISION` para evitar
olvidar investigación ya realizada sin convertirla en roadmap o autorización.

Estas referencias son derivadas y no normativas. Su presencia en el Vault no
autoriza implementación, no modifica el baseline y no autoriza ningún sprint.

---

## 10. Sprints

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

---

## 11. Diseños aprobados todavía no implementados

### Episodic Memory Admission Boundary Foundation — G1

Fuente oficial:

```text
Aranwill/jarvis/docs/project/sprints/proposals/EPISODIC-MEMORY-ADMISSION-G0-G1-DESIGN.md
```

Estado derivado:

```text
G0: PASS
G1 design: aprobado por el Owner e integrado en la fuente oficial
Implementación productiva: no autorizada
Memory persistente: no implementada
G2: requiere autorización humana separada
Sprint 7.12: no autorizado por este diseño
RDD Stage 2: no autorizado por este diseño
```

Separaciones obligatorias preservadas por G1:

```text
Conversation History != Memory != Knowledge
candidate payload != candidate control metadata
admission decision != persistence authorization != storage
HOLD != retention authorization
ELIGIBLE != storage authorization
```

La ausencia de provenance, clasificación o entradas de política requeridas debe
resolver fail-closed (`HOLD` o `REJECT`), nunca `ELIGIBLE` por defecto.

Este design record debe consultarse cuando una revisión continúe la línea de
Memory episódica o evalúe una implementación dependiente de su frontera de
admisión. Su presencia en el índice no cambia el baseline ni concede autoridad
para persistir, recuperar o promover Memory automáticamente.

### Episodic Memory Admission Boundary Foundation — G2 (registro pre-G3)

Fuente oficial:

~~~text
Aranwill/jarvis/docs/project/sprints/proposals/EPISODIC-MEMORY-ADMISSION-G2-IMPLEMENTATION-CANDIDATE-SPEC.md
~~~

Estado derivado:

~~~text
G0: PASS
G1 design: aprobado e integrado
G2 Implementation Candidate Specification: aprobada e integrada
Implementación productiva: no autorizada
Memory persistente: no implementada
Sprint 7.12: no autorizado
RDD Stage 2: no autorizado
~~~

G2 identifica como punto futuro de correlación el retorno exitoso de
`ConversationService.generate()` dentro de `ConversationCapability`, donde
`Request` y `ConversationResponse` pueden coexistir sin modificar
`ConversationRequest`, sin introducir Memory en el Kernel y sin convertir a
Conversation en propietaria de Memory.

La especificación preserva explícitamente:

~~~text
candidate payload != candidate control metadata

source authority
!= confidence
!= source security status
!= temporal validity
!= sensitivity

REJECT | HOLD | ELIGIBLE
~~~

y mantiene:

~~~text
ELIGIBLE != persistence authorization
HOLD != retention authorization
admission != storage
~~~

El candidate especificado por G2 sigue siendo una propuesta de implementación
futura. Su presencia en este índice no autoriza código productivo, persistencia,
retrieval, Knowledge, un nuevo sprint ni RDD Stage 2.

### Episodic Memory Admission Boundary Foundation — G3

Fuentes oficiales:

~~~text
Aranwill/jarvis/src/malak/memory/__init__.py
Aranwill/jarvis/src/malak/memory/episodic_admission.py
Aranwill/jarvis/tests/test_episodic_memory_admission.py
~~~

Estado derivado:

~~~text
G3: implementado e integrado
unidad separada posterior a Sprint 7.11
Sprint 7.12: no autorizado
Memory persistente: no implementada
retrieval: no implementado
RDD Stage 2: no autorizado
~~~

G3 materializa `EpisodicMemoryCandidate`, metadata de control separada,
señales de evaluación y `EpisodicAdmissionDecision` mediante una policy
determinista `episodic-admission/v1`.

Resultados:

~~~text
REJECT | HOLD | ELIGIBLE
~~~

La implementación preserva:

~~~text
Candidate != Decision
payload != control metadata
ELIGIBLE != persistence authorization
HOLD != retention authorization
admission != storage
~~~

Este registro confirma existencia de la frontera de admisión, no Memory
persistente ni una autorización para almacenamiento, retrieval, Knowledge,
Sprint 7.12 o una unidad posterior.
