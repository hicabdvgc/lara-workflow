# Stage 4. Technical specification

Use this specification for Stage 4 of [Behavioral Experiment Workflow.md](<../Behavioral Experiment Workflow.md>). Save the resulting SCHEMATICS.md at the experiment root. The framework below retains the existing component, control, resource, and data record structure.

**Note: Always check the following sites before writing anything!**
[FelixHenninger/lab.js: Online research made easy](https://github.com/FelixHenninger/lab.js/tree/main)
[lab.js/tasks at main · FelixHenninger/lab.js](https://github.com/FelixHenninger/lab.js/tree/main/tasks)
[Library reference — lab.js documentation](https://labjs.readthedocs.io/en/latest/reference/index.html)
[Examples & recipes — lab.js documentation](https://labjs.readthedocs.io/en/latest/recipes/index.html)
[Index — lab.js documentation](https://labjs.readthedocs.io/en/latest/genindex.html)

<goal>

Transform the human-written DESIGN.md into SCHEMATICS.md: a technical specification of the experiment's components, their organization, their execution behavior, and their resource and data relationships.

The author supplies the experiment design. The translating agent develops the technical structure needed to realize that design with lab.js. Organize the output around the experiment system. Scientific motivation, theoretical background, hypotheses, and narrative explanations remain in DESIGN.md.

SCHEMATICS.md must tell an implementation agent what technical units to build, how they fit together, what each unit does, when it operates, and what information moves between units. Specify behavior precisely enough that implementation does not require reconstructing the system from the original narrative.

Keep the specification at the level of technical responsibilities, behavior, timing, control, and information flow. Source-file arrangements, functions, program variables, object properties, database columns, API signatures, and executable code belong to the coding stage. The record labels and identifiers defined below organize the document; they do not prescribe identifiers or fields in the implementation.

Use the fixed output framework in the response_format section. Expand it through repeated records, nested components, and explicitly located extensions. This framework accommodates any experiment content supported by lab.js without prescribing component categories or listing the library's capabilities.

</goal>

<response_requirement>

## 1. Establish the technical scope

Read DESIGN.md together with supplied materials and the author's instructions. Use Design Doc Schematics.md to locate design information, then redistribute that information by its technical role in the system.

Consult all five references above and the relevant official documentation or source files before making lab.js-specific claims. When a linked page is inaccessible, use the official repository or another official documentation route to verify the relevant information. Check compatibility with the target version when the project specifies one. Examples establish possible implementation patterns; their experimental contents and settings do not become requirements for the current study.

The agent is responsible for technical decomposition and organization. It may introduce the functional units, coordination rules, and information handoffs needed to implement the design, even when the author has not named them. Select a coherent technical arrangement and describe its resulting behavior directly.

Preserve all experimental decisions, including participant conditions, materials, quantities, ordering constraints, timing, response meanings, and measurement definitions. Technical elaboration must preserve those decisions. Do not invent scientific content or silently change the experiment to fit a convenient implementation. Leave choices that affect only internal coding mechanics to the implementation agent.

Include technical content only. Exclude qualifications, caveats, readiness assessments, missing-information labels, unresolved questions, follow-up requests, and review reports from SCHEMATICS.md. Do not insert placeholders for absent design details or replace them with invented values. The output template's bracketed instructions must be replaced with actual specification content or removed according to the format rules.

## 2. Redistribute design information by system responsibility

Use the following mapping to extract technical requirements. A single design passage can contribute to several connected specification entries.

- **Overview and background:** Extract constraints that change system behavior or the execution environment. Keep scientific motivation and explanatory background in DESIGN.md.
- **Participation setting:** Specify the runtime boundary and relevant device, input, presentation, or deployment requirements in Section 1.
- **Participant screening, allocation, and group differences:** Locate the information acquisition, decision, and resulting behavior in the relevant components. Connect them through execution rules and information dependencies.
- **Overall procedure:** Construct the component organization in Section 2 and the execution structure in Section 3, including any nesting, ordering, repetition, or conditional progression.
- **Individual activity descriptions:** Decompose them into technical components and specify each component's operational behavior in Section 4. Identify the materials or external capabilities it uses in Section 5.
- **Expected outcomes and acceptance criteria:** Convert required observations into acquisition or calculation definitions in Section 6. Put criteria that affect execution into the relevant component or control rule. Keep hypotheses in DESIGN.md. Later statistical preprocessing and analysis are outside this experiment-development workflow.
- **Results handling:** Define recording and delivery behavior in Section 6 and any external connection in Section 5. Connect these operations to their execution triggers.
- **Additional information:** Place each technical constraint with the environment, component, control rule, resource, connection, or data operation it governs.

Do not reproduce the design document's headings as the output structure. Combine descriptions that define one technical responsibility, and separate descriptions that require independently controlled technical behavior.

## 3. Construct the component organization

A component is an identifiable technical unit with a coherent responsibility and an execution boundary. It can perform an operation, manage other components, or maintain behavior over an interval. It does not have to be visible, interactive, or equivalent to one lab.js class.

Create a separate component when a part requires independent activation, completion, coordination, or reuse. Keep details within one component when they share its execution boundary. Stop decomposition before it becomes a list of functions, event handlers, or individual coding operations.

Give each component a unique document identifier. Use C-001, C-002, and so on for newly assigned identifiers, and preserve established specification identifiers when revising an existing schematic. Use these identifiers consistently throughout the document.

Register every component once in Section 2 and provide exactly one full record for it in Section 4. Record its parent to show containment; use SYSTEM for components directly contained by the experiment. Containment and chronological order are separate relationships. Define chronology and coordination in Section 3.

A repeated component retains one definition. Describe the repetition, changing inputs, and occurrence-specific behavior through control rules. Where the same behavior is used in multiple structural positions, register those positions separately and reference the shared behavior; specify any local differences without duplicating the entire definition.

## 4. Specify execution and control

Section 3 defines how control moves through the system. Identify the entry components, activation conditions, transitions, and the conditions under which the experiment completes.

For each transition, identify its scope, the component or system event it originates from, the condition that enables it, and the component or boundary it activates next. Use START, END, and PARENT-END as document markers for experiment entry, experiment completion, and completion of an enclosing component. These markers do not prescribe software events or API names.

Use a control-rule record when a relationship needs more detail than a transition entry. Assign R-001 and subsequent identifiers. Each rule must state its scope, when it applies, its inputs, and its operational effect. Component records reference rules by identifier.

Describe only the control mechanisms needed by the experiment. For applicable mechanisms, make the following details explicit:

- Ordering specifies which units follow which and which relationships must remain fixed.
- Repetition specifies the repeated unit, count or stopping condition, and how inputs or retained information change across repetitions.
- Selection or randomization specifies the eligible material, selection unit, sampling or ordering behavior, and constraints on the resulting arrangement.
- Conditional execution specifies the information evaluated, the evaluation point, and the behavior associated with each design-defined outcome.
- Concurrent activity specifies what overlaps, what remains active, and how the end of each activity affects the others.

These are descriptive prompts, not required component types or an exhaustive set of supported behaviors. Put specialized control details in a rule's extension when necessary. Define each rule in one place and reference it elsewhere.

## 5. Describe each component's technical behavior

Every component record uses the same core headings and labels shown in the output format.

**Responsibility** states the unit's operational job. Describe its function in the experiment system without discussing research motivation.

**Activation and inputs** states when the unit becomes active and what it consumes. Describe information by meaning, source, and availability, without defining program variables or data schemas. Include dependencies on materials, preceding results, shared settings, or external connections where relevant.

**Operation** describes the unit's behavior through numbered step entries. A step can represent an action, an ongoing behavior, or the coordination of subordinate components. State what triggers the action and how long it lasts or what determines its progression. Preserve applicable presentation constraints, accepted input meanings, timing reference events, units, and behavior following input. Refer to control rules for relationships already defined in Section 3.

**Completion and outputs** states what ends the unit, the result or effect it produces, and what receives or uses that result. Completion of a component and successful delivery of its data are separate events when the system requires them to be separate.

Expand technical detail according to the actual behavior. For instance, a component whose outputs affect later execution needs a clear description of when those outputs become available and how long they remain applicable. A component coordinating subordinate units needs their activation and completion relationships. Such detail belongs under the relevant core heading or a named extension.

Avoid generic restatements such as "perform the activity as described in DESIGN.md." An implementation agent must be able to follow the technical behavior using SCHEMATICS.md and its referenced materials.

## 6. Define resource and external relationships

Section 5 identifies resources and external capabilities used by the components.

Assign M-001 and subsequent identifiers to materials or material collections. State their content role, consuming components, and the technical requirements governing their use and availability. Reference supplied material locations when available. Reference the corresponding file under templates/ or assets/ when one exists.

Keep asset templates under templates/, following Template Schematics.md. SCHEMATICS.md must not contain asset schemas, reusable asset layout templates, or asset-production examples. Preserve presentation and usage constraints needed to define experiment behavior, and connect them to the relevant components.

Assign X-001 and subsequent identifiers to external connections. Describe each connection's responsibility, the information exchanged, its trigger, and its relationship to experiment progression. Specify the required behavior at the system boundary. Leave function signatures, endpoint design, request fields, and internal service implementation to the coding stage. Preserve externally imposed technical constraints when the author supplies them.

Resources and external connections do not automatically become executable components. Register a component when the experiment needs a controlled operation that uses them.

## 7. Define data acquisition, recording, and delivery

Section 6 specifies the information the experiment must obtain and retain. Assign D-001 and subsequent identifiers to data requirements. These identifiers refer to conceptual results, not output column names.

For each requirement, state the information's meaning, its producing component or event, the acquisition or calculation rule, its unit or response interpretation, and when a record is made. Define the level at which records are distinguished and the context needed to associate them with their origin. Describe that context semantically without designing a storage schema.

For a timing measurement, identify the starting and ending events. For a derived result, identify its source observations and calculation. If a result controls subsequent execution, reference the consuming component or rule.

Define delivery separately from acquisition. Identify the data being delivered, the triggering event, the required destination and format, and the completion behavior required by the design. Coordinate external delivery through the corresponding X identifier.

lab.js can log records for multiple nested components. Specify the required information and recording events without assuming that one design activity produces exactly one library record. Verify relevant behavior against the [data format reference](https://labjs.readthedocs.io/en/latest/reference/data%20format.html) and [data storage reference](https://labjs.readthedocs.io/en/latest/reference/data.html).

## 8. Apply the format and check consistency

Use the six output sections in their exact order and retain their fixed headings and record labels. Add detail using the expansion rules below. Do not reorganize the output around the original design sections.

Give independent items separate entries so that each can be understood and referenced clearly. Keep related details that describe one coherent item together. Each entry or labeled item may contain bullet lists or numbered subentries to organize its details, conditions, or steps. Avoid excessive fragmentation: separate sentences, settings, or steps within one coherent operation do not automatically require separate records or components. Create a separate component only when it meets the technical boundaries described in Section 3 of these requirements.

Before delivering, check that every registered component has a full record, containment is consistent, execution references resolve, and data consumers receive information after it becomes available. Check that shared rules and local behavior agree and that the technical decomposition preserves the experimental design.

Keep this review internal to the translation process. SCHEMATICS.md contains the resulting technical specification.

</response_requirement>

<response_format>

## Format rules

1. Use the exact title and six numbered section headings below. Keep the numbered subsection headings and all core headings within records.
2. Replace each example record with the actual records for the experiment. Repeat records using their document identifiers. Entries without document identifiers use sequential numbers within their containing section or component subsection. Order component records by the containment structure, placing parents before their children.
3. Use separate entries with the headings and labeled bullet points shown below. Keep the labels in their specified order and add as many entries as required. Each labeled item contains a specific technical statement or a document reference. Use a reference to a shared rule when a statement would otherwise be repeated. Use this entry format throughout the output, including extensions, without tables.
4. Retain the containing section or subsection heading when there are no applicable entries. Sections containing repeatable records may contain zero records. Do not add fictitious components, placeholder records, status labels, or explanatory notices to fill empty sections.
5. Add specialized detail under a heading named "Extension: [technical subject]", one heading level below its containing record or numbered subsection. Use level-four headings for extensions to component records and level-five headings for extensions to R, M, X, or D records. Extensions must identify their scope and may add labeled lists or further subheadings. They supplement the core structure and must not redefine its labels or duplicate its contents.
6. Use R, C, M, X, and D identifiers for document cross-references. SYSTEM, START, END, and PARENT-END are structural markers. None of these names dictates the code's organization.
7. Write precise natural language. Include technical values and rules at the level needed to define behavior. Do not include executable code, programming interfaces, variable declarations, storage-field definitions, or a source-file plan.
8. Bracketed text in the template provides writing instructions. Remove it from the completed output. The template's headings and labels describe the document structure, not the experiment's software data model.

## SCHEMATICS.md template

~~~markdown
# SCHEMATICS

## 1. Execution environment

### 1.1 Runtime and system boundary
[Describe the execution setting and the responsibilities performed within the
experiment. Identify relevant external responsibilities by X identifier.
Include the target lab.js version when the project specifies one.]

### 1.2 System constraints

#### Constraint [number]

- **Scope:** [SYSTEM or component identifiers.]
- **Technical requirement:** [State the applicable runtime, presentation, input, or other technical constraint.]

## 2. Component organization

### [C identifier]

- **Name:** [Component name.]
- **Parent:** [SYSTEM or parent C identifier.]
- **Technical responsibility:** [State the unit's operational job.]

## 3. Execution structure

### 3.1 Transitions

#### Transition [number]

- **Scope:** [SYSTEM or enclosing C identifier.]
- **From:** [C identifier or START.]
- **Trigger:** [Identify the event.]
- **Condition:** [State the condition, or "Always" for an unconditional transition.]
- **To:** [C identifier, END, or PARENT-END.]
- **Coordination:** [State the handoff or reference its R rule.]

### 3.2 Control rules

#### [R identifier]: [Rule name]
- **Scope:** [Identify the components or system boundary governed by this rule.]
- **Applies when:** [State the triggering event or interval.]
- **Inputs:** [Identify the information used and its sources.]
- **Behavior:** [Specify the operational rule, including its progression or termination conditions.]
- **Result:** [State its effect on execution or information available to components.]

## 4. Component specifications

### [C identifier]: [Component name]

#### Responsibility
[State the component's technical job and reference any shared behavior definition.]

#### Activation and inputs
- **Activation:** [Reference the incoming transitions or control rule and state preparation or availability requirements.]

##### Input [number]

- **Input or dependency:** [Describe the information, material, or capability.]
- **Source:** [C, M, X, D, or R reference, or an identified participant/system source.]
- **Use and availability:** [State how it is used and when it must be available.]

#### Operation

##### Step [number]

- **Trigger or condition:** [Identify the event or condition.]
- **Technical behavior:** [Describe the action, sustained behavior, or coordination.]
- **Timing or progression:** [State duration, reference events, or the event/rule that advances execution.]

#### Completion and outputs
- **Completion:** [State the conditions that end the component and reference the outgoing transitions or enclosing control rule.]

##### Output [number]

- **Output or effect:** [Describe the produced information or system effect.]
- **Availability:** [State when it becomes available and its applicable duration.]
- **Recipient or use:** [Reference the consuming C or R entry, D recording requirement, X connection, or system effect.]

## 5. Resources and external connections

### 5.1 Materials

#### [M identifier]: [Material or collection name]
- **Content role:** [Identify the material needed by the experiment.]
- **Used by:** [Reference consuming C identifiers.]
- **Usage requirements:** [Describe selection, presentation, loading, or other usage constraints, referencing R rules where appropriate.]
- **References:** [Identify the supplied material location or corresponding file under templates/ or assets/ when available.]

### 5.2 External connections

#### [X identifier]: [Connection name]
- **Responsibility:** [State the capability supplied outside the experiment.]
- **Connected components:** [Reference the C identifiers using this connection.]
- **Exchange:** [Describe the meaning and direction of information exchanged.]
- **Trigger:** [State when the interaction occurs.]
- **Progression:** [Describe how its result or completion affects experiment execution.]

## 6. Data recording and delivery

### 6.1 Data requirements

#### [D identifier]: [Result or observation name]
- **Meaning:** [Define the information being obtained.]
- **Producer:** [Identify the C entry and event that produce it.]
- **Acquisition:** [State the observation or calculation rule, measurement endpoints, units, or response interpretation as applicable.]
- **Recording:** [State when it is recorded, the level of detail retained, and the context that associates it with its origin.]
- **Use during execution:** [Reference consuming components or rules when this result affects later behavior.]

### 6.2 Delivery

#### Delivery [number]

- **Data:** [D identifiers or defined collection.]
- **Trigger:** [Identify the component/system event.]
- **Destination:** [Identify the destination and X connection where applicable.]
- **Required form:** [Describe the required organization or export format.]
- **Completion behavior:** [State the required behavior when delivery finishes.]
~~~

The following labels are conditional: "References" in a material record and "Use during execution" in a data record. Omit these labels when they have no applicable content. Retain all other record labels; populate them with the record's actual technical behavior. A factual statement that a unit has no input dependency or produces no retained data is permitted when it follows from its defined behavior. It must not be used to substitute for information absent from the design.

</response_format>

