# Q-0011. SDKs and Integrations

**Status:** OPEN  
**Area:** Implementation  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

What should the future IMXO SDK, API, and integration model be after the core architecture stabilizes?

## Context

PREP-00 makes no final decisions about SDKs and integrations. These questions will be considered later, once the core models are sufficiently stable.

## Scope

- SDKs and APIs;
- Windows, Linux, macOS, and Android;
- browsers;
- Photoshop, GIMP, and Krita;
- system image viewers;
- viewer/editor integration;
- capture tools;
- high-level safe modification and removal operations without prematurely assigning specific APIs;
- handling related changes and removals and verifying the final state;
- enabling correct implementation without requiring every application to traverse internal container structures manually;
- behavior with partially supported extensions and production of a state suitable for export.

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
- 2026-10-01 — scope expanded with library operations for safe modification from USE-0002; status remains `OPEN`.
