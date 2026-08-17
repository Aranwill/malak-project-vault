---

id: MALAK-SESSION-CONTEXT
title: Malāk Session Context
type: session-context
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.2
created: 2026-07-20
last_reviewed: 2026-08-16
source_repository: Aranwill/jarvis
source_branch: main
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
---

# Malāk Session Context

<!-- MALAK_VAULT_SYNC:START -->
## Proyección automática de sincronización

> [!warning] Estado derivado pendiente de revisión
> Este bloque fue generado de forma determinista a partir de
> `Aranwill/jarvis/main`. No aprueba decisiones, no cierra
> sprints y no reemplaza la revisión humana del documento.

- **Run ID:** `20260817T033713631080Z_67590ba2_b4a4695b`
- **HEAD oficial observado:** `67590ba2ffe7c4938122a5ad2771266c45a21057`
- **Commit previamente observado:** `6c179730e6d4220bbba22a8282f978a7a1aa9155`
- **Generado:** `2026-08-17T03:37:13.631080+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.8.md`
- **Título declarado:** Sprint 7.8 — Cognitive Conversation Execution Path Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** `6c179730e6d4220bbba22a8282f978a7a1aa9155`

### Commits oficiales observados

- 67590ba2ffe7c4938122a5ad2771266c45a21057	Merge pull request #46 from Aranwill/fix/sprint-7.8-closure-metadata
- 87e1fda99ebb97983a6800768a48693020a0cccf	docs(project): reconcile Sprint 7.8 closure status
- bd9e3fe7f6320a8e040b959d7c6c8f5f4372d6d6	Merge pull request #45 from Aranwill/sprint/7.8-cognitive-conversation-execution-path
- 85dfef4f4675013ec6ef812be135299d2042adf6	docs(project): close Sprint 7.8 cognitive conversation path
- 434dc84e439d8ef032f3634a49e3711afffbef7d	docs(project): complete Sprint 7.8 real runtime validation
- 5651246e761ae00f7373bd677350442158da1279	test(conversation): validate cognitive execution path
- f6a6569885212dbf081e9158826a20092d50ba3a	feat(cli): route conversation through kernel
- 8423275d80c08307e08405420a00526cb9c4cd2e	feat(app): compose conversation kernel
- 054b76dc7f996e8b8ba1489560284a5f23e38544	feat(planner): add deterministic capability routing
- 8d35e4582ed6d11fae346d0444372781374993da	feat(conversation): add conversation capability adapter
- 65b2efaa79fb6ff959c1560563cdf7130269c503	feat(kernel): add external composition seam
- 7ad333ca9e835247dfceb5d59fade63cc94ef775	docs(project): activate Sprint 7.8 cognitive conversation path

### Evidencia que originó esta proyección

- `architecture-change` por `src/malak/app/cli.py`
- `architecture-change` por `src/malak/app/composition.py`
- `architecture-change` por `src/malak/capabilities/conversation.py`
- `architecture-change` por `src/malak/kernel/kernel.py`
- `architecture-change` por `src/malak/services/planner.py`
- `baseline-source-change` por `docs/project/sprints/SPRINT-7.8.md`
- `test-change` por `tests/test_app_composition.py`
- `test-change` por `tests/test_cli.py`
- `test-change` por `tests/test_conversation_capability.py`
- `test-change` por `tests/test_conversation_execution_path.py`
- `test-change` por `tests/test_kernel.py`
- `test-change` por `tests/test_planner.py`
<!-- MALAK_VAULT_SYNC:END -->

<!-- MALAK_OPERATIONAL_STATE:START -->
## Estado operativo derivado

> Estado machine-owned derivado de la fuente oficial.
> No concede autoridad ni reemplaza decisiones humanas.

- **HEAD oficial:** `67590ba2ffe7c4938122a5ad2771266c45a21057`
- **Ficha de sprint vigente:** `docs/project/sprints/SPRINT-7.8.md`
- **Titulo declarado:** Sprint 7.8 — Cognitive Conversation Execution Path Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** `6c179730e6d4220bbba22a8282f978a7a1aa9155`
<!-- MALAK_OPERATIONAL_STATE:END -->

## 1. Instrucción de uso

Este archivo es el punto de entrada para iniciar una sesión de trabajo sobre Malāk.

Debe utilizarse para:

* recuperar rápidamente el contexto vigente;
* evitar depender de conversaciones anteriores;
* distinguir baseline, roadmap y propuestas;
* mantener alineación con la arquitectura y la gobernanza;
* reducir contradicciones y reconstrucciones incorrectas.

Este archivo no reemplaza las fuentes oficiales del repositorio.

El contexto humano conserva arquitectura, gobernanza, restricciones, decisiones,
objetivos de sesión y registros históricos. No mantiene una segunda copia manual
del estado operativo mutable.

Cuando deban representarse en el Project Vault, HEAD, sprint estructurado,
conteos de tests, working tree, baseline mutable y demás datos deterministas de
estado pertenecen exclusivamente al bloque machine-managed
`MALAK_OPERATIONAL_STATE`.

Ante cualquier contradicción, prevalecen:

1. Constitución Cognitiva;
2. Constitución de Gobernanza;
3. Blueprint;
4. especificaciones aprobadas;
5. ADR aceptados;
6. contratos públicos;
7. baseline y documentación oficial vigente;
8. evidencia directa del repositorio.

---

## 2. Identidad del proyecto

**Nombre:** Malāk
**Nombre histórico:** Jarvis
**Repositorio:** `Aranwill/jarvis`
**Ruta local:** `D:\Ollama\jarvis`
**Rama oficial y permanente:** `main`
**Versión nominal:** `v0.6.0-alpha`
**Estado de desarrollo:** Foundation Implementation

Malāk es una plataforma cognitiva personal ejecutada localmente, diseñada para ser:

* modular;
* gobernable;
* extensible;
* auditable;
* agnóstica respecto de modelos y proveedores LLM;
* controlada por el propietario;
* evolucionada mediante sprints cortos y cambios reversibles.

---

## 3. Referencia operativa del contexto

Este archivo no mantiene manualmente el baseline operativo vigente de Malāk.

El HEAD oficial, el sprint estructurado representado, los resultados vigentes de
tests y validaciones, y cualquier otro dato operativo derivable de forma
determinista pertenecen a `MALAK_OPERATIONAL_STATE`.

La autorización del siguiente sprint no se deduce del estado operativo ni del
cierre de un sprint anterior. Continúa siendo una decisión humana sujeta a
gobernanza.

### Registro histórico — cierre del Sprint 7.5

La siguiente evidencia se conserva únicamente como registro histórico del cierre
del Sprint 7.5 y no representa el estado operativo actual:

```text
Sprint 7.5 — Security Control Plane Foundation
Incrementos 1 a 6: completados
183 security-specific passed
304 total passed
compileall: PASS
git diff --check: PASS
```

La revisión integral del Incremento 6 no detectó defectos bloqueantes ni requirió
cambios funcionales. Kernel, Planner, CLI, runtimes y Capability Registry
permanecieron intactos.

El estado operativo posterior debe obtenerse de la proyección machine-managed y
de la evidencia oficial correspondiente.
---

## 4. Estado arquitectónico representado

Sprint 7.8 integró la conversación dentro del pipeline
Kernel–Planner–Capability mediante una Capability dedicada y composición
externa.

La ruta cognitiva conversacional representada es:

```text
CLI
        ↓
Request
        ↓
Kernel.receive()
        ↓
Planner
        ↓
CapabilityRegistry
        ↓
ConversationCapability
        ↓
ConversationService
        ↓
ConversationProviderRegistry
        ↓
RuntimeConversationProvider
        ↓
LLMRuntime
```

### 4.1 Pipeline Kernel–Planner–Capability

Componentes principales:

* Kernel MVP;
* Planner MVP;
* Capability Registry;
* EchoCapability;
* `ConversationCapability`;
* `ConversationCapability`.

El Kernel continúa siendo la frontera cognitiva de entrada y permanece
desacoplado de servicios, providers, runtimes y modelos concretos.

### 4.2 Ruta conversacional integrada

`ConversationCapability` adapta el contrato genérico de Capability hacia
`ConversationService`.

La integración no introduce una dependencia directa desde el Kernel hacia
`ConversationService`.

La composición concreta se mantiene en la frontera de aplicación:

```text
LLMRuntime
        ↓
RuntimeConversationProvider
        ↓
ConversationProviderRegistry
        ↓
ConversationService
        ↓
ConversationCapability
        ↓
CapabilityRegistry
        ↓
Planner
        ↓
Kernel
```

La CLI enruta las solicitudes conversacionales a través de `Kernel.receive()`.

Sprint 7.8 validó esta ruta con pruebas unitarias, integración end-to-end y una
ejecución real mediante `OllamaRuntime`.

La separación arquitectónica relevante que continúa vigente es la separación
de responsabilidades: el Kernel gobierna el despacho cognitivo, mientras que
la infraestructura conversacional y de runtime permanece compuesta
externamente.

---

## 5. Componentes implementados

Componentes documentados en el alcance representado:

* Kernel MVP;
* Planner MVP;
* Capability Registry;
* EchoCapability;
* `ConversationRequest`;
* `ConversationResponse`;
* `LLMRuntime`;
* `MockLLMRuntime`;
* `OllamaRuntime`;
* `ConversationProvider`;
* `RuntimeConversationProvider`;
* `ConversationProviderNotFoundError`;
* `ConversationProviderRegistry`;
* `ConversationService`;
* CLI técnica;
* configuración externa del runtime;
* `RuntimeMetricSample`;
* `RuntimeMetricSink`;
* `InMemoryRuntimeMetricStore`;
* `JsonlRuntimeMetricStore`;
* `OperationalEvent`;
* `OperationalEventSink`;
* `InMemoryOperationalEventStore`;
* `JsonlOperationalEventStore`;
* `PermissionScope`;
* `SecurityContext`;
* `AuthorizationRequest`;
* `AuthorizationDecision`;
* `PolicyDecisionPoint`;
* `StaticPolicyDecisionPoint`;
* `PolicyRule`;
* `PolicyEffect`;
* `HumanConfirmationEvidence`;
* `HumanConfirmationVerifier`;
* `PolicyEnforcementPoint`;
* `StrictPolicyEnforcementPoint`;
* `ProtectedOperation`;
* `AuthorizationDeniedError`;
* `AuthorizationEnforcementError`;
* correlación conversacional mediante `request_id` generado
  exclusivamente en la CLI;
* perfilado inicial de métricas;
* AKS Engineering Knowledge Foundation;
* Development Framework.

La integración real con Ollama fue validada con:

```text
qwen3.5:9b
```

---

## 6. Principios no negociables

Toda propuesta debe respetar:

* Kernel First;
* Capability First;
* Runtime Independence;
* Human in Control;
* Zero Trust interno;
* Defense in Depth;
* denegación por defecto para capacidades sensibles;
* separación de responsabilidades;
* configuración externa al Kernel;
* trazabilidad;
* reversibilidad;
* cambios pequeños;
* pruebas deterministas;
* documentación sincronizada;
* validación antes de incorporar al baseline.

Principio de ejecución:

> Primero se diseña la arquitectura correcta; después se implementa cada capacidad incrementalmente sin comprometer los principios del sistema.

---

## 7. Cuatro preguntas obligatorias

Antes de aprobar cualquier cambio:

1. ¿Respeta el Blueprint?
2. ¿Respeta la Constitución Cognitiva?
3. ¿Respeta la Gobernanza?
4. ¿Simplifica o mantiene simple el Kernel?

Si alguna respuesta es negativa o incierta, el cambio no debe implementarse sin revisión formal.

---

## 8. Restricciones activas

### Kernel

El Kernel no debe:

* depender de Ollama;
* depender de proveedores concretos;
* depender de modelos concretos;
* consumir Internet;
* ejecutar herramientas externas;
* almacenar métricas;
* administrar configuración del runtime;
* aplicar recomendaciones automáticamente;
* absorber autorización;
* absorber auditoría;
* incorporar lógica de negocio;
* convertirse en un contenedor de responsabilidades.

### Capabilities

No deben crearse Capabilities únicamente para:

* demostrar routing;
* aumentar cobertura;
* ejercitar infraestructura;
* completar una secuencia;
* incorporar ejemplos sin utilidad funcional real.

Toda Capability debe aportar una función necesaria, permanente y justificable.

### Tooling

Ruff no forma parte del alcance implementado documentado aquí.

Debe evaluarse dentro de una futura Development Tooling Foundation junto con:

* mypy;
* `pyproject.toml`;
* dependencias de desarrollo;
* integración local;
* integración CI;
* reglas reproducibles.

No debe incorporarse de forma aislada o improvisada.

### Seguridad

Antes de agentes, navegación, herramientas externas, automatización, mensajería o memoria sensible deben aprobarse e implementarse los fundamentos de seguridad correspondientes.

---

## 9. Fuera de alcance documentado

No forman parte del alcance implementado documentado:

* memoria conversacional;
* historial persistente;
* agentes;
* herramientas externas;
* navegación;
* GraphRAG;
* interfaz gráfica;
* automatización del sistema operativo;
* ejecución autónoma;
* autoajuste;
* modificación automática de modelo;
* modificación automática de timeout;
* modificación automática de `keep_alive`;
* aplicación automática de recomendaciones;
* Secure Context Manager implementado;
* RAG externo;
* auditor externo.

---

## 10. Relación con el estado de sprint

El contexto de sesión no mantiene manualmente cuál es el sprint vigente, el
último sprint cerrado ni el conteo de validaciones actual.

Cuando esos datos deban representarse en el Vault, pertenecen a
`MALAK_OPERATIONAL_STATE`.

Como contexto histórico, Sprint 7.5 quedó cerrado después de completar seis
incrementos. Los contratos fundamentales de autorización, PDP, PEP y auditoría
de autorización fueron integrados y reconciliados mediante las PR documentadas
en los artefactos oficiales del proyecto.

Ese cierre no autoriza automáticamente un sprint posterior.
---

## 11. Decisiones abiertas prioritarias

### Alta prioridad

Las prioridades deben leerse desde el registro de decisiones vigente y no inferirse desde un sprint histórico.

### Prioridad media

* política de sincronización con Obsidian;
* esquema de metadatos del Vault.

El cierre de Sprint 7.5 permanece como hecho histórico. La existencia o ausencia de un sprint posterior autorizado debe resolverse mediante gobernanza y la evidencia oficial correspondiente.

### Diferidas

* Session Context Generator;
* tecnología del RAG externo;
* alcance del auditor;
* Ruff y mypy.

Los detalles completos se encuentran en:

```text
05-decisions\PENDING_DECISIONS.md
```

---

## 12. Project Context & Knowledge Governance Foundation

**Estado conceptual:**

```text
aprobada
```

**Estado de ejecución:**

```text
fundación documental inicial completada
```

**Ubicación:**

```text
D:\Ollama\malak-project-vault
```

Secuencia aprobada:

1. Project Context Foundation;
2. Obsidian Knowledge Foundation;
3. Session Context Generator;
4. External Project RAG;
5. Architecture & Security Auditor Foundation.

Estado documentado de la secuencia:

1. **Project Context Foundation:** completada en su alcance documental inicial;
2. **Obsidian Knowledge Foundation:** navegación base, índices, metadatos y primer mapa arquitectónico completados;
3. **Session Context Generator:** pendiente y no aprobado para implementación;
4. **External Project RAG:** pendiente y no aprobado para implementación;
5. **Architecture & Security Auditor Foundation:** pendiente y no aprobado para implementación.

### Vault Synchronization Agent Foundation

Estado documentado:

```text
Incorporación documental: completada mediante las PR #2, #3 y #4 del Vault
Fase 1: completed
Gates 0 a 9: cerrados
Operacionalización read-only: completed
Repositorio independiente del agente: Aranwill/malak-vault-sync-agent
PR de operacionalización del agente: #1 integrada
PR de corrección del flujo controlado: #3 integrada
PR de corrección del recovery histórico no-op: #9 integrada
Modo operativo elegido: manual-on-demand
Scheduler activo: no
Autoridad operativa: none
Fase 2 y posteriores: no aprobadas
```

La fundación fue integrada documentalmente en `Aranwill/malak-project-vault/main` mediante:

```text
PR #2
Merge commit: bcefa948b250830139233376088d1e65bd159143

PR #3
Merge commit: 918997a61e9a7b68c353c2eb5697ea21ede7e91f

PR #4
Merge commit: 52976e771ad8307badbc0ac37a78a771e6df51fc
```

Workspace externo verificado:

```text
D:\Ollama\malak-vault-sync-agent
```

Ownership del estado operativo del agente:

Este contexto no mantiene manualmente HEAD, working tree, suite, scheduler,
cursores, estado persistente, última propuesta reconciliada ni otros datos
operativos mutables del Vault Synchronization Agent.

Cuando deban proyectarse en el Project Vault, pertenecen a
`MALAK_OPERATIONAL_STATE`.

Los hashes, suites y resultados concretos de validaciones anteriores se
conservan únicamente en registros históricos y artefactos de auditoría.

La ejecución programada fue utilizada únicamente para validar la operacionalización en Windows. La tarea programada fue eliminada posteriormente por decisión humana.

El agente se ejecutará manualmente después de cada sesión aprobada de Malāk, una vez que los cambios legítimos hayan sido publicados o fusionados en `Aranwill/jarvis/main`.

Flujo operacional documentado:

```text
Avance aprobado de Malāk
→ merge o push a main
→ ejecución manual de run-once
→ revisión humana de evidencia e informe
→ rama y PR draft de actualización del Vault
→ reconciliación y aprobación humanas
→ merge exclusivamente humano
```

El cierre histórico de la Fase 1 permanece válido. La extensión `controlled-proposal` fue implementada y certificada posteriormente dentro del alcance correctivo aprobado, sin inferir aprobación de una Fase 2 ni conceder autoridad operativa al agente.

El siguiente registro conserva una validación operacional end-to-end histórica de `controlled-proposal`:

```text
Malāk base: 223b0c3794f4a857ff3ce5c3556a59445b995831
Malāk HEAD: c65bff257f877460c153583bfcd9819224ca0f5c
Vault base: 30336572ad098af9cc35b054d16950a97cf44ce2
Vault final: e9165357160386fea59706d9af4cd7504f539219
Run ID: 20260815T010848675956Z_c65bff25_30336572
Vault PR: #31
Resultado: pass

Mapping:
docs/project/concepts/
→ 10-knowledge-index/CONCEPTUAL_FOUNDATIONS.md
→ 10-knowledge-index/KNOWLEDGE_INDEX.md

Commit documental:
c21e92b19c5a7705c289bb9f2d0d60eb15a5b3dc

Commit de auditoría / PR HEAD:
7adafab01b614603ee248e8374887677e1a7981e

controlled-proposal E2E: PASS
separación content/audit: PASS
fail-closed ante expected-commit incorrecto: PASS
reconciliación humana: PASS
accept-proposal: PASS
steady state posterior: PASS
pending_proposal_*: null

```


La iniciativa:

* permanece fuera del Kernel, del runtime y del Security Control Plane;
* no forma parte del roadmap operativo de `Aranwill/jarvis`;
* mantiene `Aranwill/jarvis/main` en modo de solo lectura;
* opera desde un workspace externo;
* opera en modos `dry-run` y `controlled-proposal`;
* no utiliza LLM;
* no modifica archivos de `Aranwill/jarvis`;
* en modo controlado modifica únicamente una rama aislada del Vault;
* puede crear commits, publicar la rama y abrir una PR draft;
* mantiene snapshots históricos inmutables;
* no puede aprobar, habilitar auto-merge ni mergear PR;
* reserva toda ampliación de alcance al propietario humano;
* conserva `operational_authority: none`.

Las decisiones correspondientes permanecen resueltas y cerradas en:

```text
DEC-PEND-013 — Aprobación y cierre fundacional de Fase 1
DEC-RES-008 — Modo operativo manual-on-demand
DEC-RES-009 — Extensión gobernada controlled-proposal
```

`DEC-PEND-013` conserva la decisión fundacional de Fase 1,
`DEC-RES-008` conserva el modo operativo y `DEC-RES-009` autoriza la
extensión acotada; ninguna sustituye a las demás.

El cierre técnico se documenta en:

```text
07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE.md
```

El cierre de la operacionalización read-only se documenta en:

```text
07-audits/vault-synchronization/2026-07-24_VAULT_SYNC_OPERATIONALIZATION_CLOSURE.md
```

El cierre técnico y operativo del Incremento Correctivo Integral 5 se
documenta en el repositorio del agente:

```text
docs/INCREMENT_5_OPERATIONAL_CLOSURE.md
versión: 0.3.0
PR #8
merge commit: 5afd03e1697e4820b8b62ff3db23109fdfde8bcb
suite completa: 260 passed
```

La certificación incluyó GitHub Actions en Ubuntu y Windows, validación
nativa Windows, GitHub CLI real, recovery negativo y positivo,
normalización CRLF y cleanup gobernado.

El Vault:

* permanece fuera del repositorio principal;
* no forma parte del Kernel;
* no forma parte del runtime;
* no reemplaza Git;
* no reemplaza documentos normativos;
* no puede modificar Malāk automáticamente;
* organiza información derivada y contexto operativo.

---

## 13. Relación operativa con el Project Vault

**Repositorio local:** `D:\Ollama\malak-project-vault`
**Repositorio remoto:** `Aranwill/malak-project-vault`
**Rama oficial:** `main`

El contexto de sesión no mantiene manualmente el HEAD actual del Vault, la PR de
sincronización más reciente, la rama de propuesta, el último Run ID ni el estado
de reconciliación.

Cuando estos datos deban representarse dentro del Project Vault, pertenecen a
`MALAK_OPERATIONAL_STATE`.

La gobernanza permanece estable: una propuesta generada por el Agent es evidencia
y no una decisión; la revisión, aprobación y merge permanecen bajo autoridad
humana.
### Registro histórico — sincronización gobernada cerrada mediante PR #13

Estado remoto verificado después de aquella sincronización:

```text
Vault main: 772991d4b1dfecd95d746398bbcd268f450bfe2c
PR #13: integrada
Merge commit PR #13: 772991d4b1dfecd95d746398bbcd268f450bfe2c
Malāk observado: d1c90bf0bf55a7076d68c1f4830e89e0d843661c
PR abiertas: ninguna
Rama de propuesta #13: eliminada después del merge
```

Evidencia histórica del Vault Synchronization Agent asociada a la PR #13:

```text
run_id: 20260726T214149097509Z_d1c90bf0_70ffa813
source previous: 83ceb96838df0770bb9309172a75e3dc79bff121
source current: d1c90bf0bf55a7076d68c1f4830e89e0d843661c
Vault base: 70ffa8137a698c81b2d3013ea01f8c92f8959478
changed files: 7
document candidates: 6
validation findings: 0
conclusion: pass
```

Informe auditable integrado:

```text
07-audits/vault-synchronization/2026-07-26_VAULT_SYNC_20260726T214149097509Z_d1c90bf0_70ffa813.md
```

Estado histórico de la sincronización:

```text
end-to-end completado;
reconciliación humana incorporada;
PR #13 integrada exclusivamente por decisión del propietario;
baseline derivado del Vault actualizado en main
```

El agente recuperó el rango pendiente después del `dry-run`, creó la
propuesta controlada y mantuvo Malāk intacto. El merge humano no concede
autoridad operativa ni habilita merge automático para ciclos futuros.

### Registro histórico anterior

Estado verificado durante el cierre de la operacionalización read-only:

* PR #2 mergeada;
* PR #3 mergeada;
* PR #4 mergeada;
* HEAD remoto verificado: `03032a7b2aaecb47c27c2e8e5bff3a2c04179bd2`;
* rama oficial: `main`;
* working tree limpio antes de iniciar la rama de cierre;
* rama documental utilizada en aquella etapa: `docs/vault-sync-operationalization-closure`;
* cambios organizados mediante commits pequeños y trazables;
* ningún cambio realizado sobre `Aranwill/jarvis`.

Estado documental del Vault:

* navegación principal consolidada mediante `HOME.md`;
* índices creados para gobernanza, arquitectura, sprints, seguridad, auditorías, snapshots y plantillas;
* `KNOWLEDGE_INDEX.md` actualizado con enlaces vigentes;
* esquema de metadatos futuros definido en `00-governance/METADATA_SCHEMA.md`;
* arquitectura reorganizada dentro de `01-architecture/`;
* primer mapa arquitectónico creado en `01-architecture/CURRENT_COMPONENTS_MAP.md`;
* diagrama Mermaid validado visualmente en Obsidian;
* grafo documental operativo y sin nodos huérfanos evidentes;
* Vault Synchronization Agent Foundation integrada documentalmente;
* cierre técnico de la Fase 1 documentado;
* operacionalización read-only integrada en `main` del repositorio independiente del agente;
* modo operativo manual bajo demanda aprobado por el propietario.

Estado posterior de la iniciativa:

```text
Arquitectura de Fase 1: accepted
Política de Fase 1: accepted
Modelo de amenazas de Fase 1: accepted
Fase 1: completed
Gates 0 a 9: cerrados
Autoridad operativa: none
Agente operativo: herramienta local determinista de propuesta controlada
Repositorio del agente: Aranwill/malak-vault-sync-agent
HEAD del agente: 0feed6eae3d3919ea4867891c12eda5eea81c511
Modo operativo: manual-on-demand
Modos: dry-run y controlled-proposal
Scheduler activo: no
Kernel afectado: no
Runtime afectado: no
Security Control Plane afectado: no
Fase 2 y posteriores: no aprobadas
```

El repositorio oficial de Malāk no fue modificado durante esta línea de trabajo.

Registro histórico del baseline documentado en aquella etapa:

* repositorio: `Aranwill/jarvis`;
* rama: `main`;
* commit: `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`;
* último sprint cerrado: Sprint 7.3 — Conversation Provider Boundary Stabilization;
* pull request integrado: PR #13;
* suite documentada: 74 pruebas aprobadas;
* próximo sprint aprobado: ninguno.

Continúan pendientes y sin aprobación automática:

* fases posteriores del Vault Synchronization Agent;
* Session Context Generator;
* RAG externo;
* auditor arquitectónico;
* auditor de seguridad;
* sincronización automática;
* integración operativa entre el Vault y Malāk.

El Vault permanece como una capa documental externa, derivada y sin autoridad operativa.

---

## 14. Iniciativas futuras y contexto histórico

Registro histórico de una línea cerrada:

* Security Control Plane Foundation — Sprint 7.5 cerrado.

Sin sprint aprobado:

* Resource Governance Foundation;
* Model Governance Foundation;
* Controlled Engineering Improvement Loop Foundation;
* Development Tooling Foundation;
* Evidence Acquisition Foundation;
* Secure Context Manager;
* Architecture & Security Auditor Foundation;
* Vault Synchronization Agent Foundation, con Fase 1 completada y fases posteriores no aprobadas;
* AI Preservation System;
* Model Archive;
* Simulation & Sandbox;
* SIAL;
* Admin Identity & Access Control Layer.

La aceptación conceptual no constituye autorización de implementación.

---

## 15. Verificación obligatoria antes de trabajar

Ejecutar desde el repositorio local:

```powershell
cd D:\Ollama\jarvis

git branch --show-current
git status
git fetch --prune
git log -1 --oneline

python -m pytest -q
python -m compileall src tests
git diff --check
```

Condiciones esperadas:

* rama `main`;
* working tree limpio;
* remoto sincronizado;
* suite en verde;
* compilación sin errores;
* diff sin errores.

Registrar resultados en el contexto temporal de la sesión.

No reemplazar evidencia directa por memoria.

---

## 16. Instrucciones para el asistente

Al recibir este archivo, el asistente debe:

* responder en español;
* tratar `main` como única rama oficial;
* diferenciar baseline, roadmap, decisiones y registros históricos;
* obtener los datos operativos variables desde `MALAK_OPERATIONAL_STATE` y
  verificar la evidencia oficial antes de afirmarlos;
* no inferir autorización de un sprint por su numeración, por el cierre del
  anterior ni por su aparición en un roadmap;
* no modificar el Kernel sin necesidad arquitectónica;
* no incorporar Ruff improvisadamente;
* no confundir el Vault con la fuente de verdad;
* señalar contradicciones;
* evitar completar vacíos mediante suposiciones;
* trabajar mediante pasos pequeños;
* explicar cada paso antes de ejecutarlo;
* solicitar aprobación antes de iniciar un nuevo sprint.

Los conteos de tests, HEAD, sprint representado y demás valores operativos no
deben fijarse manualmente en esta sección.
---

## 17. Resultado de la sesión actual

### 17.1 Registro histórico — 2026-08-14

Esta subsección conserva el resultado documentado de la sesión del
2026-08-14. No representa el estado operativo actual.

```text
Malāk main observado: c65bff257f877460c153583bfcd9819224ca0f5c
Sprint 7.5: cerrado
Validación Malāk: 304 total passed
compileall Malāk: PASS
git diff --check Malāk: PASS

Vault main observado: e9165357160386fea59706d9af4cd7504f539219
Vault PR de sincronización: #31, integrada por acción humana

Agente main observado: b064e89baa183fecdeed414fc7970c55631c8034
Versión del agente: 0.3.0
controlled-proposal E2E: PASS
Autoridad operativa: none
```

La gobernanza de `controlled-proposal` se registra en `DEC-RES-009`. La
capacidad puede preparar una propuesta aislada en el Vault, pero el merge y toda
decisión material permanecen exclusivamente bajo autoridad humana.

Los valores concretos anteriores son evidencia histórica. El estado operativo
posterior corresponde a `MALAK_OPERATIONAL_STATE` y a las fuentes oficiales.
### 17.2 Registro histórico — 2026-08-01

El estado anterior registraba al agente en `0feed6e`, con `230 passed`,
Incremento 4 cerrado y las brechas correctivas todavía pendientes.

Ese estado permanece como evidencia histórica previa al Incremento Correctivo Integral 5 y no representa el estado operativo actual.

### 17.3 Registro histórico — 2026-07-26

Objetivo:

> Validar end-to-end el flujo `dry-run → controlled-proposal`,
> reconciliar la PR documental generada y cerrar operativamente el
> Vault Synchronization Agent para retomar Malāk.

Evidencia verificada:

```text
Repositorio oficial: Aranwill/jarvis
Rama: main
HEAD: d1c90bf0bf55a7076d68c1f4830e89e0d843661c
Último sprint cerrado: Sprint 7.4
Sprint vigente: Sprint 7.5, aprobado y en progreso
Incremento 4: PEP inicial completado e integrado
Suite integral documentada: 244 passed sobre 30b0558

Agente main: c54bfb0f4b1f6d715172d3dbb56704c639154019
Corrección integrada: PR #3
Suite del agente: 178 passed

Vault main: 772991d4b1dfecd95d746398bbcd268f450bfe2c
PR de sincronización: #13, integrada
Merge commit: 772991d4b1dfecd95d746398bbcd268f450bfe2c
run_id: 20260726T214149097509Z_d1c90bf0_70ffa813
resultado end-to-end: pass
```

Punto de continuidad:

1. mantener cerrado el agente para el alcance operativo documentado en aquella sesión;
2. retomar Malāk desde Sprint 7.5;
3. reconocer el Incremento 5 como integrado mediante las PR #22 y #23, sin declarar cerrado el Sprint 7.5;
4. no cerrar Sprint 7.5 sin revisión integral y aprobación humana.

### 17.4 Registro histórico anterior — 2026-07-24

**Fecha:** `2026-07-24`

Objetivo de la sesión:

> Cerrar documentalmente la operacionalización read-only del Vault Synchronization Agent y registrar la decisión humana de utilizarlo manualmente después de cada sesión aprobada de Malāk.

Trabajo completado:

* verificación de `Aranwill/jarvis/main` en `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`;
* verificación de `Aranwill/malak-project-vault/main` en `03032a7b2aaecb47c27c2e8e5bff3a2c04179bd2`;
* verificación de `Aranwill/malak-vault-sync-agent/main` en `ade622b99eaaed0a6342400db743d472aa30a3ae`;
* confirmación de la PR #1 integrada en el repositorio del agente;
* confirmación de working tree limpio y `main` alineada con `origin/main` en el agente;
* confirmación de suite completa con `165 passed`;
* validación de la configuración privada y de su exclusión de Git;
* validación de ejecución manual con resultado `pass` y código de salida `0`;
* validación temporal de ejecución mediante el Programador de tareas de Windows;
* eliminación posterior de la tarea programada por decisión humana;
* adopción del modo operativo `manual-on-demand`;
* confirmación de `last_applied_commit: null`;
* confirmación de Malāk intacto;
* confirmación del Vault intacto durante las ejecuciones del agente;
* creación del informe de cierre de la operacionalización read-only;
* actualización del índice de auditorías;
* actualización del contexto de sesión;
* preservación de `CURRENT_BASELINE.md`;
* preservación de `SPRINT_INDEX.md`;
* preservación de snapshots históricos;
* ausencia de cambios sobre `Aranwill/jarvis`;
* ausencia de aprobación de la Fase 2.

Rama documental utilizada:

```text
docs/vault-sync-operationalization-closure
```

Archivos incorporados o actualizados hasta este punto:

```text
07-audits/vault-synchronization/2026-07-24_VAULT_SYNC_OPERATIONALIZATION_CLOSURE.md
07-audits/AUDIT_INDEX.md
08-session-context/MALAK_SESSION_CONTEXT.md
```

Decisiones registradas en aquella sesión:

* `Aranwill/jarvis` continúa siendo la única fuente de verdad operativa;
* el Vault permanece como capa derivada y sin autoridad operativa;
* Obsidian continúa siendo únicamente una interfaz local;
* la Fase 1 del agente está completada y cerrada;
* la operacionalización read-only está completada;
* el agente posee un repositorio remoto independiente;
* el agente permanece externo al Kernel, runtime y Security Control Plane;
* el agente opera únicamente en modo determinista y de solo lectura;
* el modo operativo elegido es ejecución manual posterior a cada sesión aprobada de Malāk;
* no existe scheduler activo, servicio permanente, daemon ni proceso periódico;
* no se utiliza LLM;
* el agente no modifica `Aranwill/jarvis`;
* el agente no modifica automáticamente el Vault;
* no crea ramas, commits, push ni pull requests en los repositorios observados;
* no modifica snapshots históricos;
* `last_applied_commit` permanece en `null`;
* Fase 2 y posteriores permanecen no aprobadas;
* no se aprobó un próximo sprint de Malāk.

Baseline oficial conservado:

```text
Repositorio: Aranwill/jarvis
Rama: main
HEAD: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
Último sprint cerrado: Sprint 7.3 — Conversation Provider Boundary Stabilization
PR integrado: #13
Suite documentada: 74 passed
Próximo sprint aprobado: ninguno
```

Estado del agente:

```text
Repositorio: Aranwill/malak-vault-sync-agent
Workspace: D:\Ollama\malak-vault-sync-agent
Rama: main
HEAD: ade622b99eaaed0a6342400db743d472aa30a3ae
PR integrada: #1
Working tree: limpio
Remoto: configurado
Upstream: origin/main
HEAD local y remoto: coincidentes
Suite completa: 165 passed
Configuración privada: válida y excluida de Git
Ejecución manual: pass
Ejecución programada de validación: pass
Scheduler final: eliminado
Modo operativo: manual-on-demand
last_applied_commit: null
Autoridad operativa: none
```

Estado del Vault:

```text
Repositorio: Aranwill/malak-project-vault
Rama oficial: main
HEAD base verificado: 03032a7b2aaecb47c27c2e8e5bff3a2c04179bd2
Rama documental utilizada: docs/vault-sync-operationalization-closure
CURRENT_BASELINE.md modificado: no
SPRINT_INDEX.md modificado: no
Snapshots históricos modificados: no
Informes históricos modificados: no
```

Punto de continuidad:

1. actualizar los documentos gobernados restantes dentro del alcance aprobado;
2. revisar el diff completo de la rama;
3. confirmar que `CURRENT_BASELINE.md`, `SPRINT_INDEX.md` y los snapshots permanecen intactos;
4. ejecutar `git diff --check`;
5. revisar la lista total de archivos modificados;
6. crear commits pequeños, trazables y reversibles;
7. publicar la rama documental;
8. abrir una PR draft;
9. esperar revisión y merge humano;
10. no iniciar Fase 2 ni un nuevo sprint de Malāk.

No debe iniciarse ninguna fase posterior sin una nueva decisión y aprobación humana explícita.

---

## 18. Regla de cierre de sesión

Al finalizar una sesión deberá registrarse:

* fecha;
* objetivo;
* archivos creados;
* archivos modificados;
* decisiones tomadas;
* decisiones pendientes;
* estado del repositorio;
* estado del Vault;
* próximo paso recomendado;
* riesgos o contradicciones detectadas.

El cuerpo humano deberá actualizarse cuando cambien el objetivo, las decisiones,
restricciones, arquitectura relevante o hechos históricos necesarios para la
continuidad.

Los cambios de HEAD, tests, working tree, sprint estructurado, baseline u otros
datos operativos deterministas no requieren una edición manual de este cuerpo;
cuando deban representarse, pertenecen a `MALAK_OPERATIONAL_STATE`.

---

## 19. Principios rectores

> Este archivo permite continuar una sesión; no sustituye la verificación.

> La memoria puede estar desactualizada. El repositorio conserva la evidencia.

> El roadmap organiza posibilidades. La aprobación autoriza acciones.

> Cuando exista incertidumbre, no asumir.

> Malāk evoluciona mediante cambios pequeños, gobernados, trazables y reversibles.


---

## Visión futura aprobada en PR #24

Malāk permanece concebida como un control plane horizontal, soberano,
local-first y agnóstico de modelos y proveedores.

Líneas aprobadas para planificación futura:

- escalado segmentado mediante Domain Packs;
- jerarquía de políticas;
- incorporación gobernada de libros, papers, informes y fuentes externas;
- revisión periódica de investigación e incidentes;
- presencia pública y beta progresiva controlada;
- Security Learning Lab y CTF autorizados;
- evaluación adversarial con observador externo;
- Adversarial Twin, honeypots y deception defensiva aislada;
- defensa activa dentro de fronteras propias;
- control soberano de flotas de agentes.

Principio rector:

> La inteligencia propone. La gobernanza autoriza. El enforcement limita.
> El sandbox ejecuta. El observador demuestra. El humano conserva autoridad.

Estado:

```text
visión y planificación futura aprobadas
diseño detallado no aprobado
implementación no aprobada
sin número de sprint
```

No están implementados ni autorizados:

- agentes operativos;
- navegación externa;
- deep web o dark web;
- honeypots públicos;
- malware;
- beta pública;
- Domain Packs;
- respuesta ofensiva externa.
