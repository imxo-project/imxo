# PREP-05. IMXO Decision Process

**Status:** DONE  
**Closing date:** 2026-09-19  
**Document type:** preparatory project process  
**Purpose:** to define how IMXO connects use cases, open questions, research, requirements, design alternatives, architectural decisions, and normative specification text.

> PREP-05 defines the decision-making and traceability process. Rules for writing normative standard text, normative terminology, Draft versions, and specification structure belong to PREP-06. The `USE` class and the role of the research plan were added by the targeted PREP-08 amendment without reopening PREP-05.

---

## 1. Core principle

IMXO does not use a single artificial status chain such as:

`OPEN → RESEARCH → PROPOSED → ACCEPTED → NORMATIVE`

Use cases, open questions, research, requirements, design proposals, architectural decisions, and normative text are different artifact types with different lifecycles.

Instead, IMXO uses linked document classes:

- `Q` — open question;
- `USE` — informative use case;
- `RSCH` — research;
- `REQ` — requirement;
- `DES` — design and comparison of alternatives;
- `ADR` — architectural decision;
- `SPEC` — normative specification text.

A typical nonlinear model may look like this:

```text
USE ↔ Q
 \    /
  RSCH
    ↓
   REQ
    ↓
   DES
    ↓
   ADR
    ↓
   SPEC
```

This diagram is not a mandatory linear sequence. Other traceable paths and many-to-many relationships are permitted.

One research document may produce several requirements. One requirement may rely on several research documents. One architectural decision may resolve several design proposals. Correcting an obvious error may not require a separate research document.

## 2. Open questions — `Q`

A `Q` records a question that the project has not yet resolved.

Living index of open questions:

`docs/en/project/open-questions.md`

Question cards:

`docs/en/project/questions/`

Each question has a permanent identifier:

`Q-0001`, `Q-0002`, `Q-0003`, and so on.

Identifiers are never reused.

Each material question has its own Markdown card. The `open-questions.md` index contains a concise list and links to the cards.

Minimum card fields:

- identifier;
- statement;
- status;
- area;
- source;
- context;
- related research;
- related requirements;
- design documents;
- resolution, if the question is closed.
- brief status history.

Allowed statuses:

- `OPEN` — the question has not yet been resolved;
- `RESOLVED` — the question has been closed by an accepted decision;
- `SUPERSEDED` — the question has been replaced by a more precise or broader formulation.

A closed question is not removed.

## 3. Use cases — `USE`

`USE` is an informative artifact describing actors/systems, context, problem/need, expected outcome, boundaries, assumptions, and relationships with other project artifacts.

`USE` does not define architecture and is not a normative requirement, research evidence, or a promise to include a feature in a particular standard version.

Identifiers use the format `USE-0001`, `USE-0002`, and so on. They are global within the `USE` class, language- and path-independent, immutable, and never reused.

`USE` statuses are:

- `DRAFT`;
- `REVIEW`;
- `COMPLETE`;
- `WITHDRAWN`;
- `SUPERSEDED`.

`Status` describes card maturity. `COMPLETE` means the description is sufficiently complete; it does not mean `ACCEPTED` or a commitment to support the use case.

The `REVIEW` stage is optional. An editorial change may preserve `COMPLETE`; a substantive change to the same scenario returns the card to `REVIEW`; an effectively new scenario receives a new ID and the old card becomes `SUPERSEDED`. `WITHDRAWN` closes an incomplete card without replacing it.

A separate `Disposition` field describes the project's position toward the use case:

- `CANDIDATE`;
- `TARGET`;
- `NON-TARGET`;
- `DEFERRED`.

`TARGET` does not automatically turn the use case or its mentioned features into a `REQ`, v0.1 scope, or normative text.

The process and lifecycle are defined by PREP-08. The current Russian index is at `docs/ru/use-cases/README.md`, and the Russian template is at `docs/ru/templates/USE-template.md`.

## 4. Research — `RSCH`

`RSCH` answers the question:

> What is known about the subject, and which conclusions can be justified by the available sources?

Research must:

- use primary or authoritative sources;
- record the versions, editions, and dates of the standards being studied;
- separate facts from interpretation;
- identify assumptions explicitly;
- compare relevant alternatives;
- describe advantages, limitations, and implications for IMXO separately;
- record remaining unknowns.

`RSCH` statuses:

- `DRAFT`;
- `REVIEW`;
- `COMPLETE`;
- `SUPERSEDED`.

`COMPLETE` means that the research answers its question sufficiently for the current project stage.

`COMPLETE` does not mean absolute or final completeness of the subject.

A research document may recommend an alternative, but it cannot declare that alternative to be an IMXO architectural decision.

## 5. Requirements — `REQ`

`REQ` answers the question:

> What must IMXO provide, support, or guarantee?

A requirement should describe a needed property or constraint rather than a specific implementation method, unless that method is itself necessary for compatibility.

Good requirement example:

> The format must allow implementations to safely skip unknown optional extensions.

Poor requirement example:

> Every object must have a 32-byte header.

The second example is a design decision and must be considered through `DES` and `ADR`.

`REQ` statuses:

- `PROPOSED`;
- `ACCEPTED`;
- `REJECTED`;
- `SUPERSEDED`.

Requirements are not stored as one Markdown file per requirement.

They are grouped into thematic documents, while each individual requirement receives its own global identifier:

`REQ-0001`, `REQ-0002`, `REQ-0003`, and so on.

A requirement identifier must not encode a thematic category. The category is stored separately as metadata.

## 6. Design — `DES`

`DES` answers the question:

> How can a requirement or group of requirements be implemented?

A `DES` document may include:

- alternatives A/B/C;
- binary layouts;
- field tables;
- overhead calculations;
- complexity estimates;
- prototypes;
- trade-off comparisons;
- compatibility analysis;
- security analysis.

`DES` statuses:

- `DRAFT`;
- `REVIEW`;
- `COMPLETE`;
- `SUPERSEDED`.

`ACCEPTED` is not used as a `DES` status.

The selected alternative is recorded in a separate `ADR`.

## 7. Architectural decisions — `ADR`

`ADR` answers the question:

> What decision did the project make, and why?

`ADR` statuses:

- `PROPOSED`;
- `ACCEPTED`;
- `REJECTED`;
- `WITHDRAWN`;
- `SUPERSEDED`.

An `ADR` is required for a decision that materially affects at least one of the following:

- file compatibility;
- implementation compatibility;
- the physical container model;
- the logical model;
- security;
- extensibility;
- long-term compatibility;
- data interpretation;
- replacement of a previously accepted architectural decision.

Typical subjects that require an ADR include:

- container strategy;
- endianness;
- block or object structure;
- object identifiers;
- index model;
- extension model;
- text model;
- integrity/trust model;
- provenance model.

An ADR is not required for minor editorial changes.

## 8. Revising decisions

An accepted decision may be reconsidered.

An old ADR is not rewritten as though the earlier decision never existed.

When a decision is replaced:

```text
ADR-0012
Status: SUPERSEDED
Superseded by: ADR-0031
```

The new ADR states:

```text
ADR-0031
Status: ACCEPTED
Supersedes: ADR-0012
```

Documents with `REJECTED`, `WITHDRAWN`, and `SUPERSEDED` status remain in the project history.

Document identifiers are never reused.

## 9. Normative text — `SPEC`

`SPEC` contains the normative outcome of accepted requirements and architectural decisions.

PREP-05 does not define specification release statuses, rules for `MUST / SHOULD / MAY`, the structure of normative and informative sections, or Draft versioning.

Those rules belong to PREP-06.

Important:

> An `ACCEPTED` ADR is not the same as a published normative version of the standard.

## 10. Identifiers

Global sequential identifiers are used within each class:

```text
Q-0001
USE-0001
RSCH-0001
REQ-0001
DES-0001
ADR-0001
```

Preparatory documents continue to use the existing scheme:

```text
PREP-00
PREP-01
PREP-02
...
```

Identifiers:

- are not translated;
- are not reused;
- do not change when a document is moved;
- do not encode a thematic area.

The thematic area is stored separately.

## 11. Filenames

Standalone documents use the following pattern:

```text
RSCH-0001-jumbf-jlink.md
DES-0001-container-layout.md
ADR-0001-container-strategy.md
```

Question cards use the following pattern:

```text
Q-0001-container-architecture.md
Q-0002-physical-file-structure.md
```

Use-case cards use the following pattern:

```text
docs/ru/use-cases/USE-0001-example-slug.md
```

An ADR normally records one material decision in one file.

An RSCH document normally covers one standalone research subject or research question.

DES is used for one major design question or a related group of alternatives.

REQ entries are grouped into thematic documents rather than stored as one file per requirement.

## 12. Traceability

The project must make it possible to trace a material requirement or normative decision to its origin without archaeology through Git history.

Documents may include links such as:

```text
Related use cases:
- USE-0003

Related questions:
- Q-0003

Based on:
- RSCH-0004
- RSCH-0007

Requirements:
- REQ-0012
- REQ-0018

Decision:
- ADR-0006

Specified in:
- SPEC § ...
```

The logical register model is:

```text
Requirement | Use cases | Questions | Research | Design | Decision | Specification
```

Relationships are many-to-many. Not every field is required in every document, and a related `USE` is not required for every `REQ`.

## 13. GitHub Issues and Discussions

GitHub Issues are the primary public entry point for external proposals, material feedback, contributor questions, public discussion, and coordination of significant Pull Requests.

An Issue is created when a separate public discussion point provides independent value. At the current founder-led stage, the Project Lead may directly create or change a `Q`, `USE`, research plan, PREP amendment, or other process artifact when an Issue would only duplicate work already discussed and being documented.

An Issue by itself:

- is not research;
- is not a requirement;
- is not an architectural decision;
- does not automatically change the specification.

After initial review, a material Issue may be formalized as one or more project artifacts:

- `Q`;
- `USE`;
- `RSCH`;
- `REQ`;
- `DES`;
- `ADR`.

The existing `Q-0001…Q-0012` questions were transferred from PREP-00 and do not require retrospective Issues.

GitHub Discussions may be used for external or preliminary discussion, but they are not an architectural decision source by themselves.

A change to PREP-05 after its closure proceeds through a normal repository change that preserves history. A separate Issue is used when it helps public discussion or coordination, not as a mandatory ritual step.

## 14. Research plan

The future `docs/ru/project/research-plan.md` is a single living project-management document for research order, priorities, dependencies, and queue state.

It is not a separate artifact class, evidence, a research result, or a technical basis for `REQ`, `ADR`, or `SPEC`. The `PLAN-*` class and identifiers are not introduced.

The plan does not reserve `RSCH` identifiers: a number is assigned only when an actual research document is created.

PREP-08 defines the role of this path but does not create the initial research plan.

## 15. Decision authority

`ACCEPTED` status is assigned according to the current IMXO governance model.

At the current stage, final architectural decisions are recorded by the project maintainer.

A future working group or technical committee may use the same document system without changing identifiers or history.

## 16. Research completion criteria

An `RSCH` document may be moved to `COMPLETE` when:

1. the original question is stated;
2. the principal authoritative sources have been studied;
3. the external standard version and date have been recorded;
4. facts are separated from interpretation;
5. relevant alternatives have been considered;
6. implications for IMXO have been described;
7. remaining unknowns have been listed;
8. the material is sufficient for the next project step.

Absolute research completeness is not required.

## 17. Relationship to PREP-00

PREP-00 remains the project's historical baseline checkpoint.

Open questions from PREP-00 have been transferred to the living registry and separate `Q` cards.

PREP-00 is not rewritten merely to change the current status of those questions.

## 18. Relationship to PREP-06

PREP-05 defines:

- document classes;
- the decision process;
- the open-question registry and cards;
- traceability;
- revision of decisions;
- the role of Issues as a public entry point and coordination tool.

PREP-06 will separately define the rules for writing and structuring the normative standard.

## 19. Relationship to PREP-08

PREP-08 adds `USE`, its lifecycle and `Disposition`, the nonlinear traceability model, and the role of `research-plan.md`. The amendment clarifies the role of GitHub Issues, does not change the status of PREP-05, and does not begin research.

## 20. PREP-05 outcome

PREP-05 is complete.

The project has:

- a formal decision process;
- a living index of open questions;
- separate cards for material questions;
- the informative `USE` class, its template, and the Russian index;
- a permanent identifier system;
- `Q`, `USE`, `RSCH`, `DES`, and `ADR` templates;
- rules for forming and tracing `REQ` entries;
- nonlinear many-to-many traceability among `USE / Q / RSCH / REQ / DES / ADR / SPEC`;
- a defined role for the future `research-plan.md` without a `PLAN-*` class;
- rules for revising decisions;
- a defined role for GitHub Issues as a public entry point and coordination tool, rather than a mandatory predecessor to every artifact.

Further process changes follow the normal project change process and do not return PREP-05 to an unfinished preparatory state.
