---
document_id: VAULT-CURRENT-COMPONENTS-MAP-001
title: Mapa de componentes actuales
document_type: architecture
status: active
authority: derived
operational_authority: none
version: 1.2
created: 2026-07-20
last_reviewed: 2026-07-26
source_repository: Aranwill/jarvis
source_branch: main
source_commit: d1c90bf0bf55a7076d68c1f4830e89e0d843661c
baseline_reference: d1c90bf0bf55a7076d68c1f4830e89e0d843661c
tags:
  - malak
  - vault
  - architecture
  - components
  - kernel
---

# Mapa de componentes actuales

<!-- MALAK_VAULT_SYNC:START -->
## Proyección automática de sincronización

> [!warning] Estado derivado pendiente de revisión
> Este bloque fue generado de forma determinista a partir de
> `Aranwill/jarvis/main`. No aprueba decisiones, no cierra
> sprints y no reemplaza la revisión humana del documento.

- **Run ID:** `20260728T230427930525Z_38b0917c_da474149`
- **HEAD oficial observado:** `38b0917c5b8dba5c5a4ef4db157e78ac428ab4bc`
- **Commit previamente observado:** `695179aa491baeaf93189f271e6af9c611d84ca8`
- **Generado:** `2026-07-28T23:04:27.930525+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.5.md`
- **Título declarado:** Sprint 7.5 — Base del plano de control de seguridad
- **Estado declarado:** `en progreso`
- **`as_of_commit` declarado:** `af64b062aa1395ba7f7bdd59e5c1099ded68b683`

### Commits oficiales observados

- 38b0917c5b8dba5c5a4ef4db157e78ac428ab4bc	Merge pull request #23 from Aranwill/agent/sprint-7.5-pep-audit-integration
- 0ab64aeb646eb234df97b040f308cf2fd1333224	feat(security): integrate authorization audit into PEP
- 418358cc5b543c59cf4b113f42e762f6c78eec59	Merge pull request #22 from Aranwill/agent/sprint-7.5-authorization-audit-contracts
- 82c8c51f28e29340f798bfb4bacee596e92cd53a	feat(security): add authorization audit contracts

### Evidencia que originó esta proyección

- `architecture-change` por `src/malak/security/__init__.py`
- `architecture-change` por `src/malak/security/audit.py`
- `architecture-change` por `src/malak/security/pep.py`
<!-- MALAK_VAULT_SYNC:END -->

> [!warning] Naturaleza derivada
> Este documento representa únicamente relaciones verificadas en el repositorio oficial para el baseline indicado.
>
> No redefine la arquitectura, no documenta capacidades futuras y no posee autoridad operativa.

## 1. Alcance

Este mapa cubre las siguientes fronteras verificadas:

- `Request`;
- `Kernel`;
- `Planner`;
- `CapabilityRegistry`;
- `EchoCapability`;
- `Response`;
- CLI conversacional;
- eventos operativos;
- stores operativos.
- contratos fundamentales de autorización.
- Policy Decision Point mínimo.
- Policy Enforcement Point inicial.

Quedan fuera de alcance:

- integración formal entre Kernel y subsistema conversacional;
- detalle interno de proveedores y runtimes;
- métricas de runtime;
- auditoría de seguridad;
- auditoría de autorización;
- componentes propuestos en el roadmap.

Su exclusión de este documento no implica que no existan. Solamente evita mezclar subsistemas todavía no verificados dentro de este mapa.

Sprint 7.4 incorporó eventos operativos y correlación desde la CLI sin
modificar el flujo Kernel–Planner–Capability.

No existe integración formal entre `Kernel.receive` y `ConversationService`, y este mapa no propone ni autoriza dicha integración.

## 2. Baseline representado

- **Repositorio:** `Aranwill/jarvis`
- **Rama:** `main`
- **Commit:** `d1c90bf0bf55a7076d68c1f4830e89e0d843661c`
- **Versión nominal:** `v0.6.0-alpha`
- **Último sprint formalmente cerrado:** Sprint 7.4 — Consolidación de logs, métricas y auditoría
- **Sprint aprobado en progreso:** Sprint 7.5 — Base del plano de control de seguridad
- **Pull requests integrados en el rango:** PR #15, PR #16, PR #17, PR #18, PR #19 y PR #20
- **Suite integral documentada:** 244 pruebas aprobadas sobre `30b05587839cdac914e7ee31755bb5c0540862c1`
- **Incremento vigente:** Sprint 7.5, Incremento 4 completado e integrado

## 3. Componentes verificados

### `Request`

Contrato de entrada recibido por el Kernel.

Fuente:

```text
src/malak/core/request.py
```

### `Kernel`

Punto de entrada del flujo gobernado mínimo.

Responsabilidades verificadas:

- crear el Planner;
- crear el Capability Registry;
- validar solicitudes vacías;
- solicitar al Planner una capability;
- recuperar la capability desde el registro;
- ejecutar la capability;
- construir la respuesta.

Fuente:

```text
src/malak/kernel/kernel.py
```

### `Planner`

Selector determinista de capability.

Comportamiento actual:

```text
Siempre resuelve la capability "echo".
```

Fuente:

```text
src/malak/services/planner.py
```

### `CapabilityRegistry`

Registro en memoria de capabilities disponibles.

Responsabilidades verificadas:

- registrar capabilities;
- impedir nombres duplicados;
- recuperar una capability por nombre;
- listar capabilities registradas;
- normalizar nombres a minúsculas.

Fuente:

```text
src/malak/kernel/registry.py
```

### `EchoCapability`

Capability registrada durante el bootstrap del Kernel.

Fuente:

```text
src/malak/capabilities/echo.py
```

### `Response`

Contrato de salida construido por el Kernel.

Fuente:

```text
src/malak/core/response.py
```

### `OperationalEvent`

Contrato inmutable con allowlist de:

```text
event_name
component
occurred_at
outcome
request_id
reason_code
```

Fuente:

```text
src/malak/observability/operational_event.py
```

### `OperationalEventSink`

Contrato estructural de solo escritura:

```python
append(event: OperationalEvent) -> None
```

Fuente:

```text
src/malak/observability/operational_event_sink.py
```

### Stores operativos

Implementaciones verificadas:

```text
InMemoryOperationalEventStore
JsonlOperationalEventStore
```

Los stores permanecen separados de los stores de métricas.

Fuentes:

```text
src/malak/observability/operational_event_store.py
src/malak/observability/operational_event_jsonl_store.py
```

### Integración CLI

La CLI genera exclusivamente el `request_id` para cada intento
conversacional válido y emite:

```text
conversation.started
conversation.succeeded
conversation.failed
```

La dependencia del sink es opcional. `main()` no crea automáticamente
un store JSONL y no existe persistencia implícita.

Fuente:

```text
src/malak/app/cli.py
```

### Contratos fundamentales de autorización

El Sprint 7.5 incorporó cuatro contratos inmutables y desacoplados:

| Contrato | Responsabilidad verificada |
| --- | --- |
| `PermissionScope` | Identificar un recurso y una acción normalizados |
| `SecurityContext` | Identificar al sujeto y su estado de autenticación |
| `AuthorizationRequest` | Relacionar contexto, permiso, identificador y fecha trazable |
| `AuthorizationDecision` | Expresar un resultado binario y su razón |

Estos contratos:

- están expuestos mediante `malak.security`;
- separan solicitud y decisión;
- no ejecutan operaciones;
- no implementan políticas;
- no dependen de LLM;
- no modifican el Kernel, Planner ni runtimes.

Fuentes:

```text
src/malak/security/contracts.py
src/malak/security/__init__.py
tests/test_authorization_contracts.py
```

### Policy Decision Point mínimo

El Incremento 3 incorporó un punto de decisión determinista y
desacoplado:

| Componente | Responsabilidad verificada |
| --- | --- |
| `PolicyDecisionPoint` | Definir el contrato estructural de decisión |
| `StaticPolicyDecisionPoint` | Evaluar reglas exactas con denegación por defecto |
| `PolicyRule` | Relacionar sujeto, permiso y efecto explícitos |
| `PolicyEffect` | Representar `ALLOW`, `DENY` y `REQUIRE_HUMAN_CONFIRMATION` dentro del PDP |
| `HumanConfirmationEvidence` | Ligar de forma inmutable la confirmación a la solicitud original y a la nueva |
| `HumanConfirmationVerifier` | Separar la verificación de evidencia de la decisión |

La salida pública continúa siendo `AuthorizationDecision` binaria.
El PDP no admite comodines, herencia implícita, interpretación de texto
ni participación de LLM. La ausencia de regla, un sujeto no autenticado,
evidencia incongruente o un fallo del verificador producen denegación
segura.

El PDP no ejecuta operaciones. El enforcement permanece separado en el
PEP inicial descrito a continuación.

Fuentes:

```text
src/malak/security/pdp.py
src/malak/security/__init__.py
tests/test_policy_decision_point.py
docs/project/sprints/SPRINT-7.5.md
```

### Policy Enforcement Point inicial

El Incremento 4 incorporó una frontera de enforcement determinista y
fail-closed:

| Componente | Responsabilidad verificada |
| --- | --- |
| `PolicyEnforcementPoint` | Definir el contrato estructural de enforcement |
| `StrictPolicyEnforcementPoint` | Consultar al PDP inyectado, validar la decisión y controlar la ejecución |
| `ProtectedOperation` | Representar una operación protegida sin acoplarla al PEP |
| `AuthorizationDeniedError` | Diferenciar una denegación válida del PDP |
| `AuthorizationEnforcementError` | Bloquear fallos, tipos inválidos o decisiones incongruentes |

El PEP no acepta decisiones aportadas por el llamador. Consulta
directamente al PDP, verifica que la decisión corresponda al
`request_id` original y ejecuta la operación exactamente una vez solo
ante una autorización válida. Los fallos del PDP bloquean la operación;
los fallos de la operación se propagan sin reintento automático.

El incremento no conecta operaciones reales, no integra el PEP con
Kernel, Planner, CLI o runtimes y no incorpora todavía evidencia de
auditoría de autorización.

Fuentes:

```text
src/malak/security/pep.py
src/malak/security/__init__.py
tests/test_policy_enforcement_point.py
docs/architecture/adr/ADR-002-policy-enforcement-boundary.md
docs/project/sprints/SPRINT-7.5.md
```

## 4. Flujo implementado

```mermaid
flowchart LR
    Request[Request]
    Kernel[Kernel]
    Planner[Planner]
    Registry[CapabilityRegistry]
    Echo[EchoCapability]
    Response[Response]

    Request -->|receive| Kernel
    Kernel -->|resolve request| Planner
    Planner -->|capability name: echo| Kernel
    Kernel -->|get echo| Registry
    Registry -->|EchoCapability| Kernel
    Kernel -->|execute content| Echo
    Echo -->|result| Kernel
    Kernel -->|construct| Response
```

## 5. Flujo operativo conversacional

```mermaid
flowchart LR
    CLI[CLI]
    Service[ConversationService]
    Started[conversation.started]
    Final[conversation.succeeded / conversation.failed]
    Sink[OperationalEventSink]
    Memory[InMemoryOperationalEventStore]
    JSONL[JsonlOperationalEventStore]

    CLI -->|request_id generado en CLI| Started
    Started --> Sink
    CLI --> Service
    Service --> CLI
    CLI -->|mismo request_id| Final
    Final --> Sink
    Sink -. implementación .-> Memory
    Sink -. implementación .-> JSONL
```

Este flujo no se integra con `Kernel.receive`.

La observabilidad no posee semántica de autorización ni de auditoría
de seguridad.

## 6. Secuencia funcional

1. El sistema entrega un `Request` al método `Kernel.receive`.
2. El Kernel rechaza el contenido vacío.
3. El Kernel solicita al Planner el nombre de la capability.
4. El Planner devuelve actualmente `"echo"`.
5. El Kernel consulta el `CapabilityRegistry`.
6. El registro devuelve `EchoCapability`.
7. El Kernel ejecuta la capability con el contenido de la solicitud.
8. El Kernel construye un `Response`.
9. La respuesta identifica como fuente a la capability ejecutada.

## 7. Bootstrap verificado

El registro predeterminado se crea mediante:

```text
src/malak/kernel/bootstrap.py
```

El comportamiento verificado es:

1. crear una instancia de `CapabilityRegistry`;
2. crear y registrar `EchoCapability`;
3. devolver el registro inicializado.

Actualmente este documento no afirma que existan otras capabilities registradas por defecto.

## 8. Límites de la representación

Este mapa no afirma:

- que el Planner utilice un LLM;
- que exista planificación dinámica;
- que el Kernel invoque directamente un runtime LLM;
- que el subsistema conversacional forme parte de este flujo;
- que existan múltiples capabilities activas;
- que el registro sea persistente;
- que el diagrama represente toda la arquitectura de Malāk.
- que eventos operativos y métricas compartan contratos o stores;
- que exista auditoría de autorización;
- que la observabilidad adopte decisiones de autorización;
- que `ConversationRequest` contenga `request_id`.
- que los contratos de autorización concedan permisos por sí mismos.

## 9. Hallazgos arquitectónicos descriptivos

Sin convertirlos en decisiones nuevas, el código observado muestra:

- selección de capability separada de su ejecución;
- resolución determinista en el Planner actual;
- registro desacoplado mediante el contrato `Capability`;
- bootstrap explícito de capabilities;
- respuesta final construida por el Kernel;
- tratamiento explícito de solicitudes vacías y capabilities inexistentes.
- generación exclusiva de `request_id` en la CLI;
- contratos operativos separados de las métricas;
- persistencia operativa opcional e inyectada;
- degradación controlada ante fallos del sink;
- Kernel, Planner y contratos conversacionales intactos.
- solicitud, contexto, permiso y decisión representados por contratos
  separados e inmutables;
- PDP determinista separado de la ejecución;
- reglas exactas y denegación por defecto;
- evidencia de confirmación inmutable y verificador inyectable;
- PEP separado del PDP y de la operación protegida;
- enforcement fail-closed con asociación estricta por `request_id`;
- ausencia de integración con operaciones reales y de auditoría de
  autorización.

## 10. Fuentes oficiales

- `src/malak/kernel/kernel.py`
- `src/malak/kernel/bootstrap.py`
- `src/malak/kernel/registry.py`
- `src/malak/services/planner.py`
- `src/malak/contracts/capability.py`
- `src/malak/capabilities/echo.py`
- `src/malak/core/request.py`
- `src/malak/core/response.py`
- `src/malak/app/cli.py`
- `src/malak/observability/operational_event.py`
- `src/malak/observability/operational_event_sink.py`
- `src/malak/observability/operational_event_store.py`
- `src/malak/observability/operational_event_jsonl_store.py`
- `src/malak/security/contracts.py`
- `src/malak/security/pdp.py`
- `src/malak/security/pep.py`
- `src/malak/security/__init__.py`
- `tests/test_authorization_contracts.py`
- `tests/test_policy_decision_point.py`
- `tests/test_policy_enforcement_point.py`
- `docs/architecture/adr/ADR-002-policy-enforcement-boundary.md`
- `docs/project/sprints/SPRINT-7.4.md`
- `docs/project/sprints/SPRINT-7.5.md`

## 11. Navegación relacionada

- [[01-architecture/ARCHITECTURE_INDEX|Índice de arquitectura]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline vigente]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]
- [[09-repository-snapshots/SNAPSHOT_INDEX|Índice de snapshots]]
- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro]]

## 12. Próximos mapas posibles

Los siguientes mapas permanecen pendientes y no están aprobados automáticamente:

- mapa detallado del subsistema conversacional;
- mapa detallado de métricas y eventos operativos;
- mapa de contratos actuales;
- mapa de límites del Kernel.

Cada uno deberá verificarse separadamente contra el repositorio oficial.
