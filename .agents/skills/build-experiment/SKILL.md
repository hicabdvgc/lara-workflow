---
name: build-experiment
description: Build and integrate a runnable lab.js experiment from its design, technical requirements, assets, and supporting tools. Use to implement the complete participant procedure and data handling under experiment/.
---

# Build Experiment

Apply the Coder perspective to Stage 7 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Read the requirements and project

Read the established design and technical requirements, implementation plan when available, prepared assets, and required tool interfaces. Inspect existing implementation files and configuration before extending or replacing them. Identify the intended experiment project root; this reusable toolkit is not automatically the study's output location.

Use [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) for output locations and tool separation. Refer to [Framework Doc Schematics.md](<../../../workflow-templates/Framework Doc Schematics.md>) when interpreting schema records. Resolve these references relative to the skill directory.

Equivalent explicit requirements can support a build from scratch. Resolve ambiguities that affect experimental behavior before implementing dependent functionality. Develop necessary internal architecture choices within the supplied requirements, using `plan-experiment-build` when that planning work is needed.

## Implement the specified experiment

- Implement the entry point and component behavior under `experiment/`, using the selected lab.js version and project conventions. Verify uncertain library APIs, behavior, and compatibility against official documentation or source.
- Translate execution rules into the required activation, ordering, repetition, branching, sampling, coordination, and completion behavior. Preserve scope and information dependencies across component occurrences.
- Integrate prepared assets with the specified content, presentation, loading, and response behavior. Preserve identities, associations, quantities, fixed wording, and instruction placement.
- Implement timing, response interpretation, measurements, and derived results according to the specified reference events, units, and calculation rules. Align recorded context with the observation's origin.
- Implement result recording and delivery, including the required destination, format, trigger, and completion behavior. Account for the selected runtime or hosting interface when one has been specified.
- Connect required supporting tools through their defined interfaces while keeping their implementations separate under `tools/`. Identify unavailable dependencies explicitly; temporary substitutes must not be presented as completed integrations.
- Supply the runtime configuration, dependencies, and instructions required to launch the development build and locate its test results.

Use actual prepared content for the integrated experiment. Missing scientific materials or values require resolution; invented stimuli, silent content substitutions, and arbitrary defaults must not become the delivered study. Test fixtures used during development must remain distinguishable from its real materials.

## Check components and integration

Exercise relevant components as they are implemented, then run the assembled procedure through its entry point. Check that the specified branches can be reached with appropriate inputs and that connected units exchange information when required.

Inspect resulting records and verify the implemented delivery path. Diagnose observed failures, correct the affected code, and rerun the relevant checks. Use test outputs that remain distinguishable from actual participant data.

Keep verification statements proportional to the work performed. A loadable page establishes less than a completed session; a completed session covers the path actually exercised. Comprehensive technical testing follows through `test-experiment-end-to-end`. Human testing remains the researcher's and testers' responsibility.

## Deliver the runnable build

Return the entry point, required configuration and launch instructions, component or integration checks performed, and any unresolved implementation requirements. Update the existing `LIB.md` for added or changed project locations.

The build is complete when the specified procedure is runnable from entry through completion and its required paths are available for testing. Packaging and deployment have separate verification outcomes; do not equate development execution with a verified production release.
