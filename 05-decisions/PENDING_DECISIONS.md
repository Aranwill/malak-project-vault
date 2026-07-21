---

id: MALAK-PENDING-DECISIONS
title: Malāk Pending Decisions
type: decision-register
status: active
authority_level: proposal
authority_rank: 9
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-21
source_of_truth: repository-and-owner-decisions
source_repository: Aranwill/jarvis
source_branch: main
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: proposals
--------------------------

# Malāk Pending Decisions

## 1. Propósito

Este documento registra decisiones abiertas que requieren análisis, debate o aprobación explícita del propietario.

Su objetivo es:

* evitar que asuntos pendientes se pierdan entre sesiones;
* diferenciar decisiones de tareas;
* impedir que una propuesta se interprete como aprobación;
* conservar contexto, alternativas, riesgos y dependencias;
* facilitar la preparación de futuras sesiones;
* mantener trazabilidad sobre decisiones postergadas.

Este documento no autoriza implementaciones.

---

## 2. Regla general

Una decisión pendiente representa un asunto abierto.

No representa:

* una tarea asignada;
* un sprint aprobado;
* una modificación autorizada;
* una prioridad definitiva;
* una obligación de implementación;
* una aceptación arquitectónica automática.

Toda decisión deberá resolverse mediante aprobación explícita del propietario o mediante el proceso formal correspondiente.

---

## 3. Estados permitidos

Las decisiones podrán utilizar los siguientes estados:

```text
open
under_review
deferred
accepted
rejected
superseded
closed
```

### `open`

El asunto fue identificado, pero todavía no fue evaluado suficientemente.

### `under_review`

Existe una evaluación activa con alternativas, evidencia o discusión.

### `deferred`

La decisión continúa siendo válida, pero fue postergada.

### `accepted`

Existe una resolución aprobada.

Una decisión aceptada deberá formalizarse en:

* ADR;
* roadmap;
* ficha de sprint;
* política;
* baseline;
* documento arquitectónico;

según corresponda.

### `rejected`

La propuesta fue descartada.

### `superseded`

La decisión fue reemplazada por otra posterior.

### `closed`

El asunto fue resuelto y trasladado al artefacto oficial correspondiente.

---

## 4. Regla de cierre

Una decisión no debe permanecer como `accepted` indefinidamente.

Después de su aprobación debe:

1. identificarse el documento oficial afectado;
2. registrarse la decisión formal;
3. actualizarse el roadmap o baseline cuando corresponda;
4. indicarse la evidencia;
5. cambiarse su estado a `closed`.

La conversación donde se aprobó una decisión no sustituye su formalización.

---

# Decisiones abiertas

## DEC-PEND-001 — Selección del próximo sprint

**Estado:**

```text
open
```

**Prioridad:**

```text
alta
```

**Contexto:**

El baseline operativo actual corresponde al cierre del Sprint 7.3 — Conversation Provider Boundary Stabilization.

Los Sprints 7.0, 7.1, 7.2 y 7.3 están cerrados.

Baseline vigente:

```text
fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
```

Validación documentada:

```text
74 passed
```

No existe actualmente un próximo sprint aprobado.

**Decisión requerida:**

Determinar qué necesidad real de Malāk debe abordarse a continuación.

**Alternativas conocidas:**

* evaluar la delimitación entre logs, métricas y auditoría;
* evaluar el momento de implementación del Security Control Plane Foundation;
* continuar tareas documentales gobernadas del Project Vault;
* evaluar una necesidad detectada mediante relevamiento del baseline;
* no iniciar un nuevo sprint hasta completar una revisión adicional.

**Criterios obligatorios:**

* necesidad real;
* alineación con Blueprint;
* alineación con Constitución Cognitiva;
* alineación con Gobernanza;
* mantenimiento de un Kernel simple;
* alcance corto;
* reversibilidad;
* ausencia de expansión prematura;
* utilidad permanente.

**Riesgo principal:**

Seleccionar un sprint por continuidad numérica y no por necesidad arquitectónica.

**Próxima acción permitida:**

Relevamiento del baseline y presentación de alternativas.

**Acción no permitida:**

Crear una rama o modificar el repositorio oficial antes de una aprobación explícita.

---

## DEC-PEND-002 — Redefinición del Sprint 7.3

**Estado:**

```text
closed
```

**Prioridad histórica:**

```text
media
```

**Resolución:**

El identificador Sprint 7.3 fue redefinido alrededor de una necesidad arquitectónica real:

```text
Conversation Provider Boundary Stabilization
```

La implementación:

* reemplazó `MockConversationProvider` por `RuntimeConversationProvider`;
* estabilizó `ConversationProviderRegistry`;
* incorporó `ConversationProviderNotFoundError`;
* delimitó la responsabilidad de `ConversationService`;
* no incorporó una Capability artificial;
* no modificó Kernel, Planner ni el contrato `Capability`;
* fue integrada mediante el PR #13;
* produjo el baseline `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`;
* fue validada con 74 pruebas aprobadas.

**Evidencia:**

* PR #13;
* merge commit `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`;
* `04-sprints/SPRINT-7.3-CLOSURE.md`;
* documentación oficial del Sprint 7.3 en `Aranwill/jarvis/main`.

**Resultado:**

La propuesta histórica de una segunda Capability no fue adoptada.

La decisión queda cerrada y no autoriza trabajo posterior.

---

## DEC-PEND-003 — Alcance de logs, métricas y auditoría

**Estado:**

```text
open
```

**Prioridad:**

```text
media
```

**Contexto:**

Malāk posee infraestructura inicial de métricas de runtime:

* `RuntimeMetricSample`;
* `RuntimeMetricSink`;
* `InMemoryRuntimeMetricStore`;
* `JsonlRuntimeMetricStore`;
* perfilado de métricas.

No debe asumirse que logs, métricas, telemetría, seguridad y auditoría sean una única responsabilidad.

**Decisión requerida:**

Definir si deben permanecer como subsistemas separados o compartir infraestructura limitada.

**Preguntas abiertas:**

* ¿Qué eventos deben registrarse?
* ¿Qué métricas son operativas?
* ¿Qué información es evidencia de auditoría?
* ¿Qué datos pueden ser sensibles?
* ¿Qué retención resulta necesaria?
* ¿Qué responsabilidades corresponden a seguridad?
* ¿Qué contratos deben mantenerse separados?
* ¿Debe existir persistencia configurable?
* ¿Quién puede leer cada clase de información?
* ¿Qué información debe ser inmutable?

**Alternativas iniciales:**

1. mantener métricas, logs y auditoría separados;
2. compartir almacenamiento, pero no contratos;
3. compartir un envelope de eventos;
4. crear una capa común de observabilidad;
5. diferir la decisión hasta Security Control Plane.

**Riesgos:**

* acoplamiento excesivo;
* filtración de datos;
* pérdida de trazabilidad;
* complejidad prematura;
* confusión entre observación y autoridad.

---

## DEC-PEND-004 — Momento de implementación del Security Control Plane

**Estado:**

```text
open
```

**Prioridad:**

```text
alta antes de capacidades sensibles
```

**Contexto:**

Security Control Plane Foundation está aceptada conceptualmente como línea futura.

No existe todavía un sprint aprobado.

Debe implementarse antes de:

* herramientas externas;
* navegación;
* automatización del sistema operativo;
* mensajería;
* memoria sensible;
* agentes;
* ejecución de acciones de alto riesgo.

**Decisión requerida:**

Determinar en qué momento del roadmap debe convertirse en un sprint aprobado.

**Dependencias por revisar:**

* contratos actuales;
* boundaries del Kernel;
* modelo de identidad;
* modelo de permisos;
* eventos de auditoría;
* necesidad de `SecurityContext`;
* integración con capabilities;
* separación entre PDP y PEP.

**Alcance conceptual mínimo:**

* `AuthorizationRequest`;
* `AuthorizationDecision`;
* `SecurityContext`;
* `PermissionScope`;
* Policy Decision Point determinista;
* Policy Enforcement Point;
* denegación por defecto;
* ausencia de LLM en decisiones de autorización.

**Riesgo principal:**

Expandir capacidades antes de establecer límites de autoridad.

---

## DEC-PEND-005 — Relación entre Kernel y ConversationService

**Estado:**

```text
closed
```

**Prioridad histórica:**

```text
media
```

**Contexto:**

El pipeline Kernel–Planner–Capability y el subsistema conversacional de CLI son rutas separadas:

```text
Kernel
→ Planner
→ Capability Registry
→ Capability
```

y:

```text
CLI
→ ConversationService
→ ConversationProviderRegistry
→ RuntimeConversationProvider
→ LLMRuntime
```

**Resolución:**

No se aprueba ni se propone una integración formal entre `Kernel.receive` y `ConversationService`.

El cierre del Sprint 7.3 preserva expresamente esta separación.

El Kernel no debe depender de:

* `ConversationService`;
* providers concretos;
* runtimes concretos;
* Ollama;
* configuración externa;
* variables de entorno;
* persistencia;
* UI;
* transporte.

Una relación futura solo podrá volver a evaluarse si existe:

* una necesidad funcional concreta;
* un contrato arquitectónico explícito;
* evidencia de utilidad;
* preservación de Runtime Independence;
* validación de las cuatro preguntas obligatorias;
* aprobación humana explícita.

**Riesgo evitado:**

Modificar prematuramente el límite arquitectónico del Kernel o convertirlo en orquestador de infraestructura.

**Resultado:**

La separación actual se mantiene como baseline.

Esta decisión no autoriza una futura integración automática.

---

## DEC-PEND-006 — Ubicación y formalización del Project Vault

**Estado:**

```text
under_review
```

**Prioridad:**

```text
alta para continuidad de sesiones
```

**Contexto:**

El Project Vault fue creado fuera del repositorio oficial:

```text
D:\Ollama\malak-project-vault
```

Su separación fue intencional para evitar:

* contaminación del baseline;
* mezcla de autoridad;
* sobrescritura de documentación crítica;
* acoplamiento al runtime;
* incorporación prematura de artefactos derivados.

**Decisión requerida:**

Definir su modelo final de versionado y respaldo.

**Alternativas:**

1. repositorio Git local independiente;
2. repositorio privado independiente en GitHub;
3. almacenamiento exclusivamente local;
4. respaldo cifrado;
5. combinación de Git local y remoto privado.

**Criterios:**

* confidencialidad;
* trazabilidad;
* reversibilidad;
* portabilidad;
* recuperación ante pérdida;
* separación respecto del repositorio oficial;
* compatibilidad con Obsidian;
* exclusión de índices y cachés.

**Riesgos:**

* pérdida del Vault;
* duplicación no controlada;
* exposición de información sensible;
* confusión entre Vault y fuente de verdad.

---

## DEC-PEND-007 — Política de sincronización con Obsidian

**Estado:**

```text
open
```

**Prioridad:**

```text
media
```

**Contexto:**

Obsidian será utilizado como interfaz humana del Project Vault.

No debe adquirir autoridad propia ni reemplazar Git.

**Decisión requerida:**

Definir:

* método de sincronización;
* plugins permitidos;
* plugins prohibidos;
* política de escritura automática;
* política de backups;
* tratamiento de metadatos;
* uso del grafo;
* manejo de archivos adjuntos;
* protección de secretos.

**Alternativas de sincronización:**

* sin sincronización externa;
* Git privado;
* Obsidian Sync;
* almacenamiento cifrado;
* backup manual;
* Google Drive, sujeto a evaluación;
* almacenamiento local con snapshots.

**Restricciones preliminares:**

* no ejecutar plugins sin revisión;
* no habilitar publicación pública;
* no almacenar secretos;
* no permitir scripts con escritura sobre el repositorio oficial;
* no sincronizar índices RAG como fuentes documentales.

---

## DEC-PEND-008 — Modelo de metadatos del Vault

**Estado:**

```text
open
```

**Prioridad:**

```text
media
```

**Contexto:**

Los documentos iniciales utilizan metadatos YAML.

Todavía no existe un esquema formal validado.

**Decisión requerida:**

Definir el conjunto mínimo y estable de metadatos.

**Campos candidatos:**

```yaml
id:
title:
type:
status:
authority_level:
authority_rank:
version:
created:
last_reviewed:
source_of_truth:
source_repository:
source_branch:
source_commit:
derived:
operational_context:
retrieval_enabled:
retrieval_scope:
scope:
supersedes:
superseded_by:
```

**Preguntas abiertas:**

* ¿Qué campos son obligatorios?
* ¿Qué tipos documentales existirán?
* ¿Cómo se validarán IDs?
* ¿Cómo se representa la procedencia?
* ¿Cómo se registran múltiples fuentes?
* ¿Cómo se expresa vigencia?
* ¿Cómo se actualiza `last_reviewed`?
* ¿Qué campos serán utilizados por el futuro RAG?

**Riesgo principal:**

Crear un esquema excesivamente complejo antes de conocer las necesidades reales.

---

## DEC-PEND-009 — Generación automática del contexto de sesión

**Estado:**

```text
deferred
```

**Prioridad:**

```text
media después de estabilizar el Vault
```

**Contexto:**

El futuro Session Context Generator debería obtener evidencia directamente del repositorio.

**Decisión requerida:**

Definir el alcance exacto del generador.

**Datos candidatos:**

* rama;
* `HEAD`;
* estado del working tree;
* tags;
* último PR;
* tests;
* `compileall`;
* `git diff --check`;
* sprint cerrado;
* sprint aprobado;
* documentación modificada;
* decisiones abiertas;
* riesgos;
* objetivo de sesión.

**Restricciones:**

* no modificar documentación oficial;
* no aprobar decisiones;
* no inferir resultados;
* no ejecutar cambios;
* no escribir sobre el baseline sin revisión;
* generar artefactos derivados;
* citar fuentes.

**Motivo del diferimiento:**

Primero deben estabilizarse:

* gobernanza;
* baseline;
* roadmap;
* decisiones;
* plantilla de contexto;
* esquema de metadatos.

---

## DEC-PEND-010 — Tecnología del futuro RAG externo

**Estado:**

```text
deferred
```

**Prioridad:**

```text
baja en la fase actual
```

**Contexto:**

El RAG externo se implementará después de estabilizar el Vault, Obsidian y el generador de contexto.

**Decisión requerida:**

Seleccionar posteriormente:

* motor vectorial;
* modelo de embeddings;
* estrategia de chunking;
* filtros de autoridad;
* almacenamiento;
* reranking;
* citas;
* actualización incremental;
* tratamiento de contenido histórico;
* tratamiento de documentos rechazados.

**Alternativas preliminares:**

* ChromaDB;
* SQLite con extensión vectorial;
* Qdrant local;
* índice híbrido;
* búsqueda textual antes que vectorial;
* solución mínima propia.

**Regla:**

No elegir tecnología antes de definir:

* volumen;
* consultas;
* autoridad;
* seguridad;
* costos;
* mantenimiento;
* reconstrucción;
* portabilidad.

---

## DEC-PEND-011 — Alcance del futuro auditor externo

**Estado:**

```text
deferred
```

**Prioridad:**

```text
posterior al RAG externo
```

**Contexto:**

El futuro auditor deberá comparar arquitectura, implementación y evidencia.

**Decisión requerida:**

Definir el primer conjunto de controles auditables.

**Controles candidatos:**

* independencia del Kernel;
* ausencia de imports prohibidos;
* separación de runtime;
* contratos públicos;
* dependencias;
* autorización;
* trazabilidad;
* configuración;
* cobertura de tests;
* sincronización documental;
* manejo de secretos;
* integridad de archivos;
* cumplimiento de ADR.

**Restricciones:**

* solo lectura por defecto;
* resultados reproducibles;
* evidencia adjunta;
* sin corrección automática;
* sin autoridad para modificar;
* revisión humana obligatoria.

---

## DEC-PEND-012 — Incorporación de Ruff y mypy

**Estado:**

```text
deferred
```

**Prioridad:**

```text
futura
```

**Contexto:**

Ruff no forma parte del baseline.

No debe instalarse localmente de manera aislada ni incorporarse sin declaración formal.

**Decisión requerida:**

Evaluar Ruff y mypy dentro de una Development Tooling Foundation.

**Evaluación requerida:**

* reglas;
* compatibilidad;
* falsos positivos;
* costo de adopción;
* impacto sobre código existente;
* configuración en `pyproject.toml`;
* dependencias de desarrollo;
* CI;
* ejecución local;
* documentación;
* rollout incremental;
* rollback.

**Restricción:**

No incorporar tooling para resolver un problema no demostrado.

---

# Decisiones resueltas recientes

## DEC-RES-001 — Rama permanente del repositorio

**Estado:**

```text
closed
```

**Decisión:**

```text
main
```

`main` es la rama oficial, predeterminada y única rama permanente del repositorio.

Las ramas anteriores fueron integradas y eliminadas.

---

## DEC-RES-002 — Project Context & Knowledge Governance Foundation

**Estado:**

```text
closed
```

**Decisión:**

Crear una capa documental externa e independiente del repositorio principal.

Secuencia aceptada:

1. Project Context Foundation;
2. Obsidian Knowledge Foundation;
3. Session Context Generator;
4. External Project RAG;
5. Architecture & Security Auditor Foundation.

---

## DEC-RES-003 — Separación del Project Vault

**Estado:**

```text
closed
```

**Decisión:**

El Project Vault se crea inicialmente fuera del repositorio oficial:

```text
D:\Ollama\malak-project-vault
```

El Vault no forma parte del Kernel ni del runtime.

---

## DEC-RES-004 — Fuente de verdad

**Estado:**

```text
closed
```

**Decisión:**

El repositorio oficial conserva la fuente de verdad para:

* código;
* tests;
* configuración;
* documentación normativa;
* releases;
* ADR;
* baseline.

El Vault es derivado y no reemplaza esas fuentes.

---

## DEC-RES-005 — Número de tests del baseline

**Estado:**

```text
closed
```

**Decisión verificada:**

```text
74 passed
```

El valor corresponde al estado documentado al cierre del Sprint 7.3.

No debe reutilizarse automáticamente después de cambios futuros sin ejecutar nuevamente la suite.

---

## DEC-RES-006 — Último sprint cerrado

**Estado:**

```text
closed
```

**Decisión verificada:**

```text
Sprint 7.3 — Conversation Provider Boundary Stabilization
```

**Baseline resultante:**

```text
fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
```

**Pull request integrado:**

```text
PR #13
```

No debe registrarse el baseline únicamente como “Sprint 7”.

## 5. Plantilla para nuevas decisiones

Toda nueva decisión pendiente deberá utilizar una estructura equivalente:

```markdown
## DEC-PEND-XXX — Título

**Estado:**

`open`

**Prioridad:**

`baja | media | alta`

**Contexto:**

Descripción verificable del problema.

**Decisión requerida:**

Pregunta exacta que debe resolverse.

**Alternativas:**

- alternativa A;
- alternativa B;
- alternativa C.

**Criterios:**

- criterio 1;
- criterio 2.

**Riesgos:**

- riesgo 1;
- riesgo 2.

**Dependencias:**

- dependencia 1;
- dependencia 2.

**Próxima acción permitida:**

Acción de análisis o revisión.

**Acción no permitida:**

Cambio que requiere aprobación.
```

---

## 6. Regla de actualización

Este documento deberá actualizarse cuando:

* se identifique una nueva decisión material;
* una decisión pase a revisión;
* una decisión sea diferida;
* exista aprobación;
* exista rechazo;
* una decisión sea formalizada;
* una decisión sea reemplazada;
* cambie el baseline;
* cambie el roadmap;
* se cierre un sprint.

Las decisiones resueltas podrán trasladarse posteriormente a un registro histórico.

---

## 7. Principios rectores

> Registrar una decisión pendiente no significa aprobarla.

> Una pregunta abierta no debe completarse mediante suposición.

> Una conversación puede iniciar una decisión; solamente la formalización puede cerrarla.

> Cuando no existe aprobación, debe prevalecer la inacción reversible.

> Ninguna decisión pendiente concede autoridad para modificar Malāk.
