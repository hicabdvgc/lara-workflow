---
name: design-supporting-tools
description: Design supporting tools required before, during, or after experiment execution. Use to define tool responsibilities, interfaces, processing behavior, integration points, and verification criteria before implementation.
---

# Design Supporting Tools

Apply the Coder perspective to tool design in Stage 6 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the required operation

Read the requested supporting operation, relevant `DESIGN.md` and `SCHEMATICS.md` content, supplied data formats, external constraints, and execution requirements. Explicit user requirements can supply this context when no project documents exist.

Identify the capability the tool must provide and where it fits before, during, or after the experiment. Keep its responsibility aligned with the existing system boundary. Clarify ambiguities affecting required behavior, scientific meaning, or interaction with an external system before designing the dependent operation.

Use [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) for the separation between `tools/` and `experiment/`. Resolve that reference relative to the skill directory. Select technical arrangements appropriate to the operation; a supporting tool need not be a service or use a network interface.

## Define an implementable design

Describe the following at the detail needed to implement the actual tool:

- **Responsibility and invocation:** State its operation, caller or operator, triggering point, execution setting, and completion condition.
- **Inputs:** Define sources, required formats and fields, meanings, units, accepted values, and applicable validation requirements.
- **Processing:** Specify the transformations, calculations, or coordination needed to produce the required result. Preserve source identities and relationships where they matter to the operation.
- **Outputs and effects:** Define produced information, formats, destinations, effects on existing files or records, and how completion or a relevant failure is communicated. Specify repeat-invocation behavior when repeated calls affect those outputs or effects.
- **Interfaces and integration:** Define the actual invocation and exchange contract needed by the caller or consumer. Preserve externally imposed interfaces and identify how results affect experiment progression when applicable.
- **Implementation approach:** Select the required language, runtime, dependencies, and code organization according to the environment and operation. Explain consequential technical choices and verify uncertain APIs or compatibility against official sources.
- **Verification:** Identify representative inputs and expected outputs derived from the requirements, plus the boundary or failure cases implied by the defined input and interaction rules.

Concrete interfaces and data representations belong in this tool design when they are needed for implementation. Keep `SCHEMATICS.md` at its specified behavioral level and preserve its externally visible requirements.

Avoid adding unrelated capabilities or turning a simple local transformation into a larger system without a requirement. Technical choices within the established behavior can be resolved directly; changes to experimental decisions require the researcher.

## Check and deliver

Check that inputs support the proposed processing, outputs satisfy their consumers, execution dependencies are available at invocation, and completion behavior is defined. Ensure verification expectations describe required behavior rather than merely restating the proposed code.

Deliver the implementation-ready design in the user's requested form. If a project file is requested, use its established location or the relevant tool directory and update the existing `LIB.md`. Do not generate empty implementation files as part of a design-only task.

The main experiment's architecture is a separate scope. This design provides the inputs for `build-supporting-tools`, and its integration requirements also inform later experiment building and end-to-end testing.
