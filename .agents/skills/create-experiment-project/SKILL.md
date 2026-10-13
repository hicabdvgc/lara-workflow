---
name: create-experiment-project
description: Initialize an experiment project's folders and LIB.md from its requirements and the workflow's file-structure specification. Use for setting up a study workspace and placing existing documents or source collections.
---

# Create Experiment Project

Apply the Coder perspective to project setup in Stage 3 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>). Use the Designer's supplied material requirements to choose the applicable organization.

## Establish the target and structure

Read [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) and inspect the target directory before modifying it. Resolve the specification relative to this skill's directory.

Use the requested project location, available design requirements, existing documents, and known source collections. If the intended study root is ambiguous, clarify it before creating or moving files. Keep the experiment project distinct from this reusable toolkit unless the user explicitly selects the toolkit directory for that purpose.

Determine which directories are needed now and which applicable directories should be reserved for later stages. Derive component, asset, and collection subfolders from the actual requirements. The example folder names in the specification do not establish component categories or result arrangements.

## Establish the project

- Create the applicable locations for the experiment, reusable asset templates, original sources, and prepared assets. Create tool and local-data locations when required by the study. Choose any data subfolders from the result-handling requirements.
- Place existing concept, design, or technical documents at their specified locations. Preserve their contents and update affected location references when relocation is part of the request.
- Bring supplied source collections into `sources/`, preserving their identities, contents, meaningful order, and file associations. Copy external sources when collecting them into the project unless the user has requested relocation.
- Reuse existing applicable directories. Inspect name collisions and resolve distinct conflicting files before replacement; rerunning initialization must preserve existing work.
- Reserve directories for later outputs without generating empty `CONCEPT.md`, `DESIGN.md`, `SCHEMATICS.md`, experiment code, or asset files that could be mistaken for completed artifacts.

Resolve source and destination paths before any relocation and confirm that they remain within the user-designated locations. On Windows, use literal paths and native file operations consistently. Preserve the content of relocated files; organizational changes do not authorize content revision or cleanup.

## Create the project map

Create or update `LIB.md` at the experiment root to describe actual files and directories using portable project-relative paths and concise roles. Preserve an existing map's established format where practical. An empty directory may be listed as an existing reserved location; a future file must not be presented as already present.

Use an actual directory listing to reconcile the map after operations. Keep this map specific to the experiment project rather than copying the toolkit repository's structure.

## Verify and deliver

Verify that the required directories and placed files exist, relocated or copied source contents are intact, affected references resolve, and `LIB.md` matches the resulting structure. Check file content with hashes when verifying byte-preserving copies or moves.

Return the project location, the map link, and a concise account of the created structure and placed materials. Broader organization of an existing collection can use `organize-project-files`; later-stage document and implementation content is created through the corresponding tasks.
