# IMXO Governance

## 1. Purpose

This document describes the current governance model of the official **IMXO — Image Model eXchange Object** project.

IMXO is currently a research and early-design project. At this stage, it uses a simple maintainer-led model with open participation, a clearly accountable Project Lead, and public traceability for substantial technical decisions.

The governance model may evolve as IMXO matures. Any material governance change must be explicit, documented, and published.

## 2. The official IMXO project

The official, or canonical, IMXO project is maintained through the official IMXO resources, including its canonical repositories, official specification, official website, and official brand materials.

Open licenses applicable to IMXO materials allow third parties to use, distribute, and, where the applicable license permits, modify those materials.

A derivative work, fork, experimental profile, or independent implementation does not automatically become the official IMXO project.

Use of the IMXO name, logo, Kumixo, and other official brand assets is governed separately by `BRAND_POLICY.md`.

## 3. Current governance model

IMXO is currently led by its Founder and Project Lead.

**Founder and Project Lead: Fyodor Malkov**

The Project Lead is responsible for the overall technical direction of the official IMXO project and has final decision authority under the current governance model.

This includes final authority over:

- the official scope and goals of IMXO;
- acceptance of material architectural decisions;
- acceptance of ADRs;
- the content and official status of the IMXO specification;
- official releases;
- canonical repositories;
- appointment and removal of maintainers;
- delegation of project authority;
- governance changes;
- official statements made on behalf of the project;
- future stewardship of the official IMXO project.

This model is intended to preserve coherent technical direction and accountable decision-making during the early development of the project.

## 4. Open participation

IMXO welcomes constructive participation.

Useful contributions include, but are not limited to:

- technical criticism;
- alternative architectural proposals;
- research;
- primary sources and standards analysis;
- requirements and use cases;
- implementation experience;
- interoperability findings;
- accessibility analysis;
- security and privacy analysis;
- documentation;
- corrections;
- code;
- tests;
- tools;
- ideas for project development;
- proposals for collaboration.

A contributor does not need to agree with the current design direction in order to participate.

Reasoned disagreement, independent verification, and proposals to revise accepted decisions are legitimate parts of the IMXO development process.

Proposals are evaluated on their merits, including relevant evidence, technical consequences, compatibility, interoperability, accessibility, security, privacy, project scope, implementation cost, and long-term consequences.

Submission of a proposal does not guarantee acceptance.

## 5. Contributors

Anyone may become a contributor by making a constructive contribution to the project.

Contributors may:

- open Issues;
- participate in technical discussion;
- propose research;
- propose requirements;
- prepare design alternatives;
- propose ADRs;
- submit Pull Requests;
- improve documentation;
- contribute code, tests, or other materials within the project scope;
- participate in review.

Making a contribution does not automatically grant decision-making authority on behalf of the official IMXO project.

No number of commits, Pull Requests, Issues, comments, or length of participation automatically creates governance rights.

## 6. Maintainers

A maintainer is a participant to whom the Project Lead has explicitly delegated authority over part of the official project.

Maintainer status is granted by invitation of the Project Lead.

Factors that may be considered include:

- sustained substantive contributions;
- technical understanding of IMXO;
- sound engineering judgment;
- quality of review;
- ability to work constructively with alternative viewpoints;
- reliability;
- understanding of the project goals and constraints;
- history of interaction with the project and other contributors.

There is no automatic threshold of commits, Pull Requests, Issues, or time after which a contributor becomes a maintainer.

Maintainer authority may be scoped to particular areas of the project.

Appointment as a maintainer is a delegation of authority. It does not by itself transfer:

- the Project Lead role;
- overall project stewardship;
- control of the IMXO brand;
- copyright ownership;
- unilateral authority to change project governance.

The Project Lead may change or withdraw delegated maintainer authority.

## 7. Technical decisions

Material technical decisions should remain publicly traceable.

The project decision process is defined by PREP-05 and the corresponding public project documents.

Depending on the subject, a decision may involve:

```text
Issue
  ↓
Q
  ↓
RSCH
  ↓
REQ
  ↓
DES
  ↓
ADR
  ↓
SPEC
```

Not every question must pass through every artifact class.

An Issue, Pull Request, discussion, or private conversation is not by itself an architectural decision.

Where an ADR is required by the project process, the official architectural decision is recorded in the ADR.

## 8. Disagreement and reconsideration

Accepted decisions may be reconsidered when material new information becomes available, including:

- new technical evidence;
- new authoritative sources;
- new standards;
- implementation experience;
- interoperability problems;
- accessibility findings;
- security findings;
- privacy findings;
- material IPR concerns;
- other circumstances that affect the basis of the original decision.

Disagreement with the Project Lead or a maintainer is not a process violation.

Technical criticism should be evaluated on its merits.

When a material decision is superseded, project history is preserved rather than rewritten as if the previous decision never existed.

## 9. Canonical repositories and official materials

The Project Lead determines which repositories, specifications, and other resources are official IMXO resources.

Moving or renaming a canonical repository does not by itself alter:

- authorship of previously contributed material;
- the license under which that material was contributed;
- the history of project decisions;
- rights already granted under applicable open licenses.

A GitHub repository URL is an infrastructure location. It does not by itself determine the legal status of an accepted contribution.

## 10. Contributions and future stewardship

A contribution is made to the **IMXO project** under the license applicable to that category of project material, not merely to a particular repository URL or GitHub organization name.

If the canonical repository or stewardship of IMXO is later moved, renamed, or transferred, previously accepted contributions remain available under the terms under which they were accepted.

In particular:

- existing licenses continue to apply;
- contributors retain copyright in their original contributions unless explicitly agreed otherwise;
- a governance change does not retroactively change the license of an accepted contribution;
- new contribution requirements apply prospectively unless a contributor explicitly agrees otherwise or another applicable legal basis requires otherwise.

A future governance model does not automatically bind earlier contributors to new contractual, licensing, patent, or disclosure obligations.

## 11. Evolution of governance

The current governance model reflects the present stage of IMXO.

It may evolve as the project grows.

Future changes may include additional maintainers, delegated responsibility for project areas, additional review processes, or other governance structures if they become useful.

This document intentionally does not define the final organizational form of a mature IMXO project.

The governance model should be reviewed when the scale or external role of the project changes materially.

Events that may justify such a review include:

- appointment of the first additional long-term maintainer with substantial delegated responsibility;
- adoption or implementation of IMXO by an independent external organization or significant third-party implementer;
- sustained participation by multiple independent contributors or organizations;
- formal engagement with a standards organization, foundation, consortium, or similar external body;
- ecosystem adoption at a level where broader representation or additional review mechanisms would materially improve trust, interoperability, or project continuity.

These events do not automatically change governance, transfer authority, create voting rights, or alter the Project Lead role. Any governance change requires an explicit, documented, and published decision.

Any material governance change must:

1. be explicit;
2. be published;
3. preserve project history;
4. respect existing licenses and contributor rights;
5. avoid retroactively imposing new obligations on previously accepted contributions.

No period of inactivity, contributor count, or appointment of additional maintainers automatically transfers the Project Lead role or overall stewardship.

## 12. Contribution licensing

Licensing for different classes of IMXO material is defined in `LICENSES.md`.

By intentionally submitting material for inclusion in the official IMXO project, a contributor agrees that an accepted contribution may be distributed under the license applicable to that category of material.

Contributors retain copyright in their original contributions unless an explicit separate agreement states otherwise.

By submitting a contribution, the contributor represents that they have the right to provide it to the project under the applicable terms.

IMXO does not require a general copyright assignment for ordinary contributions.

Official brand assets are handled separately and are not automatically covered by the ordinary contribution process.

## 13. Intellectual property rights

Patent and similar intellectual-property matters that may affect implementation of IMXO technical mechanisms are addressed separately in `IPR_POLICY.md`.

Participation in the project must not be interpreted as an automatic grant of patent rights beyond the applicable licenses and any explicit commitments.

## 14. Participant conduct

IMXO welcomes strong technical disagreement and critical review.

Participation should remain constructive.

Personal attacks, threats, harassment, spam, deliberate disruption of technical discussion, impersonation of official project representatives, and unauthorized disclosure of another person's secrets, personal data, or confidential information are not acceptable.

Criticism of ideas, decisions, documents, code, and project actions is welcome when directed at the subject under discussion rather than at a participant personally.

## 15. Contact and collaboration

The preferred public channels for feedback and collaboration are:

- GitHub Issues;
- Pull Requests;
- other official public project channels as they become available.

For collaboration proposals, preliminary discussion, or direct contact, the public contact details listed in the Project Lead's GitHub profile may also be used.

Current public contact points include:

- Email: [fmalkov91@gmail.com](mailto:fmalkov91@gmail.com)
- LinkedIn: [linkedin.com/in/fmalkov](https://www.linkedin.com/in/fmalkov/)
- Facebook: [fyodor.malkov](https://www.facebook.com/fyodor.malkov/)
- Reddit: [u/kroxut](https://www.reddit.com/user/kroxut/)
- Telegram: [@FyodorMalkov](http://t.me/FyodorMalkov)

These channels may be used for feedback, proposals, research material, technical criticism, ideas, and collaboration inquiries.

Potential vulnerabilities and other sensitive security matters must follow `SECURITY.md`.

## 16. Source of truth

The current version of this file in the canonical IMXO repository is the official description of the current project governance model.

Git history preserves the history of governance changes.

Material changes to this policy should follow the normal project change process.
