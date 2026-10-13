---
name: revise-text-files
description: Revise existing study prose, specifications, participant-facing text, or structured text assets. Use for scoped wording and content changes that preserve experimental meaning, file structure, and item associations; executable-code changes belong to code revision.
---

# Revise Text Files

Apply the persona responsible for the content: Conceptualizer for study concepts, Designer for experimental content, and Coder for technical specifications and asset formats. Follow the revision rules in the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the requested change

Read the target files, requested edits or supplied findings, and the requirements governing their meaning and format. Identify the file's role and downstream consumers. Equivalent explicit user requirements can support a standalone revision without creating missing upstream documents.

Route by content and function rather than extension. Executable logic belongs to `revise-code` when available. For a mixed file, distinguish participant wording or textual data from executable behavior and keep the edit within the requested scope.

Clarify ambiguities that would change instructions, item meanings, scoring descriptions, conditions, timing, or other scientific decisions. An explicit researcher decision can govern the change directly; record it in the affected design documentation before dependent assets or implementation are updated. Do not infer a new design from a defect report that leaves the intended behavior unresolved.

## Use the governing structure

Read the corresponding specification when revising its output:

- Use [Concept Doc Schematics.md](<../../../workflow-templates/Concept Doc Schematics.md>) for `CONCEPT.md`.
- Use [Design Doc Schematics.md](<../../../workflow-templates/Design Doc Schematics.md>) for `DESIGN.md`.
- Use [Framework Doc Schematics.md](<../../../workflow-templates/Framework Doc Schematics.md>) for `SCHEMATICS.md`.
- Use [Template Schematics.md](<../../../workflow-templates/Template Schematics.md>) and the actual asset schema for textual material templates and completed assets.

Resolve these resources relative to this skill directory. Apply the relevant requirements to the requested edit while retaining unaffected document organization and content.

## Apply scoped revisions

Edit the intended text and necessary dependent references. Preserve unaffected wording, meaningful emphasis, identifiers, item order, labels, response-option associations, and links to media or source records. Retain original source materials when revising prepared assets so the result can be compared with its source.

For structured data, preserve types, required fields, optional-value conventions, escaping, delimiters, and encoding. A numeric-looking identifier may still be a string. Do not normalize values or reorder collections unless the requested change or format requires it.

Use the appropriate document capability when prose is stored in a format requiring document-aware editing. For text embedded in markup or a larger file, preserve its surrounding structure and bindings. Update affected file references and the existing `LIB.md` when a requested rename or location change alters the project map.

## Verify and deliver

Compare the revision with the original to confirm that the requested changes were applied and unaffected content remains intact. Parse structured formats and check their applicable schema, identities, quantities, and associations. Inspect rendered text where the change affects meaningful presentation; test its loading in the available consumer when integration is affected.

Match verification to the change. A prose correction needs content and format checks; a changed instruction or structured asset may also require an affected experiment path to be exercised. State any unavailable checks accurately.

Return the revised files and a concise account of substantive changes and verification. Keep editorial commentary outside participant-facing content and completed assets unless the user requested annotations there. Processing supplied human feedback does not entail guiding or organizing human test sessions.
