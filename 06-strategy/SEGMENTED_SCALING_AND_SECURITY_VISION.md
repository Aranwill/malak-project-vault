---
id: MALAK-SEGMENTED-SCALING-SECURITY-VISION
title: Visión de escalado segmentado y seguridad de Malāk
type: strategy-derived
status: approved_for_future_planning
authority_level: non_normative_strategy
created: 2026-07-29
last_reviewed: 2026-07-29
source_repository: Aranwill/jarvis
source_branch: main
source_commit: 4a2f49a0007290ee6b290710e28946c40cee41ff
source_pr: 24
derived: true
operational_authority: none
implementation_authorized: false
---

# Visión de escalado segmentado y seguridad de Malāk

## Propósito

Conservar la visión estratégica aprobada mediante la PR #24 sin confundirla
con arquitectura implementada, sprint aprobado o autoridad operativa.

## Ejes

- control plane horizontal y soberano;
- Domain Packs subordinados;
- conocimiento y evidencia gobernados;
- navegación externa mediante autorización y sandbox;
- revisión externa periódica;
- laboratorio educativo de seguridad;
- evaluación adversarial;
- gemelo adversarial y deception;
- defensa activa dentro de fronteras propias;
- flotas de agentes;
- presencia pública y beta progresiva.

## Jerarquía de políticas

```text
Constituciones
    → Blueprint y Gobernanza global
    → Domain Governance Profile
    → Jurisdiction Policy Pack
    → Organization Policy
    → Workflow Policy
    → autorización y ejecución
```

Una capa inferior puede restringir, pero no ampliar autoridad.

## Defensa activa y contingencia

Dentro de infraestructura propia o autorizada, Malāk podrá detectar,
contener, aislar, bloquear, engañar, revocar, cerrar, activar kill switches,
preservar evidencia y recuperar desde un baseline confiable.

Ningún agente podrá autoasignarse roles, elevar permisos ni deducir
autoridad ofensiva por haber recibido un ataque.

## Respuesta externa

Permanece diferida. Requeriría autoridad legal explícita, atribución
validada, alcance determinado, supervisión humana competente y una
capacidad institucional separada.

## Estado

```text
planificación futura aprobada
diseño detallado no aprobado
implementación no aprobada
sin número de sprint asignado
```

Este documento no modifica el baseline, no crea autoridad operativa y no
aprueba navegación, malware, honeypots públicos, hack back ni beta pública.
