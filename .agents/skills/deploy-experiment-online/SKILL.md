---
name: deploy-experiment-online
description: Deploy a released behavioral experiment to JATOS or another selected online host. Use to configure participant entry, session execution, assets, results, and host-specific operator instructions.
---

# Deploy Experiment Online

Apply the Coder perspective to Stage 11 of the [experiment workflow](<../../../Behavioral Experiment Workflow.md>).

## Establish the host and deployment scope

Read the release artifact, deployment instructions, selected hosting environment, available authorized access, and participant-entry, execution, and result requirements. Use relevant design and technical documents or equivalent explicit requirements. Identify the release and the destination study or installation, including whether the request creates a deployment or updates one.

JATOS is the workflow's preferred hosting option. Follow an explicitly selected alternative. If no destination has been established, clarify the actual host and access details before dependent operations; preference for JATOS supplies no server, account, installation, or publication permission.

Use the authorization already provided for the requested deployment. Prepare the artifact and configuration before seeking any missing permission for an external change. Keep participant recruitment and distribution of study invitations outside the deployment task unless explicitly requested.

## Prepare the host integration

Inspect the existing release integration before changing it. Verify the selected host's current requirements against official documentation or source for the deployed versions. For JATOS, establish the supported lab.js integration, import or upload format, study and component configuration, participant entry mechanism, session lifecycle, result submission, and completion behavior relevant to this study. For another host, establish the corresponding mechanisms it actually provides.

Map those mechanisms to the design's procedure and results. Identify how the entry point starts the intended experiment, how required assets and supporting services are reached, and how session results become available to the operator. Preserve required allocation, identity associations, component order, and completion rules. Hosting choices must not silently change scientific behavior.

Prepare necessary host-specific files or configuration within the existing project arrangement. Use [Experiment File Structure.md](<../../../workflow-templates/Experiment File Structure.md>) when locating and recording those outputs; resolve the reference relative to this skill directory. Keep credentials in the intended access mechanism and omit them from distributable files and operator documentation.

## Deploy and check

- Upload, import, or install the prepared artifact through the host's supported mechanism. Apply configuration to the authorized destination, preserving unrelated studies and existing result records.
- Configure participant entry, runtime connections, asset access, result delivery, and completion according to the verified integration and study requirements.
- Inspect the host's response to each mutation before retrying an ambiguous upload or import. Establish whether it succeeded before creating another deployment or replacing an existing one.
- Open the actual participant entry and check that it starts the intended release with its required assets and connections. Record initial checks and any observed integration failures.
- Use [test-online-deployment](../test-online-deployment/SKILL.md) for complete verification through session completion and result retrieval. A completed upload establishes the upload outcome; deployment verification requires actual execution evidence.

If access or a required service is unavailable, retain prepared deliverables and state the specific operation and verification still pending. Record corrections and retest the affected deployed paths.

## Deliver

Provide the deployed study identity, participant entry information, release identity, host configuration details needed by the operator, and instructions for locating and retrieving results. Include initial check outcomes and full online test evidence when performed. Update affected deployment documentation, technical records, and the existing `LIB.md`. Distinguish successful deployment operations from verification that remains outstanding.
