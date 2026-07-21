---

id: MALAK-SESSION-CONTEXT
title: Malāk Session Context
type: session-context
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-21
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

```markdown
**Estado de ejecución:**

```text
fundación documental inicial completada

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
**Repositorio remoto privado:** `Aranwill/malak-project-vault`
**Rama:** `main`

Estado verificado:

- navegación principal consolidada mediante `HOME.md`;
- índices creados para gobernanza, arquitectura, sprints, seguridad, auditorías, snapshots y plantillas;
- `KNOWLEDGE_INDEX.md` actualizado con enlaces vigentes;
- esquema de metadatos futuros definido en `00-governance/METADATA_SCHEMA.md`;
- arquitectura reorganizada dentro de `01-architecture/`;
- primer mapa arquitectónico creado en `01-architecture/CURRENT_COMPONENTS_MAP.md`;
- diagrama Mermaid validado visualmente en Obsidian;
- grafo documental operativo y sin nodos huérfanos evidentes;
- Vault sincronizado con `origin/main`.

El repositorio oficial de Malāk no fue modificado durante esta fase.

Se conserva como baseline oficial:

- repositorio: `Aranwill/jarvis`;
- rama: `main`;
- commit: `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`;
- último sprint cerrado: Sprint 7.3 — Conversation Provider Boundary Stabilization;
- pull request integrado: PR #13;
- suite documentada: 74 pruebas aprobadas;
- próximo sprint aprobado: ninguno.

Continúan pendientes y sin aprobación automática:

- Session Context Generator;
- RAG externo;
- auditor arquitectónico;
- auditor de seguridad;
- sincronización automática;
- integración operativa entre el Vault y Malāk.

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

**Fecha:** `2026-07-20`

Objetivo completado:

> Consolidar la navegación y la fundación documental inicial del Malāk Project Vault mediante Obsidian.

Trabajo realizado:

- creación y validación de `HOME.md`;
- creación de índices de gobernanza, arquitectura, sprints, seguridad, auditorías, snapshots y plantillas;
- actualización controlada de `KNOWLEDGE_INDEX.md`;
- creación de `00-governance/METADATA_SCHEMA.md`;
- reorganización de Arquitectura dentro de `01-architecture/`;
- creación de `01-architecture/CURRENT_COMPONENTS_MAP.md`;
- validación del flujo Kernel–Planner–Capability contra el repositorio oficial;
- incorporación y validación visual del diagrama Mermaid;
- comprobación del grafo documental y de los enlaces internos;
- commits pequeños y sincronización del Vault con `origin/main`.

Decisiones preservadas:

- el repositorio oficial continúa siendo la fuente de verdad;
- el Vault permanece como capa derivada y no operativa;
- Obsidian es únicamente una interfaz;
- ningún artefacto del Vault puede modificar Malāk automáticamente;
- no se aprobó un próximo sprint;
- no se aprobó RAG, automatización documental ni auditores externos.

El repositorio oficial de Malāk fue actualizado mediante el Sprint 7.3 y el PR #13 antes de esta sincronización gobernada del Vault.

Baseline conservado:

- repositorio: `Aranwill/jarvis`;
- rama: `main`;
- commit: `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`;
- último sprint cerrado: Sprint 7.3 — Conversation Provider Boundary Stabilization;
- pull request integrado: PR #13;
- pruebas documentadas: 74 aprobadas.

Punto de continuidad:

La próxima sesión debe comenzar desde el Vault ya consolidado, sin reconstruir su estructura.

Posibles trabajos futuros, todavía no aprobados:

- mapa del subsistema conversacional;
- mapa de métricas y telemetría;
- mapa de contratos actuales;
- mapa de límites del Kernel;
- mejora visual controlada de `HOME.md`.

No debe iniciarse ninguno automáticamente.

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
