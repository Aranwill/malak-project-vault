---
document_id: VAULT-SYNC-THREAT-MODEL-001
title: Modelo de amenazas del Vault Synchronization Agent
document_type: threat-model
status: accepted
authority: approved_security_documentation
operational_authority: none
version: 1.1
created: 2026-07-21
last_reviewed: 2026-08-16
implementation_approved: true
phase_1_status: completed
controlled_proposal_status: approved
runtime_component: false
kernel_component: false
tags:
  - malak
  - vault
  - synchronization
  - security
  - threats
---

# Modelo de amenazas del Vault Synchronization Agent

## 1. Propósito

Documentar las amenazas, controles, validaciones y riesgos residuales del
Vault Synchronization Agent en la Fase 1 read-only y en la extensión
gobernada `controlled-proposal`.

Este documento no convierte al agente en un componente de seguridad de Malāk.

El agente permanece:

- fuera del Kernel;
- fuera del runtime;
- fuera del Security Control Plane;
- sin autoridad operativa;
- sin autoridad documental;
- limitado a observación, validación, generación de evidencia y
  preparación de propuestas documentales aisladas.

## 2. Estado

```text
Estado del documento: accepted
Fase 1: completed
Controlled-proposal: approved
Autoridad operativa: none
Kernel afectado: no
Runtime afectado: no
Security Control Plane afectado: no
```

La aceptación de este modelo cubre la Fase 1 cerrada y el alcance aprobado
de `controlled-proposal`, incluidas sus brechas técnicas conocidas.

Fase 2 y posteriores permanecen no aprobadas.

## 3. Activos protegidos

- autoridad documental;
- integridad de `Aranwill/jarvis`;
- integridad del Malāk Project Vault;
- snapshots históricos;
- exactitud del baseline;
- historial Git;
- separación entre propuesta y decisión;
- separación entre Vault y runtime;
- separación entre observación y autoridad;
- evidencia reproducible;
- hashes y manifiestos;
- estado persistente local;
- credenciales GitHub;
- secretos, tokens y claves;
- contenido público sin información sensible;
- trazabilidad de ejecuciones;
- revisión humana.

## 4. Superficie de ataque modelada

La superficie de ataque considerada incluye:

- repositorio oficial `Aranwill/jarvis`;
- repositorio documental `Aranwill/malak-project-vault`;
- workspace externo del agente;
- comandos Git;
- archivos Markdown;
- archivos YAML;
- enlaces internos;
- metadatos;
- manifiestos;
- hashes SHA-256;
- estado persistente;
- informes de auditoría;
- configuración externa;
- lock de ejecución;
- polling externo;
- contenido documental potencialmente hostil.
- worktrees temporales;
- ramas y commits de propuesta del Vault;
- GitHub CLI autenticado;
- push de ramas;
- PR draft;
- estado local v3 y reconciliación humana.

No forman parte de la superficie aprobada:

- escritura en Malāk;
- escritura directa en `main` del Vault;
- escritura fuera del allowlist;
- force-push o reescritura de historia;
- aprobación o auto-merge;
- merge;
- webhooks;
- servidor HTTP;
- daemon;
- LLM;
- integración con Kernel;
- integración con runtime.

## 5. Amenazas, controles y riesgos residuales

### 5.1 Confused deputy

**Riesgo:** interpretar permiso técnico o evidencia como autoridad decisoria.

**Controles verificados:**

- `operational_authority: none`;
- separación explícita entre agente y humano;
- el agente no cierra decisiones;
- el agente no aprueba cambios;
- el agente no inicia fases;
- la evidencia no constituye autorización;
- Human in Control.

**Estado:**

```text
mitigado para el alcance de Fase 1
```

### 5.2 Prompt injection documental

**Riesgo:** instrucciones hostiles dentro de documentos, issues, PR o contenido externo.

**Controles verificados:**

- contenido tratado como datos;
- reglas deterministas;
- LLM no utilizado;
- allowlist y denylist;
- tipos desconocidos bloqueados;
- contradicciones críticas reportadas;
- ausencia de ejecución de instrucciones embebidas.

**Estado:**

```text
mitigado para el alcance de Fase 1
```

### 5.3 Repositorio o rama incorrectos

**Riesgo:** observar un repositorio, una rama o un `HEAD` no autorizados.

**Controles verificados:**

- validación de repositorio;
- validación de rama;
- validación de `HEAD`;
- comparación con valores esperados;
- bloqueo ante divergencias.

**Estado:**

```text
mitigado
```

### 5.4 TOCTOU

**Riesgo:** cambio de `HEAD` entre observación, validación y cierre.

**Controles verificados:**

- registro de SHAs;
- validación previa;
- revalidación final;
- controles TOCTOU;
- aborto ante cambio inesperado;
- evidencia asociada al commit observado.

**Estado:**

```text
mitigado para ejecución de solo lectura
```

### 5.5 Escritura accidental en Malāk

**Riesgo:** modificación de archivos, configuración, ramas, commits o referencias en `Aranwill/jarvis`.

**Controles verificados:**

- comandos Git auditados;
- allowlist de comandos read-only;
- denylist de comandos de escritura;
- invariantes de no modificación;
- comparación de estado antes y después;
- validación end-to-end;
- Malāk intacto.

**Estado:**

```text
mitigado
```

### 5.6 Escritura fuera de la rama controlada del Vault

**Riesgo:** escribir en `main`, en otra rama, fuera del allowlist o sobre
un snapshot histórico.

**Controles verificados:**

- `main` remoto tratado como base inmutable de la propuesta;
- worktree temporal desde el `origin/main` verificado;
- prefijo fijo de rama;
- allowlist de rutas y denylist parcial;
- snapshots fuera del allowlist;
- PR obligatoriamente draft;
- ausencia de force-push, aprobación y merge;
- `last_applied_commit: null`;
- verificación de identidad y limpieza antes de escribir.

**Estado:**

```text
mitigado y verificado dentro del alcance certificado; la denylist
explícita protege `09-repository-snapshots/**` y esa ruta permanece
fuera del alcance de escritura.
```

### 5.7 Destrucción de historia

**Riesgo:** modificación o reemplazo de snapshots históricos.

**Controles documentados:**

- snapshots fuera del allowlist;
- inmutabilidad explícita;
- validación de rutas;
- ningún snapshot modificado.

**Estado:**

```text
mitigado y verificado mediante allowlist y denylist explícita para
`09-repository-snapshots/**`
```

### 5.8 Escalada mediante credenciales

**Riesgo:** uso de tokens o credenciales con permisos de escritura.

**Controles verificados:**

- credenciales externas al repositorio;
- GitHub CLI autenticado requerido;
- identidad exacta de ambos repositorios;
- permisos limitados al Vault;
- Malāk conserva acceso read-only;
- sanitización de credenciales en evidencia e informes;
- rama y PR draft como frontera de revisión humana.

**Estado:**

```text
mitigado parcialmente; el compromiso de credenciales permanece como
riesgo residual
```

### 5.9 Falsa evidencia de pruebas

**Riesgo:** confundir pruebas del agente con pruebas oficiales de Malāk.

**Controles verificados:**

- separación entre suite del agente y suite oficial;
- suite histórica de Fase 1 registrada como `148 passed`;
- certificación histórica del Incremento Correctivo Integral 5 registrada como `260 passed`;
- validación multiplataforma en GitHub Actions Ubuntu y Windows;
- validación nativa Windows y GitHub CLI real registradas por separado;
- baseline oficial de Malāk preservado;
- evidencia vinculada al repositorio correspondiente;
- informes separados.

**Estado:**

```text
mitigado
```

### 5.10 Reescritura masiva

**Riesgo:** normalización o modificación documental fuera de alcance.

**Controles verificados:**

- límites de tamaño;
- límites de alcance;
- allowlist de rutas;
- denylist;
- ausencia de escritura;
- bloqueo de operaciones no autorizadas.
- presupuesto de archivos y tamaño;
- escritura limitada a candidatos allowlisted;
- revisión humana del diff completo.

**Estado:**

```text
mitigado para `dry-run` y `controlled-proposal`
```

### 5.11 Exposición de secretos

**Riesgo:** inclusión de tokens, credenciales, claves o datos sensibles en evidencia o informes.

**Controles verificados:**

- sanitización de evidencia;
- denylist;
- validación de contenido;
- límites de evidencia;
- exclusión de secretos;
- revisión humana requerida.

Las brechas de validación documental identificadas en una revisión anterior fueron tratadas posteriormente dentro del Incremento Correctivo Integral 5. La evidencia histórica de esa corrección debe consultarse en los artefactos de certificación.

**Estado:**

```text
mitigado, con riesgo residual
```

### 5.12 Deriva de políticas

**Riesgo:** ejecutar con políticas desactualizadas o no autorizadas.

**Controles verificados:**

- versionado de política;
- versión registrada en informes;
- tipos desconocidos bloqueados;
- agente sin capacidad para modificar su propia política;
- cualquier ampliación requiere aprobación humana.

**Estado:**

```text
mitigado
```

### 5.13 Ejecución concurrente

**Riesgo:** múltiples ejecuciones simultáneas que generen evidencia inconsistente.

**Controles verificados:**

- lock de ejecución;
- runner controlado;
- polling externo;
- estado persistente local.

**Estado:**

```text
mitigado
```

### 5.14 Evidencia manipulada o inconsistente

**Riesgo:** manifiestos, informes o artefactos que no correspondan al contenido observado.

**Controles verificados:**

- hashes SHA-256;
- manifiesto de evidencia;
- validación cruzada;
- referencias a SHAs;
- validación end-to-end;
- hashes verificados.

**Estado:**

```text
mitigado
```

### 5.15 Rama o PR huérfana

**Riesgo:** que un fallo después del push deje una rama o PR sin identidad
persistida o bloquee ejecuciones posteriores.

**Controles documentados:**

- persistencia del estado solo después de completar el circuito;
- rollback de la rama cuando falla la creación de la PR;
- propuesta pendiente con URL y commit de cabecera exactos;
- bloqueo ante estado incompleto;
- reconciliación humana antes de una nueva propuesta.

**Estado:**

```text
mitigado dentro del alcance certificado; permanece riesgo residual ante fallos remotos o pérdida de identidad fuera de los supuestos validados
```

### 5.16 TOCTOU con escritura controlada

**Riesgo:** cambio de `origin/main`, de la rama o de la PR entre la
validación, el commit, el push y la reconciliación.

**Controles documentados:**

- SHAs exactos de Malāk y Vault;
- creación desde el `origin/main` verificado;
- cabecera exacta de la PR persistida;
- verificación remota para aceptar o rechazar;
- lock de ejecución;
- aborto ante identidad ambigua.

**Estado:**

```text
mitigado para el alcance documentado, con riesgo residual remoto
```

## 6. Reglas de bloqueo verificadas

La ejecución deberá bloquearse ante:

- intento de escritura en `Aranwill/jarvis`;
- intento de escritura directa en `main` del Vault;
- intento de crear una rama fuera del prefijo autorizado;
- intento de escribir fuera del allowlist;
- intento de force-push o reescritura de historia;
- intento de abrir una PR que no sea draft;
- intento de aprobar, habilitar auto-merge o mergear;
- intento de modificar un snapshot existente;
- contradicción crítica sin resolver;
- tipo documental desconocido;
- fallo de validación de secretos;
- cambio de `HEAD` durante la ejecución;
- fallo de validación de rutas;
- fallo de validación de hashes;
- fallo de validación de metadatos;
- imposibilidad de generar evidencia;
- imposibilidad de generar el informe;
- pérdida del lock;
- ejecución concurrente no controlada;
- ampliación de alcance no aprobada.
- propuesta pendiente no reconciliada;
- identidad incompleta o contradictoria de una PR;

## 7. Registros históricos de controles verificados

### Cierre histórico de Fase 1

```text
HEAD: 954659b
Suite: 148 passed
Gate 0 a Gate 9: cierre preservado
```

### Certificación histórica del Incremento Correctivo Integral 5

```text
HEAD: 5afd03e1697e4820b8b62ff3db23109fdfde8bcb
Versión: 0.3.0
Suite: 260 passed
compileall: PASS
git diff --check: PASS
GitHub Actions Ubuntu: PASS
GitHub Actions Windows: PASS
Validación nativa Windows: PASS
GitHub CLI real: PASS
Recovery negativo real: PASS
Recovery positivo real: PASS
```

Estos bloques son evidencia histórica de controles certificados. El modelo de
amenazas no mantiene manualmente el estado operativo actual del agente; cuando
deba representarse en el Project Vault, pertenece a
`MALAK_OPERATIONAL_STATE`.
## 8. Riesgos residuales

Permanecen los siguientes riesgos:

- error humano durante la revisión;
- publicación accidental de evidencia sensible;
- respaldo remoto del agente sin revisión previa;
- deriva futura de políticas;
- ampliación prematura de permisos;
- interpretación incorrecta de `pass`;
- confusión entre detección y autorización;
- uso futuro de LLM sin controles adicionales;
- ampliación de escritura fuera de controlled-proposal sin un modelo de amenazas nuevo;
- dependencia excesiva de validadores incompletos;
- falsos positivos;
- falsos negativos;
- cambios del entorno local;
- cambios de versiones de Git o Python;
- configuración futura no auditada;
- fuga de información mediante logs o artefactos;
- TOCTOU entre push, PR y persistencia local;
- compromiso de credenciales con permiso sobre el Vault;
- rama o PR huérfana ante fallos posteriores a la creación;
- validadores documentales incompletos frente a lo declarado;
- diferencias de plataforma entre Windows y CI.

## 9. Controles no implementados

No están implementados ni aprobados:

- escritura directa en `main` del Vault;
- writer fuera del allowlist;
- force-push o reescritura de historia;
- aprobación o merge automático;
- scheduler operativo;
- servicio permanente;
- daemon;
- webhooks;
- event-driven detection;
- LLM-assisted documentation;
- modificación automática de baseline;
- cierre automático de decisiones;
- modificación de documentos normativos;
- auto-merge;
- integración con Security Control Plane;
- integración con Kernel;
- integración con runtime.

Los controles correctivos anteriormente pendientes —revalidación final
pos-escritura, frontmatter YAML, wikilinks, protección explícita de snapshots,
recuperación posterior a PR y evidencia del disparador manual— fueron
implementados y certificados en el Incremento Correctivo Integral 5.

Su cierre no autoriza capacidades adicionales fuera del alcance aprobado.

## 10. Condiciones para una ampliación futura

Antes de ampliar la escritura más allá de `controlled-proposal` deberá
existir un nuevo análisis que incluya:

1. modelo de amenazas actualizado;
2. permisos efectivos;
3. estrategia de credenciales;
4. protección de ramas;
5. control de PR;
6. presupuesto de cambios;
7. rollback;
8. controles TOCTOU con escritura;
9. escaneo de secretos;
10. revisión de dependencias;
11. pruebas de abuso;
12. pruebas de rollback;
13. revisión de gobernanza;
14. aprobación humana explícita.

## 11. Evidencia de cierre

El cierre técnico se documenta en:

- [[07-audits/vault-synchronization/2026-07-22_VAULT_SYNC_PHASE_1_CLOSURE|Informe de cierre de la Fase 1 del Vault Synchronization Agent]].

El baseline final del agente se encuentra en:

```text
docs/PHASE_1_FINAL_BASELINE.md
```

## 12. Registro histórico del estado remoto del agente

```text
Remoto configurado: sí
URL remota: Aranwill/malak-vault-sync-agent
Upstream de main: origin/main
Working tree: limpio al cierre operativo
HEAD: 5afd03e1697e4820b8b62ff3db23109fdfde8bcb
Versión: 0.3.0
Respaldo remoto: completado
Suite certificada en ese cierre: 260 passed
PR de cierre operativo: #8 integrada
```

El remoto respalda el código del agente. Los permisos de escritura usados
por `controlled-proposal` se limitan al Vault y no conceden autoridad
sobre Malāk.

## 13. Resultado final

```text
Modelo de amenazas: accepted
Fase 1: completed
Controlled-proposal: approved
Controles verificados: sí
Riesgos residuales: documentados
Autoridad operativa: none
Malāk modificado: no
Vault main modificado directamente: no
Ramas de propuesta permitidas: sí, bajo controles
Snapshots modificados: no
Fase 2 y posteriores: no aprobadas
```

La aceptación de este documento no concede autoridad adicional ni autoriza capacidades fuera de la Fase 1 cerrada y de la extensión `controlled-proposal` aprobada en `DEC-RES-009`. El Incremento Correctivo Integral 5 fue posteriormente implementado y certificado; ese cierre no amplía por sí solo el modelo de autoridad.
