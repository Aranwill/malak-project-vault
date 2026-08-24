# AGENTS.md — Instrucciones del Malāk Project Vault

## Propósito

Este archivo define las reglas operativas que deben seguir asistentes, agentes, scripts y herramientas al trabajar en el repositorio `malak-project-vault`.

Estas instrucciones gobiernan el trabajo dentro del Vault. No reemplazan, modifican ni reinterpretan la Constitución Cognitiva, la Constitución de Gobernanza, el Blueprint, los ADR aceptados ni ninguna otra fuente normativa del repositorio oficial de Malāk.

## Regla persistente de idioma

- Todas las respuestas al propietario del proyecto deben estar en español.
- Toda documentación nueva debe redactarse en español.
- Los análisis, planes, informes, notas y propuestas deben estar en español.
- Los identificadores técnicos, nombres de archivos, rutas, APIs, clases, funciones y comandos existentes pueden mantenerse en inglés.
- No se deben traducir identificadores cuando hacerlo afecte trazabilidad o consistencia.
- Cuando una fuente esté en inglés, su contenido debe explicarse en español.

## Raíz del repositorio

La raíz Git efectiva del Project Vault es:

```text
D:\Ollama\malak-project-vault
```

Ejecuta Git y las validaciones del Vault desde este directorio, salvo que una tarea aprobada requiera explícitamente otra ubicación.

## Identidad y función del Vault

- Repositorio: `Aranwill/malak-project-vault`
- Rama base permanente: `main`
- Repositorio oficial de Malāk: `Aranwill/jarvis`
- Rama oficial de Malāk: `main`
- Naturaleza del Vault: derivada, externa, gobernada y reconstruible
- Autoridad operativa sobre Malāk: ninguna

Principio rector:

> **El Vault organiza y preserva conocimiento sobre Malāk, pero no gobierna a Malāk por encima de sus documentos oficiales.**

El Vault puede conservar contexto, organizar conocimiento, resumir evidencia, mantener índices, preservar snapshots, registrar relaciones, facilitar auditoría, detectar drift y formular findings o propuestas.

El Vault no puede redefinir arquitectura, modificar gobernanza, alterar el baseline de Malāk, convertir una propuesta en decisión, convertir una referencia conceptual en autoridad normativa, asumir que un resumen derivado prevalece sobre su fuente, otorgar permisos o autoridad operacional ni corregir silenciosamente la fuente oficial.

## Fuente de verdad y precedencia

`Aranwill/jarvis/main` es la fuente de verdad de Malāk.

Cuando una afirmación del Vault contradiga una fuente oficial vigente y aplicable de Malāk, prevalece la fuente oficial.

La evaluación de autoridad debe considerar jerarquía documental, estado, vigencia, versión, alcance, aprobación, procedencia y relación con el baseline actual.

Una coincidencia semántica, un resumen, una nota, una conversación, una proyección o una salida de RAG no adquieren autoridad por ser relevantes.

La similitud no concede autoridad.

## Fuentes locales de gobierno del Vault

Antes de realizar cambios materiales en el Vault, lee según aplicabilidad:

```text
README.md
00-governance/VAULT_GOVERNANCE.md
00-governance/DOCUMENT_AUTHORITY_MODEL.md
00-governance/CONTENT_LIFECYCLE.md
```

Cuando el trabajo dependa del estado real de Malāk, consulta también las fuentes oficiales correspondientes en `Aranwill/jarvis/main`.

## Revisión integral del Vault

Cuando la tarea solicite revisar el estado del Vault, reconciliarlo con Malāk, detectar inconsistencias, validar una proyección o determinar próximos pasos, la revisión deberá basarse en evidencia y no limitarse a `README.md`.

### Minimum Review Set

Salvo que el alcance solicitado sea explícitamente menor, una revisión integral deberá considerar, según aplicabilidad:

```text
Project Vault
├── AGENTS.md
├── README.md
├── 00-governance/**
├── 01-architecture/**
├── 02-current-baseline/**
├── 03-roadmap/**
├── 04-sprints/**
├── 05-decisions/**
├── 06-security/**
├── 07-audits/**
├── 08-session-context/**
├── 09-repository-snapshots/**
├── 10-knowledge-index/**
│   ├── CONCEPTUAL_FOUNDATIONS.md
│   └── KNOWLEDGE_INDEX.md
└── artefactos directamente afectados

Malāk — source of truth
├── AGENTS.md
├── fuentes normativas aplicables
├── baseline vigente
├── ADR y decisiones aplicables
├── documents/projects/jarvis/ideas.md cuando corresponda
├── docs/project/concepts/** cuando corresponda
├── código y tests relevantes cuando corresponda
└── HEAD / evidencia de repositorio aplicable

Vault Sync Agent
├── reglas de mapping aplicables
├── cobertura de rutas
├── rutas no mapeadas
├── propuesta o PR de sync vigente
└── evidencia de reconciliación aplicable
```

La profundidad de lectura debe ser proporcional a la pregunta. No es obligatorio leer todos los archivos completos cuando una búsqueda o sección concreta aporte evidencia suficiente, pero ninguna fuente relevante puede omitirse silenciosamente.

## Referencias conceptuales

Cuando una revisión trate arquitectura futura, agentes, sandbox, cognición, modelos, memoria, conocimiento, seguridad, ingeniería, evidencia, evaluación, resource governance o self-development, deberán considerarse las referencias conceptuales oficiales de Malāk en:

```text
Aranwill/jarvis
└── docs/project/concepts/**
```

y su proyección derivada en:

```text
10-knowledge-index/CONCEPTUAL_FOUNDATIONS.md
10-knowledge-index/KNOWLEDGE_INDEX.md
```

La presencia de una referencia conceptual en el Vault:

```text
NO aumenta su autoridad
NO la convierte en baseline
NO autoriza implementación
NO autoriza sprint
NO convierte una idea en decisión
```

Si la proyección del Vault diverge de la fuente conceptual oficial, deberá reportarse el drift; no reinterpretarse la fuente para hacer coincidir ambos artefactos.

## Relación con el Vault Sync Agent

El Sync Agent es un mecanismo de detección, comparación y propuesta. No es una fuente de verdad y no gobierna el Vault ni Malāk.

Flujo esperado:

```text
Malāk / source of truth
        ↓
deterministic detection / mapping
        ↓
candidate Vault changes
        ↓
Draft Pull Request
        ↓
human visual review
        ↓
human decision
```

Una propuesta del Sync Agent no se considera correcta por haber sido generada automáticamente.

Toda proyección relevante debe poder remontarse a su fuente.

## Trazabilidad obligatoria

Cuando corresponda, todo contenido derivado o actualizado debe permitir identificar:

- fuente oficial;
- ruta fuente;
- commit o baseline aplicable;
- fecha de revisión;
- estado;
- autoridad documental;
- alcance;
- relaciones relevantes;
- observaciones de vigencia.

No presentes un resumen como hecho oficial si no existe una fuente verificable.

Cuando una fuente no pueda verificarse, indica la limitación y evita completar el vacío mediante inferencia.

## Taxonomía de drift

Las inconsistencias deben clasificarse explícitamente cuando sea posible.

Categorías mínimas:

```text
BASELINE_DRIFT
DOCUMENTATION_DRIFT
CONCEPTUAL_DRIFT
PROJECTION_DRIFT
SYNC_DRIFT
COVERAGE_DRIFT
ENCODING_DRIFT
AUTHORITY_DRIFT
```

Definiciones:

```text
BASELINE_DRIFT
→ el Vault describe un baseline, HEAD, release o estado operativo que no coincide con la fuente oficial vigente.

DOCUMENTATION_DRIFT
→ documentación derivada está desactualizada, incompleta o contradice evidencia oficial aplicable.

CONCEPTUAL_DRIFT
→ una referencia conceptual oficial no está representada correctamente en la proyección conceptual del Vault.

PROJECTION_DRIFT
→ una proyección o resumen derivado modifica, omite o contradice materialmente la fuente que pretende representar.

SYNC_DRIFT
→ el resultado esperado del mecanismo de sincronización no coincide con la proyección actual del Vault.

COVERAGE_DRIFT
→ existe una ruta o familia documental relevante de Malāk que no está cubierta por el mecanismo de mapping cuando debería estarlo.

ENCODING_DRIFT
→ contenido textual presenta corrupción, transformación inesperada de caracteres o line endings que alteran el estado observable.

AUTHORITY_DRIFT
→ un documento derivado, propuesta, nota o referencia conceptual es presentado con una autoridad superior a la que realmente posee.
```

Todo finding de drift deberá, cuando sea posible, incluir:

```text
tipo
fuente de verdad
artefacto divergente
evidencia
impacto
acción recomendada
```

Detectar drift no concede autorización para corregirlo.

## Contradicciones no resueltas

Cuando dos fuentes no puedan reconciliarse de forma segura:

1. no asumir cuál es correcta;
2. identificar ambas fuentes;
3. comparar autoridad, vigencia, alcance y baseline;
4. registrar la contradicción;
5. evitar cambios irreversibles;
6. elevar el asunto a revisión humana.

La ausencia de claridad no concede permiso para modificar.

## Contenido rechazado o excluido

El contenido marcado como `rejected`, `excluded`, `superseded` o equivalente deberá tratarse según `CONTENT_LIFECYCLE.md` y el modelo de autoridad.

No debe reutilizarse como fundamento vigente únicamente por existir en el repositorio o ser recuperable mediante búsqueda.

Las fuentes rechazadas en el repositorio oficial de Malāk no deben reintroducirse indirectamente a través del Vault.

## Control de alcance

No modifiques artefactos fuera del alcance explícitamente aprobado.

No aproveches una tarea para reescribir documentos no relacionados, corregir estilo de forma masiva, actualizar metadatos sin necesidad, reinterpretar fuentes, cambiar jerarquías, incorporar nuevas categorías de autoridad, modificar mappings del Sync Agent o modificar archivos del repositorio oficial de Malāk.

Si el trabajo revela una necesidad adicional, repórtala como finding o propuesta separada.

## Áreas protegidas del Vault

No modifiques sin autorización explícita y alcance identificado:

- `00-governance/**`;
- modelo de autoridad documental;
- lifecycle documental;
- reglas de elegibilidad para contexto o RAG;
- estructura principal del Vault;
- snapshots históricos;
- registros de decisiones;
- artefactos machine-managed;
- políticas de sincronización;
- cualquier documento que pretenda cambiar la relación de autoridad con Malāk.

Una tarea ordinaria de actualización documental no autoriza cambios en estas áreas.

## Preservación de artefactos derivados

Los artefactos derivados deben seguir siendo reconstruibles y subordinados a sus fuentes.

No modifiques una fuente de mayor autoridad para justificar un resumen derivado incorrecto.

Si una proyección está equivocada:

```text
source remains authoritative
        ↓
projection is corrected
```

no:

```text
projection exists
        ↓
source is rewritten to match projection
```

## Secuencia de trabajo obligatoria

Para cualquier cambio:

1. inspecciona el estado Git;
2. identifica cambios preexistentes;
3. lee las reglas locales aplicables;
4. verifica las fuentes oficiales de Malāk cuando el cambio dependa de ellas;
5. confirma el alcance;
6. identifica autoridad, vigencia y procedencia;
7. presenta un plan conciso;
8. aplica el cambio mínimo;
9. ejecuta validación proporcional;
10. revisa diff y alcance;
11. prepara evidencia;
12. respeta las autorizaciones Git.

No descartes, sobrescribas ni absorbas cambios preexistentes no relacionados.

## Disciplina de Git

No realices sin autorización explícita:

- crear, eliminar o cambiar ramas;
- realizar commit;
- realizar push;
- realizar pull o fetch cuando importe el estado remoto;
- realizar merge;
- realizar rebase;
- realizar reset;
- crear tags;
- realizar stash;
- crear un Pull Request;
- actualizar materialmente un Pull Request;
- eliminar archivos;
- reescribir historial.

Nunca uses operaciones destructivas para limpiar cambios del usuario.

## Pull Requests siempre en Draft

Todo Pull Request creado por asistentes, agentes o automatizaciones deberá nacer como `Draft`.

Flujo:

```text
branch
   ↓
changes
   ↓
validation
   ↓
commit
   ↓
push
   ↓
Draft Pull Request
   ↓
assistant / agent presents scope, diff and evidence
   ↓
STOP
   ↓
Owner performs visual review in GitHub
   ↓
Owner manually decides promotion / changes / closure
```

Los asistentes, agentes y automatizaciones:

- pueden preparar cambios;
- pueden validar;
- pueden realizar commit y push con autorización explícita;
- pueden crear únicamente Draft Pull Requests;
- pueden presentar evidencia y findings;
- no pueden promover un Pull Request a `Ready for Review`;
- no pueden usar CLI, API, connector ni automatización para promoverlo;
- no pueden interpretar conformidad verbal como permiso para promoverlo;
- no pueden sustituir la revisión visual del Owner.

La transición:

```text
Draft
→ Ready for Review
```

es exclusivamente humana y deberá realizarse manualmente desde la interfaz de GitHub.

Principio:

> **Author != Reviewer != Authority.**

## Validación proporcional sin loops

La validación se organiza en gates.

### Gate 1 — después de editar

Aplica cuando el contenido cambió:

```text
revisión del diff
git diff --check
UTF-8 / caracteres especiales
validaciones específicas del artefacto
```

### Gate 2 — después de staging

Aplica una vez por contenido staged:

```text
git diff --cached --check
scope / changed files
working tree == staged blob
```

### Gate 3 — antes de push

Aplica una vez al commit que se publicará:

```text
working tree esperado
scope final
UTF-8 de archivos afectados
diff del commit / validación final proporcional
```

Regla antirredundancia:

> **Si un artefacto no cambió desde un gate que ya pasó, no repitas la misma validación únicamente por rutina.**

Repite un gate cuando el archivo cambió después de validarlo, cambió el contenido staged, cambió el commit que será publicado, una nueva evidencia invalida el resultado anterior o la herramienta/entorno de validación cambió de forma relevante.

No conviertas la disciplina de validación en un loop sin nueva información.

## Disciplina UTF-8 y caracteres especiales

Los archivos de texto creados o modificados deberán conservar UTF-8 y caracteres especiales correctos.

En PowerShell, para inspección explícita:

```powershell
Get-Content <archivo> -Raw -Encoding UTF8
```

Para detectar indicadores comunes de mojibake sin incluirlos literalmente:

```powershell
$mojibakePattern = '{0}|{1}|{2}' -f [char]0x00C3, [char]0x00C2, [char]0xFFFD

Get-Content <archivo> -Raw -Encoding UTF8 |
    Select-String -Pattern $mojibakePattern
```

La salida esperada es vacía.

No utilices `git show | Select-String` como prueba de integridad Unicode.

`git diff --check` valida problemas del diff y whitespace; no demuestra por sí solo que el encoding sea correcto.

### Working tree y staged blob

Después de staging, cuando corresponda:

```powershell
$working = git hash-object -- <archivo>
$staged = (git ls-files -s -- <archivo>).Split()[1]
$working -eq $staged
```

El resultado esperado es:

```text
True
```

No repitas esta comparación si el archivo y el index no cambiaron desde el gate que ya pasó.

## Line endings y ruido de metadata

Una advertencia de conversión LF/CRLF no debe interpretarse automáticamente como cambio de contenido.

Si Git muestra un archivo modificado pero el diff está vacío:

1. compara working tree e index por hash;
2. inspecciona `git ls-files --eol`;
3. verifica atributos aplicables;
4. distingue contenido real de metadata/stat noise.

No descartes ni reescribas un archivo solo para eliminar un `M` sin comprobar antes que su contenido sea idéntico.

Los cambios de política global de EOL o `.gitattributes` requieren alcance y evaluación separados.

## Finalización

Todo cambio completado debe informar:

- archivos modificados;
- fuentes consultadas;
- authority / provenance relevante;
- validación ejecutada;
- findings de drift;
- incertidumbre restante;
- estado Git;
- rollback.

Un cambio no se considera correcto únicamente porque el Markdown sea válido. También debe preservar autoridad, trazabilidad, procedencia y coherencia con la fuente oficial.

## Rollback

El rollback debe limitarse a los archivos afectados por el cambio aprobado.

No descartes trabajo no relacionado del usuario.

No modifiques Malāk para revertir un error del Vault.

## Regla final

> **El Vault recuerda, organiza, compara y evidencia. La fuente oficial define; la gobernanza humana decide.**
