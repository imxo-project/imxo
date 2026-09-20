# IMXO IPR Policy

## 1. Purpose

This policy describes how the IMXO project handles patents and similar intellectual-property rights that may materially restrict implementation of IMXO technical mechanisms.

The goals are to identify known IPR risks early, consider them during technical design, and reduce the risk that mandatory IMXO functionality unknowingly depends on royalty-bearing patent licenses.

This policy is a project process policy. It is not legal advice, a determination of patent validity or infringement, or a patent license.

## 2. Scope

For purposes of this policy, **IPR** primarily refers to implementation-restricting rights such as:

- patents;
- published patent applications;
- unpublished patent applications, to the extent their existence may lawfully be disclosed;
- utility models;
- similar exclusive rights that may directly affect implementation of IMXO.

Copyright licensing for project materials is governed by `LICENSES.md` and the applicable license texts.

Use of the IMXO name, logo, Kumixo, and other official brand assets is governed by `BRAND_POLICY.md`.

This policy does not replace those documents.

## 3. Project goal

IMXO seeks to remain practically implementable without knowingly requiring royalty-bearing patent licenses for mandatory conformance with the core standard.

The project prefers technologies:

- for which no material IPR restriction is known;
- that are available under suitable royalty-free terms;
- that are in the public domain in the relevant respect;
- or that can be replaced by a technically acceptable open or royalty-free alternative.

This is a design goal, not a guarantee that IMXO is free from all present or future patent rights in every jurisdiction.

Absence of an IPR disclosure is not proof that no relevant IPR exists.

## 4. Mandatory and optional technologies

IPR risk is especially important when a technology is required for mandatory IMXO conformance.

The project should avoid knowingly placing a technology in the mandatory core when implementation is known to require a royalty-bearing patent license and a suitable open or royalty-free alternative exists.

IPR associated with an optional technology, external codec, optional profile, or integration does not automatically prevent that technology from being referenced or used in the broader IMXO ecosystem.

The mandatory or optional role of the technology is part of the IPR assessment.

## 5. Disclosure of known IPR

A contributor or other participant in a technical proposal should disclose potentially relevant IPR as early as reasonably possible when they have actual knowledge that such rights may materially affect a proposed mandatory IMXO feature.

This includes relevant rights actually known to be controlled by:

- the contributor;
- an organization on whose behalf the contributor is explicitly acting;
- the contributor's employer, when the contributor actually knows of the right and its potential relevance to the proposed technology.

Participants are not required to:

- perform patent searches;
- investigate patent portfolios unknown to them;
- provide legal opinions;
- determine patent validity or enforceability;
- conclude that IMXO actually infringes a patent.

Disclosure exists to inform the technical process, not to constitute an admission of infringement or validity.

## 6. Timing of disclosure

Relevant IPR information should be disclosed as early as reasonably possible.

Preferably, disclosure occurs before the affected technology is accepted as a mandatory part of IMXO.

If potentially relevant IPR becomes known only after a contribution or technical decision, it should be raised without unreasonable delay after discovery.

A later IPR discovery may be grounds to reconsider an earlier IMXO decision through the normal project process.

## 7. Disclosure content

A disclosure should provide the information that is actually known and may lawfully be shared.

Depending on the circumstances, this may include:

- a patent number;
- a published patent-application number;
- the rights holder;
- a link to a public record;
- the affected proposal, Issue, DES, ADR, or specification section;
- a short explanation of the possible relevance;
- known public licensing terms;
- a link to a published royalty-free commitment, if one exists.

A contributor is not required to provide a legal conclusion that particular claims actually cover IMXO.

Information that the contributor is not permitted to publish need not be publicly disclosed.

## 8. Public and private reporting

When the information is public and may lawfully be shared, an IPR concern should normally be raised through a GitHub Issue or another official public project channel.

If the matter involves non-public, confidential, or legally sensitive information, including an unpublished patent application, the participant should contact the Project Lead privately using public contact information listed in the canonical repository or the Project Lead's GitHub profile.

The project does not require contributors to violate lawful confidentiality obligations.

However, a technology subject to a known material IPR concern should not become mandatory merely because sufficient information cannot be publicly disclosed.

## 9. Inability to disclose

If a contributor has actual knowledge of potentially material IPR but is not permitted to disclose enough information for meaningful assessment, the contributor should not knowingly continue promoting the affected technology toward acceptance as a mandatory IMXO mechanism without first raising the situation privately with the Project Lead.

This applies only to the affected technology and does not prevent participation in other areas of the project.

## 10. Meaning of a disclosure

IMXO does not determine:

- patent validity;
- enforceability of patent claims;
- infringement;
- final legal applicability in a particular jurisdiction.

The existence of a disclosure does not mean that:

- the patent is valid;
- the patent necessarily covers IMXO;
- an IMXO implementation infringes it;
- a license is necessarily required.

A disclosure is input to technical and, when appropriate, legal evaluation.

## 11. Possible project actions

After a material IPR concern is identified, the project may:

- request additional public information;
- investigate technical alternatives;
- redesign the affected mechanism;
- replace the technology;
- use a royalty-free alternative;
- make the feature optional;
- defer a decision;
- decline the proposal;
- continue after further evaluation of known licensing terms.

The resulting decision follows the normal IMXO process and should consider technical, interoperability, accessibility, security, privacy, and IPR consequences.

When the issue materially affects architecture, the resulting decision should remain publicly traceable through the appropriate project artifacts.

## 12. Mandatory royalty-bearing technology

A technology known to require a royalty-bearing patent license in order to implement mandatory IMXO conformance should normally not be adopted as part of the mandatory core.

An exception requires explicit evaluation of:

- technical necessity;
- available alternatives;
- known licensing terms;
- consequences for independent implementations;
- consequences for open-source implementations;
- interoperability consequences;
- long-term ecosystem risk.

Any such exception requires an explicit and documented decision by the Project Lead.

## 13. External standards and technologies

An IMXO reference to an external standard does not imply that the external technology is free of patent or other IPR restrictions.

When an external technology is mandatory for IMXO conformance, known IPR conditions should be considered as part of the architectural decision.

Optional codecs, representations, profiles, and integrations may have their own licensing and IPR conditions.

## 14. CC BY 4.0

Specification text, research, and other documentation classes are licensed as described in `LICENSES.md`, including use of CC BY 4.0 for applicable materials.

CC BY 4.0 does not itself grant patent or trademark rights.

The right to read, distribute, adapt, or otherwise use specification text under CC BY 4.0 must not be interpreted as a patent license covering every technology described by that text.

## 15. Apache License 2.0

For IMXO materials distributed under the Apache License 2.0, the patent provisions of that license apply according to their own terms.

Apache License 2.0 includes a patent grant within the scope defined by the license for applicable Contributions and the Work.

That grant must not be interpreted more broadly than the Apache License 2.0 itself and is not an automatic universal patent license for all mechanisms described in a separate IMXO specification.

## 16. Licensing statements

If a patent holder or authorized representative publishes licensing terms, IMXO may consider those terms during technical decision-making.

The project should not treat an informal or ambiguous statement as equivalent to a legally sufficient patent license.

This `IPR_POLICY.md`:

- does not itself grant a patent license;
- does not itself create a royalty-free patent commitment;
- does not replace a separate commitment from a rights holder;
- does not expand patent grants contained in other applicable licenses.

## 17. IPR information and the specification

Specific IPR disclosures should normally be maintained separately from the normative specification text.

The specification should define technical requirements rather than serve as a registry of patent assertions.

The project may create a public IPR register or similar mechanism if real disclosures make one useful.

No empty IPR register is required before the first real disclosure.

## 18. Changes in IPR ownership

An IPR disclosure should be interpreted with awareness that ownership or control of the relevant right may later change.

The project must not claim that a disclosure automatically binds a future rights holder unless that effect follows from an applicable legal instrument or law.

Any separate licensing commitment is governed by its own terms.

## 19. Future policy changes

IMXO may adopt a more formal IPR or patent policy as the project matures.

A future policy may introduce additional requirements for future participation or future contributions.

Such changes do not automatically impose new patent licensing commitments, contractual obligations, disclosure duties, or similar legal obligations on earlier contributors unless they explicitly agree or another applicable legal basis provides otherwise.

Previously granted copyright and software licenses continue under their original terms.

## 20. No warranty of patent freedom

IMXO does not guarantee:

- absence of patents applicable to IMXO;
- absence of future patent applications;
- absence of unknown IPR;
- freedom to implement IMXO in every jurisdiction;
- sufficiency of any disclosure for a particular implementer.

Implementers remain responsible for their own legal assessment where one is necessary.

## 21. Informative references

The following sources informed the initial project approach:

- IETF RFC 8179 — Intellectual Property Rights in IETF Technology: https://www.rfc-editor.org/rfc/rfc8179
- W3C Patent Policy: https://www.w3.org/policies/patent-policy/
- Apache License 2.0: https://www.apache.org/licenses/LICENSE-2.0
- Creative Commons Attribution 4.0 International legal code: https://creativecommons.org/licenses/by/4.0/legalcode

These references do not make IMXO subject to the governance or patent processes of those organizations.

## 22. Source of truth

The current English version of this file in the canonical IMXO repository is the official IMXO IPR policy.

Working translations or planning drafts do not create parallel official IPR policies.

Material changes to this policy must be explicit, published, and preserved in project history.
