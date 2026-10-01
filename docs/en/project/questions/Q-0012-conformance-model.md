# Q-0012. Conformance Model

**Status:** OPEN  
**Area:** Conformance  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the normative IMXO conformance model be?

## Context

Conformance levels, mandatory implementation capabilities, and validation rules have not yet been defined.

## Scope

- conformance levels;
- mandatory decoder and encoder capabilities;
- behavior for unknown extensions;
- test suites;
- reference files;
- validation rules;
- testable sanitization guarantees and cascade-change tests;
- behavior with unknown extensions and explicit reporting when the result cannot be guaranteed;
- fixtures containing residual structures, conflicting representations, and partially supported data;
- negative tests confirming that removed content does not remain in known dependent representations.

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
- 2026-10-01 — scope expanded with testable sanitization properties from USE-0002; status remains `OPEN`.
