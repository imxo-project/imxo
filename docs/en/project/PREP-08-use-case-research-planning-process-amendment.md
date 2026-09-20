# PREP-08. Use-Case and Research Planning Process Amendment

**Russian title:** Поправка процесса: сценарии применения и планирование исследований  
**Status:** DONE  
**Date:** 2026-09-20  
**Type:** process amendment  
**Applies to:** PREP-05 and related process, navigation, and traceability documents

## 1. Purpose

PREP-08 closes a process gap found after completion of the initial PREP-00 through PREP-07 preparation baseline and before the systematic `RSCH` cycle begins.

The amendment:

- introduces `USE` as a full artifact class;
- defines the `USE` lifecycle and purpose;
- separates use cases from questions, research, and requirements;
- adds `USE` to project traceability;
- defines the role of `research-plan.md` without introducing a separate `PLAN-*` class;
- clarifies the role of GitHub Issues at the current founder-led stage;
- defines language-version rules for `USE`;
- establishes use-case navigation;
- updates the PREP-05 process without reopening it.

[`PREP-05`](PREP-05-decision-process.md) remains `DONE`. PREP-08 is a subsequent targeted process amendment.

## 2. Reason for the amendment

PREP-05 defined these classes:

- `Q`;
- `RSCH`;
- `REQ`;
- `DES`;
- `ADR`;
- `SPEC`.

Before systematic research began, two kinds of information still lacked a formal place in the process:

1. IMXO use cases;
2. the research management plan.

Use cases cannot be properly hidden inside `Q`, `RSCH`, or `REQ`:

- `Q` describes an unknown or question;
- `RSCH` contains research and evidentiary work;
- `REQ` records an accepted project requirement;
- `USE` describes an application situation, actors or systems, the problem, expected outcome, and scenario boundaries.

The research plan is likewise not research, evidence, a requirement, or an architectural decision.

## 3. GitHub Issues at the current stage

GitHub Issues remain the primary public channel for:

- external proposals;
- material feedback;
- contributor questions;
- major changes that benefit from a separate public discussion point;
- coordination of significant Pull Requests;
- triage of externally submitted proposals.

An Issue is **not a mandatory intermediate artifact** for every internal project change.

At the current founder-led research stage, the Project Lead may directly create or change `Q`, `USE`, the research plan, PREP amendments, and other process documents when a separate Issue adds no independent value.

An Issue need not be created merely to duplicate formally a decision that has already been discussed and is being documented.

An Issue is not a technical decision and does not replace `Q`, `USE`, `RSCH`, `REQ`, `DES`, `ADR`, or `SPEC`.

## 4. The `USE` class

`USE` is an informative project artifact describing an IMXO use case.

It primarily answers:

- who or which system participates;
- the context in which the task arises;
- the problem or need;
- the outcome required by the scenario;
- the scenario boundaries;
- known limitations of the current workflow;
- why the scenario may be relevant to IMXO;
- which open questions require further research.

`USE` does not define IMXO architecture.

`USE` is not a normative requirement.

`USE` is not evidence that a feature is necessary.

`USE` is not a promise to include a feature in a particular standard version.

## 5. Distinction between `USE` and other classes

### USE vs Q

`USE` describes an application situation.

`Q` describes an unknown that needs to be resolved.

Example:

```text
USE:
A user saves a screenshot of an interface.
The visual appearance needs to be preserved while the text remains programmatically available.

Q:
How should the relationship between text and visual image regions be represented?
```

One `USE` may produce multiple `Q` items. One `Q` may relate to multiple `USE` items. Research may reveal a new `USE`.

### USE vs RSCH

`USE` describes context and expected outcome.

`RSCH` verifies facts, alternatives, constraints, and hypotheses.

The existence of a `USE` does not by itself establish the market, technical, or regulatory significance of a scenario.

### USE vs REQ

`USE` does not automatically become a `REQ`.

A `USE → REQ` relationship records traceability of motivation and context, not automatic derivation of a normative requirement.

One `USE` may relate to multiple `REQ` items. One `REQ` may relate to multiple `USE`, `Q`, and `RSCH` items.

### USE vs DES / ADR / SPEC

`USE` does not select an implementation.

`DES` compares and designs alternatives. `ADR` records an accepted architectural decision. `SPEC` contains the normative outcome.

## 6. The process is a graph, not a pipeline

PREP-08 does not introduce a mandatory linear sequence.

Typical relationships may look like this:

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

Other traceable paths are also permitted, for example:

```text
USE → REQ
Q → RSCH → REQ
USE → Q → RSCH
RSCH → new USE
RSCH → new Q
```

Not every artifact must pass through every class.

## 7. USE identifiers

Each `USE` receives a permanent global identifier:

```text
USE-0001
USE-0002
USE-0003
...
```

Identifier rules:

- the sequence is global within the `USE` class;
- the ID is language-independent;
- the ID is independent of directory or subject;
- the ID is never reused;
- when a scenario is replaced, its old ID remains in project history;
- a new independent or superseding scenario receives a new ID.

The first real scenario after PREP-08 receives `USE-0001`.

PREP-08 itself does not create `USE-0001`.

## 8. USE status

A `USE` has one of these statuses:

### DRAFT

The scenario is being created or remains materially incomplete.

### REVIEW

The scenario is ready for substantive review or is under review.

Passing through `REVIEW` is not mandatory for every card. `DRAFT → COMPLETE` is permitted when a separate review stage adds no value.

### COMPLETE

The scenario is described with sufficient completeness for current project work.

`COMPLETE` describes document maturity, not a decision to support the scenario.

`COMPLETE` is not equivalent to `ACCEPTED`.

### WITHDRAWN

Work on the card ended before completion, for example because it was created in error, was an early duplicate, lost relevance before completion, or was found irrelevant before reaching `COMPLETE`.

`WITHDRAWN` does not mean that another scenario replaced it.

### SUPERSEDED

Another `USE` card replaced the scenario.

The old document is retained and states `Superseded by: USE-xxxx`. The new `USE` states `Supersedes: USE-xxxx`.

## 9. USE disposition

Document maturity and the project's position toward a scenario are separate characteristics. Therefore, `USE` has a separate `Disposition` field.

### CANDIDATE

The scenario is under consideration as a possible IMXO use case, but no target-status decision has been made.

### TARGET

The scenario is recognized as a target for IMXO development.

`TARGET` does not mean that every feature mentioned in the scenario automatically becomes a requirement or enters v0.1.

### NON-TARGET

The scenario is documented but deliberately not treated as an IMXO target under the current project model.

`NON-TARGET` is also useful for documenting format boundaries and anti-use-cases.

### DEFERRED

The target-status decision is postponed. The reason is stated briefly in the card.

## 10. Changing a completed USE

Editorial changes that do not alter scenario meaning may preserve the status:

```text
COMPLETE → COMPLETE
```

A substantive change to the same scenario returns the card to review:

```text
COMPLETE → REVIEW → COMPLETE
```

If the primary actor or system, goal, context, problem, boundaries, or meaning of the expected outcome changes materially so that the card becomes a different scenario, the old `USE` becomes `SUPERSEDED` and the new scenario receives a new ID.

History is not rewritten retroactively.

## 11. Informative nature of USE

All `USE` cards are **Informative**.

Use-case success conditions describe a desired scenario outcome but are not conformance requirements.

For example:

```text
A user can obtain programmatically available text from a saved image.
```

may be a scenario success condition.

It does not by itself create a normative requirement such as `A conforming reader MUST ...`.

Normative requirements appear only in the corresponding `REQ` and `SPEC` artifacts.

## 12. Minimum USE content

A `USE` card must contain enough information to understand the scenario without hidden assumptions.

Primary fields:

- ID and title;
- Status;
- Disposition;
- Created / Updated;
- Actors / systems;
- Context;
- Problem / need;
- Goal;
- Trigger, when applicable;
- Scenario;
- In scope;
- Out of scope;
- Inputs, when applicable;
- Expected outcome;
- Success conditions;
- Current workflow and known limitations;
- Assumptions / hypotheses;
- Relevance to IMXO;
- Cross-cutting considerations;
- Open questions;
- Related artifacts;
- History.

Sections need not contain text when objectively inapplicable. Empty formal sections must not be created merely to satisfy the template.

## 13. Solution neutrality

A `USE` should describe the problem and expected outcome without predetermining a technical implementation wherever possible.

Poor:

```text
IMXO must have a TEXT chunk with a UTF-8 payload.
```

Better:

```text
Text visually present in a screenshot needs a programmatically available representation associated with the corresponding visual region.
```

A specific container, field layout, encoding, chunk type, API, or other mechanism appears only in artifacts where it is actually researched or designed.

## 14. Assumptions and unverified claims

A `USE` may contain working hypotheses.

It should distinguish among:

- an observed fact;
- a claim supported by an external source;
- a project assumption;
- a hypothesis;
- expected value.

A `USE` must not present an assumption about the market, regulatory interpretation, user pain, or adoption as an established fact without corresponding research.

## 15. Cross-cutting considerations

Instead of requiring empty `Security / Privacy / Accessibility` sections, cards use one `Cross-cutting considerations` section.

When relevant, it may cover:

- Accessibility;
- Security;
- Privacy;
- Trust;
- IPR;
- Interoperability;
- Preservation / archival concerns;
- other cross-cutting factors.

An irrelevant factor does not require an empty subsection.

## 16. Completion criteria

A `USE` may move to `COMPLETE` when:

- the context is clear;
- the primary actors or systems are identified;
- the problem or need is defined;
- the scenario goal is clear;
- its primary boundaries are defined;
- the expected outcome is described;
- assumptions and hypotheses are not presented as facts;
- material open questions are listed;
- no hidden architectural decision is embedded in the scenario;
- existing related artifacts are identified, when any exist;
- `Disposition` is set.

## 17. USE language process

New material `USE` cards are developed in Russian first.

An English version is optional before `COMPLETE`.

An English version may be created earlier when needed for external review, collaboration, discussion with an English-speaking contributor, or engagement with an external organization.

When a Russian card moves to `COMPLETE`, an English mirror becomes mandatory.

If both versions exist, their meaning, ID, Status, Disposition, and links must remain synchronized.

Technical identifiers are not translated.

## 18. USE storage and navigation

Russian cards are stored under:

```text
docs/ru/use-cases/
```

Russian index:

```text
docs/ru/use-cases/README.md
```

The index contains a compact `ID | Name | Status | Disposition` table and links to cards. It does not duplicate card content.

The English `docs/en/use-cases/` directory is created when the first English `USE` card appears.

No empty English directory is created in advance.

## 19. README navigation

The `USE` class must be visible from the primary documentation navigation.

After PREP-08, these files are updated:

```text
README.md
README.ru.md
docs/ru/README.md
docs/en/README.md
```

Russian documents link to `docs/ru/use-cases/README.md`.

English navigation explains that use cases are Russian-first working artifacts and that English mirrors are created under the PREP-08 rules.

Until `docs/en/use-cases/README.md` exists, no broken link to a nonexistent English index is created. Navigation is updated after the English index appears.

When an existing `USE` is mentioned in a `Q`, `RSCH`, `REQ`, `DES`, `ADR`, or other Markdown document, its identifier should be a clickable link where that does not harm readability.

## 20. Traceability

`USE` is added to the IMXO Traceability Register.

Preferred logical register form:

```text
Requirement | Use cases | Questions | Research | Design | Decision | Specification
```

Relationships are many-to-many.

The `Use cases` column is not mandatory for every `REQ`.

A requirement may arise from security research, interoperability constraints, an external standard, a parser-safety requirement, or another technical basis without a particular user `USE`.

Likewise, a `USE` may exist before related `REQ` items appear.

`USE` cards use neutral links:

```text
Related questions
Related research
Related requirements
Related design
Related decisions
```

`Derived requirements` is not used as a mandatory formulation because causality may be complex and many-to-many.

## 21. Research plan

No separate `PLAN-*` class is introduced.

The research plan is a living project-management document:

```text
docs/ru/project/research-plan.md
```

It manages:

- research order;
- priorities;
- dependencies;
- scope;
- relationships between planned topics and `USE` or `Q`;
- research queue state.

The research plan is not evidence, a research result, `RSCH`, `REQ`, `DES`, `ADR`, a normative source, or a technical basis for a decision.

`Based on: research-plan.md` must not be used as the technical basis for a requirement or architectural decision.

## 22. Creating the research plan

PREP-08 defines the role of `research-plan.md` but does not create a populated initial research plan.

The initial plan is prepared after the first substantive `USE` cards exist and with consideration of existing `Q` items.

```text
PREP-08
  ↓
initial USE set
  ↓
initial research-plan.md
  ↓
RSCH-0001...
```

This builds the research order from real scenarios and open questions rather than inventing a sequence in advance without context.

## 23. RSCH identifiers in the research plan

The research plan does not reserve `RSCH` numbers.

Until an actual research document is created, a topic remains a plan entry without an `RSCH-xxxx` identifier.

An identifier is assigned only when the actual `RSCH` is created.

This prevents fictitious research, reserved but never created documents, and meaningless identifier gaps caused by queue changes.

## 24. Changing the research plan

`research-plan.md` is one living document. Git history records its changes.

Files such as `research-plan-v2.md`, `research-plan-final.md`, and `research-plan-final2.md` are not created.

Reprioritizing, adding dependencies, or changing the queue does not require a separate GitHub Issue when separate public discussion adds no value.

If a new research topic reflects a new material unknown, an appropriate `Q` may be created when needed.

## 25. PREP-05 amendments

PREP-08 requires PREP-05 to be updated by headings and meaning rather than relying only on former section numbers.

Required changes:

1. add `USE` to the project artifact classes;
2. define the purpose of `USE`;
3. add `USE-0001...` identifiers;
4. add the `USE` lifecycle;
5. add `Disposition`;
6. update the traceability model;
7. update the typical process diagram while preserving nonlinearity;
8. define Issue as a public entry channel rather than a mandatory predecessor to every artifact;
9. define the role of `research-plan.md`;
10. update the Traceability Register template;
11. reference the `USE` template and use-case index.

PREP-05 remains `DONE`. The history of the initial decision is preserved.

## 26. Initial PREP baseline

After PREP-08, the phrase `PREP cycle complete` is imprecise.

Current README and context documents use this meaning:

> Initial PREP baseline (PREP-00 through PREP-07) was completed. PREP-08 was added as a targeted process amendment before systematic research began.

In Russian:

> Первоначальная подготовительная база PREP-00…PREP-07 была завершена. PREP-08 добавлен как целевая процессная поправка до начала систематических исследований.

This does not reopen PREP-00 through PREP-07 or change their status.

## 27. What PREP-08 deliberately does not do

PREP-08 does not:

- create `USE-0001`;
- create a populated initial research plan;
- begin `RSCH`;
- create a `REQ`;
- select a container architecture;
- define the logical object model;
- define the physical file structure;
- accept an accessibility profile;
- accept a conformance profile;
- turn an adoption hypothesis into a requirement;
- introduce a separate `PLAN-*` class;
- require a GitHub Issue before every internal artifact.

## 28. PREP-08 result

Following PREP-08:

- `USE` is an official project artifact class;
- its purpose is separated from `Q`, `RSCH`, and `REQ`;
- its IDs, Status, and Disposition are defined;
- change and supersession rules are defined;
- `USE` is included in traceability;
- its language workflow and navigation are defined;
- the role of `research-plan.md` is defined;
- `PLAN-*` is not introduced;
- Issues are used where they provide real value;
- PREP-05 is updated but remains `DONE`;
- the project is ready for its first `USE` cards, followed by the initial research plan and `RSCH`.

The next process step after publication of PREP-08 is to create the first real use-case cards beginning with `USE-0001`.
