# USE-0001 — Screenshot Preserving Structured User Content

**Status:** REVIEW  
**Disposition:** CANDIDATE

## Contents

[← Back to the use-case index](README.md)

- Scenario foundation: [1](#1-actors-and-systems) · [2](#2-context) · [3](#3-problem-and-need) · [4](#4-goal) · [5](#5-trigger) · [6](#6-primary-scenario)
- Boundaries and representation: [7](#7-permitted-capture-scope) · [8](#8-visibility-and-occlusion) · [9](#9-password-fields-and-intentionally-hidden-values) · [10](#10-spatial-association-between-text-and-image) · [11](#11-text-language-and-writing-direction) · [12](#12-text-presentation)
- Semantics and structure: [13](#13-user-facing-semantics) · [14](#14-structure-and-relationships) · [15](#15-reading-order) · [16](#16-tables-lists-and-diagrams) · [17](#17-links) · [18](#18-text-recognition)
- Provenance and editing: [19](#19-data-provenance-quality-and-verification) · [20](#20-conflicts-between-sources) · [21](#21-user-editing-of-structured-information) · [22](#22-edit-history) · [23](#23-image-changes-and-related-data) · [24](#24-concealing-and-removing-information)
- Completeness and profile: [25](#25-completeness-of-structured-information) · [26](#26-saved-information-completeness-settings) · [27](#27-operational-profile) · [28](#28-lifetime-and-verification-expectations)
- Outcome and risks: [29](#29-expected-outcome) · [30](#30-success-conditions) · [31](#31-impact-of-errors-and-representation-divergence) · [32](#32-misuse-opportunities) · [33](#33-structured-data-exposure-and-minimization)
- Project context: [34](#34-current-workflow-and-known-limitations) · [35](#35-assumptions-and-hypotheses) · [36](#36-relevance-to-imxo) · [37](#37-separation-of-responsibilities) · [38](#38-cross-cutting-accessibility-considerations) · [39](#39-questions-requiring-research)
- Relationships and decision history: [40](#40-related-use-cases) · [41](#41-related-project-questions) · [42](#42-considered-and-rejected-alternatives) · [43](#43-basis-for-reconsideration) · [44](#44-external-basis) · [45](#45-supersession) · [46](#46-history)

## 1. Actors and systems

The primary actor is a user or program that captures the entire screen, an individual window, or a selected region.

The operating system, source application, browser, system accessibility services, screenshot tool, image editor, viewer, text-recognition tool, computer-vision system, AI system, and search or indexing system may participate in obtaining, creating, editing, and later using the image.

IMXO should not depend on a particular operating system, interface model, or screenshot application. The same file should remain usable by independent editor and viewer implementations.

## 2. Context

An ordinary raster screenshot preserves the visual state of a screen but generally destroys the source representation of text, interface structure, and other user-relevant information as independent data.

The text must then be recovered from pixels or obtained again from the source application. Alternative descriptions of images, accessible names of elements, their roles and states, table and list structure, and other information known to the source system at capture time are similarly lost.

Common accessibility systems already separate an element's name, role, state, and value from its visual rendering. Associated textual representations are widely used for non-text content. This demonstrates that user-facing semantics can exist independently of pixels, but it does not mean that IMXO should copy existing platform UI trees.

## 3. Problem and need

Useful information already available to the source system when an image is captured needs to be preserved without turning the screenshot into a copy of the application's internal state.

On one side, losing the original text and user-facing semantics causes unnecessary re-recognition of the image and makes the screenshot less useful for search, copying, editing, analysis, and accessibility.

On the other side, indiscriminately preserving all information available to a program may expose fully covered windows, invisible elements, real values of concealed fields, service data, and other content that the user did not include in the ordinary visual screenshot.

IMXO should lie between these extremes.

## 4. Goal

Preserve the visual representation of the captured region together with associated structured user content as fully as it can be obtained reliably and safely.

The final file should describe the user-facing representation ultimately saved, not everything ever known to the source application, capture tool, or editor.

## 5. Trigger

The scenario begins when the entire screen, an individual window, or a region selected by the user is captured.

The capture moment defines the screenshot's initial state. The source application may subsequently continue changing, close, or cease to exist; this should not automatically change the state already captured.

## 6. Primary scenario

A visual representation of the selected region is produced during capture.

At the same time, the capture tool may obtain available textual and semantic information relating to objects in that representation. Sources may include the operating system, source application, system accessibility services, and other available interfaces.

If the source information is absent or insufficient, the creation tool or a later editor may apply text recognition or other image analysis. The IMXO format itself is not required to contain a recognition mechanism.

After initial capture, the data may be processed before the final file is produced. The user may crop the image, conceal regions, correct obtained text, remove structured information, and add captions, links, regions, arrows, explanations, or other annotations.

The final IMXO is created from the resulting state after such processing.

## 7. Permitted capture scope

In the ordinary scenario, saved data may relate to the user-facing representation actually captured or constitute user-relevant semantics of objects in that representation.

Such data may include visible text, displayed values, alternative descriptions of visible images, accessible names of visible elements, their roles and states, table and list structure, label-to-field relationships, and other information that helps interpret the final image.

The fact that data is technically available to a capture tool does not by itself justify including it.

Fully hidden content, internal application state, and values that the interface intentionally does not show to the user fall outside the ordinary capture scope.

Settings that preserve additional information should not override this boundary.

## 8. Visibility and occlusion

Fully visible content belongs to the screenshot.

If part of a lower window or another visual layer remains visible, the corresponding content also belongs to the screenshot. Merely being beneath another window is not a reason to exclude an element.

Fully covered content is not included merely because the operating system or source application continues to expose it through a programmatic interface.

For partially covered text, only the portion that can be safely associated with the final user-facing representation is preserved. If a source provides the full value but the visible portion cannot be reliably separated from the hidden portion, the full value should not be saved automatically.

An overlay may be opaque, translucent, blurred, or take another form. If the final representation makes the original content effectively unavailable to ordinary visual perception, that content is treated as hidden. No universal numeric opacity threshold is established.

When uncertain, a conservative principle applies: structured data should not make a screenshot informationally broader by revealing the original hidden value.

Documented interfaces on some platforms already provide geometry for fully or partially visible text ranges, but actual accuracy depends on the platform and application and needs experimental verification.

## 9. Password fields and intentionally hidden values

If an interface displays:

`********`

or another masking symbol, the structured representation preserves the value shown to the user rather than the field's real content.

If the user deliberately reveals a password through the interface's normal action and the real value becomes visible on screen, it is treated as ordinary visible content.

The internal value of a concealed field should not enter the screenshot merely because the source application or system interface can technically expose it.

## 10. Spatial association between text and image

Where possible, all preserved text should retain a spatial association with the corresponding image region.

Spatial association is useful for accessibility, AI systems, search, user correction of text, selection, safe removal of related data, consistency checking, and later annotation.

A text object or block may be the basic unit. If the source provides more detailed data, or if such detail is needed for a correct representation, text ranges, words, and individual perceived characters may also be used.

At character-level granularity, one user-perceived character may consist of several Unicode code points; the existing standard defines extended grapheme clusters for this purpose.

Lack of exact geometry should not prohibit preserving otherwise permissible text when it can be reliably associated with a larger object or region. In that case, the exact position is unknown rather than artificially reconstructed.

## 11. Text, language, and writing direction

Structured text preserves logical content, not visual line wrapping caused only by window width or interface layout.

Semantic line breaks are preserved when they are part of the content itself. This may matter for source code, verse, and other material in which changing line breaks changes meaning.

Language may be preserved as an optional property of text or part of the text. Existing BCP 47 language tags should be used instead of a separate IMXO registry.

Writing direction is likewise preserved only when needed. Bidirectional text should rely on existing Unicode rules rather than a new IMXO-specific algorithm.

## 12. Text presentation

Font and other presentation characteristics may be preserved as optional descriptive information.

Font family, size, style, weight, color, and other properties may be useful when the source exposes them with sufficient reliability.

This information does not replace the raster and does not guarantee exact reproduction of the original rendering. The actual rendering may have used font substitution or other mechanisms.

The font file itself does not need to be embedded automatically in a screenshot solely for `USE-0001`.

Existing formats for recognition results and page structure already use a similar separation of text, its geometry, and styles.

## 13. User-facing semantics

IMXO should not be limited to letters visible in pixels.

A visible object may have user-relevant information that is not directly displayed visually. For example, an image may have an alternative description, an icon button an accessible name, and a control a role and state.

Such information is a candidate for preservation when it relates to an object included in the final user-facing representation.

The complete accessibility tree, document object model, internal application containers, service identifiers, event handlers, and other source-application implementation details should not be preserved automatically.

## 14. Structure and relationships

The structured representation should not be limited to a flat set of text rectangles.

When a source system reliably provides user-relevant structure, IMXO should allow preservation of groups and relationships without which individual elements lose meaning once separated from the source application.

Such relationships may include group membership, semantic order, the association of a label with a field, the association of a description with an object, a cell's membership in a row or column, a cell's association with a header, and similar dependencies.

IMXO's internal structure should not be a copy of the source application's tree. Several technical levels of application containers may have no meaning for the saved image.

If reliable structure cannot be determined, separate objects may be preserved without an artificially invented hierarchy.

## 15. Reading order

No single mandatory global reading order is established for the entire image.

Order is preserved where changing the sequence may change meaning.

Order is usually meaningful for a numbered list. For a table, the structure of rows, columns, and headers matters more. For a diagram, relationships between nodes may matter more than any linear order.

If several sequences are correct, IMXO is not required to choose one artificial absolute sequence. Requiring order when it affects meaning is consistent with existing accessibility practice.

The node order of a document object model or platform tree should not automatically be treated as the reading order of the final image.

## 16. Tables, lists, and diagrams

If a table is reliably known to be a table, preserving it structurally is useful instead of retaining only a set of text blocks.

The structure may include rows, columns, cells, headers, and the relationships required among them.

A simple table may later be presented to a user through a common text syntax, for example. A particular text format should not, however, limit the expressive power of IMXO's internal model.

Lists should similarly be preserved as groups of related items when that structure is reliably known.

For diagrams and schematics, preserving nodes, connections, and labels is useful when a source provides them as data. Mermaid, PlantUML, or another source language should not automatically become IMXO's internal model. Such sources should be parsed into a safe passive representation or stored separately only when explicitly needed.

## 17. Links

Under the default safe profile, visible text and the semantic fact that an object is a link are preserved, but the network address hidden behind it is not saved automatically.

The user may separately permit saving link addresses.

When an address is saved, rules may remove known sensitive parameters such as access tokens, keys, passwords, session identifiers, signatures, and similar values.

Removing known parameter names is an additional protective measure, not proof of privacy: sensitive information may use an unknown name, appear directly in the address path, or occupy another part of the address.

If the full address is already displayed to the user as ordinary text, it is treated as visible text content.

IMXO v0.1 should not automatically open links, access them over a network, or perform associated actions.

## 18. Text recognition

Text recognition is not a mandatory part of the format.

A screenshot tool, third-party editor, or other tool may apply recognition to regions for which the source system did not provide sufficient text.

Recognition may also be used as one means of checking whether structured information corresponds to the final raster.

Recognition output is derived information and should not become indistinguishable from text obtained directly from the source system.

If another user later analyzes an already modified or concealed image and derives new information through recognition, AI, or another form of analysis, that is permitted. IMXO should not prohibit image analysis.

Safe removal means that the old value is absent from the file's saved structured data. It does not guarantee that information cannot later be inferred or recovered from the remaining pixels.

## 19. Data provenance, quality, and verification

A single universal measure such as “87% confidence” should not be introduced for every kind of information.

Scores from different recognition tools, computer-vision models, and other sources may use different scales and need not be directly comparable.

It is useful to distinguish:

- data provenance;
- the source's own original score, if one is provided;
- the state of human verification or correction.

For example, a final value may have the provenance:

`recognized from image → corrected by user`

without retaining all earlier incorrect text values.

General provenance models also distinguish the object itself, the activity through which it was created or changed, and the participant in that activity. IMXO may draw on this experience without copying an existing model in full.

By default, provenance information should not automatically include a user name, computer name, device serial number, or other identifiers unnecessary for this scenario.

## 20. Conflicts between sources

No absolute hierarchy such as the following is established:

`operating system > recognition > AI`.

The source system may also provide a stale or incorrect value.

If several sources agree, the result may be used together with provenance information.

If one alternative can be matched to the final image with sufficient reliability, it may be selected.

If the user has verified and corrected a value, the corrected alternative becomes final with the corresponding provenance indication.

If a conflict cannot be resolved reliably, a tool should not silently declare one alternative to be the screenshot's definitive content.

## 21. User editing of structured information

The user should be able to inspect, correct, and remove collected textual and semantic information independently of directly editing the raster.

Correcting an existing representation must be distinguished from adding new user information.

If recognition misreads text and the user corrects it, this remains a correction of the image content.

If the user adds an explanation, comment, link, or new caption, it is a new user annotation.

Changing structured text should not silently turn it into a claim that conflicts with the visual content.

## 22. Edit history

An editor's internal undo and redo mechanism is an implementation detail of that editor.

IMXO does not determine whether an editor stores such history in memory, in a command stack, or by another method.

By default, the final file should not retain old values solely so that a third-party recipient can restore the state from before deletion or correction.

For provenance, knowing that a change occurred is sufficient, for example:

`obtained through recognition → corrected by user`

without retaining the earlier incorrect value.

A specialized persistent edit history may be considered in a separate scenario but is not part of ordinary `USE-0001`.

## 23. Image changes and related data

This rule applies to the entire IMXO ecosystem, not only to one particular screenshot tool.

Any editor that correctly supports modifying IMXO should account for relationships between the raster and structured data.

If an image region changes, the editor should determine which textual, semantic, structural, and other information no longer describes the final image correctly.

Such information should be updated, removed, or marked invalid.

A simple geometric change to an annotation region is not evidence that its meaning remains valid.

For example, if half of a region previously recognized as a face is concealed, the rectangle cannot simply be reduced and the remainder treated as a new valid face region. The old annotation should be removed or verified again.

After editing, any user may nevertheless run text recognition, computer vision, or AI analysis again on the final image and create new derived annotations with new provenance.

Rules for such cascading changes should be defined by a specification or profile, and official IMXO libraries should provide editor developers with reusable implementations of these operations. Using an official library is not a prerequisite for implementing the format.

## 24. Concealing and removing information

Removing structured information must be distinguished from concealing information.

If a user removes only machine-readable text while leaving it visible in the raster, this is not a safe concealment operation.

If a user intentionally conceals an image region, the operation should extend to related data that continues to reveal the concealed content directly.

This data may include text, descriptions, annotations, recognition results, metadata, structural relationships, additional representations, thumbnails, and other saved information.

If the remaining valid part of text or structure cannot be identified safely, removing a larger related object is preferable to leaving a potential disclosure.

If a child object is concealed, a larger independent annotation may remain valid. For example, after a vehicle registration number is removed, the “car” annotation may remain valid, while the number and information related to it should disappear.

Established document-redaction practice likewise treats visible content separately from hidden data such as metadata, comments, hidden layers, and deleted or cropped content. This is a useful external precedent for IMXO.

The detailed safe-concealment model is addressed separately in `USE-0002`.

## 25. Completeness of structured information

IMXO should not promise complete machine understanding of an image.

The file preserves what could be obtained, recognized, or added reliably.

The absence of a structured record for an object does not mean that the object is absent from the raster.

A file may contain only part of the text, several descriptions, and one table while still being a fully valid IMXO file.

An artificial percentage such as “the image is 83% structured” should not be introduced when the full set of potentially existing information cannot be determined objectively.

The fact that particular processing was performed may be preserved; for example, text recognition may have been run for a particular region while object analysis was not.

A user may later supplement the file with new manual, algorithmic, or AI-created annotations.

## 26. Saved information completeness settings

A screenshot tool or editor may offer settings for the amount of structured information to preserve.

A conservative safe profile should be used by default.

An extended or custom profile may allow more permissible semantics, such as sanitized link addresses or additional structural information.

No profile for the ordinary scenario should become a mode for collecting the application's full hidden state.

## 27. Operational profile

Taking screenshots is an interactive and potentially high-frequency process.

Manual review of every automatically discovered element cannot be treated as a prerequisite for creating a file.

Heavy operations, including additional recognition or analysis, do not have to finish at the same time as the capture event itself.

IMXO likewise does not require a “100% processed” state before saving.

Structured information may be highly incomplete, especially for games, custom-rendered applications, remote desktops, and other complex sources.

## 28. Lifetime and verification expectations

A screenshot may exist for anywhere from a few seconds to many years.

Long-term archival storage and cryptographic proof of provenance are not the primary goals of this scenario.

At the same time, the structured content of an ordinary screenshot should not require a permanent connection to the source application or a network service for basic use of the file.

## 29. Expected outcome

The user receives an ordinary visually perceivable image that may additionally contain structured text, user-facing semantics, spatial regions, structure, and relationships.

The text can be used without mandatory repeat recognition.

Applications can understand the association between text and image and, where the corresponding information is available, distinguish ordinary text, a button, a link, a table, or a described image, for example.

When no additional data is available, the raster remains a useful self-contained representation.

## 30. Success conditions

The scenario is successful when the visual image remains a self-contained representation; preserved text has a spatial association with the image where possible; useful user-facing semantics can survive separation from the source application; structure does not require copying the application's internal tree; partial structuring is treated as normal; hidden information does not enter the file merely because it is technically available; the user or editor can correct and remove structured information; and independent editors can correctly update related data when the image changes.

These statements describe the desired scenario outcome and are not, by themselves, normative specification requirements.

## 31. Impact of errors and representation divergence

The primary risk is that the visual and structured representations begin to describe different states.

Example:

`in the image: ₽1,250`  
`in the structured text: ₽12,500`

Such divergence may cause incorrect copying, search, analysis, or automated actions.

A more dangerous case is:

`in the image: ********`  
`in the structured text: the real password`

Here, the structured part directly increases the amount of information disclosed.

Errors may result from capture-time desynchronization, incorrect behavior of a system interface, a recognition error, incorrect editing, or a stale annotation.

When a conflict is detected, disputed data should not silently be treated as a correct representation of the image.

## 32. Misuse opportunities

Machine-readable text makes bulk data extraction substantially easier than a raster alone.

An adversary may also intentionally create a file that visually displays one thing while providing something else to software.

Excessive access to an application's internal tree may turn a screenshot tool into a means of extracting fully hidden information.

The primary scenario therefore does not permit full collection of an application's hidden state.

## 33. Structured-data exposure and minimization

It is necessary to distinguish among data actually presented to the user; sensitive data that the user can see and that therefore already belongs to the screenshot; and internal values known to the application but intentionally not presented to the user.

The last category is not included in an ordinary screenshot merely because it is technically available.

At the same time, adding a machine-readable representation even for visible sensitive data makes it easier to search and extract in bulk. The user should be able to remove such information from the structured part even when it remains visually visible in the raster.

## 34. Current workflow and known limitations

An ordinary raster screenshot reliably records the visual result but loses most of the original structure.

Recognition tools can recover some text, but they do so from pixels after the fact and may make errors.

Platform accessibility interfaces can provide richer source information, but its quality depends on the operating system, development framework, and particular application.

IMXO should therefore not assume that every screenshot on every platform can be fully structured.

## 35. Assumptions and hypotheses

It is assumed that a useful image can contain structured information without becoming a copy of an application.

It is assumed that information from the source system is generally preferable to recovering it again from pixels when that information reliably corresponds to the captured state.

It is assumed that text, regions, roles, descriptions, structures, and relationships have value beyond the source application.

It is assumed that an incomplete structured representation is normal and should degrade to an ordinary visual image without loss of viewability.

These assumptions require verification using real prototypes and different classes of applications.

## 36. Relevance to IMXO

This scenario tests one of the project's central hypotheses:

> an image can preserve its familiar visual representation without also destroying the textual and semantic content that existed at capture time.

The value of IMXO here is not in creating another screenshot codec, but in combining a visual representation, text, regions, structure, semantics, user annotations, and their provenance within one static object.

## 37. Separation of responsibilities

The scenario analysis identifies four distinct levels.

**The core IMXO format** defines common objects: visual representations, text, regions, semantics, relationships, annotations, provenance, and extensions.

**The screenshot profile** defines rules specific to capturing screen content: visibility, handling of concealed values, partial occlusion, safe link settings, and other characteristics.

**The platform layer** defines ways of obtaining the required data on particular operating systems.

**A particular application** defines its user interface, undo mechanism, settings, use of recognition, and other workflow characteristics.

The core format should not contain properties tied directly to Windows, Android, a browser object model, or another particular platform.

## 38. Cross-cutting accessibility considerations

Structured text, spatial associations, accessible names, descriptions, roles, states, order, and relationships may be used by assistive technologies.

Existing accessibility guidance separately emphasizes programmatically determinable names, roles, states, values, and textual alternatives for non-text content.

The presence of such information in a file does not, however, make the final product accessible by itself. A viewer must correctly expose the information through the platform accessibility interface.

A detailed scenario for people with disabilities using IMXO is addressed separately in `USE-0007`.

## 39. Questions requiring research

The scenario's conceptual model is considered formed. The remaining questions primarily require technical and experimental verification.

The actual capabilities of Windows, macOS, Linux, and Android for obtaining text, geometry, roles, states, alternative descriptions, actual visibility, partially visible ranges, and a consistent state around the capture moment need to be determined.

For each capability, the minimum documented platform version, recommended modern interface, link to primary documentation, actual IMXO test result, known limitations, and level at which further work is needed should be recorded separately.

For Linux, records need to identify not only the kernel version but primarily the user-space stack actually involved: accessibility system, Wayland or X11, desktop environment, widget toolkit, and relevant library versions.

A separate matrix of application classes is required: native system widget sets, Qt, browsers, Electron, Java, terminals, custom-rendered applications, games, and other common variants.

The practical cost of obtaining and storing spatial text detail needs research so that useful granularity can be selected without losing value.

Practical means of detecting desynchronization between the visual frame and structured information also need to be tested.

These results should be documented in separate research materials rather than duplicated within each `USE`.

## 40. Related use cases

`USE-0002` — Safe concealment and removal of data in a structured image. It addresses cascading removal of related information, handling of additional representations, and semantic validity of annotations after image modification in detail.

`USE-0003` — Screenshot as input for an AI agent. It examines a situation in which structured information is used not only for search and copying but may directly influence automated decisions and actions.

`USE-0007` — Accessible structured image for an assistive-technology user. It addresses the use of text, regions, descriptions, roles, states, and computer-vision annotations for perceiving visual content.

## 41. Related project questions

The scenario relates to the following existing open project questions:

- [`Q-0006 — Text, fonts, and glyph fallback`](../project/questions/Q-0006-text-fonts-glyph-fallback.md);
- [`Q-0007 — Provenance model`](../project/questions/Q-0007-provenance-model.md);
- [`Q-0008 — Integrity / Trust model`](../project/questions/Q-0008-integrity-trust-model.md);
- [`Q-0010 — Accessibility model`](../project/questions/Q-0010-accessibility-model.md);
- [`Q-0011 — SDK and integrations`](../project/questions/Q-0011-sdk-integrations.md);
- [`Q-0013 — Accessibility standards, regulatory mapping, and format adoption`](../project/questions/Q-0013-accessibility-regulatory-adoption.md).

## 42. Considered and rejected alternatives

**Preserving the complete application tree.** Rejected. This approach exposes an application's internal structure, transfers poorly across platforms, and may contain information outside the user-facing representation.

**Preserving fully hidden objects.** Rejected. Technical availability of an object does not indicate that the user intended to include it in the screenshot.

**A special mode for collecting all hidden information.** Rejected even as an ordinary optional setting. It creates too high a risk of turning a screenshot tool into a mechanism for covert data extraction.

**A raster with mandatory full text recognition.** Rejected as the primary path. If the source system already provides text, recovering it again from pixels is unnecessary and potentially less accurate. Recognition remains an additional tool.

**One flat set of text rectangles.** Rejected as insufficient for tables, forms, lists, labels, and other structures whose meaning depends on relationships.

**Copying document-object-model order as reading order.** Rejected. The technical order of nodes need not match the semantic order of the final image.

**One mandatory reading order for the entire screenshot.** Rejected. Some structures have several correct orders, and for some structures a linear order is not the primary way to convey meaning.

**Omitting spatial association for some preserved text to save space.** Rejected as a general approach. Spatial association is useful for accessibility, AI, editing, verification, and safe data modification. A coarser association is permitted only when exact geometry is unknown.

**Preserving visual line wrapping as content.** Rejected. Logical text is preserved; only semantic line breaks are preserved separately.

**Automatically embedding font files.** Rejected for this scenario. Presentation can be described through metadata, while the exact visual state is already present in the raster.

**One universal confidence score.** Rejected. Scores from different sources are not comparable without knowing their scale and provenance.

**Unconditional preference for the operating system over recognition.** Rejected. Platform semantics may also be stale or incorrect.

**Preserving the complete edit history in the final file.** Rejected for the ordinary scenario. Recording the provenance of a value does not require retaining old deleted values.

**Automatically preserving every link target.** Rejected for the safe profile because tokens, session identifiers, and other information absent from the visible screenshot may be disclosed.

**Using Markdown as the sole internal table model.** Rejected. A textual representation is useful for simple tables but cannot express every possible structure.

**Using Mermaid source or another diagram language as IMXO's internal semantic model.** Rejected. The internal model should remain passive and independent of particular languages and their behavior.

**Automatically shrinking an annotation geometrically after part of an object changes.** Rejected. A geometric change does not prove that the remaining region retains its earlier meaning.

**Permanently prohibiting later recognition or AI analysis of a region previously concealed by another user.** Rejected. After old structured information is removed correctly, the next user may analyze the remaining final image and create new derived information.

## 43. Basis for reconsideration

Accepted decisions may be reconsidered when new evidence appears from platform testing, new means of safely obtaining semantics, material operating-system changes, new international standards, real experience from independent implementations, or well-reasoned public project discussion.

Public discussion alone does not change a decision. If a decision actually changes because of such discussion, the card's main text is updated to the new current state, while the history and relevant section record the reason and link to the discussion.

The version-control system retains the full archaeology of changes. The card retains only the decision history useful for understanding the current model and avoiding repeated discussion of significant alternatives already considered.

## 44. External basis

The development of `USE-0001` draws on existing international experience, but none of the documents below determines IMXO's design.

[WCAG 2.2](https://www.w3.org/TR/WCAG22/) and [WAI-ARIA 1.2](https://www.w3.org/TR/wai-aria-1.2/) guidance supports the independent value of programmatically determinable names, roles, states, values, text alternatives, and meaningful order.

[Unicode Text Segmentation](https://www.unicode.org/reports/tr29/) and the [Unicode Bidirectional Algorithm](https://www.unicode.org/reports/tr9/) provide established mechanisms for segmenting perceived characters and handling bidirectional text that are preferable to IMXO-specific mechanisms.

[BCP 47 / RFC 5646](https://www.rfc-editor.org/info/rfc5646/) provides a widely used language-tag model.

[ALTO](https://www.loc.gov/standards/alto/) is an example of an existing format that stores recognized text, page geometry, and style information together.

The [W3C PROV overview](https://www.w3.org/TR/prov-overview/) demonstrates the usefulness of distinguishing an object, activities affecting it, and participants in those activities.

[Adobe guidance on redacting sensitive content from PDF files](https://helpx.adobe.com/acrobat/desktop/protect-documents/redact-pdfs/redact.html) demonstrates the need to account not only for the visible layer but also for hidden data, metadata, comments, layers, and previously deleted or cropped content.

## 45. Supersession

Does not supersede any previous `USE`.

## 46. History

The initial scenario began as the idea of preserving the text of an ordinary screenshot without mandatory repeat recognition.

During its development, the scenario expanded to preserving structured user content: spatially associated text, accessible descriptions, roles and states, semantic structures, and relationships.

Visibility boundaries, partial occlusion, password fields, text recognition, user correction, provenance, source conflicts, completeness settings, table and diagram structure, links, edit history, and cascading updates to related data were addressed separately.

Complete collection of hidden application state was considered and rejected for privacy and security reasons.

Safe concealment and removal of data was separated into `USE-0002` because that task is substantially broader than initial capture and requires its own behavior model for editors and libraries.
