---
document_id: VAULT-SYNC-FOUNDATION-001
title: Vault Synchronization Agent Foundation
document_type: architecture
status: accepted
authority: approved_architecture
operational_authority: none
version: 1.2
created: 2026-07-21
last_reviewed: 2026-08-01
source_repository: Aranwill/jarvis
source_branch: main
source_commit: b4d1d512fe953d593608391390f82ab500fdc9d6
vault_repository: Aranwill/malak-project-vault
vault_branch: main
vault_base_commit_before_update: f433b9efc426ba52141a1a3daed81795fc666e6f
agent_repository: Aranwill/malak-vault-sync-agent
agent_branch: main
agent_head: 0feed6eae3d3919ea4867891c12eda5eea81c511
implementation_approved: true
phase_1_status: completed
operationalization_status: completed
execution_mode: manual-on-demand
controlled_proposal_status: approved
scheduler_enabled: false
phase_2_approved: false
runtime_component: false
kernel_component: false
tags:
  - malak
  - vault
  - obsidian
  - synchronization
  - architecture
---

# Vault Synchronization Agent Foundation

## 1. Propósito

Definir y documentar una fundación externa para observar `Aranwill/jarvis/main`, detectar drift documental y generar evidencia verificable para el Malāk Project Vault sin otorgar autoridad operativa al agente ni al Vault.

La fundación read-only fue implementada, respaldada y operacionalizada
en Windows. Posteriormente se aprobó de forma independiente la extensión
acotada `controlled-proposal` para preparar propuestas documentales en
ramas aisladas del Vault.

El modo vigente es manual bajo demanda, posterior a cada sesión aprobada de Malāk y una vez publicados o fusionados los cambios legítimos en `Aranwill/jarvis/main`.

La iniciativa busca reducir:

- referencias de baseline desactualizadas;
- contradicciones documentales;
- pérdida de contexto entre sesiones;
- trabajo manual repetitivo;
- riesgo de interpretar evidencia derivada como fuente de verdad.

La fuente de verdad operativa continúa siendo:

```text
Aranwill/jarvis
rama main
```

El Vault permanece como una capa documental derivada, externa y sin autoridad operativa.

## 2. Naturaleza

```text
Naturaleza: tooling documental externo
Ubicación: fuera del runtime de Malāk
Estado arquitectónico: accepted
Fase 1: implementada y cerrada
Operacionalización read-only: completed
Modo operativo: manual-on-demand
Modos autorizados: dry-run y controlled-proposal
Scheduler activo: no
Autoridad operativa: none
Kernel afectado: no
Runtime afectado: no
```

No forma parte de:

- Kernel;
- Planner;
- Capability Registry;
- ConversationService;
- LLMRuntime;
- CLI;
- runtime de Malāk;
- Security Control Plane.

La Fase 1 read-only permanece cerrada. `controlled-proposal` es una
extensión independiente, explícita y limitada; no reabre la Fase 1, no
autoriza la Fase 2 y no concede autoridad decisoria.

## 3. Ubicación y separación

Workspace externo verificado:

```text
D:\Ollama\malak-vault-sync-agent
```

Repositorio independiente del agente:

```text
Aranwill/malak-vault-sync-agent
rama main
```

Repositorios observados:

```text
D:\Ollama\jarvis
D:\Ollama\malak-project-vault
```

La separación física y lógica preserva:

- independencia respecto del Kernel;
- independencia respecto del runtime;
- permisos mínimos;
- reversibilidad;
- aislamiento de fallos;
- ausencia de autoridad sobre los repositorios observados.

## 4. Baseline vigente del agente

Baseline operacional vigente:

```text
Repositorio: Aranwill/malak-vault-sync-agent
Rama: main
HEAD: 0feed6eae3d3919ea4867891c12eda5eea81c511
PR integradas relevantes: #1, #3, #4, #5 y #6
Working tree: limpio
main local: alineada con origin/main
Suite completa: 230 passed
Configuración privada: válida y excluida de Git
Ejecución manual: pass
Scheduler final: eliminado
Modo operativo: manual-on-demand
Modos autorizados: dry-run y controlled-proposal
Estado persistente: esquema v3 reconciliado
Incremento 4: cerrado
last_applied_commit: null
```

El baseline formal e histórico del cierre técnico de la Fase 1 permanece registrado en:

```text
HEAD de cierre: 954659b
Suite de cierre: 148 passed
Documento: docs/PHASE_1_FINAL_BASELINE.md
```

Ese baseline conserva la evidencia del cierre formal de los Gates 0 a 9.
Los commits posteriores incorporaron la operacionalización read-only, la
propuesta controlada y la reconciliación gobernada del estado v3 sin
modificar la autoridad operativa `none`.

Validaciones del cierre técnico:

```text
Suite completa: 148 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
Malāk intacto: sí
Vault intacto: sí
last_applied_commit: null
Hashes SHA-256 verificados: sí
```

## 5. Arquitectura implementada y operacionalizada

La arquitectura efectiva de la Fase 1 está compuesta por:

- configuración externa privada;
- validación formal de configuración;
- inspección Git de solo lectura;
- controlador de ejecución manual;
- comando `run-once`;
- runner determinista;
- lock de ejecución;
- polling externo;
- estado persistente local;
- recolector de evidencia;
- manifiesto de evidencia;
- comparador determinista;
- clasificador de cambios;
- resolvedor determinista de documentos candidatos;
- allowlist y denylist;
- validadores de rutas;
- validadores Markdown;
- validadores YAML;
- validadores de enlaces;
- validadores de hashes;
- validadores de metadatos;
- controles TOCTOU;
- sanitización de evidencia;
- límites de tamaño y alcance;
- generador de informes de auditoría;
- validación end-to-end;
- verificación de invariantes de no modificación.

La extensión `controlled-proposal` incorpora:

- cursores separados de observación y reconciliación;
- escritor determinista sobre documentos allowlisted;
- worktree temporal desde `origin/main` del Vault;
- rama de propuesta con prefijo fijo;
- commit documental;
- informe auditable y commit de auditoría;
- push sin reescritura de historia;
- apertura de PR draft mediante GitHub CLI;
- persistencia v3 de la identidad exacta de la propuesta;
- aceptación y rechazo locales sujetos a decisión humana y verificación
  del estado remoto.

La operacionalización posterior incorporó:

- repositorio remoto independiente para respaldar el código del agente;
- observación controlada de `origin/main`;
- soporte para ejecución local en Windows;
- persistencia y respaldo del estado operativo;
- configuración privada excluida de Git;
- validación temporal mediante el Programador de tareas de Windows;
- adopción final del modo manual bajo demanda;
- eliminación de la tarea programada después de su validación.

## 6. Flujos implementados

### 6.1 Fase 1 `dry-run`

```text
ejecutar run-once
→ realizar fetch controlado
→ detectar
→ comparar
→ clasificar
→ resolver documentos candidatos
→ aplicar allowlist y denylist
→ validar
→ generar evidencia
→ generar informe de auditoría
→ verificar hashes
→ comprobar invariantes
→ finalizar sin aplicar cambios
```

El flujo termina sin escritura sobre Malāk ni sobre el Vault.

La Fase 1 no prepara cambios, no crea ramas, no crea commits y no abre pull requests.

### 6.2 Extensión `controlled-proposal`

```text
ejecución manual
→ verificar Malāk y Vault
→ resolver y validar candidatos allowlisted
→ crear worktree y rama aislada del Vault
→ escribir y validar la proyección final
→ crear commit documental
→ generar y validar informe auditable
→ crear commit de auditoría
→ push de la rama
→ abrir PR draft
→ persistir propuesta pendiente
→ esperar decisión humana
```

Este flujo nunca escribe en Malāk, nunca escribe directamente en `main`
del Vault y nunca aprueba o mergea una PR.

Flujo operativo vigente:

```text
Avance aprobado de Malāk
→ merge o push a Aranwill/jarvis/main
→ ejecución manual de run-once
→ revisión humana de evidencia e informe
→ rama y PR draft de actualización del Vault
→ revisión y decisión humanas
→ merge exclusivamente humano o cierre sin merge
→ reconciliación local explícita
```

El agente observa el estado publicado de `origin/main`. Los cambios exclusivamente locales y todavía no publicados no constituyen el estado remoto que debe procesar.

Comando operativo:

```powershell
cd D:\Ollama\malak-vault-sync-agent

.\.venv\Scripts\malak-vault-sync.exe run-once `
  --config .\config\vault-sync.yaml
```

## 7. Modelo de autoridad

```text
Agente:
observa, compara, clasifica, valida, genera evidencia y prepara
propuestas documentales aisladas

LLM:
no utilizado en la Fase 1

Humano:
revisa, decide, aprueba y autoriza cualquier ampliación
```

La arquitectura preserva:

- Human in Control;
- denegación por defecto;
- mínimo privilegio;
- separación entre observación y decisión;
- trazabilidad;
- reversibilidad;
- ausencia de autoridad autónoma.

La existencia de un repositorio remoto propio para el agente no modifica este modelo de autoridad.

## 8. Límites obligatorios verificados

Durante la Fase 1:

- `Aranwill/jarvis/main` permaneció en modo de solo lectura;
- no se modificaron archivos de Malāk;
- no se ejecutó configuración de Malāk;
- no se crearon ramas en Malāk;
- no se crearon commits en Malāk;
- no se ejecutó push sobre Malāk;
- no se modificaron archivos del Vault;
- no se crearon ramas en el Vault;
- no se crearon commits en el Vault;
- no se abrieron pull requests;
- no se aprobaron ni mergearon pull requests;
- no se cerraron decisiones automáticamente;
- no se modificaron snapshots históricos;
- no se utilizó LLM;
- no se implementó servidor HTTP;
- no se implementaron webhooks;
- no se implementó daemon permanente;
- no se adquirió autoridad documental;
- no se adquirió autoridad operativa.

En la extensión `controlled-proposal`:

- Malāk conserva acceso estrictamente read-only;
- el `main` remoto del Vault permanece sin escritura directa;
- solo se modifican documentos allowlisted en una rama aislada;
- no se modifican snapshots históricos;
- no se realiza force-push;
- toda PR se abre como draft;
- una propuesta pendiente bloquea nuevas propuestas;
- la aceptación o el rechazo requieren una decisión humana explícita;
- el agente no aprueba, habilita auto-merge ni mergea.

Todos los comandos Git operativos auditados durante el cierre histórico
de la Fase 1 fueron clasificados como read-only.

Durante la operacionalización:

- el agente realizó únicamente `fetch` controlado sobre los repositorios observados;
- la configuración privada permaneció excluida de Git;
- el estado, la evidencia y los informes operativos permanecieron locales;
- `last_applied_commit` permaneció en `null`;
- la ejecución manual finalizó con resultado `pass`;
- la ejecución programada de validación finalizó con código `0`;
- la tarea programada fue eliminada después de la prueba;
- no quedó servicio, daemon ni proceso permanente en segundo plano.

## 9. Clasificación implementada

```text
CURRENT_STATE
HISTORICAL_IMMUTABLE
APPROVED_DECISION
OPEN_PROPOSAL
ROADMAP_ITEM
CLOSURE_EVIDENCE
INDEX_REFERENCE
ARCHITECTURAL_CONTRADICTION
SECURITY_CONTRADICTION
UNKNOWN
```

`UNKNOWN` implica denegación por defecto.

Las contradicciones críticas se reportan y bloquean la operación afectada.

El agente no resuelve contradicciones de autoridad, gobernanza, arquitectura o seguridad.

## 10. Política aplicable

La arquitectura debe cumplir obligatoriamente:

- [[00-governance/VAULT_SYNC_AGENT_POLICY|Política obligatoria del Vault Synchronization Agent]].

La política continúa preservando:

- solo lectura sobre Malāk;
- autoridad operativa `none`;
- snapshots inmutables;
- revisión humana;
- ausencia de auto-merge;
- ausencia de cierre automático de decisiones;
- prohibición de ampliar alcance sin aprobación explícita.

## 11. Relación con Session Context Generator

Vault Synchronization Agent Foundation:

- obtiene evidencia;
- valida evidencia;
- detecta drift;
- clasifica cambios;
- identifica documentos candidatos;
- genera informes.

Session Context Generator, si se aprueba en el futuro:

- solo podrá producir una propuesta de contexto;
- deberá consumir evidencia ya validada;
- no decidirá el baseline;
- no modificará documentos oficiales;
- no cerrará decisiones;
- no adquirirá autoridad operativa.

Esta relación permanece futura y no aprobada para implementación.

## 12. Estado de gates

```text
Gate 0 — relevamiento de solo lectura: cerrado
Gate 1 — workspace y configuración: cerrado
Gate 2 — inspección Git de solo lectura: cerrado
Gate 3 — estado persistente local: cerrado
Gate 4 — paquete de evidencia: cerrado
Gate 5 — resolución de documentos candidatos: cerrado
Gate 6 — validadores deterministas: cerrado
Gate 7 — informe de auditoría: cerrado
Gate 8 — runner, lock y polling externo: cerrado
Gate 9 — validación final: cerrado
```

Fase 1:

```text
cerrada formalmente
```

El cierre de Gate 9 no autoriza una fase posterior.

## 13. Componentes no implementados

Los siguientes componentes permanecen fuera del alcance aprobado:

- escritura directa en `main` del Vault;
- escritura fuera del allowlist documental;
- generación autónoma de propuestas sin invocación manual;
- aprobación o merge automático;
- reescritura de historia;
- scheduler permanente o activo;
- servicio permanente;
- daemon;
- webhooks;
- event-driven detection;
- LLM-assisted Documentation;
- modificación automática del baseline;
- cierre automático de decisiones;
- escritura sobre documentos normativos.

Estos elementos no deben presentarse como arquitectura implementada.

## 14. Fases futuras

Secuencia conceptual:

1. Fase 1 — Read-only Drift Detector: completada.
2. Extensión gobernada `controlled-proposal`: aprobada y cerrada en su
   alcance actual.
3. Fase 2 y ampliaciones funcionales posteriores: no aprobadas.
4. Event-driven Detection: no aprobada.
5. LLM-assisted Documentation: no aprobada.

La numeración es conceptual y no autoriza implementación automática.

Cualquier fase posterior requerirá:

1. necesidad concreta;
2. decisión independiente;
3. alcance explícito;
4. fuera de alcance;
5. evaluación de riesgos;
6. permisos mínimos;
7. rollback;
8. criterios de aceptación;
9. validación arquitectónica;
10. aprobación humana explícita.

## 15. Estado remoto del agente

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

El remoto respalda el código del agente, pero no le concede autoridad sobre Malāk ni sobre el Vault.

Estado operativo:

```text
Operacionalización read-only: completed
Modo de ejecución: manual-on-demand
Modos autorizados: dry-run y controlled-proposal
Scheduler activo: no
Tarea programada activa: no
Servicio permanente: no
Daemon: no
Proceso en segundo plano: no
```

La ejecución programada fue utilizada únicamente para validar la operacionalización en Windows. La tarea `Malak Vault Sync - Read Only` fue eliminada posteriormente por decisión humana.

## 16. Evidencia de cierre

El cierre técnico de Fase 1 está documentado en:

- [[07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE|Informe de cierre de la Fase 1 del Vault Synchronization Agent]].

El informe registra:

- baseline final;
- gates cerrados;
- validaciones;
- invariantes;
- hashes SHA-256;
- estado remoto;
- riesgos residuales;
- fuera de alcance;
- autoridad operativa `none`.

El cierre de la operacionalización read-only está documentado en:

- [[07-audits/vault-synchronization/2026-07-24_VAULT_SYNC_OPERATIONALIZATION_CLOSURE|Informe de cierre de la operacionalización read-only del Vault Synchronization Agent]].

El informe registra:

- repositorio remoto independiente;
- PR #1 integrada;
- baseline operacional `ade622b`;
- suite completa de `165 passed`;
- configuración privada validada;
- ejecución manual y ejecución programada de validación;
- eliminación posterior del scheduler;
- adopción del modo `manual-on-demand`;
- preservación de `last_applied_commit: null`;
- Fase 2 no aprobada.

El cierre del Incremento 4 está documentado en el repositorio del agente:

```text
docs/INCREMENT_4_CLOSURE.md
PR #6
merge commit: 0feed6eae3d3919ea4867891c12eda5eea81c511
suite completa: 230 passed
```

## 17. Criterios de aceptación cumplidos

- arquitectura externa al runtime;
- Malāk en modo de solo lectura;
- Vault sin autoridad operativa;
- políticas deterministas;
- denegación por defecto;
- snapshots inmutables;
- evidencia reproducible;
- informe obligatorio;
- LLM no utilizado;
- cero modificaciones en `Aranwill/jarvis`;
- cero escrituras directas en `main` del Vault;
- propuestas limitadas a ramas aisladas allowlisted;
- Gates 0 a 9 cerrados;
- suite completa en verde;
- `compileall` correcto;
- `git diff --check` correcto;
- validación end-to-end `pass`;
- `last_applied_commit: null`;
- repositorio remoto independiente configurado;
- operacionalización read-only completada;
- ejecución manual validada;
- ejecución mediante Programador de tareas validada;
- scheduler eliminado después de la validación;
- modo operativo `manual-on-demand` aprobado;
- suite operacional de `230 passed`;
- estado v3 reconciliado;
- Incremento 4 cerrado;
- Fase 2 preservada como no aprobada.

## 18. Riesgos residuales

Continúan vigentes:

- confundir observación con autoridad;
- interpretar evidencia como aprobación;
- iniciar una fase posterior por continuidad;
- conceder permisos de escritura prematuramente;
- confundir propuesta técnica con aplicación documental;
- dejar una rama o PR huérfana ante un fallo remoto;
- publicar evidencia sensible;
- olvidar ejecutar manualmente el agente después de una sesión aprobada;
- ejecutar el agente antes de publicar los cambios en `origin/main`;
- interpretar documentos candidatos como cambios obligatorios;
- reactivar un scheduler sin una nueva aprobación explícita;
- presentar componentes futuros como implementados;
- incorporar el agente al baseline operativo de Malāk;
- interpretar `pass` como autorización autónoma.

## 19. Regla de cierre

```text
Fase 1: completada
Operacionalización read-only: completada
Modo operativo: manual-on-demand
Controlled-proposal: aprobado y cerrado en su alcance vigente
Scheduler activo: no
Autoridad operativa: none
Fases posteriores: no aprobadas
```

La arquitectura aprobada de Fase 1 y su operacionalización read-only quedan cerradas.

Cualquier cambio futuro deberá registrarse mediante una nueva decisión, un nuevo alcance y una nueva aprobación humana.
