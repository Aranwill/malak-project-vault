---
document_id: VAULT-SYNC-AGENT-POLICY-001
title: Política obligatoria del Vault Synchronization Agent
document_type: governance-policy
status: accepted
authority: approved_policy
operational_authority: none
version: 1.0
created: 2026-07-21
last_reviewed: 2026-07-22
source_repository: Aranwill/jarvis
source_branch: main
source_commit: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
vault_repository: Aranwill/malak-project-vault
vault_branch: main
vault_base_commit: 52976e771ad8307badbc0ac37a78a771e6df51fc
implementation_approved: true
phase_1_status: completed
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
> Esta política fue aprobada y aplicada exclusivamente al alcance de la Fase 1.
>
> La Fase 1 fue implementada, validada y cerrada.
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
Rama: main
HEAD: 954659b
Gate 0 a Gate 9: cerrados
Suite completa: 148 passed
compileall: correcto
git diff --check: correcto
Resultado end-to-end: pass
Malāk intacto: sí
Vault intacto: sí
last_applied_commit: null
Hashes SHA-256 verificados: sí
Autoridad operativa: none
```

Todos los comandos Git operativos auditados fueron clasificados como read-only.

## 17. Estado remoto del agente

```text
Remoto configurado: no
URL remota: ninguna
Upstream de main: no
Working tree: limpio
HEAD: 954659b
Respaldo remoto: pendiente de decisión humana
Push ejecutado: no
```

La creación de un remoto y cualquier push futuro constituyen una tarea administrativa separada.

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

El baseline final del agente se encuentra en:

```text
docs/PHASE_1_FINAL_BASELINE.md
```

## 21. Estado final

```text
Política: accepted
Fase 1: completed
Agente operativo: herramienta local de solo lectura
Autoridad operativa: none
Escritura sobre Malāk: no
Escritura sobre el Vault: no
Fase 2 y posteriores: no aprobadas
Próximo sprint de Malāk: no definido
```

La aprobación de esta política no concede autorización para ninguna capacidad fuera del alcance cerrado de la Fase 1.

