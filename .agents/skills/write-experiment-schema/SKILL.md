---
name: write-experiment-schema
description: Create or revise SCHEMATICS.md from an established experiment design. Specify components, execution rules, resource relationships, and data acquisition and delivery using the workflow's technical framework.
---

# Write Experiment Schema

Apply the Coder perspective to Stage 4 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>). Translate the design into precise technical behavior while preserving the researcher's experimental decisions.

## Read the framework and establish the requirements

Read [Framework Doc Schematics.md](<../../../workflow-templates/Framework Doc Schematics.md>) in full before writing. Its six-section framework, identifiers, record labels, conditional fields, and extension rules govern the output. Resolve this reference relative to the skill directory; use the current specification under `workflow-templates/`.

Read `DESIGN.md`, relevant supplied materials, and the user's instructions. Equivalent explicit design requirements can support a standalone schema request without first generating a design document. For revisions, inspect the existing schema and preserve established identifiers for units whose identity remains unchanged.

Consult all five official lab.js references linked in the framework and the relevant documentation or source needed to substantiate technical claims. Use accessible official alternatives for unavailable pages and check the specified target version when applicable. Verify recording behavior using the framework's additional data references when relevant. Examples provide implementation possibilities; their scientific content and settings do not become study requirements.

Resolve missing or conflicting experimental decisions with the researcher before finalizing dependent specifications. Keep questions in the conversation. The completed schema must contain actual technical requirements, with no invented values or unresolved-information placeholders.

## Translate the system

- Define the execution environment and relevant internal and external responsibilities.
- Decompose the design into components with coherent responsibilities and execution boundaries. Register each component once and provide its corresponding full record. Keep containment separate from execution order and preserve shared or repeated behavior through the framework's rules.
- Define entry, activation, transitions, coordination, and completion. For applicable control rules, specify scope, trigger, inputs, effect, and progression or termination. Make the required ordering, repetition, sampling, conditional, or concurrent behavior explicit.
- Specify each component's activation and inputs, operational steps, timing or progression, completion, and outputs. Identify when information becomes available and which component or rule consumes it.
- Identify materials and external capabilities using the framework's resource records. Reference supplied locations and existing template or asset files where available. Describe interactions at the system boundary without designing program interfaces.
- Define each required observation's meaning, producer, acquisition or calculation, measurement endpoints, units, recording event, and contextual associations. Specify delivery separately, including its trigger, destination, required organization, and completion behavior.

Use C, R, M, X, and D identifiers and the structural markers exactly as the framework defines them. They organize the specification and do not prescribe implementation identifiers. Keep source-file architecture, executable code, function signatures, storage fields, and asset schemas for their corresponding later tasks.

## Verify the specification

Check that component registration and full records correspond, containment is coherent, execution references resolve, and required information is available before it is consumed. Verify that shared rules and local behavior agree, measurement definitions remain faithful to the design, and material and delivery dependencies are connected to their use points.

Follow the exact section order, headings, record labels, and allowed extensions. Retain empty containing sections as the framework requires and remove instructional placeholder text. Keep review findings and technical-source access limitations outside `SCHEMATICS.md`; unresolved limitations affecting required behavior must be addressed before the affected specification is finalized.

## Save and deliver

Save `SCHEMATICS.md` at the established experiment root or the explicitly requested destination. Resolve an ambiguous study destination before writing. Update the existing `LIB.md` when adding or changing the document's location.

Return the saved document link with a brief delivery message. Keep the output at the level required for implementation from the schema and its referenced materials, without requiring the implementer to reconstruct operational rules from the design narrative.
