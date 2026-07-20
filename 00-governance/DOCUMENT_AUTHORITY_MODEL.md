# Malāk Document Authority Model

## 1. Propósito

Este documento define la jerarquía de autoridad aplicable al conocimiento relacionado con Malāk.

Su objetivo es evitar que:

* una conversación contradiga al Blueprint;
* una propuesta se interprete como decisión aprobada;
* un resumen reemplace a una fuente oficial;
* un documento obsoleto prevalezca sobre una versión vigente;
* una coincidencia semántica en un RAG se confunda con autoridad;
* una herramienta automática modifique el criterio arquitectónico del proyecto.

Cuando dos fuentes se contradigan, deberá prevalecer la de mayor autoridad, siempre que se encuentre vigente y sea aplicable al asunto analizado.

---

## 2. Principio general

La autoridad documental no depende únicamente de la relevancia temática.

Debe evaluarse considerando:

* jerarquía;
* estado;
* vigencia;
* versión;
* alcance;
* aprobación;
* procedencia;
* relación con el baseline actual.

Una fuente de mayor autoridad puede no ser aplicable si:

* fue reemplazada;
* se encuentra fuera de alcance;
* corresponde a una versión anterior;
* regula un asunto diferente;
* fue rechazada;
* dejó de estar vigente.

---

## 3. Niveles de autoridad

### Nivel 1 — Autoridad constitucional

Incluye los documentos que establecen los principios fundamentales, límites cognitivos, modelo de control y reglas no negociables de Malāk.

Ejemplos:

* Constitución Cognitiva;
* principios fundacionales formalmente aprobados;
* modelo superior de Human in Control;
* restricciones estructurales no delegables.

Características:

* máxima autoridad;
* modificación excepcional;
* requiere aprobación humana explícita;
* no puede ser alterada por un sprint ordinario;
* no puede ser reinterpretada por resúmenes, agentes o herramientas automáticas.

Metadatos recomendados:

```yaml
authority_level: constitutional
authority_rank: 1
mutation_policy: human_approval_required
retrieval_priority: highest
```

---

### Nivel 2 — Autoridad de gobernanza

Incluye los documentos que definen cómo se toman, aprueban, implementan, revisan y auditan decisiones dentro del proyecto.

Ejemplos:

* gobernanza general de Malāk;
* modelo de autoridad;
* políticas de aprobación;
* políticas de seguridad;
* reglas de cambio;
* mecanismos de excepción;
* criterios de aceptación del baseline.

Características:

* subordinada únicamente a la autoridad constitucional;
* obligatoria para decisiones, sprints y cambios;
* no puede ser omitida por conveniencia técnica;
* prevalece sobre planes de implementación y notas operativas.

Metadatos recomendados:

```yaml
authority_level: governance
authority_rank: 2
mutation_policy: controlled_change
retrieval_priority: highest
```

---

### Nivel 3 — Autoridad arquitectónica

Incluye los documentos que describen la arquitectura aprobada de Malāk.

Ejemplos:

* Blueprint;
* documentación del Kernel;
* arquitectura de runtime;
* modelo de conocimiento;
* límites entre componentes;
* zonas de confianza;
* arquitectura de seguridad;
* principios de desacoplamiento;
* contratos arquitectónicos estables.

Características:

* debe respetar los niveles constitucional y de gobernanza;
* define la forma válida de implementar capacidades;
* prevalece sobre implementaciones accidentales o históricas;
* toda desviación requiere ADR, justificación y aprobación.

Metadatos recomendados:

```yaml
authority_level: architecture
authority_rank: 3
mutation_policy: adr_and_human_approval
retrieval_priority: very_high
```

---

### Nivel 4 — Decisiones arquitectónicas aprobadas

Incluye ADR, RFC o decisiones equivalentes formalmente aceptadas.

Ejemplos:

* elección de una abstracción;
* separación de responsabilidades;
* adopción de un contrato;
* reemplazo de una arquitectura anterior;
* excepción explícita;
* decisión de seguridad aprobada.

Características:

* complementan o precisan la arquitectura;
* no pueden contradecir niveles superiores;
* deben indicar alcance y documentos afectados;
* pueden reemplazar decisiones previas si lo declaran explícitamente;
* su estado debe ser `accepted` o `active`.

Metadatos recomendados:

```yaml
authority_level: approved_decision
authority_rank: 4
mutation_policy: superseding_decision_required
retrieval_priority: very_high
```

---

### Nivel 5 — Baseline y releases vigentes

Incluye la evidencia formal del estado aceptado del proyecto.

Ejemplos:

* release vigente;
* manifest;
* baseline aprobado;
* versión actual;
* estado validado de tests;
* componentes implementados;
* commits de referencia;
* checklist de release;
* certificaciones internas.

Características:

* define qué está realmente incorporado;
* prevalece sobre planes futuros;
* debe ser verificable contra el repositorio;
* no reemplaza la arquitectura, pero determina el estado efectivo de implementación.

Metadatos recomendados:

```yaml
authority_level: baseline
authority_rank: 5
mutation_policy: release_process
retrieval_priority: high
```

---

### Nivel 6 — Documentación técnica vigente

Incluye documentación oficial que describe módulos, contratos, flujos, interfaces, pruebas y procedimientos actuales.

Ejemplos:

* documentación de componentes;
* contratos técnicos;
* guías de integración;
* documentación de desarrollo;
* checklist;
* documentación de tests;
* especificaciones operativas.

Características:

* válida mientras coincida con el baseline;
* debe sincronizarse con código y arquitectura;
* si contradice una fuente superior, debe corregirse;
* puede quedar obsoleta aunque el archivo siga existiendo.

Metadatos recomendados:

```yaml
authority_level: technical_documentation
authority_rank: 6
mutation_policy: reviewed_update
retrieval_priority: high
```

---

### Nivel 7 — Roadmap aprobado

Incluye fases, iniciativas y sprints futuros aceptados conceptualmente.

Ejemplos:

* roadmap;
* secuencia de implementación;
* fases futuras;
* backlog aprobado;
* iniciativas arquitectónicas pendientes.

Características:

* expresa intención futura;
* no demuestra implementación;
* no puede utilizarse como evidencia de cumplimiento;
* puede cambiar mediante gobernanza;
* debe diferenciar claramente lo aprobado de lo meramente propuesto.

Metadatos recomendados:

```yaml
authority_level: approved_roadmap
authority_rank: 7
mutation_policy: planning_approval
retrieval_priority: medium_high
```

---

### Nivel 8 — Planes de sprint y documentos de trabajo

Incluye la planificación concreta de una unidad de implementación.

Ejemplos:

* objetivos de sprint;
* alcance;
* tareas;
* criterios de aceptación;
* validaciones previstas;
* riesgos;
* plan de rollback.

Características:

* subordinada al roadmap y arquitectura;
* válida únicamente para el sprint correspondiente;
* no debe ampliar el alcance sin aprobación;
* al finalizar, sus resultados deben reflejarse en el baseline o quedar registrados como incompletos.

Metadatos recomendados:

```yaml
authority_level: sprint_plan
authority_rank: 8
mutation_policy: sprint_control
retrieval_priority: medium
```

---

### Nivel 9 — Propuestas y decisiones pendientes

Incluye ideas estructuradas que todavía no han sido aprobadas.

Ejemplos:

* RFC en revisión;
* ADR propuesto;
* alternativas;
* investigaciones;
* evaluaciones tecnológicas;
* mejoras sugeridas;
* decisiones pendientes.

Características:

* no constituyen autoridad vigente;
* deben presentarse como propuestas;
* no pueden alterar el contexto operativo;
* pueden originar decisiones formales después de revisión.

Metadatos recomendados:

```yaml
authority_level: proposal
authority_rank: 9
mutation_policy: review_required
retrieval_priority: low
```

---

### Nivel 10 — Notas, sesiones y conversaciones

Incluye material informal o contextual.

Ejemplos:

* conversaciones con asistentes;
* notas de reunión;
* transcripciones;
* observaciones;
* lluvia de ideas;
* resúmenes de sesión;
* borradores rápidos;
* recordatorios.

Características:

* valor contextual, no normativo;
* puede contener errores, contradicciones o información incompleta;
* no debe considerarse fuente de verdad;
* toda decisión relevante debe trasladarse a un documento formal.

Metadatos recomendados:

```yaml
authority_level: informal_context
authority_rank: 10
mutation_policy: unrestricted_notes
retrieval_priority: lowest
```

---

### Nivel 11 — Contenido rechazado, obsoleto o no confiable

Incluye material que no debe influir en decisiones vigentes.

Ejemplos:

* documentos rechazados;
* versiones reemplazadas;
* propuestas descartadas;
* documentación corrupta;
* resúmenes sin fuente;
* contenido no verificable;
* material incompatible con la gobernanza.

Características:

* excluido del contexto operativo;
* excluido del RAG activo por defecto;
* solo conservado por trazabilidad o auditoría;
* debe estar marcado explícitamente.

Metadatos recomendados:

```yaml
authority_level: excluded
authority_rank: 11
status: rejected
retrieval_enabled: false
operational_context: false
```

---

## 4. Regla de prevalencia

Cuando dos documentos se contradigan, se aplicará el siguiente orden:

1. verificar si ambos se encuentran vigentes;
2. verificar si regulan el mismo asunto;
3. verificar si pertenecen al mismo baseline;
4. comparar su nivel de autoridad;
5. comprobar si uno reemplaza explícitamente al otro;
6. revisar ADR, release o decisión posterior;
7. registrar la contradicción si no puede resolverse.

Nunca deberá resolverse una contradicción únicamente mediante similitud semántica o interpretación del LLM.

---

## 5. Autoridad frente a implementación real

La implementación no obtiene autoridad automáticamente por existir en el código.

Si el código contradice la arquitectura aprobada:

* la arquitectura continúa siendo la referencia normativa;
* el código debe tratarse como posible desviación;
* deberá evaluarse si existe un ADR aprobado;
* deberá registrarse un hallazgo;
* deberá corregirse el código o actualizarse formalmente la arquitectura.

No se debe modificar documentación superior únicamente para justificar una implementación accidental.

---

## 6. Autoridad frente a conversaciones

Las conversaciones pueden:

* aportar contexto;
* registrar razonamientos;
* detectar riesgos;
* proponer mejoras;
* documentar intenciones;
* servir como evidencia auxiliar.

Las conversaciones no pueden:

* modificar el baseline;
* aprobar un sprint por sí solas;
* reemplazar un ADR;
* redefinir la arquitectura;
* modificar la Constitución Cognitiva;
* alterar la gobernanza;
* convertir una propuesta en decisión vigente.

Toda decisión surgida en una conversación debe formalizarse en el artefacto correspondiente.

---

## 7. Autoridad frente a resúmenes

Un resumen es siempre una representación derivada.

Debe:

* identificar sus fuentes;
* indicar la fecha de actualización;
* declarar su alcance;
* evitar introducir decisiones nuevas;
* distinguir hechos de interpretaciones;
* poder ser regenerado.

Cuando un resumen contradiga a su fuente, prevalece la fuente.

---

## 8. Autoridad en el RAG externo

El futuro RAG deberá aplicar filtros antes del ranking semántico.

Orden recomendado:

1. estado documental;
2. vigencia;
3. nivel de autoridad;
4. compatibilidad con el baseline;
5. aplicabilidad al tema;
6. relevancia semántica;
7. fecha;
8. calidad de la fuente.

Una fuente de menor autoridad no deberá desplazar a una fuente superior solo por tener mayor similitud vectorial.

---

## 9. Autoridad temporal

Todo documento susceptible de quedar obsoleto deberá indicar:

* fecha de creación;
* fecha de última revisión;
* versión;
* baseline aplicable;
* documento reemplazado;
* documento que lo reemplaza;
* estado actual.

Ejemplo:

```yaml
created: 2026-07-20
last_reviewed: 2026-07-20
status: active
applies_to_version: v0.7.x-alpha
supersedes: null
superseded_by: null
```

---

## 10. Autoridad por alcance

Un documento puede tener alta autoridad y, sin embargo, no ser aplicable a todos los módulos.

Cuando corresponda, deberá indicar:

```yaml
scope:
  - kernel
  - runtime
  - security
  - documentation
```

Una decisión limitada a telemetría no debe utilizarse para justificar cambios en autorización, memoria o Kernel.

---

## 11. Tratamiento de contradicciones no resueltas

Cuando no sea posible determinar qué fuente prevalece:

1. no asumir una respuesta;
2. registrar la contradicción;
3. identificar las fuentes involucradas;
4. suspender cualquier cambio irreversible relacionado;
5. generar una decisión pendiente;
6. elevar el asunto a revisión humana.

La ausencia de claridad no concede permiso para modificar.

---

## 12. Metadatos mínimos recomendados

Los documentos gobernados deberían incluir, cuando resulte aplicable:

```yaml
---
id: DOC-EXAMPLE-001
title: Example
type: architecture
status: active
authority_level: architecture
authority_rank: 3
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-20
source_of_truth: repository
applies_to_version: v0.7.x-alpha
scope:
  - runtime
supersedes: null
superseded_by: null
retrieval_enabled: true
operational_context: true
---
```

Estos metadatos no deben agregarse de forma masiva a documentos oficiales sin revisión previa.

---

## 13. Regla para asistentes y herramientas

Todo asistente, script, RAG o auditor que utilice el Vault deberá:

* identificar la autoridad de las fuentes;
* evitar presentar propuestas como decisiones;
* citar el origen;
* señalar contradicciones;
* respetar exclusiones;
* diferenciar implementación actual de roadmap futuro;
* declarar cuando una afirmación no pueda verificarse;
* evitar completar vacíos mediante suposiciones.

---

## 14. Principio rector

> La relevancia ayuda a encontrar una fuente. La autoridad determina cuánto puede confiarse en ella.

> La implementación demuestra lo que existe. La gobernanza determina lo que está permitido.
