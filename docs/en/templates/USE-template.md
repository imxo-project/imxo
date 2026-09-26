# USE-xxxx — <short scenario title>

**Status:** DRAFT  
**Disposition:** CANDIDATE  
**Created:** YYYY-MM-DD  
**Updated:** YYYY-MM-DD

> `USE` is an informative description of an application scenario. This card is not a normative requirement, an architectural decision, or evidence that a feature is necessary.

For material characteristics, use explicit values such as `unknown`, `to be researched`, `estimated`, `range`, `not applicable`, or unambiguous equivalents when precise information is unavailable.

## Actors / systems

Identify the people or systems participating in the scenario.

Example categories: person, operating system, application, camera, screenshot tool, AI agent, CV system, editor, archive, assistive technology, web service.

## Context

Describe the context in which the task arises.

Include only the context needed to understand the scenario.

## Problem / need

Describe the problem or need represented by the scenario.

Do not prescribe a technical solution when none has been accepted.

## Goal

Describe the outcome the actor or system is trying to achieve.

## Trigger

Describe what starts the scenario.

Delete this section if a separate trigger is unnecessary.

## Scenario

Provide a concise sequence of events or interactions.

Do not turn this section into a description of IMXO internal architecture.

## In scope

State what belongs to this scenario.

## Out of scope

State what this card deliberately does not cover.

This is especially important when related but independent tasks exist nearby.

## Inputs

List input data or preconditions when material.

Delete this section if it is inapplicable.

## Operational profile

- Frequency / event rate:
- Typical volume:
- Peak / burst characteristics:
- Interactive or batch:
- Producers / consumers:
- Is manual review realistic:
- Sensitivity to processing/storage overhead:

Do not conflate global market or adoption scale with the operational characteristics of this scenario.

## Longevity and verification expectations

- Expected useful lifetime:
- Expected retention period:
- Required provenance / integrity verification horizon:
- Offline or self-contained verification needed:
- Dependence on external services acceptable:

Record scenario expectations without selecting a cryptographic, PKI, or archival architecture.

## Expected outcome

Describe the result expected from the scenario perspective.

## Success conditions

List observable conditions under which the scenario can be considered successful.

Success conditions are not conformance requirements and do not by themselves create `MUST / SHOULD / MAY` statements.

## Failure and representation-divergence impact

- What if structured data is wrong or stale?
- What if structured and visible representations disagree?
- Who or what consumes the incorrect representation?
- Can this trigger automated action?
- Would a human notice the mismatch?
- Are the consequences reversible?
- What material harm may result?
- Which representations or layers may diverge?

This section does not assume that an adversary exists.

## Adversarial / misuse incentives

- Who could benefit from false or inconsistent data?
- What could they gain?
- What would be beneficial to falsify?
- Which representation/layer would be attractive to manipulate?
- Who or what could be misled?
- What downstream effect could result?

Do not assign subjective threat or risk levels without a separate accepted model.

## Structured-data exposure and data minimization

- What sensitive data may become machine-readable?
- Is it already visible in the rendered image?
- Could structured data expose information not visible to the user?
- Can sensitive data be excluded at capture time?
- Can source/application semantics help exclude it?
- Can the data be safely removed after capture?
- What happens during redaction/sanitization?
- Which related representations must be updated together?
- What are the indexing/search risks?
- What are the AI/agent ingestion risks?
- Does machine readability, searchability, indexing, copying, AI/agent ingestion, or bulk extraction amplify exposure?

Explicitly check for divergence such as:

```text
visible representation:
Password: ••••••••

structured representation:
Password: real-secret-value
```

Do not select a specific protection mechanism in this card.

## Current workflow and known limitations

Describe how the task is handled now and which confirmed limitations are known.

Do not present assumptions about users, markets, regulation, or adoption as established facts.

## Assumptions / hypotheses

List working assumptions that still require verification.

Where possible, state what a future `RSCH` needs to verify.

## Relevance to IMXO

Explain why this scenario may be relevant to IMXO.

This section justifies researching the scenario; it is not evidence that a feature is necessary.

## Cross-cutting considerations

Add only relevant subsections.

Possible areas:

- Accessibility
- Security
- Privacy
- Trust
- IPR
- Interoperability
- Preservation / archival concerns

Do not create empty subsections merely to satisfy the template.

This section does not replace the core operational-profile, longevity and verification, failure/divergence, adversarial-incentive, or structured-data-exposure characteristics.

## Open questions

List related unknowns and questions.

Link existing `Q` cards where available.

## Related artifacts

### Related questions

- none

### Related research

- none

### Related requirements

- none

### Related design

- none

### Related decisions

- none

## Supersession

Delete this section if the card neither supersedes nor is superseded by another card.

**Supersedes:** none  
**Superseded by:** none

## History

- YYYY-MM-DD — card created.
