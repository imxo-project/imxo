# PREP-06. IMXO Specification Writing Rules

**Status:** DONE  
**Recorded date:** 2026-09-20  
**Document type:** normative specification preparation rules  
**Purpose:** establish consistent language, structure, and technical presentation rules for the future IMXO specification.

> PREP-06 defines **how to write the IMXO specification**, but does not define a specific format architecture. Container selection, endianness, encodings, object types, MIME type, magic bytes, and other architectural decisions are handled through `RSCH / REQ / DES / ADR`.

## 1. Scope

PREP-06 applies to future `SPEC` documents and related material that directly describes normative IMXO behavior.

PREP-06 defines:

- normative and informative content;
- normative language;
- rules for writing testable requirements;
- terminology and identifier rules;
- methods for describing binary and logical structures;
- rules for describing numbers, units, strings, time, and bit fields;
- rules for describing errors and unknown data;
- presentation of examples, notes, and rationale;
- normative and informative references;
- requirements for Security and Privacy Considerations;
- language-version rules;
- traceability among requirements, decisions, and the specification;
- minimum requirements for the specification version and change history.

PREP-06 does not define:

- a specific IMXO container;
- a specific byte order;
- a specific set of primitive types;
- a specific string encoding;
- a specific time format;
- a specific reserved-bits model;
- the standard's release lifecycle;
- the final conformance model.

## 2. Normative and Informative content

In `SPEC` documents, content is **Normative** by default unless a section or block is explicitly marked **Informative**.

The following elements are informative by default:

- `Example`;
- `Note`;
- `Rationale`;
- `Implementation Note`.

They must not be the sole place where a normative requirement is introduced.

Diagrams and figures are informative unless explicitly defined otherwise. Even when a figure explains a normative structure, mandatory behavior must be expressed in normative text or a normative table and must not depend solely on visual interpretation of the figure.

Normative and informative content must not contradict each other. If an informative example conflicts with normative text, the normative text is the source of truth.

## 3. Normative language: RFC 2119 + RFC 8174

IMXO uses the BCP 14 requirements model based on:

- RFC 2119 — *Key words for use in RFCs to Indicate Requirement Levels*;
- RFC 8174 — *Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words*.

Normative references:

- https://www.rfc-editor.org/rfc/rfc2119
- https://www.rfc-editor.org/rfc/rfc8174

IMXO normative text uses this restricted set of key words:

```text
MUST
MUST NOT
SHOULD
SHOULD NOT
MAY
```

Other BCP 14 synonyms, such as `SHALL`, `REQUIRED`, `RECOMMENDED`, and `OPTIONAL`, are not used in IMXO normative text without a specific reason.

Only uppercase forms have the special normative meaning. Ordinary lowercase English words `must`, `should`, and `may` are not treated as BCP 14 key words.

### 3.1. Use of SHOULD

`SHOULD` and `SHOULD NOT` are used only when deviation can genuinely be acceptable.

If a deviation breaks compatibility, correctness, integrity, or mandatory safe behavior, `MUST` or `MUST NOT` is used.

If the consequences of deviation are material, the specification should explain them near the relevant requirement or in linked explanatory content.

`SHOULD` is not used as a softer or more polite form of `MUST`.

### 3.2. BCP 14 in Informative content

Informative blocks must not use BCP 14 words in their normative sense.

If an example, note, or rationale needs to refer to mandatory behavior, it should refer to the normative text.

## 4. Testability of normative requirements

A normative requirement must be worded so that, where possible, it can be determined whether a file or implementation conforms to it.

Avoid vague wording such as:

```text
should be robust
should be fast
normally
usually
where appropriate
if necessary
```

when the satisfaction criterion is not defined.

Poor:

> A parser SHOULD be robust.

Better:

> A reader MUST reject an object whose declared size exceeds the bounds of its containing object.

This example demonstrates style only and does not introduce an IMXO architectural rule.

## 5. Subject of a normative requirement

Every behavioral normative statement must unambiguously identify **who or what is required to perform the behavior**.

Depending on future terminology, the subject may be:

- a file;
- an object;
- a writer;
- a reader;
- an encoder;
- a decoder;
- a validator;
- another explicitly defined component.

PREP-06 does not establish the final set of these terms.

Normative text must distinguish among:

- data properties;
- producer/writer requirements;
- consumer/reader requirements;
- validator requirements.

## 6. Relationship between REQ and SPEC normative statements

`REQ-xxxx` is a high-level project requirement.

One `REQ` may produce multiple normative statements in `SPEC`.

The following rule does not apply:

> one `MUST` = one `REQ`.

`REQ` identifiers must not proliferate merely to cover every individual sentence containing a BCP 14 word.

## 7. Terminology and identifiers

One normative concept should have one primary name.

Do not use `block`, `chunk`, `record`, and `object` interchangeably for the same entity unless a distinction among them is defined.

A term must be defined before its first normative use if its meaning is:

- specific to IMXO;
- different from common usage;
- critical to compatibility.

Technical identifiers are not translated between language versions:

```text
object_id
content_hash
REQ-0012
ADR-0007
```

If the specification uses the terms `canonical`, `normalized`, or `equivalent`, their exact semantics must be defined before their first normative use. These terms are not used as casual synonyms.

## 8. Representation of numbers and units

Numeric notation must be unambiguous.

Recommended forms:

```text
42          decimal
0x2A        hexadecimal
0b101010    binary, when binary notation is genuinely useful
```

A number without a prefix is decimal unless the section establishes another explicit rule.

The unit is stated explicitly for physical sizes and offsets.

If the term `byte` is used, the specification must explicitly define it as an eight-bit unit before normative use.

Unambiguously defined units such as `KiB` and `MiB` may be used for data sizes when genuinely needed.

Forms such as `KB`, `Kb`, and `kB` must not be mixed without defining their semantics.

## 9. Primitive types

PREP-06 does not establish the final set of IMXO primitive types.

If the specification uses types such as:

```text
uint8
uint16
uint32
uint64
bytes[N]
UUID
```

each type must be centrally defined before normative use.

For a numeric field, the following must be defined where necessary:

- allowed range;
- unit;
- meaning of zero;
- special values;
- constraints;
- behavior for out-of-range values.

The notation `length: uint64` is insufficient by itself if the semantics of `length` are unclear.

## 10. Byte order

PREP-06 does not select an IMXO byte order.

For every multi-byte field, byte order must:

- be defined directly; or
- be inherited from an explicitly stated general rule.

Normative text must not rely on `native endian`, `platform endian`, or `host endian` unless that property is a deliberately defined part of the format.

## 11. Fixed Binary Layout

Structures with a fixed physical layout use this standard form:

| Offset | Size | Type | Field | Description |
|---:|---:|---|---|---|

An additional `Condition` column may be added when necessary.

Applicable parameters must be defined before the table:

```text
Offset base: ...
Units: bytes
Byte order: ...
```

`Byte order` is stated only when applicable.

Rules:

- `Offset` is always measured from an explicitly stated base;
- `Size` has an explicitly stated unit;
- variable size is represented as `variable` or by a normative formula;
- padding and alignment are not implied automatically;
- reserved fields must be shown in the layout;
- the table describes structure but does not replace the normative description of field semantics.

## 12. Logical / Variable Structure

Logical, nested, and variable structures use this form:

| Field | Type | Cardinality | Condition | Description |
|---|---|---|---|---|

Standard cardinality forms:

```text
1
0..1
0..N
1..N
```

Specific limits such as `0..255` or `1..16` may be used when necessary.

If a field is conditional, `Condition` must be precise enough for an implementation to determine when the field:

- must be present;
- must not be present;
- may be present.

Vague conditions such as `if needed` are not used without a definition.

## 13. Bit / Flag Layout

Flags and bit fields use a separate form:

| Bits | Name | Description |
|---:|---|---|

Ranges are written unambiguously, for example:

```text
0
1
2..7
```

PREP-06 does not define a general policy for reserved bits.

For each reserved field or range, the specification must explicitly define applicable writer and reader behavior.

The specific policy is determined by the relevant `REQ / DES / ADR / SPEC`.

## 14. Strings and text fields

A field must not be described merely as a `string` when additional rules are required for compatibility.

If the specification introduces a string or text field, the following must be defined where necessary:

- encoding;
- method for expressing length;
- termination;
- normalization rules;
- allowed and disallowed sequences;
- handling of invalid sequences.

PREP-06 does not select a specific encoding or normalization model.

## 15. Dates and time

If the specification introduces a date or time value, it must explicitly define the applicable parameters:

- encoding;
- epoch or another basis;
- timezone / UTC semantics;
- precision;
- allowed range;
- special values, if any.

PREP-06 does not select a specific timestamp format.

## 16. Platform and implementation independence

Normative text must not depend on unspecified properties of:

- a CPU;
- an operating system;
- a programming language;
- an ABI;
- a runtime;
- a file system;
- a specific library.

Avoid undefined constructs such as `integer`, `native endian`, `standard string`, `usual timestamp`, and `platform encoding` unless their exact semantics are defined.

## 17. Validity, errors, unknown, and unsupported data

The specification must distinguish data states from implementation support.

At minimum, the following must not be treated as synonyms:

```text
unknown != invalid
unsupported != invalid
```

If the following terms are used:

- `valid`;
- `invalid`;
- `malformed`;
- `unknown`;
- `unsupported`;
- `corrupted`;

their exact definitions must be established before their first normative use.

Data validity and required reader behavior are separate statements.

For example, a statement that an object is invalid under condition X does not by itself mean that a reader is required to stop processing the entire file. Required implementation behavior is defined separately.

## 18. Unknown, reserved, and extension-defined data

The terms `reserved`, `unknown`, `unsupported`, and `extension-defined` are not used interchangeably.

PREP-06 does not define a specific extension model.

The future specification must explicitly describe producer and consumer behavior for each category when the distinction affects compatibility.

## 19. Examples, Notes, Rationale, and Implementation Notes

### Example

Demonstrates the application of normative rules. Does not introduce a new requirement.

### Note

Provides additional explanation. Does not introduce a new requirement.

### Rationale

Explains why a rule exists. The full history of an architectural decision is retained in an ADR rather than duplicated in `SPEC`.

### Implementation Note

May provide practical implementation guidance but does not define mandatory behavior.

If following the guidance is mandatory for conformance, the rule must appear in normative text.

## 20. Figures and diagrams

A diagram should help readers understand the specification but must not be the sole source of normative behavior.

If an informative diagram conflicts with normative text, the normative text is the source of truth.

If a normative diagram is ever used, its normative status and exact semantics must be stated explicitly.

## 21. Pseudocode and algorithms

Pseudocode and illustrative algorithms are **Informative** by default.

If the standard requires a specific result, the following are defined normatively:

- input data;
- required result;
- constraints;
- errors;
- observable behavior.

An implementation may use another equivalent algorithm unless the specification explicitly requires a particular algorithm as part of the format.

If the algorithm itself is a normative IMXO element, that status must be stated explicitly.

## 22. References

References are divided into:

### Normative References

Documents whose requirements must be followed to implement the corresponding normative IMXO requirement.

### Informative References

Material used for understanding, research, comparison, or historical context.

If behavior depends on a specific revision of an external standard, the specific version, edition, or date must be stated.

A standard-family name without a version is insufficient when different editions may produce different behavior.

## 23. Internal references

Explicit references to a section or stable identifier are preferred over expressions such as `as described above` and `as mentioned earlier`.

Traceability must not depend solely on the displayed section number if that number may change during editing.

The stable-anchor system will be defined when an actual `SPEC` structure exists.

## 24. Security Considerations

The future IMXO specification must contain an overall `Security Considerations` section.

It must address normatively relevant risks associated with, among other things:

- parsing;
- corrupted structures;
- resource exhaustion;
- discrepancies between visual and structured layers;
- provenance;
- integrity/trust;
- extensions;
- external or linked data, if allowed by the future architecture.

Local security notes are added only where they improve understanding of a specific mechanism.

PREP-06 does not replace a separate threat model.

## 25. Privacy Considerations

The future IMXO specification must contain a separate `Privacy Considerations` section.

It must address potential information disclosure through:

- metadata;
- EXIF-like data;
- geographic coordinates;
- text layers;
- semantic annotations;
- faces and other CV annotations;
- provenance;
- accessibility descriptions;
- hidden or invisible structured data.

Security and privacy are not treated as interchangeable concepts.

## 26. Language versions

At the current stage, new substantive documents are first developed and approved in Russian and then translated into English.

For the future stable normative specification:

- the English version is expected to be normative;
- the Russian version is maintained as an official synchronized version.

Technical identifiers, field names, requirement numbers, ADR identifiers, and other stable identifiers are not translated.

A translation must not independently change normative meaning.

If a discrepancy is found between language versions, it is treated as a documentation synchronization error and corrected separately.

## 27. IMXO Traceability Register

Traceability is maintained separately from readable normative text.

The concept of an **IMXO Traceability Register** is introduced.

It is an informative project engineering artifact, not a normative part of `SPEC`.

Typical relationship:

```text
Q / RSCH
   ↓
  REQ
   ↓
  DES
   ↓
  ADR
   ↓
  SPEC
```

This may later be extended as follows:

```text
SPEC
 ↓
Conformance rule
 ↓
Test vector / validator test
```

### 27.1. Bidirectionality

Traceability must make it possible to:

- navigate from a question or requirement to the accepted decision and normative text;
- navigate from a normative element back to the requirement, ADR, and originating question or research.

### 27.2. A complete linear chain is not required

Not every artifact is required to have every intermediate class.

Many-to-many relationships are permitted:

- one RSCH → multiple REQ;
- multiple RSCH → one REQ;
- multiple REQ → one DES;
- multiple DES → one ADR;
- one ADR → multiple SPEC elements.

### 27.3. SPEC is not cluttered with administrative traceability

Normative text does not require `Derived from: REQ-...` or `Decision: ADR-...` beside every paragraph.

The Traceability Register is maintained separately. If published alongside the specification, it is Informative.

### 27.4. Stable references

Traceability should refer to stable identifiers or anchors where possible, rather than only to displayed section numbers.

The specific anchor system will be defined after the `SPEC` structure exists.

## 28. Version and change history

PREP-06 does not define the standard's complete release lifecycle.

Every published specification instance must explicitly state:

- a version identifier;
- document status;
- publication or record date.

Changes between published versions must be documented.

Specific statuses such as `Working Draft`, `Candidate`, and `Published`, as well as the changelog format, will be defined before the first actual `SPEC` publication cycle.

## 29. Deprecated, obsolete, reserved, and removed

PREP-06 does not define a complete feature-deprecation lifecycle.

The terms `deprecated`, `obsolete`, `reserved`, and `removed` are not treated as synonyms.

The exact semantics of each term must be defined before its first normative use.

## 30. PREP-06 result

Following acceptance of PREP-06, IMXO has established:

- separation of Normative and Informative content;
- BCP 14 as the basis for normative language;
- the restricted `MUST / MUST NOT / SHOULD / SHOULD NOT / MAY` set;
- rules for testable requirements;
- an explicit subject for normative behavior;
- separation between `REQ` and individual SPEC normative statements;
- consistent terminology rules;
- consistent numeric and structural notation rules;
- three standard table forms: Fixed Binary Layout, Logical / Variable Structure, and Bit / Flag Layout;
- rules for strings, time, and platform independence;
- separation of validity, error, and support states;
- rules for Examples, Notes, Rationale, Figures, and pseudocode;
- Normative and Informative References;
- Security and Privacy Considerations;
- the RU/EN language model;
- a separate bidirectional Traceability Register;
- minimum requirements for version and change history.

Further changes to PREP-06 follow the ordinary project change process and do not return the preparation stage to an incomplete state.
