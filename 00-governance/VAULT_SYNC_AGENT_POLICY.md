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

# Política obligatoria del Vault Synchronization Agent

> [!warning] Estado
> Esta política se encuentra `under_review`.
> No autoriza implementación, ejecución automatica ni escritura sobre `main`.

## 1. Propósito principal

Mantener actualizado el Malāk Project Vault utilizado por Obsidian con los cambios verificados del repositorio oficial de Malāk.

El agente no otorgará autoridad operativa al Vault y no convertirá información derivada en fuente de verdad.

## 2. Fuente de verdad

La fuente operativa y documental principal continua siendo:

```text
Aranwill/jarvis
rama main
```

El Vault permanece como capa documental externa, representacion derivada e interfaz de navegacion para Obsidian.

## 3. Permisos sobre Malāk

Sobre `Aranwill/jarvis`, el agente tendrá exclusivamente permisos de lectura.

Podra verificar `HEAD`, leer commits y PR integradas, inspeccionar documentación, código, pruebas y configuración, recuperar evidencia de cierre de sprint y comparar estados entre commits.

No podrá crear ramas, modificar archivos, crear commits, abrir o aprobar PR, mergear, eliminar ramas, ejecutar cambios ni alterar configuración del repositorio.

## 4. Permisos sobre el Vault

Sobre `Aranwill/malak-project-vault`, y solo cuando exista implementación aprobada, podrá leer `main`, crear una rama documental desde un `HEAD` verificado, modificar rutas incluidas en una allowlist aprobada, crear archivos nuevos cuando corresponda, generar commits pequenos y trazables, abrir una PR draft y generar un informe de auditoría.

No podrá escribir directamente en `main`, aprobar PR, habilitar auto-merge, mergear, eliminar ramas protegidas, modificar snapshots existentes, cerrar decisiones sin aprobacion humana, convertir propuestas en decisiones, elevar permisos ni modificar sus propias politicas.

## 5. Exclusividad humana del merge

El merge final será realizado exclusivamente por el propietario humano después de revisar el diff completo, el informe de auditoría, los archivos creados y modificados, los cambios bloqueados, las contradicciones, los riesgos y el rollback.

El agente no podrá aprobar, mergear ni habilitar auto-merge antes, durante o después de su ejecución.

## 6. Informe obligatorio de ejecución

Toda ejecución que cree o modifique archivos del Vault deberá generar un informe dentro de la misma rama y PR.

Ubicacion:

```text
07-audits/vault-synchronization/
```

Nombre recomendado:

```text
YYYY-MM-DD_VAULT_SYNC_<RUN_ID>.md
```

Si el informe no puede generarse o validarse, la PR no deberá abrirse.

## 7. Contenido minimo del informe

El informe deberá incluir:

- identificador estable de ejecución;
- fecha y hora;
- version del agente y de la política;
- modo de ejecución;
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
- checklist de revisión humana.

## 8. Trazabilidad de cambios

Por cada archivo modificado se registrará:

- ruta;
- operación;
- motivo;
- evidencia de origen;
- rango de líneas antes;
- rango de líneas después;
- resumen estructurado;
- referencia al diff Git exacto.

La evidencia principal será: ruta, commit de rama, diff Git, rangos de líneas y resumen.

Por cada archivo creado se registrará ruta, propósito, evidencia, generador o renderer, cantidad de líneas y hash cuando sea posible.

## 9. Archivos deliberadamente no modificados

Los documentos evaluados y preservados deberan quedar registrados. Los snapshots historicos existentes deberan figurar como `unchanged` cuando hayan sido considerados.

## 10. Cambios bloqueados

Toda operación denegada deberá registrar archivo, cambio solicitado, resultado, razón, política aplicada y necesidad de revisión humana.

## 11. Contradicciones

El agente podrá detectar y reportar contradicciones, pero no resolvera automaticamente contradicciones de autoridad, arquitectura, gobernanza, seguridad, decisiones, roadmap o estado de sprint.

Ante una contradiccion critica, la operación afectada se bloqueará.

## 12. Validaciones obligatorias

Antes de abrir una PR draft se registraran:

- validación de repositorio y rama;
- validación de `HEAD` esperado;
- validación TOCTOU antes de escribir y antes de abrir la PR;
- validación de rutas permitidas;
- validación de snapshots inmutables;
- validación de enlaces internos y metadatos;
- validación de referencias de commit;
- escaneo de secretos;
- validación de tamano y alcance del diff;
- validación del informe de auditoría.

Estados permitidos: `PASS`, `FAIL`, `BLOCKED`, `NOT_APPLICABLE`.

## 13. Uso del LLM

El LLM podrá asistir en redaccion, resumen, explicacion de riesgos, deteccion auxiliar de ambiguedades y preparacion del cuerpo de la PR.

No podrá decidir autoridad, autorizar operaciones, aprobar archivos, convertir propuestas en decisiones, resolver contradicciones criticas, seleccionar permisos, determinar un merge ni modificar politicas.

Toda salida asistida por LLM quedará pendiente de revisión humana.

## 14. Reglas permanentes

- `POL-001` — `Aranwill/jarvis` será siempre de solo lectura.
- `POL-002` — No se escribira directamente en `main` del Vault.
- `POL-003` — Toda escritura requerira una rama nueva desde un `HEAD` verificado.
- `POL-004` — Toda propuesta se presentara mediante PR draft.
- `POL-005` — Los snapshots existentes son inmutables.
- `POL-006` — Un snapshot nuevo solo podrá proponerse ante un nuevo baseline oficial.
- `POL-007` — Una propuesta no podrá convertirse automaticamente en decisión.
- `POL-008` — Una decisión no podrá cerrarse sin evidencia formal y aprobacion humana.
- `POL-009` — Las contradicciones criticas bloquearan la operación afectada.
- `POL-010` — Los tipos documentales desconocidos se denegaran por defecto.
- `POL-011` — El LLM no tendrá autoridad de seguridad, gobernanza ni merge.
- `POL-012` — Toda ejecución deberá registrar evidencia, riesgos y rollback.
- `POL-013` — Toda ejecución con cambios deberá generar y validar un informe de auditoría en la misma rama y PR.
- `POL-014` — Solo el propietario humano podrá aprobar y mergear.
- `POL-015` — Al ser repositorios públicos, no se incluiran secretos, tokens, credenciales, claves ni datos sensibles.

## 15. Flujo obligatorio

```text
detectar
→ comparar
→ clasificar
→ validar
→ proponer
→ preparar cambios
→ generar informe de auditoría
→ validar nuevamente
→ abrir PR draft
→ revisión y merge humano
```

## 16. Estado

```text
Política: under_review
Implementación: no aprobada
Agente operativo: no implementado
Proximo sprint de Malāk: no definido
```
