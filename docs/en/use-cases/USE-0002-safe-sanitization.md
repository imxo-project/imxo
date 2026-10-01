# USE-0002 — Safe Sanitization of a Structured Image

**Status:** REVIEW  
**Disposition:** CANDIDATE  
**Created:** 2026-09-26  
**Updated:** 2026-10-01

> A `USE` is an informative description of an application scenario. This card is not a normative requirement, an architectural decision, or evidence that a particular feature is required.

In this card, **sanitization** means intentionally producing a final structured image in which selected content is no longer retained as part of the file itself or its related representations.

## 1. Actors and systems

The primary actor is a user or system that needs to remove particular content from a structured image before transfer, publication, storage, subsequent processing, or another use.

The operation may involve an image editor, screenshot tool, viewer with editing capabilities, automated content-preparation system, information-protection system, computer-vision tool, AI system, or other software capable of modifying IMXO content.

The information being removed is not necessarily personal or secret. Reasons may include protecting confidential data, minimizing data, correcting erroneous content, removing an unnecessary object, applying organizational policy, or otherwise intentionally forming the final state of the file.

The sanitizing tool need not be the program that originally created the file. Correctness of the result therefore cannot depend on a particular vendor, application, or image-creation environment.

## 2. Context

IMXO may contain multiple interrelated forms of visual and structured data.

A single file may potentially contain one or more rasters, vector elements, text, spatial regions, annotations, descriptions, recognition results, machine-generated markup, alternative object interpretations, and derived information.

The same or related content may be present in several representations at once.

For example, text visible in a raster may also exist as structured text, a region description, an annotation, or recognition output. An image object may have several annotations with different boundaries, names, and provenance.

Changing only one representation does not guarantee removal of the information from the others.

In a simple raster image, the user primarily works with pixels directly. In a structured image, visual removal or concealment may leave the original content in machine-readable form.

The file may consequently appear sanitized to a person while continuing to expose the previous data to a viewer, search system, assistive technology, AI system, or another automated consumer.

The problem is not limited to confidential information. The same divergence may arise after cropping an image, removing an object, correcting text, changing part of an image, deleting an annotation, or otherwise editing the final content.

Data may also be hidden directly inside a retained visual or other media representation in ways not described by the IMXO structural model. This case is fundamentally different from ordinary relationships among file objects and is treated below as a separate scenario boundary.

## 3. Problem and need

A user or system needs to be able to remove content from the final structured image without reliably related representations and derived information silently retaining the removed data.

Safety of the operation cannot depend on whether the user understands the container internals and can independently locate every copy, relationship, and derived representation.

A relationship between data may be known directly from the file structure, an explicit relationship between objects, their provenance, geometry, or an unambiguously defined transformation rule.

For example, a preview may be known to derive from the primary image, text may be associated with a particular region, and a description may belong to a particular object.

A purely semantic relationship that requires external content analysis or knowledge of the world need not be discovered automatically by the base IMXO model.

Several people, programs, or automated analyzers may describe the same visual fragment differently. They may draw different boundaries, use different names, identify an object at different levels of detail, or disagree about whether the fragment is an independent object at all.

Such variation is not an error by itself.

Exact agreement of coordinates, names, or categories therefore cannot be treated as a mandatory condition for object identity or relationship.

Sanitization must also avoid creating a new disclosure channel. The final file need not reveal that particular content previously existed, that a particular region was sanitized, or that it contained data of interest.

## 4. Goal

The goal is a final structured image from which selected content has been removed throughout the complete reliably known chain of related data inside that file.

Removal covers not only the current visual or structured representation, but also known related objects, derived data, and other internal structures when they still contain the information being removed.

If the future IMXO physical model includes previous states, backup structures, old blocks, or other retained internal data, sanitization cannot leave the removed content there merely because ordinary file reading no longer references it.

After a successful operation, the final file describes its current state rather than hiding former content behind a new rendering.

The meaning of the sanitized result persists through the file's subsequent normal lifetime. Opening, resaving, or correctly editing it must not independently restore removed data from remnants retained in the same file.

IMXO does not, however, promise that information cannot be derived again by analyzing data the user intentionally retained in the final image.

If structured text is removed while the same word remains visible in an unchanged raster, later recognition may recover it again. That is a new analysis of the retained image, not restoration of the old structured value.

Similarly, ordinary IMXO sanitization does not establish the absence of arbitrary information that may have been hidden beforehand by an unknown method inside a retained media representation and is not represented as an IMXO object or dependency.

## 5. Trigger

The scenario begins when a user or automated system determines that some content must no longer be present in the final version of a structured image.

The reason may be preparing the file for publication or transfer, applying data-minimization rules, correcting erroneous content, removing an object, or another operation specifically intended to stop retaining the former content in the final file.

Sanitization is distinct from temporary concealment.

Temporary concealment may leave the original content as part of the file so that it can be displayed again later.

Sanitization means intending to produce a state in which the selected content is no longer part of the final distributed file.

A correct user-facing tool clearly distinguishes operations that retain original data from operations that remove it. IMXO does not define the particular user-interface design.

## 6. Primary scenario

The user or system opens a structured image and identifies content that must be removed from the final result.

The target may be text, a visual region, an object, an annotation, a semantic description, machine-generated markup, or other file content.

The operation accounts for reliably known relationships and dependencies associated with the content being changed.

Removing a visual region causes its related textual, semantic, annotation, and derived data to be considered.

Removing or replacing text causes other known representations that directly depend on the former value to be considered.

When an image is cropped, data that relates entirely to content outside the new boundary is not retained merely because it is represented separately from the raster.

The final file is produced without the removed data in every known structure relevant to the operation.

This card does not determine the specific physical mechanism for that operation.

If the operation is interrupted, or a correct implementation cannot reliably finish processing the known dependency chain, the result is not presented as successfully sanitized.

## 7. Scenario scope

The scenario covers removal or modification of data that forms part of a particular IMXO file and relates to the content selected for sanitization.

The scope may include:

- current visual representations;
- structured text;
- semantic objects;
- annotations;
- machine-generated markup;
- descriptions;
- derived representations;
- reduced copies and previews;
- directly related hashes and other derived values;
- internal previous states, if the format permits them;
- old or backup structures, if the selected physical model contains them;
- unused parts of the internal file structure when they continue to retain former data;
- embedded data reliably known to belong to the removed object, even when a particular implementation cannot render its internal format.

Removing a larger visual region also affects structured information about content that disappears completely with that region.

If an object is affected only in part, its old structured information does not automatically remain current. Depending on the nature of the data, it may be updated, reduced, removed, or marked invalid.

Simple geometric containment does not by itself establish a parent-child relationship.

If a cup region lies inside a table rectangle, deleting the “table” annotation is not sufficient reason to delete an independent “cup” annotation automatically.

Cascading change relies on a reliably known dependency or on actual disappearance of visual content, not solely on coordinate overlap or containment.

When text is removed only in part, safely determinable remaining portions may be retained.

For example, the original string may become:

`Number: 12****78`

provided that the removed characters are truly absent from the file data related to them.

The application determines the specific visual or textual replacement method.

## 8. Out of scope

IMXO is not responsible for guaranteed physical erasure of the source file from storage media.

That is a separate responsibility of the operating system, file system, storage medium, and specialized secure-erasure tools.

IMXO also does not control previously created copies, backups, archives, caches, version-control copies, or instances held by other users.

Removing data from one IMXO file is not a mechanism for globally revoking information that has already been distributed.

The format does not define DRM and does not attempt to prevent copying or taking a new screenshot of a displayed image.

IMXO does not prevent analysis of data the user chose to retain in the final raster, vector representation, or other accessible content.

Ordinary IMXO sanitization also does not guarantee detection and removal of arbitrary data hidden by an unknown steganographic method directly inside a retained raster, vector, or other media representation.

Such hidden content may have no object, identifier, relationship, or other structural link by which an IMXO implementation could determine that it exists.

Detecting, analyzing, and attempting to neutralize steganographic channels belongs to separate specialized tools or possible optional enhanced-verification modes.

The format also does not prevent a user from deliberately retaining original values. Safe defaults, warnings, and training are properties of applications and libraries, not enforcement mechanisms of the container.

The specific visual treatment—filling, replacement, blurring, region deletion, or another method—belongs to the editor.

The visual effect alone is not evidence that the structured file was correctly sanitized.

This card does not define a specific physical dependency architecture, embedded-history format, library API structure, or exact container-writing method.

## 9. Inputs and preconditions

The source object is a structured image that may contain one or more visual and structured representations.

Safe modification requires information sufficient to interpret known relationships, object ownership, and derived data.

A correct implementation need not be able to render or internally decode every embedded format.

If the file structure reliably establishes that data opaque to the current program belongs to an object being removed, the absence of a codec does not by itself require retaining that data.

This separates the ability to manage the container structure safely from the ability to render every embedded format.

A different situation arises when a retained raster or other media block itself contains an unknown hidden payload.

For example, IMXO may correctly know that a particular PNG is the primary raster representation without knowing that a third party hid an additional message inside its pixel data. Placing the image in a container does not make that information a known IMXO dependency.

For the scenario to succeed, data that forms part of the IMXO structure or extensions remains within the scope of reliably known dependencies and does not survive sanitization solely because it is placed in an extension. This does not apply to arbitrary unknown encoding inside retained media content.

The absence of a known relationship is not proof that no semantic dependency exists.

Additional analysis by text-recognition, computer-vision, AI, steganalysis, or specialized modules may be used to find potentially related or hidden data, but it is not a condition of base IMXO correctness.

## 10. Operational profile

The most obvious primary mode is interactive.

A user edits an image and expects a correct final file without manually inspecting internal container blocks, indexes, and relationships.

Automated and batch processing must also be possible.

For example, a system may apply sanitization rules to many images before publication, transfer between environments, or storage.

Safety cannot depend on mandatory human inspection of every internal object.

It also cannot require an external AI system or hidden-channel analysis tool.

Sensitive-data identification may be performed separately through organizational rules, specialized analyzers, recognition tools, external libraries, or AI.

IMXO is not expected to detect every possible secret universally. The scenario requires correct handling of content already selected for removal and its known dependencies.

Actual operation frequency, file sizes, batch volumes, and acceptable overhead require experimental validation.

## 11. Lifetime and verification expectations

Sanitization is not a property only of the instant when a file is saved.

If data was correctly removed from a particular IMXO file, it does not later reappear from old representations retained inside it during ordinary opening, resaving, copying, or correct editing.

The meaning of the result persists for as long as that final file exists.

Previous independent copies and data retained outside the file are not covered by this guarantee.

Long-term cryptographic proof that sanitization occurred is not required for this scenario.

Basic use of the result does not depend on an external network service.

## 12. Expected outcome

After successful sanitization, the selected content is absent throughout the reliably known chain of corresponding data in the particular final IMXO file.

The removed value is not retained as a hidden old version, unused object, derived representation, related preview, hash, or other internal content from which the former value can be obtained or confirmed directly.

If the future physical model includes additional internal structures, they likewise do not retain the removed content merely because ordinary file reading no longer uses them.

The final file represents its current state.

If the user deliberately leaves the same information in an independent visual representation, it may still be obtained through a new analysis of that representation.

Removing structured text while retaining the original raster means removing the structured text, not prohibiting later recognition of the pixels.

Successful ordinary sanitization also does not assert the absence of an unknown steganographic payload inside media data that remains part of the final file.

## 13. Success conditions

The scenario succeeds when the content being removed is absent as a retained remnant from every reliably known dependent structure in the file.

The old value cannot be restored by reading a previous internal state, old object, related annotation, derived representation, or another structure that the operation should have affected.

If part of the file or dependency chain cannot be processed reliably, the tool does not present the result as known to be fully sanitized.

Subsequent correct resaving does not independently bring back the old content.

Success does not mean that information cannot be derived anew from a raster, vector representation, or other content the user chose to retain.

Nor does it establish the absence of unknown steganographic information inside retained media content unless detecting it was a separate operation explicitly performed.

These conditions describe the expected scenario outcome and are not by themselves normative IMXO conformance requirements.

## 14. Impact of errors and representation divergence

The main dangerous error occurs when a person believes information was removed while another file consumer continues to obtain it.

Examples include:

- a visual region changes while structured text remains;
- text is removed while an old description remains;
- a primary object is removed while a preview contains the former value;
- the current state is sanitized while an old object version remains inside the container;
- the removed value remains in derived data;
- assistive technology receives information no longer present in current visual content;
- an AI system receives old structured information that the user believes was removed.

Stale annotation is a separate error class.

After an image changes, a structured object may remain syntactically valid while no longer describing current visual content correctly.

For example, after part of a person is removed, an old face region, label, or classification may no longer match the image.

Such information must be reconsidered rather than treated as automatically valid.

The opposite error is also dangerous: an overly broad cascade rule may remove independent data merely because its geometry intersected or was contained by the changed region.

The scenario outcome therefore requires distinguishing actual dependency from simple spatial proximity; the specific representation of that distinction is determined later.

For `USE-0002`, divergence between visual and structured state is not only a quality problem but also a potential source of data disclosure.

## 15. Misuse opportunities

No guarantee can be made that arbitrary third-party software is honest.

A developer may modify a library, bypass safe operations, construct a file manually, or deliberately retain contradictory data.

A malicious file may likewise display one thing visually while providing something else to software.

Steganography adds another class of hidden channel: data may be intentionally embedded directly into an image or other media content so that ordinary viewing does not reveal the existence of the additional information.

Such content may have no relationship to the IMXO object model and therefore need not be detected by ordinary traversal of structural dependencies.

Practical steganographic methods can use images as carriers for hidden data; MITRE ATT&CK also documents the use of steganography in digital media to conceal information.

Changing part of an image or transcoding it may disrupt some hidden encodings, but does not universally prove the absence of a hidden payload.

IMXO is not intended to provide universal protection against deliberately malicious software or every possible hidden channel.

A correct operation over IMXO covers known dependencies and does not leave hidden disclosure channels solely because of the format's own organization; the specific architectural mechanism is determined later.

## 16. Structured-data exposure and minimization

A machine-readable representation increases an image's usefulness but also increases the consequences of mistakenly retaining sensitive information.

Structured text, annotations, and descriptions are easier to search, copy, index, extract automatically, and provide to AI systems than the same information when it is present only visually.

The principle “the user no longer sees the data” is therefore insufficient.

If information must no longer form part of the final file, it is not retained merely because it exists in an invisible or rarely used representation.

The fact that sanitization occurred also need not be retained automatically.

The final recipient need not know that a region previously contained different content, where removal occurred, or what data was removed.

If an organization needs a separate audit trail, it may be provided by an external process or a future specialized mechanism that is not a condition of this scenario.

## 17. Current workflow and known limitations

The divergence between visible and internal content is not unique to IMXO. Complex documents can already contain both a visually perceived representation and additional data that may not be obvious during ordinary viewing.

In PDF, such data includes metadata, comments, hidden layers, attachments, embedded search indexes, deleted or cropped content, overlapping objects, and hidden text. [Adobe documentation on types of removable data](https://helpx.adobe.com/acrobat/desktop/protect-documents/redact-pdfs/redactable-data.html) explicitly includes transparent text, text covered by other content, and text in a background-matching color as hidden text, while the [PDF sanitization guide](https://helpx.adobe.com/acrobat/desktop/protect-documents/redact-pdfs/sanitize.html) distinguishes removal of visible content from removal of hidden data.

In Microsoft Office documents, Document Inspector separately searches for hidden text, comments and revision information, personal properties, custom XML data, embedded objects, invisible objects, and off-slide content. [Microsoft Document Inspector documentation](https://support.microsoft.com/en-us/office/collab-files/remove-hidden-data-and-personal-information-by-inspecting-documents-presentations-or-workbooks) also records detection limits: white text on a white background is not identified as standard `Hidden Text`, covered objects may not be found, and some embedded objects can be found but not removed automatically.

On web pages, visual and programmatic availability may likewise differ. [W3C/WAI Technique C7](https://www.w3.org/WAI/WCAG21/Techniques/css/C7) demonstrates a method that keeps text from appearing on screen while leaving it available to screen readers and braille displays.

In PDF, the visible graphical representation and extractable text may also be distinct related representations. [The PDF Association `ActualText` example](https://pdfa.org/techniques-for-accessible-pdf/actualtext-provides-correct-extractable-characters-in-place-of-ocr-errors/UA1_Tpdf-G2_06/) separately tests whether machine-extractable characters correspond to the visual representation.

These examples show that visual absence and actual absence from machine-accessible structure are different properties.

Another class of concealment embeds additional data directly inside the media content itself. The [NIST glossary](https://csrc.nist.gov/glossary/term/steganography) defines steganography as hiding the existence of communication or embedding data within other data to conceal it.

[OpenStego](https://www.openstego.com/) is a practical example: it can place arbitrary data inside an image and later extract it; [RandomLSB](https://www.openstego.com/features) uses the least-significant bits of image color channels.

IMXO must therefore distinguish structural sanitization of known objects, representations, and dependencies from analysis of hidden channels inside media data, which may require specialized methods and has no universal detection guarantee.

Database and other dataset anonymization presents an analogous broad class of tasks in which detecting sensitive information, choosing a transformation policy, and producing a sanitized result may be separate stages.

## 18. Assumptions and hypotheses

IMXO may contain several related representations and interpretations of visual content, but need not contain them in every file.

They may include rasters, vector elements, text, regions, annotations, descriptions, relationships, and machine-generated information.

Different people, programs, and automated analyzers may independently describe the same visual content differently.

Differences may include:

- geometric boundaries;
- level of detail;
- name;
- category;
- relationships to other objects;
- the interpretation of whether a selected fragment is an independent object at all.

Two rectangles that differ by one pixel may describe the same object. Two substantially overlapping regions may describe different objects.

One person may call an object a “dog,” another a “Chihuahua,” and a third an “animal.”

Different automated analyzers may likewise classify the same visual fragment differently.

The scenario does not assume that there is a single mandatory machine or human interpretation of the image.

The format may retain several such assertions together with information about their provenance.

Normalizing names, finding similar regions, detecting likely duplicates, matching synonyms, and merging annotations may be useful additional functions, but are not mandatory container responsibilities.

The working hypothesis is that multiple related representations increase the risk of residual data after an image changes.

A correct safe-removal operation therefore covers the complete reliably known chain of selected content within the final file.

The structural model cannot by itself guarantee discovery of arbitrary information hidden by an unknown method inside retained media content.

Nor is universal protection possible against an intentionally modified implementation that bypasses safe operations.

## 19. Relevance to IMXO

`USE-0002` tests a fundamental property of the structured-image concept: the ability to edit a rich, multipart representation safely.

IMXO may potentially combine several rasters, vector content, text, regions, overlapping regions, relationships, annotations, descriptions, and several independent interpretations of the same visual content in one file.

This increases the file's usefulness while also creating more places where former information may survive editing.

The format needs to allow several differing assertions about the same or a nearby visual object without requiring them to be reduced to one “truth.”

For example, different people or programs may retain different boundaries and names for one fragment.

The consumer or additional analysis tools decide which assertions to use, which sources to trust, and whether two annotations describe the same object.

After visual content changes, however, structured assertions whose correctness depends on the changed region cannot silently remain current when they no longer correspond to the image state.

The scenario's guarantee boundary also remains explicit: safe management of IMXO objects and dependencies is not proof that no unknown hidden channel exists inside retained media content.

Safe editing may therefore affect the logical object model, dependencies, the physical container structure, extensibility, possible previous-state storage, and future library operations.

If rich structure makes reliable removal practically impossible, it becomes an additional IMXO risk rather than a benefit.

## 20. Cross-cutting concerns

### Security

Removed content does not remain in known dependent representations or residual structures of the final file.

Structural sanitization is distinct from hidden-channel analysis of retained media content. Performing one operation is not evidence that the other was performed.

### Privacy

Machine-readable form increases the consequences of mistakenly retaining sensitive data.

### Interoperability

An independent editor needs enough standardized information about IMXO structure and relationships to perform modification correctly even when it did not create the source file.

### Extensibility

New data types and embedded formats cannot easily fall outside the dependency model and silently survive sanitization.

### Accessibility

If content is removed from the final image, the old value does not continue to be conveyed to an assistive-technology user through a related structured representation.

### Long-term preservation

Archival existence of a file is not a reason to retain removed previous values inside it.

### Trust

A visually sanitized appearance alone does not prove the absence of residual structured data or an unknown hidden channel in media content.

### Cryptography

This scenario does not require its own built-in infrastructure for digital signatures, certificates, or cryptographic provenance attestation.

Mechanisms for detecting accidental corruption of the physical container are considered separately from the trust system.

## 21. Separation of responsibilities

Several levels of responsibility must be distinguished for this scenario.

**The IMXO format** represents objects, relationships, dependencies, and visual and structured data to the extent needed for independent understanding of the file.

**The library layer** may provide reusable safe-modification and removal operations so applications do not each have to reproduce all internal dependency logic.

The exact responsibilities and API of such a layer remain matters for later design.

**An editor or other application** defines the user scenario, selects the operation target, provides the interface, and decides how to change visual content.

**Specialized external tools** may detect sensitive data, recognize documents, faces, numbers, secrets, and personal information, analyze possible hidden channels, and perform other tasks that need not become mandatory parts of the base format.

The format is not responsible for universal recognition of such data.

## 22. Verifying the sanitization result

After the operation, it must be possible to check structural consistency of the result within the model known to the IMXO implementation.

The check may search for remaining references to the removed object, dependent representations, old internal states, derived data, and other structures the operation should have affected.

This does not require repeating raster recognition, analyzing the image with AI, performing steganalysis, or proving the absence of every logically or covertly encoded item of information.

The purpose is to verify that the structural operation itself completed consistently and did not leave a known part of the chain untreated.

The specific verification mechanism is determined later.

## 23. Failure or interruption

Safe removal is treated as an integral operation.

If file writing is interrupted, storage fails, only part of the cascade completes, or a mandatory known dependency cannot be processed, the result is not presented to the user as successfully sanitized.

The desired behavior can be stated as:

> either the operation completes in full, or the result is not considered successfully sanitized.

The mechanism providing this property—rebuilding, a temporary file, atomic replacement, or another approach—is an architectural decision and is not selected by this card.

Temporary data created outside the final IMXO by a particular editor belongs to the application environment and operating system.

## 24. History and previous states

If previous states are stored inside the IMXO itself, they are part of that file and fall within the sanitization scope.

Removing content from the current state while retaining the same value in accessible internal history is not successful sanitization.

An individual editor's internal undo mechanism may exist separately from the file and is an application implementation detail.

Similarly, cloud history, a backup, a version-control system, and a previously saved instance are external copies outside the responsibility of this file.

If the selected IMXO architecture supports embedded history, successful sanitization covers states within the final file that relate to the removed content.

## 25. Alternative annotations and normalization

One visual object may have several independent annotations.

They may originate from different people, programs, computer-vision models, or other sources.

Their region boundaries need not match exactly.

Their names and categories may also differ.

The scenario assumes that such variants can be retained as independent assertions with the necessary provenance information; the specific logical model is determined later.

The format need not determine automatically that two similar regions represent the same object.

An additional tool may normalize names, find similar regions, compare overlaps, match labels, and identify synonyms and likely duplicates.

Such analysis is an additional capability.

When visual content changes, every structured assertion whose validity depends on the changed region needs reconsideration.

If a large visual object is removed together with its content, reliably dependent child data is also removed or rebuilt.

Simple geometric containment alone is not sufficient reason for a cascade.

Spatial relationship and actual dependency must be distinguished.

## 26. Export and conversion to other formats

Exporting IMXO to another format is a separate data transformation.

Different target formats have different expressive capabilities and need not preserve the complete IMXO structure.

Export to an ordinary raster format will usually discard most of the structured model.

More structured formats may potentially carry more visual, textual, vector, or additional information, but an exact mapping from IMXO to PDF, SVG, and other formats requires separate design and practical validation.

The target format's capabilities and the exporter implementation determine the specific data that can be carried.

IMXO does not guarantee preservation of its complete structure after conversion to another format.

The general rule relevant to this scenario is that correct export of a sanitized file proceeds from its current final state and does not use internal data already removed by sanitization.

## 27. Moving data between files

Sanitization is limited to the particular file in which the operation is performed.

Once an object is copied from one IMXO into another file, two independent data instances exist.

Removing the object from the source file does not automatically remove it from the previously created copy.

The same rule applies to clipboard data, exported files, backups, and previously sent instances.

IMXO is not a distributed data-revocation system.

## 28. Questions requiring further work

Work on `USE-0002` identified several project uncertainties, but they do not automatically become separate new `Q` cards.

### Project unknowns

They are already covered by existing project questions:

- physical absence of removed data from residual structures — [`Q-0002`](../project/questions/Q-0002-physical-file-structure.md);
- relationship types, dependencies, and nesting — [`Q-0003`](../project/questions/Q-0003-logical-object-model.md);
- interaction between removal and provenance — [`Q-0007`](../project/questions/Q-0007-provenance-model.md);
- representation consistency and verification data — [`Q-0008`](../project/questions/Q-0008-integrity-trust-model.md);
- alternative annotations and annotation changes — [`Q-0009`](../project/questions/Q-0009-cv-annotations.md);
- library operations and integrations — [`Q-0011`](../project/questions/Q-0011-sdk-integrations.md);
- testable properties of a correct implementation — [`Q-0012`](../project/questions/Q-0012-conformance-model.md).

The cross-cutting question of safe-modification and cascade-operation semantics is recorded in [`Q-0014`](../project/questions/Q-0014-safe-editing-cascade-operations.md).

### Future factual research

Separate `RSCH` work under an approved research plan may be needed for:

- existing sanitization models for complex documents and structured data;
- practical cost of physical rebuilding or other ways to remove residual data;
- prototype behavior with large dependency chains and partially affected objects;
- extensions and opaque embedded representations;
- result verification and safe completion when operations fail;
- conversion of sanitized IMXO data into other formats;
- existing approaches to finding, masking, and anonymizing sensitive data;
- capabilities and limitations of steganalysis for raster and other media representations;
- the effect of decoding, re-encoding, resizing, cropping, and other transformations on different hidden-channel classes;
- whether a separate optional enhanced media-sanitization or verification mode is useful and what its guarantee boundary would be.

Such research is created as separate `RSCH` artifacts when the relevant topic enters an approved research plan. `RSCH` identifiers are not reserved in advance.

## 29. Related artifacts

### Related use cases

[`USE-0001 — Screenshot Preserving Structured User Content`](USE-0001-structured-screenshot-content.md) directly created the need to consider safe removal and cascading update of related data separately.

Planned `USE-0003`, `USE-0004`, and `USE-0006` may also affect this scenario after their cards are created because automated agents, computer vision, and machine-generated semantic annotations can create additional derived representations.

### Related project questions

- [`Q-0001 — IMXO Container Architecture`](../project/questions/Q-0001-container-architecture.md);
- [`Q-0002 — Physical File Structure`](../project/questions/Q-0002-physical-file-structure.md);
- [`Q-0003 — Logical Object Model`](../project/questions/Q-0003-logical-object-model.md);
- [`Q-0007 — Provenance Model`](../project/questions/Q-0007-provenance-model.md);
- [`Q-0008 — Integrity / Trust Model`](../project/questions/Q-0008-integrity-trust-model.md);
- [`Q-0009 — Computer Vision Annotations`](../project/questions/Q-0009-cv-annotations.md);
- [`Q-0010 — Accessibility Model`](../project/questions/Q-0010-accessibility-model.md);
- [`Q-0011 — SDKs and Integrations`](../project/questions/Q-0011-sdk-integrations.md);
- [`Q-0012 — Conformance Model`](../project/questions/Q-0012-conformance-model.md);
- [`Q-0014 — Safe Modification, Dependencies, and Cascade Operations`](../project/questions/Q-0014-safe-editing-cascade-operations.md).

### Related research

Not assigned yet.

### Related requirements

None yet.

### Related design decisions

None yet.

## 30. Considered and rejected alternatives

**Treat visual concealment as sufficient removal.** Rejected. In a structured image, the original data may remain in other representations.

**Remove only the directly selected object.** Rejected. Reliably known dependent and derived data belong to the same operation.

**Retain the old value in the final file's embedded history after sanitization.** Rejected. This permits direct recovery of the removed data from the same file.

**Retain a hash of the removed value merely because it is not the original value.** Rejected as a universal approach. A derived value may confirm a guess about the source data or, under some conditions, help recover it.

**Require exact coordinate agreement as evidence of object identity.** Rejected. Independent annotations of the same object may have different boundaries.

**Treat every geometric containment as a parent-child relationship.** Rejected. Spatial containment does not prove semantic dependency.

**Automatically remove every intersecting object.** Rejected. An independent object may legitimately intersect the changed region and remain current.

**Automatically select one correct annotation from several.** Rejected. People and automated systems may provide several valid interpretations.

**Require AI for correct sanitization.** Rejected. Base correctness relies on known file structure and dependencies.

**Automatically retain a marker that a particular region was sanitized.** Rejected for an ordinary result. Such a marker may itself disclose additional information.

**Control external copies and previously sent files.** Rejected as a responsibility of an image format.

**Use DRM as a means of safe removal.** Rejected. Access control and data removal are different tasks.

**Prohibit subsequent analysis of the remaining image.** Rejected. A user may analyze the content actually retained.

**Treat the absence of a codec for an embedded format as an automatic obstacle to removing the entire related block.** Rejected. If the container knows that the data belongs to the removed object, inability to render it does not itself require preserving the block.

**Guarantee complete preservation of IMXO structure when exporting to any other format.** Rejected. The target format determines export capabilities.

**Guarantee the absence of all steganographically hidden information after ordinary IMXO sanitization.** Rejected. An arbitrary hidden channel inside retained media content may have no structural representation or known IMXO dependency and cannot be detected reliably by processing the file's object model alone.

**Treat ordinary image transcoding as proof that steganographic information was removed.** Rejected. Different concealment methods have different properties, and changing media data does not universally guarantee the absence of a hidden message.

## 31. Basis for reconsideration

The conclusions of this card may be reconsidered if practical implementation shows that the described safe-removal model is technically infeasible or imposes unacceptable constraints.

Other grounds may include:

- discovery of new residual- or hidden-data classes;
- a change to the selected physical container model;
- emergence of new extension types;
- experience from independent implementations;
- ambiguity discovered in dependency rules;
- results of future `USE` work;
- systematic research into existing formats, sanitization tools, and hidden-channel analysis methods;
- substantiated public project discussion.

A changed conclusion requires updating the current card and briefly recording the reason in its history.

The version-control system retains the complete editorial history.

## 32. External basis

Existing formats and data-processing tools demonstrate that visual removal, removal of hidden data, detection of sensitive content, hidden-channel analysis, and physical destruction of data are distinct tasks.

[Adobe Acrobat](https://helpx.adobe.com/acrobat/desktop/protect-documents/redact-pdfs/sanitize.html) distinguishes removal of visible PDF content from sanitization of hidden data; its [list of removable data types](https://helpx.adobe.com/acrobat/desktop/protect-documents/redact-pdfs/redactable-data.html) includes metadata, comments, hidden layers, attachments, an embedded search index, deleted or cropped content, overlapping objects, and hidden text.

[Microsoft Document Inspector](https://support.microsoft.com/en-us/office/collab-files/remove-hidden-data-and-personal-information-by-inspecting-documents-presentations-or-workbooks) searches for hidden text, comments, tracked changes, custom XML, invisible objects, off-slide content, embedded files, and other supplementary Office-document data. The same documentation notes that white text on a white background and covered objects may not be detected, while some discovered items cannot be removed automatically.

[W3C/WAI](https://www.w3.org/WAI/WCAG21/Techniques/css/C7) describes a method by which text is not displayed visually while remaining available to assistive technology. The [PDF Association](https://pdfa.org/techniques-for-accessible-pdf/actualtext-provides-correct-extractable-characters-in-place-of-ocr-errors/UA1_Tpdf-G2_06/) demonstrates a related but independent machine-extractable PDF text representation.

[NIST](https://csrc.nist.gov/glossary/term/steganography) defines steganography as hiding the existence of communication or embedding data within other data. [OpenStego](https://www.openstego.com/) can embed arbitrary data in an image and later extract it, while [MITRE ATT&CK T1027.003](https://attack.mitre.org/techniques/T1027/003/) documents practical use of steganography in digital media. These sources establish a separate class of hidden channels but do not imply that IMXO needs built-in universal steganalysis.

[NIST SP 800-88 Rev. 2](https://doi.org/10.6028/NIST.SP.800-88r2) treats physical-media sanitization as a distinct task. For IMXO, this supports the responsibility boundary between destroying data on storage media and sanitizing the contents of one file.

[Presidio](https://microsoft.github.io/presidio/) separates detection of personal information from subsequent anonymization of detected entities and explicitly warns that automated detection does not guarantee finding all sensitive information. Its [text anonymization documentation](https://microsoft.github.io/presidio/text_anonymization/) separately presents the analyzer and anonymizer. This matches the scenario boundary: an external analyzer may decide what to remove, while an IMXO operation correctly handles already selected content and known dependencies.

Database-anonymization tools offer further examples of different sensitive-data processing modes without directly transferring a database model to an image format. [PostgreSQL Anonymizer](https://postgresql-anonymizer.readthedocs.io/en/stable/) distinguishes dynamic masking, static masking, and anonymous dumps. [Greenmask validate](https://docs.greenmask.io/latest/commands/validate/) checks transformed data, displays source/result differences, compares schemas, and can fail in strict mode when warnings remain unresolved. [`pg_anon`](https://github.com/TantorLabs/pg_anon) uses descriptions of sensitive fields and produces an anonymized result through dump and restore.

These systems do not determine IMXO's design and are not copied literally. They serve as independent external examples distinguishing temporary concealment, production of a sanitized result, and separate verification of a completed transformation.

## 33. Supersession

`USE-0002` does not supersede an earlier use case.

If later work shows that this scenario needs to be divided into several materially different use cases, the new cards receive their own identifiers and supersession relationships are recorded under PREP-08.

## 34. History

`USE-0002` arose from safe-modification and removal questions identified while developing [`USE-0001`](USE-0001-structured-screenshot-content.md).

The initial problem concerned a user visually concealing or removing content while its textual or semantic representation remained in the file.

The scenario was expanded into a general model for safe sanitization of a structured image.

The operation was found to need consideration not only of current representations, but also of derived data, hashes, previews, and other known dependencies within the particular file.

If the selected physical model contains previous states, old blocks, backup indexes, or other residual structures, sanitization likewise cannot retain removed data in them.

It was separately recorded that IMXO is not responsible for external copies, physical erasure of storage media, revocation of previously sent files, DRM, or making it impossible to derive information again from visual data deliberately retained by the user.

The boundary between temporary concealment and removal was developed.

Several independent human and machine annotations of the same visual content were considered. Differences in boundaries, names, and classification are a normal property of structured data rather than automatically an error.

The scenario records that simple geometric containment does not by itself prove a parent-child relationship, while a change to visual content requires reconsideration of reliably dependent structured assertions.

Result verification, interrupted operations, possible state history, movement of data between files, and export to formats with different expressive capabilities were considered separately.

A further boundary was drawn between structural IMXO sanitization and steganographically hidden data within retained media content. Ordinary sanitization does not promise universal detection of such hidden channels. Any separate enhanced inspection, normalization, or steganalysis mode requires later research.

The scenario identified an independent open question about safe-modification and cascade-operation semantics, recorded as [Q-0014](../project/questions/Q-0014-safe-editing-cascade-operations.md).

2026-10-01 — the card was refined following review: architectural assumptions were neutralized, independent external bases were added, and the identified unknowns were linked to existing `Q` cards and the new `Q-0014`.
