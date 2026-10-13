# Stage 5. Asset template and formatting specification

Use this specification for Stage 5 of [Behavioral Experiment Workflow.md](<../Behavioral Experiment Workflow.md>). First establish reusable asset structures under templates/, then populate them from the collected materials under sources/ to produce completed assets under assets/. A request limited to template creation covers the first part; completion of Stage 5 also requires formatting and verifying the required assets.

**Note: Consult the following official references when creating templates. Verify the relevant asset formats and lab.js requirements against the documentation or source files.**

- [FelixHenninger/lab.js: Online research made easy](https://github.com/FelixHenninger/lab.js/tree/main)
- [lab.js task examples](https://github.com/FelixHenninger/lab.js/tree/main/tasks)
- [Library reference — lab.js documentation](https://labjs.readthedocs.io/en/latest/reference/index.html)
- [Examples & recipes — lab.js documentation](https://labjs.readthedocs.io/en/latest/recipes/index.html)
- [Documentation index — lab.js](https://labjs.readthedocs.io/en/latest/genindex.html)

<goal>

Use DESIGN.md and SCHEMATICS.md to create asset templates in the experiment's project-relative templates/ directory.

A template is an asset expressed in its intended format, with its content structure in place. Include fixed asset content already established by the design and fillable slots for content that will come from the user's loose materials. Later, an agent can populate that structure with the supplied text, documents, media, or file collections to produce completed assets under assets/.

The generated templates contain asset content and structure. Instructions for template creation and asset formatting belong in this guideline. Details about how components use an asset or its parts, including presentation behavior, timing, selection, responses, and execution order, remain in SCHEMATICS.md.

Choose a suitable format for each asset type. Templates may differ in structure across types and experiments. Every template must conform to the experiment's requirements while remaining a direct, reusable representation of the formatted asset.

</goal>

<response_requirement>

## 1. Read the experiment requirements

Read DESIGN.md and SCHEMATICS.md together. Identify the assets the experiment requires and the content and structural constraints those assets must satisfy. Use component and material references to establish coverage during preparation.

Consult all five official references above and follow the relevant documentation or source files for technical claims. Use an accessible official source when a linked page cannot be read. Verify compatibility with the specified lab.js version when applicable.

Use the experiment's technical requirements to choose the asset structure. Keep explanations of those requirements and of component behavior outside the generated templates. Do not add component-use descriptions or reproduce the experiment's execution specification inside an asset.

Preserve the design's content, quantities, meanings, and relationships. Choose formatting details where the design leaves them to the agent, without inventing experimental material or changing the experiment to suit a convenient format.

## 2. Identify the required template types

Create a template for each distinct asset structure needed by the experiment. Derive the types from the actual requirements; do not start from a predefined catalogue of component categories or lab.js features.

Share a template when several assets require the same structure. Create separate templates when their content structures differ materially. A component may require several asset structures, while a component with no prepared content requires no asset template.

Keep coherent assets together. Separate independent items into separate entries or files where appropriate. Use nested records, bullet lists, or numbered entries for related parts of one asset. Avoid splitting every sentence or property into its own template, and avoid packing unrelated items into one entry.

## 3. Construct the formatted asset

Choose the actual file format and arrange the asset in that format. The template must contain the structure that will be populated, rather than a prose description of how someone could create that structure.

Include the applicable asset elements directly:

- Preserve the asset's content sections, item boundaries, hierarchy, and meaningful order.
- Include concrete field names, content labels, or markup when they form part of the chosen asset representation.
- Group repeated or nested content according to the asset's actual relationships.
- Include identifiers, file references, and content metadata when they are part of the required asset data.
- Retain fixed wording or other fixed asset content supplied by the design.
- Put clear fillable slots where source-derived content will later be inserted.

Use self-descriptive field names and placeholder names so that the structure can be understood without a separate instruction document embedded in the template. Use a consistent placeholder convention within each asset format. Preserve the selected format's syntax.

Keep data that belongs to the asset distinct from instructions to the implementer. Item labels, content associations, and required item-specific annotations may be asset data. Statements telling a component when to load, display, select, score, or otherwise use those elements belong in SCHEMATICS.md.

Participant-facing instructions are asset content when the experiment requires them. Preserve that content, including directions addressed to the participant. Exclude agent-facing explanations about how to process or implement the asset.

## 4. Handle source content and fillable slots

At template creation, include actual content only when it is supplied or fixed by the experiment documents. Use placeholders for content expected from a later source batch. Do not fabricate examples of scientific material to fill the template.

Make each placeholder correspond to a specific content part. Represent repeating items through the appropriate repeated structure, keeping the parts of one item together. Preserve exact collection sizes when required; do not choose an experimental item count merely to illustrate the format.

When loose materials are supplied for formatting, the converting agent should apply the following working rules. These rules remain in this guideline and are not copied into the asset files:

1. Inspect the source contents and recognize individual items, groups, order, and associated files.
2. Match the source parts to the template's content slots using the design, schema, and the source's explicit organization.
3. Populate each coherent item, preserving supplied wording, meaningful formatting, labels, and relationships.
4. Preserve intentional repetitions. Derive content annotations only from supplied information or rules established by the experiment.
5. Write completed assets in the template's format and replace all fillable slots with actual content or the format's appropriate representation of optional absence.

Keep original source files intact. Do not silently discard items, rewrite experimental content, or guess required values. Preserve any source associations needed to maintain the identity and relationships of the formatted material.

## 5. Represent media and collections

Use the format and organization appropriate to the actual material. A template may consist of a content file, a structured collection with file references, or several related asset files.

For media supplied later, represent its place through the required content structure and clearly named reference slots. Do not manufacture empty or invalid binary files to stand in for real media. Keep accompanying metadata limited to information that belongs to the formatted asset.

Preserve relevant properties of source media. Cropping, resizing, recompression, recoloring, duration changes, or similar transformations must follow the experiment's requirements. A display-size requirement in SCHEMATICS.md does not by itself authorize permanent alteration of the source file.

Keep references consistent with the asset directory arrangement. Use portable relative references where appropriate and maintain filename case and associations between files. Preserve the distinction between several uses of one material and several distinct material items.

## 6. Keep the generated output limited to assets

Generated templates must contain the formatted asset structure, its fixed content, and its fillable slots. Do not include the following:

- Component mappings, consumer descriptions, or explanations of how asset parts are used.
- Runtime behavior, control rules, event handling, or experiment implementation code.
- Conversion procedures, source-reading instructions, or instructions to an agent.
- Format-definition essays, field dictionaries, compatibility explanations, or usage guides.
- Validation checklists, qualification statements, unresolved questions, or follow-up sections.

Do not create TEMPLATE.md instruction packages, README files, or a template index as part of this output. A Markdown file is appropriate when Markdown is the selected format of the asset itself; its contents must then be the asset's own headings, entries, and content slots.

Use filenames and directories to organize templates. Avoid introducing descriptive documentation files in place of the assets the user requested.

## 7. Check the templates before delivery

Review each template against DESIGN.md and SCHEMATICS.md. Confirm that the required content can be represented, fixed content is preserved, fillable slots are clear, and the structure respects the asset's required relationships.

Check syntax, encoding, escaping, identifiers, references, and the coherence of repeated entries as applicable to the selected format. Ensure that placeholders remain visibly distinguishable from actual content and that their representation does not invalidate the file format.

Confirm that the templates cover the required asset types without duplicating compatible structures or creating templates for components that need no prepared assets. Keep these checks internal to the creation process.

When templates are later populated, check that the completed assets contain the required source-derived content and valid file references, with no unfilled slots. Preserve this separation between reusable templates and completed assets.

</response_requirement>

<response_format>

## Output location

Save the actual template files under templates/, relative to the experiment root. Group them in subdirectories by asset role when useful. Use filenames and extensions that match the asset format.

Completed source-derived assets belong under assets/ when the user requests the later formatting stage. Creating the templates alone does not require producing completed assets.

## File contents

Each generated file must directly represent an asset in its chosen format. Its structure may contain:

- Fixed content established by the experiment.
- Fillable slots for source-derived content.
- Repeated or nested entries belonging to the asset.
- Required content identifiers, annotations, and references to associated asset files.

Include each element only when the asset requires it. Do not impose the same headings, fields, or record structure on every asset type.

Use the native syntax of the selected format. For assets represented in Markdown or plain text, use meaningful headings and separate labeled or numbered entries, with lists inside coherent entries where useful. Avoid Markdown tables.

## Output boundaries

Return the template files and, when formatting is requested, the completed asset files themselves. Do not wrap them in a template-specification document or append explanations of their preparation, validation, or use. A brief delivery message may identify the files that were created.

The goal, requirements, and format sections in this guideline govern the creation process. They must not be copied into the generated asset templates.

</response_format>

