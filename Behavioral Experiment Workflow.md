# LARA Workflow - A lab.js based AI workflow for behavioral experiment design & deployment

## 1. Purpose and scope

This workflow describes how to turn a research concept into a functioning behavioral experiment built with lab.js and deployed locally, online, or in both settings. It covers conceptualization, experimental design, design documentation, source-material collection, technical specification, asset preparation, supporting-tool development, experiment implementation, testing, and deployment.

The workflow defines the work and the expected outcomes at each stage. The research design governs experimental decisions, and the technical specification translates those decisions into implementable behavior. Materials, implementation, testing, and deployment must remain consistent with both.

## 2. Workflow overview

1. Define the research concept and intended observations.
2. Develop the experimental design and write the design document.
3. Collect and organize source materials.
4. Translate the design into a technical specification.
5. Prepare, format, and verify experiment assets.
6. Develop and test required supporting tools.
7. Build and integrate the experiment.
8. Test the complete system technically.
9. Conduct human testing and revise the experiment.
10. Package the tested experiment for its intended deployment.
11. Deploy locally, online, or in both settings and verify the deployed system.

These stages describe the main dependency order. Material collection can begin while the design is being developed. Supporting-tool development and experiment implementation can overlap after their responsibilities and interactions have been specified. Findings that affect the design, materials, or behavior return to the relevant earlier stage before affected work proceeds.

## 3. Workflow stages

### Stage 1. Conceptualize the study

**Inputs:** The research question, relevant theoretical background, and the researcher's initial study requirements.

**Activities:**

- Define what the study aims to investigate or assess.
- Identify the constructs, participant behaviors, and observations relevant to that aim.
- Establish the proposed tasks, questionnaires, manipulations, or other activities through which those observations will be obtained.
- Identify the intended participant population and whether participation will occur locally, online, or in both settings.
- Establish the practical constraints that shape the experiment, such as available equipment, presentation media, input methods, and session duration.

**Outputs:** A study concept describing its purpose, intended population, proposed activities, required observations, and execution setting.

**Completion criterion:** The researcher can explain what participants will do, what the study will measure, and how those observations address its purpose.

### Stage 2. Develop the design and write the design document

**Inputs:** The study concept and the researcher's experimental decisions.

**Activities:**

- Write `DESIGN.md` as the authoritative statement of the experiment's intended design.
- Describe the study overview, relevant background, and objectives.
- Specify participant screening, grouping, allocation, and any differences in procedure between groups. Identify where information used for those decisions will be collected.
- Define the overall procedure, including entry, component order, branching, repetition, breaks, and completion.
- Describe each component in sufficient detail to establish its content, presentation, participant actions, response meanings, timing, and completion conditions.
- Specify randomization, sampling, counterbalancing, and other manipulations at the experiment or component level, as applicable.
- Define the required outcomes, including measurement meanings, calculation rules, and any inclusion, exclusion, or performance criteria established by the design.
- Describe how results should be recorded, organized, stored, and delivered in each intended execution setting.
- Record additional study-specific requirements that affect participant experience or system behavior.

**Outputs:** A design document that defines the participant procedure, experimental conditions, required materials, observations, and result-handling requirements.

**Completion criterion:** Decisions needed to determine experimental behavior are explicit. Any ambiguity that would change the study's content, conditions, measurements, or participant experience has been resolved with the researcher before dependent implementation begins.

### Stage 3. Collect and organize source materials

**Inputs:** The design document and the source materials supplied or selected for the study.

**Activities:**

- Collect the texts, questionnaire items, response options, scales, images, audio, video, and other materials required by the design.
- Collect participant-facing wording, including instructions, prompts, feedback, and completion messages where required.
- Organize materials by their intended role and preserve item identities, meaningful order, group membership, labels, and associations between files.
- Compare the collected materials with the design's required content and quantities.
- Resolve missing content or unclear source associations with the researcher before formatting the affected materials.
- Preserve the original source files so that the prepared assets can be checked against them and recreated when necessary.

**Outputs:** An organized source-material collection with identifiable relationships to the experiment's content requirements.

**Completion criterion:** The materials needed for the next preparation step are available, identifiable, and sufficient for the design-defined content and quantities.

### Stage 4. Produce the technical specification

**Inputs:** The design document, available source materials, and the intended local or online execution setting.

**Activities:**

- Translate the design into a technical specification describing the experiment's execution environment, component organization, execution structure, component behavior, resources, external connections, and data handling.
- Define component responsibilities and containment separately from chronological execution order.
- Specify activation, inputs, operations, timing, completion, outputs, and information dependencies for each component.
- Define the control rules governing ordering, repetition, selection, randomization, conditional progression, and any concurrent activity required by the design.
- Identify the materials each component consumes and the requirements governing their availability and use.
- Define the meaning, source, measurement endpoints, units, recording events, and delivery requirements of the required observations.
- Identify any supporting capabilities that operate outside the main experiment and define their interactions with it.
- Verify lab.js-specific technical assumptions against official documentation or source information appropriate to the selected implementation version.

**Outputs:** A technical specification that connects the design to implementable system behavior while preserving the researcher's experimental decisions.

**Completion criterion:** Components, control rules, resource dependencies, supporting capabilities, and data flows form a coherent system that can be implemented without reconstructing its behavior from the original narrative.

### Stage 5. Prepare, format, and verify assets

**Inputs:** The design document, technical specification, and collected source materials.

**Activities:**

- Establish the concrete content structure and file format needed for each distinct asset type.
- Convert the source materials into those formats while preserving supplied wording, meaningful formatting, quantities, identities, and relationships.
- Include required content identifiers, annotations, and references to associated media.
- Apply media transformations when the experiment's requirements call for them, while retaining the original sources.
- Save completed experiment assets under `assets/` and organize them according to their actual roles and relationships.
- Check syntax, encoding, escaping, file references, item associations, and required collection sizes.
- Verify that the completed assets contain the required content and that all temporary content slots have been resolved.

**Outputs:** A complete set of formatted assets that can be consumed by the experiment and checked against the original materials.

**Completion criterion:** Every required prepared asset has valid content and references, preserves the design's requirements, and is ready for integration.

### Stage 6. Develop and test supporting tools

**Inputs:** The technical specification and any source or result formats involved in external operations.

**Activities:**

- Identify which supporting tools the specified workflow requires before, during, or after experiment execution.
- Define each tool's responsibility, inputs, outputs, invocation point, and interaction with the rest of the system.
- Implement the required tools under `tools/`, keeping their implementation separate from the main experiment.
- Test each tool from representative input through the expected output.
- Verify that its outputs and completion behavior satisfy the experiment's requirements.

**Outputs:** Tested supporting tools with established interactions and usable inputs and outputs.

**Completion criterion:** Each required tool performs its specified operation and can participate in the complete workflow. This stage is omitted when the experiment requires no supporting tools.

### Stage 7. Build and integrate the experiment

**Inputs:** The design document, technical specification, prepared assets, and required supporting tools.

**Activities:**

- Implement the experiment under `experiment/` using lab.js.
- Build the specified components and connect their activation, progression, completion, and information dependencies.
- Integrate prepared assets and implement the required presentation, participant interaction, timing, response interpretation, and control behavior.
- Implement the specified data acquisition, calculations, recording, and delivery behavior.
- Connect supporting tools at their defined points of interaction.
- Check individual components during development before assembling the complete participant procedure.

**Outputs:** An integrated experiment executable with its required assets, data handling, and supporting-tool connections.

**Completion criterion:** The complete procedure can be run from entry through completion, and each design-defined branch can be exercised for technical testing.

### Stage 8. Test the complete system technically

**Inputs:** The integrated experiment and the requirements established in the design and technical specification.

**Activities:**

- Run end-to-end tests from experiment launch through result delivery.
- Exercise the required conditions, branches, repetitions, screening outcomes, grouping behavior, and completion paths.
- Check stimulus content, response handling, measurement definitions, timing behavior, and control rules against the specification.
- Use repeated runs where necessary to verify randomization, sampling, counterbalancing, and behavior that depends on multiple sessions or participants.
- Inspect recorded results for the required values, units, contextual associations, organization, and destination.
- Test required supporting-tool interactions as part of the complete system.
- Correct observed defects and retest the affected behavior and its connected paths.

**Outputs:** A technically tested experiment and recorded test outcomes showing whether its required behavior is satisfied.

**Completion criterion:** The tested system executes the specified procedure, records the required observations, and delivers results as required. Defects that prevent those outcomes have been corrected and retested.

### Stage 9. Conduct human testing and revise

**Inputs:** The technically tested executable, its materials, and the intended participant procedure.

The researcher and human testers conduct the runs. AI skills process supplied observations, log results, and apply requested revisions.

**Activities:**

- Perform two repetitions of the same test using the actual experiment executable.
- In each repetition, verify the complete participant experience, including instruction comprehension, presentation, interaction, navigation, and completion, together with applicable randomization, grouping, counterbalancing, result organization, and other study requirements.
- Include enough testers and runs to exercise the study's relevant requirements.
- Compare tester observations and recorded results with the intended design.
- Correct implementation defects. When findings require an experimental decision, resolve that decision with the researcher and update the design and affected specification before implementation changes.
- Repeat affected technical and human checks after revisions.

**Outputs:** A revised experiment supported by human test observations and verified result records.

**Completion criterion:** Both repetitions have been completed, and issues affecting the intended participant experience or required study behavior have been resolved and retested.

### Stage 10. Package the tested experiment

**Inputs:** The tested experiment, prepared assets, supporting tools, dependencies, and the selected deployment setting or settings.

**Activities:**

- Assemble the files and dependencies required to run the tested experiment.
- Include the required assets and supporting tools, preserving their expected paths and connections.
- Prepare the configuration needed for each intended deployment setting, including result destinations and external connections.
- Write the local run instructions, online deployment instructions, or both, according to the intended use.
- Record how to start the experiment, confirm successful completion, and locate or retrieve the resulting data.
- Verify the assembled package by following its instructions in the intended setting.

**Outputs:** A tested release package with the configuration and instructions needed for its selected deployment settings.

**Completion criterion:** The package contains the required runtime materials and can be started and completed using the supplied instructions, with results reaching their configured destination.

### Stage 11. Deploy and verify

**Inputs:** The tested release package and the selected local equipment, online hosting environment, or both.

#### Local deployment

- Place the release package and required dependencies on the intended local equipment.
- Configure and start the required local runtime and supporting services.
- Confirm that the experiment loads its assets and accepts the intended input on that equipment.
- Complete a test session and verify the resulting records at the configured local destination.
- Confirm that the operator can launch subsequent sessions and retrieve their results using the supplied instructions.

#### Online deployment

- Deploy the release package to the selected hosting environment and configure its required services and connections.
- Verify the participant entry address and the availability of the experiment and its assets.
- Complete a test session through the deployed participant entry point using the intended device and browser configuration.
- Verify result delivery, storage, and retrieval in the deployed environment.
- Exercise any required allocation or result-handling behavior that spans multiple online sessions.

#### Deployment in both settings

- Complete the local and online verification procedures independently.
- Confirm that each setting uses the intended experiment content and behavior.
- Verify any design-defined differences between the settings and their respective result destinations.

**Outputs:** A functioning local deployment, online deployment, or both, with verified participant access and result retrieval.

**Completion criterion:** The deployed experiment completes a real test session in every intended setting, produces the required data, and supports the specified operational procedure.

## 4. Revision and completion rules

- Changes to experimental content, conditions, quantities, timing, response meanings, or measurement definitions must be resolved with the researcher and reflected in the design document before dependent work is updated.
- Changes to technical organization or behavior must be reflected in the technical specification and any affected implementation or assets.
- Source materials remain available for comparison when prepared assets are revised.
- Changes discovered during testing or deployment return to the affected development stage and are followed by the relevant verification.
- Completion of the workflow requires verified execution and result retrieval in the intended deployment setting or settings. Later statistical preprocessing and analysis remain outside this experiment-development workflow.
