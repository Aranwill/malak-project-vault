---
document_id: VAULT-AUDIT-INDEX-001
title: Índice de auditorías
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-07-20
tags:
  - malak
  - vault
  - audits
  - navigation
---

# Índice de auditorías

> [!important] Naturaleza de las auditorías
> Las auditorías documentan observaciones, evidencia, riesgos y recomendaciones.
>
> Una auditoría no modifica automáticamente el repositorio, el roadmap, el baseline ni las decisiones del proyecto.

## Propósito

Esta sección está reservada para revisiones independientes o controladas sobre:

- arquitectura;
- seguridad;
- calidad de código;
- cumplimiento documental;
- coherencia entre repositorio y Vault;
- dependencias;
- pruebas;
- gobernanza;
- riesgos operativos.

## Estado actual

No existen auditorías formales registradas en este índice.

La ausencia de una auditoría no debe interpretarse como ausencia de riesgos ni como certificación del sistema.

## Navegación relacionada

- [[02-current-baseline/CURRENT_BASELINE|Baseline vigente]]
- [[06-security/SECURITY_INDEX|Seguridad]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Snapshot de referencia]]
- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro]]

## Estructura mínima futura

Toda auditoría deberá incluir:

- identificador estable;
- fecha;
- alcance;
- baseline evaluado;
- fuentes consultadas;
- metodología;
- evidencia;
- hallazgos;
- severidad o prioridad;
- riesgos;
- recomendaciones;
- limitaciones;
- estado de tratamiento;
- responsable de la decisión.

## Estados permitidos

- `draft`
- `under-review`
- `accepted`
- `partially-accepted`
- `rejected`
- `superseded`
- `closed`

## Reglas permanentes

- Separar evidencia de interpretación.
- No presentar inferencias como hechos confirmados.
- Vincular cada auditoría con el baseline evaluado.
- No alterar una auditoría cerrada para adaptarla a estados posteriores.
- Registrar las correcciones mediante documentos o revisiones nuevas.
- Las recomendaciones requieren aprobación antes de convertirse en trabajo.
- Los hallazgos no autorizan cambios automáticos.

## Informes de Vault Synchronization

- [[07-audits/vault-synchronization/2026-07-21_VAULT_SYNC_FOUNDATION_POLICY|Incorporación documental de Vault Synchronization Agent Foundation]]

Estado del informe: `proposed`.

El informe registra evidencia, límites, validaciones, riesgos y revisión humana pendiente.
