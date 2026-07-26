---

id: MALAK-IMPLEMENTATION-ROADMAP
title: Malāk Implementation Roadmap
type: roadmap-summary
status: active
authority_level: approved_roadmap
authority_rank: 7
version: 1.1
created: 2026-07-20
last_reviewed: 2026-07-26
source_of_truth: repository
source_repository: Aranwill/jarvis
source_branch: main
source_commit: 4afeed440a3bf2096035d0d458d2ef75c71689fd
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
---

# Malāk Implementation Roadmap

## 1. Propósito

Este documento organiza el estado de implementación y las líneas futuras conocidas de Malāk.

Su propósito es:

* diferenciar lo implementado de lo pendiente;
* separar decisiones aprobadas de propuestas;
* conservar una secuencia arquitectónica coherente;
* evitar que una idea futura se interprete como autorización;
* facilitar la preparación de sesiones;
* servir como referencia operativa para el Project Vault.

Este documento es derivado.

No reemplaza:

* Constitución Cognitiva;
* Constitución de Gobernanza;
* Blueprint;
* ADR aceptados;
* especificaciones aprobadas;
* contratos públicos;
* roadmap oficial del repositorio;
* fichas de sprint;
* aprobación explícita del propietario.

---

## 2. Autoridad y limitaciones

La existencia de una fase, iniciativa, sprint o capacidad dentro de este documento no implica autorización para implementarla.

Ningún elemento futuro podrá iniciarse sin:

1. revisión del baseline vigente;
2. inspección del código;
3. inspección de tests;
4. revisión documental;
5. identificación de una necesidad real;
6. definición de alcance;
7. definición de fuera de alcance;
8. evaluación de riesgos;
9. evaluación de dependencias;
10. plan de rollback;
11. respuesta a las cuatro preguntas obligatorias;
12. debate del plan;
13. aprobación explícita del propietario.

El cierre de un sprint no autoriza automáticamente el siguiente.

---

## 3. Estado general

**Rama permanente:**

```text
main
```

**Versión nominal:**

```text
v0.6.0-alpha
```

**Baseline operativo actual:**

```text
main en 4afeed440a3bf2096035d0d458d2ef75c71689fd
Sprint 7.4 cerrado
Sprint 7.5 aprobado y en progreso
Incremento 1 integrado mediante PR #15
Incremento 2 reconciliado mediante PR #16
```

**Suite documentada:**

```text
166 passed
```

La suite corresponde a la validación integral ejecutada sobre
`c0a4283b100609daeb4b3422dd28634df9d851b6`. Los commits posteriores
hasta `4afeed440a3bf2096035d0d458d2ef75c71689fd` fueron exclusivamente
documentales y no se presenta la suite como reejecutada después de ese
commit validado.

**Estado del trabajo vigente:**

```text
Sprint 7.5 en progreso
Incrementos 1 y 2 completados
Incremento 3 — PDP mínimo: pendiente de diseño y aprobación incremental
```

---

## 4. Sprints cerrados

### Sprint 7.0 — CLI mínima con MockLLMRuntime

**Estado:**

```text
cerrado
```

Resultado:

* CLI técnica mínima;
* ejecución mediante `MockLLMRuntime`;
* comandos básicos;
* control de errores;
* flujo conversacional local;
* sin integración formal con el Kernel.

---

### Sprint 7.1 — Composición de CLI con OllamaRuntime

**Estado:**

```text
cerrado
```

Resultado:

* selección externa del runtime;
* soporte para `MockLLMRuntime`;
* soporte para `OllamaRuntime`;
* configuración mediante variables de entorno;
* composición en la frontera de aplicación;
* Kernel sin modificación;
* integración real validada con un modelo local.

---

### Sprint 7.2 — Runtime Metric Sink Contract

**Estado:**

```text
cerrado
```

Resultado:

* incorporación de `RuntimeMetricSink`;
* contrato estructural de solo escritura;
* desacoplamiento de `OllamaRuntime` respecto de stores concretos;
* compatibilidad con `InMemoryRuntimeMetricStore`;
* compatibilidad con `JsonlRuntimeMetricStore`;
* pruebas deterministas;
* ausencia de cambios en Kernel y contratos conversacionales.

---

### Sprint 7.3 — Conversation Provider Boundary Stabilization

**Estado:**

```text
cerrado
```

Resultado:

* estabilización de `ConversationProviderRegistry`;
* incorporación de `ConversationProviderNotFoundError`;
* delimitación mínima de `ConversationService`;
* integración mediante PR #13;
* baseline resultante `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`.

---

### Sprint 7.4 — Consolidación de logs, métricas y auditoría

**Estado:**

```text
cerrado
```

Resultado:

* eventos operativos y correlación desde la CLI;
* métricas, eventos y auditoría separados;
* 94 pruebas específicas y 121 pruebas totales aprobadas;
* integración técnica mediante la PR #14;
* sincronización gobernada del Vault completada;
* Kernel, Planner y `ConversationService` intactos.

---

## 5. Estado del bloque 7.x

| Sprint | Estado    | Autorización |
| ------ | --------- | ------------ |
| 7.0    | Cerrado   | Implementado |
| 7.1    | Cerrado   | Implementado |
| 7.2    | Cerrado   | Implementado |
| 7.3    | Cerrado   | Implementado |
| 7.4    | Cerrado   | Implementado y sincronizado |
| 7.5    | En progreso | Aprobado; Incrementos 1 y 2 completados |
| 7.6    | Propuesta | No aprobado  |
| 7.7    | Propuesta | No aprobado  |

El Sprint 7.4 fue cerrado formalmente. El Sprint 7.5 fue aprobado por
el propietario y activado en la documentación oficial.

La numeración histórica se conserva como referencia.

No establece una secuencia obligatoria.

Las fichas de Sprint 7.6 y 7.7 deben tratarse como propuestas hasta que
el propietario las apruebe expresamente.

---

## 6. Trabajo vigente

El trabajo vigente es el Sprint 7.5 — Base del plano de control de
seguridad.

Estado incremental:

1. contratos fundamentales de autorización: completado e integrado;
2. activación y reconciliación documental: completado;
3. Policy Decision Point mínimo: pendiente de diseño, revisión y
   aprobación humana;
4. Policy Enforcement Point inicial: pendiente;
5. evidencia de auditoría de autorización: pendiente;
6. revisión integral y cierre: pendiente.

Antes del PDP debe resolverse la semántica exacta de confirmación
humana. `AuthorizationDecision` conserva por ahora una decisión binaria
y no se incorporará un tercer estado por inferencia.

---

## 7. Estado de líneas del roadmap oficial

### 7.1 Consolidación de logs, métricas y auditoría

**Estado:**

```text
Sprint 7.4 cerrado
```

Resultado:

* métricas, eventos operativos y auditoría permanecen separados;
* `OperationalEvent` define una allowlist mínima e inmutable;
* `OperationalEventSink` conserva semántica de solo escritura;
* existen stores operativos separados de los stores de métricas;
* la CLI genera exclusivamente el `request_id`;
* los contratos conversacionales permanecen intactos;
* no se implementó auditoría de seguridad;
* no se incorporaron dependencias externas;
* Kernel, Planner y `ConversationService` permanecieron intactos.

---

### 7.2 Security Control Plane Foundation

**Estado:**

```text
Sprint 7.5 aprobado y en progreso
```

**Implementación:**

```text
contratos fundamentales integrados;
PDP, PEP y auditoría de autorización pendientes
```

Esta fundación deberá establecerse antes de capacidades externas o de alto riesgo.

Estado verificado:

* separación entre solicitud, autorización, ejecución y auditoría;
* denegación por defecto;
* `AuthorizationRequest`;
* `AuthorizationDecision`;
* `SecurityContext`;
* `PermissionScope`;
* Policy Decision Point determinista;
* Policy Enforcement Point;
* independencia respecto del Kernel;
* decisiones de seguridad sin LLM.

Los cuatro contratos públicos fueron integrados mediante la PR #15 y
validados con 45 pruebas específicas y 166 pruebas totales. La
aprobación del sprint no autoriza automáticamente sus incrementos
pendientes.

---

### 7.3 Preparación del AKS para GraphRAG

**Estado:**

```text
no aprobada
```

Esta propuesta no implica implementar GraphRAG.

Antes de avanzar deberá evaluarse:

* madurez del AKS;
* estructura documental;
* metadatos;
* IDs;
* relaciones;
* autoridad;
* trazabilidad;
* volumen real de información;
* utilidad operativa;
* costo de mantenimiento.

GraphRAG no debe implementarse únicamente por disponibilidad tecnológica.

---

### 7.4 Validación de baseline y release interna

**Estado:**

```text
no aprobada
```

Solo podrá realizarse cuando:

* los bloques previos estén cerrados;
* el código esté sincronizado;
* la documentación esté alineada;
* las pruebas estén en verde;
* los contratos estén estabilizados;
* no existan desviaciones conocidas;
* se defina formalmente el contenido de la release.


## 8. Iniciativas arquitectónicas aceptadas conceptualmente

Las siguientes iniciativas organizan líneas presentes y futuras. Su
estado debe leerse individualmente: la inclusión en esta sección no
constituye autorización adicional.

---

### 8.1 Project Context & Knowledge Governance Foundation

**Estado conceptual:**

```text
aprobada
```

**Estado de ejecución:**

```text
iniciada externamente
```

Ubicación:

```text
D:\Ollama\malak-project-vault
```

Objetivos:

* contexto de sesión actualizado;
* jerarquía documental;
* continuidad entre sesiones;
* reducción de contradicciones;
* Obsidian como interfaz humana;
* RAG externo;
* auditoría arquitectónica y de seguridad.

Secuencia aprobada:

1. Project Context Foundation;
2. Obsidian Knowledge Foundation;
3. Session Context Generator;
4. External Project RAG;
5. Architecture & Security Auditor Foundation.

Esta iniciativa debe permanecer separada del Kernel y del runtime de Malāk.

---

### 8.1.1 Vault Synchronization Agent Foundation

**Naturaleza:**

```text
tooling documental externo
```

**Estado documental:**

```text
integrado en el Malāk Project Vault mediante las PR #2, #3 y #4
```

**Estado arquitectónico:**

```text
Fase 1 aprobada, implementada y cerrada
```

**Implementación:**

```text
Fase 1 completada mediante Gates 0 a 9
```

**Estado operativo:**

```text
operacionalización manual completada
modo manual-on-demand
modos dry-run y controlled-proposal
scheduler activo: no
```

**Autoridad operativa:**

```text
none
```

La fundación define una capacidad externa para observar
`Aranwill/jarvis/main`, comparar estados, validar evidencia y detectar
drift documental sin modificar Malāk. En modo `controlled-proposal`
puede preparar cambios únicamente en una rama aislada del Vault y abrir
una PR draft; nunca escribe directamente en `main`.

No forma parte de:

* Kernel;
* Planner;
* Capability Registry;
* ConversationService;
* LLMRuntime;
* CLI;
* runtime de Malāk;
* Security Control Plane.

**Ubicación verificada:**

```text
D:\Ollama\malak-vault-sync-agent
```

La implementación permanece separada de:

```text
D:\Ollama\jarvis
D:\Ollama\malak-project-vault
```

**Baseline operativo vigente del agente:**

```text
Repositorio: Aranwill/malak-vault-sync-agent
Rama: main
HEAD: c54bfb0f4b1f6d715172d3dbb56704c639154019
PR de operacionalización: #1 integrada
PR de corrección del flujo controlado: #3 integrada
Working tree: limpio
main local: alineada con origin/main
Suite completa: 178 passed
Configuración privada: válida y excluida de Git
Ejecución manual end-to-end: pass
Scheduler final: eliminado
Modo operativo: manual-on-demand
Cursores de observación y propuesta: independientes
last_applied_commit: null
```

**Baseline histórico del cierre formal de la Fase 1:**

```text
Rama: main
HEAD: 954659b
Último commit: docs(baseline): record phase 1 completion
Commit anterior: 7ff4880 fix(audit): align canonical run id contract
Suite completa: 148 passed
```

El baseline histórico de cierre se encuentra en:

```text
docs/PHASE_1_FINAL_BASELINE.md
```

**Estado de gates:**

```text
Gate 0: cerrado
Gate 1: cerrado
Gate 2: cerrado
Gate 3: cerrado
Gate 4: cerrado
Gate 5: cerrado
Gate 6: cerrado
Gate 7: cerrado
Gate 8: cerrado
Gate 9: cerrado
Fase 1: cerrada formalmente
```

**Resultado de validación:**

```text
Suite de cierre de Fase 1: 148 passed
Suite operacional vigente: 178 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
Ejecución manual controlled-proposal: pass
Malāk intacto: sí
Vault main intacto: sí
last_applied_commit: null
Hashes SHA-256 verificados: sí
```

Todos los comandos Git operativos auditados durante el cierre histórico
de la Fase 1 fueron clasificados como operaciones de solo lectura. El
alcance controlado vigente añade escritura únicamente sobre una rama de
propuesta del Vault.

**Capacidades operativas vigentes:**

La lista incluye la base read-only de la Fase 1 y la extensión
controlada aprobada posteriormente:

* detección determinista de cambios en `Aranwill/jarvis/main`;
* comparación entre el HEAD remoto y el último commit observado;
* inspección Git de solo lectura;
* estado persistente local;
* generación de paquetes de evidencia;
* resolución determinista de documentos candidatos;
* aplicación de allowlist y denylist;
* validación de rutas;
* validación de Markdown;
* validación de YAML;
* validación de enlaces;
* validación de hashes;
* validación de metadatos;
* controles TOCTOU;
* sanitización de evidencia;
* límites de tamaño y alcance;
* generación de informes de auditoría;
* runner manual;
* lock de ejecución;
* polling externo;
* validación final end-to-end.
* cursores independientes para observación y propuesta;
* creación controlada de rama y commits en el Vault;
* publicación y apertura de PR draft;
* ausencia de aprobación o merge automático.

**Modelo de autoridad:**

```text
Agente:
observa, compara, valida, genera evidencia y prepara propuestas
documentales aisladas

LLM:
no utilizado en la Fase 1

Humano:
revisa, aprueba y autoriza cualquier ampliación
```

La finalización técnica no concede autoridad documental ni operativa al agente.

**Invariantes preservadas:**

* `Aranwill/jarvis` permaneció en modo de solo lectura;
* no se modificaron archivos de Malāk;
* no se ejecutó configuración de Malāk;
* no se crearon ramas, commits ni push sobre Malāk;
* no se escribió directamente sobre `main` del Vault;
* las modificaciones del Vault quedaron limitadas a una rama de propuesta;
* no se aprobaron ni mergearon PR;
* no se cerraron decisiones automáticamente;
* no se modificaron snapshots históricos;
* no se utilizó LLM;
* no se incorporó el agente al Kernel ni al runtime;
* `last_applied_commit` permaneció en `null`.

**Estado remoto del agente:**

```text
Remoto configurado: sí
Repositorio remoto: Aranwill/malak-vault-sync-agent
Rama remota: main
Upstream de main: origin/main
Respaldo remoto: completado
HEAD local y remoto: coincidentes
```

La existencia del repositorio remoto no concede autoridad operativa ni documental al agente.

**Modo operativo vigente:**

```text
Ejecución manual posterior a cada sesión aprobada de Malāk
```

La ejecución programada se utilizó únicamente para validar la operacionalización en Windows. La tarea programada fue eliminada posteriormente por decisión humana.

El agente deberá ejecutarse después de que los cambios legítimos de Malāk hayan sido publicados o fusionados en `Aranwill/jarvis/main`.

Flujo vigente:

```text
Avance aprobado de Malāk
→ merge o push a main
→ ejecución manual de run-once
→ revisión humana de evidencia e informe
→ rama y PR draft de actualización del Vault
→ reconciliación y aprobación humanas
→ merge exclusivamente humano
```

La ejecución end-to-end del flujo controlado quedó demostrada mediante:

```text
Run ID: 20260726T191148713343Z_4afeed44_b20482cf
Rango: 7cd7fcc811df01555837319ec4cac0a93ef94fff
       → 4afeed440a3bf2096035d0d458d2ef75c71689fd
PR draft del Vault: #10
Resultado: pass
```

**Evidencia de cierre:**

```text
07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE.md
07-audits/vault-synchronization/2026-07-24_VAULT_SYNC_OPERATIONALIZATION_CLOSURE.md
07-audits/vault-synchronization/2026-07-26_VAULT_SYNC_20260726T191148713343Z_4afeed44_b20482cf.md
```

**Fase 2 y posteriores:**

```text
no aprobadas
```

El baseline operativo vigente no autoriza:

* escritura directa en `main` del Vault;
* aprobación o merge automático;
* actualización automática de baseline;
* modificación de documentos normativos;
* modificación de snapshots;
* integración con Kernel, Planner, Capability Registry, ConversationService, LLMRuntime o CLI;
* uso de LLM;
* scheduler operativo;
* servicio permanente;
* daemon;
* webhooks;
* automatización completa;
* capacidades de fases posteriores.

Cualquier ampliación requerirá:

1. una necesidad concreta;
2. alcance explícito;
3. fuera de alcance;
4. evaluación de riesgos;
5. rollback;
6. validación arquitectónica;
7. decisión independiente;
8. aprobación humana explícita.


---

### 8.2 Resource Governance Foundation

**Estado conceptual:**

```text
aprobada como línea futura
```

Objetivo:

* reducir RAM;
* reducir VRAM;
* reducir latencia;
* limitar contexto;
* controlar carga de modelos;
* reducir herramientas activas;
* controlar almacenamiento;
* evitar complejidad innecesaria.

Principios:

* activar solo capacidades necesarias;
* lazy loading;
* descarga tras inactividad;
* un modelo pesado en VRAM por defecto;
* ejecución secuencial antes que paralela;
* caché de corta duración;
* herramientas filtradas por contexto;
* top-k limitado;
* índices reconstruibles;
* degradación controlada.

No existe todavía un sprint aprobado para esta fundación.

---

### 8.3 Model Governance Foundation

**Estado conceptual:**

```text
aprobada como línea futura
```

Objetivos:

* registro de modelos;
* versiones;
* licencias;
* tokenizers;
* capacidades;
* compatibilidad;
* benchmarks;
* integridad;
* metadatos;
* criterios de selección;
* preservación.

No existe todavía un sprint aprobado para esta fundación.

---

### 8.4 Controlled Engineering Improvement Loop Foundation

**Estado conceptual:**

```text
aprobada como línea futura
```

Ubicación recomendada:

```text
después de Model Governance Foundation
```

Principios:

> Malāk no se automejora modificándose. Se automejora aumentando la calidad de sus observaciones, evaluaciones y propuestas.

> La capacidad de aprender no implica autoridad para cambiar.

> La evidencia puede originar una propuesta; solamente la gobernanza puede convertirla en una modificación.

Alcance conceptual:

* observar telemetría;
* analizar benchmarks;
* revisar fallos;
* revisar incidentes;
* detectar oportunidades;
* generar propuestas;
* evaluar impacto;
* documentar riesgos;
* definir rollback;
* presentar evidencia;
* requerir aprobación humana.

No existe todavía un sprint aprobado.

---

### 8.5 Development Tooling Foundation

**Estado conceptual:**

```text
pendiente de evaluación formal
```

Deberá evaluar conjuntamente:

* Ruff;
* mypy;
* `pyproject.toml`;
* dependencias de desarrollo;
* separación entre dependencias productivas y de desarrollo;
* integración local;
* integración CI;
* reglas reproducibles;
* versionado;
* documentación.

Ruff no debe incorporarse aisladamente ni de forma improvisada.

---

### 8.6 Evidence Acquisition Foundation

**Estado conceptual:**

```text
aprobada como línea futura
```

Arquitectura objetivo:

```text
Evidence Broker
        ↓
Search Layer
        ↓
Fetch Layer
        ↓
Content Sanitizer
        ↓
Prompt Injection Detection
        ↓
Evidence Validation
        ↓
AKS Intake
        ↓
Browser Worker opcional
```

Principio:

```text
Internet is Hostile by Default
```

El Kernel y los LLM no deberán consumir contenido externo crudo.

No existe todavía un sprint aprobado.

---

### 8.7 Secure Context Manager

**Estado conceptual:**

```text
pendiente de implementación
```

Principio:

> Validate once, trust briefly, verify continuously.

Los contextos futuros deberán considerar:

* sesión;
* identidad;
* roles;
* trust level;
* permisos;
* timestamp;
* TTL;
* nonce;
* hash;
* firma;
* renovación;
* invalidación;
* trazabilidad.

No existe todavía un sprint aprobado.

---

### 8.8 Architecture & Security Auditor Foundation

**Estado conceptual:**

```text
aprobada como evolución futura del Project Vault
```

Objetivo:

comparar:

* arquitectura declarada;
* implementación real;
* tests;
* configuración;
* dependencias;
* políticas;
* telemetría;
* evidencia operativa.

Modo operativo esperado:

```text
solo lectura por defecto
```

Resultados esperados:

* conforme;
* parcialmente conforme;
* no conforme;
* no verificable;
* no aplicable.

El auditor no podrá modificar automáticamente el sistema auditado.

---

### 8.9 Sandbox Containment & Evaluation Evidence Foundation

**Estado conceptual:**

```text
incorporada a la planificación futura
diseño detallado no aprobado
implementación no aprobada
sin número de sprint asignado
```

Ubicación lógica propuesta:

```text
después de Security Control Plane Foundation
antes de simulaciones con agentes o del
Controlled Engineering Improvement Loop Foundation
```

Alcance conceptual:

* aislamiento y entornos descartables;
* control de red, archivos, procesos y herramientas;
* límites de CPU, RAM, VRAM, disco, tiempo y procesos;
* manifiestos reproducibles;
* telemetría externa al agente;
* registro verificable de operaciones;
* snapshots y hashes anteriores y posteriores;
* kill switch, timeout, cuarentena y cierre seguro;
* artefactos de evaluación separados;
* revisión humana obligatoria.

La incorporación documental no aprueba su diseño ni implementación.

---

## 9. Capacidades futuras sin implementación aprobada

Se mantienen como líneas futuras o pendientes:

* memoria conversacional;
* historial persistente;
* herramientas externas;
* navegación;
* agentes;
* mensajería;
* automatización del sistema operativo;
* GraphRAG;
* interfaz gráfica;
* SIAL;
* Simulation & Sandbox;
* Admin Identity & Access Control Layer;
* AI Preservation System;
* Model Archive;
* Metadata Registry;
* License and Tokenizer Vault;
* Prompt Library;
* Benchmark Registry;
* Compatibility Matrix;
* Integrity Checker;
* propuestas de mejora Nivel 4;
* Security Research Lab opcional.

La presencia en esta lista no implica:

* orden;
* prioridad;
* aprobación;
* fecha;
* sprint asignado;
* obligación de implementación.

---

## 10. Orden arquitectónico general

La secuencia de alto nivel debe respetar:

```text
Fundaciones
    ↓
Contratos
    ↓
Implementación mínima
    ↓
Pruebas
    ↓
Documentación
    ↓
Validación
    ↓
Baseline
    ↓
Siguiente fase
```

Para capacidades sensibles:

```text
Gobernanza
    ↓
Seguridad
    ↓
Autorización
    ↓
Ejecución controlada
    ↓
Auditoría
    ↓
Expansión de capacidades
```

Para el Project Vault:

```text
Gobernanza documental
    ↓
Contexto verificable
    ↓
Obsidian
    ↓
Generación automática de contexto
    ↓
RAG externo
    ↓
Auditor externo
```

---

## 11. Reglas de ejecución

Todo sprint deberá:

* ser corto;
* poseer un alcance limitado;
* implementar una unidad coherente;
* evitar cambios laterales;
* incluir tests;
* incluir validación arquitectónica;
* incluir revisión documental;
* verificar integración;
* utilizar commits pequeños;
* ser reversible;
* documentar rollback;
* cerrar antes de iniciar el siguiente.

No se deben agrupar varias fundaciones en un único sprint.

---

## 12. Reglas de exclusión

Ningún sprint futuro podrá:

* ampliar el Kernel con lógica de negocio;
* acoplar el Kernel a un runtime;
* acoplar el Kernel a un modelo;
* acoplar el Kernel a Internet;
* introducir dependencias no aprobadas;
* modificar contratos centrales sin revisión;
* implementar agentes antes de seguridad;
* ejecutar acciones sensibles sin autorización;
* utilizar telemetría como autoridad automática;
* permitir que un LLM modifique el baseline;
* confundir una propuesta con una decisión;
* asumir que el hardware actual define la arquitectura permanente.

---

## 13. Selección del próximo sprint

El próximo sprint deberá seleccionarse mediante este proceso:

### Paso 1 — Verificación

* confirmar rama `main`;
* confirmar working tree limpio;
* confirmar `HEAD`;
* ejecutar tests;
* ejecutar `compileall`;
* ejecutar `git diff --check`.

### Paso 2 — Relevamiento

* revisar código;
* revisar arquitectura;
* revisar contratos;
* revisar roadmap;
* revisar documentación;
* revisar riesgos;
* revisar deuda técnica.

### Paso 3 — Necesidad

Responder:

* ¿qué problema real existe?
* ¿por qué debe resolverse ahora?
* ¿qué componente corresponde modificar?
* ¿qué sucede si no se implementa?
* ¿existe una solución más simple?

### Paso 4 — Gobernanza

Responder las cuatro preguntas obligatorias:

1. ¿Respeta el Blueprint?
2. ¿Respeta la Constitución Cognitiva?
3. ¿Respeta la Gobernanza?
4. ¿Simplifica o mantiene simple el Kernel?

### Paso 5 — Propuesta

Presentar:

* nombre del sprint;
* objetivo;
* alcance;
* fuera de alcance;
* archivos afectados;
* contratos afectados;
* tests;
* riesgos;
* rollback;
* documentación;
* criterios de aceptación.

### Paso 6 — Aprobación

Solo después de aprobación explícita podrá:

* crearse una rama;
* modificarse código;
* modificarse documentación oficial;
* iniciar la implementación.

---

## 14. Relación con el contexto de sesión

El archivo:

```text
08-session-context\MALAK_SESSION_CONTEXT.md
```

deberá incluir únicamente:

* baseline actual;
* último sprint cerrado;
* estado de tests;
* próxima iniciativa aprobada, si existe;
* decisiones pendientes;
* restricciones;
* objetivo de la sesión.

Mientras el Sprint 7.5 permanezca abierto deberá indicar:

```text
Sprint 7.5: aprobado y en progreso.
Incremento 3: pendiente de diseño, revisión y aprobación humana.
Sprint posterior: no aprobado.
```

---

## 15. Regla de actualización

Este documento deberá revisarse cuando ocurra:

* cierre de sprint;
* aprobación de sprint;
* rechazo de propuesta;
* aceptación de iniciativa;
* cambio de prioridad;
* nueva release;
* cambio de arquitectura;
* aceptación de ADR;
* cambio de baseline;
* incorporación de una Capability;
* incorporación de una dependencia;
* cambio material del roadmap oficial.

---

## 16. Principios rectores

> Una hoja de ruta organiza posibilidades; no concede autoridad.

> El siguiente número de sprint no determina la siguiente necesidad.

> Cada capacidad debe justificar su existencia.

> Primero se diseña la arquitectura correcta; después se implementa incrementalmente.

> La aprobación conceptual de una fundación no equivale a autorización para implementarla.

> Ningún sprint comienza sin revisión, debate y aprobación explícita.
