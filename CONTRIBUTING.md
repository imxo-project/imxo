# Contributing to IMXO

Thank you for your interest in IMXO.

IMXO is currently in the research and early design stage. Contributions should help clarify the problem space, evaluate existing standards, refine requirements, improve the project infrastructure, or provide useful implementation and interoperability experience without presenting unresolved architecture as settled.

## What you can contribute

Useful contributions include:

- corrections and clarifications to project documentation;
- research on image formats, metadata systems, and container architectures;
- comparisons involving JUMBF / JLINK, ISO BMFF / HEIF, RIFF, PNG chunks, TIFF / BigTIFF, ZIP-like models, and other relevant standards;
- requirements, use cases, and interoperability constraints;
- terminology proposals;
- threat models, parser-safety analysis, trust models, and prompt-injection-like scenarios;
- accessibility research and analysis;
- English and Russian translation corrections;
- proposals for examples, test data, schemas, conformance material, or future implementations;
- feedback based on practical implementation or archival experience;
- alternative architectural proposals and criticism of current project assumptions;
- proposals for collaboration.

Proposals for executable behavior, automatic network access, embedded scripts, or other active features are outside the accepted passive v0.1 baseline. They may be discussed only when clearly identified as out of scope for v0.1.

## Before starting

1. Read `README.md` and the relevant public project documents.
2. Check whether the subject is an accepted baseline concept, an open question, or an existing decision.
3. For substantial research, structural changes, or design proposals, open a GitHub Issue before preparing a large Pull Request.
4. Keep unresolved proposals marked as `OPEN`, hypotheses, research questions, or design proposals.
5. Do not assume that IMXO requires a new custom container or that any existing container has already been selected.

Early coordination is especially important for large documents, new directory trees, binary fixtures, schemas, and implementation work.

## Submitting an Issue

Use GitHub Issues for focused feedback, research proposals, design concerns, collaboration proposals, and defect reports.

Include, where applicable:

1. the affected document, file, or topic;
2. the relevant section, identifier, or passage;
3. the type of feedback: error, ambiguity, contradiction, proposal, source, security concern, accessibility concern, IPR concern, or implementation experience;
4. an explanation of the impact on IMXO;
5. a verifiable source or minimal example;
6. suggested wording or an outline of the proposed change.

Do not use public Issues to report an unpatched vulnerability or confidential legal/IPR information that should not be public. Use the appropriate private contact path first.

## Pull Requests

Keep Pull Requests focused and reviewable.

- Explain what changed and why.
- Link the relevant Issue, research document, requirement, or decision when one exists.
- Separate research, requirements, design discussion, ADRs, and normative specification text.
- Preserve accepted decisions and their rationale.
- Do not silently resolve contradictions or close open questions.
- Where both Russian and English versions already exist, keep them synchronized when practical.
- New substantive documents follow the project's current language workflow.
- Preserve technical identifiers across languages.
- Avoid unrelated formatting or repository-wide restructuring.
- Do not add large binary files unless they are approved brand assets, test fixtures, or release artifacts.
- Describe how the change was checked.

An accepted architectural decision should be recorded in an ADR before being treated as part of the normative design where the project process requires an ADR.

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

## Accessibility

Accessibility is a first-class evaluation criterion for IMXO.

Research and design proposals may consider standards, regulations, and implementation practices such as WCAG, EN 301 549, the European Accessibility Act, Section 508, ADA-related requirements, and other relevant accessibility frameworks.

Do not claim that a regulation requires IMXO or that IMXO automatically provides legal compliance.

Accessibility contributions should distinguish:

- requirements imposed on content, products, services, software, or procurement;
- capabilities that can be represented in an IMXO file;
- behavior required from viewers, SDKs, applications, or assistive-technology integration;
- normative requirements from adoption or policy arguments.

## Languages and translations

The project maintains English and Russian documentation.

Where corresponding public documents already exist in both languages:

- preserve meaning, structure, identifiers, and references;
- use matching filenames where practical;
- do not translate technical identifiers or field names;
- keep both language versions synchronized when practical.

New substantive research and design documents are currently developed in Russian first and translated after the Russian structure and content have been approved.

Before beginning a substantial translation into another language, open an Issue to identify the source document, source language, and revision and to avoid parallel work.

## Security, privacy, and trust

Security contributions should consider that structured data may not match visible pixels and is not automatically trustworthy.

Do not submit secrets, personal data, proprietary source code, embargoed vulnerability details, or other confidential material in Issues, Pull Requests, comments, examples, or test files.

Test data must be original, appropriately licensed, or otherwise safe to redistribute. Passwords and secret values must not be exposed through structured example layers.

## Licensing of contributions

The licensing model is defined in `LICENSES.md`.

By intentionally submitting material for inclusion in the official IMXO project, you agree that an accepted contribution may be distributed under the license applicable to that category of project material.

You retain copyright in your original contribution unless an explicit separate agreement states otherwise.

By submitting a contribution, you represent that you have the right to provide it to the project under the applicable terms.

IMXO does not require a general copyright assignment, CLA, or DCO for ordinary contributions at this stage.

Official brand assets are governed separately by `BRAND_POLICY.md`.

Patent and similar implementation-related intellectual-property matters are addressed in [`IPR_POLICY.md`](IPR_POLICY.md).

## Governance

IMXO welcomes technical disagreement and alternative proposals.

Participation does not automatically grant decision-making authority over the official project.

The current governance model, Project Lead role, maintainer model, and decision authority are described in [`GOVERNANCE.md`](GOVERNANCE.md).

Substantial technical decisions remain publicly traceable through the project's Q / RSCH / REQ / DES / ADR / SPEC process.

## Contact and collaboration

The preferred public channels are GitHub Issues and Pull Requests.

For collaboration proposals, preliminary discussion, or direct contact, the public contact details listed in the Project Lead's GitHub profile may also be used.

Current public contact points include:

- Email: [fmalkov91@gmail.com](mailto:fmalkov91@gmail.com)
- LinkedIn: [linkedin.com/in/fmalkov](https://www.linkedin.com/in/fmalkov/)
- Facebook: [fyodor.malkov](https://www.facebook.com/fyodor.malkov/)
- Reddit: [u/kroxut](https://www.reddit.com/user/kroxut/)
- Telegram: [@FyodorMalkov](http://t.me/FyodorMalkov)

Potential vulnerabilities and other sensitive security matters must follow [`SECURITY.md`](SECURITY.md).

## Participant conduct

Strong technical criticism and disagreement are welcome.

Personal attacks, threats, harassment, spam, deliberate disruption, impersonation of official project representatives, and unauthorized disclosure of another person's secrets, personal data, or confidential information are not acceptable.

Critique ideas, decisions, documents, code, and project actions rather than attacking participants personally.
