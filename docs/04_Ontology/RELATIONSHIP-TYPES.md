---
id: ONTO-RELATIONSHIP-TYPES
title: Relaciones controladas de FisioOS
type: ontology-specification
status: Approved
version: 1.0
---

# RELATIONSHIP-TYPES

| Relación | Dominio | Rango | Inversa |
|---|---|---|---|
| authored_by | PUB, THESIS | PERSON | author_of |
| directed_by | THESIS | PERSON | director_of |
| affiliated_with | PERSON | ORG | has_affiliate |
| founded_by | ORG | PERSON | founder_of |
| offers_service | ORG | SERVICE | offered_by |
| related_to_pathology | EX, TRT, PRO, PUB | PAT | has_related_item |
| evaluates | TEST | PAT, FIND | evaluated_by |
| treated_with | PAT, CASE | TRT | treats |
| includes_exercise | PROGRAM, PRO | EX | included_in |
| supported_by | PAT, TRT, EX, PRO | PUB | supports |
| derived_from | PUB, MEDIA, ASSET | THESIS, PUB, PROCESS | source_of |
| reported_in | PUB, THESIS, ORG, PERSON | MEDIA | reports |
| uses_asset | PUB, PRO, PROCESS | ASSET | used_by |
| part_of_process | WORKFLOW | PROCESS | has_workflow |
| implements_capability | PROCESS, WORKFLOW | CAP | implemented_by |
| uses_dataset | PROCESS, WORKFLOW, CAP | DATASET | used_by |
| produces | PROCESS, WORKFLOW, CAP | ASSET, PUB, CASE, PROGRAM | produced_by |

## Reglas

1. Usar relaciones oficiales antes de crear variantes.
2. Añadir relación inversa cuando sea relevante.
3. Evitar `related_to` salvo que no exista una relación más precisa.
4. Las relaciones clínicas no implican indicación universal.
