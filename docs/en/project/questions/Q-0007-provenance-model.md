# Q-0007. Provenance Model

**Status:** OPEN  
**Area:** Provenance  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the normative IMXO provenance model be?

## Context

IMXO must support describing data origin and identifying who or what produced a specific part of the structured data. The exact model will be designed separately.

## Scope

- provenance structure and granularity;
- source identification;
- transformation chains;
- trusted and untrusted sources;
- provenance inheritance rules;
- interaction with hashes and signatures;
- representing provenance of a removal or transformation without retaining the removed value;
- risk of disclosing removed content through provenance, derived identifiers, or hashes;
- recording that a transformation occurred without creating hidden history of the former content.

## Related research

Not assigned yet.

## Related requirements

None yet.

## Related design documents

- [USE-0002 — Safe Sanitization of a Structured Image](../../use-cases/USE-0002-safe-sanitization.md)

## Resolution

Not resolved.

## History

- 2026-09-19 — question transferred from PREP-00 into a separate card.
- 2026-10-01 — scope expanded with the interaction between provenance and sanitization from USE-0002; status remains `OPEN`.
