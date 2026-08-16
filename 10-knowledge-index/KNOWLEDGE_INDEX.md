---
id: MALAK-KNOWLEDGE-INDEX
title: Malāk Knowledge Index
type: knowledge-index
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-08-12
source_of_truth: project-vault
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

- **Run ID:** `20260816T002114666009Z_089255e2_b9fbb7e7`
- **HEAD oficial observado:** `089255e23bd2b686436140ca569edf09c08819a7`
- **Commit previamente observado:** `c65bff257f877460c153583bfcd9819224ca0f5c`
- **Generado:** `2026-08-16T00:21:14.666009+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.6.md`
- **Título declarado:** Sprint 7.6 — Secure Context Lifecycle Foundation
- **Estado declarado:** `cerrado`
- **`as_of_commit` declarado:** `821497485f1b861cafa97cc5720616c3314b35bf`

### Commits oficiales observados

- 089255e23bd2b686436140ca569edf09c08819a7	Merge pull request #43 from Aranwill/docs/sprint-7.6-final-reconciliation
- 145f4f96b06429b95725b189d88865270d4efce9	docs(project): reconcile Sprint 7.6 closure
- 821497485f1b861cafa97cc5720616c3314b35bf	Merge pull request #42 from Aranwill/sprint/7.6-h-context-propagation-contract
- a481f0b1cff36c737feaef3a39c8962e1c31f5fd	Merge pull request #41 from Aranwill/sprint/7.6-g-context-validity-window
- 5e3273329a9c7517f1f61bf25d84f084fe6c4828	Merge pull request #40 from Aranwill/sprint/7.6-f-pdp-context-lifecycle
- aa06e98a2e1e20a5d81007bac83920a79f23092d	feat(security): establish SecurityContext propagation contract
- 47ac4f68b3eb7df64a53b3faac38b37e991849a3	feat(security): enforce SecurityContext validity window
- 1733e1791897f9fa1524e2d9c8f0c5e42e2cbe6b	feat(security): enforce SecurityContext lifecycle in PDP
- 3945fd0b664ab5b56b15fa3ce3485abf16d8d990	feat(security): establish SecurityContextRenewer boundary
- e674567a8aa6db3eccfb06ef2f91097517614097	feat(security): establish SecurityContextIssuer boundary
- 5dceb2b998ad07093eef2565e8daaebe70ca6af9	feat(security): establish SecurityContextValidator boundary
- c9769b63afc0b1aa72f9dd023b205e2762f0029f	feat(security): establish Clock boundary
- 92e2911199f836d7c83d3d87c9739ccfbfaa0785	Merge pull request #39 from Aranwill/sprint/7.6-a-security-context-contract
- 9833a33e5daf360baf2412b0df116f722ca237cd	feat(security): establish SecurityContext lifecycle contract
- a11617e4056325d593e3b1999baf07570cebd0d6	Merge pull request #38 from Aranwill/agent/directional-communication-rule
- 502a80775ba3383f5e5161516975109208f11c17	docs: formalize directional communication and authority flow
- 7b1cd23470b8ab2b44ad58ce8ab885b4d9d82f64	Merge pull request #37 from Aranwill/agent/engineering-method-sdd-tdd
- 2bfb357792aa5fc836f28b9ed431660f80513137	docs: establish SDD TDD and risk-based engineering method

### Evidencia que originó esta proyección

- `governance-change` por `docs/architecture/adr/ADR-003-directional-communication-and-authority-flow.md`
- `governance-change` por `docs/architecture/decisions/decision-index.md`
<!-- MALAK_VAULT_SYNC:END -->

## 1. Propósito

Este documento es el índice maestro de navegación del Malāk Project Vault.

Su función es:

- facilitar el acceso al conocimiento vigente;
- conectar gobernanza, baseline, roadmap y decisiones;
- reducir búsquedas manuales;
- preparar relaciones documentales para Obsidian;
- servir como base futura para índices temáticos;
- preservar la diferencia entre fuentes oficiales y artefactos derivados.

Este índice no reemplaza los documentos enlazados ni les concede autoridad adicional.

---

## 2. Punto de entrada de sesión

- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto operativo de sesión]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline actual]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]

Orden recomendado al iniciar una sesión:

1. contexto de sesión;
2. baseline actual;
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

## 4. Baseline vigente

- [[02-current-baseline/CURRENT_BASELINE|Malāk Current Baseline]]

Estado documentado al revisar este índice:

```text
Repositorio: Aranwill/jarvis
Rama permanente: main
Versión nominal: v0.6.0-alpha
Último sprint formalmente cerrado: Sprint 7.5 — Security Control Plane Foundation
Último cambio documental integrado: PR #34 — reconciliación de contexto posterior a IDEA-024
Baseline técnico observado: cdc0f1d78d1e896400f81a609df16aaa90d25313
Versión nominal: v0.6.0-alpha
Suite integral documentada del cierre de Sprint 7.5: 304 passed
Validación de seguridad documentada: 183 security-specific passed
compileall: PASS
git diff --check: PASS
Sprint posterior autorizado: ninguno
```

## 5. Roadmap

- [[03-roadmap/IMPLEMENTATION_ROADMAP|Malāk Implementation Roadmap]]

Regla:

> La presencia de una iniciativa en el roadmap no constituye autorización para implementarla.

Actualmente:

- los Sprints 7.0, 7.1, 7.2, 7.3, 7.4 y 7.5 están formalmente cerrados;
- Sprint 7.5 cerró la Security Control Plane Foundation;
- no existe un sprint posterior autorizado;
- IDEA-024 — Governed Agent Composition & Mission Orchestration Foundation permanece en estado `capturada` y no forma parte del roadmap aprobado;
- las iniciativas futuras requieren revisión y aprobación explícita;
- el cierre de un sprint no autoriza automáticamente el siguiente;
- no existe una integración formal aprobada entre `Kernel.receive` y `ConversationService`.

---
## 6. Registro de decisiones

- [[05-decisions/PENDING_DECISIONS|Malāk Pending Decisions]]

Categorías actuales:

### Prioridad alta

No se registra una decisión abierta de alta prioridad derivada del cierre del Sprint 7.5.

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

Existe un mapa derivado vigente:

- [[01-architecture/CURRENT_COMPONENTS_MAP|Mapa de componentes actuales]]

El mapa representa:

- el flujo Kernel–Planner–Capability;
- la frontera de eventos operativos integrada en la CLI;
- la separación entre métricas, eventos operativos y auditoría.

El subsistema conversacional se mantiene separado y no existe integración formal entre `Kernel.receive` y `ConversationService`.

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
- diferenciar implementación actual y arquitectura futura;
- evitar reinterpretaciones no aprobadas.

No deben crearse diagramas o mapas sin una necesidad concreta.

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

Sprints cerrados conocidos:

| Sprint | Resultado |
| ------ | --------- |
| 7.0 | CLI mínima con `MockLLMRuntime` |
| 7.1 | Composición de CLI con `OllamaRuntime` |
| 7.2 | Contrato estructural `RuntimeMetricSink` |
| 7.3 | Conversation Provider Boundary Stabilization |
| 7.4 | Logs, métricas, eventos operativos y sincronización gobernada; cerrado |
| 7.5 | Security Control Plane Foundation; cerrado |

---

## 10. Seguridad

Carpeta:

[[06-security/SECURITY_INDEX|Índice de seguridad]]

Estado:

Índice de navegación activo con un modelo de amenazas aceptado para la
Fase 1 y `controlled-proposal`, con los controles correctivos del
Incremento Correctivo Integral 5 implementados y certificados.

Los riesgos residuales de gobernanza, autoridad y operación permanecen
documentados; la certificación técnica no elimina esos riesgos ni amplía
la autoridad del agente.

El agente permanece fuera del Security Control Plane, del Kernel y del runtime.

Controles de Fase 1 verificados:

- comandos Git auditados como read-only;
- validación de repositorio, rama y `HEAD`;
- allowlist y denylist;
- controles TOCTOU;
- validación de rutas, Markdown básico, archivos YAML independientes,
  enlaces Markdown relativos y metadatos cubiertos;
- hashes SHA-256;
- invariantes de no modificación;
- `last_applied_commit: null`;
- Malāk intacto;
- Vault intacto.

Contenido futuro previsto:

- riesgos;
- controles;
- límites de autoridad;
- amenazas;
- Security Control Plane;
- Secure Context Manager;
- seguridad del Vault;
- revisión de plugins;
- políticas de sincronización;
- tratamiento de información sensible.

No se almacenarán:

- contraseñas;
- tokens;
- claves privadas;
- secretos de API;
- credenciales;
- dumps sensibles no sanitizados.

La existencia de esta carpeta no concede autoridad adicional. El Security Control Plane Foundation está implementado y Sprint 7.5 está cerrado, pero sus capacidades permanecen sujetas a las fronteras de autoridad y seguridad vigentes.

---

## 11. Auditorías

Carpeta:

[[07-audits/AUDIT_INDEX|Índice de auditorías]]

Estado:

`Índice de navegación activo con informes formales de Vault Synchronization registrados.`

Informes vigentes:

- [[07-audits/vault-synchronization/2026-07-21_VAULT_SYNC_FOUNDATION_POLICY|Informe de incorporación documental de Vault Synchronization Agent Foundation]];
- [[07-audits/vault-synchronization/2026-07-21_VAULT_SYNC_FOUNDATION_MERGE_CLOSURE|Informe de cierre posterior al merge humano]];
- [[07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE|Informe de cierre de la Fase 1 del Vault Synchronization Agent]].

El primer informe conserva el estado previo al merge.

El segundo informe registra la integración efectiva mediante la PR #2.

El tercer informe registra la implementación supervisada, la validación end-to-end y el cierre formal de los Gates 0 a 9.

Los informes históricos anteriores no deben modificarse retroactivamente.

Contenido futuro previsto:

- auditorías documentales;
- auditorías arquitectónicas;
- controles;
- hallazgos;
- evidencia;
- desviaciones;
- remediaciones;
- resultados históricos.

Todo auditor deberá operar:

- en modo de solo lectura por defecto;
- con evidencia reproducible;
- sin capacidad de modificación automática;
- sujeto a revisión humana;
- separado del Kernel y del runtime.

---

## 12. Snapshots del repositorio

Carpeta:

`09-repository-snapshots`

### Snapshots disponibles

- [[09-repository-snapshots/SNAPSHOT_INDEX|Índice de snapshots]]
- [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Snapshot de main — 2026-07-20 — fdb3ee9]]
- [[09-repository-snapshots/2026-07-21_MAIN_FD4DA3D|Snapshot de main — 2026-07-21 — fd4da3d]]
- [[09-repository-snapshots/2026-07-25_MAIN_7CD7FCC|Snapshot de main — 2026-07-25 — 7cd7fcc]]

El snapshot de `7cd7fcc` registra el merge técnico de Sprint 7.4 sin
declarar su cierre formal.

No debe modificarse el snapshot de `fdb3ee9` para representar el estado posterior.

Estado registrado en el snapshot:

- repositorio: `Aranwill/jarvis`;
- rama: `main`;
- commit: `fdb3ee922efc796e53ade1fc3abe4125f4072bd0`;
- `HEAD` local y `origin/main`: coincidentes;
- working tree: limpio;
- tags sobre `HEAD`: ninguno;
- Python validado: `3.12.10`;
- entorno de tests: `.venv`;
- tests: `69 passed in 0.21s`;
- compilación: correcta;
- `git diff --check`: correcto;
- estado documental: histórico e inmutable.

Los snapshots históricos permanecen inmutables y no deben editarse para representar estados posteriores.

La creación de un snapshot nuevo debe realizarse mediante el proceso gobernado correspondiente cuando el cambio material del baseline justifique conservar una nueva referencia histórica.

---

## 13. Project Vault

- [[README|README del Project Vault]]

Ubicación local:

`D:\Ollama\malak-project-vault`

Repositorio remoto independiente:

`Aranwill/malak-project-vault`

Rama permanente:

`main`

El Vault permanece separado de:

- repositorio oficial de Malāk;
- Kernel;
- runtime;
- memoria cognitiva;
- índices vectoriales;
- cachés;
- automatización operativa.

El repositorio oficial conserva la fuente de verdad.

---

## 14. Flujo de conocimiento

```text
Repositorio oficial de Malāk
        ↓
Verificación directa
        ↓
Documentos derivados del Vault
        ↓
Índices de navegación
        ↓
Contexto de sesión
        ↓
Futuro RAG externo
        ↓
Futuro auditor externo

---
```

## 14.1 Ideas y visión futura

El registro no normativo de ideas permanece en el repositorio oficial:

`documents/projects/jarvis/ideas.md`

Estado relevante observado:

- `IDEA-024 — Governed Agent Composition & Mission Orchestration Foundation`: `capturada`;
- su incorporación no modifica Blueprint, Constituciones, Gobernanza ni roadmap;
- no autoriza un nuevo sprint ni implementación;
- cualquier promoción futura deberá pasar por evaluación arquitectónica y aprobación humana.

---

## 15. Índices futuros

Se crearán únicamente cuando exista suficiente contenido real.

Índices candidatos:

- `ARCHITECTURE_INDEX.md`;
- `SECURITY_INDEX.md`;
- `SPRINT_INDEX.md`;
- `DECISION_INDEX.md`;
- `AUDIT_INDEX.md`;
- `SOURCE_INDEX.md`;
- `GLOSSARY_INDEX.md`.

No deben crearse índices vacíos únicamente para completar la estructura.

Cada índice deberá justificar:

- qué problema de navegación resuelve;
- qué fuentes utiliza;
- qué autoridad posee;
- cómo se mantiene actualizado;
- qué información excluye.

---

## 16. Reglas de navegación

Al utilizar este índice:

- verificar siempre la vigencia del documento enlazado;
- no asumir que una propuesta está aprobada;
- no considerar un resumen superior a su fuente;
- revisar el baseline antes del roadmap;
- revisar decisiones pendientes antes de iniciar trabajo;
- verificar el repositorio para datos variables;
- señalar cualquier contradicción;
- no reutilizar snapshots como si representaran el presente;
- diferenciar documentos activos, históricos y propuestos.

---

## 17. Verificación antes de una sesión técnica

Desde el repositorio oficial:

```powershell
cd D:\Ollama\jarvis

git fetch --prune
git branch --show-current
git status
git rev-parse HEAD
git rev-parse origin/main
git log -1 --oneline

.\.venv\Scripts\Activate.ps1
python -m pytest -q
python -m compileall src tests
git diff --check

---
```

## 18. Regla de actualización

Actualizar este índice cuando:

- se cree un documento principal;
- cambie el baseline;
- se cierre un sprint;
- se apruebe o cierre una decisión;
- se cree un índice temático;
- se incorpore una nueva categoría de conocimiento;
- cambie el flujo de navegación recomendado;
- se genere un nuevo snapshot;
- se archive o reemplace un documento enlazado.

Toda actualización debe conservar enlaces válidos y evitar referencias a documentos inexistentes.

---

## 19. Estado actual de la fundación

### Project Context Foundation

`implementada en su alcance documental inicial`

Incluye:

- gobernanza del Vault;
- modelo de autoridad;
- ciclo de vida del contenido;
- baseline actual;
- roadmap derivado;
- decisiones pendientes;
- contexto de sesión;
- plantillas;
- README;
- Git local;
- respaldo remoto público;
- integración mínima con Obsidian;
- índice maestro;
- primer snapshot formal.

### Obsidian Knowledge Foundation

`iniciada`

Incluye:

- Vault abierto en Obsidian;
- configuración local excluida de Git;
- navegación mediante Wikilinks;
- índice maestro inicial.

Todavía no incluye:

- plugins comunitarios;
- automatización;
- GraphRAG;
- generación automática de contexto;
- índices temáticos avanzados.

---

## 20. Principios rectores

> Un índice ayuda a encontrar conocimiento; no reemplaza su autoridad.

> La navegación debe comenzar desde el contexto vigente y terminar en evidencia verificable.

> No se debe crear estructura documental sin una necesidad real.

> Un snapshot conserva el pasado; el repositorio determina el presente.

> El Vault conserva contexto. El repositorio conserva el estado oficial.

---

## 21. Vault Synchronization Agent Foundation

Capacidad externa de observación, comparación, validación y generación de evidencia para el Malāk Project Vault.

El alcance vigente añade la preparación de propuestas deterministas en
ramas aisladas del Vault, sin autoridad de aprobación o merge.

La fundación documental fue integrada en `Aranwill/malak-project-vault/main` mediante:

```text
PR #2
Merge commit: bcefa948b250830139233376088d1e65bd159143

PR #3
Merge commit: 918997a61e9a7b68c353c2eb5697ea21ede7e91f

PR #4
Merge commit: 52976e771ad8307badbc0ac37a78a771e6df51fc
```

### Gobernanza

- [[00-governance/VAULT_SYNC_AGENT_POLICY|Política obligatoria del Vault Synchronization Agent]]

Estado:

```text
accepted
```

### Arquitectura

- [[01-architecture/VAULT_SYNCHRONIZATION_AGENT_FOUNDATION|Vault Synchronization Agent Foundation]]

Estado:

```text
Fase 1 aceptada, implementada y cerrada
Extensión controlled-proposal aceptada, implementada y certificada
Incremento Correctivo Integral 5 cerrado técnica y operativamente
Conformidad del alcance correctivo aprobado completada
```

### Seguridad

- [[06-security/VAULT_SYNCHRONIZATION_THREAT_MODEL|Modelo de amenazas del Vault Synchronization Agent]]

Estado:

```text
accepted
```

### Auditoría

- [[07-audits/vault-synchronization/2026-07-21_VAULT_SYNC_FOUNDATION_POLICY|Informe de incorporación documental]]
- [[07-audits/vault-synchronization/2026-07-21_VAULT_SYNC_FOUNDATION_MERGE_CLOSURE|Informe de cierre posterior al merge humano]]
- [[07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE|Informe de cierre de la Fase 1]]

### Plantilla

- [[templates/VAULT_SYNC_EXECUTION_REPORT_TEMPLATE|Plantilla de informe de ejecución]]

### Decisión cerrada

- [[05-decisions/PENDING_DECISIONS#DEC-PEND-013 — Aprobación e implementación del Vault Synchronization Agent|DEC-PEND-013 — Aprobación e implementación del Vault Synchronization Agent]]
- [[05-decisions/PENDING_DECISIONS#DEC-RES-009 — Extensión gobernada controlled-proposal|DEC-RES-009 — Extensión gobernada controlled-proposal]]

`DEC-PEND-013` permanece `closed`.
`DEC-RES-009` formaliza el alcance operativo controlado vigente.

### Baseline vigente del agente

```text
Workspace: D:\Ollama\malak-vault-sync-agent
Rama: main
HEAD: 5afd03e1697e4820b8b62ff3db23109fdfde8bcb
Versión: 0.3.0
Working tree: limpio al cierre operativo
Suite completa: 260 passed
compileall: PASS
git diff --check: PASS
GitHub Actions Ubuntu: PASS
GitHub Actions Windows: PASS
Validación nativa Windows: PASS
GitHub CLI real: PASS
Recovery negativo real: PASS
Recovery positivo real: PASS
Estado persistente: esquema v3 intacto
last_applied_commit: null
pending_proposal_*: null
Modo operativo: manual-on-demand
Scheduler activo: no
Autoridad operativa: none
```

El Incremento Correctivo Integral 5 cerró técnica y operativamente el
alcance correctivo aprobado de `controlled-proposal`.

Este estado no autoriza Fase 2, scheduler, auto-merge, uso de LLM ni
ninguna ampliación de autoridad.

### Estado remoto

```text
Remoto configurado: sí
URL remota: Aranwill/malak-vault-sync-agent
Upstream de main: origin/main
Respaldo remoto: completado
```

### Estado general

```text
Incorporación documental: completada
Arquitectura de Fase 1: accepted
Política de Fase 1: accepted
Modelo de amenazas de Fase 1: accepted
Fase 1: completed
Controlled-proposal: approved
Controlled-proposal conformance: corrective work required
Gates 0 a 9: cerrados
Agente operativo: herramienta externa determinista de propuesta controlada
Autoridad operativa: none
Kernel afectado: no
Runtime afectado: no
Security Control Plane afectado: no
Fase 2 y posteriores: no aprobadas
```

La Fase 1 y la extensión vigente:

- observa y compara estados;
- clasifica cambios;
- resuelve documentos candidatos;
- aplica allowlist y denylist;
- valida rutas, Markdown básico, archivos YAML independientes, enlaces
  Markdown relativos, hashes y metadatos cubiertos;
- genera evidencia e informes locales;
- no modifica `Aranwill/jarvis`;
- escribe solo en una rama aislada y allowlisted del Vault;
- crea commits, push y PR draft sin aprobar ni mergear;
- no utiliza LLM;
- no modifica snapshots históricos;
- no cierra decisiones automáticamente.

Permanecen pendientes la revalidación final, el frontmatter YAML, los
wikilinks, la denylist exacta de snapshots, la recuperación de propuestas
remotas no persistidas localmente y el disparador real de los informes.
`DEC-PEND-013` conserva la decisión fundacional de Fase 1,
`DEC-RES-008` conserva el modo manual y `DEC-RES-009` conserva el alcance
autorizado de propuesta controlada.

La implementación del agente no modifica el baseline operativo de Malāk y no lo convierte en parte del Kernel, del runtime ni del sistema cognitivo.

Fase 2 y posteriores permanecen no aprobadas.

Cualquier ampliación requerirá una decisión independiente y aprobación humana explícita.
