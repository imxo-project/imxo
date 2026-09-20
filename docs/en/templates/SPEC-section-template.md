# SPEC Section Template

> This template helps apply PREP-06. It does not create normative IMXO requirements by itself.

## Section title

**Status:** Normative

Briefly state the purpose of the section.

## Normative rules

Write requirements with an explicit subject:

```text
A reader MUST ...
A writer MUST NOT ...
A conforming object MAY ...
```

Use only:

```text
MUST
MUST NOT
SHOULD
SHOULD NOT
MAY
```

## Fixed Binary Layout

If the section describes a fixed physical structure:

```text
Offset base: ...
Units: bytes
Byte order: ...
```

| Offset | Size | Type | Field | Description |
|---:|---:|---|---|---|
| | | | | |

Add a `Condition` column when necessary.

## Logical / Variable Structure

| Field | Type | Cardinality | Condition | Description |
|---|---|---|---|---|
| | | | | |

Use cardinality `1`, `0..1`, `0..N`, `1..N`, or specific limits.

## Bit / Flag Layout

| Bits | Name | Description |
|---:|---|---|
| | | |

Define writer and reader behavior for reserved bits separately.

## Semantics and constraints

For each relevant field, define:

- meaning;
- range;
- unit;
- special values;
- presence conditions;
- invalid/unsupported behavior;
- interaction with unknown extensions.

## Informative Note

> **Note (Informative):** ...

Do not introduce a new normative requirement here.

## Example

> **Example (Informative):** ...

The example must conform to the normative text but does not replace it.

## Security Considerations

Add locally only if the mechanism has specific risks.

## Privacy Considerations

Add locally only if the mechanism creates a specific risk of information disclosure.

## References

### Normative

- ...

### Informative

- ...
