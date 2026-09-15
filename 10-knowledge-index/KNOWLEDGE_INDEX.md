---
id: MALAK-KNOWLEDGE-INDEX
title: Malāk Knowledge Index
type: knowledge-index
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.1
created: 2026-07-20
last_reviewed: 2026-09-12
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

- **Run ID:** `20260915T230550157682Z_75c04178_80e2de35`
- **HEAD oficial observado:** `75c04178049a4cd2d90680b27ae0921b39b4215e`
- **Commit previamente observado:** `46dde74592ffc336104f4309cdd8a966b518fc53`
- **Generado:** `2026-09-15T23:05:50.157682+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.11.md`
- **Título declarado:** Sprint 7.11 — Reproducible Validation Pipeline Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible

### Commits oficiales observados

- 75c04178049a4cd2d90680b27ae0921b39b4215e	Merge pull request #139 from Aranwill/feat/g2a-bound-authorization-enforcement-20260915
- afdb2b792d9bb56f6e63f6a1cc548cb5444d0d36	test(security): preserve audit positional field compatibility
- 568e6aa9b920fc27362e54c9142d22b2c7b54eba	refactor(security): preserve audit positional compatibility
- f5bbff29a031da2ea4bbb86ea44f11faa931568a	test(security): cover requested and actual audit bindings
- bde8e059d6cf62a7a60c0b8f96bb4c8383728902	test(security): cover authorization operation binding contracts
- 9f60a1c88ba36cdf6dc64aa35e3ffe3b1c3397bb	test(security): cover exact PEP operation binding enforcement
- 5d2188eef5b3a3de56fea18252ff19ffccbd9756	test(security): cover bound PDP authorization semantics
- 5f74d7f5a26da93db3e18628cd4c69bd0b4c8e37	feat(security): enforce exact protected operation binding
- b9f1ae941637d921e25d89b0d1c8623430dec2a1	feat(security): preserve exact binding through policy decisions
- 8512b407338cec9208219f6ce59289cbe3852535	feat(security): export authorization operation binding
- cc131c9941129c7969bb01edb91beba8a5459e7a	feat(security): audit exact authorization operation binding
- 5ed57fef444745b4e36c72cd7fbae02dfa0eadb6	feat(security): add exact authorization operation binding
- c0387e785bab8ec5fcffe2d80a01efc95f5e7d61	test(security): define RED audit binding expectations
- 3c957f821d52e525e8aed4ae27dd836d5b3cd2ea	Merge pull request #138 from Aranwill/docs/adr-002-bound-authorization-amendment-20260915
- 9a385cfdb2663bbf40a12e43ec9c21c61624b942	docs(adr): harden ADR-002 with bound authorization enforcement
- 225c19ea7b5bd207bbabbd58e56294072037b940	Merge pull request #137 from Aranwill/docs/adr-002-bound-authorization-hardening-20260915
- e30d03c139607245f27bd354994918e3f67ae5bc	docs(security): specify ADR-002 bound authorization hardening

### Evidencia que originó esta proyección

- `baseline-source-change` por `docs/project/sprints/proposals/MALAK-ADR-002-BOUND-AUTHORIZATION-ENFORCEMENT-HARDENING-G2.md`
- `governance-change` por `docs/architecture/adr/ADR-002-policy-enforcement-boundary.md`
<!-- MALAK_VAULT_SYNC:END -->

<!-- MALAK_OPERATIONAL_STATE:START -->
## Estado operativo derivado

> Estado machine-owned derivado de la fuente oficial.
> No concede autoridad ni reemplaza decisiones humanas.

- **HEAD oficial:** `75c04178049a4cd2d90680b27ae0921b39b4215e`
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

Estado cognitivo relevante para navegación:

```text
G2A Protected Finalization Foundation: INTEGRATED / ISOLATED
Assurance Signal Authority G0/G1: INTEGRATED DESIGN
Signal Boundary G2: INTEGRATED / ISOLATED
Conversation G2B: BLOCKED / NOT AUTHORIZED
Sprint 7.12: NOT AUTHORIZED
RDD Stage 2: NOT AUTHORIZED
```

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
- la separación entre métricas, eventos operativos y auditoría;
- la cadena episódica aislada Admission → Provenance → Producer Authorization → Governed Projection → Consumption;
- G2A Protected Finalization como foundation aislada, sin wiring conversacional;
- G2 Assurance Signal Authority & Projection como foundation aislada, sin producers runtime ni wiring conversacional.

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

## 11. Registro de fronteras episódicas y cognitive assurance

### Episodic Memory Admission Boundary Foundation — G1

Fuente oficial:

```text
Aranwill/jarvis/docs/project/sprints/proposals/EPISODIC-MEMORY-ADMISSION-G0-G1-DESIGN.md
```

Estado histórico derivado:

```text
G0: PASS
G1 design: aprobado por el Owner e integrado en la fuente oficial
G1 != implementación productiva
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

### Episodic Memory Admission Boundary Foundation — G2 (registro pre-G3)

Fuente oficial:

~~~text
Aranwill/jarvis/docs/project/sprints/proposals/EPISODIC-MEMORY-ADMISSION-G2-IMPLEMENTATION-CANDIDATE-SPEC.md
~~~

Este registro conserva la candidate specification previa a la integración de G3.
No debe interpretarse como estado operativo actual ni como autorización de
persistencia, retrieval, Knowledge, Sprint 7.12 o RDD Stage 2.

### Episodic Memory Admission Boundary — G3

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

### Assessment Provenance Boundary

Fuente oficial:

```text
Aranwill/jarvis/src/malak/memory/assessment_provenance.py
```

Estado:

```text
implementado e integrado
resultado: VALID | HOLD | INVALID
```

Provenance liga un assessment a su candidato, kind y producer role sin
convertirse en identidad, verdad, permiso o autoridad.

### Assessment Producer Authorization Boundary

Fuente oficial:

```text
Aranwill/jarvis/src/malak/memory/assessment_producer_authorization.py
```

Estado:

```text
implementado e integrado
resultado: AUTHORIZED | HOLD | DENIED
```

Producer authorization es una frontera propia y no debe confundirse con
provenance, Admission ni autorización de persistencia.

### Governed Input Projection Boundary

Fuente oficial:

```text
Aranwill/jarvis/src/malak/memory/governed_input_projection.py
```

Estado:

```text
implementado e integrado
resultado: READY | HOLD | DENIED
```

La projection reconstruye inputs trust-sensitive únicamente desde assessments
candidate-bound con provenance y autorización verificadas. No acepta campos
sensibles por mera presencia y no aplica last-write-wins.

### Governed Projection Consumption Boundary

Fuente oficial:

```text
Aranwill/jarvis/src/malak/memory/governed_projection_consumption.py
```

Estado:

```text
implementado e integrado
resultado: BLOCKED | EVALUATED
```

El consumer valida binding y policy-version, construye una vista efímera del
contexto gobernado y llama exactamente una vez a Episodic Admission cuando la
projection es consumible.

Regla:

```text
Projection READY != Admission ELIGIBLE
```

Toda la cadena episódica permanece sin Conversation/runtime wiring,
persistencia, retrieval o Knowledge.

### G2A — Protected Finalization Foundation

Fuentes oficiales:

```text
Aranwill/jarvis/src/malak/core/protected_finalization.py
Aranwill/jarvis/tests/test_protected_finalization.py
Aranwill/jarvis/docs/project/sprints/proposals/MALAK-PROGRESSIVE-COGNITIVE-ASSURANCE-RUNTIME-G2A-IMPLEMENTATION-CANDIDATE-SPEC.md
```

Estado:

```text
implementada e integrada como foundation determinista aislada
ACCEPT | ABSTAIN | BLOCK
Conversation wiring: no implementado
```

G2A separa generación y finalización protegida, pero todavía no participa del
runtime conversacional real.

### Assurance Signal Authority Boundary — G0/G1

Fuente oficial:

```text
Aranwill/jarvis/docs/project/sprints/proposals/MALAK-ASSURANCE-SIGNAL-AUTHORITY-G0-G1-DESIGN.md
```

G0/G1 definió la separación entre observations, producer authorization,
projection y finalization decision.

### G2 — Assurance Signal Authority & Projection Foundation

Fuentes oficiales:

```text
Aranwill/jarvis/src/malak/core/assurance_signal_projection.py
Aranwill/jarvis/tests/test_assurance_signal_projection.py
Aranwill/jarvis/docs/project/sprints/proposals/MALAK-ASSURANCE-SIGNAL-BOUNDARY-G2-IMPLEMENTATION-CANDIDATE-SPEC.md
```

Estado:

```text
Signal Boundary G2: INTEGRATED / ISOLATED
Conversation G2B: BLOCKED / NOT AUTHORIZED
Sprint 7.12: NOT AUTHORIZED
RDD Stage 2: NOT AUTHORIZED
```

G2 valida authority/projection de cinco assurance signals y solo produce un
`ProtectedFinalizationInput` cuando el set es `READY`.

El baseline continúa sin producers runtime legítimos para:

```text
applicability
evidence_required
support_sufficient
contradiction_unresolved
policy_violation
```

Separaciones preservadas:

```text
Evidence != Authority
producer permission != signal truth
Security authorization != Cognitive policy disposition
G2 READY != G2A ACCEPT
G2 DENIED != G2A BLOCK
G2 integrated != G2B authorized
```

La foundation es same-process y no afirma identidad criptográfica, replay
protection ni provenance criptográfica del `AuthorizationDecision`.

Este índice registra existencia y relaciones; no concede autorización para la
siguiente unidad.
