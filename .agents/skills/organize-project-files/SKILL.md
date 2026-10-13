---
name: organize-project-files
description: Organize, relocate, or rename experiment project files while preserving source content, associations, references, and LIB.md. Use for restructuring existing source collections or technical project files.
---

# Organize Project Files

Apply the Designer perspective to source collections and the Coder perspective to technical files. Support Stage 3 and subsequent organizational changes in the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Inspect the current organization

Read [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>), the existing `LIB.md` when present, and the requested organizational requirements. Resolve the specification relative to this skill's directory.

Inventory the files in scope and identify their roles and relationships from actual contents, manifests, references, and design requirements. Distinguish original sources, reusable asset structures, prepared assets, implementation files, tools, and result records. Do not infer experimental grouping, order, or item identity solely from an ambiguous filename.

Use the intended study root and the user's named locations. Clarify uncertain destinations, identities, or organization rules before applying changes that depend on them. A narrowly scoped collection can be organized without building the rest of the project.

## Plan and apply the changes

1. Establish an old-to-new path mapping for the required moves or renames. Account for related files and directory-relative links together.
2. Inspect destination collisions, including case-only differences on filesystems where they matter. Resolve competing files without overwriting distinct content or inventing new scientific identifiers.
3. Locate affected references in the relevant documents, manifests, asset collections, and implementation. Determine how each path is resolved before changing it; relative paths, project-root paths, and runtime URLs may use different bases.
4. Move or rename the authorized files using resolved paths within the intended locations. Use native literal-path operations on Windows. Keep file contents unchanged except for the identified reference updates needed by the organization.
5. Update affected references and reconcile `LIB.md` with the resulting structure. Create the map when organizing the experiment project requires one and it is absent.

Preserve source provenance, item associations, meaningful sequence, and intentional repetitions. Keep the path mapping available through verification so the original and final identities can be reconciled. Similar content or repeated use is not sufficient reason to merge or delete files.

## Verify the organization

Check that every intended destination exists and that files subjected only to moves or renames retain their contents, using hashes where appropriate. Inspect reference edits separately and verify links against their actual resolution base. Preserve filename case required by the deployment environment.

When executable references are affected, run the relevant existing loading or execution check to verify that the moved resources remain usable. If a reference cannot be verified with the available files or environment, report that specific limitation; do not claim the whole project has been tested.

Reconcile `LIB.md` with the final inventory. Return the changed locations, significant reference updates, and verification outcome. Formatting materials, changing scientific content, screening items, and deleting redundant files belong to their corresponding tasks.
