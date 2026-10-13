---
name: format-study-materials
description: Convert selected source materials into completed experiment assets using established templates or explicit target formats. Use to populate content slots, preserve material relationships, and verify ready-to-use assets under assets/.
---

# Format Study Materials

Apply the Designer perspective with Coder support for technical formats to Stage 5 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Read the target structure

Read [Template Schematics.md](<../../../workflow-templates/Template Schematics.md>), especially its source-formatting, media, verification, and output rules. Resolve the reference relative to this skill's directory.

Read the selected source materials, existing asset templates or explicit target formats, and relevant design and technical requirements. Inspect any selection record to identify the intended subset. Equivalent user requirements can support a standalone formatting request.

Establish the mapping from source items and their associated parts to the target structure. Clarify ambiguous identities, conflicting fixed content, or missing required values before populating dependent fields. If an asset structure must first be created, use the requirements and `write-material-templates` where that work is in scope.

Follow the specification's official-reference requirements when establishing lab.js-specific format compatibility. Verify relevant claims against the applicable documentation or source and the specified target version.

## Populate the assets

- Preserve the selected content's wording, meaningful formatting, order, identifiers, labels, and associations. Keep related parts of one item together.
- Populate fixed content and source-derived slots according to the template. Preserve established collection sizes and intentional repetitions; report source shortages instead of inventing or duplicating content to fill them.
- Derive annotations only from supplied information or design-defined rules. Preserve distinctions such as identifiers versus numeric measurements when converting structured data.
- Replace required slots with actual content. Use the format's representation of optional absence only when that absence is allowed; an unknown required value is not an optional omission.
- Perform specified file conversions or media transformations while retaining the originals. Cropping, resizing, recompression, recoloring, or duration changes require support in the study requirements. A runtime display-size instruction alone does not authorize modifying source media.
- Maintain references between completed content and actual associated files. Use portable paths with the correct resolution base and filename case for the intended asset arrangement.

Keep runtime control rules and agent-facing explanations outside the completed assets. Participant-facing instructions remain asset content when required. Preserve the reusable templates under `templates/` and original collections under `sources/`.

## Save and verify

Write completed assets under the established experiment's `assets/` directory or the explicitly requested destination. Resolve an ambiguous destination before writing and preserve unrelated existing assets.

Parse or inspect the chosen formats to check syntax, data types, encoding, escaping, and required structure. Check item counts, identities, associations, and concrete file references against the selected sources. Confirm that all required slots are resolved and that no unintended item has been omitted or added.

Inspect rendered, displayed, or played results where conversion can affect meaningful presentation. Check the properties affected by requested media transformations. If the target consumer is available, verify the relevant asset-loading path without claiming that the entire experiment has been tested.

Return the completed asset files with a brief delivery message and update the existing `LIB.md` for added or changed locations. Keep validation commentary outside the assets. If an asset cannot be completed because required source content is absent, identify the specific gap and do not present it as ready for use.
