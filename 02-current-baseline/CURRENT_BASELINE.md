---

id: MALAK-BASELINE-CURRENT
title: Malāk Current Baseline
type: baseline-summary
status: active
authority_level: baseline
authority_rank: 5
version: 1.1
created: 2026-07-20
last_reviewed: 2026-08-14
source_of_truth: repository
source_repository: Aranwill/jarvis
source_branch: main
source_commit: c65bff257f877460c153583bfcd9819224ca0f5c
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
---

# Malāk Current Baseline

<!-- MALAK_VAULT_SYNC:START -->
## Proyección automática de sincronización

> [!warning] Estado derivado pendiente de revisión
> Este bloque fue generado de forma determinista a partir de
> `Aranwill/jarvis/main`. No aprueba decisiones, no cierra
> sprints y no reemplaza la revisión humana del documento.

- **Run ID:** `20260812T230820718673Z_cdc0f1d7_d28990bd`
- **HEAD oficial observado:** `cdc0f1d78d1e896400f81a609df16aaa90d25313`
- **Commit previamente observado:** `7d6feaaaebb53b3c12bc2d1a170be85008ba9e5e`
- **Generado:** `2026-08-12T23:08:20.718673+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.5.md`
- **Título declarado:** Sprint 7.5 — Base del plano de control de seguridad
- **Estado declarado:** `cerrado`
- **`as_of_commit` declarado:** `62bdc11c3ce16cb2cb54bb61bddfab4e39d689a8`

### Commits oficiales observados

- cdc0f1d78d1e896400f81a609df16aaa90d25313	Merge pull request #34 from Aranwill/docs/reconcile-project-context-after-idea-024
- 167f3d8fb86671cbd119fd17e3ed27da8f7d740f	docs(project): reconcile context after idea 024
- 48d6ea2de9d7bd60495208b77d81175415bc3350	Merge pull request #33 from Aranwill/docs/add-governed-mission-orchestration-idea
- 170dd31e67c3199ed6f43c114ff9b45cc1778ee8	docs(ideas): add governed mission orchestration foundation

### Evidencia que originó esta proyección

- `baseline-source-change` por `docs/project/project_context.md`
- `baseline-source-change` por `documents/projects/jarvis/ideas.md`
<!-- MALAK_VAULT_SYNC:END -->

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
c65bff257f877460c153583bfcd9819224ca0f5c
```

**Descripción:**

```text
Merge pull request #36 from Aranwill/docs/concept-governance-clarification
```

La PR #36 incorporó una aclaración documental en
docs/project/concepts/README.md sobre la naturaleza derivada de las
proyecciones del Project Vault. No introdujo cambios de código, contratos,
Kernel, Planner, runtime ni comportamiento de seguridad.

El Sprint 7.5 permanece cerrado y no existe ningún sprint posterior autorizado.

El hash registrado aquí es una referencia temporal y deberá actualizarse
cuando cambie materialmente `HEAD`.

---

## 5. Baseline operativo actual

**Último sprint formalmente cerrado:**

```text
Sprint 7.5 — Security Control Plane Foundation
```

**Sprint actualmente autorizado:**

```text
Ninguno.
```

El bloque 7.x presenta el siguiente estado:

| Sprint | Estado  | Resultado                                                             |
| ------ | ------- | --------------------------------------------------------------------- |
| 7.0    | Cerrado | CLI mínima con `MockLLMRuntime`                                       |
| 7.1    | Cerrado | Composición de CLI con `OllamaRuntime` mediante configuración externa |
| 7.2    | Cerrado | Contrato estructural `RuntimeMetricSink` de solo escritura            |
| 7.3    | Cerrado | Estabilización de la frontera `ConversationService`–Provider–Runtime  |
| 7.4    | Cerrado | Eventos operativos, correlación desde la CLI y sincronización gobernada del Vault |
| 7.5    | Cerrado | Security Control Plane Foundation; autorización, PDP, PEP, auditoría y revisión integral completados |

El Sprint 7.5 fue aprobado explícitamente por el propietario y quedó
cerrado después de completar seis incrementos pequeños, revisables y
reversibles.

El cierre integral confirmó:

- contratos de autorización estables;
- Policy Decision Point mínimo, determinista y fail-closed;
- Policy Enforcement Point separado de la lógica de negocio del Kernel;
- evidencia de auditoría estructurada e integrada de forma fail-closed;
- separación entre decisión, enforcement, auditoría y operación protegida;
- control humano y denegación por defecto preservados;
- ausencia de rutas operativas reales habilitadas por este sprint;
- ausencia de defectos bloqueantes durante la revisión integral;
- 183 pruebas específicas de seguridad aprobadas;
- 304 pruebas totales aprobadas;
- `compileall`: PASS;
- `git diff --check`: PASS;
- Kernel, Planner, CLI, runtimes y Capability Registry intactos.

El Incremento 6 no requirió cambios funcionales.

No existe ningún sprint posterior autorizado automáticamente por el
cierre del Sprint 7.5.

El Secure Context Manager, persistencia de auditoría, identidad
criptográfica, TTL, nonce, prevención persistente de replay, agentes,
navegación y rutas operativas reales permanecen fuera de alcance.

---

## 5.1 Planificación futura aprobada sin implementación

La PR #24 incorporó al roadmap oficial:

- `Segmented Domain Governance Foundation`;
- `Knowledge Intake & External Evidence Governance`;
- `Security Learning, Adversarial Evaluation & Deception`.

También registró investigación externa, presencia pública controlada,
escalado vertical y flotas de agentes.

Estado común:

```text
planificación futura aprobada
diseño detallado no aprobado
implementación no aprobada
sin número de sprint asignado
```

No forman parte del baseline operativo:

- Domain Packs;
- navegación externa;
- agentes autónomos;
- sandboxes avanzados;
- honeypots públicos;
- gemelo adversarial;
- beta pública;
- respuesta ofensiva externa.

---

## 6. Estado de validación

**Última suite integral documentada:**

```text
304 passed
```

Validaciones documentadas:

```powershell
python -m pytest -q
python -m compileall src tests
git diff --check
```

Resultado registrado:

* 19 pruebas específicas del Incremento 4 aprobadas;
* 304 pruebas totales aprobadas;
* compilación validada sin errores;
* diff validado sin errores de formato;
* Kernel, Planner y runtimes sin cambios;
* ningún LLM participa en decisiones de autorización.

La validación integral fue ejecutada sobre:

```text
b4d1d512fe953d593608391390f82ab500fdc9d6
```

La suite integral fue reejecutada sobre el HEAD verificado durante la
auditoría de cierre del 2026-07-31 y registró `304 passed`. La validación
anterior de `244 passed` sobre
`30b05587839cdac914e7ee31755bb5c0540862c1` se conserva únicamente como
evidencia histórica.

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

### 8.14 Operational Events

Estado:

```text
implementación técnica integrada en Sprint 7.4
```

Componentes:

* `OperationalEvent`;
* `OperationalEventSink`;
* `InMemoryOperationalEventStore`;
* `JsonlOperationalEventStore`.

Propiedades:

* contrato inmutable;
* allowlist estricta de seis campos;
* timestamps UTC;
* sink de solo escritura;
* stores separados de las métricas;
* persistencia JSONL append-only;
* límite de 4096 bytes por línea;
* errores de persistencia explícitos;
* ausencia de dependencias externas.

Los eventos no incorporan prompts, respuestas, contenido
conversacional, secretos, credenciales, modelos, proveedores ni
excepciones.

La CLI genera exclusivamente el `request_id` y lo utiliza para
correlacionar:

```text
conversation.started
conversation.succeeded
conversation.failed
```

`ConversationRequest`, `ConversationResponse`, Kernel, Planner y
`ConversationService` permanecen intactos.

La auditoría de seguridad no fue implementada.

---

### 8.15 Contratos fundamentales de autorización

Estado:

```text
implementados e integrados en Sprint 7.5, Incremento 1
```

Componentes públicos expuestos mediante `malak.security`:

* `PermissionScope`;
* `SecurityContext`;
* `AuthorizationRequest`;
* `AuthorizationDecision`.

Propiedades verificadas:

* contratos inmutables;
* validación estricta y normalización de texto requerido;
* `AuthorizationRequest` relaciona contexto y permiso;
* identificador trazable y fecha con zona horaria;
* `AuthorizationDecision` mantiene resultado binario explícito;
* solicitud y decisión permanecen separadas;
* no existe decisión de autorización basada en LLM;
* Kernel, Planner y runtimes permanecen intactos.

Fuentes:

```text
src/malak/security/contracts.py
src/malak/security/__init__.py
tests/test_authorization_contracts.py
docs/project/sprints/SPRINT-7.5.md
```

El PDP mínimo está implementado e integrado en Sprint 7.5, Incremento
3. El PEP inicial está implementado e integrado como Incremento 4.
La evidencia de auditoría de autorización y su integración fail-closed
con el PEP fueron incorporadas mediante las PR #22 y #23. El Incremento 5 quedó integrado. El Incremento 6 completó la revisión
integral y el cierre del Sprint 7.5 sin requerir cambios funcionales.
El cierre no autoriza automáticamente ningún sprint posterior.

---

### 8.16 Policy Enforcement Point inicial

Estado:

```text
implementado e integrado en Sprint 7.5, Incremento 4
```

Componentes públicos expuestos mediante `malak.security`:

* `PolicyEnforcementPoint`;
* `StrictPolicyEnforcementPoint`;
* `ProtectedOperation`;
* `AuthorizationDeniedError`;
* `AuthorizationEnforcementError`.

Propiedades verificadas:

* el PEP consulta directamente al PDP confiable inyectado;
* la API no acepta una `AuthorizationDecision` aportada por el llamador;
* la decisión debe corresponder al `request_id` de la solicitud;
* denegaciones, fallos y respuestas inválidas bloquean la operación;
* una autorización válida permite una única ejecución;
* los errores de la operación se propagan sin reintento;
* no existe integración con operaciones reales;
* Kernel, Planner, CLI y runtimes permanecen intactos;
* la auditoría de autorización está integrada mediante las PR #22 y #23;

Fuentes:

```text
src/malak/security/pep.py
src/malak/security/__init__.py
tests/test_policy_enforcement_point.py
docs/architecture/adr/ADR-002-policy-enforcement-boundary.md
docs/project/sprints/SPRINT-7.5.md
```

---

### 8.17 AKS Engineering Knowledge Foundation

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

### 8.18 Development Framework

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
* Secure Context Manager;

---

## 13. Estado del roadmap

La hoja de ruta oficial se encuentra clasificada como:

```text
activa, derivada, informativa y no normativa
```

No aprueba arquitectura ni autoriza implementaciones.

Estado vigente:

| Línea                                       | Estado      |
| ------------------------------------------- | ----------- |
| Consolidación de logs, métricas y auditoría | Sprint 7.4 cerrado |
| Security Control Plane Foundation | Sprint 7.5 cerrado |
| Preparación del AKS para GraphRAG           | No aprobada |
| Validación de baseline y release interna    | No aprobada |

El Sprint 7.5 quedó cerrado después de completar y validar sus seis
incrementos. El cierre del sprint no autoriza automáticamente ningún
sprint posterior.

Las líneas marcadas como no aprobadas no poseen autorización de
implementación.

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

Estado verificado después de la reconciliación gobernada de la PR #31:

```text
Repositorio: Aranwill/malak-project-vault
Rama oficial: main
HEAD verificado: e9165357160386fea59706d9af4cd7504f539219
PR de sincronización: #31
Estado de la PR: integrada
Rama de propuesta: agent/vault-sync-c65bff25
Rama remota de propuesta: eliminada después del merge
Malāk observado: c65bff257f877460c153583bfcd9819224ca0f5c
Run ID: 20260815T010848675956Z_c65bff25_30336572
Resultado del agente: pass
Propuesta reconciliada por humano: sí
accept-proposal: completado
Steady state posterior: pass
Merge automático autorizado: no
```

La PR #31 fue producida mediante `controlled-proposal`, revisada y mergeada
exclusivamente bajo autoridad humana. El agente no escribió directamente
sobre `main` del Vault ni modificó `Aranwill/jarvis`.

La reconciliación automática actualizó únicamente la proyección gestionada
de los documentos candidatos y preservó el frontmatter y el contenido humano.
La presente revisión manual corrige los metadatos y referencias operativas
activas que quedaron fuera de la autoridad del agente.

### Registro histórico — propuesta de sincronización PR #10

Estado base verificado al preparar aquella propuesta:

```text
Repositorio: Aranwill/malak-project-vault
Rama: main
HEAD base: b20482cff9f104c86d7967b393381021b21ec629
Rama de propuesta: agent/vault-sync-4afeed44
PR draft: #10
Working tree inicial: limpio
```

La navegación, gobernanza, índices, snapshots y respaldo remoto del
Vault están operativos.

La propuesta de la PR #10 fue producida por una ejecución manual bajo
demanda del agente. Este bloque se conserva como evidencia histórica y
no representa la propuesta ni el HEAD vigentes.

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
docs/project/sprints/SPRINT-7.3.md
docs/project/sprints/SPRINT-7.4.md
docs/project/sprints/SPRINT-7.5.md
src/malak/security/contracts.py
src/malak/security/__init__.py
tests/test_authorization_contracts.py
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
