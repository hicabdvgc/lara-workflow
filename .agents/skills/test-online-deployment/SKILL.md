---
name: test-online-deployment
description: Test a behavioral experiment through its actual deployed participant entry point. Use to verify online session behavior, hosting integration, result submission, storage, and retrieval on JATOS or another selected host.
---

# Test Online Deployment

Apply the Coder perspective, using the Designer's study-level expectations, to Stage 11 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the deployed test scope

Read the deployed participant entry information, release identity, hosting configuration, required device and browser configurations, and expected session and result behavior. Use `DESIGN.md`, `SCHEMATICS.md`, previous test evidence, or equivalent explicit requirements to determine expected outcomes.

Reuse the relevant study-level checks from [test-experiment-end-to-end](../test-experiment-end-to-end/SKILL.md). Add the checks needed for actual online entry, hosting integration, and result handling. Select cases that cover required branches and behavior spanning sessions without introducing new experimental conditions or arbitrary test quantities.

Establish how test sessions can be recognized in the target environment using its existing configuration and study requirements. Account for their effect on shared allocation or session state when such behavior is part of the design. Keep test evidence identifiable; do not delete stored results or reset shared state merely to tidy the test run.

Verify uncertain host APIs, state meanings, and result-retrieval mechanisms against official documentation for the version in use. Lack of access to a required device, host function, or stored result is a verification limitation to record.

## Exercise actual online sessions

- Enter through the deployed participant route using the intended access mechanism. An editor preview, local copy, or administrator-only launch covers its own path and cannot establish the participant route's behavior.
- Confirm that the intended release loads and that assets, supporting services, and host initialization work in the tested browser and device configuration.
- Complete the specified procedure through its branches, interactions, and completion paths. Check that host integration preserves the expected content, response handling, measurements, and transitions.
- Observe result submission and host-side session completion. Retrieve the corresponding stored results through the operator's actual retrieval mechanism and compare their content and organization with the expected records. A completion screen or successful request alone does not establish retrievable results.
- Run the distinct or repeated sessions needed for specified allocation, sampling, counterbalancing, or result organization. Check which information persists or changes between sessions according to the design. Reuse session identity only where the required procedure calls for it.
- Exercise interruption, re-entry, or other lifecycle behavior when required by the study or relevant to an observed defect. Judge it against established requirements; clarify unspecified behavior before changing it.

Test each required environment that is available and state the actual coverage. Browser emulation and scripted interaction do not establish behavior on physical equipment that was never exercised.

## Record findings and retests

Use `log-test-results` when available. Otherwise record the deployed release and entry route, host, device and browser, case, session identifiers, inputs, expected and actual outcomes, status, and evidence in the project's test records. Keep result references sufficient to connect the observed session to its retrieved data.

Distinguish confirmed defects, blocked checks, and unexecuted cases. For failures, preserve reproduction details and identify the affected requirement and deployment or implementation area. After corrections, retest the failing behavior and connected paths against the updated deployment, retaining the earlier evidence.

## Deliver

Return the online verification record, deployment-specific defects, and a precise account of passing and outstanding requirements and configurations. Human test observations remain supplied by the researcher or testers. Claim verified online execution only where the actual deployed procedure and required result retrieval were exercised successfully.
