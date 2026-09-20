# IMXO documentation

IMXO documentation is organized by purpose so that research, requirements, design work, accepted decisions, and normative specification text remain distinct.

## Document classes

- `project/` — project preparation, baseline documents, rules, and plans;
- `research/` — research into existing standards, containers, and technologies;
- `requirements/` — IMXO requirements;
- `design/` — design work performed before a final decision is accepted;
- `decisions/` — ADRs and other accepted architectural decisions;
- `specification/` — normative specification text;
- `conformance/` — conformance rules and validation material;
- `glossary/` — terms and definitions.

Directories are created when their first substantive document is added.

## Languages and identifiers

English and Russian documentation use mirrored structures under `docs/en/` and `docs/ru/`. Equivalent documents use the same filenames and technical identifiers wherever possible.

Identifiers such as `PREP-00`, `RSCH-01`, `REQ-001`, `ADR-0001`, `object_id`, and `content_hash` are not translated.

## Published project documents

- [`project/PREP-00-baseline.md`](project/PREP-00-baseline.md) — initial project baseline;
- [`project/PREP-05-decision-process.md`](project/PREP-05-decision-process.md) — completed decision-making and traceability process;
- [`project/PREP-06-specification-writing-rules.md`](project/PREP-06-specification-writing-rules.md) — completed writing rules for the future normative specification;
- [`project/open-questions.md`](project/open-questions.md) — living index of open questions;
- [`project/questions/`](project/questions/) — individual cards for material questions;
- [`templates/Q-template.md`](templates/Q-template.md) — open-question card template;
- [`templates/RSCH-template.md`](templates/RSCH-template.md) — research document template;
- [`templates/DES-template.md`](templates/DES-template.md) — design document template;
- [`templates/ADR-template.md`](templates/ADR-template.md) — architectural decision template;
- [`templates/SPEC-section-template.md`](templates/SPEC-section-template.md) — future normative specification section template;
- [`templates/TRACEABILITY-register-template.md`](templates/TRACEABILITY-register-template.md) — separate informative bidirectional traceability register template.

Russian documentation is available under [`../ru/`](../ru/README.md).

## Document boundaries

Research compares evidence and alternatives. Requirements state needs and constraints. Design documents develop proposals. ADRs record accepted decisions. The specification states the resulting normative requirements.

A hypothesis or design proposal is not an accepted decision unless that status is explicitly recorded.
