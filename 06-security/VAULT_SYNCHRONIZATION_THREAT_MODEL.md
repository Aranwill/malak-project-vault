---
document_id: VAULT-SYNC-THREAT-MODEL-001
title: Modelo de amenazas del Vault Synchronization Agent
document_type: threat-model
status: under_review
authority: proposal
operational_authority: none
version: 0.1
created: 2026-07-21
last_reviewed: 2026-07-21
implementation_approved: false
tags:
  - malak
  - vault
  - synchronization
  - security
  - threats
---

# Modelo de amenazas del Vault Synchronization Agent

## Activos protegidos

- autoridad documental;
- integridad del Vault;
- snapshots historicos;
- exactitud del baseline;
- credenciales GitHub;
- historial Git;
- separacion entre propuesta y decision;
- separacion entre Vault y runtime;
- contenido publico sin secretos.

## Amenazas y controles

### Confused deputy

Riesgo: interpretar permiso tecnico como autoridad decisoria.

Control: politicas deterministas, PR draft, merge humano y prohibicion de cambiar estados de decision.

### Prompt injection documental

Riesgo: instrucciones hostiles dentro de documentos, issues o PR.

Control: tratar contenido como datos, no instrucciones; separar LLM de autorizacion; allowlist de operaciones.

### Repositorio o rama incorrectos

Control: validar repositorio, rama y `HEAD` esperado antes de leer, escribir y abrir PR.

### TOCTOU

Riesgo: cambio de `HEAD` entre comparacion y escritura.

Control: registrar SHAs y abortar si cambian.

### Destruccion de historia

Control: snapshots existentes en denylist absoluta de actualizacion.

### Escalada mediante token

Control: solo lectura en Malak; permisos minimos en Vault; sin auto-merge ni administracion.

### Falsa evidencia de pruebas

Control: distinguir pruebas ejecutadas por el agente de pruebas documentadas por fuentes oficiales.

### Reescritura masiva

Control: presupuesto maximo de archivos y lineas; bloqueo de normalizaciones masivas no aprobadas.

### Exposicion de secretos

Control: escaneo de secretos y bloqueo de tokens, credenciales, claves y datos sensibles.

### Deriva de politicas

Control: versionar politicas, registrar su version en cada informe y denegar tipos desconocidos.

## Reglas de bloqueo

La ejecucion debera bloquearse ante:

- intento de escritura en `Aranwill/jarvis`;
- intento de escritura directa en `main`;
- intento de modificar un snapshot existente;
- contradiccion critica sin resolver;
- tipo documental desconocido;
- fallo de validacion de secretos;
- cambio de `HEAD` durante la ejecucion;
- imposibilidad de generar el informe de auditoria.
