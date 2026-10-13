---
name: revise-multimodal-files
description: Edit existing study images, audio, video, and other multimodal assets to requested content or technical requirements. Use for media revisions that retain original sources and verify the resulting presentation and experiment compatibility.
---

# Revise Multimodal Files

Apply the Designer perspective with Coder support for integration, following the revision rules in the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the source and requirements

Inspect the actual target media and read the requested revisions, source associations, and relevant content and technical requirements. Use the design, technical specification, asset requirements, or equivalent explicit user instructions. Identify the destination and which version the experiment currently consumes.

Read the relevant media, source-preservation, and verification requirements in [Template Schematics.md](<../../../workflow-templates/Template Schematics.md>) when revising prepared study assets. Resolve this reference relative to the skill directory.

Determine which properties the edit should change and which experimentally meaningful properties must remain. Examples include content, crop, color, dimensions, duration, playback rate, loudness, channels, and synchronization, as relevant to the actual request. A display-size requirement alone does not establish permission to crop or resample the source.

Resolve ambiguous changes to stimulus meaning or presentation with the researcher before performing them. Reflect established scientific changes in the relevant design requirements before dependent revisions. Creating a new material from a brief belongs to `create-study-materials` when available.

## Revise the media

- Retain the original source and identify the revised derivative so its source and role remain traceable. Use the existing project arrangement and naming conventions, preserving item identifiers and associations.
- Select an available editing capability that supports the requested operation and follow its applicable instructions. Check uncertain tool behavior, output-format support, and compatibility against official documentation when needed.
- Apply the specified transformation while preserving unaffected content and required properties. Use a method whose precision can satisfy the task; a visually plausible result does not establish preservation of exact pixel, acoustic, or timing properties.
- For combined media, preserve required relationships among audio, frames, captions, overlays, and associated files. If an edit changes a timeline, update dependent timing information only according to the requested or design-defined change.
- Save in the requested format or the established consumer-compatible format. Record transformation settings when needed to reproduce the derivative or verify a study requirement.

If the available capability cannot perform or inspect a required operation, explain the specific limitation and retain any completed work. Do not substitute a different stimulus or transformation without a supporting user requirement.

## Inspect the result and integration

Open the rendered image or document, or play the revised audio or video using available inspection capabilities. Check the requested content changes and relevant presentation properties against the source and requirements. Metadata and a successful export alone do not establish perceptual quality or correct media content. Identify any modality or segment that could not be inspected.

Measure technical properties affected by the operation where the requirements define them. Confirm that the actual output format is supported by the intended consumer, and inspect the relevant presentation or playback in the experiment when it is available and the revision affects integration.

Update dependent asset references when a path, format, or association changes, and update the existing `LIB.md` for changed locations. Retest the affected loading and presentation paths. Keep source records available for comparison and avoid replacing unrelated assets during batch revisions.

## Deliver

Return the revised media files with their source associations, a concise description of the applied changes, and evidence of the requested content and technical checks. Distinguish measured, inspected, and unverified properties. Report experiment compatibility only to the extent actually checked; media inspection alone does not establish a complete experiment test.
