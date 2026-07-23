---
document_id: VAULT-SYNC-THREAT-MODEL-001
title: Modelo de amenazas del Vault Synchronization Agent
document_type: threat-model
status: accepted
authority: approved_security_documentation
operational_authority: none
version: 1.0
created: 2026-07-21
last_reviewed: 2026-07-22
implementation_approved: true
phase_1_status: completed
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

Documentar las amenazas, controles, validaciones y riesgos residuales del Vault Synchronization Agent en su Fase 1.

Este documento no convierte al agente en un componente de seguridad de Malāk.

El agente permanece:

- fuera del Kernel;
- fuera del runtime;
- fuera del Security Control Plane;
- sin autoridad operativa;
- sin autoridad documental;
- limitado a observación, validación y generación de evidencia.

## 2. Estado

```text
Estado del documento: accepted
Fase 1: completed
Autoridad operativa: none
Kernel afectado: no
Runtime afectado: no
Security Control Plane afectado: no
```

La aceptación de este modelo se limita a los controles implementados y verificados durante la Fase 1.

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

## 4. Superficie de ataque de la Fase 1

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

No forman parte de la superficie aprobada:

- escritura en Malāk;
- escritura en el Vault;
- ramas automáticas;
- commits automáticos;
- PR automáticas;
- merge;
- webhooks;
- servidor HTTP;
- daemon;
- LLM;
- integración con Kernel;
- integración con runtime.

## 5. Amenazas y controles verificados

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

### 5.6 Escritura accidental en el Vault

**Riesgo:** modificación automática del Vault durante la Fase 1.

**Controles verificados:**

- permisos de solo lectura;
- ausencia de writer;
- ausencia de creación de ramas;
- ausencia de commits;
- ausencia de push;
- ausencia de PR;
- `last_applied_commit: null`;
- Vault intacto.

**Estado:**

```text
mitigado
```

### 5.7 Destrucción de historia

**Riesgo:** modificación o reemplazo de snapshots históricos.

**Controles verificados:**

- snapshots en denylist;
- inmutabilidad explícita;
- validación de rutas;
- bloqueo de actualización de snapshots existentes;
- ningún snapshot modificado.

**Estado:**

```text
mitigado
```

### 5.8 Escalada mediante credenciales

**Riesgo:** uso de tokens o credenciales con permisos de escritura.

**Controles verificados:**

- Fase 1 sin credenciales de escritura;
- agente sin remoto configurado;
- sin upstream;
- sin push;
- sin integración de escritura con GitHub;
- permisos mínimos.

**Estado:**

```text
mitigado para el entorno verificado
```

### 5.9 Falsa evidencia de pruebas

**Riesgo:** confundir pruebas del agente con pruebas oficiales de Malāk.

**Controles verificados:**

- separación entre suite del agente y suite oficial;
- suite del agente registrada como `148 passed`;
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

**Estado:**

```text
mitigado en Fase 1
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

## 6. Reglas de bloqueo verificadas

La ejecución deberá bloquearse ante:

- intento de escritura en `Aranwill/jarvis`;
- intento de escritura en el Vault;
- intento de crear ramas;
- intento de crear commits;
- intento de ejecutar push;
- intento de abrir PR;
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

## 7. Controles verificados al cierre de Fase 1

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
Comandos Git auditados como read-only: sí
Autoridad operativa: none
```

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
- incorporación de escritura sin un modelo de amenazas nuevo;
- dependencia excesiva de validadores incompletos;
- falsos positivos;
- falsos negativos;
- cambios del entorno local;
- cambios de versiones de Git o Python;
- configuración futura no auditada;
- fuga de información mediante logs o artefactos;
- TOCTOU en una futura fase con escritura;
- compromiso de credenciales en una fase posterior.

## 9. Controles no implementados

No están implementados ni aprobados:

- writer sobre el Vault;
- branch writer;
- commit generator;
- PR draft preparer;
- integración GitHub con permisos de escritura;
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

## 10. Condiciones para una fase futura

Antes de cualquier fase con escritura deberá existir un nuevo análisis que incluya:

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

## 12. Estado remoto del agente

```text
Remoto configurado: no
URL remota: ninguna
Upstream de main: no
Working tree: limpio
HEAD: 954659b
Respaldo remoto: pendiente de decisión humana
Push ejecutado: no
```

La creación de un remoto y cualquier push futuro requieren una tarea administrativa separada.

## 13. Resultado final

```text
Modelo de amenazas: accepted
Fase 1: completed
Controles verificados: sí
Riesgos residuales: documentados
Autoridad operativa: none
Malāk modificado: no
Vault modificado automáticamente: no
Snapshots modificados: no
Fase 2 y posteriores: no aprobadas
```

La aceptación de este documento no concede autoridad adicional ni autoriza capacidades fuera del alcance cerrado de la Fase 1.
