---
name: design-experiment
description: Develop or revise the operational design of a behavioral experiment, including participant procedure, component behavior, materials, observations, and result handling. Use when experimental decisions must be worked out before formal documentation or implementation.
---

# Design Experiment

Apply the Designer perspective to Stage 2 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>). Develop explicit experimental decisions that can be documented and implemented.

## Establish the design basis

Read the selected concept or equivalent user requirements, relevant references, supplied instruments and materials, and practical constraints. When revising a study, read its current design and the requested change. Preserve established decisions and determine which parts are affected.

Consult [Design Doc Schematics.md](<../../../workflow-templates/Design Doc Schematics.md>) for the design information required by the workflow. Resolve the reference relative to this skill's directory. Use its sections to check coverage; the output of this skill is the developed design and decision record, and formal `DESIGN.md` authoring is a separate catalog capability.

Ask focused questions when a missing choice changes experimental behavior. Offer reasoned alternatives when the researcher wants help making that choice. Keep alternatives and recommendations identifiable as proposals until the researcher selects them. Work from the available requirements without requiring every earlier workflow artifact.

## Develop the applicable operational requirements

Address the following according to the actual study:

- **Participants and setting:** Define the intended participation setting and any screening, allocation, or group-specific behavior. Identify the source and collection point of information used for these decisions.
- **Overall procedure:** Establish entry, component sequence, transitions, repetition, breaks, branching, and completion where required. Distinguish rules applying across the experiment from rules local to a component.
- **Component behavior:** Define what the participant sees, hears, reads, or does; the content and instructions required; accepted responses and their meanings; timing; progression; and completion. Specify instruction needs within the design while the researcher determines their requirements.
- **Control arrangements:** Define eligible materials, ordering or sampling units, repetitions, constraints, and the scope of randomization or counterbalancing when required. Identify how each design-defined branch is selected and what follows it.
- **Materials:** State required content, properties, quantities, identities, and relationships. Preserve any adopted instrument's exact version and relevant administration requirements. Treat material discovery, screening, and formatting as subsequent or separately requested work.
- **Observations:** Define the meaning, source, units, measurement endpoints, response interpretation, and calculation rules of required results. Specify inclusion, exclusion, or performance criteria when established, including whether they affect execution or later handling.
- **Result handling:** Establish recording detail, associations needed to identify records, organization, destination, delivery trigger, and completion behavior according to the study's requirements. Keep later statistical preprocessing and analysis outside this workflow task.

Do not introduce fixed counts, experimental conditions, standard task structures, or measurement types solely to fill these categories. Include the behaviors that the design requires and resolve missing required values with the researcher.

## Check feasibility and coherence

Check that the proposed procedure can obtain the intended observations, that information needed by a decision is available at the relevant point, and that component and overall rules agree. Explain methodological tradeoffs that materially affect the requested design without expanding into unrelated study changes.

Verify uncertain empirical or instrument claims against primary evidence. Verify a lab.js-specific feasibility claim against applicable official documentation or source before relying on it. A technical limitation that changes the experiment requires a design decision; do not silently alter the procedure to accommodate implementation.

## Deliver the decisions

Present the developed design in the requested form. Use coherent sections organized around the actual study, with precise operational values where decided. Identify substantive changes when revising an existing design and distinguish settled requirements from outstanding decisions.

Before declaring the requested design complete, check that dependent behavior can be specified without guessing scientific choices. If the researcher requested exploration or a partial design, state which portion has been developed and which choices remain open.

Hand the established decisions to the formal design-document writing stage when that output is requested. Writing code, preparing assets, running tests, and administering human test sessions remain outside this skill's scope. Save a separate design artifact only when requested; an ordinary design discussion can deliver its decision record in the conversation.
