---

id: MALAK-PROJECT-VAULT-README
title: Malāk Project Vault
type: index
status: active
authority_level: technical_documentation
authority_rank: 6
version: 1.0
created: 2026-07-20
last_reviewed: 2026-08-11
source_of_truth: project-vault
derived: false
operational_context: true
retrieval_enabled: true
retrieval_scope: active
-----------------------

# Malāk Project Vault

## 1. Descripción

Malāk Project Vault es una capa documental externa, gobernada e independiente del repositorio y del runtime principal de Malāk.

Su propósito es conservar y organizar conocimiento verificable sobre el proyecto para:

* mantener continuidad entre sesiones;
* reducir pérdida de contexto;
* evitar contradicciones y reconstrucciones incorrectas;
* distinguir baseline, decisiones, propuestas y roadmap;
* preservar trazabilidad;
* facilitar revisión arquitectónica;
* preparar Obsidian como interfaz de navegación;
* preparar un futuro RAG externo;
* sentar las bases de un auditor arquitectónico y de seguridad.

El Vault organiza conocimiento sobre Malāk.

No gobierna a Malāk por encima de sus documentos oficiales.

---

## 2. Ubicación

Ubicación local inicial:

```text
D:\Ollama\malak-project-vault
```

Repositorio oficial de Malāk:

```text
D:\Ollama\jarvis
```

Repositorio remoto oficial:

```text
https://github.com/Aranwill/jarvis
```

Rama oficial y permanente:

```text
main
```

El Vault debe permanecer separado del repositorio principal mientras se estabilizan su gobernanza, estructura, seguridad y modelo de versionado.

---

## 3. Fuente de verdad

El repositorio oficial de Malāk conserva la fuente de verdad para:

* código;
* tests;
* configuración;
* manifests;
* releases;
* Blueprint;
* Constitución Cognitiva;
* Constitución de Gobernanza;
* ADR;
* contratos públicos;
* documentación operativa;
* historial Git;
* baseline implementado.

El Vault contiene:

* resúmenes derivados;
* contexto operativo;
* registros de decisiones;
* plantillas;
* snapshots;
* índices;
* relaciones documentales;
* material de apoyo para auditoría.

Cuando exista una contradicción, prevalece la fuente oficial de mayor autoridad y vigencia.

---

## 4. Estado actual de Malāk

Datos verificados al revisar este Vault:

```text
Repositorio: Aranwill/jarvis
Rama permanente: main
Versión nominal: v0.6.0-alpha
Último sprint cerrado: Sprint 7.5 — Security Control Plane Foundation
Pull request de reconciliación más reciente: PR #32
Suite documentada: 304 passed
Próximo sprint aprobado: ninguno
```

Último commit remoto verificado:

```text
7d6feaaaebb53b3c12bc2d1a170be85008ba9e5e
```

Descripción:

```text
Merge pull request #32 from Aranwill/docs/reconcile-project-context-2026-08-11
```

El baseline vigente tiene cerrado Sprint 7.5 — Security Control Plane
Foundation. El bloque 7.x completado comprende los sprints 7.0 a 7.5.

No existe un sprint posterior autorizado.

La frontera entre `Kernel.receive` y `ConversationService` continúa sin
integración formal aprobada.

Estos datos deben revalidarse cuando cambie `HEAD`.

## 5. Principios del Vault

El Vault se rige por los siguientes principios:

* repositorio oficial como fuente de verdad;
* jerarquía documental explícita;
* trazabilidad;
* Human in Control;
* separación respecto del Kernel;
* separación respecto del runtime;
* no modificación automática;
* evidencia antes que memoria;
* propuestas separadas de decisiones;
* índices y cachés reconstruibles;
* solo lectura por defecto para auditoría;
* exclusión de contenido rechazado del contexto activo;
* mínima autoridad para herramientas automáticas.

---

## 6. Estructura

```text
malak-project-vault/
├── 00-governance/
├── 01-architecture/
├── 02-current-baseline/
├── 03-roadmap/
├── 04-sprints/
├── 05-decisions/
├── 06-security/
├── 07-audits/
├── 08-session-context/
├── 09-repository-snapshots/
├── 10-knowledge-index/
├── templates/
└── README.md
```

---

## 7. Descripción de carpetas

### `00-governance`

Contiene las reglas que gobiernan el propio Vault.

Documentos actuales:

* `VAULT_GOVERNANCE.md`;
* `DOCUMENT_AUTHORITY_MODEL.md`;
* `CONTENT_LIFECYCLE.md`.

Esta carpeta define:

* propósito;
* límites;
* niveles de autoridad;
* estados documentales;
* reglas de vigencia;
* elegibilidad para contexto;
* elegibilidad para RAG;
* tratamiento de contenido rechazado;
* control de cambios.

---

### `01-architecture`

Destinada a mapas y resúmenes derivados de la arquitectura oficial.

Podrá contener:

* mapas de componentes;
* relaciones entre módulos;
* diagramas;
* matrices de dependencias;
* límites arquitectónicos;
* resúmenes del Blueprint;
* relaciones entre contratos.

No deberá contener reinterpretaciones que contradigan la documentación oficial.

---

### `02-current-baseline`

Contiene la vista operativa compacta del estado actual de Malāk.

Documento principal:

```text
CURRENT_BASELINE.md
```

Debe reflejar:

* rama;
* versión;
* último sprint cerrado;
* pruebas;
* componentes implementados;
* restricciones;
* fuera de alcance;
* evidencia Git;
* límites e incertidumbres.

Debe actualizarse después de cambios materiales del baseline.

---

### `03-roadmap`

Contiene vistas derivadas de las líneas de implementación.

Documento principal:

```text
IMPLEMENTATION_ROADMAP.md
```

Debe separar:

* sprints cerrados;
* iniciativas conceptualmente aceptadas;
* propuestas;
* elementos diferidos;
* capacidades futuras;
* acciones no autorizadas.

Una entrada en el roadmap no concede autorización para implementarla.

---

### `04-sprints`

Destinada a registros de trabajo y cierres de sprint del Vault.

Podrá contener:

* resúmenes de sprints cerrados;
* evidencia de validación;
* relaciones entre sprint y baseline;
* cierres históricos;
* referencias a fichas oficiales del repositorio.

No debe reemplazar las fichas oficiales de sprint.

Registros históricos disponibles incluyen:

* `SPRINT_INDEX.md`;
* `SPRINT-7.3-CLOSURE.md`;
* `SPRINT-7.4-CLOSURE.md`.

El baseline operativo vigente reconoce Sprint 7.5 como último sprint
formalmente cerrado a partir de la documentación oficial del repositorio
principal. La ausencia de una ficha de cierre específica del Vault no debe
reinterpretarse como un estado anterior del proyecto.

---

### `05-decisions`

Contiene decisiones abiertas, resueltas o diferidas.

Documento principal:

```text
PENDING_DECISIONS.md
```

Debe distinguir:

* pregunta abierta;
* propuesta;
* decisión aprobada;
* decisión rechazada;
* decisión formalizada;
* asunto diferido.

Una conversación no equivale a una decisión formal.

---

### `06-security`

Destinada a conocimiento derivado de seguridad.

Podrá contener:

* mapas de controles;
* riesgos;
* amenazas;
* boundaries;
* relación con Security Control Plane;
* hallazgos;
* políticas de acceso al Vault;
* revisión de plugins;
* reglas de sincronización.

No debe contener secretos.

---

### `07-audits`

Destinada a evidencia e informes de auditoría.

Podrá contener:

* auditorías de arquitectura;
* auditorías documentales;
* hallazgos;
* controles;
* evidencias;
* desviaciones;
* planes de remediación;
* resultados históricos.

Todo auditor deberá operar en modo de solo lectura por defecto.

---

### `08-session-context`

Contiene el contexto compacto para iniciar sesiones.

Documento principal:

```text
MALAK_SESSION_CONTEXT.md
```

Debe incluir:

* identidad del proyecto;
* baseline;
* restricciones;
* decisiones abiertas;
* último sprint cerrado;
* estado del próximo sprint;
* objetivo de la sesión;
* verificaciones obligatorias.

Este archivo debe compartirse al comenzar una nueva sesión de trabajo.

---

### `09-repository-snapshots`

Destinada a snapshots inmutables del estado del repositorio.

Un snapshot podrá registrar:

* fecha;
* rama;
* commit;
* working tree;
* tests;
* compilación;
* diff;
* documentación;
* herramientas utilizadas.

Los snapshots son históricos y no deben modificarse después de su cierre.

---

### `10-knowledge-index`

Destinada a índices de navegación humana.

Podrá contener:

* índices por tema;
* índices por documento;
* relaciones;
* glosario;
* mapas de conceptos;
* índices de ADR;
* índices de riesgos;
* índices de controles.

No debe contener bases vectoriales, embeddings ni cachés binarias.

---

### `templates`

Contiene plantillas reutilizables.

Plantillas actuales:

* `SESSION_CLOSE_TEMPLATE.md`;
* `SPRINT_CLOSE_TEMPLATE.md`.

Las plantillas no representan sesiones o sprints reales hasta que se genere una copia identificada.

---

## 8. Documentos iniciales

Documentos creados durante la fundación inicial:

```text
00-governance\VAULT_GOVERNANCE.md
00-governance\DOCUMENT_AUTHORITY_MODEL.md
00-governance\CONTENT_LIFECYCLE.md
02-current-baseline\CURRENT_BASELINE.md
03-roadmap\IMPLEMENTATION_ROADMAP.md
05-decisions\PENDING_DECISIONS.md
08-session-context\MALAK_SESSION_CONTEXT.md
templates\SESSION_CLOSE_TEMPLATE.md
templates\SPRINT_CLOSE_TEMPLATE.md
README.md
```

---

## 9. Jerarquía de autoridad

Orden general:

1. autoridad constitucional;
2. gobernanza;
3. arquitectura;
4. decisiones aprobadas;
5. baseline y releases;
6. documentación técnica vigente;
7. roadmap aprobado;
8. planes de sprint;
9. propuestas;
10. notas y conversaciones;
11. contenido rechazado o excluido.

La relevancia semántica no reemplaza la autoridad.

Un documento más parecido a una consulta no debe prevalecer sobre una fuente superior.

---

## 10. Estados documentales

Estados admitidos:

```text
draft
proposed
accepted
active
superseded
deprecated
rejected
archived
```

Reglas principales:

* `draft`: no aprobado;
* `proposed`: pendiente de revisión;
* `accepted`: aprobado conceptualmente;
* `active`: vigente;
* `superseded`: reemplazado;
* `deprecated`: uso limitado;
* `rejected`: excluido;
* `archived`: histórico.

La existencia de un archivo no demuestra vigencia.

---

## 11. Flujo de inicio de sesión

Antes de comenzar una sesión sobre Malāk:

1. abrir `MALAK_SESSION_CONTEXT.md`;
2. revisar `CURRENT_BASELINE.md`;
3. revisar `PENDING_DECISIONS.md`;
4. verificar el repositorio;
5. definir un objetivo único;
6. registrar el alcance;
7. evitar iniciar cambios no aprobados.

Verificación recomendada:

```powershell
cd D:\Ollama\jarvis

git branch --show-current
git status
git fetch --prune
git log -1 --oneline

python -m pytest -q
python -m compileall src tests
git diff --check
```

Condiciones esperadas:

* rama `main`;
* working tree limpio;
* remoto sincronizado;
* tests en verde;
* compilación sin errores;
* diff sin errores.

---

## 12. Flujo de cierre de sesión

Al finalizar:

1. copiar `SESSION_CLOSE_TEMPLATE.md`;
2. asignar fecha e identificador;
3. registrar trabajo realizado;
4. registrar decisiones;
5. registrar contradicciones;
6. registrar riesgos;
7. registrar validaciones;
8. actualizar documentos afectados;
9. actualizar `MALAK_SESSION_CONTEXT.md`;
10. definir un único próximo paso recomendado.

El cierre de una sesión no autoriza el siguiente cambio.

---

## 13. Flujo de cierre de sprint

Cuando se cierre un sprint:

1. copiar `SPRINT_CLOSE_TEMPLATE.md`;
2. registrar alcance aprobado;
3. registrar implementación real;
4. registrar tests;
5. registrar compilación;
6. registrar diff;
7. validar arquitectura;
8. validar seguridad;
9. documentar rollback;
10. registrar PR y merge;
11. actualizar baseline;
12. actualizar contexto;
13. actualizar decisiones;
14. eliminar la rama temporal cuando corresponda.

Un sprint se cierra con evidencia, no con intención.

---

## 14. Uso con Obsidian

Este directorio podrá abrirse directamente como Vault de Obsidian.

Uso esperado:

* navegación;
* edición Markdown;
* enlaces internos;
* propiedades YAML;
* búsqueda;
* grafo;
* índices;
* relaciones entre documentos.

Obsidian no debe:

* reemplazar Git;
* modificar el repositorio oficial automáticamente;
* ejecutar scripts no revisados;
* almacenar secretos;
* publicar el Vault;
* otorgar autoridad a notas informales.

Los plugins deberán evaluarse antes de su instalación.

---

## 15. Uso futuro con RAG

El futuro RAG externo deberá:

* aplicar filtros de autoridad;
* aplicar filtros de estado;
* aplicar filtros de vigencia;
* citar fuentes;
* diferenciar hechos y propuestas;
* excluir contenido rechazado;
* priorizar documentos activos;
* conservar trazabilidad;
* utilizar índices reconstruibles;
* permanecer desacoplado del Kernel.

Orden recomendado de recuperación:

1. estado;
2. vigencia;
3. autoridad;
4. baseline aplicable;
5. alcance;
6. relevancia semántica;
7. fecha;
8. calidad de la fuente.

La similitud vectorial no concede autoridad.

---

## 16. Artefactos reconstruibles

Se consideran derivados y reconstruibles:

* embeddings;
* bases vectoriales;
* cachés;
* índices automáticos;
* grafos generados;
* fragmentos procesados;
* resultados temporales;
* resúmenes automáticos;
* reportes no aprobados.

Estos elementos no deben almacenarse como fuentes documentales permanentes.

Ubicación futura recomendada:

```text
D:\Ollama\malak-rag-runtime
```

---

## 17. Seguridad

El Vault no debe almacenar:

* contraseñas;
* tokens;
* claves privadas;
* secretos de API;
* credenciales;
* datos personales innecesarios;
* configuraciones sensibles;
* dumps no sanitizados;
* contenido externo hostil sin procesar.

Los mecanismos de sincronización, backup y plugins deberán evaluarse formalmente.

Principio:

> Validate once, trust briefly, verify continuously.

---

## 18. Versionado

El modelo definitivo de versionado continúa pendiente de decisión.

Opciones en evaluación:

* Git local independiente;
* repositorio privado independiente;
* respaldo cifrado;
* Git más backup externo;
* almacenamiento local con snapshots.

Hasta resolverlo:

* no inicializar sincronización automática;
* no publicar el Vault;
* no conectarlo con el repositorio principal;
* no subir índices o cachés;
* no almacenar secretos.

---

## 19. Relación con el repositorio principal

```text
Repositorio oficial
    ↓
Fuente de verdad
    ↓
Verificación
    ↓
Project Vault
    ↓
Contexto, índices y auditoría
```

El flujo inverso debe requerir revisión humana:

```text
Project Vault
    ↓
Propuesta
    ↓
Revisión
    ↓
Aprobación
    ↓
Cambio formal en repositorio
```

El Vault no puede modificar directamente la autoridad oficial.

---

## 20. Estado de implementación del Vault

### Project Context Foundation

```text
fundación inicial completada
```

### Obsidian Knowledge Foundation

```text
fundación inicial completada
```

### Session Context Generator

```text
diferida
```

### External Project RAG

```text
no implementado
```

### Architecture & Security Auditor Foundation

```text
no implementada
```

---

## 21. Próximos pasos del Vault

Próximos pasos sujetos a revisión y aprobación:

1. mantener sincronizados los documentos activos después de cambios materiales;
2. detectar referencias operativas desfasadas sin alterar registros históricos;
3. evaluar un control determinista de frescura documental;
4. revisar el modelo de versionado y respaldo cuando exista una necesidad concreta;
5. revisar la política de sincronización con Obsidian;
6. revisar el esquema de metadatos;
7. mantener diferido el Session Context Generator;
8. mantener no implementado el RAG externo;
9. mantener no implementado el auditor externo.

Esta lista no autoriza implementaciones automáticas.

## 22. Reglas para asistentes

Todo asistente que utilice este Vault deberá:

* responder en español;
* verificar datos variables;
* tratar `main` como rama oficial;
* diferenciar baseline y roadmap;
* no inventar cantidad de tests;
* no asumir el próximo sprint;
* no introducir capacidades artificiales;
* no modificar el Kernel sin necesidad;
* no incorporar Ruff improvisadamente;
* no presentar propuestas como decisiones;
* señalar contradicciones;
* conservar trazabilidad;
* trabajar mediante pasos pequeños;
* respetar Human in Control.

---

## 23. Principios rectores

> El repositorio conserva el estado real.

> El Vault conserva el contexto verificable.

> Obsidian facilita la navegación.

> El RAG facilitará la recuperación.

> El auditor facilitará la validación.

> Ninguna de estas capas obtiene autoridad para modificar Malāk automáticamente.

> La evidencia puede originar una propuesta; solamente la gobernanza puede convertirla en una modificación.

## Navegación principal

- [[10-knowledge-index/KNOWLEDGE_INDEX|Índice maestro de conocimiento]]
- [[00-governance/VAULT_GOVERNANCE|Gobernanza del Vault]]
- [[00-governance/DOCUMENT_AUTHORITY_MODEL|Modelo de autoridad documental]]
- [[00-governance/CONTENT_LIFECYCLE|Ciclo de vida del contenido]]
- [[02-current-baseline/CURRENT_BASELINE|Baseline actual]]
- [[03-roadmap/IMPLEMENTATION_ROADMAP|Roadmap de implementación]]
- [[05-decisions/PENDING_DECISIONS|Decisiones pendientes]]
- [[08-session-context/MALAK_SESSION_CONTEXT|Contexto de sesión]]
- [[01-architecture/ARCHITECTURE_INDEX|Índice de arquitectura]]
- [[04-sprints/SPRINT_INDEX|Índice de sprints]]
- [[04-sprints/SPRINT-7.3-CLOSURE|Cierre del Sprint 7.3]]
- [[09-repository-snapshots/SNAPSHOT_INDEX|Índice de snapshots]]
