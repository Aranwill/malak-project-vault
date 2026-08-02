---
document_id: VAULT-SYNC-AGENT-POLICY-001
title: Política obligatoria del Vault Synchronization Agent
document_type: governance-policy
status: accepted
authority: approved_policy
operational_authority: none
version: 1.2
created: 2026-07-21
last_reviewed: 2026-08-01
source_repository: Aranwill/jarvis
source_branch: main
source_commit: b4d1d512fe953d593608391390f82ab500fdc9d6
vault_repository: Aranwill/malak-project-vault
vault_branch: main
vault_base_commit: f433b9efc426ba52141a1a3daed81795fc666e6f
agent_repository: Aranwill/malak-vault-sync-agent
agent_branch: main
agent_commit: 0feed6eae3d3919ea4867891c12eda5eea81c511
implementation_approved: true
phase_1_status: completed
operationalization_status: completed
execution_mode: manual-on-demand
controlled_proposal_status: approved
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
> Esta política fue aprobada originalmente para la Fase 1 read-only y
> ahora incorpora la extensión independiente y gobernada
> `controlled-proposal`.
>
> La Fase 1 fue implementada, validada y cerrada.
>
> El modo vigente es manual bajo demanda. `dry-run` conserva el alcance
> read-only; `controlled-proposal` puede preparar una propuesta únicamente
> en una rama aislada del Vault.
>
> No existe un scheduler activo, un servicio permanente ni un proceso del agente en segundo plano.
>
> La política no concede autoridad operativa, no autoriza escritura sobre
> Malāk ni sobre `main` del Vault y no aprueba Fase 2 ni fases posteriores.
> La revisión, aceptación, rechazo y merge continúan bajo autoridad humana.

## 1. Propósito principal

Regular el comportamiento del Vault Synchronization Agent como tooling documental externo, determinista y gobernado.

La política busca permitir:

- observación de `Aranwill/jarvis/main`;
- detección de drift documental;
- comparación de estados;
- validación de evidencia;
- generación de informes;
- trazabilidad reproducible;
- preparación determinista de propuestas documentales aisladas;

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
Modos autorizados: dry-run y controlled-proposal
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
- preparar cambios deterministas en documentos allowlisted del Vault;
- crear una rama aislada de propuesta;
- crear commits trazables en esa rama;
- publicar la rama;
- abrir una PR draft.

El agente no puede:

- decidir;
- aprobar;
- modificar Malāk;
- escribir directamente en `main` del Vault;
- modificar documentos fuera del allowlist;
- modificar snapshots históricos;
- aprobar, habilitar auto-merge o mergear PR;
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

## 5. Permisos sobre el Vault

Durante la Fase 1 histórica, el agente tuvo exclusivamente permisos de
lectura sobre `Aranwill/malak-project-vault`.

En el modo vigente `controlled-proposal`, la extensión aprobada permite
escritura técnica limitada a una rama aislada creada desde el `main`
remoto verificado. Esta capacidad prepara una propuesta; no constituye
autoridad documental ni aplicación automática.

Puede:

- leer `main`;
- verificar `HEAD`;
- inspeccionar documentos;
- resolver documentos candidatos;
- validar rutas;
- validar Markdown;
- validar archivos YAML independientes;
- validar enlaces Markdown relativos;
- validar hashes;
- validar metadatos;
- detectar contradicciones;
- generar evidencia local;
- generar informes locales.
- avanzar el `main` local limpio únicamente mediante `fast-forward` hacia
  `origin/main`;
- crear un worktree temporal desde el `origin/main` verificado;
- modificar únicamente documentos derivados allowlisted;
- crear commits de contenido y auditoría;
- publicar únicamente una rama con el prefijo autorizado;
- abrir únicamente una PR draft dirigida a `main`;
- persistir la identidad de la propuesta pendiente después de completar
  el circuito remoto.

En `main@0feed6e`, estas capacidades no incluyen todavía validación del
frontmatter YAML de documentos Markdown, validación de wikilinks ni
revalidación del contenido final después de insertar la proyección.
Tampoco existe recuperación completa si la PR fue creada y falla la
persistencia posterior de su identidad. Son brechas técnicas conocidas,
no permisos implícitos ni controles verificados.

No puede:

- escribir directamente en `main` local o remoto del Vault;
- realizar `push --force` o reescribir historia;
- crear ramas fuera del prefijo autorizado;
- modificar documentos fuera del allowlist;
- modificar documentos normativos por inferencia;
- aprobar PR;
- habilitar auto-merge;
- mergear;
- eliminar ramas;
- modificar snapshots;
- cerrar decisiones;
- convertir propuestas en decisiones;
- elevar permisos;
- modificar sus propias políticas.

Una configuración que omita el push, la PR draft, el prefijo de rama o
la identidad exacta de los repositorios deberá ser rechazada.

## 6. Exclusividad humana

Toda decisión material permanece bajo control humano.

El propietario humano conserva exclusivamente la autoridad para:

- aprobar una nueva fase;
- aprobar un cambio de alcance;
- conceder permisos;
- autorizar la ejecución del modo `controlled-proposal`;
- revisar el contenido y la auditoría de cada propuesta;
- aceptar o rechazar la propuesta;
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

Durante la Fase 1, el informe permaneció local y no modificó el Vault.

En `dry-run`, la evidencia y el informe continúan siendo artefactos
locales. En `controlled-proposal`, el informe auditable puede incorporarse
a la misma rama aislada después del commit de contenido. Su presencia en
la rama o en la PR no constituye aprobación ni merge.

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

### 12.1 Requisitos obligatorios de `controlled-proposal`

Antes de declarar conformidad técnica completa, el modo deberá:

- revalidar cada documento Markdown después de escribir la proyección;
- validar el frontmatter YAML delimitado por `---`;
- validar enlaces Markdown relativos y wikilinks de Obsidian;
- bloquear explícitamente `09-repository-snapshots/**` en la denylist,
  además de mantener esa ruta fuera del allowlist;
- persistir o recuperar de forma inequívoca la identidad de una rama o
  PR creada antes de cualquier fallo local posterior;
- registrar `triggered_by: manual-on-demand` mientras ese sea el modo
  operativo vigente.

La corrección de estas brechas requiere un incremento técnico separado y
aprobación humana explícita. Esta política no lo inicia automáticamente.

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
- `POL-019` — `last_applied_commit` permanecerá siempre en `null`; una propuesta no equivale a aplicación.
- `POL-020` — El agente permanecerá fuera del Kernel y del runtime.
- `POL-021` — La ejecución operativa vigente será manual y bajo demanda.
- `POL-022` — El agente deberá ejecutarse después de que los cambios aprobados hayan sido publicados o fusionados en `Aranwill/jarvis/main`.
- `POL-023` — No existirá scheduler activo, servicio permanente ni daemon sin una decisión independiente y aprobación humana explícita.
- `POL-024` — El repositorio remoto del agente no le concede autoridad sobre Malāk ni sobre el Vault.
- `POL-025` — `controlled-proposal` solo escribirá en una rama aislada del Vault creada desde el `origin/main` verificado.
- `POL-026` — Toda PR creada por el agente permanecerá en draft hasta una decisión humana.
- `POL-027` — El agente no aprobará, habilitará auto-merge ni mergeará una PR.
- `POL-028` — El agente no realizará force-push ni reescribirá historia.
- `POL-029` — Una propuesta pendiente bloqueará la creación de otra propuesta hasta su reconciliación humana.
- `POL-030` — Aceptar o rechazar una propuesta exigirá identidad remota verificable y una decisión humana explícita.

## 15. Flujos obligatorios

### 15.1 `dry-run`

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

### 15.2 `controlled-proposal`

Flujo normativo aprobado:

```text
ejecutar manualmente
→ verificar repositorios, ramas, HEAD y working trees
→ detectar y validar candidatos allowlisted
→ crear worktree y rama aislada desde origin/main del Vault
→ escribir y validar la proyección final
→ crear commit documental
→ generar y validar informe auditable
→ crear commit de auditoría
→ publicar la rama sin force-push
→ abrir PR draft
→ persistir la identidad exacta de la propuesta pendiente
→ detenerse para revisión humana
```

El flujo anterior expresa el contrato obligatorio. El baseline
`main@0feed6e` implementa el núcleo de propuesta, pero todavía no satisface
todos los controles enumerados en 12.1.

## 16. Controles verificados al cierre

```text
Workspace: D:\Ollama\malak-vault-sync-agent
Repositorio: Aranwill/malak-vault-sync-agent
Rama: main
HEAD: 0feed6eae3d3919ea4867891c12eda5eea81c511
Gate 0 a Gate 9: cerrados
Suite completa: 230 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
Configuración privada: válida y excluida de Git
Ejecución manual: pass
Controlled-proposal: núcleo implementado y validado
Conformidad técnica completa: pendiente
Estado persistente: esquema v3 reconciliado
Incremento 4: cerrado
Scheduler final: eliminado
Modo operativo: manual-on-demand
Malāk intacto: sí
Vault main intacto: sí
last_applied_commit: null
Hashes SHA-256 verificados: sí
Autoridad operativa: none
```

`230 passed`, `compileall`, `git diff --check` y el resultado end-to-end
son evidencia válida de su alcance probado. No acreditan validación de
frontmatter, wikilinks, contenido final pos-escritura, denylist corregida
ni recuperación posterior a la creación de una PR.

Los comandos sobre Malāk permanecen read-only. Las operaciones de
escritura autorizadas están limitadas a la rama aislada de propuesta del
Vault y a la persistencia local del estado.

## 17. Estado remoto y operacionalización del agente

```text
Remoto configurado: sí
Repositorio remoto: Aranwill/malak-vault-sync-agent
Rama remota: main
Upstream de main: origin/main
Working tree: limpio
HEAD: 0feed6eae3d3919ea4867891c12eda5eea81c511
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
→ rama y PR draft de actualización del Vault
→ revisión y decisión humanas
→ merge exclusivamente humano o cierre sin merge
→ reconciliación local explícita de la propuesta
```

Los cambios exclusivamente locales y todavía no publicados en `origin/main` no constituyen el estado remoto que debe observar el agente.

## 18. Capacidades no aprobadas

No están aprobadas:

- escritura directa en `main` del Vault;
- escritura fuera del allowlist documental;
- creación autónoma de propuestas sin invocación manual;
- force-push o reescritura de historia;
- aprobación, auto-merge o merge de PR;
- modificación automática del baseline;
- modificación de documentos normativos;
- modificación de snapshots;
- scheduler operativo;
- servicio permanente;
- daemon;
- webhooks;
- integración con GitHub distinta de la rama y PR draft autorizadas;
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

El cierre técnico y operativo del estado v3 está documentado en el
repositorio del agente:

```text
docs/INCREMENT_4_CLOSURE.md
PR #6
merge commit: 0feed6eae3d3919ea4867891c12eda5eea81c511
```

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
HEAD del agente: 0feed6eae3d3919ea4867891c12eda5eea81c511
Agente operativo: herramienta externa con propuesta controlada
Modo operativo: manual-on-demand
Modos autorizados: dry-run y controlled-proposal
Conformidad de controlled-proposal: corrección técnica pendiente
Scheduler activo: no
Autoridad operativa: none
Escritura sobre Malāk: no
Escritura sobre el Vault: solo rama aislada de propuesta
Fase 2 y posteriores: no aprobadas
Próximo sprint de Malāk: no definido
```

La aprobación de esta política no concede autorización para ninguna
capacidad fuera de la Fase 1 histórica y de la extensión
`controlled-proposal` delimitada en `DEC-RES-009`.
