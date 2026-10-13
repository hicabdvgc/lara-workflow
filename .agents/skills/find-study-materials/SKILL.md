---
name: find-study-materials
description: Find candidate texts, images, audio, video, and other materials for a behavioral study. Use to search supplied collections or external sources, collect accessible originals, and record provenance for later screening.
---

# Find Study Materials

Apply the Designer perspective to material discovery in Stage 3 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the search requirements

Read the relevant design, material requirements, and user instructions. Identify the requested content, media types, quantities, language, properties, and source restrictions. Equivalent explicit requirements support a standalone discovery task.

Clarify ambiguous content or selection requirements that would materially change the search. Preserve the researcher's specified categories and quantities; do not introduce a preferred stimulus type or collection size. Use `find-standardized-tests` for specialized instrument discovery when applicable.

## Locate and inspect candidates

Search the supplied collections or external sources permitted by the request. Use source metadata and meaningful content searches to locate candidates, then inspect the available material and its authoritative source information.

For each candidate, establish its identity, source location, available content or technical properties, and relevant access or reuse conditions. Distinguish source-reported descriptions from properties actually inspected or measured. A thumbnail, excerpt, or preview establishes only what can be verified from that representation.

Prefer original source records and files when available. Preserve the identity of specific editions, variants, recordings, or versions rather than treating related items as interchangeable. Record associations such as a media file and its transcript or an item and its supplied annotations when those associations exist.

A search match supplies a candidate. Acceptance under the study's criteria belongs to `screen-study-materials`. Explain apparent relevance without declaring unperformed screening complete. If suitable candidates are scarce or inaccessible, report the actual collection and the remaining gap; do not fabricate replacements or silently relax the requirements.

## Collect and preserve

When files are to be collected, use the established experiment root and the source organization in [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>). Resolve that reference relative to this skill's directory. Clarify an ambiguous destination before saving.

- Save accessible originals under `sources/` within the requested collection scope. Preserve externally supplied originals when copying them into the project.
- Preserve meaningful filenames, item identities, content, ordering, and associations. Resolve destination collisions without overwriting distinct materials.
- Record the source link or supplied location, original identifier or filename, and the local location so provenance remains traceable after organization. Include relevant attribution or reuse information verified at the source.
- Verify that obtained files are the intended material and are readable. Identify preview or partial content accurately. Keep inaccessible candidates as references rather than creating empty stand-in files.

Access and reuse conditions must come from available evidence. Finding a resource does not authorize purchasing it or contacting its provider. Keep collection within the requested scope and available access.

## Deliver

Return the candidate collection or source-linked results requested by the user, with the descriptive information needed for screening. Use an existing collection inventory where available; keep provenance records separate from participant-facing asset content. Update an existing `LIB.md` for new collection locations.

Before delivery, check that local files correspond to their source records, associated parts remain connected, and reported properties reflect inspected evidence. State any unmet content or quantity requirements. Screening, scientific-content revision, and asset formatting are separate tasks.
