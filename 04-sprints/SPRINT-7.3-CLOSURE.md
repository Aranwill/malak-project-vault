---
document_id: VAULT-SPRINT-7.3-CLOSURE-001
title: Cierre del Sprint 7.3 — Conversation Provider Boundary Stabilization
document_type: sprint-closure
status: closed
authority: derived
operational_authority: none
created: 2026-07-21
last_reviewed: 2026-07-21
source_repository: Aranwill/jarvis
source_branch: main
baseline_start: fdb3ee922efc796e53ade1fc3abe4125f4072bd0
baseline_result: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
pull_request: 13
tags:
  - malak
  - vault
  - sprint
  - closure
  - conversation
  - provider
---

# Cierre del Sprint 7.3 — Conversation Provider Boundary Stabilization

> [!warning] Autoridad documental
> Este documento es un registro derivado del cierre verificado en `Aranwill/jarvis/main`.
>
> No reemplaza el código, las pruebas, el pull request, el historial Git ni la documentación oficial del repositorio.

## 1. Estado

- **Sprint:** 7.3
- **Estado:** cerrado
- **Pull request:** PR #13
- **Rama integrada:** `feature/sprint-7.3-conversation-provider-boundary`
- **Rama destino:** `main`
- **Merge commit:** `fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627`
- **Rama temporal:** eliminada local y remotamente
- **Próximo sprint aprobado:** ninguno

## 2. Baseline de inicio

```text
fdb3ee922efc796e53ade1fc3abe4125f4072bd0
```

Descripción:

```text
Merge pull request #12 from Aranwill/docs/documentation-source-consolidation
```

Estado documentado al inicio:

- último sprint cerrado: Sprint 7.2 — Runtime Metric Sink Contract;
- suite: 69 pruebas aprobadas;
- Kernel y subsistema conversacional separados;
- `MockConversationProvider` presentaba una denominación ambigua;
- `ConversationProviderRegistry` carecía de validaciones explícitas.

## 3. Objetivo

Estabilizar la frontera del subsistema conversacional entre:

```text
ConversationService
→ ConversationProviderRegistry
→ ConversationProvider
→ LLMRuntime
```

El sprint debía corregir ambigüedades de nombres y comportamiento sin modificar el Kernel, el Planner ni el contrato `Capability`.

## 4. Problema verificado

`MockConversationProvider` actuaba como adaptador genérico sobre cualquier implementación de `LLMRuntime`, incluida `OllamaRuntime`.

Su nombre no representaba su responsabilidad real.

Además, `ConversationProviderRegistry`:

- no normalizaba nombres;
- permitía sobrescrituras silenciosas;
- exponía un `KeyError` interno;
- no rechazaba nombres vacíos;
- no rechazaba registros duplicados.

`ConversationService` también necesitaba una frontera de responsabilidad más explícita.

## 5. Alcance implementado

- renombrado de `MockConversationProvider` a `RuntimeConversationProvider`;
- renombrado de `mock_provider.py` a `runtime_provider.py`;
- actualización de imports y pruebas;
- normalización de nombres mediante `strip().lower()`;
- rechazo de nombres vacíos;
- rechazo de registros duplicados;
- incorporación de `ConversationProviderNotFoundError`;
- encapsulación del `KeyError` interno del registry;
- listado ordenado de providers;
- responsabilidad mínima explícita de `ConversationService`;
- preservación de compatibilidad con `MockLLMRuntime`;
- preservación de compatibilidad con `OllamaRuntime`;
- preservación del comportamiento observable de la CLI;
- documentación oficial del sprint;
- archivado del borrador anterior no aprobado sin alterar su contenido.

## 6. Fuera de alcance confirmado

No se incorporaron:

- cambios en el Kernel;
- cambios en el Planner;
- cambios en `Capability`;
- nuevas Capabilities;
- integración entre `Kernel.receive` y `ConversationService`;
- nuevos runtimes;
- nuevos providers específicos;
- retries;
- fallback;
- logging;
- nuevas métricas;
- persistencia conversacional;
- memoria;
- auditoría;
- autorización;
- Security Control Plane;
- selección automática de modelos;
- cambios en timeout;
- cambios en `keep_alive`.

## 7. Archivos de código afectados

```text
src/malak/app/cli.py
src/malak/core/conversation_registry.py
src/malak/providers/runtime_provider.py
src/malak/services/conversation_service.py
```

Archivo retirado mediante renombrado:

```text
src/malak/providers/mock_provider.py
```

## 8. Pruebas afectadas

```text
tests/test_cli.py
tests/test_conversation_registry.py
tests/test_conversation_service.py
tests/test_runtime_integration.py
tests/test_runtime_provider.py
```

Archivo retirado mediante renombrado:

```text
tests/test_mock_provider.py
```

## 9. Commits del sprint

```text
50c34af refactor(conversation): clarify runtime provider role
dcd580e refactor(conversation): stabilize provider registry
d7eb1aa refactor(conversation): define minimal service boundary
739924f docs(sprints): archive superseded Sprint 7.3 draft
e354e7b docs(sprint): document Sprint 7.3 provider boundary
277b521 docs(sprint): complete Sprint 7.3 record
```

## 10. Pull request y merge

```text
PR #13 — Sprint 7.3 — Conversation Provider Boundary Stabilization
```

Resultado:

- PR revisado;
- sin conflictos con `main`;
- seis commits integrados;
- merge realizado;
- rama temporal eliminada;
- nuevo HEAD verificado en `main`.

Merge commit:

```text
fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
```

## 11. Validación post-merge

Suite completa:

```text
74 passed
```

Validaciones ejecutadas:

```powershell
.\.venv\Scripts\python.exe -m pytest -q
.\.venv\Scripts\python.exe -m compileall src tests
git diff --check
git status
```

Resultado:

- 74 pruebas aprobadas;
- compilación sin errores;
- diff sin errores de formato;
- working tree limpio;
- `main` alineada con `origin/main`;
- rama local del sprint eliminada.

## 12. Resultado arquitectónico

La ruta conversacional queda representada como:

```text
CLI
→ ConversationService
→ ConversationProviderRegistry
→ RuntimeConversationProvider
→ LLMRuntime
```

El registry ahora:

- normaliza nombres;
- rechaza nombres vacíos;
- rechaza duplicados;
- devuelve un error público explícito ante providers inexistentes;
- mantiene resultados ordenados.

`ConversationService`:

- resuelve el provider solicitado;
- delega la solicitud;
- devuelve la respuesta;
- no selecciona modelos;
- no selecciona runtimes;
- no implementa retries;
- no incorpora logging, métricas, persistencia ni gobernanza.

## 13. Separación vigente

Continúan existiendo dos rutas diferenciadas:

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

No existe integración formal entre `Kernel.receive` y `ConversationService`.

El cierre del Sprint 7.3 no autoriza ni propone dicha integración.

## 14. Riesgos controlados

### Renombrado puramente cosmético

Mitigado mediante estabilización real del comportamiento público del registry y pruebas específicas.

### Expansión de responsabilidades

Mitigada mediante límites explícitos en `RuntimeConversationProvider` y `ConversationService`.

### Regresión de la CLI

Mitigada mediante pruebas unitarias, de integración y de CLI.

### Exposición de errores internos

Mitigada mediante `ConversationProviderNotFoundError`.

## 15. Rollback

El rollback puede realizarse revirtiendo los commits del sprint.

La reversión restauraría:

- `MockConversationProvider`;
- `mock_provider.py`;
- comportamiento anterior del registry;
- ausencia de `ConversationProviderNotFoundError`;
- docstring anterior de `ConversationService`;
- pruebas y referencias anteriores.

El rollback no afectaría:

- Kernel;
- Planner;
- Capability Registry;
- runtimes;
- contratos conversacionales;
- métricas;
- configuración externa.

## 16. Validación de gobernanza

### ¿Respeta el Blueprint?

Sí. Mantiene contratos públicos y separación entre módulos.

### ¿Respeta la Constitución Cognitiva?

Sí. Aplica un cambio mínimo, verificable, proporcional y reversible.

### ¿Respeta la Constitución de Gobernanza?

Sí. Preserva trazabilidad, límites de responsabilidad, pruebas y rollback.

### ¿Simplifica o mantiene simple el Kernel?

Sí. El Kernel no fue modificado ni recibió dependencias nuevas.

## 17. Pendientes trasladados

El Sprint 7.3 no aprueba automáticamente trabajo posterior.

Permanecen pendientes de evaluación separada:

- selección del próximo sprint;
- momento de implementación del Security Control Plane;
- delimitación entre logs, métricas y auditoría;
- versionado y respaldo del Vault;
- Session Context Generator;
- RAG externo;
- auditor externo;
- Development Tooling Foundation.

## 18. Cierre

El Sprint 7.3 queda cerrado con:

- alcance implementado;
- validación completa;
- documentación oficial;
- PR integrado;
- baseline actualizado;
- rollback definido;
- sin ampliación no autorizada de arquitectura;
- sin próximo sprint aprobado.
