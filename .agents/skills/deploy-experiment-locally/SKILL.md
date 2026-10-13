---
name: deploy-experiment-locally
description: Install, configure, and verify a released behavioral experiment on its intended local equipment. Use for local setup, repeatable operator launch, supporting-service connections, and result retrieval.
---

# Deploy Experiment Locally

Apply the Coder perspective to Stage 11 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the target setup

Read the release artifact and its instructions, target equipment and runtime requirements, required supporting services, and result destinations. Use relevant `DESIGN.md` and `SCHEMATICS.md` requirements or equivalent explicit user requirements. Identify the release version and the local equipment actually accessible for deployment.

Resolve missing target or configuration details when they affect installation, execution, or result handling. A local deployment may use network services. Treat offline operation as a requirement only when the study specifies it.

Use [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) when locating project files or recording deployment outputs. Resolve this reference relative to the skill directory. Keep the experiment's deployment destination distinct from this workflow toolkit's repository.

## Install and configure

- Place or extract the identified release on the intended equipment, preserving asset paths and required supporting-tool files. Identify any existing installation before replacing files so unrelated studies and collected results remain intact.
- Install or configure the runtime and dependencies required by the release. Verify uncertain commands, interfaces, and version compatibility against official documentation for the actual software in use.
- Configure the specified connections, result destination, and equipment-dependent settings. Preserve scientific content, response mappings, measurements, timing requirements, and session rules.
- Start the runtime and supporting services in their required order. Use the release's intended launch mechanism and record any working-directory or configuration dependencies needed to repeat it.
- Reflect necessary technical configuration changes in the applicable deployment instructions and technical specification. Resolve any change to experimental behavior with the researcher before implementing it.

Use the deployment access and scope already authorized by the user. When the target equipment is unavailable, prepare the requested setup files and instructions and identify the remaining installation and execution checks accurately.

## Verify on the equipment

Use [test-experiment-end-to-end](../test-experiment-end-to-end/SKILL.md) to run a complete session on the actual local setup. Confirm that assets load, the intended input devices work, supporting services participate as specified, and the session reaches completion.

Inspect the resulting records at the configured destination. Check their values and organization against the expected session, then exercise the operator's retrieval procedure. Verify that another session can be launched through the documented procedure and that its result handling follows the design.

When offline operation is required, exercise the required procedure without network access in the intended test environment. Record the condition actually tested. Verification on another computer or with remote services available establishes only that tested configuration.

Record the release, equipment, runtime, configuration, session inputs, expected and observed results, and evidence locations. Use `log-test-results` if available; otherwise preserve these details in the project's existing test records. Report failed, blocked, and unexecuted checks separately from passes. Retest affected execution and retrieval paths after corrections.

## Deliver

Provide the installation location, operator instructions for starting required services and sessions, completion indicators, and result-retrieval steps. Include verification evidence and any remaining limitations. Update the existing `LIB.md` when deployment artifacts change the project map. Claim a functioning local deployment only when execution and result retrieval have been observed on the intended setup.
