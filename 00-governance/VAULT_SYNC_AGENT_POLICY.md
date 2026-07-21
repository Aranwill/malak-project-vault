---
document_id: VAULT-SYNC-AGENT-POLICY-001
title: Politica obligatoria del Vault Synchronization Agent
document_type: governance-policy
status: under_review
authority: proposal
operational_authority: none
version: 0.1
created: 2026-07-21
last_reviewed: 2026-07-21
source_repository: Aranwill/jarvis
source_branch: main
source_commit: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
vault_repository: Aranwill/malak-project-vault
vault_branch: main
vault_base_commit: e3c2786a22ee9a3584a8e4acc589e14fc891b938
implementation_approved: false
human_review_required: true
tags:
  - malak
  - vault
  - synchronization
  - governance
  - human-in-control
---

# Politica obligatoria del Vault Synchronization Agent

> [!warning] Estado
> Esta politica se encuentra `under_review`.
> No autoriza implementacion, ejecucion automatica ni escritura sobre `main`.

## 1. Proposito principal

Mantener actualizado el Malak Project Vault utilizado por Obsidian con los cambios verificados del repositorio oficial de Malak.

El agente no otorgara autoridad operativa al Vault y no convertira informacion derivada en fuente de verdad.

## 2. Fuente de verdad

La fuente operativa y documental principal continua siendo:

```text
Aranwill/jarvis
rama main
```

El Vault permanece como capa documental externa, representacion derivada e interfaz de navegacion para Obsidian.

## 3. Permisos sobre Malak

Sobre `Aranwill/jarvis`, el agente tendra exclusivamente permisos de lectura.

Podra verificar `HEAD`, leer commits y PR integradas, inspeccionar documentacion, codigo, pruebas y configuracion, recuperar evidencia de cierre de sprint y comparar estados entre commits.

No podra crear ramas, modificar archivos, crear commits, abrir o aprobar PR, mergear, eliminar ramas, ejecutar cambios ni alterar configuracion del repositorio.

## 4. Permisos sobre el Vault

Sobre `Aranwill/malak-project-vault`, y solo cuando exista implementacion aprobada, podra leer `main`, crear una rama documental desde un `HEAD` verificado, modificar rutas incluidas en una allowlist aprobada, crear archivos nuevos cuando corresponda, generar commits pequenos y trazables, abrir una PR draft y generar un informe de auditoria.

No podra escribir directamente en `main`, aprobar PR, habilitar auto-merge, mergear, eliminar ramas protegidas, modificar snapshots existentes, cerrar decisiones sin aprobacion humana, convertir propuestas en decisiones, elevar permisos ni modificar sus propias politicas.

## 5. Exclusividad humana del merge

El merge final sera realizado exclusivamente por el propietario humano despues de revisar el diff completo, el informe de auditoria, los archivos creados y modificados, los cambios bloqueados, las contradicciones, los riesgos y el rollback.

El agente no podra aprobar, mergear ni habilitar auto-merge antes, durante o despues de su ejecucion.

## 6. Informe obligatorio de ejecucion

Toda ejecucion que cree o modifique archivos del Vault debera generar un informe dentro de la misma rama y PR.

Ubicacion:

```text
07-audits/vault-synchronization/
```

Nombre recomendado:

```text
YYYY-MM-DD_VAULT_SYNC_<RUN_ID>.md
```

Si el informe no puede generarse o validarse, la PR no debera abrirse.

## 7. Contenido minimo del informe

El informe debera incluir:

- identificador estable de ejecucion;
- fecha y hora;
- version del agente y de la politica;
- modo de ejecucion;
- repositorios, ramas y HEAD involucrados;
- rama de trabajo;
- origen del disparador;
- autoridad operativa declarada;
- resultado y nivel de riesgo;
- resumen ejecutivo;
- evidencia consultada;
- archivos modificados y creados;
- archivos deliberadamente no modificados;
- cambios bloqueados;
- contradicciones detectadas;
- validaciones ejecutadas;
- riesgos;
- rollback;
- checklist de revision humana.

## 8. Trazabilidad de cambios

Por cada archivo modificado se registrara:

- ruta;
- operacion;
- motivo;
- evidencia de origen;
- rango de lineas antes;
- rango de lineas despues;
- resumen estructurado;
- referencia al diff Git exacto.

La evidencia principal sera: ruta, commit de rama, diff Git, rangos de lineas y resumen.

Por cada archivo creado se registrara ruta, proposito, evidencia, generador o renderer, cantidad de lineas y hash cuando sea posible.

## 9. Archivos deliberadamente no modificados

Los documentos evaluados y preservados deberan quedar registrados. Los snapshots historicos existentes deberan figurar como `unchanged` cuando hayan sido considerados.

## 10. Cambios bloqueados

Toda operacion denegada debera registrar archivo, cambio solicitado, resultado, razon, politica aplicada y necesidad de revision humana.

## 11. Contradicciones

El agente podra detectar y reportar contradicciones, pero no resolvera automaticamente contradicciones de autoridad, arquitectura, gobernanza, seguridad, decisiones, roadmap o estado de sprint.

Ante una contradiccion critica, la operacion afectada se bloqueara.

## 12. Validaciones obligatorias

Antes de abrir una PR draft se registraran:

- validacion de repositorio y rama;
- validacion de `HEAD` esperado;
- validacion TOCTOU antes de escribir y antes de abrir la PR;
- validacion de rutas permitidas;
- validacion de snapshots inmutables;
- validacion de enlaces internos y metadatos;
- validacion de referencias de commit;
- escaneo de secretos;
- validacion de tamano y alcance del diff;
- validacion del informe de auditoria.

Estados permitidos: `PASS`, `FAIL`, `BLOCKED`, `NOT_APPLICABLE`.

## 13. Uso del LLM

El LLM podra asistir en redaccion, resumen, explicacion de riesgos, deteccion auxiliar de ambiguedades y preparacion del cuerpo de la PR.

No podra decidir autoridad, autorizar operaciones, aprobar archivos, convertir propuestas en decisiones, resolver contradicciones criticas, seleccionar permisos, determinar un merge ni modificar politicas.

Toda salida asistida por LLM quedara pendiente de revision humana.

## 14. Reglas permanentes

- `POL-001` — `Aranwill/jarvis` sera siempre de solo lectura.
- `POL-002` — No se escribira directamente en `main` del Vault.
- `POL-003` — Toda escritura requerira una rama nueva desde un `HEAD` verificado.
- `POL-004` — Toda propuesta se presentara mediante PR draft.
- `POL-005` — Los snapshots existentes son inmutables.
- `POL-006` — Un snapshot nuevo solo podra proponerse ante un nuevo baseline oficial.
- `POL-007` — Una propuesta no podra convertirse automaticamente en decision.
- `POL-008` — Una decision no podra cerrarse sin evidencia formal y aprobacion humana.
- `POL-009` — Las contradicciones criticas bloquearan la operacion afectada.
- `POL-010` — Los tipos documentales desconocidos se denegaran por defecto.
- `POL-011` — El LLM no tendra autoridad de seguridad, gobernanza ni merge.
- `POL-012` — Toda ejecucion debera registrar evidencia, riesgos y rollback.
- `POL-013` — Toda ejecucion con cambios debera generar y validar un informe de auditoria en la misma rama y PR.
- `POL-014` — Solo el propietario humano podra aprobar y mergear.
- `POL-015` — Al ser repositorios publicos, no se incluiran secretos, tokens, credenciales, claves ni datos sensibles.

## 15. Flujo obligatorio

```text
detectar
→ comparar
→ clasificar
→ validar
→ proponer
→ preparar cambios
→ generar informe de auditoria
→ validar nuevamente
→ abrir PR draft
→ revision y merge humano
```

## 16. Estado

```text
Politica: under_review
Implementacion: no aprobada
Agente operativo: no implementado
Proximo sprint de Malak: no definido
```
