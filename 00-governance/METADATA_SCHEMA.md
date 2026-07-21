Biblioteca
/
METADATA_SCHEMA.md


---
document_id: VAULT-METADATA-SCHEMA-001
title: Esquema de metadatos del Malāk Project Vault
document_type: governance
status: active
authority: derived
operational_authority: none
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-21
source_repository: Aranwill/jarvis
source_branch: main
tags:
  - malak
  - vault
  - governance
  - metadata
---

# Esquema de metadatos del Malāk Project Vault

> [!warning] Alcance
> Este documento define el esquema recomendado para documentos nuevos del Malāk Project Vault.
>
> No autoriza una migración masiva ni modifica retroactivamente documentos existentes.

## 1. Objetivo

Establecer un conjunto mínimo, consistente y gobernable de propiedades YAML para:

- identificar documentos;
- distinguir su tipo;
- declarar su estado;
- registrar su autoridad;
- preservar trazabilidad;
- facilitar navegación y recuperación futura;
- evitar que documentos derivados aparenten autoridad operativa.

## 2. Principio de compatibilidad

El Vault contiene documentos creados con esquemas anteriores, incluyendo propiedades como:

```yaml
id:
type:
authority_level:
authority_rank:
source_of_truth:
```

Esos documentos no deben modificarse únicamente para ajustarlos a este esquema.

La normalización retroactiva requerirá:

- una decisión explícita;
- alcance definido;
- revisión documental;
- validación de impacto;
- commits pequeños y reversibles.

## 3. Esquema mínimo recomendado

Todo documento nuevo debería incluir:

```yaml
---
document_id: IDENTIFICADOR-ESTABLE
title: Título legible
document_type: tipo-documental
status: draft
authority: derived
operational_authority: none
created: AAAA-MM-DD
last_reviewed: AAAA-MM-DD
tags:
  - malak
  - vault
---
```

## 4. Propiedades obligatorias

### `document_id`

Identificador único y estable.

Reglas:

- no debe reutilizarse;
- no debe depender del nombre físico del archivo;
- debe permanecer estable aunque el archivo sea movido;
- debe utilizar mayúsculas y guiones cuando corresponda.

Ejemplo:

```yaml
document_id: VAULT-SECURITY-INDEX-001
```

### `title`

Título humano del documento.

Ejemplo:

```yaml
title: Índice de seguridad
```

### `document_type`

Clasificación funcional del documento.

Valores recomendados:

```text
navigation
governance
baseline
roadmap
decision-register
session-context
repository-snapshot
audit
security
architecture
template
reference
```

La incorporación de nuevos tipos debe ser deliberada y documentada.

### `status`

Estado del ciclo de vida documental.

Valores recomendados:

```text
draft
under-review
active
proposed
accepted
rejected
superseded
archived
deprecated
```

El significado completo de cada estado debe interpretarse mediante:

```text
00-governance/CONTENT_LIFECYCLE.md
```

### `authority`

Naturaleza de la autoridad del documento.

Valores recomendados:

```text
official
derived
historical
informational
excluded
```

Para documentos del Vault, el valor predeterminado debe ser:

```yaml
authority: derived
```

La propiedad no reemplaza el modelo definido en:

```text
00-governance/DOCUMENT_AUTHORITY_MODEL.md
```

### `operational_authority`

Indica si el documento puede modificar o gobernar directamente el runtime, código, configuración o infraestructura de Malāk.

Valor permitido actualmente para documentos del Vault:

```yaml
operational_authority: none
```

Ningún documento derivado del Vault debe declarar autoridad operativa.

### `created`

Fecha de creación del documento.

Formato:

```yaml
created: AAAA-MM-DD
```

### `last_reviewed`

Fecha de la última revisión humana significativa.

Formato:

```yaml
last_reviewed: AAAA-MM-DD
```

No debe actualizarse automáticamente al abrir, formatear o mover el archivo.

### `tags`

Etiquetas destinadas a navegación y clasificación.

Ejemplo:

```yaml
tags:
  - malak
  - vault
  - security
```

Las etiquetas no conceden autoridad ni estado.

## 5. Propiedades opcionales

### Fuente documental

```yaml
source_repository: Aranwill/jarvis
source_branch: main
source_commit: HASH_COMPLETO
```

Utilizar cuando el documento derive de un estado específico del repositorio oficial.

### Versión

```yaml
version: 1.0
```

Recomendada para documentos normativos o estructuras reutilizables.

No debe confundirse con la versión nominal de Malāk.

### Documento reemplazado

```yaml
supersedes: DOCUMENT-ID
```

### Documento reemplazante

```yaml
superseded_by: DOCUMENT-ID
```

### Baseline de referencia

```yaml
baseline_reference: HASH-COMPLETO
```

### Relación con sprint

```yaml
sprint_reference: SPRINT-7.2
```

La referencia no implica aprobación ni cierre.

## 6. Propiedades restringidas

Los documentos nuevos no deben utilizar sin una política formal:

```yaml
source_of_truth: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
auto_update: true
```

Estas propiedades pueden sugerir capacidades, autoridad o automatización no implementadas.

Una futura política de recuperación o RAG deberá definirlas expresamente antes de su adopción.

## 7. Ejemplos

### Índice de navegación

```yaml
---
document_id: VAULT-AUDIT-INDEX-001
title: Índice de auditorías
document_type: navigation
status: active
authority: derived
operational_authority: none
created: 2026-07-20
last_reviewed: 2026-07-20
tags:
  - malak
  - vault
  - audits
  - navigation
---
```

El ejemplo siguiente representa deliberadamente un snapshot histórico concreto.

Sus fechas y su `source_commit` no deben actualizarse para reflejar el baseline vigente, porque hacerlo alteraría la evidencia histórica representada.

### Snapshot histórico

```yaml
---
document_id: MALAK-REPOSITORY-SNAPSHOT-2026-07-20-FDB3EE9
title: Malāk Repository Snapshot — 2026-07-20
document_type: repository-snapshot
status: archived
authority: historical
operational_authority: none
source_repository: Aranwill/jarvis
source_branch: main
source_commit: fdb3ee922efc796e53ade1fc3abe4125f4072bd0
created: 2026-07-20
last_reviewed: 2026-07-20
tags:
  - malak
  - vault
  - snapshot
---
```

### Documento en borrador

```yaml
---
document_id: VAULT-EXAMPLE-DRAFT-001
title: Documento de ejemplo
document_type: reference
status: draft
authority: derived
operational_authority: none
created: 2026-07-20
last_reviewed: 2026-07-20
tags:
  - malak
  - vault
  - draft
---
```

## 8. Reglas de aplicación

- Aplicar este esquema a documentos nuevos.
- No reescribir documentos existentes sin una tarea aprobada.
- No agregar propiedades vacías únicamente para completar una plantilla.
- No declarar autoridad superior a la fuente real.
- No utilizar metadatos para simular capacidades no implementadas.
- Mantener cambios pequeños, revisables y reversibles.
- Validar el frontmatter antes de hacer commit.
- Preservar Human in Control.

## 9. Relación con otros documentos

- [[00-governance/GOVERNANCE_INDEX|Índice de gobernanza]]
- [[00-governance/VAULT_GOVERNANCE|Gobernanza del Vault]]
- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[00-governance/CONTENT_LIFECYCLE|Ciclo de vida del contenido]]
- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro]]

## 10. Estado de adopción

Este esquema queda recomendado para documentos creados a partir de su aprobación.

Los documentos anteriores permanecen válidos bajo su esquema original mientras:

- no contradigan la gobernanza vigente;
- mantengan su trazabilidad;
- no aparenten autoridad operativa;
- no sean reemplazados mediante un proceso documentado.