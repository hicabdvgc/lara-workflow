# LARA Workflow Personas and Skills Specification

## 1. Purpose and scope

This document defines the three personas and 31 implemented skills for [Behavioral Experiment Workflow.md](<Behavioral Experiment Workflow.md>). It specifies their functionality, responsibilities, inputs, outputs, and relationships.

Skills 01–27 correspond to the originally requested capabilities. Skills 28–29 address original material creation and consistency review across project artifacts. Skills 30–31 provide the subsequently requested instruction-planning and procedure-diagram capabilities. All 31 skills are implemented under `.agents/skills/` using the names below.

A persona defines the perspective and responsibilities applied to a task. A skill defines a reusable capability with a concrete outcome. Several personas may use the same skill. The primary persona identifies the usual lead for that capability; it does not require separate agents or automatic delegation.

## 2. Shared functional requirements

- Each skill must work from the user's requirements and relevant available project artifacts. It should use the existing specifications where applicable and create the requested output from scratch when sufficient requirements are supplied. An isolated task does not require generating every earlier workflow artifact.
- Existing specifications govern their corresponding output structures. When an upstream document is unavailable, equivalent user-supplied requirements can provide the needed information. Experimental ambiguities must be resolved with the user before dependent decisions are implemented.
- The skills must accommodate different study topics, methodologies, participant populations, activity types, materials, observations, and execution settings. Examples and reference studies supply possibilities and evidence; they do not establish requirements for the current study.
- The user's experimental decisions govern scientific content, conditions, quantities, timing, response meanings, and measurements. Technical choices may be developed within those requirements. Proposals that change experimental decisions must remain identifiable as proposals until resolved with the user.
- Research and discovery skills must identify their sources and distinguish verified information from inference or unavailable information. Technical skills must verify relevant APIs, formats, and version compatibility against applicable official sources when used.
- Skills must preserve source materials, meaningful content associations, and the relationship between study requirements and generated artifacts. File operations must keep affected references and `LIB.md` accurate.
- Completion must be supported by the requested output and appropriate verification. Test results must reflect observed runs, and deployment claims must reflect the environment actually exercised.
- A skill invocation covers the requested task and its necessary handoffs. It does not imply authorization to contact researchers or participants, purchase materials, publish an experiment, or change unrelated projects.

## 3. Personas

### 3.1 Conceptualizer

**Purpose:** Develop a researcher's initial direction into a coherent study concept supported by relevant research.

**Responsibilities:** The Conceptualizer explores ideas with the user, clarifies research purposes and relevant constructs or behaviors, locates reference studies, and explains how proposed activities and observations could address the intended question. It distinguishes evidence, interpretation, and proposed directions and preserves the user's control over the study's scientific aims.

**Typical inputs:** The user's research direction, questions, existing ideas, relevant literature, practical constraints, and feedback on candidate concepts.

**Typical outputs:** Candidate ideas, source-supported research summaries, conceptual alternatives, and a completed or revised `CONCEPT.md`.

**Handoff:** Pass the selected concept, supporting references, established requirements, and remaining design decisions to the Designer. Technical feasibility questions may be referred to the Coder. The Conceptualizer's proposals become design requirements through the user's decisions.

### 3.2 Designer

**Purpose:** Develop the experiment's actual design and obtain, evaluate, and organize the materials needed to realize it.

**Responsibilities:** The Designer specifies the participant procedure, applicable conditions and control arrangements, content requirements, observations, and result-handling requirements. It finds standardized instruments and other materials, evaluates their suitability against the study's criteria, preserves source relationships, and writes the design document. It also assesses participant-facing content and human test findings for their implications for the design.

**Typical inputs:** The study concept, user decisions, reference evidence, available instruments and materials, execution constraints, and participant-experience findings.

**Typical outputs:** Design decisions, `DESIGN.md`, organized source collections, material selection records, content requirements, and design revisions.

**Handoff:** Supply the Coder with the design, selected materials, required observations, and operational constraints. Resolve questions that affect scientific or participant-facing behavior with the user. Consult the Conceptualizer when a proposed design change affects the study's underlying purpose.

### 3.3 Coder

**Purpose:** Implement, verify, package, and deploy the technical system required by the experiment.

**Responsibilities:** The Coder translates the design into technical specifications and implementation architecture, defines usable asset formats, builds supporting tools and experiment code, and verifies their integrated behavior. It manages technical file organization, code revisions, release preparation, and local or online deployment. It supplies evidence about what the system actually does and records observed limitations or defects precisely.

**Typical inputs:** The user's technical requirements, `DESIGN.md`, source materials and prepared assets, technical specifications, target environments, and test findings.

**Typical outputs:** `SCHEMATICS.md`, asset structures, supporting tools, experiment implementation, technical test evidence, release packages, and verified deployments.

**Handoff:** Return design-affecting choices to the Designer and user. Supply runnable builds implementing the researcher's specified instructions and procedure. Deliver release artifacts together with the instructions and result-retrieval information required for the selected environment.

## 4. Existing specification resources

These files define the reusable output structures for the first five workflow stages. They are distinct from the experiment-specific documents and assets produced by using them.

| Resource | Intended use |
|---|---|
| [Concept Doc Schematics.md](<workflow-templates/Concept Doc Schematics.md>) | Guides conceptualization and the structure of `CONCEPT.md`. |
| [Design Doc Schematics.md](<workflow-templates/Design Doc Schematics.md>) | Guides the structure and content of `DESIGN.md`. |
| [Experiment File Structure.md](<workflow-templates/Experiment File Structure.md>) | Guides project creation, source-material organization, and the locations of later outputs. |
| [Framework Doc Schematics.md](<workflow-templates/Framework Doc Schematics.md>) | Guides the technical responsibilities, execution, resource, and data records in `SCHEMATICS.md`. |
| [Template Schematics.md](<workflow-templates/Template Schematics.md>) | Guides asset structures under `templates/` and completed materials under `assets/`. |

The catalog below refers to these resources by filename. Activities such as brainstorming, literature discovery, architecture selection, testing, and deployment use their own task requirements and relevant evidence; they do not require inventing additional document templates at this stage.

## 5. Requested skill catalog

### 01. `brainstorm-study`

**Primary persona:** Conceptualizer.

**Inputs:** The user's research direction, interests, constraints, and any existing ideas or evidence.

**Function:** Explore candidate questions, study approaches, participant activities, and observations through discussion. Explain the rationale, differences, and practical implications of the alternatives that matter to the user's direction. Refine candidates in response to user feedback.

**Outputs:** A set of clearly described candidate ideas and an account of which directions the user has selected, rejected, or left open.

**Boundary:** This skill supports exploration. Consolidating the selected direction into the study concept belongs to `conceptualize-study`; factual claims requiring evidence use verified sources.

### 02. `find-reference-studies`

**Primary persona:** Conceptualizer; the Designer may also use it.

**Inputs:** A research question, concept, construct, method of interest, or a specific evidence request.

**Function:** Search for relevant studies, inspect accessible primary reports, and extract the purpose, population, procedure, materials, observations, and findings relevant to the request. Explain each source's relevance and identify differences that matter when applying it to the proposed study.

**Outputs:** A source-linked collection of reference studies with verified bibliographic information and focused summaries. The account identifies whether claims were verified from a full report, abstract, or another available source.

**Boundary:** Finding a precedent does not establish its suitability or make its experimental settings requirements for the current study. This skill does not invent inaccessible methods or findings.

### 03. `find-standardized-tests`

**Primary persona:** Designer; the Conceptualizer may contribute to construct alignment.

**Inputs:** The intended construct or assessment purpose, participant population, language, administration setting, and other supplied selection criteria.

**Function:** Locate candidate standardized instruments and verify their identity, version, intended use, administration, scoring, available validation evidence, and access or usage conditions. Compare candidates against the supplied requirements using official instrument resources and primary validation sources where available.

**Outputs:** A source-linked comparison of suitable candidates, their relevant evidence, access locations, and any unresolved information affecting selection.

**Boundary:** Selection and adoption remain design decisions. A modified or newly written instrument must be identified accurately; evidence for an original version does not automatically apply to an adaptation.

### 04. `conceptualize-study`

**Primary persona:** Conceptualizer.

**Inputs:** The user's selected direction, relevant references, proposed activities and observations, and established practical constraints.

**Function:** Develop a coherent explanation of the study's purpose, relevant concepts, intended participants, proposed activities, expected information, and execution setting. Distinguish established decisions from provisional choices and connect the intended observations to the research purpose.

**Outputs:** `CONCEPT.md`, created or revised according to Concept Doc Schematics.md, with genuine remaining design decisions represented as that specification permits.

**Boundary:** This skill establishes the study concept. Detailed operational design is developed through `design-experiment`.

### 05. `design-experiment`

**Primary persona:** Designer.

**Inputs:** The concept or equivalent user requirements, reference evidence, candidate instruments or materials, and practical constraints.

**Function:** Develop the participant procedure and component behavior. Specify applicable screening, allocation, ordering, repetition, randomization, timing, responses, observations, and result handling. Determine content and material requirements and resolve choices that affect the experimental design with the user.

**Outputs:** An explicit set of design decisions and requirements sufficient to describe the intended experiment, including any decisions revised during the task.

**Boundary:** This skill develops the design. `write-design-document` places that design in its formal document structure. Neither activity prescribes a particular methodology by default.

### 06. `write-design-document`

**Primary persona:** Designer.

**Inputs:** The established experimental design, source notes, user decisions, and any existing design document.

**Function:** Synthesize the design into the prescribed sections, preserve its substantive decisions, and connect overall procedure, component details, required outcomes, and result handling. Identify ambiguities that prevent faithful documentation and obtain the needed clarification.

**Outputs:** A complete or updated `DESIGN.md` following Design Doc Schematics.md.

**Boundary:** Writing the document does not authorize selecting missing experimental values. Questions requiring new design decisions return to `design-experiment` and the user.

### 07. `create-experiment-project`

**Primary persona:** Coder; the Designer supplies material-organization requirements.

**Inputs:** The intended project location, current project contents, design requirements, and any existing concept or design documents.

**Function:** Establish the applicable project directories using Experiment File Structure.md. Place existing project documents and source collections in their intended locations, reserve appropriate locations for later outputs, and create or update `LIB.md` to describe the actual structure.

**Outputs:** An initialized experiment project with the required directories and an accurate file-location map.

**Boundary:** Project initialization creates the structure needed by the study. Experiment-specific content and later-stage documents are produced by their corresponding skills.

### 08. `organize-project-files`

**Primary persona:** Designer for source collections; Coder for technical project files.

**Inputs:** Existing files, their known relationships, the required organization, and the current project map.

**Function:** Classify, place, and rename files where the requested organization requires it. Preserve source identities and associations, maintain dependent references, and update `LIB.md`. Apply Experiment File Structure.md to project organization.

**Outputs:** An organized collection or project with resolvable references and an accurate account of file locations.

**Boundary:** This skill changes organization. Content transformation, scientific screening, and deletion are handled by their respective skills.

### 09. `write-experiment-schema`

**Primary persona:** Coder; the Designer resolves experimental ambiguities.

**Inputs:** `DESIGN.md` or equivalent explicit design requirements, supplied materials, and the execution setting.

**Function:** Translate the experiment into component responsibilities, execution structure, operational behavior, resource dependencies, external connections, and data recording and delivery requirements. Check containment, references, timing definitions, and information availability.

**Outputs:** `SCHEMATICS.md` following Framework Doc Schematics.md, using its component, rule, material, external-connection, and data identifiers.

**Boundary:** The schema describes technical behavior and relationships. Source-code architecture, function signatures, implementation fields, and asset-file structures are developed in the later technical and material-formatting tasks.

### 10. `write-material-templates`

**Primary persona:** Coder; the Designer verifies content requirements.

**Inputs:** The design, technical specification, and required asset structures or representative source materials.

**Function:** Select suitable asset formats and construct reusable representations containing required structure, fixed content, and identifiable fillable slots. Preserve item relationships and share structures where their requirements are compatible. Verify the chosen syntax and references.

**Outputs:** Actual asset template files under `templates/`, following Template Schematics.md.

**Boundary:** This skill creates asset structures. Populating them from source collections belongs to `format-study-materials`, and instructions governing runtime behavior remain in the technical specification.

### 11. `find-study-materials`

**Primary persona:** Designer.

**Inputs:** The required content, media types, quantities, characteristics, language, and other design-defined selection requirements.

**Function:** Locate candidate materials in supplied collections or appropriate external sources. Establish their provenance, available properties, and relevant access or reuse conditions. Collect accessible materials within the requested scope and retain their source associations.

**Outputs:** A candidate collection under `sources/` where files can be obtained, together with source references and descriptive information needed for selection.

**Boundary:** Discovery supplies candidates. Acceptance against study criteria belongs to `screen-study-materials`. Specialized discovery of standardized instruments belongs to `find-standardized-tests`.

### 12. `screen-study-materials`

**Primary persona:** Designer.

**Inputs:** Candidate materials and explicit inclusion, exclusion, content, quality, quantity, or collection-level criteria from the study.

**Function:** Evaluate materials against the supplied criteria, using inspection or measurement appropriate to each criterion. Check relevant relationships across the collection, such as required categories or counts, when specified. Distinguish measured properties, judgments, and information that cannot yet be established.

**Outputs:** A selection record identifying accepted, excluded, and unresolved candidates with reasons tied to the criteria, plus the selected collection or references to it.

**Boundary:** This skill does not create new scientific selection thresholds or alter content to make it pass screening. Exclusion from a selection does not require deleting the source material.

### 13. `format-study-materials`

**Primary persona:** Designer; the Coder supports technical format requirements.

**Inputs:** Selected source materials, asset templates or explicit target formats, and the relevant design and technical requirements.

**Function:** Populate the required structures, preserving wording, meaningful order, identities, annotations, and associations. Perform specified format conversions or media transformations. Check syntax, encoding, quantities, references, and completion of all required content slots.

**Outputs:** Completed, usable assets under `assets/`, following Template Schematics.md and the established asset structures, with original sources retained.

**Boundary:** Formatting implements defined representations. Changes to scientific content, screening criteria, or participant-facing meaning require a corresponding design decision.

### 14. `design-supporting-tools`

**Primary persona:** Coder.

**Inputs:** Required supporting operations, relevant technical specifications, external constraints, and input and output requirements.

**Function:** Define each required tool's responsibility, interfaces, processing behavior, execution setting, dependencies, and integration points. Establish the cases and expected outputs needed to verify the tool. Choose technical approaches supported by the actual requirements.

**Outputs:** An implementation-ready tool design with defined inputs, outputs, interactions, and verification criteria.

**Boundary:** Tool design covers supporting capabilities identified by the study. The main experiment's architecture belongs to `plan-experiment-build`.

### 15. `build-supporting-tools`

**Primary persona:** Coder.

**Inputs:** A tool design or equivalent explicit requirements, relevant interfaces, and representative input data.

**Function:** Implement the tool under `tools/`, preserve its defined separation from the main experiment, and verify its behavior from input through output. Supply the instructions or configuration needed to use it in the specified workflow.

**Outputs:** A working supporting tool, its required dependencies and operational instructions, and evidence of the tests performed.

**Boundary:** Tool-level verification demonstrates the tool's behavior. Its interaction with the complete experiment is also exercised during integrated experiment testing.

### 16. `plan-experiment-build`

**Primary persona:** Coder.

**Inputs:** The design, technical specification, prepared asset formats, supporting-tool interfaces, and intended execution and deployment settings.

**Function:** Select the implementation architecture and technical approach. Map specified behavior to appropriate lab.js facilities or required custom code; define code organization, component interfaces, asset loading, state handling, result handling, dependencies, and build strategy. Compare alternatives where they materially affect the requirements and verify uncertain technical capabilities with focused checks when needed.

**Outputs:** A concrete implementation plan identifying the selected architecture, technical decisions, integration approach, and verification strategy.

**Boundary:** This skill makes implementation decisions within the design and schema. Changes to scientific behavior return to the Designer and user.

### 17. `build-experiment`

**Primary persona:** Coder.

**Inputs:** The design and technical requirements, implementation plan where available, prepared assets, and required supporting tools.

**Function:** Implement the full lab.js experiment under `experiment/`. Integrate component behavior, control rules, presentation, responses, measurements, assets, supporting tools, and result handling. Check components as they are built and assemble the complete participant procedure.

**Outputs:** A runnable integrated experiment with its necessary configuration and instructions for development testing.

**Boundary:** A successful build establishes a runnable implementation. Full technical testing, human testing, release preparation, and deployment provide their own completion evidence.

### 18. `test-experiment-end-to-end`

**Primary persona:** Coder; the Designer supplies design-specific expected outcomes.

**Inputs:** A runnable experiment, its expected behavior, required execution environments, and representative test inputs.

**Function:** Exercise complete sessions, relevant branches and conditions, supporting-tool interactions, and result delivery. Use repeated runs when required to check allocation, randomization, counterbalancing, or other cross-session behavior. Compare actual presentation, responses, control behavior, measurement values and units, and stored results with the requirements.

**Outputs:** Observed test outcomes, reproducible defect reports, and a coverage account identifying tested and untested requirements, recorded through `log-test-results`.

**Boundary:** This skill supports development and deployed local testing. Human testing is performed by human testers under the researcher's arrangements. The additional behavior of an online hosting environment is checked through `test-online-deployment`. Browser observations alone must not be represented as physical timing measurements when the study requires external measurement.

### 19. `clean-project-residuals`

**Primary persona:** Coder; the Designer may clarify the purpose of material collections.

**Inputs:** The project, its actual dependencies and references, and the user's cleanup scope.

**Function:** Identify residual outputs and redundant files, establish why they are removable, and remove or consolidate items within the authorized scope. Preserve needed originals, distinct material identities, runtime dependencies, study data, and test evidence. Update affected references and `LIB.md`, then verify the affected use paths.

**Outputs:** A cleaned project and a concise record of removed or consolidated items and the verification performed.

**Boundary:** A filename, age, or lack of an obvious direct reference alone does not establish that a file is disposable. Repeated stimuli or multiple uses of one source may be intentional study content.

### 20. `package-production-experiment`

**Primary persona:** Coder.

**Inputs:** The tested experiment, required assets and tools, relevant test outcomes, and the intended deployment format and environment.

**Function:** Produce the release artifact in the required form, including its runtime assets, dependencies, configuration, and run or deployment instructions. Verify that the artifact corresponds to the tested implementation and can complete the required procedure when launched through the supplied instructions.

**Outputs:** A production-ready experiment file or package, as required by the target, with release identification, operational instructions, and the applicable verification evidence.

**Boundary:** The required deliverable may be one file or a package. Its form follows the selected target and system requirements. Packaging does not itself establish successful installation on the final host.

### 21. `deploy-experiment-locally`

**Primary persona:** Coder.

**Inputs:** The release artifact, target local equipment and runtime requirements, required supporting services, and result destinations.

**Function:** Install or place the required files, configure the local execution environment and connections, launch the experiment, and verify a complete session using the actual local setup. Confirm that the operator can repeat the procedure and retrieve its results.

**Outputs:** A functioning local deployment, local run and result-retrieval instructions, and evidence from the deployment verification.

**Boundary:** A local deployment may use network services if the design requires them. Offline operation must be verified when it is an actual requirement. Reuse `test-experiment-end-to-end` for complete local execution checks.

### 22. `deploy-experiment-online`

**Primary persona:** Coder.

**Inputs:** The release artifact, selected hosting environment, authorized access, and requirements for participant entry, execution, and results.

**Function:** Prepare and deploy the experiment for the selected host. Use JATOS as the preferred hosting option for this workflow while supporting explicitly selected alternatives. Verify the target's current integration requirements and configure the required execution, session lifecycle, asset access, result submission, and completion behavior. Record how participants enter the deployed experiment and how operators retrieve results.

**Outputs:** A deployed study, its participant entry information, host-specific configuration and operator instructions, and the outcome of initial deployment checks.

**Boundary:** Hosting details must follow the selected environment and verified documentation. The JATOS preference does not establish a server address, account, installation, or permission to publish. Full online verification belongs to `test-online-deployment`.

### 23. `test-online-deployment`

**Primary persona:** Coder; the Designer supplies applicable study-level expectations.

**Inputs:** The deployed participant entry point, target environment, required device and browser configurations, and expected session and result behavior.

**Function:** Execute the experiment through its deployed entry point. Verify asset delivery, hosting integration, session progression, completion, result submission, storage, and retrieval. Exercise required branches and cross-session behavior in the online environment, including applicable allocation and result organization. Use the actual hosting service, including JATOS when selected.

**Outputs:** Online test evidence, deployment-specific defects, and a precise account of which configurations and requirements passed or remain untested, recorded through `log-test-results`.

**Boundary:** A working landing page or successful upload is insufficient evidence of a complete deployed session. This skill reuses study-level test expectations while checking the additional behavior introduced by online hosting.

### 24. `revise-text-files`

**Primary persona:** The persona responsible for the content: Conceptualizer, Designer, or Coder.

**Inputs:** Existing textual documents or structured text assets, requested changes, and the requirements that govern their meaning and format.

**Function:** Apply scoped revisions to prose, specifications, participant-facing text, and textual data files. Preserve unaffected content, meaningful identifiers and associations, and the syntax of structured formats. Check the revised content against the governing document or asset specification.

**Outputs:** Revised text files and a concise description of substantive changes and relevant checks.

**Boundary:** Routing depends on the file's role. Executable source code belongs to `revise-code`; scientific changes to instructions, items, or scoring descriptions must follow the user's design decisions even when expressed as a text edit.

### 25. `revise-multimodal-files`

**Primary persona:** Designer; the Coder contributes where technical integration is affected.

**Inputs:** Existing images, audio, video, or other multimodal assets, the requested changes, and the study's content and technical constraints.

**Function:** Apply the requested content or media transformations using appropriate editing capabilities. Preserve relevant properties and source associations, retain originals, inspect the rendered or played result, and check format compatibility. Update dependent references when the revision changes them.

**Outputs:** Revised media assets and verification of the requested changes and applicable presentation properties.

**Boundary:** Changes to stimulus content, duration, appearance, or other experimentally meaningful properties follow the design's requirements. Creating new study materials from a brief is addressed by the `create-study-materials` skill.

### 26. `revise-code`

**Primary persona:** Coder.

**Inputs:** Existing experiment or tool code, a requested behavior change or defect report, and relevant requirements and test evidence.

**Function:** Locate the affected implementation, make the required correction or change, preserve defined interfaces and unaffected behavior, and update technical documentation when its statements change. Run targeted verification and affected integration paths based on the actual change.

**Outputs:** Revised code with a description of the behavior changed and evidence from relevant tests.

**Boundary:** Code revisions must preserve the study's scientific requirements unless the user has changed them. A passing technical test does not itself establish that a changed experimental decision is appropriate.

### 27. `log-test-results`

**Primary persona:** Coder for technical testing; Designer for human test observations.

**Inputs:** Actual test runs, expected outcomes, observations, relevant execution context, and retest information.

**Function:** Record the tested artifact or version, environment, case or requirement, inputs, expected and actual results, outcome, and supporting evidence. Connect defects to corrections and retests while preserving earlier observations. Distinguish failures, blocked tests, and tests that were not executed from successful checks.

**Outputs:** A test record that supports reproduction, coverage assessment, defect follow-up, and release decisions across tool, experiment, human, and deployment testing.

**Boundary:** Logging records and organizes evidence. It does not execute tests or infer successful outcomes from plans, implementation claims, or absent error reports. Technical testing skills determine their test coverage; human test observations are supplied by the researcher or testers.

## 6. Additional implemented skills

The following implemented capabilities address original material creation and consistency review, extending the originally requested 27 skills.

### 28. `create-study-materials`

**Primary persona:** Designer; the Conceptualizer may support alignment with the study purpose.

**Reason for addition:** Discovery supplies existing materials, and revision changes existing files. A study may instead require original materials created from the researcher's requirements.

**Inputs:** An explicit content brief, the intended role of the materials, design-defined constraints, and required output formats.

**Function:** Author the requested original content or media, preserve its relationship to the study requirements, and identify it as newly created material. Check that the output satisfies the brief and supply it for screening and formatting where required.

**Outputs:** Original study materials with identifiable source versions and an account of their conformity to the supplied requirements.

**Boundary:** New materials must not be presented as published instruments, standardized tests, validated stimuli, or empirical evidence without the corresponding basis. Item meanings and scientific content follow the user's brief.

### 29. `review-experiment-consistency`

**Primary persona:** Designer for experimental meaning and Coder for implementation correspondence; the Conceptualizer contributes when the concept is affected.

**Reason for addition:** Individual writing and revision skills check their own outputs. A separate review can assess correspondence across artifacts after handoffs or changes without rewriting them as part of the review.

**Inputs:** The current requirements and the relevant concept, design, schema, materials, implementation, or test evidence for the requested review scope.

**Function:** Trace requirements through the available artifacts, identify contradictions and omitted requirements, check references and content associations, and locate the downstream effects of a proposed or completed change. Distinguish confirmed discrepancies from questions requiring a design decision.

**Outputs:** An evidence-based consistency review identifying affected artifacts and the specific decisions, revisions, or tests needed to address each finding.

**Boundary:** This skill can review any relevant subset of artifacts. It does not silently resolve scientific disagreements, replace executable testing, or mandate a full-project review for every small change.

## 7. Additional requested skills

### 30. `plan-study-instructions`

**Primary persona:** Designer.

**Inputs:** The study's procedure and requirements, the researcher's intended instructions, any existing wording or briefing materials, and the intended delivery setting and format.

**Function:** Help the researcher determine what instructions are needed, whom they address, what they must communicate, and when and where they will be provided. Develop the content and wording with the researcher. For instructions incorporated into the experiment, record their content, placement, and relevant presentation or progression requirements in DESIGN.md using Design Doc Schematics.md. For instructions provided separately, prepare the material in the format requested by the user and identify its relationship to the study procedure.

**Outputs:** An instruction plan, the corresponding design-document content for embedded instructions, and separate instruction or briefing materials in the requested formats when applicable.

**Boundary:** The researcher determines the instruction requirements. This skill supports their planning and preparation; running human tests remains the researcher's and testers' responsibility. Implementing embedded instructions uses the existing asset and experiment-building skills, and subsequent changes use the relevant revision skills.

### 31. `diagram-study-procedure`

**Primary persona:** Designer; the Coder supports rendering and technical representation when needed.

**Inputs:** The study procedure from DESIGN.md, relevant technical specifications, or equivalent explicit user requirements, together with the requested scope and output format.

**Function:** Create a readable diagram of the study's procedure. Represent its entry, activities, order, and completion, together with applicable branches, repetitions, grouping differences, and timing relationships established by the design. Select the visual detail appropriate to the requested view, preserve the meaning of the procedure, and check the rendered diagram for legibility and correspondence with the source requirements.

**Outputs:** A procedure diagram in SVG or another suitable user-requested format, with labels and connections that accurately represent the requested procedure.

**Boundary:** The diagram visualizes the specified study procedure. It does not introduce experimental steps or infer unresolved transitions. It may visualize a proposed procedure when the user requests that scope, with its provisional status made clear.

## 8. Relationship to the eleven-stage workflow

The table identifies the relevant implemented capabilities at each stage. Use the skills that the actual task requires; a stage does not require invoking every listed skill.

| Workflow stage | Lead | Relevant skills |
|---|---|---|
| 1. Conceptualize the study. | Conceptualizer. | 01 brainstorm-study, 02 find-reference-studies, and 04 conceptualize-study. |
| 2. Develop the design and write the design document. | Designer. | 02 find-reference-studies, 03 find-standardized-tests, 05 design-experiment, 06 write-design-document, 30 plan-study-instructions, and 31 diagram-study-procedure when visualization is requested. |
| 3. Collect and organize source materials. | Designer, with Coder support for project setup. | 07 create-experiment-project, 08 organize-project-files, 11 find-study-materials, 12 screen-study-materials, and 28 create-study-materials. |
| 4. Produce the technical specification. | Coder. | 09 write-experiment-schema. |
| 5. Prepare, format, and verify assets. | Designer and Coder. | 10 write-material-templates, 13 format-study-materials, and 24 or 25 for required revisions. |
| 6. Develop and test supporting tools. | Coder. | 14 design-supporting-tools, 15 build-supporting-tools, and 27 log-test-results. |
| 7. Build and integrate the experiment. | Coder. | 16 plan-experiment-build and 17 build-experiment. |
| 8. Test the complete system technically. | Coder. | 18 test-experiment-end-to-end, 26 revise-code, and 27 log-test-results. |
| 9. Conduct human testing and revise. | The researcher and human testers perform the testing. Designer and Coder handle supplied findings within their existing responsibilities. | 27 log-test-results records supplied observations; 24 revise-text-files, 25 revise-multimodal-files, and 26 revise-code address resulting changes. Design changes also use 05 and 06. |
| 10. Package the tested experiment. | Coder. | 19 clean-project-residuals when cleanup is needed, 20 package-production-experiment, 18 test-experiment-end-to-end, and 27 log-test-results. |
| 11. Deploy and verify. | Coder. | 21 deploy-experiment-locally with 18 for local verification; 22 deploy-experiment-online with 23 test-online-deployment for online verification; and 27 log-test-results. |

File organization, scoped revisions, and test logging may recur wherever the relevant work occurs. Proposed skill 29, `review-experiment-consistency`, supports requested cross-artifact reviews and the assessment of changes affecting multiple stages.

Skill 30, `plan-study-instructions`, also supports preparation of separate briefing materials in the user-requested format. Embedded instruction content proceeds through the existing asset preparation and implementation stages. Skill 31, `diagram-study-procedure`, can be used whenever the user needs a visual representation of the current or proposed procedure.

Human testing consists of repeated runs of the experiment by human testers. The researcher determines the needed instructions and incorporates them into the experiment or prepares separate briefing materials. These repetitions require no dedicated AI skill for guidance or organization. Supplied observations and resulting revisions are handled by the existing logging, design, and revision skills.

## 9. Functional handoffs

1. Brainstorming and research discovery provide options and evidence. Conceptualization consolidates the direction established with the user.
2. Experiment design establishes operational decisions. Instruction planning develops the researcher-defined instructions for inclusion in DESIGN.md or delivery as separate materials. Design-document writing expresses the design in the reusable document structure, and procedure diagramming visualizes it when requested.
3. Material discovery or creation supplies candidates. Screening determines their suitability under the study's criteria. Formatting turns selected content into usable assets.
4. Schema writing defines technical behavior. Pre-build planning selects the implementation architecture. Tool and experiment building produce the working system.
5. Technical testing skills produce execution evidence, and the researcher or human testers supply human test observations. Test logging preserves that evidence. Existing design and revision skills address the resulting changes, followed by the relevant technical tests or researcher-managed human retesting.
6. Production packaging assembles the tested deliverable. Deployment establishes it in the selected environment. Verification confirms execution and result retrieval in that environment.

Data-output validation belongs within the relevant tool, experiment, and deployment tests. Local deployment verification uses the existing end-to-end testing capability. These responsibilities are covered by the implemented skill set.
