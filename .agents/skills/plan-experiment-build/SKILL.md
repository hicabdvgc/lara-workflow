---
name: plan-experiment-build
description: Plan the implementation architecture and technical approach for a lab.js experiment. Use to choose component mappings, code organization, interfaces, asset and state handling, dependencies, and a build and verification strategy.
---

# Plan Experiment Build

Apply the Coder perspective to implementation planning for Stage 7 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the implementation basis

Read the design, technical specification, asset formats, supporting-tool contracts, and intended execution and deployment settings. Inspect existing code and project conventions when extending an experiment. Equivalent explicit requirements can support planning without generating missing upstream documents solely for this task.

Read [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) for the separation of experiment code, assets, and tools. Use [Framework Doc Schematics.md](<../../../workflow-templates/Framework Doc Schematics.md>) when interpreting the schema's behavioral responsibilities and identifiers. Resolve these references relative to this skill's directory.

Preserve experimental decisions and externally imposed constraints. Clarify contradictions or missing requirements that affect scientific behavior. Resolve internal coding choices directly when they preserve the specified behavior.

## Choose the technical approach

- Map each specified responsibility and control rule to suitable lab.js facilities or necessary custom code. Preserve the distinction between document components and library classes; their relationship follows the required behavior.
- Select the applicable lab.js version and implementation route within the user's constraints. Consult official documentation, source, and relevant examples to verify capabilities and compatibility. Identify the versions on which technical decisions depend.
- Define source organization, the entry point, component interfaces, state ownership and lifetime, and the information passed between units.
- Define how prepared assets are located, loaded, and made available before use, preserving their identities and associations. Address presentation and input requirements relevant to the target devices and execution setting.
- Map observation acquisition, calculations, recording, and delivery to the implementation. Preserve measurement reference events, units, recording detail, and the distinction between experiment completion and result delivery where required.
- Define connections to supporting tools and services through their established interfaces. Keep tool implementations under `tools/` and main experiment code under `experiment/`.
- Identify runtime and build dependencies, configuration, and the procedure for producing the required executable or development build. Account for the selected deployment target's actual requirements.

Compare alternatives when the choice materially affects the requirements, maintenance of the proposed implementation, or execution behavior. Avoid introducing infrastructure merely because it is available. Document the selected approach and the consequential reasons for it.

## Resolve technical uncertainty

Use focused documentation checks or small capability probes when needed to establish whether an approach works in the intended environment. Keep probe artifacts separate from the actual experiment and identify what was observed. A successful isolated probe supports the tested capability, without establishing complete experiment behavior.

If a technical limitation would change experimental content, timing, measurements, or procedure, return that decision to the researcher. Distinguish verified technical choices from unresolved dependencies in the plan.

## Deliver the implementation plan

Provide a concrete plan in the requested form, covering architecture, selected dependencies, interfaces, integration, build order, and verification. Map implementation work to the relevant schema identifiers when present. Define expected verification outcomes from the requirements, including the required complete-session and result-delivery paths.

Keep implementation-level choices in the plan; preserve the schema's specified abstraction level. Save a plan file at the established or requested location when a file is requested, and update the existing `LIB.md` for new locations.

Check that every required technical responsibility has an implementation approach and that dependencies can be satisfied in the chosen order. Hand the plan to experiment implementation. Planning alone does not produce a tested experiment.
