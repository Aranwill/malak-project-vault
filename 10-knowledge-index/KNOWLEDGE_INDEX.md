---
id: MALAK-KNOWLEDGE-INDEX
title: Malāk Knowledge Index
type: knowledge-index
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-07-21
source_of_truth: project-vault
derived: true
operational_context: true
retrieval_enabled: true
retrieval_scope: active
---

# Malāk Knowledge Index

## 1. Propósito

Este documento es el índice maestro de navegación del Malāk Project Vault.

Su función es:

- facilitar el acceso al conocimiento vigente;
- conectar gobernanza, baseline, roadmap y decisiones;
- reducir búsquedas manuales;
- preparar relaciones documentales para Obsidian;
- servir como base futura para índices temáticos;
- preservar la diferencia entre fuentes oficiales y artefactos derivados.

Este índice no reemplaza los documentos enlazados ni les concede autoridad adicional.

---

## 2. Punto de entrada de sesión

- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto operativo de sesión]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline actual]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]

Orden recomendado al iniciar una sesión:

1. contexto de sesión;
2. baseline actual;
3. decisiones pendientes;
4. roadmap;
5. verificación directa del repositorio oficial.

---

## 3. Gobernanza del Vault

- [[00-governance/VAULT_GOVERNANCE|Gobernanza del Vault]]
- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[00-governance/CONTENT_LIFECYCLE|Ciclo de vida del contenido]]

Estas fuentes determinan:

- qué función cumple el Vault;
- qué contenido puede ingresar;
- qué documento prevalece ante contradicciones;
- cómo se clasifican borradores, propuestas y documentos vigentes;
- qué contenido puede utilizarse en contexto operativo;
- qué contenido podrá recuperarse mediante el futuro RAG.

---

## 4. Baseline vigente

- [[02-current-baseline/CURRENT_BASELINE|Malāk Current Baseline]]

Estado documentado al revisar este índice:

```text
Repositorio: Aranwill/jarvis
Rama permanente: main
Versión nominal: v0.6.0-alpha
Último sprint cerrado: Sprint 7.3 — Conversation Provider Boundary Stabilization
Pull request integrado: PR #13
Baseline resultante: fd4da3d371d07b6aa91cc9f1c4d4bac3838ad627
Suite documentada: 74 passed
Próximo sprint aprobado: ninguno
```

## 5. Roadmap

- [[03-roadmap/IMPLEMENTATION_ROADMAP|Malāk Implementation Roadmap]]

Regla:

> La presencia de una iniciativa en el roadmap no constituye autorización para implementarla.

Actualmente:

- los Sprints 7.0, 7.1, 7.2 y 7.3 están cerrados;
- no existe un próximo sprint aprobado;
- las iniciativas futuras requieren revisión y aprobación explícita;
- el cierre de un sprint no autoriza automáticamente el siguiente;
- Sprint 7.3 no aprobó una integración entre `Kernel.receive` y `ConversationService`.

---
## 6. Registro de decisiones

- [[05-decisions/PENDING_DECISIONS|Malāk Pending Decisions]]

Categorías actuales:

Categorías actuales:

### Prioridad alta

- selección del próximo sprint;
- momento de implementación del Security Control Plane;
- versionado y respaldo del Project Vault.

### Prioridad media

- alcance y separación entre logs, métricas y auditoría;
- política de sincronización con Obsidian;
- esquema de metadatos del Vault.

### Decisiones cerradas recientes

- redefinición del Sprint 7.3;
- relación entre Kernel y `ConversationService`.

### Diferidas

- Session Context Generator;
- RAG externo;
- auditor externo;
- Ruff y mypy.

---

## 7. Plantillas operativas

- [[templates/SESSION_CLOSE_TEMPLATE|Plantilla de cierre de sesión]]
- [[templates/SPRINT_CLOSE_TEMPLATE|Plantilla de cierre de sprint]]

Las plantillas deben copiarse antes de utilizarlas.

No deben completarse directamente sobre el archivo original.

---

## 8. Arquitectura

Carpeta:

[[01-architecture/ARCHITECTURE_INDEX|Índice de arquitectura]]

Estado:

Estado:

Índice de navegación creado.

Existe un mapa derivado vigente:

- [[01-architecture/CURRENT_COMPONENTS_MAP|Mapa de componentes actuales]]

El mapa representa el flujo Kernel–Planner–Capability.

El subsistema conversacional se mantiene separado y no existe integración formal entre `Kernel.receive` y `ConversationService`.

Contenido futuro previsto:

- mapa de componentes;
- mapa de contratos;
- límites del Kernel;
- relación Kernel–Planner–Capability;
- subsistema conversacional;
- runtime;
- métricas;
- zonas de confianza;
- dependencias arquitectónicas.

Toda representación deberá:

- derivarse de fuentes oficiales;
- identificar su procedencia;
- respetar la jerarquía documental;
- diferenciar implementación actual y arquitectura futura;
- evitar reinterpretaciones no aprobadas.

No deben crearse diagramas o mapas sin una necesidad concreta.

---

## 9. Sprints

Carpeta:

[[04-sprints/SPRINT_INDEX|Índice de sprints]]

Estado:

Estado:

Índice de navegación creado.

El cierre del Sprint 7.3 se encuentra registrado en:

- [[04-sprints/SPRINT-7.3-CLOSURE|Cierre del Sprint 7.3]]

La reconstrucción retrospectiva de sprints anteriores continúa pendiente y requiere una tarea documental separada.

Podrá contener:

- resúmenes de sprints cerrados;
- evidencia de validación;
- relación entre sprint y baseline;
- referencias a PR;
- referencias a commits;
- resultados de tests;
- documentación de cierre.

No reemplazará:

- las fichas oficiales del repositorio;
- el historial Git;
- los PR;
- los documentos de release.

Sprints cerrados conocidos:

| Sprint | Resultado |
| ------ | --------- |
| 7.0 | CLI mínima con `MockLLMRuntime` |
| 7.1 | Composición de CLI con `OllamaRuntime` |
| 7.2 | Contrato estructural `RuntimeMetricSink` |
| 7.3 | Conversation Provider Boundary Stabilization |

---

## 10. Seguridad

Carpeta:

[[06-security/SECURITY_INDEX|Índice de seguridad]]

Estado:

`Índice de navegación creado. El contenido especializado de seguridad continúa pendiente.`

Contenido futuro previsto:

- riesgos;
- controles;
- límites de autoridad;
- amenazas;
- Security Control Plane;
- Secure Context Manager;
- seguridad del Vault;
- revisión de plugins;
- políticas de sincronización;
- tratamiento de información sensible.

No se almacenarán:

- contraseñas;
- tokens;
- claves privadas;
- secretos de API;
- credenciales;
- dumps sensibles no sanitizados.

La existencia de esta carpeta no implica que el Security Control Plane esté implementado.

---

## 11. Auditorías

Carpeta:

[[07-audits/AUDIT_INDEX|Índice de auditorías]]

Estado:

`Índice de navegación creado. No existen auditorías formales registradas.`

Contenido futuro previsto:

- auditorías documentales;
- auditorías arquitectónicas;
- controles;
- hallazgos;
- evidencia;
- desviaciones;
- remediaciones;
- resultados históricos.

Todo auditor deberá operar:

- en modo de solo lectura por defecto;
- con evidencia reproducible;
- sin capacidad de modificación automática;
- sujeto a revisión humana;
- separado del Kernel y del runtime.

---

## 12. Snapshots del repositorio

Carpeta:

`09-repository-snapshots`

### Snapshots disponibles

- [[09-repository-snapshots/SNAPSHOT_INDEX|Índice de snapshots]]
- [[09-repository-snapshots/2026-07-20_MAIN_FDB3EE9|Snapshot de main — 2026-07-20 — fdb3ee9]]

El snapshot correspondiente al baseline del Sprint 7.3 debe registrarse como un artefacto nuevo e inmutable.

No debe modificarse el snapshot de `fdb3ee9` para representar el estado posterior.

Estado registrado en el snapshot:

- repositorio: `Aranwill/jarvis`;
- rama: `main`;
- commit: `fdb3ee922efc796e53ade1fc3abe4125f4072bd0`;
- `HEAD` local y `origin/main`: coincidentes;
- working tree: limpio;
- tags sobre `HEAD`: ninguno;
- Python validado: `3.12.10`;
- entorno de tests: `.venv`;
- tests: `69 passed in 0.21s`;
- compilación: correcta;
- `git diff --check`: correcto;
- estado documental: histórico e inmutable.

Cada cambio material del repositorio deberá producir un snapshot nuevo.

Los snapshots anteriores no deben editarse para representar estados posteriores.

---

## 13. Project Vault

- [[README|README del Project Vault]]

Ubicación local:

`D:\Ollama\malak-project-vault`

Repositorio remoto independiente:

`Aranwill/malak-project-vault`

Rama permanente:

`main`

El Vault permanece separado de:

- repositorio oficial de Malāk;
- Kernel;
- runtime;
- memoria cognitiva;
- índices vectoriales;
- cachés;
- automatización operativa.

El repositorio oficial conserva la fuente de verdad.

---

## 14. Flujo de conocimiento

```text
Repositorio oficial de Malāk
        ↓
Verificación directa
        ↓
Documentos derivados del Vault
        ↓
Índices de navegación
        ↓
Contexto de sesión
        ↓
Futuro RAG externo
        ↓
Futuro auditor externo

---
```

## 15. Índices futuros

Se crearán únicamente cuando exista suficiente contenido real.

Índices candidatos:

- `ARCHITECTURE_INDEX.md`;
- `SECURITY_INDEX.md`;
- `SPRINT_INDEX.md`;
- `DECISION_INDEX.md`;
- `AUDIT_INDEX.md`;
- `SOURCE_INDEX.md`;
- `GLOSSARY_INDEX.md`.

No deben crearse índices vacíos únicamente para completar la estructura.

Cada índice deberá justificar:

- qué problema de navegación resuelve;
- qué fuentes utiliza;
- qué autoridad posee;
- cómo se mantiene actualizado;
- qué información excluye.

---

## 16. Reglas de navegación

Al utilizar este índice:

- verificar siempre la vigencia del documento enlazado;
- no asumir que una propuesta está aprobada;
- no considerar un resumen superior a su fuente;
- revisar el baseline antes del roadmap;
- revisar decisiones pendientes antes de iniciar trabajo;
- verificar el repositorio para datos variables;
- señalar cualquier contradicción;
- no reutilizar snapshots como si representaran el presente;
- diferenciar documentos activos, históricos y propuestos.

---

## 17. Verificación antes de una sesión técnica

Desde el repositorio oficial:

```powershell
cd D:\Ollama\jarvis

git fetch --prune
git branch --show-current
git status
git rev-parse HEAD
git rev-parse origin/main
git log -1 --oneline

.\.venv\Scripts\Activate.ps1
python -m pytest -q
python -m compileall src tests
git diff --check

---
```

## 18. Regla de actualización

Actualizar este índice cuando:

- se cree un documento principal;
- cambie el baseline;
- se cierre un sprint;
- se apruebe o cierre una decisión;
- se cree un índice temático;
- se incorpore una nueva categoría de conocimiento;
- cambie el flujo de navegación recomendado;
- se genere un nuevo snapshot;
- se archive o reemplace un documento enlazado.

Toda actualización debe conservar enlaces válidos y evitar referencias a documentos inexistentes.

---

## 19. Estado actual de la fundación

### Project Context Foundation

`implementada en su alcance documental inicial`

Incluye:

- gobernanza del Vault;
- modelo de autoridad;
- ciclo de vida del contenido;
- baseline actual;
- roadmap derivado;
- decisiones pendientes;
- contexto de sesión;
- plantillas;
- README;
- Git local;
- respaldo remoto público;
- integración mínima con Obsidian;
- índice maestro;
- primer snapshot formal.

### Obsidian Knowledge Foundation

`iniciada`

Incluye:

- Vault abierto en Obsidian;
- configuración local excluida de Git;
- navegación mediante Wikilinks;
- índice maestro inicial.

Todavía no incluye:

- plugins comunitarios;
- automatización;
- GraphRAG;
- generación automática de contexto;
- índices temáticos avanzados.

---

## 20. Principios rectores

> Un índice ayuda a encontrar conocimiento; no reemplaza su autoridad.

> La navegación debe comenzar desde el contexto vigente y terminar en evidencia verificable.

> No se debe crear estructura documental sin una necesidad real.

> Un snapshot conserva el pasado; el repositorio determina el presente.

> El Vault conserva contexto. El repositorio conserva el estado oficial.

---

## 21. Vault Synchronization Agent Foundation

Documentación propuesta para mantener actualizado el Vault utilizado por Obsidian mediante cambios verificados del repositorio oficial.

### Gobernanza

- [[00-governance/VAULT_SYNC_AGENT_POLICY|Política obligatoria del Vault Synchronization Agent]]

### Arquitectura

- [[01-architecture/VAULT_SYNCHRONIZATION_AGENT_FOUNDATION|Vault Synchronization Agent Foundation]]

### Seguridad

- [[06-security/VAULT_SYNCHRONIZATION_THREAT_MODEL|Modelo de amenazas del Vault Synchronization Agent]]

### Auditoría

- [[07-audits/vault-synchronization/2026-07-21_VAULT_SYNC_FOUNDATION_POLICY|Informe de incorporación documental]]

### Plantilla

- [[templates/VAULT_SYNC_EXECUTION_REPORT_TEMPLATE|Plantilla de informe de ejecución]]

Estado general:

```text
Arquitectura: under_review
Implementación: no aprobada
Autoridad operativa: ninguna
Merge: exclusivamente humano
