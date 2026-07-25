---

id: MALAK-PENDING-DECISIONS
title: Malāk Pending Decisions
type: decision-register
status: active
authority_level: proposal
authority_rank: 9
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-25
source_of_truth: repository-and-owner-decisions
source_repository: Aranwill/jarvis
source_branch: main
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: proposals
---

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
closed
```

**Prioridad histórica:**

```text
alta
```

**Resolución:**

```text
Sprint 7.4 — Consolidación de logs, métricas y auditoría
```

Sprint 7.4 fue seleccionado después de:

* necesidad real;
* alineación con Blueprint;
* alineación con Constitución Cognitiva;
* alineación con Gobernanza;
* mantenimiento de un Kernel simple;
* alcance explícito y limitado;
* riesgos y rollback;
* aprobación humana.

**Evidencia:**

* `docs/project/sprints/SPRINT-7.4.md`;
* PR #14;
* merge commit `7cd7fcc811df01555837319ec4cac0a93ef94fff`;
* validación integral con 121 pruebas aprobadas;
* registro gobernado del Incremento 8.

**Resultado:**

La decisión histórica de seleccionar el sprint posterior a Sprint 7.3
queda resuelta.

Esta resolución no aprueba automáticamente un sprint posterior a
Sprint 7.4.

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
closed
```

**Prioridad histórica:**

```text
media
```

**Resolución:**

Métricas, eventos operativos y auditoría permanecen como subsistemas
separados.

Pueden compartir únicamente convenciones mínimas de trazabilidad:

* identificadores;
* fechas UTC;
* nombres de eventos y componentes.

No comparten:

* contratos;
* stores;
* políticas de error;
* políticas de retención;
* autoridad;
* un envelope universal.

Sprint 7.4 implementó únicamente eventos operativos:

* `OperationalEvent`;
* `OperationalEventSink`;
* stores operativos separados;
* integración opcional en la CLI;
* `request_id` generado exclusivamente en la CLI.

No implementó auditoría de seguridad ni autorización.

**Evidencia:**

* `docs/project/sprints/SPRINT-7.4.md`;
* PR #14;
* merge commit `7cd7fcc811df01555837319ec4cac0a93ef94fff`;
* 94 pruebas específicas;
* 121 pruebas totales;
* revisión de privacidad y arquitectura con resultado `APTO`.

**Deuda futura no bloqueante:**

* validación adicional de identificadores;
* exposición de errores;
* rotación y límites de crecimiento;
* retención y eliminación;
* concurrencia;
* recuperación ante corrupción parcial;
* permisos del archivo persistido.

**Resultado:**

La decisión de frontera queda cerrada. Las políticas futuras de
retención, seguridad y auditoría requieren alcance y aprobación
independientes.

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
closed
```

**Prioridad histórica:**

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

**Resolución:**

Se adopta la combinación de:

```text
Git local independiente
→ repositorio privado independiente en GitHub
```

Repositorio:

```text
Aranwill/malak-project-vault
```

Rama oficial:

```text
main
```

Estado verificado antes de la actualización documental vigente:

```text
HEAD: 03032a7b2aaecb47c27c2e8e5bff3a2c04179bd2
Working tree: limpio
main local: alineada con origin/main
```

El repositorio privado remoto proporciona respaldo, portabilidad y trazabilidad sin modificar la jerarquía de autoridad.

**Límites preservados:**

* el Vault continúa separado de `Aranwill/jarvis`;
* el Vault continúa siendo documental y derivado;
* el Vault no adquiere autoridad operativa;
* Obsidian continúa siendo únicamente una interfaz local;
* los snapshots históricos permanecen inmutables;
* índices, cachés, configuración privada y artefactos operativos no deben convertirse en fuentes documentales;
* la publicación remota no autoriza automatización ni escritura sobre Malāk.

**Evidencia:**

* repositorio privado `Aranwill/malak-project-vault`;
* PR #2 — incorporación documental de Vault Synchronization Agent Foundation;
* PR #3 — cierre posterior al merge humano;
* PR #4 — cierre técnico de la Fase 1;
* `07-audits/AUDIT_INDEX.md`;
* `08-session-context/MALAK_SESSION_CONTEXT.md`.

**Resultado:**

La decisión sobre ubicación, versionado y respaldo queda cerrada.

La política específica de sincronización con Obsidian permanece abierta en `DEC-PEND-007`.

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

## DEC-PEND-013 — Aprobación e implementación del Vault Synchronization Agent

**Estado:**

```text
closed
```

**Prioridad histórica:**

```text
alta para continuidad documental
```

**Contexto:**

La fundación documental `Vault Synchronization Agent Foundation` fue integrada en la rama `main` de `Aranwill/malak-project-vault` mediante:

```text
PR #2
Merge commit: bcefa948b250830139233376088d1e65bd159143
```

El cierre documental posterior fue integrado mediante:

```text
PR #3
Merge commit: 918997a61e9a7b68c353c2eb5697ea21ede7e91f
```

La incorporación documental no constituyó por sí sola aceptación arquitectónica ni autorización de implementación.

Después de revisar la política, la arquitectura, el modelo de amenazas, los límites operativos y la propuesta de implementación, el propietario aprobó la arquitectura mínima y la implementación supervisada de la Fase 1.

**Decisión:**

Se acepta la arquitectura mínima del Vault Synchronization Agent y se autoriza exclusivamente la implementación supervisada de la Fase 1.

La autorización se limita a una herramienta externa en Python que opere inicialmente como detector determinista de cambios y generador de evidencia en modo `dry-run`.

**Alcance autorizado de la Fase 1:**

* detectar cambios en `Aranwill/jarvis/main`;
* comparar el HEAD remoto con el último commit observado;
* registrar estado operativo local;
* generar un paquete de evidencia;
* identificar documentos candidatos del Vault mediante reglas deterministas;
* aplicar allowlist y denylist;
* validar rutas, Markdown, YAML, enlaces, hashes y metadatos;
* generar un informe de auditoría;
* operar mediante ejecución manual o scheduler externo;
* trabajar mediante gates pequeños y aprobación humana entre cada gate.

**Límites obligatorios:**

* `Aranwill/jarvis` permanece en modo de solo lectura;
* el Vault permanece fuera del Kernel y del runtime;
* la implementación se realizará en un workspace externo;
* la primera versión operará exclusivamente en modo `dry-run`;
* no se utilizará LLM durante la Fase 1;
* no se modificarán archivos de `Aranwill/jarvis`;
* no se modificarán archivos del Vault mediante el agente;
* no se crearán ramas mediante el agente;
* no se crearán commits mediante el agente;
* no se ejecutará `push`;
* no se abrirán pull requests;
* no se aprobarán ni mergearán pull requests;
* no se cerrarán decisiones automáticamente;
* no se modificarán snapshots históricos;
* no se implementará servidor HTTP;
* no se implementarán webhooks;
* no se implementará un daemon permanente;
* no se avanzará automáticamente entre gates;
* todo cambio de alcance requerirá aprobación humana explícita.

**Modelo de autoridad:**

```text
Agente:
observa, compara, valida y genera evidencia

LLM:
no utilizado en la Fase 1

Humano:
revisa, aprueba y autoriza cada gate
```

La autorización técnica no otorga autoridad documental ni operativa al agente.

**Ubicación prevista:**

```text
D:\Ollama\malak-vault-sync-agent
```

La ubicación es externa a:

```text
D:\Ollama\jarvis
D:\Ollama\malak-project-vault
```

**Permisos mínimos:**

* lectura de `D:\Ollama\jarvis`;
* lectura de `D:\Ollama\malak-project-vault`;
* escritura exclusiva dentro de `D:\Ollama\malak-vault-sync-agent`;
* comandos Git limitados a operaciones explícitamente autorizadas de lectura;
* sin credenciales de escritura sobre GitHub durante la Fase 1.

**Proceso de implementación aprobado:**

```text
Gate 0 — relevamiento de solo lectura
Gate 1 — workspace y configuración
Gate 2 — inspección Git de solo lectura
Gate 3 — estado persistente local
Gate 4 — paquete de evidencia
Gate 5 — resolución de documentos candidatos
Gate 6 — validadores deterministas
Gate 7 — informe de auditoría
Gate 8 — runner, lock y polling externo
Gate 9 — validación final
```

Cada gate debe:

1. mantener alcance limitado;
2. incluir pruebas;
3. demostrar que no modificó los repositorios observados;
4. presentar archivos creados o modificados;
5. presentar riesgos y desviaciones;
6. detenerse antes del siguiente gate;
7. esperar aprobación humana explícita.

**Fuera de alcance:**

* modificación automática del Vault;
* creación automática de ramas documentales;
* creación automática de commits;
* apertura automática de PR draft;
* actualización automática de baseline;
* modificación de documentos normativos;
* modificación de snapshots;
* integración con Kernel, Planner, Capability Registry, ConversationService, LLMRuntime o CLI;
* uso de LLM para permisos, gobernanza o decisiones;
* automatización completa;
* capacidades de fases posteriores.

**Validación arquitectónica:**

1. ¿Respeta el Blueprint?

   Sí. La herramienta permanece externa y no modifica la arquitectura operativa de Malāk.

2. ¿Respeta la Constitución Cognitiva?

   Sí. El agente observa y genera evidencia, pero no adquiere autoridad decisoria.

3. ¿Respeta la Gobernanza?

   Sí. Mantiene Human in Control, denegación por defecto, mínimo privilegio, trazabilidad y aprobación humana entre gates.

4. ¿Simplifica o mantiene simple el Kernel?

   Sí. El Kernel no es modificado ni conoce al agente.

**Riesgos aceptados y controles:**

* escritura accidental: controlada mediante separación de workspace y permisos mínimos;
* deriva de alcance: controlada mediante gates y aprobación humana;
* TOCTOU: deberá validarse antes de cerrar cada ejecución;
* exposición de secretos: deberá prevenirse mediante denylist, sanitización y límites de evidencia;
* falsos positivos: deberán explicarse mediante reglas deterministas;
* interpretación de evidencia como aprobación: prohibida explícitamente;
* ejecución defectuosa: reversible mediante deshabilitación del scheduler y eliminación del workspace.

**Rollback:**

La Fase 1 no modificará los repositorios observados.

El rollback consistirá en:

1. detener la ejecución;
2. deshabilitar cualquier scheduler;
3. retirar el workspace del agente;
4. restaurar el último estado local válido;
5. conservar o eliminar evidencia según decisión humana;
6. verificar que ambos repositorios permanecen sin cambios.

**Criterio de cierre:**

La decisión se considera resuelta porque:

* la arquitectura mínima fue revisada;
* la Fase 1 fue delimitada;
* los permisos fueron definidos;
* el alcance y fuera de alcance fueron aceptados;
* los gates fueron establecidos;
* el rollback fue definido;
* la implementación supervisada fue autorizada expresamente.

La autorización se limita a la Fase 1 y no aprueba ninguna fase posterior.

**Resultado posterior de implementación — cierre formal de Fase 1:**

La implementación autorizada fue completada y cerrada formalmente en el workspace externo:

```text
D:\Ollama\malak-vault-sync-agent
```

Estado final verificado:

```text
Rama: main
HEAD: 954659b
Último commit: docs(baseline): record phase 1 completion
Commit anterior: 7ff4880 fix(audit): align canonical run id contract
Working tree: limpio
Gate 0 a Gate 9: cerrados
Fase 1: cerrada formalmente
Suite completa: 148 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
last_applied_commit: null
Autoridad operativa: none
```

La validación final confirmó:

* Malāk intacto;
* Vault intacto;
* ausencia de modificación automática;
* evidencia e informe generados;
* hashes SHA-256 verificados;
* comandos Git operativos auditados como read-only;
* ninguna rama, commit, push ni pull request creada mediante el agente;
* ningún snapshot histórico modificado;
* ninguna decisión cerrada automáticamente;
* ninguna autoridad documental u operativa concedida al agente.

La evidencia de cierre se registra en:

```text
07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE.md
```

El baseline final del agente se encuentra en:

```text
docs/PHASE_1_FINAL_BASELINE.md
```

Este baseline se conserva como evidencia histórica del cierre técnico de la Fase 1.

**Resultado posterior de operacionalización read-only:**

Después del cierre formal de la Fase 1, el agente fue respaldado en un repositorio remoto independiente y operacionalizado en Windows sin ampliar su autoridad ni habilitar escritura sobre los repositorios observados.

Baseline operacional vigente:

```text
Repositorio: Aranwill/malak-vault-sync-agent
Rama: main
HEAD: ade622b99eaaed0a6342400db743d472aa30a3ae
PR integrada: #1
Working tree: limpio
main local: alineada con origin/main
Suite completa: 165 passed
Configuración privada: válida y excluida de Git
Ejecución manual: pass
Ejecución programada de validación: pass
last_applied_commit: null
Autoridad operativa: none
```

Estado remoto vigente del agente:

```text
Remoto configurado: sí
Repositorio remoto: Aranwill/malak-vault-sync-agent
Rama remota: main
Upstream de main: origin/main
Respaldo remoto: completado
HEAD local y remoto: coincidentes
```

La ejecución mediante el Programador de tareas de Windows fue utilizada únicamente para validar que el mismo comando `run-once` podía ejecutarse correctamente. La tarea programada fue eliminada posteriormente por decisión humana.

Modo operativo elegido:

```text
manual-on-demand
```

Flujo vigente:

```text
Avance aprobado de Malāk
→ merge o push a Aranwill/jarvis/main
→ ejecución manual de run-once
→ revisión humana de evidencia e informe
→ propuesta de actualización del Vault
→ aprobación del propietario
→ actualización documental gobernada
```

La evidencia del cierre de la operacionalización read-only se registra en:

```text
07-audits/vault-synchronization/2026-07-24_VAULT_SYNC_OPERATIONALIZATION_CLOSURE.md
```

Este resultado no reabre `DEC-PEND-013`, no modifica su estado `closed` y no autoriza:

* Fase 2;
* escritura automática en el Vault;
* creación automática de ramas, commits o pull requests;
* scheduler activo o ejecución permanente sin una nueva aprobación;
* servicio permanente;
* daemon;
* webhooks;
* uso de LLM;
* integración con Kernel o runtime;
* modificación de Malāk;
* modificación de snapshots históricos.

Cualquier ampliación de alcance requerirá una decisión independiente y aprobación humana explícita.

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

---

## DEC-RES-007 — Versionado y respaldo del Project Vault

**Estado:**

```text
closed
```

**Decisión:**

El Project Vault utiliza Git local y un repositorio privado independiente:

```text
Repositorio: Aranwill/malak-project-vault
Rama: main
```

El remoto proporciona respaldo y trazabilidad, pero no modifica el carácter derivado del Vault ni le concede autoridad sobre Malāk.

Esta resolución cierra `DEC-PEND-006` y no resuelve la política específica de sincronización con Obsidian registrada en `DEC-PEND-007`.

---

## DEC-RES-008 — Modo operativo del Vault Synchronization Agent

**Estado:**

```text
closed
```

**Decisión:**

El Vault Synchronization Agent se ejecutará:

```text
manualmente y bajo demanda
después de cada sesión aprobada de Malāk
una vez publicados o fusionados los cambios en Aranwill/jarvis/main
```

La ejecución programada fue validada técnicamente y la tarea del Programador de tareas de Windows fue eliminada por decisión humana.

Estado final:

```text
Modo operativo: manual-on-demand
Scheduler configurado: no
Servicio permanente: no
Daemon: no
Autoridad operativa: none
Fase 2 aprobada: no
```

Esta decisión no autoriza escritura automática sobre el Vault ni ampliaciones de alcance.

---

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
