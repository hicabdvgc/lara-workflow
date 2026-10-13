---
name: revise-code
description: Correct or change existing behavioral experiment or supporting-tool code. Use for implementation defects and requested behavior changes that require preserving study requirements, interfaces, and unaffected behavior and verifying the affected execution paths.
---

# Revise Code

Apply the Coder perspective to implementation revisions throughout the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the intended behavior

Read the requested change or defect report, relevant code, design and technical requirements, and available test evidence. Locate the implementation actually used by the affected experiment or tool, including its build or export process when generated files are involved. Equivalent explicit user requirements can support a standalone correction.

Trace the observed behavior to its inputs, component or tool responsibilities, interfaces, and outputs. Reproduce a reported defect when the environment and evidence permit. If reproduction is unavailable, distinguish the supplied observation from what code inspection establishes.

Resolve ambiguity that affects scientific content, conditions, timing, response meanings, or measurements with the researcher before dependent changes. Implement an explicit researcher decision without requesting it again, and reflect the decision in the relevant design documentation. A technical failure alone does not supply a new experimental rule.

## Make the scoped change

- Identify the code and necessary callers or consumers affected by the change. Preserve unrelated user edits and existing project organization.
- Correct the responsible source and regenerate derived deliverables through the established process when necessary. Keep source and delivered behavior consistent.
- Preserve defined interfaces, asset identities, result fields and meanings, supporting-tool boundaries, and unaffected session behavior. If the requested change alters an interface, update its required producers, consumers, and documentation together.
- Verify relevant lab.js, host, runtime, or dependency APIs and version compatibility against applicable official documentation or source. Use the project's established dependencies and technical route unless the requested change requires otherwise.
- Keep implementation choices within the established scientific requirements. Route accompanying content or media edits through the corresponding revision capability when needed.

Update `SCHEMATICS.md` when the change alters its technical statements, using the relevant structure in [Framework Doc Schematics.md](<../../../workflow-templates/Framework Doc Schematics.md>). Resolve the reference relative to this skill directory. Update affected run instructions, file references, and the existing `LIB.md` when their information changes.

## Verify the correction

Choose checks from the changed requirement and its connected behavior. Run the affected component or tool with meaningful inputs and compare actual outputs with expected results. Exercise the integration paths that consume the changed behavior, including result delivery when affected. Use [test-experiment-end-to-end](../test-experiment-end-to-end/SKILL.md) or [test-online-deployment](../test-online-deployment/SKILL.md) when the revision requires those scopes.

For a reproduced defect, confirm that the original failing case now satisfies its requirement. Add a regression test when it meaningfully protects the corrected behavior within the existing test setup. Do not treat a syntax check as evidence of successful participant execution or stored results.

Record the tested version, inputs, expected and actual outcomes, and remaining limitations with [log-test-results](../log-test-results/SKILL.md). Preserve the earlier failure and connect it to the correction and retest. Human observations remain supplied by the researcher or testers.

## Deliver

Return the changed files, a concise explanation of the resulting behavior, and relevant verification evidence. Identify unresolved failures or unavailable checks accurately. Technical tests establish implementation behavior within their coverage; scientific changes remain governed by the researcher's decisions.
