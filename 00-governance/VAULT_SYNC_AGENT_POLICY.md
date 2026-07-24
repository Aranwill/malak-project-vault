---
document_id: VAULT-SYNC-AGENT-POLICY-001
title: Política obligatoria del Vault Synchronization Agent
document_type: governance-policy
status: accepted
authority: approved_policy
operational_authority: none
version: 1.1
created: 2026-07-21
last_reviewed: 2026-07-24
source_repository: Aranwill/jarvis
source_branch: main
source_commit: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
vault_repository: Aranwill/malak-project-vault
vault_branch: main
vault_base_commit: 03032a7b2aaecb47c27c2e8e5bff3a2c04179bd2
agent_repository: Aranwill/malak-vault-sync-agent
agent_branch: main
agent_commit: ade622b99eaaed0a6342400db743d472aa30a3ae
implementation_approved: true
phase_1_status: completed
operationalization_status: completed
execution_mode: manual-on-demand
scheduler_enabled: false
phase_2_approved: false
human_review_required: true
tags:
  - malak
  - vault
  - synchronization
  - governance
  - human-in-control
---

# Política obligatoria del Vault Synchronization Agent

> [!important] Estado
> Esta política fue aprobada originalmente para el alcance de la Fase 1 y continúa rigiendo la operacionalización read-only sin ampliar permisos ni autoridad.
>
> La Fase 1 fue implementada, validada y cerrada.
>
> La operacionalización read-only fue integrada y validada. El modo vigente es la ejecución manual bajo demanda después de cada sesión aprobada de Malāk.
>
> No existe un scheduler activo, un servicio permanente ni un proceso del agente en segundo plano.
>
> La política no concede autoridad operativa al agente, no autoriza escritura sobre Malāk ni sobre el Vault y no aprueba fases posteriores.

## 1. Propósito principal

Regular el comportamiento del Vault Synchronization Agent como tooling documental externo, determinista y gobernado.

La política busca permitir:

- observación de `Aranwill/jarvis/main`;
- detección de drift documental;
- comparación de estados;
- validación de evidencia;
- generación de informes;
- trazabilidad reproducible;

sin otorgar autoridad operativa al agente ni convertir el Vault en fuente de verdad.

## 2. Fuente de verdad

La fuente de verdad operativa y documental principal continúa siendo:

```text
Aranwill/jarvis
rama main
```

El Vault permanece como:

- capa documental externa;
- representación derivada;
- interfaz de navegación para Obsidian;
- repositorio sin autoridad operativa.

Ante contradicción, prevalecerá la fuente con mayor autoridad documental.

## 3. Naturaleza y autoridad

```text
Naturaleza: tooling documental externo
Fase 1: completada
Operacionalización read-only: completada
Repositorio: Aranwill/malak-vault-sync-agent
Modo operativo: manual-on-demand
Scheduler activo: no
Autoridad operativa: none
Autoridad documental: none
Kernel afectado: no
Runtime afectado: no
```

El agente puede:

- observar;
- comparar;
- clasificar;
- validar;
- generar evidencia;
- generar informes locales.

El agente no puede:

- decidir;
- aprobar;
- modificar Malāk;
- modificar el Vault;
- cerrar decisiones;
- iniciar nuevas fases;
- ampliar sus permisos;
- modificar esta política;
- adquirir autoridad operativa.

## 4. Permisos sobre Malāk

Sobre `Aranwill/jarvis`, el agente tendrá exclusivamente permisos de lectura.

Puede:

- verificar `HEAD`;
- leer commits integrados;
- leer PR integradas;
- inspeccionar documentación;
- inspeccionar código;
- inspeccionar pruebas;
- inspeccionar configuración;
- recuperar evidencia de cierre de sprint;
- comparar estados entre commits.

No puede:

- crear ramas;
- modificar archivos;
- crear commits;
- ejecutar push;
- abrir PR;
- aprobar PR;
- mergear PR;
- eliminar ramas;
- ejecutar cambios;
- modificar configuración;
- ejecutar acciones operativas sobre Malāk.

## 5. Permisos sobre el Vault durante la Fase 1

Durante la Fase 1, sobre `Aranwill/malak-project-vault`, el agente tuvo exclusivamente permisos de lectura.

Puede:

- leer `main`;
- verificar `HEAD`;
- inspeccionar documentos;
- resolver documentos candidatos;
- validar rutas;
- validar Markdown;
- validar YAML;
- validar enlaces;
- validar hashes;
- validar metadatos;
- detectar contradicciones;
- generar evidencia local;
- generar informes locales.

No puede:

- modificar archivos del Vault;
- crear ramas;
- crear commits;
- ejecutar push;
- abrir PR;
- aprobar PR;
- habilitar auto-merge;
- mergear;
- eliminar ramas;
- modificar snapshots;
- cerrar decisiones;
- convertir propuestas en decisiones;
- elevar permisos;
- modificar sus propias políticas.

## 6. Exclusividad humana

Toda decisión material permanece bajo control humano.

El propietario humano conserva exclusivamente la autoridad para:

- aprobar una nueva fase;
- aprobar un cambio de alcance;
- conceder permisos;
- aprobar escritura documental;
- crear o autorizar ramas;
- aprobar commits;
- abrir o autorizar PR;
- aprobar y mergear;
- cerrar decisiones;
- modificar políticas;
- modificar arquitectura;
- aceptar riesgos;
- autorizar rollback.

La evidencia generada por el agente no constituye aprobación.

## 7. Evidencia e informe obligatorio

Toda ejecución deberá generar evidencia reproducible dentro del workspace externo del agente.

La evidencia mínima deberá incluir:

- identificador estable de ejecución;
- fecha y hora;
- versión del agente;
- versión de la política;
- modo de ejecución;
- repositorios observados;
- ramas observadas;
- HEAD verificados;
- autoridad operativa declarada;
- resultado;
- nivel de riesgo;
- evidencia consultada;
- documentos candidatos;
- validaciones ejecutadas;
- contradicciones detectadas;
- operaciones bloqueadas;
- riesgos;
- rollback;
- hashes cuando corresponda.

Durante la Fase 1, el informe permanece local y no modifica automáticamente el Vault.

En el modo operativo vigente, la evidencia y el informe continúan siendo artefactos locales del agente. Su revisión puede originar una propuesta humana de actualización documental, pero nunca una modificación automática ni una aprobación.

## 8. Trazabilidad

Toda evidencia deberá permitir reconstruir:

- qué repositorio fue observado;
- qué rama fue observada;
- qué commit fue utilizado;
- qué documentos fueron considerados;
- qué validaciones fueron ejecutadas;
- qué operación fue permitida;
- qué operación fue bloqueada;
- qué política fue aplicada;
- cuál fue el resultado;
- qué riesgo residual permanece.

La evidencia deberá separar siempre:

- hecho verificado;
- inferencia;
- propuesta;
- decisión;
- implementación.

## 9. Archivos deliberadamente no modificados

Los documentos evaluados y preservados deberán quedar registrados como `unchanged` cuando corresponda.

Los snapshots históricos existentes deberán permanecer inmutables.

Un snapshot nuevo solo podrá proponerse cuando cambie materialmente el baseline oficial de `Aranwill/jarvis/main`.

## 10. Cambios bloqueados

Toda operación denegada deberá registrar:

- archivo o recurso;
- operación solicitada;
- resultado;
- razón;
- política aplicada;
- necesidad de revisión humana.

Los estados admitidos son:

```text
PASS
FAIL
BLOCKED
NOT_APPLICABLE
```

## 11. Contradicciones

El agente puede detectar y reportar contradicciones.

No puede resolver automáticamente contradicciones relacionadas con:

- autoridad;
- arquitectura;
- gobernanza;
- seguridad;
- decisiones;
- roadmap;
- baseline;
- estado de sprint;
- snapshots;
- documentos normativos.

Ante una contradicción crítica, la operación afectada deberá bloquearse.

## 12. Validaciones obligatorias de Fase 1

La Fase 1 deberá validar como mínimo:

- repositorio esperado;
- rama esperada;
- `HEAD` esperado;
- comandos Git de solo lectura;
- ausencia de comandos Git de escritura;
- allowlist;
- denylist;
- rutas permitidas;
- snapshots inmutables;
- Markdown;
- YAML;
- enlaces internos;
- referencias de commit;
- hashes SHA-256;
- metadatos;
- límites de tamaño;
- límites de alcance;
- sanitización de evidencia;
- controles TOCTOU;
- invariantes de no modificación;
- estado persistente;
- `last_applied_commit`;
- informe de auditoría;
- resultado end-to-end.

## 13. Uso del LLM

Durante la Fase 1:

```text
LLM: no utilizado
```

El LLM no puede:

- decidir autoridad;
- autorizar operaciones;
- aprobar archivos;
- convertir propuestas en decisiones;
- resolver contradicciones críticas;
- seleccionar permisos;
- determinar un merge;
- modificar políticas;
- cerrar decisiones;
- iniciar fases.

El uso futuro de LLM requerirá una decisión independiente y aprobación humana explícita.

## 14. Reglas permanentes

- `POL-001` — `Aranwill/jarvis` será siempre de solo lectura.
- `POL-002` — La Fase 1 no escribirá en el Vault.
- `POL-003` — Toda ampliación de permisos requerirá una decisión independiente.
- `POL-004` — Ninguna fase posterior se inicia automáticamente.
- `POL-005` — Los snapshots existentes son inmutables.
- `POL-006` — Un snapshot nuevo solo podrá proponerse ante un nuevo baseline oficial.
- `POL-007` — Una propuesta no podrá convertirse automáticamente en decisión.
- `POL-008` — Una decisión no podrá cerrarse sin evidencia formal y aprobación humana.
- `POL-009` — Las contradicciones críticas bloquearán la operación afectada.
- `POL-010` — Los tipos documentales desconocidos se denegarán por defecto.
- `POL-011` — El LLM no tendrá autoridad de seguridad, gobernanza ni merge.
- `POL-012` — Toda ejecución deberá registrar evidencia, riesgos y rollback.
- `POL-013` — Toda evidencia deberá ser reproducible y trazable.
- `POL-014` — Solo el propietario humano podrá aprobar una ampliación de alcance.
- `POL-015` — No se incluirán secretos, tokens, credenciales, claves ni datos sensibles.
- `POL-016` — El agente no podrá modificar sus propias políticas.
- `POL-017` — El agente no podrá otorgarse permisos.
- `POL-018` — La evidencia no constituye aprobación.
- `POL-019` — `last_applied_commit` permanecerá en `null` mientras no exista escritura aprobada.
- `POL-020` — El agente permanecerá fuera del Kernel y del runtime.
- `POL-021` — La ejecución operativa vigente será manual y bajo demanda.
- `POL-022` — El agente deberá ejecutarse después de que los cambios aprobados hayan sido publicados o fusionados en `Aranwill/jarvis/main`.
- `POL-023` — No existirá scheduler activo, servicio permanente ni daemon sin una decisión independiente y aprobación humana explícita.
- `POL-024` — El repositorio remoto del agente no le concede autoridad sobre Malāk ni sobre el Vault.

## 15. Flujo obligatorio de Fase 1

```text
detectar
→ comparar
→ clasificar
→ resolver documentos candidatos
→ aplicar allowlist y denylist
→ validar
→ generar evidencia
→ generar informe
→ verificar hashes
→ comprobar invariantes
→ finalizar sin aplicar cambios
```

## 16. Controles verificados al cierre

```text
Workspace: D:\Ollama\malak-vault-sync-agent
Repositorio: Aranwill/malak-vault-sync-agent
Rama: main
HEAD: ade622b99eaaed0a6342400db743d472aa30a3ae
Gate 0 a Gate 9: cerrados
Suite completa: 165 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
Configuración privada: válida y excluida de Git
Ejecución manual: pass
Ejecución programada de validación: pass
Scheduler final: eliminado
Modo operativo: manual-on-demand
Malāk intacto: sí
Vault intacto: sí
last_applied_commit: null
Hashes SHA-256 verificados: sí
Autoridad operativa: none
```

Todos los comandos Git operativos auditados fueron clasificados como read-only.

## 17. Estado remoto y operacionalización del agente

```text
Remoto configurado: sí
Repositorio remoto: Aranwill/malak-vault-sync-agent
Rama remota: main
Upstream de main: origin/main
Working tree: limpio
HEAD: ade622b99eaaed0a6342400db743d472aa30a3ae
HEAD local y remoto: coincidentes
Respaldo remoto: completado
PR de operacionalización: #1 integrada
```

La existencia del repositorio remoto del agente constituye respaldo y trazabilidad de su propio código. No modifica su autoridad, no lo convierte en parte de Malāk y no le concede permisos de escritura sobre los repositorios observados.

Se validaron tanto la ejecución manual como una ejecución temporal mediante el Programador de tareas de Windows. Después de la validación, la tarea programada fue eliminada por decisión humana.

Estado operativo vigente:

```text
Modo: manual-on-demand
Scheduler activo: no
Servicio permanente: no
Daemon: no
Proceso en segundo plano: no
Autoridad operativa: none
```

El flujo autorizado es:

```text
avance aprobado de Malāk
→ merge o push a Aranwill/jarvis/main
→ ejecución manual de run-once
→ revisión humana de evidencia e informe
→ propuesta de actualización del Vault
→ aprobación del propietario
→ actualización documental gobernada
```

Los cambios exclusivamente locales y todavía no publicados en `origin/main` no constituyen el estado remoto que debe observar el agente.

## 18. Capacidades futuras no aprobadas

No están aprobadas:

- escritura documental;
- creación automática de ramas;
- creación automática de commits;
- apertura automática de PR draft;
- modificación automática del baseline;
- modificación de documentos normativos;
- modificación de snapshots;
- scheduler operativo;
- servicio permanente;
- daemon;
- webhooks;
- integración con GitHub para escritura;
- uso de LLM;
- automatización completa;
- integración con Kernel;
- integración con runtime;
- capacidades de Fase 2 y posteriores.

## 19. Condiciones para una ampliación futura

Cualquier ampliación requerirá:

1. necesidad concreta;
2. decisión independiente;
3. alcance explícito;
4. fuera de alcance;
5. permisos mínimos;
6. evaluación de riesgos;
7. modelo de amenazas;
8. rollback;
9. criterios de aceptación;
10. validación arquitectónica;
11. revisión de gobernanza;
12. aprobación humana explícita.

## 20. Evidencia de cierre

El cierre de la Fase 1 está documentado en:

- [[07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE|Informe de cierre de la Fase 1 del Vault Synchronization Agent]].

El cierre de la operacionalización read-only está documentado en:

- [[07-audits/vault-synchronization/2026-07-24_VAULT_SYNC_OPERATIONALIZATION_CLOSURE|Informe de cierre de la operacionalización read-only del Vault Synchronization Agent]].

El baseline final del agente se encuentra en:

```text
docs/PHASE_1_FINAL_BASELINE.md
```

## 21. Estado final

```text
Política: accepted
Fase 1: completed
Operacionalización read-only: completed
Repositorio del agente: Aranwill/malak-vault-sync-agent
HEAD del agente: ade622b99eaaed0a6342400db743d472aa30a3ae
Agente operativo: herramienta externa de solo lectura
Modo operativo: manual-on-demand
Scheduler activo: no
Autoridad operativa: none
Escritura sobre Malāk: no
Escritura sobre el Vault: no
Fase 2 y posteriores: no aprobadas
Próximo sprint de Malāk: no definido
```

La aprobación de esta política no concede autorización para ninguna capacidad fuera del alcance cerrado de la Fase 1.

