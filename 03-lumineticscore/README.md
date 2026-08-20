# Artifact 3: LumineticsCore — AI Governance Case Study

Third system in the AI governance portfolio. Same method: pick one system, argue through it field by field, no template shortcuts.

## Why this system

I have extensive experience in healthcare. This system also raises a governance question I haven’t seen addressed elsewhere: what “autonomous diagnosis” actually means once you trace human oversight through the system. The FDA calls this diagnostic. But no one — PCP or ophthalmologist — checks the model’s work before it drives a referral decision.

## Purpose

LumineticsCore (formerly IDx-DR) is deployed in select primary care offices. It screens adult diabetic patients for more-than-mild diabetic retinopathy at the point of care. Fundus camera images go in; a diagnosis comes out, with no ophthalmologist review. That’s a different process than the normal path. Normally the PCP refers the patient out, and a separate eye-care specialist performs the exam and makes the diagnosis. Here the diagnosis happens in the PCP’s office, before any specialist is involved. It’s a supplemental screening option, meant to catch patients who might otherwise miss or delay that separate exam. A positive result triggers immediate referral to an eye-care provider.

## Jurisdiction

Single-jurisdiction. IDx-DR is deployed only in U.S. primary care offices. Every patient encounter happens in the U.S. Every regulatory question falls under the FDA, through CDRH’s De Novo/510(k) pathway. There’s no cross-border exposure.

## Risk Tier

High. There are two ways this system can be wrong: a false positive or a false negative. A false positive means the system flags retinopathy that isn’t there. That sends the patient to an ophthalmologist for a dilated exam they didn’t need. It costs the patient time and an extra appointment, and the specialist visit itself corrects the error. The risk stops there. A false negative is the dangerous direction. That’s the system saying “no retinopathy” when disease is present. It delays referral and lets retinopathy progress toward vision loss, undetected. The patient bears that burden directly. There are some safety nets: the next annual screening, patient-reported vision changes, routine device maintenance and recalibration. None of those catch the error at the point it’s made.

## Model Type

Deep-learning computer-vision algorithm (CNN) trained on retinal fundus images to detect signs of more-than-mild diabetic retinopathy and output a binary result. The deployed system has no explainability layer. The primary care physician receiving the result isn’t trained to read fundus images. The ophthalmologist who is trained never sees the images, only the patients referred out after a positive result.

## Human Oversight

The PCP reviews the result before it reaches the patient. That review is procedural, not clinical — confirming the test completed, the image was gradable, and deciding whether to refer. The PCP knows diabetic retinopathy as a disease and knows a positive result is serious. The PCP does not read the fundus image. That’s a separate, trained skill, and here the AI does it instead of a person. No one evaluates the images during or right after the test. The only image-level check happens later, if the patient is referred out and completes that visit.

## Data Sources

Two fundus images per eye, taken at the current visit. That’s the only input the model uses. There is no comparison against the patient’s own prior images — the system has no memory of past visits. The model itself was trained separately, before deployment, on a dataset of fundus images collected and graded by ophthalmologists. That training data shapes what the model has learned to detect, but it plays no role in any individual patient’s result — each screening is judged fresh, against the trained model, not against that patient’s history.

The model does not train continuously. Once cleared, the algorithm is locked. Any change to it that could affect the false-positive or false-negative rate requires a new FDA submission before it can be used commercially. That’s happened once: a 2021 update improved the system’s ability to read low-quality images and its processing speed, but left the diagnostic algorithm itself unchanged.

The training dataset’s size, source, and grading methodology aren’t disclosed. FDA guidance calls for that information to be shared with users. In practice it mostly isn’t: a review of FDA-cleared AI device submissions found fewer than 2% report their exact training dataset source. Manufacturers can withhold that data as a trade secret or confidential commercial information, a protection recognized under FOIA. FDA sees the training data during review. The public sees a summary. Proprietary designation closes the second channel, not the first.

Post-market accuracy validation — independent testing of the deployed system’s real-world performance, separate from the pivotal trial used for clearance — is not an FDA requirement for this device. It happened anyway, but not where this artifact’s jurisdiction applies. The independent studies that exist were run in Poland, Switzerland, and Germany. None turned up testing the U.S. deployment specifically. LumineticsCore also carries CE marking for the European market, a separate regulatory track from its FDA clearance, so those studies may not even be evaluating the same cleared version used in U.S. primary care offices. Whether an algorithm checked against Polish, Swiss, and German patient populations performs the same way in U.S. primary care patients is an open question, not a confirmed fact.

That’s one system, six fields. The finding that stuck with me: “autonomous diagnosis” sounds like a bigger claim than what oversight actually delivers. The PCP reviews the result, but doesn’t check the model’s work. The ophthalmologist could check the model’s work, but never sees it unless the patient is already referred out. No one checks the model’s output before the referral decision.

Next up: system four.
