AI Policy-to-Controls Matrix - System 3 - Autonomous Diabetic Retinopathy Screening
AI Governance Portfolio — Artifact 3

This is Artifact 3 of my AI Governance Portfolio, following the AI System Inventory (Artifact 1) and the Impact Assessment (Artifact 2).

The first artifact in this portfolio documented LumineticsCore, an autonomous AI system used for diabetic-retinopathy testing at the point of care. The second examined how its diagnostic result could affect a patient's care pathway, where people remain involved, and what uncertainty remains.

Artifact 3 asks what happens after those risks and impacts are understood. If a healthcare organization has policies covering human oversight, patient safety, performance monitoring, incident response, and accountability, what controls would put those commitments into practice for this system?

That question changes the discussion. An approved policy communicates the organization's intentions. It does not tell a clinic how to confirm that a patient is within the system's intended population, what to do when image quality is insufficient, how to document a referral, or who can suspend use when the process is not operating as expected.

The policy becomes useful when it changes the workflow.

## The system and the workflow

LumineticsCore autonomously detects more than mild diabetic retinopathy in adults with diabetes who have not previously been diagnosed with diabetic retinopathy. The current product information identifies the Topcon NW400 as the indicated camera.

A trained operator captures two fundus images of each eye and submits them to the system. The documented outputs include detection of more than mild diabetic retinopathy with referral to an eye-care professional, no detection with rescreening in 12 months, and insufficient image quality.

The diagnostic determination does not require a specialist to review the images before the result is returned. That autonomy makes the surrounding operational controls especially important. People still determine whether the patient is eligible, acquire the images, communicate the result, arrange follow-up, respond to exceptions, and decide whether continued use remains acceptable.

This artifact is a governance design exercise for a healthcare organization using the system. It is not an audit of Digital Diagnostics, a description of the company's internal controls, or clinical advice. An actual implementation would need to follow the current labeling, instructions for use, applicable requirements, and the healthcare organization's approved clinical procedures.

## The first control begins before the images

Consider a policy commitment that AI systems will be used only for their approved purpose and population.

For LumineticsCore, that commitment must enter the patient-selection process. The organization needs a defined way to confirm that the patient meets the applicable eligibility criteria before the exam begins. The control also needs a response when the criteria are not met. Continuing with the AI exam cannot be the default simply because the equipment is available.

Evidence might include the eligibility fields completed for the encounter and the version of the criteria used. Effectiveness testing would go further by sampling records and determining whether ineligible patients were prevented from entering the autonomous diagnostic pathway.

A completed field shows that someone recorded an answer. Testing shows whether the control protected the boundary.

## Image quality is part of governance

The system depends on retinal images captured by an operator. Image acquisition is therefore part of the control environment rather than a preliminary technical step.

A policy requiring competent use could translate into role-based training, documented qualification, use of the indicated equipment, and a defined process for insufficient-quality results. The organization would also decide when another capture should be attempted and when the patient should leave the autonomous pathway for a different form of care.

The evidence may show that an operator completed training and that the system returned an image-quality result. An effectiveness review would examine whether operators consistently followed the process and whether repeated quality failures were investigated by location, equipment, or operator.

## Human oversight surrounds the autonomous result

Artifact 2 raised an important distinction. Human participation is not the same as human verification.

People participate throughout this workflow, but the autonomous diagnostic result is not routinely created by a specialist overread. A policy that simply requires a human in the loop would obscure how the system actually operates.

A more accurate control design identifies the decisions people still own. Staff confirm eligibility and capture the images. The care team communicates the result and follows the required pathway. A designated owner reviews incidents, monitoring results, and changes. An authorized leader can restrict or suspend use when evidence no longer supports continued operation.

That is meaningful oversight because it defines authority and intervention points without pretending that a clinician independently verifies every AI diagnosis.

## Illustrative controls for the healthcare organization

The following examples show how broad policy commitments could be translated for this use case. The exact owners, thresholds, frequencies, and records would need approval within the deploying organization.

| Control area | Illustrative control activity | Evidence and response |
|---|---|---|
| Patient eligibility | Confirm that the patient meets the current indications and organizational criteria before images are captured. | Retain the eligibility record. Route patients outside the criteria to the approved alternative process. |
| Operator and equipment | Permit trained operators to use the indicated equipment and follow the approved image-acquisition procedure. | Retain training and equipment records. Restrict access when qualification or equipment status is not current. |
| Image quality | Follow a defined process when the system reports insufficient image quality, including limits on repeat attempts and an alternative pathway. | Record attempts and disposition. Investigate repeated failures and suspend the affected workflow when necessary. |
| Results and follow-up | Communicate the result and complete the approved referral or rescreening workflow associated with that result. | Retain the result and follow-up record. Escalate missed or delayed actions under the clinical process. |
| Operational monitoring | Monitor agreed measures such as unusable-image rates, workflow completion, incidents, and material deviations from intended use. | Review trends against approved thresholds. Open corrective action or restrict use when limits are exceeded. |
| Changes and incidents | Review material changes to the system, labeling, equipment, integration, or clinical workflow before continued use. | Retain the change or incident decision. Give an authorized owner the ability to pause or deactivate the workflow. |

## Evidence is not the same as effectiveness

A policy-to-controls matrix needs both.

A training record can show that an operator completed a course. It does not establish that the operator consistently captures usable images. A referral order can show that an action was entered. It does not show whether the workflow identifies uncompleted referrals and responds to them. A monthly report can show that monitoring occurred. It does not show whether the organization acted when results moved outside an approved threshold.

For each control, I would ask two separate questions. What evidence shows that the required activity occurred? How will the organization determine whether the control achieved its objective?

Separating those questions helps prevent governance from becoming a collection of completed forms.

## Bias findings need an operating response

This also connects Artifact 3 to the recent bias series.

If monitoring or assessment identifies a meaningful difference in image-quality failures, diagnostic performance, access, or follow-up across relevant groups, the finding needs an operating path. The organization must know who reviews it, what additional evidence is required, who can approve corrective action, and who can restrict continued use.

The threshold cannot be invented after an uncomfortable result appears. The method, decision rights, and escalation path should be established before the organization depends on the control.

Finding a difference creates information. Governance determines what happens because of it.

## The policy must reach the patient workflow

The progression across these three artifacts is now clearer.

Artifact 1 documented what LumineticsCore does. Artifact 2 traced how an autonomous result could affect the care pathway. Artifact 3 translates policy commitments into controls around patient selection, image acquisition, results, follow-up, monitoring, change, and intervention.

The matrix does not prove that every proposed control is appropriate or effective. It makes the questions visible so the healthcare organization can assign owners, approve thresholds, collect evidence, test performance, and respond when the workflow falls outside its intended boundaries.

That is the practical test of an AI policy. Can the organization show how the commitment changed what happens during an actual patient encounter?

Published as the third article in the AI Governance Portfolio series on [Substack](https://rwahai.substack.com), following the [AI System Inventory](https://rwahai.substack.com/p/artifact-3-ai-system-inventory-autonomous) and the [LumineticsCore Impact Assessment](https://rwahai.substack.com/p/ai-impact-assessment-system-3-autonomous): [AI Policy-to-Controls Matrix - System 3 - Autonomous Diabetic Retinopathy Screening](https://rwahai.substack.com/p/ai-policy-to-controls-matrix-system)
