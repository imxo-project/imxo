# PREP-07. Licensing, Project Governance, and IPR

**Status:** DONE  
**Recorded date:** 2026-09-20  
**Document type:** project preparation decision  
**Purpose:** establish the minimum licensing, official IMXO project governance, and IPR-handling model for the research stage.

> PREP-07 does not attempt to design the future organizational form of a mature IMXO project in advance. It establishes only the model needed now: open participation, clear accountability for the official project, transparent recording of decisions, and careful handling of IPR.

## 1. Context

IMXO is in the research and early-design stage.

At this stage, the project needs a model that simultaneously:

- allows any interested person to propose ideas, research, criticism, code, and collaboration;
- preserves a coherent technical direction for the official IMXO project;
- does not create fictitious committees, voting procedures, or organizational structures before a real need exists;
- does not obstruct future governance development;
- preserves the terms under which contributors provide material;
- does not create false assurances concerning patents or other IPR.

## 2. Licensing

The project has already adopted a mixed licensing model:

- code, reference implementations, SDKs, tools, validation logic, and corresponding machine-readable implementation materials — Apache License 2.0;
- specification text, research, requirements, design documents, ADR text, and general documentation — CC BY 4.0;
- official IMXO and Kumixo brand material — separate `BRAND_POLICY.md`;
- third-party material retains its own applicable terms.

The current licensing map is maintained in `LICENSES.md`.

PREP-07 does not change this model.

If a new class of material appears in the future and the current licensing map does not cover it adequately, its terms must be defined before public distribution.

## 3. Inbound contributions

At this stage, the project does not introduce:

- a CLA;
- a DCO;
- mandatory copyright assignment;
- automatic transfer of copyright to the project.

A contributor retains copyright in their own original contribution unless an explicit separate agreement states otherwise.

By intentionally submitting material for inclusion in the official IMXO project, a contributor agrees that an accepted contribution may be distributed under the license applicable to that class of material under `LICENSES.md`.

The contributor must have the right to provide the material under those terms.

A contribution is treated as a contribution to the IMXO project, not merely to a particular repository URL.

Moving, renaming, or changing the canonical repository does not retroactively change the license of a previously accepted contribution.

## 4. Current governance model

The official IMXO project uses this model:

**Founder / Project Lead → Maintainers → Contributors**

**Founder and Project Lead: Fyodor Malkov**

At the current stage, the Project Lead has final responsibility for the official technical direction of IMXO.

Anyone may propose:

- technical criticism;
- alternative architectural solutions;
- research;
- requirements;
- documentation;
- code;
- tests;
- security and privacy analysis;
- accessibility analysis;
- interoperability findings;
- collaboration proposals;
- other constructive changes.

A participant does not need to agree with the project's current direction for their proposal to be considered.

However, making a contribution does not automatically grant the right to make decisions on behalf of the official IMXO project.

## 5. Project Lead authority

At the current stage, the Project Lead has final authority over:

- the official project scope;
- material architectural decisions;
- acceptance of `ACCEPTED` ADRs;
- the official status and content of the specification;
- official releases;
- canonical repositories;
- appointment and removal of maintainers;
- delegation of authority;
- governance changes;
- official statements made on behalf of the project;
- future stewardship of the official IMXO project.

This centralization applies to the official IMXO project and does not remove the right of third parties to use openly licensed material within the applicable licenses.

A derivative work, fork, or experimental profile does not automatically become official IMXO.

## 6. Maintainers

Maintainer status is granted only by explicit invitation from the Project Lead.

Factors that may be considered include:

- sustained substantive contributions;
- technical understanding of IMXO;
- quality of engineering decisions;
- quality of review;
- ability to work constructively with alternative positions;
- reliability;
- understanding of project goals and constraints;
- history of interaction with the project and its participants.

There is no automatic number of commits, Pull Requests, Issues, or period of participation after which a contributor receives maintainer status.

Appointment as a maintainer is a delegation of authority and does not by itself transfer:

- the Project Lead role;
- overall stewardship;
- the IMXO brand;
- copyright;
- the right to change governance unilaterally.

## 7. Open technical discussion

Reasoned disagreement with the Project Lead or a maintainer is permitted and welcomed.

Material decisions must remain publicly traceable under the PREP-05 process.

Private correspondence, an Issue, a Pull Request, or a discussion does not by itself replace a required project artifact.

Accepted decisions may be reconsidered when the following become available:

- new data;
- new authoritative sources;
- new standards;
- implementation experience;
- interoperability problems;
- accessibility findings;
- security/privacy findings;
- IPR concerns;
- other material circumstances.

The history of previous decisions is not rewritten retroactively.

## 8. Future governance development

PREP-07 does not predetermine the future organizational form of a mature IMXO project.

Governance may evolve with the project.

The governance model should be reviewed when the scale or external role of the project changes materially.

Events that may justify such a review include:

- appointment of the first additional long-term maintainer with substantial delegated responsibility;
- adoption or implementation of IMXO by an independent external organization or significant third-party implementer;
- sustained participation by multiple independent contributors or organizations;
- formal engagement with a standards organization, foundation, consortium, or similar external body;
- ecosystem adoption at a level where broader representation or additional review mechanisms would materially improve trust, interoperability, or project continuity.

These events do not automatically change governance, transfer authority, create voting rights, or alter the Project Lead role. Any governance change requires an explicit, documented, and published decision.

Any material change must:

- be explicit;
- be documented;
- be published;
- preserve project history;
- respect licenses and rights already granted by contributors;
- not impose new legal obligations retroactively on earlier contributors without their explicit agreement or another applicable legal basis.

New contribution or IPR requirements apply prospectively by default.

Moving or renaming the canonical repository does not change the terms of previously accepted contributions.

## 9. IPR

The official IPR policy is published at the root of the canonical repository as `IPR_POLICY.md`.

It is separate from `LICENSES.md`, `BRAND_POLICY.md`, copyright licensing, and trademark or brand rules.

The primary purpose of the IPR policy is to identify known patent-like restrictions before they silently become mandatory IMXO dependencies.

IMXO seeks to avoid including technologies known to require a royalty-bearing patent license in the mandatory core when an acceptable open or royalty-free alternative exists.

This is a design goal, not a guarantee that no patents exist.

## 10. Minimum IPR model

At the current stage:

- a contributor is not required to perform a patent search;
- actual knowledge of potentially material IPR should be disclosed as early as possible;
- disclosure is not an admission of validity, infringement, or enforceability;
- the project does not itself determine patent validity;
- `IPR_POLICY.md` is not itself a patent license;
- CC BY 4.0 is not treated as a patent license;
- the Apache-2.0 patent grant applies only within the scope of the Apache License 2.0 itself;
- a potential IPR concern becomes input to the ordinary IMXO technical process;
- no empty IPR registry is created in advance.

If a material IPR concern cannot be disclosed publicly, it may first be reported privately to the Project Lead.

A known but undisclosable concern must not silently accompany advancement of the affected technology into the mandatory core.

## 11. Accessibility as a technical decision criterion

Accessibility is an independent criterion for evaluating proposals alongside:

- technical correctness;
- interoperability;
- security;
- privacy;
- compatibility;
- long-term sustainability.

PREP-07 does not claim that any law or standard requires the use of IMXO.

The following require separate research:

- European Accessibility Act;
- WCAG;
- EN 301 549;
- Section 508;
- ADA practice and regulatory requirements;
- other relevant accessibility standards and regulatory frameworks.

The research goal is to determine:

- which requirements actually apply to images, images of text, and structured visual content;
- which IMXO capabilities may help satisfy those requirements;
- which capabilities belong to the file itself and which require viewer, SDK, or application behavior;
- whether accessibility can become an independent adoption driver for the format;
- which public claims are supportable and which would be unfounded.

This subject remains `OPEN` and is handled through separate Q/RSCH artifacts.

## 12. Public policy files

After PREP-07, the official public policy files are:

- `/GOVERNANCE.md`;
- `/IPR_POLICY.md`;
- `/CONTRIBUTING.md`;
- `/SECURITY.md`;
- `/BRAND_POLICY.md`;
- `/LICENSES.md`.

`GOVERNANCE.md` and `IPR_POLICY.md` are published only in English and are the sole official versions of their respective policies.

The Russian PREP-07 document records the history and rationale for the adopted model but does not create a parallel policy.

## 13. Deliberately not introduced now

PREP-07 does not introduce:

- a CLA;
- a DCO;
- a steering committee;
- elections;
- voting or quorum rules;
- a membership model;
- an appeals board;
- a patent pool;
- a project-specific universal RF patent grant;
- automatic maintainer promotion;
- inactivity-based transfer of leadership;
- the Contributor Covenant;
- `AUTHORS.md`;
- a predefined foundation or other future organizational model.

Such mechanisms may be considered later if project growth creates a real need.

## 14. Contacting the author and project

The preferred channels for feedback, proposals, research, and collaboration are public:

- GitHub Issues;
- Pull Requests;
- other official public project channels.

Direct contact through details published in the Project Lead's GitHub profile is also permitted:

- Email: `fmalkov91@gmail.com`
- LinkedIn: https://www.linkedin.com/in/fmalkov/
- Facebook: https://www.facebook.com/fyodor.malkov/
- Reddit: https://www.reddit.com/user/kroxut/
- Telegram: http://t.me/FyodorMalkov

Security-sensitive messages must follow `SECURITY.md`.

## 15. PREP-07 result

Following acceptance of PREP-07:

- the current mixed licensing model is confirmed;
- inbound contribution principles are defined;
- the maintainer-led model of the official IMXO project is established;
- the Project Lead retains final authority during the research stage;
- participation and technical criticism remain open;
- maintainer rights do not arise automatically;
- future governance is not designed in advance;
- the terms of previously accepted contributions are protected from retroactive change;
- a separate English `IPR_POLICY.md` is introduced;
- accessibility is formally included as a decision criterion and a separate research direction;
- the initial PREP-00 through PREP-07 preparation baseline is considered complete.

The next project stage is approval and launch of a systematic research plan.
