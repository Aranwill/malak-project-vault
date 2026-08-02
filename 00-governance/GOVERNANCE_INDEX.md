---
document_id: VAULT-GOVERNANCE-INDEX-001
title: Índice de gobernanza del Vault
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-07-22
tags:
  - malak
  - vault
  - governance
  - navigation
---

# Índice de gobernanza del Vault

> [!warning] Alcance
> Esta sección gobierna el uso documental del Malāk Project Vault.
>
> No reemplaza la gobernanza oficial existente en el repositorio de Malāk ni concede autoridad operativa al Vault.

## Documentos principales

- [[00-governance/VAULT_GOVERNANCE|Gobernanza del Vault]]
- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[00-governance/CONTENT_LIFECYCLE|Ciclo de vida del contenido]]
- [[00-governance/METADATA_SCHEMA|Esquema de metadatos]]

## Principios permanentes

- El repositorio oficial es la fuente de verdad.
- El Vault contiene representaciones derivadas.
- Obsidian es únicamente una interfaz.
- Ningún documento del Vault puede modificar Malāk automáticamente.
- Las decisiones requieren aprobación humana explícita.
- Los snapshots históricos son inmutables.
- Una propuesta no constituye una decisión.
- Una referencia derivada no reemplaza su fuente.

## Uso recomendado

Antes de crear o modificar un documento del Vault:

1. identificar su fuente;
2. determinar su nivel de autoridad;
3. asignar un estado documental;
4. registrar la fecha de revisión;
5. enlazar la fuente o el baseline correspondiente;
6. evitar duplicar contenido oficial sin necesidad;
7. confirmar que el documento no adquiere autoridad operativa.

## Navegación relacionada

- [[HOME|Inicio]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline vigente]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]
- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro]]
## Vault Synchronization Agent

- [[00-governance/VAULT_SYNC_AGENT_POLICY|Política obligatoria del Vault Synchronization Agent]]

Estado de la política:

```text
accepted
```

Estado de implementación:

```text
Fase 1 completada y cerrada
Controlled-proposal aprobado; núcleo operativo implementado
Conformidad técnica completa: pendiente de incremento correctivo
Modo manual-on-demand
```

Autoridad operativa:

```text
none
```

La política conserva el cierre histórico de Fase 1 e incorpora la
extensión independiente `controlled-proposal`, registrada en
`DEC-RES-009`.

La Fase 1:

- operó en modo determinista y de solo lectura;
- mantuvo `Aranwill/jarvis/main` intacto;
- mantuvo el Vault intacto;
- no utilizó LLM;
- no creó ramas, commits, push ni pull requests mediante el agente;
- no modificó snapshots históricos;
- preservó `last_applied_commit: null`.

Fase 2 y posteriores permanecen no aprobadas.

La extensión vigente permite únicamente una rama aislada, commits, push
y PR draft sobre documentos allowlisted del Vault. No autoriza:

- escritura directa en `main` del Vault;
- escritura fuera del allowlist;
- force-push o reescritura de historia;
- aprobación, auto-merge o merge de PR;
- propuestas autónomas sin invocación manual;
- scheduler operativo;
- servicio permanente;
- daemon;
- webhooks;
- uso de LLM;
- integración con Kernel o runtime;
- modificación de Malāk;
- modificación de snapshots históricos.

La suite vigente (`230 passed`) verifica el núcleo de ese flujo, pero no
demuestra todavía conformidad completa con todos los controles normativos.
Permanecen como requisitos correctivos no implementados:

- revalidar el contenido final después de insertar la proyección;
- validar frontmatter YAML y wikilinks de documentos Markdown;
- corregir la denylist explícita a `09-repository-snapshots/**`;
- recuperar de forma gobernada una rama o PR creada antes de persistir
  su identidad local;
- registrar el disparador real `manual-on-demand` en los informes.

Estos requisitos no amplían autoridad ni autorizan por sí solos un nuevo
incremento de implementación.

Cualquier ampliación de alcance requiere una decisión independiente y aprobación humana explícita.
