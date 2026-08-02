---
id: MALAK-KNOWLEDGE-INDEX
title: Malāk Knowledge Index
type: knowledge-index
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-25
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

- **Run ID:** `20260728T213937172036Z_695179aa_379503f9`
- **HEAD oficial observado:** `695179aa491baeaf93189f271e6af9c611d84ca8`
- **Commit previamente observado:** `4afeed440a3bf2096035d0d458d2ef75c71689fd`
- **Generado:** `2026-07-28T21:39:37.172036+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.5.md`
- **Título declarado:** Sprint 7.5 — Base del plano de control de seguridad
- **Estado declarado:** `en progreso`
- **`as_of_commit` declarado:** `af64b062aa1395ba7f7bdd59e5c1099ded68b683`

### Commits oficiales observados

- 695179aa491baeaf93189f271e6af9c611d84ca8	Merge pull request #21 from Aranwill/agent/record-high-value-evolution-ideas
- cad60e8e7bff256458e06d69fc1dfd674075cb0f	docs(ideas): record validation and evolution foundations
- d1c90bf0bf55a7076d68c1f4830e89e0d843661c	Merge pull request #20 from Aranwill/agent/sprint-7.5-pep-doc-reconciliation
- 3c2acdbdadae84535b08c039243d4da405560d89	docs: reconcile sprint 7.5 PEP integration
- af64b062aa1395ba7f7bdd59e5c1099ded68b683	Merge pull request #19 from Aranwill/agent/sprint-7.5-initial-pep
- 30b05587839cdac914e7ee31755bb5c0540862c1	feat(security): add initial policy enforcement point
- 83ceb96838df0770bb9309172a75e3dc79bff121	Merge pull request #18 from Aranwill/agent/sprint-7.5-pdp-doc-reconciliation
- e26469eb422f6686850057de5c0d1ef57f7faaa9	docs: reconcile sprint 7.5 PDP integration
- 78799deabba5009e66c219220349e8202f5464bb	Merge pull request #17 from Aranwill/agent/sprint-7.5-minimal-pdp
- 5947f3b702477bb10a183a75b95efbe06e4681e6	feat(security): add minimal policy decision point

### Evidencia que originó esta proyección

- `governance-change` por `docs/architecture/adr/ADR-002-policy-enforcement-boundary.md`
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
Último sprint formalmente cerrado: Sprint 7.3 — Conversation Provider Boundary Stabilization
Sprint integrado en progreso: Sprint 7.4 — Consolidación de logs, métricas y auditoría
Pull request integrado: PR #14
Baseline técnico: 7cd7fcc811df01555837319ec4cac0a93ef94fff
Suite integral documentada: 121 passed sobre 5b951918006c464745e1eb1e3816bde619fad8b1
Incremento 8: en ejecución documental gobernada
Sprint posterior aprobado: ninguno
```

## 5. Roadmap

- [[03-roadmap/IMPLEMENTATION_ROADMAP|Malāk Implementation Roadmap]]

Regla:

> La presencia de una iniciativa en el roadmap no constituye autorización para implementarla.

Actualmente:

- los Sprints 7.0, 7.1, 7.2 y 7.3 están formalmente cerrados;
- Sprint 7.4 está mergeado y continúa en progreso;
- los Incrementos 1 a 7 de Sprint 7.4 están completados;
- el Incremento 8 está en ejecución documental gobernada;
- no existe un sprint posterior aprobado;
- las iniciativas futuras requieren revisión y aprobación explícita;
- el cierre de un sprint no autoriza automáticamente el siguiente;
- Sprint 7.3 no aprobó una integración entre `Kernel.receive` y `ConversationService`.

---
## 6. Registro de decisiones

- [[05-decisions/PENDING_DECISIONS|Malāk Pending Decisions]]

Categorías actuales:

### Prioridad alta

- cierre formal de Sprint 7.4 después del Incremento 8;
- momento de implementación del Security Control Plane;

### Prioridad media

- política de sincronización con Obsidian;
- esquema de metadatos del Vault.

### Decisiones cerradas recientes

- redefinición del Sprint 7.3;
- relación entre Kernel y `ConversationService`;
- aprobación e implementación de la Fase 1 del Vault Synchronization Agent (`DEC-PEND-013`);
- cierre técnico y validación final de la Fase 1.
- selección de Sprint 7.4 (`DEC-PEND-001`);
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
| 7.4 | Eventos operativos y correlación CLI; cierre formal pendiente |

---

## 10. Seguridad

Carpeta:

[[06-security/SECURITY_INDEX|Índice de seguridad]]

Estado:

`Índice de navegación activo con un modelo de amenazas aceptado para la Fase 1 y controlled-proposal, con brechas técnicas registradas.`

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

La existencia de esta carpeta no implica que el Security Control Plane esté implementado.

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

Cada cambio material del repositorio deberá producir un snapshot nuevo.

Los snapshots anteriores no deben editarse para representar estados posteriores.

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
Extensión controlled-proposal aceptada
Conformidad técnica completa pendiente
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
HEAD: 0feed6eae3d3919ea4867891c12eda5eea81c511
Working tree: limpio
Suite completa: 230 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
last_applied_commit: null
```

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
