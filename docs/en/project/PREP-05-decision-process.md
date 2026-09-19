# PREP-05. IMXO Decision Process

**Status:** DRAFT  
**Document type:** preparatory project process  
**Purpose:** to define how IMXO turns open questions into research, requirements, design alternatives, architectural decisions, and ultimately normative specification text.

> PREP-05 defines the decision-making and traceability process. Rules for writing normative standard text, normative terminology, Draft versions, and specification structure belong to PREP-06.

---

## 1. Core principle

IMXO does not use a single artificial status chain such as:

`OPEN → RESEARCH → PROPOSED → ACCEPTED → NORMATIVE`

Research, requirements, design proposals, architectural decisions, and normative text are different artifact types with different lifecycles.

Instead, IMXO uses linked document classes:

- `Q` — open question;
- `RSCH` — research;
- `REQ` — requirement;
- `DES` — design and comparison of alternatives;
- `ADR` — architectural decision;
- `SPEC` — normative specification text.

A typical path may look like this:

```text
Q
↓
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

This path is not a mandatory linear sequence.

One research document may produce several requirements. One requirement may rely on several research documents. One architectural decision may resolve several design proposals. Correcting an obvious error may not require a separate research document.

## 2. Open questions — `Q`

A `Q` records a question that the project has not yet resolved.

Open questions are maintained in a living registry:

`docs/en/project/open-questions.md`

Each question has a permanent identifier:

`Q-0001`, `Q-0002`, `Q-0003`, and so on.

Identifiers are never reused.

Minimum question fields:

- identifier;
- statement;
- status;
- area;
- source;
- related research;
- resolution, if the question is closed.

Allowed statuses:

- `OPEN` — the question has not yet been resolved;
- `RESOLVED` — the question has been closed by an accepted decision;
- `SUPERSEDED` — the question has been replaced by a more precise or broader formulation.

A closed question is not removed from the registry.

## 3. Research — `RSCH`

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

`COMPLETE` does not mean that the subject has been researched permanently or exhaustively.

A research document may recommend an alternative, but it cannot declare that alternative to be an IMXO architectural decision.

## 4. Requirements — `REQ`

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

## 5. Design — `DES`

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

## 6. Architectural decisions — `ADR`

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

## 7. Revising decisions

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

## 8. Normative text — `SPEC`

`SPEC` contains the normative outcome of accepted requirements and architectural decisions.

PREP-05 does not define specification release statuses, rules for `MUST / SHOULD / MAY`, the structure of normative and informative sections, or Draft versioning.

Those rules belong to PREP-06.

Important:

> An `ACCEPTED` ADR is not the same as a published normative version of the standard.

## 9. Identifiers

Global sequential identifiers are used within each class:

```text
Q-0001
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

## 10. Filenames

Standalone documents use the following pattern:

```text
RSCH-0001-jumbf-jlink.md
DES-0001-container-layout.md
ADR-0001-container-strategy.md
```

An ADR normally records one material decision in one file.

An RSCH document normally covers one standalone research subject or research question.

DES is used for one major design question or a related group of alternatives.

REQ entries are grouped into thematic documents rather than stored as one file per requirement.

## 11. Traceability

The project must make it possible to trace a material requirement or normative decision to its origin without archaeology through Git history.

Documents may include links such as:

```text
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

Not every field is required in every document.

## 12. GitHub Issues and Discussions

GitHub Issues, Discussions, and other external feedback channels are not mandatory parts of the internal IMXO process.

At the current stage, the project does not use them as its primary decision-making system.

If external proposals are received later, the maintainer may convert a material question into a standard IMXO artifact.

Discussion on an external platform does not automatically become an architectural decision.

## 13. Decision authority

`ACCEPTED` status is assigned according to the current IMXO governance model.

PREP-05 does not establish a specific future governance structure.

At the current stage, final architectural decisions are recorded by the project maintainer.

## 14. Research completion criteria

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

## 15. Relationship to PREP-00

PREP-00 remains the project's historical baseline checkpoint.

Open questions from PREP-00 are transferred to the living `open-questions.md` registry.

After that transfer, PREP-00 is not rewritten merely to change question statuses.

## 16. Relationship to PREP-06

PREP-05 defines:

- document classes;
- the decision process;
- the open-question registry;
- traceability;
- revision of decisions.

PREP-06 will separately define the rules for writing and structuring the normative standard.

## 17. PREP-05 outcome

Once PREP-05 is accepted, the project must have:

- a formal decision process;
- a living registry of open questions;
- a permanent identifier system;
- `RSCH`, `DES`, and `ADR` templates;
- rules for forming and tracing `REQ` entries;
- rules for revising decisions.
