# Q-0002. Physical File Structure

**Status:** OPEN  
**Area:** Container  
**Source:** PREP-00  
**Created:** 2026-09-19

## Question

How should the physical structure of an IMXO file be designed?

## Context

PREP-00 deliberately leaves the binary structure undefined until container alternatives have been researched and requirements refined.

## Scope

- file signature, endianness, and global header;
- sizes and structure of block or chunk headers;
- `type`, sizes, `uint64`, `object_id`, and flags;
- header and content CRCs and cryptographic hashes;
- nesting, footer, primary index, and backup index;
- recovery sync marker, padding, and alignment;
- handling of damaged data;
- preservation of unknown blocks;
- removal of data from obsolete blocks, residual structures, indexes, free areas, and padding when the selected physical model contains such elements;
- safe production of the final file and behavior when an operation is interrupted;
- conflict between preserving unknown blocks and guaranteeing removal of related data;
- conditions under which a local update is sufficient or another method of producing a sanitized result is required, without preselecting mandatory full rebuilding.

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
- 2026-10-01 — scope expanded with physical sanitization implications from USE-0002; status remains `OPEN`.
