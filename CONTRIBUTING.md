# Contributing to IMXO

Thank you for your interest in IMXO.

IMXO is currently in the research and early design stage. Contributions should help clarify the problem space, evaluate existing standards, refine requirements, or improve the project infrastructure without presenting unresolved architecture as settled.

## What you can contribute

Useful contributions include:

- corrections and clarifications to project documentation;
- research on image formats, metadata systems, and container architectures;
- comparisons involving JUMBF / JLINK, ISO BMFF / HEIF, RIFF, PNG chunks, TIFF / BigTIFF, ZIP-like models, and other relevant standards;
- requirements, use cases, and interoperability constraints;
- terminology proposals;
- threat models, parser-safety analysis, trust models, and prompt-injection-like scenarios;
- accessibility considerations;
- English and Russian translation corrections;
- proposals for examples, test data, schemas, conformance material, or future implementations;
- feedback based on practical implementation or archival experience.

Proposals for executable behavior, automatic network access, embedded scripts, or other active features are outside the accepted passive v0.1 baseline. They may be discussed only when clearly identified as out of scope for v0.1.

## Before starting

1. Read [`README.md`](README.md) and the relevant public project documents.
2. Check whether the subject is an accepted baseline concept, an open question, or an existing decision.
3. For substantial research, structural changes, or design proposals, open a GitHub Issue before preparing a large pull request.
4. Keep unresolved proposals marked as `OPEN`, hypotheses, research questions, or design proposals.
5. Do not assume that IMXO requires a new custom container or that any existing container has already been selected.

Early coordination is especially important for large documents, new directory trees, binary fixtures, schemas, and implementation work.

## Submitting an issue

Use [GitHub Issues](../../issues) for focused feedback, research proposals, and defect reports.

Include, where applicable:

1. the affected document, file, or topic;
2. the relevant section, identifier, or passage;
3. the type of feedback: error, ambiguity, contradiction, proposal, source, security concern, or implementation experience;
4. an explanation of the impact on IMXO;
5. a verifiable source or minimal example;
6. suggested wording or an outline of the proposed change.

Do not use public issues to report an unpatched vulnerability in code that may later become security-sensitive. Contact the maintainer privately first.

## Pull requests

Keep pull requests focused and reviewable.

- Explain what changed and why.
- Link the relevant Issue, research document, requirement, or decision when one exists.
- Separate research, requirements, design discussion, ADRs, and normative specification text.
- Preserve accepted decisions and their rationale.
- Do not silently resolve contradictions or close open questions.
- Keep equivalent English and Russian documents synchronized.
- Preserve technical identifiers across languages.
- Avoid unrelated formatting or repository-wide restructuring.
- Do not add large binary files unless they are approved brand assets, test fixtures, or release artifacts.
- Describe how the change was checked.

An accepted architectural decision should be recorded in an ADR before being treated as part of the normative design.

## Research and sources

Research contributions should:

- prefer primary or authoritative sources;
- identify the standard version, edition, and publication date;
- cite exact sections wherever possible;
- distinguish normative facts from summaries and interpretations;
- mark inferences explicitly;
- keep quotations brief and exact;
- describe advantages, disadvantages, and consequences for IMXO separately;
- list remaining open questions.

Do not attribute behavior to an external standard unless the cited source supports it.

## Languages and translations

The project maintains English and Russian documentation in mirrored structures.

For corresponding documents:

- preserve meaning, structure, identifiers, and references;
- use matching filenames wherever possible;
- do not translate technical identifiers or field names;
- update both language versions as part of the same contribution when practical.

Before beginning a substantial translation into another language, open an Issue to identify the source document, source language, and revision and to avoid parallel work.

## Security, privacy, and trust

Security contributions should consider that structured data may not match visible pixels and is not automatically trustworthy.

Do not submit secrets, personal data, proprietary source code, embargoed vulnerability details, or other confidential material in Issues, pull requests, comments, examples, or test files.

Test data must be original, appropriately licensed, or otherwise safe to redistribute. Passwords and secret values must not be exposed through structured example layers.

## Licensing and brand assets

Review [`LICENSES.md`](LICENSES.md) before contributing. Code and machine-readable implementation material use the Apache License 2.0 provided in [`LICENSE`](LICENSE). Documentation uses CC BY 4.0 provided in [`LICENSE-CC-BY-4.0.txt`](LICENSE-CC-BY-4.0.txt). Official brand assets are governed separately by [`BRAND_POLICY.md`](BRAND_POLICY.md).

The complete licensing model is still being implemented. If the applicable license is unclear, discuss it before submitting the contribution.

Do not submit third-party material unless you have the right to contribute it under the applicable project terms. IMXO logos, Kumixo artwork, and other brand assets require explicit review and must not be assumed to fall under the documentation license.

## How decisions are made

Feedback and proposals are evaluated against the accepted baseline, available evidence, compatibility implications, security risks, and project scope. Not every proposal will be accepted.

Research documents compare alternatives. ADRs record accepted architectural decisions. The specification describes the resulting normative requirements.

## Contact

For preliminary discussion or matters that should not initially be public:

- Telegram: [@FyodorMalkov](https://t.me/FyodorMalkov)
- Email: [iksut@ya.ru](mailto:iksut@ya.ru)
