# IMXO Traceability Register — Template

> This file is a template for an informative engineering artifact. The actual Traceability Register is created after the first requirements and normative SPEC elements exist.

## 1. Requirements traceability

| Requirement | Use cases | Questions | Research | Design | Decision | Specification |
|---|---|---|---|---|---|---|
| REQ-XXXX | USE-XXXX | Q-XXXX | RSCH-XXXX | DES-XXXX | ADR-XXXX | stable SPEC anchor |

Multiple references are permitted in a single cell.

There is no requirement to fill every artifact class artificially when it is not needed.

## 2. Decision traceability

| Decision | Use cases | Questions | Research | Requirements | Design | Specification |
|---|---|---|---|---|---|---|
| ADR-XXXX | USE-XXXX | Q-XXXX | RSCH-XXXX | REQ-XXXX | DES-XXXX | stable SPEC anchor |

## 3. Specification backtrace

| SPEC anchor | Requirement | Decision | Use cases | Questions | Research |
|---|---|---|---|---|---|
| stable SPEC anchor | REQ-XXXX | ADR-XXXX | USE-XXXX | Q-XXXX | RSCH-XXXX |

This table provides reverse traceability from normative text to the origin of a decision.

## 4. Future conformance traceability

After conformance tooling exists, an additional table may be added:

| SPEC anchor / Requirement | Conformance rule | Test vector | Validator test | Status |
|---|---|---|---|---|
| | | | | |

PREP-06 does not require this table to be created before the corresponding material exists.

## Rules

- The Traceability Register is Informative.
- It does not replace normative `SPEC`.
- Many-to-many relationships are permitted.
- The `Use cases` and `Questions` fields are optional and are not created artificially for every relationship.
- References use stable identifiers or anchors where possible.
- A displayed section number must not be the sole reference point.
- A missing intermediate artifact class is not created merely to fill the table.
