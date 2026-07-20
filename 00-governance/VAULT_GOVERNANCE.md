# Malāk Project Vault Governance

## 1. Propósito

El Malāk Project Vault es una capa documental externa, gobernada e independiente del runtime principal de Malāk.

Su propósito es:

* conservar un contexto actualizado, compacto y verificable del proyecto;
* facilitar la continuidad entre sesiones de trabajo;
* reducir contradicciones, desvíos y pérdida de contexto;
* organizar conocimiento técnico, arquitectónico, operativo y de seguridad;
* preparar una futura base de conocimiento navegable mediante Obsidian;
* permitir la construcción posterior de un RAG externo con filtros de autoridad;
* sentar las bases de un auditor arquitectónico y de seguridad independiente.

El Vault no forma parte del Kernel ni del runtime operativo de Malāk.

---

## 2. Fuente de verdad

El repositorio oficial de Malāk conserva la fuente de verdad para:

* código fuente;
* tests;
* configuraciones;
* manifests;
* releases;
* documentación arquitectónica oficial;
* Blueprint;
* Constitución Cognitiva;
* gobernanza;
* ADR aprobados;
* políticas de seguridad;
* documentación de implementación vigente.

El Vault no reemplaza, sobrescribe ni redefine esos documentos.

Los contenidos del Vault deben referenciar, resumir, organizar o analizar la información oficial sin modificar su autoridad original.

---

## 3. Principio de separación

El Vault debe permanecer separado de:

* Kernel;
* Planner;
* runtime LLM;
* capabilities operativas;
* memoria interna de Malāk;
* sistemas de ejecución;
* índices vectoriales productivos;
* cachés operativas;
* automatizaciones con capacidad de escritura.

El Vault podrá ser consultado por herramientas externas, pero no deberá obtener autoridad operativa sobre Malāk.

---

## 4. Principio de autoridad documental

No todos los documentos poseen el mismo nivel de autoridad.

La autoridad debe determinarse según:

* origen;
* estado;
* vigencia;
* aprobación;
* tipo documental;
* relación con el baseline actual.

Una conversación, nota, idea, borrador o propuesta no debe interpretarse como una decisión aprobada.

Los sistemas de búsqueda, RAG, resumen y auditoría deberán respetar el modelo definido en:

`DOCUMENT_AUTHORITY_MODEL.md`

---

## 5. Principio de trazabilidad

Todo contenido relevante incorporado al Vault deberá poder vincularse con su origen.

Cuando corresponda, deberá registrarse:

* documento fuente;
* ruta dentro del repositorio;
* versión o release;
* commit;
* fecha de revisión;
* estado;
* responsable de aprobación;
* relaciones con ADR, sprint, riesgo o control;
* observaciones de vigencia.

No deben presentarse resúmenes como hechos oficiales cuando no exista una fuente verificable.

---

## 6. Principio de no modificación automática

Ningún LLM, agente, script o herramienta podrá modificar automáticamente documentos de máxima autoridad.

Las actualizaciones propuestas por herramientas automáticas deberán:

1. generarse como propuesta;
2. conservar evidencia;
3. indicar el origen del cambio;
4. identificar documentos afectados;
5. ser revisadas por una persona;
6. aprobarse explícitamente antes de incorporarse.

La generación automática de contexto no equivale a autoridad para modificar el baseline.

---

## 7. Principio Human in Control

Toda decisión que altere:

* arquitectura;
* seguridad;
* gobernanza;
* roadmap;
* baseline;
* permisos;
* alcance de un sprint;
* documentación oficial;

requiere aprobación humana explícita.

El Vault puede registrar, comparar, sugerir y advertir, pero no decidir por sí mismo.

---

## 8. Estados documentales

Los documentos y artefactos podrán utilizar los siguientes estados:

* `draft`: contenido en elaboración;
* `proposed`: propuesta pendiente de revisión;
* `accepted`: contenido aprobado;
* `active`: contenido vigente y aplicable;
* `superseded`: reemplazado por una versión posterior;
* `deprecated`: vigente de forma limitada, pendiente de retiro;
* `rejected`: contenido rechazado y no aplicable;
* `archived`: preservado únicamente como evidencia histórica.

El comportamiento de cada estado se define en:

`CONTENT_LIFECYCLE.md`

---

## 9. Contenido rechazado

Los documentos rechazados deberán:

* conservarse únicamente cuando exista valor histórico o de auditoría;
* marcarse explícitamente como `rejected`;
* quedar excluidos del contexto operativo;
* quedar excluidos del RAG activo por defecto;
* no reutilizarse como base arquitectónica;
* no mezclarse con documentación vigente.

Un documento rechazado no debe influir en respuestas, planes o decisiones futuras.

---

## 10. Contexto de sesión

El archivo:

`08-session-context/MALAK_SESSION_CONTEXT.md`

será el punto de entrada principal para nuevas sesiones de trabajo.

Deberá contener solamente información vigente, resumida y necesaria para continuar el proyecto sin revalidar toda su historia.

Como mínimo deberá incluir:

* identidad del proyecto;
* baseline actual;
* rama base;
* release vigente;
* estado de tests;
* componentes implementados;
* principios no negociables;
* restricciones activas;
* último sprint completado;
* próximo sprint aprobado;
* decisiones pendientes;
* riesgos actuales;
* objetivo concreto de la sesión.

El contexto de sesión no reemplaza los documentos oficiales.

---

## 11. Información derivada

Los siguientes elementos se consideran artefactos derivados y reconstruibles:

* embeddings;
* índices vectoriales;
* índices de texto;
* grafos;
* cachés;
* resultados temporales de búsqueda;
* fragmentos procesados;
* resúmenes generados automáticamente;
* snapshots técnicos no aprobados.

Estos artefactos no deben considerarse fuentes de verdad.

Su pérdida no debe comprometer la integridad documental del proyecto.

---

## 12. Uso de Obsidian

Obsidian podrá utilizarse como interfaz humana para:

* navegar documentos;
* visualizar relaciones;
* editar Markdown;
* consultar metadatos;
* explorar decisiones;
* relacionar sprints, módulos, riesgos y controles;
* visualizar el grafo de conocimiento.

Obsidian no reemplaza Git ni modifica la jerarquía documental.

Los plugins utilizados deberán evaluarse antes de habilitar capacidades de escritura automática, sincronización externa o ejecución de código.

---

## 13. Uso futuro de RAG

El futuro RAG externo deberá:

* priorizar documentos según autoridad;
* filtrar por estado y vigencia;
* citar fuentes;
* diferenciar hechos, decisiones, propuestas y notas;
* excluir contenido rechazado por defecto;
* evitar que una coincidencia semántica prevalezca sobre la autoridad documental;
* conservar trazabilidad entre respuesta y documento fuente.

La similitud vectorial no concede autoridad.

---

## 14. Auditoría futura

El futuro auditor de Malāk deberá permanecer independiente del Kernel y operar en modo de solo lectura por defecto.

Deberá poder comparar:

* arquitectura declarada;
* implementación real;
* tests;
* dependencias;
* configuración;
* políticas;
* telemetría;
* evidencia operativa.

Sus resultados deberán clasificarse como:

* conforme;
* parcialmente conforme;
* no conforme;
* no verificable;
* no aplicable.

Una observación de auditoría no podrá modificar automáticamente el sistema auditado.

---

## 15. Control de cambios

Todo cambio material en la gobernanza del Vault deberá:

1. documentar la motivación;
2. identificar el impacto;
3. conservar la versión anterior;
4. indicar el responsable de aprobación;
5. actualizar la fecha de revisión;
6. verificar que no contradiga la gobernanza oficial de Malāk.

---

## 16. Principio rector

> El Vault organiza y preserva conocimiento sobre Malāk, pero no gobierna a Malāk por encima de sus documentos oficiales.

> La evidencia puede originar una propuesta; solamente la gobernanza puede convertirla en una modificación.
