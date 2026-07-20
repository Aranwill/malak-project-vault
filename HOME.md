---

document_id: VAULT-HOME-001
title: Malāk Project Vault
document_type: navigation
status: active
authority: derived
operational_authority: none
repository_source: Aranwill/jarvis
repository_branch: main
last_reviewed: 2026-07-20
tags:

* malak
* vault
* navigation
* project-context

---

# Malāk Project Vault

> [!warning] Naturaleza del Vault
> Este Vault es una capa documental derivada, auxiliar y no operativa.
>
> El repositorio oficial `Aranwill/jarvis`, sobre la rama `main`, conserva la fuente de verdad para el código, las pruebas, la documentación oficial y el estado operativo de Malāk.
>
> Ningún contenido de este Vault puede modificar Malāk automáticamente.

## Estado actual

* **Repositorio oficial:** `Aranwill/jarvis`
* **Rama oficial y única:** `main`
* **Baseline verificado:** `fdb3ee922efc796e53ade1fc3abe4125f4072bd0`
* **Versión nominal:** `v0.6.0-alpha`
* **Último sprint cerrado:** Sprint 7.2 — Runtime Metric Sink Contract
* **Pruebas verificadas:** 69 aprobadas
* **Próximo sprint:** no aprobado
* **Control de decisiones:** Human in Control

Abrir el estado completo:

* [[02-current-baseline/CURRENT_BASELINE|Current Baseline]]
* [[08-session-context/MALAK_SESSION_CONTEXT|Contexto vigente de sesión]]
* [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Snapshot del repositorio]]

---

## Navegación principal

### Gobernanza

Reglas que controlan el uso, actualización y autoridad documental del Vault.

* [[00-governance/GOVERNANCE_INDEX|Índice de gobernanza]]
* [[00-governance/VAULT_GOVERNANCE|Gobernanza del Vault]]
* [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
* [[00-governance/CONTENT_LIFECYCLE|Ciclo de vida del contenido]]

### Arquitectura

Contexto arquitectónico derivado y referencias hacia las fuentes oficiales correspondientes.

* [[01-architecture|Arquitectura]]

### Baseline vigente

Representación derivada del estado oficialmente verificado del proyecto.

* [[02-current-baseline/CURRENT_BASELINE|Baseline actual]]

### Roadmap

Planificación consolidada y líneas futuras registradas.

> [!important]
> La presencia de una iniciativa en el roadmap no implica aprobación para implementarla.

* [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]

### Sprints

Registro documental de sprints propuestos, activos y cerrados.

* [[04-sprints/SPRINT_INDEX|Sprints]]

### Decisiones

Decisiones pendientes o sujetas a aprobación explícita.

* [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]

### Seguridad

Contexto y documentación derivada relacionada con seguridad, autoridad y control.

* [[06-security/SECURITY_INDEX|Seguridad]]

### Auditorías

Hallazgos, revisiones y evaluaciones independientes.

* [[07-audits/AUDIT_INDEX|Auditorías]]

### Contexto de sesión

Punto de continuidad compacto para nuevas sesiones de trabajo.

* [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]

### Snapshots del repositorio

Capturas históricas, inmutables y derivadas del repositorio oficial.

* [[09-repository-snapshots/SNAPSHOT_INDEX|Índice de snapshots]]
* [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Snapshot 2026-07-20 — main — fdb3ee9]]

### Índice maestro

Navegación transversal por documentos, conceptos y relaciones.

* [[10-knowledge-index/KNOWLEDGE_INDEX|Knowledge Index]]

### Plantillas

Estructuras controladas para documentar sesiones y cierres de sprint.

* [[templates/SESSION_CLOSE_TEMPLATE|Plantilla de cierre de sesión]]
* [[templates/SPRINT_CLOSE_TEMPLATE|Plantilla de cierre de sprint]]
* [[templates/TEMPLATE_INDEX|Índice de plantillas]]

---

## Flujo recomendado de trabajo

1. Abrir [[08-session-context/MALAK_SESSION_CONTEXT|MALAK_SESSION_CONTEXT]].
2. Confirmar el estado representado en [[02-current-baseline/CURRENT_BASELINE|CURRENT_BASELINE]].
3. Consultar [[05-decisions/PENDING_DECISIONS|PENDING_DECISIONS]].
4. Definir explícitamente el objetivo de la sesión.
5. Trabajar sobre el repositorio oficial cuando exista implementación.
6. Validar el repositorio oficial.
7. Actualizar los documentos derivados que correspondan.
8. Crear un snapshot solo cuando se necesite preservar un estado histórico.
9. Cerrar la sesión mediante [[templates/SESSION_CLOSE_TEMPLATE|SESSION_CLOSE_TEMPLATE]].

---

## Reglas permanentes

* El repositorio oficial es la fuente de verdad.
* El Vault no posee autoridad operativa.
* Obsidian es únicamente una interfaz de navegación.
* Los snapshots históricos son inmutables.
* No se sobrescribe un snapshot existente.
* Las decisiones futuras requieren aprobación humana explícita.
* Una propuesta no es una decisión.
* Un documento derivado no puede reemplazar una fuente oficial.
* Ningún mecanismo del Vault puede ejecutar cambios automáticos sobre Malāk.
* Ante contradicción, prevalece la fuente con mayor autoridad documental.

---

## Control de continuidad

### Antes de comenzar una sesión

* [ ] Leer el contexto vigente.
* [ ] Confirmar el baseline referenciado.
* [ ] Revisar decisiones pendientes.
* [ ] Definir el alcance de trabajo.
* [ ] Confirmar si la tarea es documental o afecta el repositorio oficial.

### Antes de cerrar una sesión

* [ ] Registrar las decisiones efectivamente aprobadas.
* [ ] Diferenciar hechos, propuestas y pendientes.
* [ ] Actualizar el contexto de sesión.
* [ ] Actualizar el baseline solo si cambió el repositorio oficial.
* [ ] Crear un snapshot únicamente cuando corresponda.
* [ ] Confirmar que el Vault no adquirió autoridad operativa.

---

## Accesos rápidos

* [[02-current-baseline/CURRENT_BASELINE|¿Dónde estamos?]]
* [[03-roadmap/IMPLEMENTATION_ROADMAP|¿Hacia dónde podríamos avanzar?]]
* [[05-decisions/PENDING_DECISIONS|¿Qué falta decidir?]]
* [[08-session-context/MALAK_SESSION_CONTEXT|¿Qué debe conocer una nueva sesión?]]
* [[10-knowledge-index/KNOWLEDGE_INDEX|¿Dónde está cada conocimiento?]]
