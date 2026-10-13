# Project instructions

## Scope

This repository develops LARA Workflow, a lab.js based AI workflow for behavioral experiment design & deployment, with skills, personas, and specifications. Implement the functionality requested for the current task, using the established catalog and workflow.

## Project references

- Read [Behavioral Experiment Workflow.md](<Behavioral Experiment Workflow.md>) for the development stages relevant to the task.
- Read the applicable entries in [Personas and Skills Specification.md](<Personas and Skills Specification.md>) for skill responsibilities and persona boundaries.
- Use the relevant specification under `workflow-templates/` when producing or implementing its corresponding output.

## File organization

- Implement each skill in `.agents/skills/<catalog-skill-name>/`. Add a valid `SKILL.md` when implementing that skill and remove its `.gitkeep` once the directory contains real files.
- Place persona definitions under `personas/<persona-name>/`. A persona describes task responsibilities; its existence does not request autonomous agent delegation.
- Add supporting files when the skill or persona actually requires them. Use portable relative paths for repository resources and update affected links when moving files.
- Preserve the scope and methodological neutrality of the specifications. Resolve experimental ambiguities with the researcher and verify uncertain technical claims against official sources.

## Human testing

The researcher and human testers perform the repeated experiment runs. Existing skills handle supplied observations, logging, and revisions. Instruction planning helps the researcher prepare embedded instructions or separate briefing materials; it does not guide or organize human test sessions.
