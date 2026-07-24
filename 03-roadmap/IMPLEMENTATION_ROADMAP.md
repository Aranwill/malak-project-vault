---

id: MALAK-IMPLEMENTATION-ROADMAP
title: Malāk Implementation Roadmap
type: roadmap-summary
status: active
authority_level: approved_roadmap
authority_rank: 7
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-24
source_of_truth: repository
source_repository: Aranwill/jarvis
source_branch: main
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
Sprint 7.3 cerrado — Conversation Provider Boundary Stabilization
```

**Suite documentada:**

```text
74 passed
```

**Estado del próximo sprint:**

```text
No aprobado
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

## 5. Estado del bloque 7.x

| Sprint | Estado    | Autorización |
| ------ | --------- | ------------ |
| 7.0    | Cerrado   | Implementado |
| 7.1    | Cerrado   | Implementado |
| 7.2    | Cerrado   | Implementado |
| 7.3    | Cerrado   | Implementado |
| 7.4    | Propuesta | No aprobado  |
| 7.5    | Propuesta | No aprobado  |
| 7.6    | Propuesta | No aprobado  |
| 7.7    | Propuesta | No aprobado  |

El cierre del Sprint 7.3 no autoriza el inicio de Sprint 7.4 ni establece que la numeración histórica deba continuar.

La numeración histórica se conserva como referencia.

No establece una secuencia obligatoria.

Las fichas de sprints futuros deben tratarse como propuestas hasta que el propietario las apruebe expresamente.

---

## 6. Próximo sprint

Actualmente no existe un próximo sprint aprobado.

El Sprint 7.3 no aprobó una integración entre `Kernel.receive` y `ConversationService`.

Ambas rutas permanecen separadas y cualquier relación futura requerirá una necesidad concreta, diseño arquitectónico y aprobación explícita.

Antes de seleccionar el siguiente sprint deberá realizarse:

1. relevamiento completo del baseline;
2. revisión de arquitectura;
3. revisión del estado de la CLI;
4. revisión del subsistema de métricas;
5. revisión del Kernel;
6. revisión del Planner;
7. revisión del Capability Registry;
8. revisión de contratos centrales;
9. revisión de seguridad;
10. análisis de necesidades reales.

No deberá seleccionarse un sprint únicamente porque sea el siguiente número disponible.

---

## 7. Propuestas pendientes del roadmap oficial

### 7.1 Consolidación de logs, métricas y auditoría

**Estado:**

```text
no aprobada
```

Antes de implementarla deberá determinarse:

* qué logs existen;
* qué métricas existen;
* qué contratos están implementados;
* qué evidencia se necesita conservar;
* qué parte corresponde a observabilidad;
* qué parte corresponde a auditoría;
* qué parte corresponde a seguridad;
* qué almacenamiento resulta necesario;
* qué datos son sensibles;
* qué retención es apropiada.

No debe crearse una infraestructura unificada solo por conveniencia conceptual.

---

### 7.2 Security Control Plane Foundation

**Estado:**

```text
conceptualmente aceptada como línea futura
```

**Implementación:**

```text
no aprobada
```

Esta fundación deberá establecerse antes de capacidades externas o de alto riesgo.

Alcance conceptual conocido:

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

La aceptación conceptual de esta línea no autoriza todavía su sprint de implementación.

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

Las siguientes iniciativas fueron aceptadas como direcciones futuras, pero no forman parte del baseline implementado.

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
operacionalización read-only completada
modo manual-on-demand
scheduler activo: no
```

**Autoridad operativa:**

```text
none
```

La fundación define una capacidad externa para observar `Aranwill/jarvis/main`, comparar estados, validar evidencia y detectar drift documental sin modificar Malāk ni el Vault.

La implementación y la operacionalización completadas permanecen dentro del alcance read-only aprobado para la Fase 1.

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

**Repositorio independiente del agente:**

```text
Repositorio: Aranwill/malak-vault-sync-agent
Rama: main
HEAD: ade622b99eaaed0a6342400db743d472aa30a3ae
PR de operacionalización: #1 integrada
Working tree: limpio
main local: alineada con origin/main
Suite completa: 165 passed
Configuración privada: válida y excluida de Git
Ejecución manual: pass
Ejecución programada de validación: pass
Scheduler final: eliminado
Modo operativo: manual-on-demand
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
Suite operacional vigente: 165 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
Ejecución manual operacional: pass
Ejecución programada de validación: pass
Malāk intacto: sí
Vault intacto: sí
last_applied_commit: null
Hashes SHA-256 verificados: sí
```

Todos los comandos Git operativos auditados durante la Fase 1 fueron clasificados como operaciones de solo lectura.

**Capacidades implementadas en Fase 1:**

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

**Modelo de autoridad:**

```text
Agente:
observa, compara, valida y genera evidencia

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
* no se modificaron archivos del Vault mediante el agente;
* no se crearon ramas, commits ni PR mediante el agente;
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
→ propuesta de actualización del Vault
→ aprobación del propietario
→ actualización documental gobernada
```

**Evidencia de cierre:**

```text
07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE.md
07-audits/vault-synchronization/2026-07-24_VAULT_SYNC_OPERATIONALIZATION_CLOSURE.md
```

**Fase 2 y posteriores:**

```text
no aprobadas
```

El cierre de la Fase 1 no autoriza:

* modificación automática del Vault;
* escritura documental mediante el agente;
* creación automática de ramas;
* creación automática de commits;
* apertura automática de PR draft;
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

Mientras no exista un próximo sprint aprobado deberá indicar:

```text
Próximo sprint: pendiente de revisión y aprobación.
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