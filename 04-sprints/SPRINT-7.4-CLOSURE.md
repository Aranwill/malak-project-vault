---
document_id: VAULT-SPRINT-7.4-CLOSURE-001
title: Registro de cierre gobernado del Sprint 7.4
document_type: sprint-closure
status: in_progress
authority: derived
operational_authority: none
created: 2026-07-25
last_reviewed: 2026-07-25
source_repository: Aranwill/jarvis
source_branch: main
baseline_start: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
source_commit: 7cd7fcc811df01555837319ec4cac0a93ef94fff
pull_request: 14
vault_sync_run_id: 20260725T032607612120Z_7cd7fcc8_49858c60
tags:
  - malak
  - vault
  - sprint
  - sprint-7.4
  - closure
  - observability
---

# Registro de cierre gobernado del Sprint 7.4

> [!warning] Cierre formal pendiente
> Este documento registra evidencia derivada del cierre técnico y del
> Incremento 8 en ejecución.
>
> No declara formalmente cerrado el Sprint 7.4 mientras la ficha
> oficial en `Aranwill/jarvis/main` continúe con estado `en progreso`.

## 1. Estado

- **Sprint:** 7.4
- **Título:** Consolidación de logs, métricas y auditoría
- **Estado general:** en progreso
- **Incremento 7:** completado, validado y mergeado
- **Incremento 8:** en ejecución documental gobernada
- **Pull request:** PR #14
- **Rama integrada:** `feature/sprint-7.4-logs-metrics-audit`
- **Rama destino:** `main`
- **Merge commit:** `7cd7fcc811df01555837319ec4cac0a93ef94fff`
- **Sprint posterior aprobado:** ninguno

## 2. Baseline de inicio

```text
fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
```

Descripción:

```text
Merge pull request #13 from Aranwill/feature/sprint-7.3-conversation-provider-boundary
```

Estado documentado al inicio:

- Sprint 7.3 cerrado;
- suite de 74 pruebas aprobadas;
- métricas de runtime existentes;
- ausencia de contrato formal de eventos operativos;
- ausencia de auditoría de seguridad;
- Kernel y subsistema conversacional separados.

## 3. Objetivo

Establecer una frontera mínima y estable de observabilidad operativa,
manteniendo separados:

- métricas de rendimiento;
- logs o eventos operativos;
- evidencia de auditoría.

El sprint no implementó una plataforma general de observabilidad,
autorización ni auditoría de seguridad.

## 4. Resultado técnico

Se incorporaron:

- `OperationalEvent`;
- `OperationalEventSink`;
- `InMemoryOperationalEventStore`;
- `JsonlOperationalEventStore`;
- persistencia JSONL append-only separada de las métricas;
- límite de 4096 bytes por línea;
- integración opcional del sink en la CLI;
- generación exclusiva de `request_id` en la CLI;
- correlación entre `conversation.started` y el evento final;
- políticas explícitas ante fallos del sink o almacenamiento;
- pruebas deterministas de contratos, persistencia, privacidad y
  degradación.

## 5. Separación arquitectónica

Las métricas, los eventos operativos y la auditoría permanecen
separados.

No comparten:

- contratos;
- stores;
- políticas de error;
- políticas de retención;
- autoridad;
- un envelope universal.

Sólo pueden compartir convenciones mínimas de trazabilidad:

- identificadores;
- fechas UTC;
- nombres de eventos;
- nombres de componentes.

No se implementó:

- auditoría de seguridad;
- autorización;
- PDP;
- PEP;
- decisiones de seguridad;
- automatización basada en telemetría.

## 6. Privacidad

Los eventos operativos no registran:

- prompts;
- respuestas;
- contenido conversacional;
- secretos;
- credenciales;
- tokens;
- datos personales;
- modelos;
- proveedores;
- excepciones;
- campos adicionales.

La allowlist persistida contiene:

```text
event_name
component
occurred_at
outcome
request_id
reason_code
```

## 7. Compatibilidad

Permanecen intactos:

- Kernel;
- Planner;
- `ConversationService`;
- `ConversationRequest`;
- `ConversationResponse`;
- los demás contratos conversacionales;
- contratos y stores de métricas.

No se incorporaron dependencias externas.

`main()` no crea automáticamente un store JSONL y no existe
persistencia operativa implícita.

## 8. Validación integral

La validación integral fue ejecutada sobre:

```text
5b951918006c464745e1eb1e3816bde619fad8b1
```

Resultados:

```text
Pruebas específicas: 94 passed
Suite completa: 121 passed
compileall: PASS
git diff --check: PASS
Revisión de privacidad: PASS
Revisión arquitectónica: PASS
Rollback: PASS
Hallazgos bloqueantes: ninguno
```

Los commits posteriores al commit validado fueron exclusivamente
documentales.

Las pruebas y `compileall` no se presentan como reejecutados después
del merge.

## 9. Pull request y merge

```text
PR #14
Título: feat(observability): add operational events and CLI correlation
Base: main
Head: feature/sprint-7.4-logs-metrics-audit
Estado: MERGED
Merge commit: 7cd7fcc811df01555837319ec4cac0a93ef94fff
Fecha del merge: 2026-07-25T03:14:37Z
```

Alcance del PR:

```text
14 archivos modificados
2139 inserciones
44 eliminaciones
```

## 10. Evidencia del Vault Synchronization Agent

Ejecución read-only aprobada:

```text
run_id: 20260725T032607612120Z_7cd7fcc8_49858c60
generated_at: 2026-07-25T03:26:07.612120+00:00
mode: dry-run
source main: 7cd7fcc811df01555837319ec4cac0a93ef94fff
baseline anterior: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
Vault main: 49858c603c1b5ec533e26e8986b24c24d41d4dd5
changed files: 14
document candidates: 4
validation findings: 0
conclusion: pass
```

Referencia local:

```text
D:\Ollama\malak-vault-sync-agent\var\reports\20260725T032607612120Z_7cd7fcc8_49858c60\audit-report.md
D:\Ollama\malak-vault-sync-agent\var\evidence\20260725T032607612120Z_7cd7fcc8_49858c60
```

Hash de evidencia:

```text
18b9eeba722ad6838749c3adb66d43d5834883c8d294f7eb24994d68308a10fc
```

## 11. Deuda futura no bloqueante

Permanece fuera del alcance:

- validación adicional de identificadores;
- control de exposición de errores;
- rotación y límites de crecimiento;
- retención y eliminación;
- concurrencia;
- recuperación ante corrupción parcial;
- permisos del archivo persistido.

Estas observaciones no impiden el cierre técnico.

## 12. Rollback

El historial del sprint está dividido en commits incrementales para:

- activación documental;
- contrato de eventos;
- sink y store en memoria;
- persistencia JSONL;
- integración CLI;
- actualizaciones documentales.

La integración puede revertirse sin modificar:

- Kernel;
- Planner;
- `ConversationService`;
- contratos conversacionales;
- stores de métricas.

## 13. Estado del Incremento 8

El Incremento 8 permanece:

```text
en ejecución
```

Para completarlo se requiere:

1. revisión humana de esta propuesta;
2. aplicación de los cambios aprobados;
3. validación del diff;
4. commit documental;
5. publicación de una rama del Vault;
6. creación y revisión de un PR;
7. merge humano en `Aranwill/malak-project-vault/main`.

## 14. Condición de cierre formal

La fuente oficial:

```text
Aranwill/jarvis/main
docs/project/sprints/SPRINT-7.4.md
```

mantiene:

```text
status: en progreso
```

Después del merge de la actualización gobernada del Vault deberá
realizarse una actualización posterior en `Aranwill/jarvis/main` para:

- registrar la finalización del Incremento 8;
- actualizar el estado general de Sprint 7.4;
- registrar el commit o PR del Vault;
- eliminar la contradicción entre la fuente oficial y este registro
  derivado.

Hasta entonces:

```text
Sprint 7.4: en progreso
Incremento 7: completado, validado y mergeado
Incremento 8: en ejecución
Cierre formal: pendiente
```

## 15. Invariantes preservadas

- ningún snapshot histórico fue modificado;
- el agente operó en modo read-only;
- `Aranwill/jarvis` no fue modificado durante la ejecución del agente;
- el Vault no fue modificado automáticamente;
- el agente no creó ramas, commits, push ni PR;
- no se utilizó LLM;
- el Vault conserva autoridad operativa `none`;
- no se inició un sprint posterior.
