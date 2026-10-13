---
name: log-test-results
description: Record observed tool, experiment, human, and deployment test outcomes with reproducible context and evidence. Use to document actual runs, defects, corrections, and retests while distinguishing passing, failed, blocked, and unexecuted checks.
---

# Log Test Results

Apply the Coder perspective to technical evidence and the Designer perspective to supplied human observations across the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Identify the evidence

Read actual run outputs, observations, expected outcomes, execution context, and available correction or retest information. Use the existing project test records and naming conventions when present. A standalone logging request can use supplied evidence without generating other workflow documents.

Identify which artifact and environment each observation concerns. Distinguish direct execution evidence from a researcher or tester's report and identify the supplied source. Human test records document runs performed by the researcher and testers; this skill does not guide or organize those sessions.

Keep expected behavior separate from observed behavior. Link expectations to a requirement or explicit user decision. If a missing requirement or missing observation prevents judging an outcome, record the gap and seek the specific information needed. Never reconstruct an unreported result from implementation intent or the absence of an error report.

## Write usable records

Use the project's established format or a concise structured record suited to the supplied evidence. For each case or run, preserve the following information where available:

- Identify the tested artifact or version and the case or requirement, with the test date and evidence source when known.
- Describe the actual environment, configuration, setup, and inputs needed to interpret or reproduce the observation. Include the participant entry route or session identity when it connects the run to deployed results.
- State the expected outcome and its basis separately from the observed outcome.
- Record the outcome status and link the supporting logs, screenshots, result records, or supplied observations. Use actual evidence locations and preserve their connection to the tested version.
- For a defect, describe the reproducible discrepancy, affected behavior, and any known correction and retest references.

Mark unavailable information explicitly. The date of writing a record must not be presented as the date of an earlier run when that date is unknown. Preserve meaningful source wording when paraphrasing a tester's report would change its interpretation.

Use a passing status only when evidence supports the stated expectation within the tested scope. Record a failure when an executed check contradicts it. Record a blocked check when a known obstacle prevented execution or completion, and an unexecuted check when no run occurred. Incomplete evidence can leave an outcome undetermined; it supplies no passing result.

## Preserve history and assess coverage

Add correction and retest entries while retaining earlier observations. Connect each retest to the relevant defect and updated artifact. A claimed fix with no retest remains a correction awaiting verification. Keep outcomes for different versions, environments, and sessions distinguishable.

Summarize coverage using the cases and requirements actually represented in the records. Technical testing skills establish their test cases; supplied human observations establish human-test evidence. Logging does not execute tests or infer coverage of configurations absent from the evidence.

## Deliver

Save the record in the experiment project's established location or the requested destination, and update the existing `LIB.md` if the project map changes. Verify evidence references and consistency between individual outcomes and the summary. Return the record with a concise account of documented results and information still missing, without turning incomplete records into a release-readiness claim.
