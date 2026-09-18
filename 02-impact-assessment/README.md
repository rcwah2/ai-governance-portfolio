AI Impact Assessment - System 3 - Autonomous Diabetic Retinopathy Screening
AI Governance Portfolio — Artifact 2

This is Artifact 2 of my AI Governance Portfolio, following the AI System Inventory (Artifact 1).

Part 1 — Why move from inventory to impact and risk?

In Artifact 1, I focused on understanding the system itself: what it does, how it operates, who uses it, what data it relies on, and where human involvement exists.

That provides a foundation. But an inventory by itself does not tell us whether the characteristics of a system create meaningful risk.

Artifact 2 asks a different question:

What are the potential consequences of how this system operates, and what should we do about them?

For this assessment, I am continuing with LumineticsCore, the autonomous diabetic-retinopathy diagnostic system from the previous system inventory.

I am using the NIST AI Risk Management Framework as the primary reference point. I am not treating NIST AI RMF as a checklist. I am using its GOVERN, MAP, MEASURE, and MANAGE functions to help structure the analysis.

The objective is also not to start from the assumption that the AI is dangerous. A useful assessment needs to consider the value the system is intended to create alongside the potential consequences when the technology, workflow, or surrounding controls do not operate as intended.

Artifact 1 described the system. Artifact 2 examines why the characteristics of that system matter.

Part 2 — The 7-Step Impact & Risk Assessment

| Step | Assessment Area | What I Looked At | Key Findings | Governance Implication |
|---|---|---|---|---|
| 1 | Intended Benefit | What value is the system intended to create? | Point-of-care diabetic-retinopathy screening, earlier identification of patients requiring follow-up, and less dependence on a separate specialist visit for the initial diagnostic assessment. | Risk should be considered alongside the value the system is intended to create. |
| 2 | Affected Stakeholders | Who could benefit, be burdened, or be harmed? | Patients, primary-care providers and staff, eye-care specialists, healthcare organizations, the AI developer, and payors or health systems. | The impact extends beyond the individual patient. The AI operates within a larger clinical and organizational environment. |
| 3 | Impact Pathways | How could an AI output translate into a real-world consequence? | A false negative could delay referral or treatment. A false positive could create unnecessary referral, cost, anxiety, and use of specialist resources. | A generic risk such as "incorrect diagnosis" does not explain enough. The assessment needs to follow the result through the workflow. |
| 4 | Controls & Residual Risk | What safeguards already exist, and what risk remains? | Defined use case and patient population, image-quality requirements, clinical workflow, regulatory authorization, and specialist follow-up following referral. | The existence and effectiveness of controls affect the actual residual risk. |
| 5 | Human Oversight | Where does human judgment enter the process? | Humans capture images, communicate results, manage the clinical process, and provide specialist follow-up. The AI diagnostic determination itself does not require routine specialist verification before affecting the pathway. | Human involvement should not automatically be interpreted as human verification of the AI decision. |
| 6 | Evidence & Uncertainty | What conclusions can reasonably be supported? | Clinical validation, performance evidence, eligibility requirements, controls, and known limitations can support the analysis, but uncertainty remains. | The assessment should make uncertainty visible rather than imply more precision than the evidence supports. |
| 7 | Decision Rights & Risk Response | Who determines whether the remaining risk is acceptable? | Responsibility may involve healthcare organizations, clinical leadership, physicians, the developer, executives, and regulators depending on the decision. | The assessment should provide decision-ready evidence to those who actually have authority to act on the risk. |

Part 3 — What stood out to me?

One thing became particularly clear as I worked through the assessment: identifying a risk is not the same as understanding its impact.

Consider an incorrect diagnostic result.

A false negative could mean that a patient who should have been referred continues through the normal care pathway. If disease is present, that could delay diagnosis, referral, or treatment.

A false positive creates a different consequence. The patient may undergo an unnecessary specialist referral, incur additional cost, experience anxiety, and consume specialist capacity.

Both originate from the same broad risk—an incorrect AI result—but their consequences are different.

That is why an entry such as "Risk: inaccurate diagnosis" is not enough for me.

The governance value comes from tracing the risk far enough to understand what actually happens next.

This is also where the system inventory becomes useful. The inventory established how the system works. The impact assessment uses that understanding to follow an AI result into the real-world process surrounding it.

Part 4 — Human oversight was more complicated than it first appeared

The question of human oversight also became more nuanced.

It is common to ask whether an AI system has a "human in the loop." But I do not think that question tells us enough here.

Humans participate throughout the LumineticsCore workflow. Clinical personnel capture the images, providers communicate results, specialists become involved when referral occurs, and the healthcare organization manages the surrounding clinical process.

However, human participation does not necessarily mean that a specialist independently verifies the AI diagnostic determination before it influences the patient pathway.

Human participation is not the same as human verification.

For me, the more important governance issue is understanding where human judgment enters the process, whether someone has the ability and authority to intervene, and what happens when the AI produces an incorrect result.

That provides much more information about actual oversight than simply marking Human-in-the-loop: Yes.

Part 5 — Avoiding false precision

Another issue I considered was whether to assign numerical risk scores.

A traditional risk assessment might assign a likelihood of 3, severity of 5, and calculate a risk score of 15.

That can be useful when an organization has a defined methodology, consistent scoring criteria, and sufficient evidence to support the inputs.

But without those things, a number can create an impression of precision that the underlying evidence does not justify.

For this assessment, I would rather make explicit what is known, what evidence supports the conclusion, what controls are already operating, and what uncertainty remains.

If additional evidence would materially change the assessment, that should also be visible.

A risk assessment should make uncertainty visible, not hide it behind a number.

Quantitative scoring can come later when there is a defensible basis for it.

Part 6 — Preliminary assessment

I would not reduce LumineticsCore to a single high-risk or low-risk designation based on this exercise alone.

The more useful conclusion is that the system has meaningful clinical impact because an autonomous diagnostic determination can influence whether a patient moves into specialist care.

That places particular importance on diagnostic performance, patient eligibility, image quality, the referral process, monitoring, accountability, and the evidence supporting continued use.

But those risks also need to be considered alongside the reason the system exists.

LumineticsCore is intended to make diabetic-retinopathy screening more accessible and allow patients who need additional care to be identified within the primary-care environment.

The governance question therefore is not whether autonomous diagnostic AI is inherently good or bad.

It is:

What can happen, how significant could the consequences be, what controls reduce those risks, what uncertainty remains, and who has authority to decide whether the remaining risk is acceptable?

That is the transition I wanted to demonstrate with Artifact 2.

The system inventory told me what the system is.

The impact and risk assessment begins to tell me why those characteristics matter.

Part 7 — What comes next?

The next artifact moves from understanding consequences to examining what the system is actually capable of doing and the authority it has been given.

Artifact 3 — Authority, Capability & Autonomy Assessment

The central question becomes:

What can this AI system actually do, what authority has it been given, and where should the boundaries be?

That begins moving the portfolio from understanding risk toward determining what governance controls may be appropriate.
