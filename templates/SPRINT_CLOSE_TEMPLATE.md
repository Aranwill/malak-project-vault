---

id: TEMPLATE-SESSION-CLOSE
title: Malāk Session Close Template
type: template
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-20
derived: false
operational_context: false
retrieval_enabled: true
retrieval_scope: active
-----------------------

# Malāk — Cierre de sesión

## 1. Identificación

**Fecha:**

```text
AAAA-MM-DD
```

**Hora de inicio:**

```text
HH:MM
```

**Hora de cierre:**

```text
HH:MM
```

**Responsable:**

```text
Héctor Rodríguez
```

**Tipo de sesión:**

```text
documentación | arquitectura | implementación | pruebas | auditoría | investigación | mantenimiento
```

---

## 2. Objetivo de la sesión

Describir de forma breve y concreta el objetivo aprobado al iniciar la sesión.

```text
Ejemplo:
Completar la gobernanza documental inicial del Malāk Project Vault.
```

---

## 3. Alcance autorizado

Registrar qué estaba permitido realizar.

```text
- actividad autorizada;
- documento autorizado;
- módulo autorizado;
- validación autorizada.
```

---

## 4. Fuera de alcance

Registrar explícitamente qué no debía modificarse.

```text
- Kernel;
- contratos centrales;
- repositorio oficial;
- dependencias;
- roadmap;
- seguridad;
- otro elemento protegido.
```

---

## 5. Estado inicial del repositorio oficial

**Repositorio:**

```text
Aranwill/jarvis
```

**Rama esperada:**

```text
main
```

**Rama verificada:**

```text
pendiente
```

**Commit inicial:**

```text
pendiente
```

**Working tree inicial:**

```text
limpio | con cambios | no verificado
```

**Sincronización con remoto:**

```text
sincronizado | desactualizado | no verificado
```

---

## 6. Validaciones iniciales

| Validación                       | Resultado |
| -------------------------------- | --------- |
| `git branch --show-current`      | Pendiente |
| `git status`                     | Pendiente |
| `git log -1 --oneline`           | Pendiente |
| `python -m pytest -q`            | Pendiente |
| `python -m compileall src tests` | Pendiente |
| `git diff --check`               | Pendiente |

Cuando la sesión no involucre el repositorio oficial, indicar:

```text
No aplicable: sesión exclusiva del Project Vault.
```

---

## 7. Trabajo realizado

Registrar únicamente acciones efectivamente realizadas.

```text
1. Acción realizada.
2. Archivo creado o modificado.
3. Validación ejecutada.
4. Resultado obtenido.
```

No registrar como realizado aquello que solo fue discutido o propuesto.

---

## 8. Archivos creados

| Archivo | Ubicación     | Estado |
| ------- | ------------- | ------ |
| Ejemplo | Ruta completa | Creado |

Si no se crearon archivos:

```text
Ninguno.
```

---

## 9. Archivos modificados

| Archivo | Ubicación     | Motivo      |
| ------- | ------------- | ----------- |
| Ejemplo | Ruta completa | Descripción |

Si no se modificaron archivos:

```text
Ninguno.
```

---

## 10. Archivos eliminados

| Archivo | Ubicación     | Motivo      |
| ------- | ------------- | ----------- |
| Ejemplo | Ruta completa | Descripción |

Si no se eliminaron archivos:

```text
Ninguno.
```

---

## 11. Decisiones tomadas

Registrar solo decisiones explícitamente aprobadas.

### DEC-SESSION-XXX — Título

**Decisión:**

```text
Descripción exacta de la decisión aprobada.
```

**Aprobada por:**

```text
Propietario
```

**Impacto:**

```text
baseline | roadmap | Vault | arquitectura | documentación | ninguno
```

**Documento que debe actualizarse:**

```text
Ruta o identificador
```

Si no se aprobaron decisiones:

```text
Ninguna.
```

---

## 12. Propuestas discutidas

Registrar ideas que no fueron aprobadas.

| Propuesta | Estado    | Próxima acción |
| --------- | --------- | -------------- |
| Ejemplo   | Pendiente | Revisar        |

Una propuesta discutida no debe registrarse como decisión.

---

## 13. Decisiones pendientes

| ID           | Decisión    | Estado | Prioridad |
| ------------ | ----------- | ------ | --------- |
| DEC-PEND-XXX | Descripción | open   | alta      |

Verificar si corresponde actualizar:

```text
05-decisions\PENDING_DECISIONS.md
```

---

## 14. Contradicciones detectadas

Registrar cualquier discrepancia entre:

* memoria y repositorio;
* README y roadmap;
* código y arquitectura;
* sprint y baseline;
* documentación vigente y legacy;
* Vault y fuente oficial.

### Contradicción

**Fuente A:**

```text
Documento o evidencia
```

**Fuente B:**

```text
Documento o evidencia
```

**Estado:**

```text
resuelta | pendiente | bloqueante
```

**Resolución o próxima acción:**

```text
Descripción
```

Si no se detectaron contradicciones:

```text
Ninguna.
```

---

## 15. Riesgos detectados

| Riesgo  | Severidad | Estado  | Mitigación |
| ------- | --------- | ------- | ---------- |
| Ejemplo | baja      | abierto | Revisar    |

Si no se detectaron riesgos:

```text
Ninguno.
```

---

## 16. Validaciones finales

| Validación              | Resultado                 |
| ----------------------- | ------------------------- |
| Tests                   | No ejecutados / Resultado |
| `compileall`            | No ejecutado / Resultado  |
| `git diff --check`      | No ejecutado / Resultado  |
| Revisión documental     | Completa / Incompleta     |
| Revisión arquitectónica | Completa / Incompleta     |
| Working tree            | Limpio / Con cambios      |
| Sincronización remota   | Confirmada / Pendiente    |

---

## 17. Estado final del repositorio

**Rama final:**

```text
main | no aplicable
```

**Commit final:**

```text
SHA | sin cambios | no aplicable
```

**Working tree final:**

```text
limpio | con cambios | no verificado
```

**Pull request:**

```text
número | no creado | no aplicable
```

**Merge:**

```text
realizado | pendiente | no aplicable
```

---

## 18. Estado final del Project Vault

Registrar los documentos actualizados durante la sesión.

```text
- documento;
- documento;
- plantilla;
- metadato.
```

**Estado general:**

```text
estable | en construcción | requiere revisión
```

---

## 19. Contexto que debe actualizarse

Marcar los documentos que requieren actualización:

```text
[ ] CURRENT_BASELINE.md
[ ] IMPLEMENTATION_ROADMAP.md
[ ] PENDING_DECISIONS.md
[ ] MALAK_SESSION_CONTEXT.md
[ ] README.md del Vault
[ ] Documento de sprint
[ ] ADR
[ ] Otro
```

---

## 20. Próximo paso recomendado

Registrar una única acción siguiente, concreta y no autorizante.

```text
Ejemplo:
Completar la plantilla de cierre de sprint.
```

Este campo no aprueba el próximo sprint ni autoriza modificaciones.

---

## 21. Acción bloqueada hasta aprobación

Registrar cualquier acción que no deba iniciarse automáticamente.

```text
Ejemplo:
No iniciar un nuevo sprint de Malāk hasta completar el relevamiento y obtener aprobación explícita.
```

---

## 22. Resumen compacto para próxima sesión

```text
Fecha:
Objetivo completado:
Último sprint cerrado:
Rama oficial:
Tests documentados:
Archivos principales modificados:
Decisiones aprobadas:
Decisiones pendientes:
Próximo paso recomendado:
Acciones no autorizadas:
```

Este bloque podrá copiarse temporalmente al inicio de una nueva sesión, junto con:

```text
08-session-context\MALAK_SESSION_CONTEXT.md
```

---

## 23. Declaración de cierre

```text
La sesión se cierra con el alcance documentado.
No se consideran aprobadas acciones, sprints o modificaciones que no hayan sido registradas explícitamente.
```

---

## 24. Principios rectores

> Registrar lo realizado evita reconstruirlo de memoria.

> Lo discutido no equivale a lo aprobado.

> El cierre de una sesión no autoriza el siguiente cambio.

> Toda continuidad debe comenzar desde evidencia verificable.
