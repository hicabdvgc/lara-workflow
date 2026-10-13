---
name: write-material-templates
description: Create reusable asset template files with fixed content, structured entries, and fillable slots for an experiment. Use to establish material formats under templates/ before populating completed assets.
---

# Write Material Templates

Apply the Coder perspective to the template-creation part of Stage 5 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>). Use the Designer's content requirements to determine the structures needed.

## Read the specification and requirements

Read [Template Schematics.md](<../../../workflow-templates/Template Schematics.md>) before creating or revising templates. Follow its rules for native formats, source-derived content, media references, and output boundaries. Resolve this specification relative to the skill directory.

Read the relevant design, technical specification, and representative source materials where supplied. Equivalent explicit requirements can support a standalone request. Identify the required content and structural constraints without requiring unrelated project stages to be completed first.

Consult all five official references linked in the specification and the relevant documentation or source files for lab.js-specific requirements. Verify compatibility with a specified target version. Resolve ambiguities affecting scientific content or required relationships with the researcher before choosing the affected structure.

## Construct the asset structures

- Identify distinct asset structures from the actual requirements. Reuse a template for compatible assets and separate structures when their requirements materially differ. Components without prepared content require no asset template.
- Choose a file format that represents the required content and can be used by the specified implementation. Write the asset structure in that format, including concrete field names or markup where appropriate.
- Preserve coherent item boundaries, hierarchy, meaningful order, fixed wording, identifiers, annotations, and associations between content and media. Include each element when the asset requires it.
- Insert clearly identifiable slots for source-derived content that will be supplied later. Use a consistent, syntax-valid placeholder convention within each format. Distinguish an unfilled required slot from a valid optional absence; never use a plausible experimental value as a disguised placeholder.
- Represent repeated content according to its relationships and preserve any design-defined collection size. Do not choose an experimental item count merely to illustrate a format.
- Represent future media through the required file-reference slots. Keep real supplied media intact and avoid empty or invalid binary stand-ins.

The template itself contains asset content and structure. Participant-facing instructions are content when the study requires them. Component-use explanations, timing, selection, response handling, and execution order remain in `SCHEMATICS.md` or the supplied technical requirements. Agent-facing conversion instructions and validation commentary remain outside the asset files.

## Save and verify

Save actual template files under the experiment's `templates/` directory, using role-based subdirectories where useful and extensions matching the selected formats. Identify the intended experiment root before writing; the toolkit's `workflow-templates/` contains the reusable specification, not the study's output templates.

Check syntax with an appropriate parser or format inspection, as available. Check encoding, escaping, fixed content, repeated structures, identifiers, and file associations. Validate concrete references against available files; keep future-media slots visibly identifiable without claiming those target files already exist. Check that every required asset structure is represented and that compatible structures are not unnecessarily duplicated.

When revising an existing template, preserve unaffected content and examine whether the structural change affects existing completed assets. Report affected downstream work without silently rewriting those assets beyond the request. Update the existing `LIB.md` for added or changed template locations.

Return the template files with a brief delivery message. Do not generate explanatory TEMPLATE.md packages, README files, template indexes, or component-mapping documents as substitutes for the assets. Completed source-derived materials belong under `assets/` and are produced when the separate formatting work is requested.
