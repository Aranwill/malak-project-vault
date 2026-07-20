# Malāk Content Lifecycle

## 1. Propósito

Este documento define el ciclo de vida de los contenidos almacenados en el Malāk Project Vault.

Su objetivo es garantizar que cada documento, nota, propuesta, resumen, snapshot o artefacto pueda identificarse según:

* su estado;
* su vigencia;
* su nivel de aprobación;
* su aplicabilidad;
* su relación con el baseline;
* su elegibilidad para contexto operativo;
* su elegibilidad para recuperación mediante RAG;
* su valor histórico o de auditoría.

El ciclo de vida documental evita que contenido incompleto, reemplazado, rechazado o desactualizado influya en decisiones vigentes.

---

## 2. Principio general

Todo contenido relevante debe poseer un estado explícito.

La existencia de un archivo no implica que:

* esté aprobado;
* se encuentre vigente;
* represente el baseline;
* pueda utilizarse como contexto operativo;
* sea elegible para recuperación automática;
* tenga autoridad sobre otros documentos.

Cuando un documento no posea estado identificable, deberá tratarse como no verificado hasta que sea revisado.

---

## 3. Estados documentales

### 3.1 `draft`

Contenido en elaboración.

Se utiliza cuando:

* el documento todavía está siendo escrito;
* su estructura puede cambiar;
* contiene información incompleta;
* no fue sometido a revisión;
* no existe aprobación formal.

Reglas:

* no constituye autoridad vigente;
* no debe utilizarse para modificar el baseline;
* puede ser editado libremente dentro de su alcance;
* debe identificarse claramente como borrador;
* no debe incluirse en el contexto operativo por defecto;
* puede ser recuperado únicamente en búsquedas orientadas a borradores.

Metadatos recomendados:

```yaml
status: draft
approved: false
operational_context: false
retrieval_enabled: false
```

Transiciones permitidas:

```text
draft → proposed
draft → archived
draft → rejected
```

---

### 3.2 `proposed`

Contenido estructurado presentado para revisión.

Se utiliza cuando:

* una idea fue formalizada;
* existe una propuesta de decisión;
* se plantea un cambio arquitectónico;
* se propone una nueva fase;
* se presenta un ajuste de gobernanza;
* se documenta una alternativa para evaluación.

Reglas:

* no constituye una decisión aprobada;
* debe identificar problema, objetivo, alcance e impacto;
* debe indicar riesgos y documentos afectados;
* debe conservar evidencia y motivación;
* debe permanecer fuera del contexto operativo por defecto;
* puede aparecer en consultas sobre propuestas pendientes;
* requiere revisión humana para avanzar.

Metadatos recomendados:

```yaml
status: proposed
approved: false
operational_context: false
retrieval_enabled: true
retrieval_scope: proposals
```

Transiciones permitidas:

```text
proposed → accepted
proposed → rejected
proposed → draft
proposed → archived
```

---

### 3.3 `accepted`

Contenido aprobado conceptualmente.

Se utiliza cuando:

* la propuesta fue revisada;
* existe aprobación humana explícita;
* el contenido fue aceptado como decisión, criterio o dirección;
* todavía puede requerir implementación, publicación o activación.

Reglas:

* puede orientar planificación futura;
* no demuestra que una capacidad esté implementada;
* debe indicar quién o qué proceso aprobó el contenido;
* debe registrar la fecha de aprobación;
* puede incorporarse al roadmap o backlog aprobado;
* debe diferenciarse de `active`.

Metadatos recomendados:

```yaml
status: accepted
approved: true
operational_context: true
implementation_status: pending
```

Transiciones permitidas:

```text
accepted → active
accepted → superseded
accepted → deprecated
accepted → archived
```

---

### 3.4 `active`

Contenido vigente y aplicable.

Se utiliza cuando:

* el documento forma parte del baseline vigente;
* la decisión está actualmente en efecto;
* la política debe cumplirse;
* la arquitectura descrita continúa siendo válida;
* el contenido fue aprobado y activado.

Reglas:

* puede utilizarse en contexto operativo;
* debe priorizarse en búsquedas y RAG;
* debe tener fuente y vigencia verificables;
* debe revisarse cuando cambie el baseline;
* cualquier contradicción con otro documento activo debe investigarse;
* no puede modificarse silenciosamente.

Metadatos recomendados:

```yaml
status: active
approved: true
operational_context: true
retrieval_enabled: true
retrieval_priority: high
```

Transiciones permitidas:

```text
active → superseded
active → deprecated
active → archived
```

---

### 3.5 `superseded`

Contenido reemplazado por una versión o decisión posterior.

Se utiliza cuando:

* existe un documento nuevo que lo sustituye;
* una decisión posterior modifica su criterio;
* una versión más reciente se convierte en referencia;
* su contenido deja de ser aplicable al baseline actual.

Reglas:

* debe conservarse por trazabilidad;
* debe identificar qué documento lo reemplazó;
* no debe aparecer en contexto operativo por defecto;
* puede recuperarse para auditoría histórica;
* no debe utilizarse para justificar decisiones actuales;
* sus enlaces deben apuntar al reemplazo vigente.

Metadatos recomendados:

```yaml
status: superseded
operational_context: false
retrieval_enabled: true
retrieval_scope: historical
superseded_by: DOC-ID
```

Transiciones permitidas:

```text
superseded → archived
```

No debe volver a `active` sin una decisión formal nueva.

---

### 3.6 `deprecated`

Contenido todavía existente, pero cuyo uso debe limitarse o eliminarse.

Se utiliza cuando:

* existe una alternativa recomendada;
* una interfaz sigue disponible por compatibilidad;
* una práctica está en proceso de retiro;
* un documento continúa siendo parcialmente aplicable;
* se planificó su reemplazo.

Reglas:

* debe indicar las limitaciones actuales;
* debe identificar la alternativa recomendada;
* debe indicar una fecha o condición de retiro cuando sea posible;
* puede aparecer en contexto operativo con advertencia;
* no debe utilizarse para nuevas implementaciones salvo excepción aprobada.

Metadatos recomendados:

```yaml
status: deprecated
operational_context: limited
retrieval_enabled: true
warning_required: true
replacement: DOC-ID
```

Transiciones permitidas:

```text
deprecated → superseded
deprecated → archived
deprecated → active
```

La transición a `active` requiere revisión y aprobación explícita.

---

### 3.7 `rejected`

Contenido evaluado y descartado.

Se utiliza cuando:

* una propuesta fue rechazada;
* un documento fue invalidado;
* un enfoque contradice la arquitectura;
* una idea no cumple con la gobernanza;
* el contenido no debe reutilizarse;
* existe riesgo de que vuelva a introducirse por error.

Reglas:

* no debe influir en decisiones vigentes;
* debe quedar excluido del contexto operativo;
* debe quedar excluido del RAG activo por defecto;
* debe conservarse únicamente si existe valor histórico o de auditoría;
* debe indicar el motivo del rechazo;
* no debe reutilizarse parcialmente sin una nueva evaluación formal.

Metadatos recomendados:

```yaml
status: rejected
approved: false
operational_context: false
retrieval_enabled: false
rejection_reason: required
```

Transiciones permitidas:

```text
rejected → archived
```

Un contenido rechazado no debe regresar directamente a `proposed` o `active`. Una nueva propuesta deberá generarse como artefacto independiente.

---

### 3.8 `archived`

Contenido preservado únicamente como referencia histórica, evidencia o auditoría.

Se utiliza cuando:

* finalizó su ciclo de vida;
* dejó de ser necesario para el trabajo corriente;
* se conserva por trazabilidad;
* pertenece a una versión antigua;
* documenta una sesión o estado histórico;
* no debe intervenir en decisiones actuales.

Reglas:

* debe permanecer fuera del contexto operativo;
* no debe recuperarse en consultas normales;
* puede utilizarse en auditorías o reconstrucciones históricas;
* debe conservar su origen y fecha;
* no debe editarse salvo para corregir metadatos o integridad.

Metadatos recomendados:

```yaml
status: archived
operational_context: false
retrieval_enabled: true
retrieval_scope: archive
immutable: true
```

Estado final por defecto.

---

## 4. Estados de implementación

El estado documental no debe confundirse con el estado de implementación.

Un documento puede estar `accepted`, pero la capacidad todavía no estar implementada.

Estados recomendados:

```yaml
implementation_status:
  - not_applicable
  - not_started
  - planned
  - in_progress
  - partially_implemented
  - implemented
  - validated
  - released
  - rolled_back
```

Ejemplo:

```yaml
status: accepted
implementation_status: planned
```

Esto significa que la decisión está aprobada, pero todavía no forma parte del baseline.

---

## 5. Estados de revisión

Cuando resulte necesario, podrá utilizarse un estado de revisión separado:

```yaml
review_status:
  - not_reviewed
  - under_review
  - changes_requested
  - reviewed
  - verified
```

Ejemplo:

```yaml
status: proposed
review_status: under_review
```

El estado de revisión no modifica por sí mismo la autoridad del documento.

---

## 6. Elegibilidad para contexto operativo

El campo `operational_context` determina si un documento puede formar parte del contexto utilizado en sesiones de trabajo.

Valores recomendados:

```yaml
operational_context:
  - true
  - false
  - limited
```

### `true`

El contenido puede utilizarse normalmente.

Aplicable a:

* documentos `active`;
* baseline vigente;
* decisiones aceptadas relevantes;
* roadmap aprobado;
* restricciones activas.

### `false`

El contenido debe excluirse.

Aplicable a:

* borradores;
* documentos rechazados;
* material archivado;
* contenido reemplazado;
* conversaciones sin formalizar.

### `limited`

El contenido puede utilizarse con advertencias.

Aplicable a:

* documentos deprecados;
* información parcialmente vigente;
* material histórico necesario para explicar una transición.

---

## 7. Elegibilidad para RAG

El campo `retrieval_enabled` determina si un contenido puede indexarse o recuperarse.

La habilitación de recuperación no implica que el contenido deba aparecer en todas las consultas.

Ejemplo:

```yaml
retrieval_enabled: true
retrieval_scope: historical
```

Ámbitos recomendados:

```yaml
retrieval_scope:
  - active
  - proposals
  - historical
  - archive
  - audit
  - excluded
```

El RAG deberá consultar por defecto únicamente:

```yaml
retrieval_scope:
  - active
```

Las propuestas, archivos históricos y documentos rechazados deberán requerir una consulta explícita o modo especializado.

---

## 8. Reglas de transición

Toda transición material debe registrar:

* estado anterior;
* estado nuevo;
* fecha;
* motivo;
* persona responsable;
* evidencia;
* documentos relacionados;
* impacto en el contexto operativo;
* impacto en índices o RAG.

Ejemplo:

```yaml
lifecycle_history:
  - from: proposed
    to: accepted
    date: 2026-07-20
    approved_by: owner
    reason: Architecture direction approved
```

---

## 9. Aprobación humana

Las siguientes transiciones requieren aprobación humana explícita:

```text
proposed → accepted
accepted → active
active → deprecated
active → superseded
deprecated → active
```

También requiere aprobación humana:

* cambiar autoridad documental;
* habilitar un documento rechazado para recuperación;
* modificar el baseline aplicable;
* declarar que una capacidad fue validada;
* alterar el estado de un documento constitucional o de gobernanza.

---

## 10. Revisión temporal

Los documentos vigentes deberán revisarse cuando ocurra alguno de los siguientes eventos:

* cierre de sprint;
* nueva release;
* cambio arquitectónico;
* aprobación de un ADR;
* modificación de gobernanza;
* detección de contradicción;
* auditoría;
* cambio de dependencia crítica;
* cambio de versión aplicable;
* incidente de seguridad.

Metadatos recomendados:

```yaml
last_reviewed: 2026-07-20
review_trigger:
  - release_change
  - architecture_change
```

---

## 11. Documentos sin estado

Cuando se encuentre un documento sin estado:

1. no asumir que está vigente;
2. identificar su origen;
3. verificar su relación con el baseline;
4. comparar con documentos superiores;
5. asignar un estado provisional;
6. solicitar revisión humana si puede afectar decisiones.

Estado provisional recomendado:

```yaml
status: draft
review_status: not_reviewed
operational_context: false
retrieval_enabled: false
```

---

## 12. Resúmenes y contexto generado

Los resúmenes generados automáticamente deberán:

* declararse como artefactos derivados;
* registrar las fuentes utilizadas;
* indicar fecha y hora de generación;
* identificar el baseline analizado;
* poder regenerarse;
* no introducir decisiones;
* quedar invalidados si cambia una fuente crítica.

Ejemplo:

```yaml
type: generated_summary
status: active
derived: true
source_documents:
  - DOC-BLUEPRINT-001
  - RELEASE-0.7
generated_at: 2026-07-20
```

Un resumen generado puede estar `active` como herramienta operativa, pero nunca superar la autoridad de sus fuentes.

---

## 13. Snapshots del repositorio

Los snapshots deberán representar un estado puntual del repositorio.

Deberán registrar:

* repositorio;
* rama;
* commit;
* fecha;
* working tree;
* estado de tests;
* herramientas utilizadas;
* resultado de validación.

Ejemplo:

```yaml
type: repository_snapshot
status: archived
branch: main
commit: abc1234
captured_at: 2026-07-20
tests_passed: 57
```

Los snapshots no deben modificarse una vez registrados.

---

## 14. Contradicciones de estado

Si un documento aparece marcado simultáneamente como:

```yaml
status: rejected
operational_context: true
```

o:

```yaml
status: superseded
retrieval_scope: active
```

debe considerarse inconsistente.

Ante una inconsistencia:

1. excluir el documento del contexto operativo;
2. suspender su recuperación automática;
3. registrar el hallazgo;
4. revisar manualmente sus metadatos;
5. corregir el estado antes de reutilizarlo.

La opción más restrictiva debe prevalecer hasta resolver la contradicción.

---

## 15. Matriz resumida

| Estado       |         Vigente | Contexto operativo |      RAG activo | Requiere aprobación |
| ------------ | --------------: | -----------------: | --------------: | ------------------: |
| `draft`      |              No |                 No |              No |                  No |
| `proposed`   |              No |                 No |              No |    Sí, para avanzar |
| `accepted`   | Conceptualmente |                 Sí |              Sí |                  Sí |
| `active`     |              Sí |                 Sí |              Sí |                  Sí |
| `superseded` |              No |                 No |              No |                  Sí |
| `deprecated` |        Limitado |           Limitado | Con advertencia |                  Sí |
| `rejected`   |              No |                 No |              No |  Sí, para registrar |
| `archived`   |              No |                 No |              No |                  No |

---

## 16. Principios rectores

> La existencia de un documento no demuestra su vigencia.

> Una propuesta aprobada no demuestra que haya sido implementada.

> Un artefacto histórico puede conservarse sin formar parte del contexto operativo.

> El contenido rechazado debe permanecer trazable, pero no influyente.

> Cuando el estado sea incierto, debe prevalecer la opción más restrictiva.
