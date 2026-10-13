---
name: review-experiment-consistency
description: Review correspondence among study requirements, documents, materials, code, and test evidence. Use to identify contradictions, omissions, broken associations, or downstream effects within a requested subset of experiment artifacts.
---

# Review Experiment Consistency

Apply the Designer perspective to experimental meaning and the Coder perspective to implementation correspondence. Use the Conceptualizer perspective when the study purpose is affected. Follow the requirements and revision rules in the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the review scope and authority

Read the requested review scope, current user decisions, and relevant available artifacts. These can include `CONCEPT.md`, `DESIGN.md`, `SCHEMATICS.md`, `LIB.md`, sources, prepared materials, code, deployment configuration, and test evidence. Review the subset needed for the question; a local comparison does not require a full-project audit.

Identify the versions being compared and the authoritative requirement for each issue. The design governs experimental behavior, while the technical specification describes its implementation. Explicit user decisions can establish a change whose downstream artifacts still need revision. Do not select a conflicting requirement merely because it agrees with the current code.

For structural questions, consult the corresponding resource under [workflow-templates](../../../workflow-templates/) and resolve it relative to this skill directory. Equivalent explicit requirements can support review when upstream documents are absent. Distinguish an unavailable artifact from evidence of a missing requirement in an artifact that was inspected.

## Trace the relevant requirements

Follow each in-scope requirement through its available representations and consumers. Preserve the distinction between experimental meaning, technical organization, chronological execution, and observed test behavior.

- Compare specified procedure, conditions, branches, repetition, timing, and completion with the relevant component descriptions and implementation paths.
- Trace content identities, quantities, labels, meaningful order, and media associations from source to prepared asset and consumer where those relationships are in scope.
- Compare measurement meanings, units, reference events, calculations, recording, and result destinations across the governing requirements and corresponding implementation.
- Check concrete file references, interfaces, and the project map where the reviewed change affects them.
- Relate test evidence to the specific artifact, environment, and behavior it exercised. Identify when existing evidence predates a relevant change or leaves a required path untested.

For a proposed or completed change, identify the documents, materials, code, configuration, and verification paths that depend on it. Trace actual references and responsibilities rather than assuming every project file needs revision.

Verify uncertain technical claims against official documentation or source appropriate to the project's versions. Code correspondence can support a static finding, while runtime and deployment claims require applicable execution evidence.

## Report actionable findings

For each confirmed discrepancy, identify the governing requirement, exact conflicting locations or evidence, practical consequence, and affected artifacts. Describe the decision, revision, or test needed to resolve it. Separate confirmed findings from unresolved design questions and limitations caused by unavailable evidence.

Keep proposals identifiable. A consistency review does not silently resolve scientific disagreements or modify reviewed artifacts. Apply fixes only when the user's request also authorizes revisions, using the corresponding revision capability and relevant verification.

## Deliver

Return an evidence-based review in the requested form, with the scope and versions inspected, actionable findings, and remaining questions or unverified relationships. If no discrepancies are found, state that conclusion within the inspected scope. Do not equate static consistency with successful execution, human comprehension, or verified deployment.
