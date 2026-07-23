---

id: MALAK-SESSION-CONTEXT
title: Malāk Session Context
type: session-context
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-22
source_repository: Aranwill/jarvis
source_branch: main
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
-----------------------

# Malāk Session Context

## 1. Instrucción de uso

Este archivo es el punto de entrada para iniciar una sesión de trabajo sobre Malāk.

Debe utilizarse para:

* recuperar rápidamente el contexto vigente;
* evitar depender de conversaciones anteriores;
* distinguir baseline, roadmap y propuestas;
* mantener alineación con la arquitectura y la gobernanza;
* reducir contradicciones y reconstrucciones incorrectas.

Este archivo no reemplaza las fuentes oficiales del repositorio.

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

## 3. Baseline operativo vigente

**Último sprint cerrado:**

```text
Sprint 7.3 — Conversation Provider Boundary Stabilization
```

**Sprints cerrados del bloque 7.x:**

| Sprint | Resultado                                                  |
| ------ | ---------------------------------------------------------- |
| 7.0    | CLI mínima con `MockLLMRuntime`                            |
| 7.1    | CLI con `OllamaRuntime` mediante configuración externa     |
| 7.2    | Contrato estructural `RuntimeMetricSink` de solo escritura |
| 7.3    | Estabilización de la frontera `ConversationService`–Provider–Runtime |

**Suite validada al cierre del Sprint 7.3:**

```text
74 passed
```

**Último commit remoto verificado al revisar este contexto:**

```text
fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
```

Descripción:

```text
Merge pull request #13 from Aranwill/feature/sprint-7.3-conversation-provider-boundary
```

Estos datos deben volver a verificarse si cambia `HEAD`.

---

## 4. Estado arquitectónico actual

Malāk mantiene dos rutas todavía separadas.

### 4.1 Pipeline Kernel–Planner–Capability

Componentes principales:

* Kernel MVP;
* Planner MVP;
* Capability Registry;
* EchoCapability.

### 4.2 Subsistema conversacional de CLI

Composición actual:

```text
Variables de entorno
        ↓
CLIConfiguration
        ↓
build_runtime()
        ↓
LLMRuntime
├── MockLLMRuntime
└── OllamaRuntime
        ↓
RuntimeConversationProvider
        ↓
ConversationProviderRegistry
        ↓
ConversationService
        ↓
run_cli()
```

No existe todavía una integración formal validada entre:

```text
Kernel.receive
```

y:

```text
ConversationService
```

No existe integración formal entre `Kernel.receive` y `ConversationService`.

El cierre del Sprint 7.3 no autoriza ni propone dicha integración.

La CLI técnica no representa todavía el pipeline cognitivo completo de Malāk.

---

## 5. Componentes implementados

Estado conocido del baseline:

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

Ruff no forma parte del baseline actual.

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

## 9. Fuera de alcance actual

Todavía no forman parte del baseline:

* integración formal Kernel–ConversationService;
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
* Security Control Plane implementado;
* Secure Context Manager implementado;
* RAG externo;
* auditor externo.

---

## 10. Estado del próximo sprint

```text
Próximo sprint: no aprobado.
```

El Sprint 7.3 fue cerrado e integrado en `main`.

No existe un Sprint 7.4 aprobado ni una continuación automática autorizada.

No debe iniciarse un sprint por continuidad numérica.

Antes de seleccionar el siguiente sprint se requiere:

* relevamiento completo;
* identificación de una necesidad real;
* revisión de arquitectura;
* revisión de código;
* revisión de tests;
* revisión documental;
* definición de alcance;
* definición de fuera de alcance;
* riesgos;
* rollback;
* criterios de aceptación;
* aprobación explícita del propietario.

---

## 11. Decisiones abiertas prioritarias

### Alta prioridad

* selección del próximo sprint;
* momento de implementación del Security Control Plane;
* modelo de versionado y respaldo del Project Vault.

### Prioridad media

* alcance y separación entre logs, métricas y auditoría;
* política de sincronización con Obsidian;
* esquema de metadatos del Vault.

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

Estado actual de la secuencia:

1. **Project Context Foundation:** completada en su alcance documental inicial;
2. **Obsidian Knowledge Foundation:** navegación base, índices, metadatos y primer mapa arquitectónico completados;
3. **Session Context Generator:** pendiente y no aprobado para implementación;
4. **External Project RAG:** pendiente y no aprobado para implementación;
5. **Architecture & Security Auditor Foundation:** pendiente y no aprobado para implementación.

### Vault Synchronization Agent Foundation

Estado vigente:

```text
Incorporación documental: completada mediante las PR #2, #3 y #4
Arquitectura de Fase 1: accepted
Política de Fase 1: accepted
Modelo de amenazas de Fase 1: accepted
Fase 1: completed
Gates 0 a 9: cerrados
Agente operativo: herramienta local determinista de solo lectura
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

Baseline final del agente:

```text
Rama: main
HEAD: 954659b
Último commit: docs(baseline): record phase 1 completion
Commit anterior: 7ff4880 fix(audit): align canonical run id contract
Working tree: limpio
Suite completa: 148 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
last_applied_commit: null
```

Estado remoto verificado:

```text
Remoto configurado: no
URL remota: ninguna
Upstream de main: no
Respaldo remoto: pendiente de decisión humana
Push ejecutado: no
```

La implementación completada se limita exclusivamente a la Fase 1.

La iniciativa:

* permanece fuera del Kernel, del runtime y del Security Control Plane;
* no forma parte del roadmap operativo de `Aranwill/jarvis`;
* mantiene `Aranwill/jarvis/main` en modo de solo lectura;
* opera desde un workspace externo;
* opera en modo `dry-run`;
* no utiliza LLM;
* no modifica archivos de `Aranwill/jarvis`;
* no modifica automáticamente archivos del Vault;
* no crea ramas, commits, push ni pull requests mediante el agente;
* mantiene snapshots históricos inmutables;
* no puede aprobar, habilitar auto-merge ni mergear PR;
* reserva toda ampliación de alcance al propietario humano;
* conserva `operational_authority: none`.

La decisión correspondiente permanece resuelta y cerrada en:

```text
DEC-PEND-013 — Aprobación e implementación del Vault Synchronization Agent
```

El cierre técnico se documenta en:

```text
07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE.md
```

El Vault:

* permanece fuera del repositorio principal;
* no forma parte del Kernel;
* no forma parte del runtime;
* no reemplaza Git;
* no reemplaza documentos normativos;
* no puede modificar Malāk automáticamente;
* organiza información derivada y contexto operativo.

---

## 13. Estado actual del Vault

**Repositorio local:** `D:\Ollama\malak-project-vault`  
**Repositorio remoto público:** `Aranwill/malak-project-vault`  
**Rama oficial:** `main`

Estado verificado del Vault antes de esta actualización documental:

* PR #2 mergeada;
* PR #3 mergeada;
* PR #4 mergeada;
* HEAD remoto verificado: `52976e771ad8307badbc0ac37a78a771e6df51fc`;
* rama oficial: `main`;
* working tree limpio antes de iniciar la rama de cierre;
* rama documental actual: `docs/vault-sync-phase-1-closure`;
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
* Vault Synchronization Agent Foundation integrada documentalmente.

Estado posterior de la iniciativa:

```text
Arquitectura de Fase 1: accepted
Política de Fase 1: accepted
Modelo de amenazas de Fase 1: accepted
Fase 1: completed
Gates 0 a 9: cerrados
Autoridad operativa: none
Agente operativo: herramienta local determinista de solo lectura
Kernel afectado: no
Runtime afectado: no
Security Control Plane afectado: no
Fase 2 y posteriores: no aprobadas
```

El repositorio oficial de Malāk no fue modificado durante esta línea de trabajo.

Se conserva como baseline oficial documentado:

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

## 14. Iniciativas futuras aceptadas conceptualmente

Sin sprint aprobado:

* Security Control Plane Foundation;
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
* reconocer Sprint 7.3 como último sprint cerrado;
* utilizar 74 pruebas como último resultado documentado, no como resultado eterno;
* diferenciar baseline, roadmap y propuestas;
* no asumir que existe un próximo sprint aprobado;
* no modificar el Kernel sin necesidad arquitectónica;
* no incorporar Ruff improvisadamente;
* no confundir el Vault con la fuente de verdad;
* verificar el repositorio antes de afirmar datos variables;
* señalar contradicciones;
* evitar completar vacíos mediante suposiciones;
* trabajar mediante pasos pequeños;
* explicar cada paso antes de ejecutarlo;
* solicitar aprobación antes de iniciar un nuevo sprint.

---

## 17. Resultado de la sesión actual

**Fecha:** `2026-07-22`

Objetivo de la sesión:

> Cerrar administrativamente la Fase 1 del Vault Synchronization Agent, verificar su estado remoto y actualizar de forma gobernada la documentación derivada del Malāk Project Vault.

Trabajo completado:

* verificación del repositorio local del agente;
* confirmación de rama `main`;
* confirmación de HEAD `954659b`;
* confirmación de working tree limpio;
* verificación de ausencia de remoto;
* verificación de ausencia de upstream;
* confirmación de que no se ejecutó push;
* confirmación de Gate 8 cerrado;
* confirmación de Gate 9 cerrado;
* confirmación de Fase 1 cerrada formalmente;
* confirmación de suite completa con `148 passed`;
* confirmación de `compileall` correcto;
* confirmación de `git diff --check` correcto;
* confirmación de resultado end-to-end `pass`;
* confirmación de Malāk intacto;
* confirmación del Vault intacto durante la ejecución del agente;
* confirmación de `last_applied_commit: null`;
* confirmación de hashes SHA-256 verificados;
* confirmación de comandos Git operativos auditados como read-only;
* creación del informe de cierre de Fase 1;
* actualización de decisiones, roadmap, arquitectura, política, seguridad e índices relacionados;
* preservación de `CURRENT_BASELINE.md`;
* preservación de snapshots históricos;
* preservación de informes históricos;
* ausencia de cambios sobre `Aranwill/jarvis`.

Rama documental utilizada:

```text
docs/vault-sync-phase-1-closure
```

Commits creados hasta esta actualización:

```text
c7bb158 docs(audit): record vault sync phase 1 closure
e7cec8a docs(audits): index vault sync phase 1 closure
3888a27 docs(decisions): record vault sync phase 1 result
91942d5 docs(roadmap): close vault sync phase 1
f820465 docs(architecture): close vault sync phase 1
b594af0 docs(governance): approve vault sync phase 1 policy
07d5dc4 docs(security): close vault sync phase 1 threat model
32e67b6 docs(governance): index vault sync phase 1 closure
706b522 docs(architecture): index vault sync phase 1 closure
63f6f27 docs(security): index vault sync phase 1 closure
17a5bf2 docs(knowledge): index vault sync phase 1 closure
```

Decisiones vigentes:

* `Aranwill/jarvis` continúa siendo la única fuente de verdad operativa;
* el Vault permanece como capa derivada y sin autoridad operativa;
* Obsidian continúa siendo únicamente una interfaz local;
* la Fase 1 del agente está completada y cerrada;
* el agente permanece externo al Kernel, runtime y Security Control Plane;
* el agente opera únicamente en modo determinista y de solo lectura;
* no se utilizó LLM;
* el agente no modificó `Aranwill/jarvis`;
* el agente no modificó automáticamente el Vault;
* no creó ramas, commits, push ni pull requests;
* no modificó snapshots históricos;
* no existe remoto configurado para el agente;
* no se ejecutó push del agente;
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
Workspace: D:\Ollama\malak-vault-sync-agent
Rama: main
HEAD: 954659b
Working tree: limpio
Remoto: no configurado
Upstream: no configurado
Suite completa: 148 passed
compileall: correcto
git diff --check: correcto
End-to-end: pass
last_applied_commit: null
Autoridad operativa: none
```

Estado del Vault:

```text
Repositorio: Aranwill/malak-project-vault
Rama oficial: main
HEAD base verificado: 52976e771ad8307badbc0ac37a78a771e6df51fc
Rama documental actual: docs/vault-sync-phase-1-closure
CURRENT_BASELINE.md modificado: no
Snapshots históricos modificados: no
Informes históricos modificados: no
```

Punto de continuidad:

1. completar los índices o documentos finales aún necesarios;
2. validar el diff completo de la rama;
3. confirmar que `CURRENT_BASELINE.md` y snapshots permanecen intactos;
4. ejecutar `git diff --check`;
5. revisar la lista total de archivos modificados;
6. publicar la rama documental;
7. abrir una PR draft;
8. esperar revisión y merge humano;
9. no iniciar Fase 2;
10. tratar la creación del remoto del agente como una tarea administrativa separada.

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

Luego deberá actualizarse este archivo si cambió algún dato operativo relevante.

---

## 19. Principios rectores

> Este archivo permite continuar una sesión; no sustituye la verificación.

> La memoria puede estar desactualizada. El repositorio conserva la evidencia.

> El roadmap organiza posibilidades. La aprobación autoriza acciones.

> Cuando exista incertidumbre, no asumir.

> Malāk evoluciona mediante cambios pequeños, gobernados, trazables y reversibles.