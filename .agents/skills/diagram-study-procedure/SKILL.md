---
name: diagram-study-procedure
description: Create a diagram of a specified behavioral study procedure in SVG or another suitable requested format. Use to visualize entry, activities, sequence, branches, repetition, and completion while preserving design-defined relationships.
---

# Diagram Study Procedure

Apply the Designer perspective with Coder support for rendering when needed. Visualize the current or explicitly proposed procedure described by the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the procedure and view

Read the relevant procedure from `DESIGN.md`, supporting technical specifications, or equivalent explicit user requirements. Identify the requested scope, level of detail, audience, and output format. A diagram may cover the whole study or a specified component without depicting unrelated project stages.

Use [Design Doc Schematics.md](<../../../workflow-templates/Design Doc Schematics.md>) when locating overall sequencing, group differences, and component behavior in the design. Resolve the reference relative to this skill directory. Technical component containment and file organization do not, by themselves, establish chronological order.

Identify the entry, activities, transitions, and completion paths within scope, together with specified branching conditions, repetitions, group differences, and timing relationships. Clarify unresolved transitions or conflicting requirements before depicting them as established behavior. A requested proposed procedure can be visualized with its provisional status clearly identified.

## Construct the diagram

- Represent the actual activities and transitions using labels consistent with the source requirements. Select detail that supports the requested view without adding experimental steps.
- Label branches with the specified conditions and show their destinations and any subsequent convergence. Preserve distinctions among alternative routes, simultaneous activity, and successive steps when relevant.
- Represent repetition with its established count or stopping rule. Show variable ordering or selection as a rule or labeled structure so a single illustrated path does not imply a fixed order.
- Include timing relationships when they matter to the requested view. Use stated durations or constraints and avoid implying a time scale when layout spacing is only for readability.
- Distinguish grouping or condition-specific paths where required by the design. Use concise legends when symbols or visual conventions need explanation.

Use a diagramming or vector-rendering capability appropriate to the requested file format and follow its applicable instructions. When no format has been specified, SVG is a suitable default for a standalone procedure diagram. Produce the usable diagram file; source notation alone fulfills the request only when that is the requested output. Retain editable source when the chosen rendering process needs it for later revisions.

Keep the visualization focused on the study procedure. Asset inventories, component architecture, and development workflow stages belong in the diagram only when they are part of the requested view.

## Render and verify

Open the generated diagram through an available renderer and inspect its actual appearance. Check label legibility, text clipping, arrow direction, connector endpoints, overlaps, and whether branch labels can be associated with the correct paths. Adjust layout until the requested view is readable at its intended display or export size.

Trace each represented path against the source procedure, including exits and repetition boundaries. Confirm that simplifying the diagram has preserved sequence and decision meanings. Check the output file's syntax or renderability as appropriate. If rendering cannot be inspected, identify that limitation and do not claim visual verification.

## Deliver

Save the diagram and any needed editable source in the experiment project's established location or the requested destination. Update affected document links and the existing `LIB.md` when the project map changes. Return the diagram with a concise statement of its scope, source version, and verification. The visualization communicates the specified procedure; it does not establish that the experiment implements or successfully executes it.
