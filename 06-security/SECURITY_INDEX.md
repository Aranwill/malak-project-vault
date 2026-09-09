---
document_id: VAULT-SECURITY-INDEX-001
title: Índice de seguridad
document_type: navigation
status: active
authority: derived
operational_authority: none
last_reviewed: 2026-09-09
tags:
  - malak
  - vault
  - security
  - navigation
---

# Índice de seguridad

<!-- MALAK_VAULT_SYNC:START -->
## Proyección automática de sincronización

> [!warning] Estado derivado pendiente de revisión
> Este bloque fue generado de forma determinista a partir de
> `Aranwill/jarvis/main`. No aprueba decisiones, no cierra
> sprints y no reemplaza la revisión humana del documento.

- **Run ID:** `20260909T124638201108Z_10d6945d_4d016aa6`
- **HEAD oficial observado:** `10d6945d6f19a61c9dc9724738545107b9148707`
- **Commit previamente observado:** `6458fd98b3af16401d485495eb7cd1eae4b23881`
- **Generado:** `2026-09-09T12:46:38.201108+00:00`
- **Prioridad:** `high`
- **Disposición:** `review_required`

### Estado estructurado de la fuente oficial

- **Ficha de sprint más reciente:** `docs/project/sprints/SPRINT-7.11.md`
- **Título declarado:** Sprint 7.11 — Reproducible Validation Pipeline Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible

### Commits oficiales observados

- 10d6945d6f19a61c9dc9724738545107b9148707	Merge pull request #71 from Aranwill/docs/security-policy-context-map-20260909
- c5ae605cbbea73552c7ec68b5e2f3338e8a95b19	Merge pull request #70 from Aranwill/docs/research-horizon-security-reconciliation-20260909
- 590e0f60154663daad51c12e125ed152fd574ffd	docs: remove trailing whitespace from security header
- 96fbfc2337112dc123e7c2bd2a563f9c84d4c810	docs: record security policy and context mapping reconciliation
- c64eab525e4291068eb9ca76cc0f60d77a6f29c2	docs: clarify security policy authority and future capabilities
- d07551d1d5be3252d5d1adbc316671e28fc50dab	docs: add security and research horizon PR checks
- e9ea04ae88a7070d6a99a2b0eb54992b0384de67	docs: add security horizon checks to development checklist
- 3c712317b4d31c353a2bb7a8e5ec8b542d73d5f8	docs: include security and research horizon in construction admission
- cfeb9b40e92fc5ceb8772e1ca5af7f7f47045f8e	docs: make security and research horizon mandatory review inputs
- 5f11b07e7a34d277a6fc4de4e331a99c164f1027	docs: reconcile active security policy with current architecture
- e093ef3c654369bcbc0eae1dc1e0222edcf86a5b	docs: clarify world models vs autonomous self-modification
- 91f24646b279fc96ae442dcbab63fed14842a517	docs: index Malak research horizon map
- 0ec2f22a43b02eca53e427b4c8265f86aeefd4f0	docs: add Malak research horizon security reconciliation

### Evidencia que originó esta proyección

- `security-change` por `SECURITY.md`
<!-- MALAK_VAULT_SYNC:END -->

<!-- MALAK_OPERATIONAL_STATE:START -->
## Estado operativo derivado

> Estado machine-owned derivado de la fuente oficial.
> No concede autoridad ni reemplaza decisiones humanas.

- **HEAD oficial:** `10d6945d6f19a61c9dc9724738545107b9148707`
- **Ficha de sprint vigente:** `docs/project/sprints/SPRINT-7.11.md`
- **Titulo declarado:** Sprint 7.11 — Reproducible Validation Pipeline Foundation
- **Estado declarado:** `completado`
- **`as_of_commit` declarado:** no disponible
<!-- MALAK_OPERATIONAL_STATE:END -->

> [!danger] Sin autoridad operativa
> Este documento no implementa, habilita ni modifica controles de seguridad de Malāk.
>
> Los controles efectivos deben existir y validarse en el repositorio oficial o en la infraestructura correspondiente.

## Propósito

Esta sección organiza conocimiento derivado relacionado con:

- modelo de autoridad;
- límites de confianza;
- políticas de autorización;
- amenazas y riesgos;
- controles propuestos;
- validaciones de seguridad;
- incidentes y hallazgos;
- decisiones pendientes.

## Estado actual

Este índice no declara implementado ningún componente de seguridad de Malāk.

El repositorio oficial `Aranwill/jarvis/main` mantiene la fuente de verdad para
la política y los controles efectivos. La política activa se encuentra en:

```text
SECURITY.md
versión: 2.0
estado: activo
clasificación: política de seguridad protegida
```

La política distingue explícitamente entre:

```text
control implementado
!=
requisito de seguridad futuro
!=
autorización de implementación
```

El Vault Synchronization Agent permanece fuera del Security Control Plane, del Kernel y del runtime.

Su modelo de amenazas cubre la Fase 1 read-only cerrada y la extensión
gobernada `controlled-proposal`, siempre como tooling externo,
determinista y sin autoridad operativa.

La aceptación de ese modelo:

- documenta amenazas, controles verificados y brechas conocidas;
- registra riesgos residuales;
- no convierte al agente en un control de seguridad de Malāk;
- no concede autoridad operativa;
- no autoriza fases posteriores;
- no modifica el baseline operativo de Malāk.

## Navegación relacionada

- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline vigente]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[07-audits/AUDIT_INDEX|Auditorías]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]
- [[10-knowledge-index/CONCEPTUAL_FOUNDATIONS|Fundamentos conceptuales]]
- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro]]

Fuente oficial principal:

```text
Aranwill/jarvis/SECURITY.md
```

Referencia conceptual no normativa relacionada:

```text
Aranwill/jarvis/docs/project/concepts/MALAK_RESEARCH_HORIZON_MAP.md
```

## Principios aplicables

- Human in Control.
- Denegación por defecto.
- Separación entre solicitar, autorizar, ejecutar y auditar.
- Menor privilegio.
- Least Context cuando corresponda.
- Defensa en profundidad.
- Zero Trust interno.
- Validación explícita de entradas y límites.
- Trazabilidad de decisiones y acciones.
- Ningún LLM constituye por sí mismo una autoridad de seguridad.
- Una propuesta de seguridad no equivale a un control implementado.
- Un research gap no equivale a una autorización de implementación.

Separaciones estables preservadas por la política oficial:

```text
Model != System
Intelligence != Authority
Capability != Permission
Decision != Execution
Execution != Evidence
Evidence != Authority

Conversation != Memory
Memory != Knowledge
Knowledge != Policy

External Content != Instructions
Tool Output != Authority
Artifact Trust != Execution Authorization
```

## Postura de seguridad activa representada

La política oficial `SECURITY.md` v2.0 formaliza como postura activa:

- Zero Trust y Defense in Depth;
- Human in Control;
- default deny y comportamiento fail-closed para operaciones sensibles;
- Security Control Plane con separación PDP / PEP / protected operation / evidence;
- Secure Context Lifecycle vigente sin presentar identidad criptográfica fuerte como implementada;
- Prompt & Context Trust Boundary;
- requisitos de confianza y anti-poisoning para futura Memory / Knowledge;
- AI Supply-Chain Trust como requisito de admisión futura;
- delegación sin expansión de autoridad;
- Compromise Containment & Trust Revocation;
- defensa activa, deception, honeypots y forensics dentro de fronteras autorizadas;
- clasificación y disclosure de datos;
- Resource Governance para futuras superficies de mayor riesgo.

La política conserva explícitamente como no implementados, entre otros:

- identidad y firmas criptográficas fuertes;
- PKI;
- nonce / replay protection;
- MFA;
- Secure Context Manager criptográfico completo;
- Secure Message Bus / IPC seguro;
- Sandbox gobernado;
- agentes y tools operativos;
- navegación;
- Memory persistente;
- automatización defensiva avanzada.

La presencia de estos requisitos no habilita ningún componente ni sprint.

## Contención, deception y respuesta

La postura futura preserva el siguiente orden defensivo conceptual:

```text
SUSPECT
  ↓
FREEZE / REVOKE AUTHORITY
  ↓
CUT OR RESTRICT COMMUNICATION
  ↓
ISOLATE / QUARANTINE
  ↓
PRESERVE EVIDENCE
  ↓
ASSESS BLAST RADIUS
  ↓
REVALIDATE RELATED TRUST
  ↓
REBUILD FROM KNOWN-GOOD
  ↓
VERIFY BEFORE REINTRODUCTION
```

Principio derivado de la política oficial:

> **Compromise must reduce authority, never expand investigation privileges.**

Deception, honeypots, honeynets, honeytokens y observación adversarial permanecen
sujetos a capacidades aprobadas, aislamiento, egress controlado y supervisión
humana. Una IP u otro indicador técnico constituye evidencia observada, no prueba
automática de identidad.

Malāk no realiza `hack back` autónomo. Un ataque recibido no concede autoridad
para comprometer infraestructura externa.

## Relación con Research Horizon

`MALAK_RESEARCH_HORIZON_MAP.md` es una referencia conceptual no normativa para
reconciliar investigación reciente con conceptos existentes y detectar gaps
reales sin duplicar arquitectura.

Entre las líneas que deben revalidarse antes de futuras implementaciones están:

- Prompt & Context Trust Boundary — `REINFORCE_EXISTING`;
- Memory & Knowledge Trust / Poisoning — `GAP_CANDIDATE`;
- AI Supply-Chain Trust — `GAP_CANDIDATE`;
- Agent Identity & Delegation — `GAP_CANDIDATE`;
- Compromise Containment & Trust Revocation — `GAP_CANDIDATE`;
- Data Classification & Disclosure Control — `GAP_CANDIDATE`;
- Governed Interoperability MCP/A2A — `WATCH`;
- Governed Procedural Learning — `REINFORCE_EXISTING`.

Estas clasificaciones ayudan a no olvidar investigación ya realizada, pero:

```text
research horizon != roadmap
research gap != approved architecture
research gap != implementation authorization
```

## Clasificación recomendada

Los futuros documentos de esta sección deberán identificarse como uno de los siguientes tipos:

- modelo de amenaza;
- evaluación de riesgo;
- propuesta de control;
- especificación de seguridad;
- validación;
- hallazgo;
- incidente;
- decisión;
- referencia derivada.

## Restricción permanente

El Vault no debe almacenar secretos operativos, credenciales, tokens, claves privadas ni datos sensibles necesarios para ejecutar Malāk.

## Modelos de amenazas documentados

- [[06-security/VAULT_SYNCHRONIZATION_THREAT_MODEL|Modelo de amenazas del Vault Synchronization Agent]]

Estado:

```text
accepted
```

Alcance:

```text
Fase 1 completada y cerrada
Controlled-proposal aprobado
```

Autoridad operativa:

```text
none
```

Controles verificados durante la Fase 1:

- comandos Git auditados como read-only;
- validación de repositorio, rama y `HEAD`;
- allowlist y denylist;
- controles TOCTOU;
- validación de rutas;
- validación estructural básica de Markdown y de archivos YAML
  independientes;
- validación de enlaces Markdown relativos y metadatos cubiertos;
- hashes SHA-256;
- sanitización de evidencia;
- límites de tamaño y alcance;
- lock de ejecución;
- polling externo;
- invariantes de no modificación;
- `last_applied_commit: null`;
- Malāk intacto;
- Vault intacto;
- cero modificaciones de snapshots históricos.

Controles adicionales de `controlled-proposal`:

- escritura limitada a una rama aislada del Vault;
- allowlist de documentos, que actualmente mantiene snapshots fuera del
  alcance de escritura;
- PR obligatoriamente draft;
- ausencia de force-push, aprobación y merge;
- identidad exacta de la propuesta pendiente;
- reconciliación posterior a una decisión humana verificable.

Brechas técnicas conocidas:

Controles correctivos certificados:

- revalidación del contenido final después de escribir;
- validación de frontmatter YAML en documentos Markdown;
- validación de wikilinks;
- denylist explícita correcta para `09-repository-snapshots/**`;
- recuperación remota de propuestas cuando la PR existe y la
  persistencia local no quedó completada;
- registro explícito del modo operativo `manual-on-demand`;
- normalización de finales de línea CRLF obtenidos mediante GitHub CLI
  antes de interpretar la identidad remota de una propuesta.

Estos controles fueron implementados y certificados durante el
Incremento Correctivo Integral 5.

Su cierre no elimina los riesgos residuales del sistema ni modifica la
autoridad del agente.

Riesgos residuales documentados:

- error humano durante la revisión;
- publicación accidental de evidencia sensible;
- ampliación prematura de permisos;
- respaldo remoto sin revisión previa;
- falsos positivos y falsos negativos;
- deriva futura de políticas;
- TOCTOU entre push, PR y persistencia local;
- compromiso de credenciales con permiso sobre el Vault;
- rama o PR huérfana ante un fallo remoto;
- validadores documentales incompletos;
- diferencias entre Windows y CI.

El modelo no constituye un componente del Security Control Plane.

Fase 2 y posteriores permanecen no aprobadas.

Cualquier fase con escritura requerirá un nuevo modelo de amenazas, permisos mínimos, estrategia de credenciales, rollback y aprobación humana explícita.
