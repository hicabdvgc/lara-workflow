---
name: build-supporting-tools
description: Implement and verify experiment-supporting tools from a tool design or explicit requirements. Use to create working tools under tools/, supply their dependencies and run instructions, and test input-to-output behavior.
---

# Build Supporting Tools

Apply the Coder perspective to tool creation and verification in Stage 6 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Read the requirements and environment

Read the tool design or equivalent explicit requirements, relevant experiment interfaces, representative inputs, and the existing project code and configuration. Inspect a supplied implementation before changing it.

Identify the required operation, accepted inputs, outputs and effects, invocation, and completion behavior. Resolve missing behavioral choices with the researcher or user before implementing dependent functionality. Use `design-supporting-tools` when needed design work is part of the request; a separate design document is unnecessary when the requirements already determine the operation.

Read [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) for the tool's project location and encapsulation requirements. Resolve that reference relative to this skill's directory. Establish the intended experiment root before writing files.

## Implement the tool

- Implement the required capability under its own directory in the experiment's `tools/`. Keep its implementation separate from `experiment/` and connect it through the defined interface.
- Use the selected runtime and libraries, reusing suitable existing project conventions. Verify uncertain API behavior, dependency compatibility, and external interfaces against applicable official sources before relying on them.
- Implement the specified input handling, processing, outputs, effects, and completion behavior. Preserve units, content meanings, record identities, and associations required by the design.
- Handle invalid inputs and interaction failures according to the defined contract and actual requirements. Keep changes to existing files or records within the intended operation and destination.
- Include the dependencies and configuration needed to run the tool reproducibly in the target environment. Keep machine-specific paths or access values in the appropriate runtime configuration rather than embedding them in reusable code.
- Provide the operational instructions appropriate to the tool: how to prepare its environment, invoke it, provide inputs, and locate or receive outputs. Describe required external services or access only when the tool uses them.

Keep implementation proportional to the requested operation. Tool creation does not authorize building unrelated experiment components, deploying services, or changing the scientific procedure.

## Verify actual behavior

Execute the tool through its intended entry point with representative inputs. Compare observed outputs and effects with expectations derived from the requirements. Inspect the resulting files, records, or return values, including their formats and associations where relevant.

Exercise the relevant boundary and failure cases established by the contract, and verify repeat invocation when its effects matter. Run tests in an appropriate isolated location when the operation writes files or records so test outputs remain distinguishable from study materials and collected results.

Use the defined caller or an appropriate test caller to check the tool's exchange contract. If an external dependency is simulated, identify that fact and the integration that remains unverified. Report an unavailable required service or environment accurately; simulated responses do not establish a working external connection.

Correct observed defects and retest the affected behavior. Record the tool version or artifact, invocation, inputs, expected and observed results, and any remaining verification limits in the project's existing test-record format or a concise test report. The later logging skill may organize this evidence when available; creating this tool does not depend on that skill being installed.

## Deliver

Deliver the working tool, required dependency and configuration files, operational instructions, and test evidence. Update the existing `LIB.md` for added or changed tool locations. State any unverified requirement explicitly instead of claiming full completion from code creation alone.

Tool-level verification establishes the tool's own behavior and exchange contract. Its interactions with the complete experiment are also exercised during integrated experiment testing.
