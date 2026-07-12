---
id: GRAPH-DOCTORADO-001
title: Grafo de relaciones del doctorado
type: relationship-map
status: Approved
version: 1.0
created: 2026-07-13
---

# GRAPH-DOCTORADO-001 — Grafo de relaciones del doctorado

## Relación principal

[[PERSON-001]]
→ autor_de → [[THESIS-000001]]

## Dirección

[[THESIS-000001]]
→ dirigida_por → [[PERSON-002]]

[[THESIS-000001]]
→ dirigida_por → [[PERSON-003]]

[[THESIS-000001]]
→ dirigida_por → [[PERSON-004]]

## Instituciones

[[THESIS-000001]]
→ vinculada_con → [[ORG-002]]

[[THESIS-000001]]
→ investigación_realizada_en → [[ORG-005]]

## Publicaciones

[[THESIS-000001]]
→ genera → [[PUB-000001]]

[[THESIS-000001]]
→ línea_continuada_por → [[PUB-000002]]

[[THESIS-000001]]
→ línea_continuada_por → [[PUB-000006]]

[[THESIS-000001]]
→ línea_continuada_por → [[PUB-000008]]

## Medios

[[THESIS-000001]]
→ difundida_en → [[DOSSIER-000001]]

[[THESIS-000001]]
→ relacionada_con → [[DOSSIER-000002]]

[[THESIS-000001]]
→ difundida_en_radio → [[MEDIA-000027]]

[[THESIS-000001]]
→ difundida_en_televisión → [[MEDIA-000028]]

## Aplicaciones

[[THESIS-000001]]
→ relacionada_con → [[PAT-000005]]

[[THESIS-000001]]
→ pertenece_a → [[RESEARCH-001]]

[[THESIS-000001]]
→ pertenece_a → [[RESEARCH-005]]
