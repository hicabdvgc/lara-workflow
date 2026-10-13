# Stage 3. Project folder structure specification

Use this structure for Stage 3 of [Behavioral Experiment Workflow.md](<../Behavioral Experiment Workflow.md>) to organize the experiment project and collected source materials. The structure also reserves locations for outputs produced in later stages. Existing concept and design documents belong at the project root.

Choose subfolders according to the actual study and its materials. The example subfolder names below are illustrative; create the applicable directories without assuming particular component types, media, participant groups, or result arrangements. Create documents at their corresponding workflow stages. Record actual file and directory paths in LIB.md and update it as the project changes.

Collect the materials required by DESIGN.md under sources/, preserving their contents, identities, meaningful order, and file associations. Compare the collection with the design's content and quantity requirements and resolve missing content or unclear associations with the author before formatting the affected materials.

## Project structure

ROOT_PATH

- CONCEPT.md --- This is the study concept developed during conceptualization.
- DESIGN.md --- This is the manually written design document for the experiment. 
- SCHEMATICS.md --- This is the structured technical specification derived from the experiment's design document. It describes the components, execution behavior, resources, and data relationships needed for implementation. It can also be used with LIB.md to examine the consistency of the experiment's files and functionality when changes occur.
- LIB.md --- This is a file containing the structure of the ROOT_PATH folder, it aims to act as an authoritative document outlining path to different files and directories. 
- experiment/ --- This is the folder that contains the main lab.js implementation of the experiment, including the executable file and all its functional components. 
- templates/ --- This is the folder that contains reusable asset structures, fixed content, and fillable slots for each distinct asset type required by the experiment. Share a template across compatible assets and create separate structures when their requirements differ. Presentation and randomization behavior are specified in SCHEMATICS.md.
	- asset_type_1/
	- asset_type_2/
	- asset_type_3/
	- ...
- sources/ --- This is the folder that preserves the original materials collected for the experiment. Keep source contents and associations intact while preparing completed assets under assets/. Organize source subfolders according to the supplied materials and the design.
	- collection_1/
	- collection_2/
	- ...
- assets/ --- This is the folder that contains the prepared textual or multimodal assets used by the experiment's components. Retain them here as verification material and to support rebuilding the experiment. Their inclusion or loading in the deployed experiment follows the technical specification.
	- com_1/
	- com_2/
	- com_3/
	- ...
- data/ --- This is the folder for locally retained experiment data. Use overall/, entries/, or another arrangement according to the design's result-handling requirements. Overall results may contain records collected across participants or conditions, while entries/ may contain records for individual sessions. When data is stored externally, its destination is specified in SCHEMATICS.md; this folder applies to any required local copies.
	- overall/
	- entries/
		- entry_1/
		- entry_2/
		- ...
- tools/ --- This is the folder that contains tools (e.g., for timestamp collection, csv transformation, etc.) that are not essential to the tests themselves, but are nevertheless crucial for the whole system to work. Each tool will get their own folder, acting as individual assets and connected to the overall system through encapsulated apis or ports. Never embed the tools directly in the experiment! Keep the experiment and the tools encapsulated within themselves.
	- tool_1/
	- tool_2/
	- ...
