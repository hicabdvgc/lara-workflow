---
name: test-experiment-end-to-end
description: Test complete experiment sessions against the design, including branches, repeated runs, supporting tools, measurements, and result delivery. Use for technical verification of development builds and local deployments.
---

# Test Experiment End to End

Apply the Coder perspective to Stage 8 and local execution verification in the [experiment workflow](<../../../Behavioral Experiment Workflow.md>). Use design-defined expectations supplied by the researcher or Designer.

## Establish the test basis

Read the runnable experiment's launch instructions, design and technical requirements, required environments, and relevant earlier test records. Identify the artifact or version being tested and its actual configuration.

Define cases from the required behavior, independently of the current implementation. Cover applicable completion paths, screening and allocation outcomes, branches, repetitions, response meanings, measurements, supporting-tool exchanges, and data destinations. Derive expected results from specified rules and known test inputs.

Clarify absent expected behavior when it prevents a meaningful judgment. Do not change the experiment's acceptance criteria to make a test pass. Use representative test sessions and destinations that are distinguishable from actual participant records.

## Execute complete sessions

- Launch through the intended entry point in the required execution environment. Inspect actual presentation and interact with the participant interface using available browser or execution tools.
- Exercise the applicable paths through their real transitions. Test setup may establish a specified initial condition, but identify any bypassed behavior and do not count it as covered.
- Compare content, asset loading, instructions, input handling, progression, and completion with the requirements. Observe relevant runtime failures and supporting-tool interactions.
- Inspect recorded observations, units, calculations, occurrence context, and associations using the known test inputs. Follow delivery through to the specified output or destination; a completion screen alone does not establish successful recording or delivery.
- Repeat sessions when required to exercise allocation, sampling, randomization, counterbalancing, or other cross-session rules. Check design-defined invariants and record the relevant conditions. Random variation alone does not establish correctness, and independent random draws need not yield exact balance unless the design requires it.
- Exercise the device, browser, and local execution configurations required by the study within the available environment. Identify configurations that were not exercised.

Inspect code or intermediate records when needed to diagnose discrepancies, while preserving the distinction between source inspection and executed behavior. A mocked service establishes the simulated exchange only; it does not verify the real connection.

## Interpret timing and coverage accurately

Verify measurement definitions, reference events, units, and recorded software behavior using available evidence. Browser events and timestamps do not establish physical display, sound, or input latency when the requirement calls for external measurement. Identify that unverified requirement instead of inferring it from a configured duration.

AI-driven technical sessions are not human test rounds. Findings about human comprehension or participant experience require actual human observations supplied by the researcher or testers. Hosting-specific online verification belongs to the online-deployment testing task.

## Record findings and retests

For each case, record the requirement, artifact, environment, setup and inputs, expected outcome, observed outcome, and evidence. Distinguish passed, failed, blocked, and unexecuted cases. Include reproducible steps and affected records for defects.

Use `log-test-results` when available, or the existing project test-record format or a concise report when that skill is not yet installed. Preserve earlier findings when adding correction and retest results. If fixing defects is part of the request, correct them and rerun the affected cases and connected paths; a test-only request produces findings without silently changing the experiment.

Return the observed results and a coverage account. Declare only the requirements actually verified as passing and identify any remaining issue that prevents the requested complete-session or data-delivery outcome.
