---
name: package-production-experiment
description: Produce a release-ready experiment file or package for the selected deployment target. Use to assemble the tested implementation, assets, tools, dependencies, configuration, instructions, and release verification evidence.
---

# Package Production Experiment

Apply the Coder perspective to Stage 10 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the release inputs and target

Read the tested experiment, required assets and supporting tools, applicable test results, selected deployment setting, and required deliverable format. Identify the exact implementation and configuration that the evidence covers.

Review supplied human test outcomes when assessing completion of the full workflow. Human testing is performed by the researcher and testers; absent outcomes must not be inferred from technical runs. A packaging request can still produce the requested artifact while identifying verification that remains outstanding.

Clarify an unspecified target or output form when it changes what must be packaged. The deliverable can be a single experiment file or a multi-file package, according to the actual runtime and host requirements. Verify target-specific formats and compatibility against applicable official documentation, including JATOS when selected.

Use [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) to locate the source implementation, assets, and tools. Resolve the reference relative to this skill's directory. Establish the intended release destination without treating the toolkit repository as the experiment project.

## Assemble the release

- Build or export from the identified implementation using the established process. Record the release identity and the source version or other identifier needed to associate it with test evidence.
- Include required runtime assets, tool deliverables, dependencies, and configuration while preserving expected paths and interfaces. Keep external requirements explicit when they must be supplied by the target environment.
- Preserve the implemented scientific content, execution rules, response meanings, measurements, and result-handling behavior during bundling or export. Recheck affected behavior when the release process transforms executable content or assets.
- Select package contents according to the runtime and operational requirements. Keep original sources and retained evidence in the development project when they are not part of the runtime package. Do not include collected participant records or incidental test outputs merely because they share the project directory.
- Keep environment-specific access values in their appropriate deployment configuration. Supply configuration instructions without distributing unrelated local settings or credentials.
- Produce the requested file or archive, with instructions for dependencies, configuration, launch or deployment, successful completion, and result retrieval in each selected setting.

The package must not depend on unnoticed files elsewhere in the development checkout. Identify intentional remote resources or services and their configuration so the operator can satisfy those dependencies.

## Verify the actual artifact

Inspect the packaged contents and launch the release artifact through its supplied instructions in an appropriate clean or isolated location. For an archive, exercise an extracted copy. Check that assets and required connections resolve without relying on the development working directory.

Run a complete session through result delivery and retrieval, using the relevant end-to-end testing capability where available. Exercise additional paths affected by packaging or target-specific changes and compare the results with the required behavior. Record the actual release artifact, environment, and outcomes tested.

If the intended environment or an external dependency is unavailable, state precisely what was verified and what remains outstanding. Successful packaging or local inspection does not establish installation or execution on the final host.

## Deliver

Return the release file or package, its release identity, run or deployment instructions, and applicable verification evidence. Update the existing `LIB.md` for the release location when it belongs in the project map.

Describe the artifact as production-ready only to the extent supported by the required tests and environment checks. Local and online deployment tasks establish the release in their target environments and supply their own verification outcomes.
