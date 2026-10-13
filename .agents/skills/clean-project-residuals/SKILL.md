---
name: clean-project-residuals
description: Remove or consolidate verified residual and redundant experiment files within the user's cleanup scope. Use to clean a project while preserving required sources, material identities, runtime dependencies, results, and test evidence.
---

# Clean Project Residuals

Apply the Coder perspective to project cleanup, including release preparation in Stage 10 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>). Use the Designer's established material relationships when assessing source collections.

## Establish the scope and dependencies

Read the user's cleanup request, the actual project inventory, `LIB.md` when present, and the relevant build, runtime, and asset references. Use [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) to distinguish sources, templates, assets, implementation, tools, and data. Resolve the reference relative to this skill's directory.

Identify the intended project root and which classes of files the request covers. Inspect candidate contents and their producers and consumers. Check indirect dependencies such as dynamically constructed asset paths, collection manifests, build inputs, and externally referenced exports when relevant to a candidate.

## Establish removability

For each candidate, determine why it is removable within the requested scope: for example, a confirmed temporary output from a completed operation or a superseded generated artifact whose required replacement and regeneration path are established.

Preserve needed original materials, distinct item identities, intentional stimulus repetitions, runtime and build dependencies, collected study data, and required test evidence. A name, age, matching hash, or lack of an obvious direct reference does not by itself establish that an item can be removed.

Consolidate files only when their separate identities and paths have no required meaning and the affected references can be maintained. If a candidate's purpose or authority for removal remains ambiguous, ask about that candidate and continue with independently verified cleanup. A clear cleanup request authorizes the identified removals within its scope; avoid repeated confirmation of already-established choices.

## Apply bounded changes

- Keep a concrete list of the exact paths to remove or consolidate and the reason for each action.
- Resolve the final absolute targets before deletion or relocation and verify that they remain inside the intended workspace or explicitly named directory. Account for symbolic links or reparse points when they affect the actual target.
- On Windows, use native PowerShell operations with literal paths throughout. Inspect recursive targets before removal and avoid passing computed deletion commands between shells.
- Apply changes to the verified targets. Update references affected by consolidation, preserving each reference's path-resolution semantics.
- Update `LIB.md` to reflect the actual remaining files and locations. Preserve unrelated project content and repository metadata.

Project cleanup changes the working project. Excluding a development-only file from a release package can be handled during packaging without deleting the project copy.

## Verify and report

Confirm that only the intended items were removed or consolidated. Check affected references and run the relevant existing build, loading, or execution checks when the cleanup touches their dependencies. Preserve evidence needed to assess the cleanup result.

Return a concise record of changed paths, their removability basis, verification performed, and any candidates left unresolved. Do not equate a smaller directory or successful deletion command with a verified working experiment.
