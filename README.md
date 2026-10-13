<h1 align="center">LARA Workflow</h1>

<p align="center">
  A lab.js based AI workflow for behavioral experiment design &amp; deployment<br>
  31 skills. Three personas. Five templates. Eleven workflow stages.
</p>

<p align="center">
  <a href=".agents/skills">Explore the skills</a> ·
  <a href="personas">Meet the personas</a> ·
  <a href="workflow-templates">Browse the templates</a>
</p>

## What this project provides

LARA Workflow helps researchers use Codex to conceptualize, design, build,
test, and deploy behavioral experiments with lab.js. It connects research
questions, design decisions, study materials, technical implementation, and
verification through a shared workflow.

Skills provide instructions for individual tasks. Personas define the
perspective and responsibilities applied to those tasks. Templates specify the
structure of the documents, folders, and materials produced along the way.
The researcher determines the study's purpose, methodology, participant
population, procedure, and measurements. The workflow accommodates those choices
without prescribing a particular paradigm or type of study.

Use the complete workflow to develop a new experiment, or select a skill for
an existing project with sufficient requirements and supporting materials.
Study-specific documents, assets, code, and results are created in the experiment
project as work progresses.

## Contents

- [What is included](#what-is-included)
- [Get started](#get-started)
- [The eleven-stage workflow](#the-eleven-stage-workflow)
- [Templates and study documents](#templates-and-study-documents)
- [Skills](#skills)
- [Personas and responsibilities](#personas-and-responsibilities)
- [Example requests](#example-requests)
- [Project organization](#project-organization)
- [Testing and deployment](#testing-and-deployment)
- [Customize and maintain](#customize-and-maintain)

## What is included

| Component | Included | Purpose |
|---|---:|---|
| [Workflow guide](<Behavioral Experiment Workflow.md>) | 11 stages | Defines development activities, inputs, outputs, and completion criteria. |
| [Skills](.agents/skills/) | 31 | Provides reusable instructions for research, design, materials, implementation, testing, revision, and deployment. |
| [Personas](personas/) | 3 | Defines Conceptualizer, Designer, and Coder responsibilities and handoffs. |
| [Workflow templates](workflow-templates/) | 5 | Specifies the structures used for concept, design, project organization, technical specification, and asset preparation. |
| [Persona and skill specification](<Personas and Skills Specification.md>) | 1 catalog | Describes each capability's scope, inputs, outputs, and relationship to the workflow. |
| [Project instructions](AGENTS.md) | 1 guide | Establishes repository conventions and researcher responsibilities. |

Each skill includes a `SKILL.md` instruction file and `agents/openai.yaml`
display metadata. All 31 skills and three persona definitions are implemented.
The toolkit contains instructions and specifications; experiment code and its
runtime dependencies are produced or obtained for the particular study.

## Get started

**Read the [workflow guide](<Behavioral Experiment Workflow.md>) first.** It
explains what each stage produces and how the work fits together.

1. Clone the repository or download and extract the complete ZIP. Preserve the
   hidden `.agents/` directory and keep the shared specifications beside it.
2. Open the extracted repository root as a project in Codex. This is the folder
   containing `README.md`, `AGENTS.md`, and `.agents/`.
3. Read [AGENTS.md](AGENTS.md). Identify your research direction, available
   documents and materials, intended execution setting, and experiment folder.
4. Start a chat in the project and request the relevant skill using
   `$skill-name`, followed by the task and its inputs. For an initial idea, start
   with `$brainstorm-study`.
5. When ready to create the study workspace, use `$create-experiment-project`
   with its target path and available requirements. Keep the experiment folder
   distinct from this reusable toolkit and provide its path in subsequent tasks.

### Requirements

| Requirement | Purpose |
|---|---|
| A Codex environment with project skill support | Loads the instructions under `.agents/skills/`. |
| Access to the toolkit and the intended experiment folder | Allows skills to read shared specifications and work on study artifacts. |
| Research, file, coding, browser, or media capabilities appropriate to the task | Supports the selected discovery, implementation, formatting, or testing work. |
| The experiment's chosen lab.js version and runtime dependencies | Supports building and running the specified experiment. |
| The selected local equipment or online host | Supports deployment and verification in the intended setting. |

The instruction toolkit has no bundled runtime dependencies or installation
script. Supporting tools and experiments document their own dependencies as
they are built. Git is useful for cloning and version control; downloading the
complete ZIP also provides the toolkit files.

For an existing experiment, supply its current documents, sources, code, and
known issues, then choose the skill that addresses the next task. An isolated
revision can use explicit requirements without first generating every workflow
document.

## The eleven-stage workflow

The [complete workflow](<Behavioral Experiment Workflow.md>) defines the detailed
activities and completion criteria for each stage.

| Stage | Main work | Expected output |
|---|---|---|
| **1. Conceptualize** | Explore the research direction, references, proposed activities, and intended observations. | A study concept recorded in `CONCEPT.md`. |
| **2. Design** | Establish the participant procedure, content, conditions, instructions, measurements, and result handling. | `DESIGN.md` with explicit experimental decisions. |
| **3. Collect and organize** | Set up the experiment project, collect original materials, and preserve their identities and relationships. | Organized `sources/` and an accurate project map in `LIB.md`. |
| **4. Specify the system** | Translate the design into components, execution rules, resource requirements, and data flows. | `SCHEMATICS.md`. |
| **5. Prepare assets** | Define reusable material formats, populate them, and verify the completed content. | Study-specific `templates/` and prepared `assets/`. |
| **6. Develop supporting tools** | Design, implement, and test any required external capabilities and their interfaces. | Working tools with run instructions and verification evidence. |
| **7. Build the experiment** | Plan the architecture and implement the complete lab.js procedure, assets, data handling, and tool connections. | A runnable experiment under `experiment/`. |
| **8. Test technically** | Exercise required paths, repetitions, measurements, integrations, and result delivery. | Observed technical test results and verified corrections. |
| **9. Test with humans** | The researcher and testers perform repeated runs of the experiment and supply observations. | Human test findings, any required revisions, and relevant retest evidence. |
| **10. Package** | Assemble the tested implementation, dependencies, configuration, and operating instructions. | A verified release file or package for the selected target. |
| **11. Deploy and verify** | Install locally, deploy online, or do both, then test actual sessions and retrieve their results. | Verified access, execution, and result retrieval in each intended setting. |

These stages express dependencies. Material collection may overlap design, and
tool development may overlap implementation once their interfaces are specified.
Supporting-tool development applies when the experiment needs it. Findings that
affect earlier decisions return to the relevant stage before dependent work is
updated.

## Templates and study documents

The five files under `workflow-templates/` are general specifications used to
create study-specific outputs. Their content is adapted to the researcher's
requirements and available materials.

| Template | Used for | What it establishes |
|---|---|---|
| [Concept Doc Schematics](<workflow-templates/Concept Doc Schematics.md>) | `CONCEPT.md` | Research purpose, intended population, proposed activities, observations, and practical constraints. |
| [Design Doc Schematics](<workflow-templates/Design Doc Schematics.md>) | `DESIGN.md` | The intended experiment, participant procedure, component behavior, materials, and result requirements. |
| [Experiment File Structure](<workflow-templates/Experiment File Structure.md>) | Study folders and `LIB.md` | Locations for documents, sources, assets, implementation, tools, and applicable local data. |
| [Framework Doc Schematics](<workflow-templates/Framework Doc Schematics.md>) | `SCHEMATICS.md` | Technical responsibilities, execution behavior, resource relationships, and data acquisition and delivery. |
| [Template Schematics](<workflow-templates/Template Schematics.md>) | Study `templates/` and completed `assets/` | Reusable material structures, fixed content, fillable slots, and formatting requirements. |

`DESIGN.md` carries the experimental decisions. `SCHEMATICS.md` translates them
into implementable behavior. `LIB.md` records actual file locations as the
project develops. Original materials remain available in `sources/` so prepared
assets can be checked and recreated.

## Skills

Use `$skill-name` in a Codex chat with the task, experiment location, and relevant
inputs. Each linked `SKILL.md` explains its procedure and verification. The
following groups help locate a capability; select the skills needed for the
actual work.

| Task | Skills |
|---|---|
| Explore and research | [brainstorm-study](.agents/skills/brainstorm-study/SKILL.md), [find-reference-studies](.agents/skills/find-reference-studies/SKILL.md), [find-standardized-tests](.agents/skills/find-standardized-tests/SKILL.md) |
| Conceptualize and design | [conceptualize-study](.agents/skills/conceptualize-study/SKILL.md), [design-experiment](.agents/skills/design-experiment/SKILL.md), [write-design-document](.agents/skills/write-design-document/SKILL.md) |
| Set up and specify | [create-experiment-project](.agents/skills/create-experiment-project/SKILL.md), [organize-project-files](.agents/skills/organize-project-files/SKILL.md), [write-experiment-schema](.agents/skills/write-experiment-schema/SKILL.md), [write-material-templates](.agents/skills/write-material-templates/SKILL.md) |
| Prepare materials | [find-study-materials](.agents/skills/find-study-materials/SKILL.md), [screen-study-materials](.agents/skills/screen-study-materials/SKILL.md), [format-study-materials](.agents/skills/format-study-materials/SKILL.md), [create-study-materials](.agents/skills/create-study-materials/SKILL.md) |
| Prepare instructions and diagrams | [plan-study-instructions](.agents/skills/plan-study-instructions/SKILL.md), [diagram-study-procedure](.agents/skills/diagram-study-procedure/SKILL.md) |
| Develop supporting tools | [design-supporting-tools](.agents/skills/design-supporting-tools/SKILL.md), [build-supporting-tools](.agents/skills/build-supporting-tools/SKILL.md) |
| Plan and build | [plan-experiment-build](.agents/skills/plan-experiment-build/SKILL.md), [build-experiment](.agents/skills/build-experiment/SKILL.md) |
| Review, test, and record | [review-experiment-consistency](.agents/skills/review-experiment-consistency/SKILL.md), [test-experiment-end-to-end](.agents/skills/test-experiment-end-to-end/SKILL.md), [log-test-results](.agents/skills/log-test-results/SKILL.md) |
| Revise existing work | [revise-text-files](.agents/skills/revise-text-files/SKILL.md), [revise-multimodal-files](.agents/skills/revise-multimodal-files/SKILL.md), [revise-code](.agents/skills/revise-code/SKILL.md) |
| Clean and package | [clean-project-residuals](.agents/skills/clean-project-residuals/SKILL.md), [package-production-experiment](.agents/skills/package-production-experiment/SKILL.md) |
| Deploy and verify | [deploy-experiment-locally](.agents/skills/deploy-experiment-locally/SKILL.md), [deploy-experiment-online](.agents/skills/deploy-experiment-online/SKILL.md), [test-online-deployment](.agents/skills/test-online-deployment/SKILL.md) |

## Personas and responsibilities

| Persona | Focus | Typical handoff |
|---|---|---|
| [Conceptualizer](personas/conceptualizer/PERSONA.md) | Develops research ideas and concepts with the researcher and relevant studies. | A selected concept, supporting evidence, constraints, and remaining design questions. |
| [Designer](personas/designer/PERSONA.md) | Defines the experimental procedure and obtains, screens, organizes, and prepares materials and instructions. | Design decisions, `DESIGN.md`, selected content, and expected observations. |
| [Coder](personas/coder/PERSONA.md) | Specifies, implements, tests, packages, and deploys the technical system. | Technical specifications, runnable artifacts, verification evidence, and operating instructions. |

To apply a persona, ask Codex to read its `PERSONA.md` and use that perspective
for the task. These files describe reusable responsibilities. They can be used
within a single chat; separate agent configuration and delegation are outside
their role.

The researcher resolves decisions affecting scientific aims, experimental
conditions, participant experience, timing, response meanings, and measurements.
Personas contribute proposals and evidence within their areas of responsibility.

## Example requests

Replace the bracketed placeholders with your own requirements and paths. These
are individual chat requests; each task uses the inputs available at that point.

### Explore a study direction

```text
$brainstorm-study Help me explore [research question] for [population],
within [practical constraints]. Compare possible participant activities
and the observations each would provide.
```

### Write an established design

```text
$write-design-document Use the agreed decisions in [notes path] and the
concept in [study folder]/CONCEPT.md to write [study folder]/DESIGN.md.
Identify any remaining decisions needed to specify the experiment.
```

### Prepare materials

```text
$format-study-materials Prepare the selected sources in [study folder]/sources/
using the formats in [study folder]/templates/ and the requirements in
DESIGN.md and SCHEMATICS.md. Save the completed assets under assets/.
```

### Plan the implementation

```text
Read personas/coder/PERSONA.md and use the Coder perspective.
$plan-experiment-build Plan the implementation for [study folder], using
its DESIGN.md, SCHEMATICS.md, available assets, and [deployment target].
```

### Verify a deployed experiment

```text
$test-online-deployment Test [participant entry URL] against the design
and release in [study folder]. Verify a complete session and retrieve
its stored results using [authorized access details or location].
```

## Project organization

The reusable toolkit has this structure:

```text
.
├── README.md
├── AGENTS.md
├── .gitattributes
├── .gitignore
├── Behavioral Experiment Workflow.md
├── Personas and Skills Specification.md
├── .agents/
│   └── skills/
│       └── <skill-name>/
│           ├── SKILL.md
│           └── agents/openai.yaml
├── personas/
│   ├── conceptualizer/PERSONA.md
│   ├── designer/PERSONA.md
│   └── coder/PERSONA.md
└── workflow-templates/
    ├── Concept Doc Schematics.md
    ├── Design Doc Schematics.md
    ├── Experiment File Structure.md
    ├── Framework Doc Schematics.md
    └── Template Schematics.md
```

An experiment project develops its own `CONCEPT.md`, `DESIGN.md`,
`SCHEMATICS.md`, and `LIB.md`, alongside applicable `sources/`, `templates/`,
`assets/`, `experiment/`, `tools/`, and `data/` folders. Choose subfolders and
local data arrangements from the actual study requirements. The
[folder specification](<workflow-templates/Experiment File Structure.md>) defines
their roles; documents and implementation files are created at their respective
workflow stages.

Keep the toolkit's relative paths intact so skills and personas can locate
shared specifications. Update the experiment's `LIB.md` and affected references
when study files are added, moved, or renamed.

## Testing and deployment

Technical testing exercises the actual experiment from entry through completion
and result delivery. Coverage follows the design's branches, repetitions,
response rules, measurements, and supporting-tool interactions. Test records
identify the artifact, environment, observed outcomes, defects, and retests.

The researcher and human testers perform the repeated human test runs. They
supply observations for logging, assessment, and revision. Instruction planning
helps the researcher prepare instructions inside the experiment, documented in
`DESIGN.md`, or separate briefing materials in the requested format. Those
materials are prepared before testing. The AI's role covers preparation and
processing supplied findings; the researcher and testers conduct the sessions.

Package the tested experiment with its required assets, dependencies,
configuration, and instructions for launching sessions and retrieving results.
Local deployment is verified on the intended equipment. Online deployment
primarily uses JATOS and can support another host selected by the researcher.
Its integration follows the selected host's requirements and the experiment's
result-handling design.

Verify each intended deployment setting by completing a session and retrieving
its results. The workflow ends with verified experiment execution and result
delivery. Later statistical preprocessing and analysis are outside its scope.

## Customize and maintain

Adapt study-specific choices in the experiment's documents and materials. When
changing the reusable workflow, read the relevant parts of the
[workflow guide](<Behavioral Experiment Workflow.md>) and
[persona and skill catalog](<Personas and Skills Specification.md>), then update
the affected skill, persona, or template and its references.

Preserve the specifications' methodological neutrality and keep source materials,
material identities, and document-to-implementation relationships traceable.
Verify technical assumptions against official sources for the versions actually
used. After changes, check the affected outputs, local links, and behavior, and
record what was observed.
