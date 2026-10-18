# USE-0003 — Structured Screenshot as Input to an AI System

**Status:** REVIEW  
**Disposition:** CANDIDATE  
**Created:** 2026-10-18  
**Updated:** 2026-10-18

> A `USE` is an informative description of an IMXO application scenario. This card is not a normative requirement, an architectural decision, research evidence, or a commitment to include a particular feature in the standard.

## 1. Participants and Systems

The primary consumer is an artificial-intelligence system that uses a screenshot to analyze content, prepare a response, make a decision, or support subsequent interaction with an external system.

Participants may include a user, operating system or application, IMXO capture tool, OCR/CV system, editor, reader, AI-input transformation tool, analyzer or agent, and an external system that uses the result. The file creator, source of an individual structured assertion, and final consumer may differ. The provenance of an assertion may be a chain of transformations rather than a single source.

## 2. Context

A raster screenshot preserves a visual representation of an interface but does not necessarily preserve text, structure, and relationships known at capture time. An automated consumer may recover such information through recognition or obtain it directly from the application. The saved file is often used without access to the original source.

IMXO is considered as a potential portable representation of an image together with related structured assertions. The presence of structure does not automatically make it trustworthy, current, or more useful than the raster. A consumer may use visual data, structure, or a combination according to the task and cost.

## 3. Problem and Need

When working only with a raster, an automated consumer may repeatedly extract information that was already known, make recognition errors, lose relationships among elements, and consume additional resources.

Additional structure also introduces problems: increased size, alternative and conflicting assertions, desynchronization during capture and editing, unknown provenance, instruction-injection risks, selective verification, and possible loss of meaning during transformation for a model.

The need is not to provide the maximum amount of metadata, but to enable reasonable use of available structure while accounting for its limitations.

## 4. Goal

Enable an AI system to use structured screenshot content where useful without losing access to the captured visual representation or treating structure as unconditional truth.

The consumer may account for known provenance, currency, consistency, and incompleteness. Machine-readable assertions do not automatically acquire the authority of instructions. Savings in tokens, computation, or recognition are not guaranteed; research must establish any benefit.

## 5. Initiation

The scenario begins when an automated consumer needs to analyze a saved or directly received screenshot: explain an error, locate an element, extract data, describe an interface, check a test, prepare a response, or choose a later action. Executing an action is not required.

## 6. Main Scenario

The AI system receives an IMXO file or a representation prepared from it, directly or through an external program. Visual content and any structured information that is present and can be read correctly are available.

The consumer identifies relevant data types and selects regions and objects without necessarily analyzing all content. If the information is sufficient and acceptable, it may be used; when there is doubt, conflict, or a consequential decision, the consumer may additionally check the visual representation or available external sources.

Provenance, verification, and consistency information are themselves assertions, not absolute proof. If data may have been obtained from different interface states, known divergence or uncertainty is taken into account.

The result is a response, analysis, extracted information, new annotation, or basis for a decision by an external system. Action-execution mechanisms are outside the format.

## 7. Scenario Scope

The scenario covers use of raster and related text; regions, semantic objects, and relationships; provenance and transformations; independent and derived assertions; alternatives and conflicts; known and unknown currency; selective retrieval; partial representations and completeness boundaries; transformation for AI; risks of incorrect decisions; and reuse of results when they are stored.

The scenario concerns a screenshot and a captured user-facing representation. General principles may transfer to other images, but that does not automatically broaden the scope of `USE-0003`.

## 8. Out of Scope

This card does not define AI architecture, training, or reasoning; application-control protocols; click-execution mechanisms; action permissions; particular OCR/CV algorithms; a universal trust score; a rule for resolving every conflict; a mandatory reading API; a request format for a particular model; a mandatory cryptographic system; universal protection against instruction injection; synchronization with a live interface; a streaming temporal model; or inter-frame relationships.

Consequences of incorrect agent decisions are considered when evaluating the scenario, but IMXO does not become a command protocol or video format.

## 9. Inputs and Preconditions

The input is a static IMXO with a raster screenshot representation; structured information may be complete, partial, or absent.

**Direct reading:** the consumer interprets IMXO itself. **Mediated use:** a reading or transformation tool prepares another input, and the AI may not receive the source file.

No assumption is made that the source is trusted, every annotation is accurate, every extension is supported, or the original application is available. When structure is absent, the raster remains useful, but that case does not demonstrate the value of IMXO.

## 10. Operational Profile

**One-time analysis:** an individual screenshot used for a response or explanation; quality, verifiability, and usability matter.

**Batch processing:** many saved screenshots; aggregate cost, throughput, resource limits, and resilience to erroneous or excessively complex data matter.

**Sequential agent operation:** repeated individual screenshots between external actions; latency, observation currency, and consequences of error matter. This does not require video or dynamic behavior inside IMXO.

The number of elements, processing frequency, peak load, file sizes, and acceptable latency are unknown and require validation. Creators and consumers may differ. Manual review is not assumed to be mandatory for every object.

## 11. Useful Lifetime and Verification Expectations

Four properties are distinguished: **integrity of the saved file**, **fidelity of the original capture**, **consistency of visual and structured representations**, and **currency relative to the live application**. One property does not prove another.

A screenshot may be stale for acting on an interface while remaining a faithful historical representation. Useful lifetime and retention depend on the task and owner policy. Provenance or integrity verification may be needed immediately or later; offline analysis without the application is permitted, although some external evidence may be unavailable. This USE does not select cryptographic or archival architecture.

## 12. Expected Result

An automated consumer can use visual and related structured information without treating any representation as the sole unconditional source of truth, while accounting for available provenance, alternatives, limitations, and incompleteness. Uncertainty does not automatically become trust or error. Quality, portability, reuse, and cost reduction remain expectations to be tested.

## 13. Success Conditions

Success is evaluated separately:

- **IMXO representation:** can describe different properties, alternative assertions, relationships, and known limitations without false confidence.
- **Correct reading and transformation:** supported data is provided without undisclosed distortion of meaning, provenance, or completeness.
- **AI consumer:** applies its own rules for verification, trust, and handling untrusted information; IMXO does not guarantee correct behavior by an arbitrary agent.
- **Practical utility:** measurable advantages or acceptable tradeoffs over existing approaches are found for defined tasks.

These are expectations of an informative USE, not normative implementation requirements.

## 14. Consequences of Errors and Representation Divergence

Possible cases include desynchronization **during capture** (raster and structure are taken from different states), desynchronization **after editing**, staleness **relative to a live source**, incorrect initial recognition, distortion **during extraction or transformation**, and incorrect AI interpretation.

Consequences depend on context, ranging from an incorrect description to a decision causing material harm or a dangerous action. A person may not see a structured error that is not visible to them. Consequences are not always reversible. Container correctness does not prove correctness of capture, structure, or an external action.

## 15. Abuse Potential

An attacker may substitute values or annotations, forge verification and provenance information, create many conflicting assertions, overwhelm a consumer with complex structure, inject instructions into visible or primarily machine-readable content, and propagate false conclusions through chains of AI systems.

Instruction injection is also possible through an ordinary raster; additional structure creates a potentially convenient machine channel. Trust markings may themselves be untrustworthy. No universal numeric risk classification is introduced.

## 16. Structured-Data Exposure and Minimization

Compared with pixels alone, structure makes text easier to search, copy, index, extract in bulk, and transmit. Not every consumer should receive every region, relationship, annotation, or provenance record.

Utility for AI does not authorize extraction of hidden internal application state. Permitted user-relevant semantics, such as an accessible button name, may differ from visible text; this does not permit disclosure of the true value of a masked password or hidden token. The boundary follows the permitted-capture policy in `USE-0001`, not a rule that everything absent from pixels is forbidden.

`USE-0002` applies to removal of related information, but processing one file does not remove earlier external copies, logs, requests, or results held by third-party systems.

## 17. Existing Ways to Address the Task

The comparison includes raster only; raster with OCR/CV; direct access to application data and platform automation facilities; combined application data and image; an image with a separate JSON/XML sidecar or other structure; existing formats and containers such as PNG with additional chunks, SVG, PDF, and others; and IMXO.

Direct access may be better for a live interface, while a separate metadata file may be sufficient for some analytical tasks. Storing text in the same file as an image does not prove the need for a new format. The comparison covers coordinated storage, preservation of relationships, independent reading, portability, safe editing, extensibility, and implementation and adoption cost.

## 18. Assumptions and Testable Hypotheses

1. For predefined tasks, structure improves quality or reduces the **total** processing cost relative to raster alone.
2. Selective verification of important and doubtful regions provides a useful cost/error tradeoff compared with complete reanalysis.
3. A portable structured screenshot is useful when the source application is unavailable and when exchanging data among independent programs.
4. Alternative assertions and provenance chains may improve analysis but may also increase noise, cost, and error.
5. Additional structure may increase the cost of reading, selection, transformation, conflict resolution, and verification.
6. Machine-readable semantics create specific abuse opportunities that must be studied at both the model and consumer levels.
7. A single structured object may offer advantages over an image with separate metadata; the nature and magnitude of those advantages are unknown.

Research defines task classes, starting conditions, comparison alternatives, and metrics in advance. A negative result is acceptable. These hypotheses are not requirements.

## 19. Significance for IMXO

`USE-0003` tests whether a static format can represent a screenshot together with additional assertions so that they can be used selectively while preserving differences, provenance, and uncertainty and retaining the raster as a verification reference.

The needs of a particular AI model must not dictate the core architecture. No mandatory AI-specific layer, embedded prompts, commands, or vendor-specific tokenized structures are assumed.

## 20. Cross-Cutting Concerns

**Security:** untrusted files, resource attacks, false assertions, instruction injection. **Privacy:** permitted capture, minimization, sanitization, bulk-extraction risk. **Accessibility:** semantics may legitimately differ from visible text. **Compatibility:** independent programs and analyzers. **Long-term use:** operation without the application and possible loss of external verification information. **Trust:** provenance, authenticity, integrity, currency, and fitness for a task differ. **Extensibility:** unknown annotation types must not silently replace the meaning of known ones.

## 21. Assertions, Properties, and Relationships

Different assertions may describe different properties of one object. For example, visible `OK` text and the accessible name “Confirm changes” may both be correct. Conflict must be assessed with respect to object, property, and state, not by simple inequality of values.

Independent observations may have different geometric boundaries and categories. Coordinate equality is not universal proof of identity; geometric intersection does not prove dependency. A current or preferred representation does not require alternatives to be deleted. The specific object and relationship model remains open.

## 22. Provenance and Trust Boundary

Information about the source, transformation chain, checks, integrity or authenticity, relationship to a state, conflicts, and original recognizer scores may be useful to a consumer. These properties cannot be reduced to one universal trust number.

Entries such as `verified` and `human checked` are themselves assertions and are not necessarily substantiated. A known source does not prove correctness or currency. The consumer determines fitness for use based on the task and possible consequences. Unknown property values are allowed.

## 23. Consistency During Capture and After Modification

The raster, text, and accessibility tree may be obtained at times `T1`, `T2`, and `T3` while the source application changes. A file may preserve complete structural integrity while combining information from different states.

Partial editing may make a previous machine assertion inapplicable to the new composition even when new fragment coordinates can be calculated. Splitting a recognized object does not automatically confirm the same classification for each fragment; currency may remain unknown.

Related structure may also become stale after editing. The format does not guarantee universally atomic capture or prescribe a specific synchronization method, but it does not assume that data obtained at different times or modified independently should be falsely declared consistent. Currency of an external live application is considered separately from consistency of the saved file.

## 24. Partial Data Retrieval and Completeness

A consumer may need only one region, object type, or assertion group. For a subset, completeness of **content**, **relationships**, **provenance**, and **processing of supported types** are distinct.

Completeness does not mean a universal statement that “nothing else exists in the file”; it is a judgment within a known selection scope, understood types, and program capabilities. Unknown extensions may contain unaccounted data. Absence of an object, relationship, or provenance record from a subset does not prove its absence from the source. A completeness claim is itself an assertion; this USE does not fix its model or representation.

## 25. Transforming IMXO into AI Input

An adapter may select, reduce, and transform data, but it may also lose relationships, provenance, alternatives, or unknown currency, or present an unsubstantiated value as verified. Correctness of the source representation, extraction, and transformation must be distinguished.

Not all content must be supplied to the model. Reduction, however, must not silently turn uncertainty into certainty or a partial representation into a complete one. This card does not design a request format for a particular model or an adapter API.

## 26. Resource Limits and Inability to Process

The costs of physical file parsing, structure extraction, model-input preparation, analysis, and conflict checking are considered separately. Selective semantic processing does not guarantee inexpensive container reading.

Corruption, excessive nesting, large volume, and unknown extensions may occur. “Could not read” does not mean “no data exists.” When a usable raster is available, a consumer may sometimes continue with known limitations, but partial reading does not guarantee the safety of an arbitrary file. Limits on time, memory, object count, and structure depth belong to later research and implementations.

## 27. IMXO Passivity and AI Safety

IMXO v0.1 remains static and passive: it contains no executable scripts, network requests, events, or agent commands. Text in an image or annotation may attempt to influence an AI system. Machine readability does not grant ordinary data the authority of an instruction.

Trust boundaries, handling of instruction injection, and action policy are the responsibility of the external consumer. The format does not promise universal protection, but it must not intentionally mix image description with control logic.

## 28. Using Results for Actions

An element's coordinates, name, and semantic role describe the image; they do not prescribe an operation. The execution mechanism, agent authority, and confirmation of actions are outside the format.

Even a new screenshot may cease to match the interface between analysis and action. Reacquiring state, checking immediately before an operation, and monitoring its consequences belong to the external system.

## 29. Reuse of Machine Assertions

An AI result may be added as an annotation or stored separately. An independent observation of the image differs from an inference based on previous assertions. Several derived conclusions from one error are not independent confirmations.

When results are reused, preserving available provenance and dependencies is useful. The specific structure of chains and relationships remains open. An agent is not required to modify the source file.

## 30. Separation of Responsibilities

**IMXO model:** representation of an image, structure, and known differences if the corresponding mechanisms are accepted. **Reader:** correct interpretation of supported content. **Adapter:** data selection and transformation without unjustified claims of completeness or truth. **Source and capture:** permitted user-facing representation and capture policy. **AI consumer:** analysis, verification, and handling of untrusted data. **Execution system:** authority and external actions.

The exact allocation among software components is determined by later architecture and is not fixed by this USE.

## 31. Matters Requiring Further Work

**Assertions and relationships:** alternative descriptions, properties, dependencies and provenance, and the effects of editing.

**Trust and security:** raster/structure conflict, capture-time desynchronization, false verification claims, instruction injection, and propagation of errors among systems.

**Partial representations:** completeness, unknown extensions, omitted relationships, selection cost, and effect on AI quality.

**Transformations:** preservation of meaning and provenance when adapting data for AI.

**Efficiency:** comparison of raster, OCR, direct application access, hybrid access, an image with separate data, and IMXO in terms of quality, errors, latency, volume, total computation, and verification.

**Basis for a new format:** what PNG, SVG, PDF, and container solutions already support; independent reading, consistency, interoperability, and adoption cost.

Topics are linked to `Q` cards and the overall research program; `RSCH` identifiers are assigned only to cards that actually exist.

## 32. Related Artifacts

### Related use cases

- [`USE-0001`](USE-0001-structured-screenshot-content.md) — source of a permitted structured screenshot.
- [`USE-0002`](USE-0002-safe-sanitization.md) — safe sanitization of saved content.

Future CV, machine-semantics, and accessibility scenarios may refine the shared models, but they are not considered published until their files exist.

### Related questions

- [`Q-0003`](../project/questions/Q-0003-logical-object-model.md) — logical object model.
- [`Q-0007`](../project/questions/Q-0007-provenance-model.md) — provenance.
- [`Q-0008`](../project/questions/Q-0008-integrity-trust-model.md) — integrity and trust.
- [`Q-0009`](../project/questions/Q-0009-cv-annotations.md) — CV annotations.
- [`Q-0010`](../project/questions/Q-0010-accessibility-model.md) — accessibility.
- [`Q-0011`](../project/questions/Q-0011-sdk-integrations.md) — libraries and integrations.
- [`Q-0012`](../project/questions/Q-0012-conformance-model.md) — implementation conformance.
- [`Q-0014`](../project/questions/Q-0014-safe-editing-cascade-operations.md) — safe modification and dependencies.

A separate Q on partial completeness is appropriate only after checking the existing coverage of Q-0003/0011/0012; do not create one automatically.

### Related research

- [RSCH-0001 — Container Architecture Comparison](../research/RSCH-0001-container-architecture-comparison.md)
- [RSCH-0004 — Objects, Relationships, and Alternative Assertions](../research/RSCH-0004-object-relationships-alternative-assertions.md)
- [RSCH-0005 — Provenance and Transformation Chains](../research/RSCH-0005-provenance-transformation-chains.md)
- [RSCH-0006 — Integrity, Consistency, and Trust Boundaries](../research/RSCH-0006-integrity-consistency-trust-boundaries.md)
- [RSCH-0009 — Partial Representations and Selective Extraction](../research/RSCH-0009-partial-representations-selective-extraction.md)
- [RSCH-0010 — AI Ingestion Threats and Semantic Laundering](../research/RSCH-0010-ai-ingestion-threats-semantic-laundering.md)
- [RSCH-0011 — AI Input Preparation Comparison](../research/RSCH-0011-ai-input-efficiency-comparison.md)
- [RSCH-0012 — CV Annotation Interchange Formats](../research/RSCH-0012-cv-annotation-interchange-formats.md)

Every card has `DRAFT` status; substantive research starts only after review and approval of the overall plan.

### Related requirements

None yet.

### Related design decisions

None yet.

## 33. Considered and Rejected Approaches

- Treat structured data as unconditionally more correct than the raster — rejected.
- Treat the raster as the sole source of user-relevant semantics — rejected.
- Declare every difference in values a conflict without checking property and state — rejected.
- Always require complete recognition again — rejected.
- Introduce one mandatory universal `trust score` — rejected.
- Treat a `verified` entry as proof — rejected.
- Treat absence of conflict as proof of consistency — rejected.
- Treat absence of an object from a selection as proof of its absence from the source file — rejected.
- Equate support for known types with understanding future extensions — rejected.
- Require processing of every annotation and collapse alternatives into a single truth — rejected.
- Treat multiple derived conclusions as independent confirmations — rejected.
- Include any programmatically available hidden data for agent convenience — rejected.
- Turn semantics into commands for an agent — rejected.
- Introduce a mandatory specialized AI layer or adapt the core format to a particular model — not accepted.
- Treat selective semantics as a guarantee of inexpensive physical reading — rejected.
- Treat token savings or one file with metadata as sufficient proof that a new format is needed — rejected.
- Require IMXO to guarantee the safety of an arbitrary agent — rejected.
- Introduce executable logic, application control, or a temporal video model into a static image — rejected.

## 34. Basis for Reconsideration

Hypotheses may change as a result of research without superseding the scenario. Grounds for refining the USE include new material divergence classes, safe-processing limitations, loss of meaning during transfer, results from independent implementations, comparative experiments, and development of other USE cards.

If one-time analysis and autonomous control prove fundamentally different in purpose, consequences, and required format properties, a separate USE may be appropriate. One negative experiment does not by itself invalidate the scenario. Material changes follow PREP-08.

## 35. External Basis

The following documents are useful for framing questions and research, but do not by themselves prove that IMXO is needed:

- [Microsoft UI Automation Overview](https://learn.microsoft.com/en-us/windows/win32/winauto/uiauto-uiautomationoverview) — programmatic access to interface elements, properties, and relationships.
- [PNG Specification, Third Edition](https://www.w3.org/TR/png-3/) — ancillary chunks and textual data in PNG.
- [OWASP — LLM01:2025 Prompt Injection](https://genai.owasp.org/llmrisk/llm01-prompt-injection/) — risk that untrusted content influences an AI system.
- [OWASP — LLM Prompt Injection Prevention Cheat Sheet](https://cheatsheetseries.owasp.org/cheatsheets/LLM_Prompt_Injection_Prevention_Cheat_Sheet.html) — boundary between user data and control instructions.
- [Ultralytics — Data Collection and Annotation](https://github.com/ultralytics/ultralytics/blob/main/docs/en/guides/data-collection-and-annotation.md) — existing CV-annotation types and interchange practices.

Before approving this section, an agent must verify that the links are available and titles are accurate and remove unsupported claims about source content without adding new conclusions on its own initiative.

## 36. Supersession

`USE-0003` does not supersede earlier scenarios.

## 37. History

- 2026-10-17 — concept of automated structured-screenshot consumption, trust, conflicts, partial processing, responsibility boundaries, and research hypotheses agreed; critical passes over working sections 1–38 completed.
- 2026-10-18 — complete Russian edition prepared for publication as `REVIEW / CANDIDATE`; unresolved technical matters left to `Q` and `RSCH`.
- 2026-10-18 — consequences of partial editing for applicability of machine assertions clarified; planned USE-0004 remains a separate scenario.
- 2026-10-18 — complete English mirror created with matching status, disposition, meaning, and links.
