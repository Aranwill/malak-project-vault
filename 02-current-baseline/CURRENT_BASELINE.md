---

id: MALAK-BASELINE-CURRENT
title: Malāk Current Baseline
type: baseline-summary
status: active
authority_level: baseline
authority_rank: 5
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-21
source_of_truth: repository
source_repository: Aranwill/jarvis
source_branch: main
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
-----------------------

# Malāk Current Baseline

## 1. Propósito

Este documento ofrece una vista operativa compacta del baseline vigente de Malāk.

Es un artefacto derivado del repositorio oficial y no reemplaza:

* la Constitución Cognitiva;
* la Constitución de Gobernanza;
* el Blueprint;
* las especificaciones aprobadas;
* los ADR aceptados;
* los contratos públicos;
* las releases;
* el código;
* las pruebas;
* el historial Git;
* la documentación operativa oficial.

Toda afirmación contenida aquí debe poder verificarse contra la rama `main` del repositorio oficial.

Cuando este documento contradiga una fuente normativa o una evidencia más reciente del repositorio, prevalecerá la fuente oficial.

---

## 2. Identidad del proyecto

**Nombre:** Malāk
**Nombre histórico:** Jarvis
**Naturaleza:** plataforma cognitiva personal ejecutada localmente
**Estado de desarrollo:** Foundation Implementation
**Versión nominal actual:** `v0.6.0-alpha`

Malāk está diseñado para ser:

* modular;
* gobernable;
* extensible;
* auditable;
* local-first;
* agnóstico respecto del modelo o proveedor LLM;
* controlado por el propietario;
* evolucionado mediante cambios pequeños, probados y reversibles.

---

## 3. Repositorio oficial

**Repositorio:**

```text
https://github.com/Aranwill/jarvis
```

**Ruta local conocida:**

```text
D:\Ollama\jarvis
```

**Rama permanente y oficial:**

```text
main
```

La rama `main` es:

* la rama predeterminada del repositorio;
* la única rama permanente;
* la fuente del baseline operativo actual;
* la referencia obligatoria para documentación, código y validaciones.

Las ramas temporales de sprint, feature, corrección o documentación deben eliminarse después de su integración y validación, salvo decisión explícita en contrario.

No debe utilizarse ninguna rama histórica como fuente del estado actual.

---

## 4. Referencia Git verificada

**Último commit remoto verificado al revisar este documento:**

```text
fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
```

**Descripción:**

```text
Merge pull request #13 from Aranwill/feature/sprint-7.3-conversation-provider-boundary
```

Este commit cerró el Sprint 7.3 — Conversation Provider Boundary Stabilization e incorporó la estabilización de la frontera del subsistema conversacional.

El hash registrado aquí es una referencia temporal y deberá actualizarse cuando cambie materialmente `HEAD`.

---

## 5. Baseline operativo actual

**Último sprint cerrado:**

```text
Sprint 7.3 — Conversation Provider Boundary Stabilization
```

El bloque 7.x contiene actualmente los siguientes sprints cerrados:

| Sprint | Estado  | Resultado                                                             |
| ------ | ------- | --------------------------------------------------------------------- |
| 7.0    | Cerrado | CLI mínima con `MockLLMRuntime`                                       |
| 7.1    | Cerrado | Composición de CLI con `OllamaRuntime` mediante configuración externa |
| 7.2    | Cerrado | Contrato estructural `RuntimeMetricSink` de solo escritura            |
| 7.3    | Cerrado | Estabilización de la frontera `ConversationService`–Provider–Runtime  |

No existe todavía un siguiente sprint aprobado automáticamente.

El cierre de un sprint no autoriza el inicio del siguiente.

---

## 6. Estado de validación

**Suite validada al cierre del Sprint 7.3:**

```text
74 passed
```

Validaciones documentadas:

```powershell
python -m pytest -q
python -m compileall src tests
git diff --check
```

Resultado registrado:

* 74 pruebas aprobadas;
* compilación validada sin errores;
* diff validado sin errores de formato;
* documentación sincronizada para el alcance del sprint.

Este resultado representa el estado documentado del baseline remoto.

Antes de una nueva implementación deberá verificarse nuevamente en el entorno local:

* rama actual;
* sincronización con remoto;
* working tree;
* versión de Python;
* dependencias;
* suite completa;
* compilación;
* formato del diff.

---

## 7. Estado arquitectónico general

Malāk mantiene actualmente dos rutas diferenciadas.

### 7.1 Pipeline Kernel–Planner–Capability

Ruta arquitectónica interna destinada al procesamiento controlado mediante:

* Kernel;
* Planner;
* Capability Registry;
* Capabilities.

### 7.2 Subsistema conversacional de CLI

Ruta técnica actual:

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

Estas rutas permanecen separadas.

Todavía no existe una integración formal validada entre:

```text
Kernel.receive
```

y:

```text
ConversationService
```

La CLI técnica no representa todavía el pipeline cognitivo completo de Malāk.

---

## 8. Componentes implementados

### 8.1 Kernel MVP

Estado:

```text
implementado
```

Características:

* Kernel mínimo;
* desacoplado de runtimes concretos;
* desacoplado de proveedores concretos;
* desacoplado de modelos concretos;
* sin configuración operativa de runtime incorporada;
* sin responsabilidades de almacenamiento de métricas;
* sin acceso directo a Internet;
* sin ejecución autónoma.

---

### 8.2 Planner MVP

Estado:

```text
implementado
```

Características:

* planificación mínima;
* subordinación al Kernel y a la gobernanza;
* sin autoridad autónoma;
* sin agentes avanzados;
* sin ejecución externa.

---

### 8.3 Capability Registry

Estado:

```text
implementado
```

Función:

* registrar Capabilities;
* resolver capacidades de manera desacoplada;
* preservar separación entre Kernel y funcionalidad concreta.

La existencia del Registry no justifica incorporar Capabilities artificiales.

Toda nueva Capability deberá añadir una función real, necesaria y permanente.

---

### 8.4 EchoCapability

Estado:

```text
implementado
```

Función:

* Capability mínima del baseline;
* validación del flujo Kernel–Planner–Capability;
* soporte para pruebas deterministas.

---

### 8.5 Conversation Contract

Componentes:

* `ConversationRequest`;
* `ConversationResponse`.

Estado:

```text
implementado
```

Función:

* definir contratos conversacionales centrales;
* desacoplar servicios, providers y runtimes;
* evitar dependencia de proveedores concretos.

---

### 8.6 LLMRuntime

Estado:

```text
implementado
```

Función:

* único punto de abstracción para runtimes LLM;
* preservar Runtime Independence;
* evitar acoplamiento del Kernel a Ollama u otro proveedor.

---

### 8.7 MockLLMRuntime

Estado:

```text
implementado
```

Uso:

* desarrollo;
* tests;
* validaciones deterministas;
* ejecución sin servicios externos.

Es el runtime predeterminado de la CLI.

---

### 8.8 OllamaRuntime

Estado:

```text
implementado
```

Características:

* integración local con Ollama;
* composición externa al Kernel;
* configuración mediante variables de entorno;
* soporte para inyección opcional de métricas;
* pruebas deterministas sin necesidad obligatoria de un servicio Ollama activo.

La integración real fue validada con:

```text
qwen3.5:9b
```

---

### 8.9 Conversation Provider

Componentes implementados:

* `ConversationProvider`;
* `RuntimeConversationProvider`;
* `ConversationProviderRegistry`;
* `ConversationProviderNotFoundError`;
* `ConversationService`.

Función:

* separar el servicio conversacional del runtime concreto;
* adaptar solicitudes conversacionales a un `LLMRuntime` inyectado;
* registrar y resolver providers mediante nombres normalizados;
* rechazar nombres vacíos y registros duplicados;
* encapsular el `KeyError` interno mediante `ConversationProviderNotFoundError`;
* preservar una responsabilidad mínima en `ConversationService`;
* componer la CLI sin modificar el Kernel.

Límites vigentes:

* `RuntimeConversationProvider` no selecciona modelos ni configura runtimes;
* `ConversationService` no implementa retries, logging, métricas, persistencia ni gobernanza;
* no existe integración formal entre `ConversationService` y `Kernel.receive`;
* el Sprint 7.3 no incorporó nuevas Capabilities.

---

### 8.10 CLI técnica

Estado:

```text
implementada
```

La CLI permite:

* ingresar mensajes por terminal;
* construir un `ConversationRequest`;
* seleccionar runtime mediante configuración externa;
* utilizar `MockLLMRuntime`;
* utilizar `OllamaRuntime`;
* resolver providers;
* delegar mediante `ConversationService`;
* mostrar `ConversationResponse`;
* consultar `status`;
* consultar `help`;
* controlar entradas vacías;
* controlar errores del runtime;
* finalizar mediante comandos, EOF o `Ctrl + C`.

Comandos documentados:

```text
help
ayuda
status
exit
quit
salir
```

---

### 8.11 Configuración externa de la CLI

Variables admitidas:

| Variable                |                      Obligatoria | Valor predeterminado     |
| ----------------------- | -------------------------------: | ------------------------ |
| `MALAK_RUNTIME`         |                               No | `mock`                   |
| `MALAK_OLLAMA_MODEL`    | Sí cuando el runtime es `ollama` | Sin valor                |
| `MALAK_OLLAMA_BASE_URL` |                               No | `http://localhost:11434` |

Valores admitidos para `MALAK_RUNTIME`:

```text
mock
ollama
```

La configuración permanece en la frontera de aplicación y no debe introducirse en el Kernel.

---

### 8.12 Runtime Metrics

Estado:

```text
implementación inicial validada
```

Incluye:

* `RuntimeMetricSample`;
* almacenamiento de métricas en memoria;
* almacenamiento JSONL;
* perfilado de métricas;
* soporte para observación de tiempos del runtime;
* base para análisis posterior de comportamiento.

La infraestructura de métricas no posee autoridad para modificar automáticamente:

* timeout;
* modelo;
* `keep_alive`;
* configuración;
* permanencia en VRAM;
* selección de runtime.

---

### 8.13 RuntimeMetricSink

Estado:

```text
implementado y validado en Sprint 7.2
```

`RuntimeMetricSink` es un `Protocol` estructural mínimo.

Expone únicamente:

```python
append(sample: RuntimeMetricSample) -> None
```

Es un contrato intencionalmente de solo escritura.

No expone:

* lectura;
* filtrado;
* perfilado;
* recomendaciones;
* configuración;
* persistencia concreta;
* autoajuste.

`OllamaRuntime` depende de `RuntimeMetricSink` y no de un store concreto.

Implementaciones estructuralmente compatibles:

* `InMemoryRuntimeMetricStore`;
* `JsonlRuntimeMetricStore`.

---

### 8.14 AKS Engineering Knowledge Foundation

Estado:

```text
implementado en su alcance fundacional
```

Incluye una estructura inicial para:

* estándares;
* patrones;
* recetas;
* ejemplos;
* tecnologías;
* learning packs;
* glosario;
* referencias.

No debe confundirse con:

* el Project Vault externo;
* el futuro RAG;
* GraphRAG;
* memoria cognitiva;
* un sistema de autoridad automática.

---

### 8.15 Development Framework

Estado:

```text
implementado
```

Incluye documentación para:

* preparación del entorno;
* disciplina de desarrollo;
* validación;
* integración;
* checklist;
* trazabilidad.

Versión de Python documentada como validada:

```text
Python 3.12.10
```

---

## 9. Principios vigentes

Malāk mantiene como principios centrales:

* Kernel First;
* Capability First;
* Runtime Independence;
* Human in Control;
* Zero Trust interno;
* Defense in Depth;
* configuración externa al Kernel;
* cambios pequeños;
* pruebas deterministas;
* trazabilidad;
* reversibilidad;
* separación entre medición, recomendación y configuración efectiva;
* arquitectura antes que implementación;
* validación antes de incorporar al baseline.

---

## 10. Cuatro preguntas obligatorias

Toda propuesta deberá responder:

1. ¿Respeta el Blueprint?
2. ¿Respeta la Constitución Cognitiva?
3. ¿Respeta la Gobernanza?
4. ¿Simplifica o mantiene simple el Kernel?

Una respuesta negativa o incierta impide la incorporación automática del cambio.

---

## 11. Restricciones vigentes

### 11.1 Kernel

El Kernel no debe:

* depender de Ollama;
* depender de un proveedor LLM concreto;
* depender de un modelo concreto;
* administrar variables de entorno del runtime;
* almacenar métricas;
* generar recomendaciones de rendimiento;
* aplicar configuración automática;
* ejecutar herramientas externas;
* consumir Internet;
* absorber lógica de negocio;
* asumir funciones de auditoría;
* asumir autorización;
* incorporar dependencias no aprobadas.

---

### 11.2 Capabilities

No deben crearse Capabilities únicamente para:

* demostrar routing;
* validar múltiples entradas;
* aumentar cobertura;
* completar una secuencia prevista;
* probar infraestructura interna;
* incorporar ejemplos sin utilidad permanente.

La infraestructura debe validarse mediante:

* tests;
* fixtures;
* dobles;
* contratos;
* integración controlada.

---

### 11.3 Seguridad

Antes de introducir:

* agentes;
* herramientas externas;
* automatización del sistema operativo;
* navegación;
* mensajería externa;
* memoria sensible;
* Capabilities de alto riesgo;

deben aprobarse e implementarse los fundamentos de seguridad y gobernanza correspondientes.

---

### 11.4 Tooling

Ruff no forma parte del baseline actual.

Su evaluación permanece reservada para una futura fase formal de Development Tooling que deberá considerar conjuntamente:

* Ruff;
* mypy;
* `pyproject.toml`;
* dependencias de desarrollo;
* ejecución local;
* CI;
* reglas reproducibles.

No debe instalarse o incorporarse improvisadamente.

---

## 12. Fuera de alcance actual

Todavía no forman parte del baseline operativo:

* integración formal entre `Kernel.receive` y `ConversationService`;
* memoria conversacional;
* historial persistente de conversaciones;
* agentes;
* herramientas externas;
* navegación;
* GraphRAG;
* interfaz gráfica;
* ejecución autónoma;
* aplicación automática de recomendaciones;
* modificación automática de timeout;
* modificación automática del modelo;
* modificación automática de `keep_alive`;
* configuración de persistencia de métricas desde la CLI;
* campañas formales de calibración;
* comparación automática de modelos;
* autoajuste.

---

## 13. Estado del roadmap

La hoja de ruta oficial se encuentra clasificada como:

```text
borrador, derivada, informativa y no normativa
```

No aprueba arquitectura ni autoriza implementaciones.

Propuestas actualmente documentadas como no aprobadas:

| Propuesta                                   | Estado      |
| ------------------------------------------- | ----------- |
| Sprint 7.3                                  | No aprobado |
| Consolidación de logs, métricas y auditoría | No aprobada |
| Security Control Plane Foundation           | No aprobada |
| Preparación del AKS para GraphRAG           | No aprobada |
| Validación de baseline y release interna    | No aprobada |

La tabla no establece una secuencia obligatoria.

El próximo sprint deberá seleccionarse únicamente después de:

1. inspeccionar el baseline;
2. revisar código, tests y documentación;
3. identificar una necesidad real;
4. justificar utilidad;
5. definir alcance y fuera de alcance;
6. evaluar riesgos, dependencias y rollback;
7. responder las cuatro preguntas obligatorias;
8. debatir el plan;
9. obtener aprobación explícita del propietario.

---

## 14. Project Context & Knowledge Governance Foundation

Estado:

```text
aprobada e iniciada fuera del repositorio principal
```

Ubicación local:

```text
D:\Ollama\malak-project-vault
```

Objetivos:

* mantener un contexto de sesión verificable;
* evitar pérdida de información entre sesiones;
* preservar autoridad documental;
* preparar Obsidian como interfaz de conocimiento;
* preparar un RAG externo;
* sentar bases para auditoría arquitectónica y de seguridad.

Secuencia conceptual aprobada:

1. Project Context Foundation;
2. Obsidian Knowledge Foundation;
3. Session Context Generator;
4. External Project RAG;
5. Architecture & Security Auditor Foundation.

Esta iniciativa:

* no forma parte del Kernel;
* no reemplaza el repositorio;
* no reemplaza la documentación normativa;
* no posee autoridad para modificar Malāk;
* debe operar de manera independiente.

---

## 15. Estado actual del Project Vault

Estado verificado durante la creación inicial:

* estructura de carpetas creada;
* `VAULT_GOVERNANCE.md` creado;
* `DOCUMENT_AUTHORITY_MODEL.md` creado;
* `CONTENT_LIFECYCLE.md` creado;
* `CURRENT_BASELINE.md` en actualización;
* Obsidian todavía no configurado;
* Git del Vault todavía no inicializado;
* RAG no implementado;
* embeddings no generados;
* índices no creados;
* auditor no implementado.

---

## 16. Fuentes oficiales principales

Documentación relevante verificada en `main`:

```text
README.md
docs/architecture/blueprint.md
docs/architecture/kernel.md
docs/governance/cognitive_constitution.md
docs/governance/governance_constitution.md
docs/development/development_environment.md
docs/project/implementation_roadmap.md
docs/project/sprints/SPRINT-7.0.md
docs/project/sprints/SPRINT-7.1.md
docs/project/sprints/SPRINT-7.2.md
```

Las fichas de sprints futuros no constituyen aprobación para implementarlos.

---

## 17. Verificación obligatoria al iniciar una sesión

Antes de modificar Malāk, verificar en el repositorio local:

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
* working tree limpio antes de iniciar;
* repositorio sincronizado;
* suite en verde;
* compilación sin errores;
* diff sin errores.

Los resultados deberán incorporarse al contexto de sesión como evidencia temporal, no como memoria permanente incuestionable.

---

## 18. Regla de actualización

Este documento deberá actualizarse cuando ocurra:

* cambio material de `HEAD`;
* cierre de sprint;
* merge;
* nueva release;
* modificación de contratos públicos;
* aceptación de ADR;
* cambio de rama permanente;
* cambio de suite;
* incorporación o retiro de componentes;
* cambio arquitectónico;
* certificación de un nuevo baseline;
* cambio material en gobernanza.

Toda actualización debe basarse primero en evidencia del repositorio.

---

## 19. Incertidumbres y límites

Este documento no confirma por sí mismo:

* el estado del working tree local;
* pruebas ejecutadas después del último commit remoto;
* cambios locales sin push;
* servicios Ollama activos;
* modelos instalados actualmente;
* estado del hardware;
* decisiones conversadas pero no formalizadas;
* aprobación de un próximo sprint.

Estos puntos deberán verificarse en el momento correspondiente.

---

## 20. Principios rectores

> El baseline describe lo que existe y fue validado.

> El roadmap describe posibilidades y propuestas, no autorizaciones.

> La memoria facilita la continuidad; el repositorio determina el estado real.

> La implementación demuestra existencia. La gobernanza determina legitimidad.

> Ningún sprint comienza sin revisión y aprobación explícita.
