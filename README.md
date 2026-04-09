
PA Confidence Score & Triage UI

The PA Confidence Score reduces staff review time from 4.5 minutes to under 90 seconds for 53% of submissions, while surfacing the exact intervention needed on the remaining 47%, before a single PA is submitted to a payer.
This report includes the problem statement, prototype built, the evidence base, and the business impact at scale.

Why this problem exists
Prior authorization is a gatekeeping mechanism health insurers use to control costs. In principle it is a reasonable check. In practice it has become one of the most damaging administrative failures in American healthcare creating friction that harms patients, burns clinical staff, and costs the system hundreds of billions of dollars annually.

The PA burden,US healthcare system
Source
300 million+ PA requests processed annually
CMS / AMA 2023
$528 billion annual administrative waste in US healthcare
AMA Prior Authorization Survey 2023
4 to 14 days average time for a PA determination
AHIP / CoverMyMeds Evidence Report 2023
13+ hours per week physicians spend on PA tasks
AMA Prior Authorization Survey 2023
15–30% first-pass denial rate depending on drug class
CoverMyMeds Evidence Report 2023
94% of physicians report PA causes treatment delays
AMA Prior Authorization Survey 2023
25% patient abandonment rate per PA delay event (specialty drugs)
Avalere Health 2023
80%+ of denied PAs are ultimately approved on appeal  most denials are procedural, not clinical
AMA 2023

Who bears the pain
Patients: wait 7–14 days for a medication they need now. 1 in 4 abandon treatment during this window. For OUD patients on buprenorphine, a delay is not an inconvenience,  it is a relapse risk.
Clinical staff: PA coordinators spend 4–6 hours per day on PA-related tasks at a 50 PA/day clinic. This is administrative overhead the AI was supposed to eliminate.
Prescribers: 33% report a patient experienced a serious adverse event directly attributable to a PA delay. Every denial for a missing data element was preventable.
Provider organisations: each denied PA costs 4–7 hours of appeal time, risks losing the prescription entirely, and creates a measurable revenue gap from uncaptured specialty drug prescriptions.

Problem Statement 
WHO
Clinical support staff (PA coordinators, nurses) at multi-provider clinics processing 50+ PAs per week
PROBLEM
The AI-generated PA answers are accurate for common drug/payer combinations, but fall apart on edge cases, unusual step therapy criteria, rare payer portals, or newly updated formulary requirements. Staff spend 60–80% of their review time on the 20% of PAs where the AI is weakest, and they have no way to know in advance which submissions will require heavy edits.
WHY IT MATTERS
The value of the human review checkpoint degrades if staff can't triage. A PA coordinator reviewing 20 AI-generated submissions of equal apparent confidence is doing full-effort reviews on all 20, eliminating the efficiency gain. Approval rates for edge-case PAs remain lower than they should be because staff aren't equipped with the right information to intervene correctly.
WHY NOW
As Develop Health scales to more drug classes and payer combinations (especially GLP-1s with new payer criteria in 2025–2026), the long-tail of edge cases grows faster than the AI's training data. The AHIP 2026 real-time PA commitments also mean that payer criteria are being restructured, creating a new wave of edge cases.
WHY DEVELOP HEALTH
Develop Health already has the outcome data. Every PA that was submitted, every determination returned, every denial reason, this data can train a confidence scoring system. No competitor has this closed-loop data at the payer-drug-plan combination level. This is a defensible, data-network-effect moat.

Why existing solutions have not solved it
Legacy ePA hubs (CoverMyMeds, Surescripts) route electronic PA requests but cover only 80% of payers and do not generate clinical answers,  a human still fills the form. Neither system tells a PA coordinator which submissions are at risk before they are submitted, and neither one learns from the outcomes of past submissions.
The PA crisis is not a routing problem. It is a clinical intelligence problem. No competitor is solving it at the answer-generation and risk-prediction layer. That is where Develop Health's data asset creates an asymmetric advantage.
2) The Current User Journey: For detailed User journey refer  page 1 & 2 of (Link)
3) The Specific Gap: AI Without Triage Intelligence
Develop Health has solved the hard part of PA automation: connecting to 99%+ of payers, selecting the right form, generating AI-drafted clinical answers, and submitting across every channel. What it has not yet solved is the step that sits between AI generation and payer submission, the human review queue.

Today that queue is a flat list. Every PA lands in it at equal weight. A submission for semaglutide to UnitedHealth with complete documentation and a 94% historical approval rate sits next to a submission for the same drug to Humana with missing A1C data and a 48% historical approval rate. Both PAs look identical in the queue. The coordinator opens them in order and spends 4.5 minutes on each.
The AI automated the work of generating a PA. It did not automate the judgement about which ones are ready to go and which ones will fail. That judgement gap is where 4.5 minutes per PA disappears,and where 15–20% of avoidable denials originate.
What the coordinator cannot see today
Which PAs have a high historical approval rate for this exact drug/payer/plan combination and are safe to approve quickly.
Which PAs are missing a specific documentation element the payer will deny for, and what that element is.
Which PA answers may be based on outdated payer step therapy criteria that changed since the AI was last trained.
Which submitted PAs are at high risk of denial where proactive intervention is still possible.

None of these questions require new data. Develop Health already has the historical PA outcomes, the payer criteria, and the AI answer quality signals to answer all four. The gap is a product gap,these signals have not been surfaced in the review workflow.
Solution: PA Confidence Score & Triage UI
CONCEPT
An AI-generated confidence score and visual triage layer on the PA review queue, so staff can review high-risk submissions first and breeze through high-confidence ones in seconds.
JOB TO BE DONE
When I review my PA queue, I need to know which submissions need my attention and which I can approve in one click, so I can protect my time for the cases where my judgment actually changes the outcome.
KEY FEATURES
•      Each PA in the review queue gets a confidence score (0–100) based on drug/payer/plan combination, historical approval rate, completeness of clinical documentation, and AI answer quality.
•      Color-coded triage: Green (approve in 1-click), Yellow (review AI answer), Red (intervention needed, with specific flag: 'Missing prior therapy documentation for Step 2').
•      Explainability card: For Yellow/Red PAs, a 3-line explanation of why confidence is low and what data would improve it.
•      Bulk approve mode: Staff can approve all Green PAs with a single action, with a confirmation screen showing the count.
•      Feedback loop: Staff disagreement with AI score (editing an answer, changing a Red to approved) trains the model. Logged and reviewed by the PM in a weekly eval report.
WHY DEVELOP HEALTH
Develop Health already has historical PA outcomes data of drug/payer/plan/denial-reason granularity to train this model. The EHR integration provides documentation completeness signals. No new data sources needed, this is a product layer on existing infrastructure.
SUCCESS METRIC (90 days)
Time spent per PA review drops from avg. 4.5 minutes to <90 seconds for Green-tier submissions (measured via session analytics). Overall PA processing throughput increases by 30%+ within 60 days of launch.

4)The Business Cost of This Gap
Staff time consumed,by clinic size
Clinic size
PAs/day
Review hrs/week before
Review hrs/week after
Hours saved/week
Small  (1–3 providers)
15
5.6 hrs
2.3 hrs
3.3 hrs  (59%↓)
Mid  (4–10 providers)
50
18.8 hrs
7.7 hrs
11.1 hrs  (59%↓)
Large  (10+ providers)
150
56.3 hrs
23.1 hrs
33.2 hrs  (59%↓)
Basis, After: Green 30s, Yellow 2.5min, Red 7min. Mix: 53% Green / 27% Yellow / 20% Red
—
4.5 min avg
Tiered by confidence score
—

The renewal risk
When a clinic head of operations sits down for contract renewal, they ask: what has this platform measurably improved? Throughput speed is table stakes. The question at year two is approval rate improvement. Without the confidence score and its upstream feedback loop, Develop Health cannot show a causal link between its platform and a clinic's approval rate. That is a retention risk as contracts mature.
The pharma expansion opportunity
A GLP-1 drug with 10,000 active PA submissions per month and a 2 percentage point approval rate improvement represents 200 additional fills per month. At $800 average brand revenue per fill that is $160,000 per month in recovered prescription revenue, revenue a pharma brand would pay a hub service to capture. Develop Health captures it as a byproduct of its core platform.
The confidence score is the mechanism by which Develop Health converts its routing and submission infrastructure into a clinical intelligence platform. That conversion justifies expansion pricing, pharma revenue, and second-year retention.


5) The PA Confidence Score and Triage UI
When a PA enters the review queue, the system scores it 0–100 using four signals: historical first-pass approval rate for that exact drug/payer/plan combination; documentation completeness against payer-required elements in the patient EHR; AI answer quality and internal consistency; and payer criteria freshness. The score assigns a tier. (Also refer section 2 of Link)

Tier
Score
Staff action
Target review time
GREEN
75–100
Bulk approve. One click for all Green PAs.
Under 30 seconds total
YELLOW
40–74
Review AI answer. Specific flag for lowest sub-score.
2–3 minutes
RED
0–39
Do not submit. Fix flagged issues. Exact missing data listed.
5–10 min (intervention)


What makes the score defensible is the data it runs on. Develop Health's historical PA outcomes database, every submission, determination, and denial reason at drug/payer/plan granularity, is the training asset. This data does not exist in any competitor's system. The more volume the platform processes, the more accurate the score becomes.
What the staff sees: a triage queue sorted by risk. Red cases first, then Yellow, then Green. Each row shows a score badge and recommended action. Clicking opens a four-factor bar chart and, for Yellow and Red cases, an explainability card that says exactly what is missing and what to do next.
The prototype is complete,30 real PA scenarios, live confidence scoring, triage queue, bulk approve, explainability cards, and a Demo Mode panel showing the three validated denial predictions. Opens in any browser with no internet connection.
6) The New User Journey: After the Confidence Score 
For detailed User journey refer Page 1 & 2 of (Link)
7) How the Confidence Score Is Calculated
The confidence score is a weighted composite of four signals, each independently computable from data Develop Health already holds
Factor
Weight
What it measures
Data source
Historical approval rate
35%
First-pass approval % for this exact drug × payer × plan over trailing 12 months. Weighted 2x toward last 90 days to reflect payer criteria changes.
Develop Health PA outcomes database
Documentation completeness
30%
% of payer-required documentation elements present and within acceptable timeframe in the patient EHR at PA generation time.
EHR integration + payer criteria library
AI answer quality
25%
LLM self-confidence + step therapy logic check (deterministic rule) + internal consistency check + answer completeness.
LLM eval layer + rule engine
Payer criteria freshness
10%
How recently the payer's step therapy criteria were verified. Forced to 0% if criteria change detected,triggers mandatory tier upgrade.
Payer criteria monitoring system


Formula: Score = (0.35 × Historical Rate) + (0.30 × Doc Completeness) + (0.25 × AI Quality) + (0.10 × Payer Freshness)     Green ≥75  |  Yellow 40–74  |  Red <40
 8) The Data Asset and the Moat
Develop Health is the only actor in the PA ecosystem that sees both sides: what the provider submitted and what the payer decided. CoverMyMeds sees PA volume but not the clinical answer content. Surescripts routes transactions but does not generate answers. Payer-side AI sees the insurer's criteria but not the provider's documentation process.

Volume milestone
What the model gains
First 10,000 PAs
Statistically reliable approval rates for top 50 drug/payer combinations. Baseline model deployable.
50,000 PAs
Long-tail payer/plan combinations have sufficient history. Documentation completeness correlation validated against outcomes.
250,000 PAs
Temporal patterns visible,seasonal payer criteria changes detectable. Model accuracy exceeds human expert intuition for common combinations.
1M+ PAs
Network effect: cross-clinic patterns surface. A documentation gap identified at Clinic A improves the model for every other clinic before they experience the denial.


A new entrant cannot replicate this dataset without years of PA volume. A large incumbent can replicate the triage UI in 90 days. They cannot replicate the training data in three years. The confidence score is the product expression of a moat that grows with every PA the platform processes.
9) Validation: Testing with Real PA Coordinators
The prototype is built against sample data. The next validation step is testing with real PA coordinators at existing customer clinics. (refer 3.4 of Link)
      10) Impact Model: What This Moves for Customers
Clinic size
PAs/day
Review hrs/wk before
Review hrs/wk after
Hrs saved/wk
Preventable denials avoided/mo
Small  (1–3)
15
5.6
2.3
3.3  (59%↓)
9
Mid  (4–10)
50
18.8
7.7
11.1  (59%↓)
30
Large  (10+)
150
56.3
23.1
33.2  (59%↓)
90


The pharma revenue calculation
A specialty drug with 10,000 active PA submissions per month at a 14% baseline denial rate loses 1,400 prescription fills per month to abandonment. A 2 percentage point improvement in first-pass approval, achievable through the documentation completeness interventions the confidence score enables, recovers 200 additional fills. At $800 average brand revenue per fill: $160,000 per month. Annually: $1.92 million per drug. This is the economic basis for the pharma data product in the 12-month horizon.
11)The Moat
Data advantage: competitors cannot acquire Develop Health's historical PA outcomes data, it is a byproduct of operating the platform, not a purchasable asset.
Network effect: every new clinic adds training data that improves accuracy for all existing clinics. The model gets better as the customer base grows.
Integration depth: each EHR integration deepens the documentation completeness signal and creates switching costs simultaneously.
First-mover compounding: the first 250,000 PAs are the hardest to get,they require the customer relationships, payer integrations, and clinical trust. Develop Health has them.

The question for any competitor is not "can we build a triage UI?",yes, obviously. The question is "can we train a confidence score model without the drug/payer/plan outcome data?" The answer is no,not for years.
12) What Comes Next: Three Horizons
Horizon
Deliverable
Success metric
Near term
60–90 days
Deploy confidence scoring to production across pilot clinics. Instrument review time and approval rate as tracked metrics.
Green-tier review time <90 sec. False positive rate <12%.
Medium term
6 months
Denial Intelligence Dashboard: connect denial reason data to upstream EHR documentation gaps. Generates specific intake form fix recommendations per drug/payer.
Clinic approval rate +2 ppts vs. baseline within 90 days of dashboard launch.
Long term
12 months
Pharma Brand Intelligence Portal: expose anonymised approval rate benchmarks to pharma brand teams as a paid data product. 
First pharma pilot contract signed. Brand team identifies top 3 payer denial causes within 2 weeks of drug going live.

The confidence score is step one of a three-horizon platform move: PA automation → clinical intelligence → pharma data product. Each horizon is built on he data asset created by the previous one.




Confidence Score Algorithm

This section specifies how each of the four confidence factors is computed.
2.1  Factor 1: Historical Approval Rate (Weight: 35%)
Definition
The percentage of prior PA submissions with the same drug (at NDC or brand level), payer, and plan combination that resulted in first-pass approval, over a rolling 12-month lookback window.
Computation
Query: SELECT COUNT(approved) / COUNT(*) AS approval_rate FROM pa_outcomes WHERE drug_ndc = [ndc] AND payer_id = [payer] AND plan_id = [plan] AND submitted_at > NOW() - INTERVAL 12 MONTHS
Data requirements
Minimum 10 submitted PAs for a given combination to use the historical rate. Below 10: use payer-level rate (same payer, any plan, same drug). Below 10 at payer level: use drug-level rate (any payer, same drug class). Below 10 at drug-class level: default to 0.50 (neutral, 50%) and flag 'Insufficient history.'
Weight the 12-month window toward more recent submissions: submissions from the last 90 days receive 2x weight. This handles payer criteria changes,  recent denials for the same combination are more predictive than older approvals.
Edge cases
Newly approved drug (FDA approval within 12 months): historical rate defaults to drug-class rate + a 'New drug' flag that lowers overall confidence by 5 points.
Payer newly integrated (Develop Health's first month with a payer): default to 50% + 'New payer' flag.
Generic substitution: if brand drug is being submitted but generic equivalent exists in the payer's formulary, surface 'Generic available on formulary,  payer may deny brand PA' as an additional flag.
2.2  Factor 2: Documentation Completeness (Weight: 30%)
Definition
The percentage of the payer's known required documentation elements that are present, parseable, and within the acceptable timeframe in the patient's EHR record at the time of PA generation.
Payer criteria library
To compute this sub-score, Develop Health must maintain a structured library of payer PA criteria, specifically: (a) what data elements the payer requires, (b) the format required (ICD-10 code specificity, date range for lab values, dosage/duration for prior therapy), and (c) the acceptable timeframe for each element. This library is the critical data asset that enables the documentation completeness score. It must be maintained by a clinical ops team member and refreshed whenever payer criteria changes are detected.
Computation
For each required element in the payer criteria library for this drug/payer combination: check EHR data at patient level → present and within timeframe = 1.0 / present but expired = 0.5 / missing = 0.0. Documentation Completeness = mean of element scores × 100.
Key required elements by drug class (examples)
Drug class
Typically required elements
Common timeframe requirements
GLP-1 / Obesity
BMI, A1C or FBG, prior metformin trial (dose, duration, failure), ICD-10 E11/E66 specificity
A1C within 6 months, BMI within 12 months, metformin trial 90+ days
Buprenorphine / MOUD
OUD diagnosis (ICD-10 F11.20), PDMP check date, prior treatment history, MOUD prescriber waiver (pre-2023)
PDMP within 7 days, OUD diagnosis documented within 12 months
Biologics (Dupixent, Humira)
Diagnosis specificity (atopic derm, RA), prior conventional therapy (methotrexate, TCS), failure documentation
Conventional therapy trial 12+ weeks, failure documented in clinical note
Specialty psych (antipsychotics)
Diagnosis, prior antipsychotic trials (2+ agents), failure/intolerance documentation
Prior trials within 24 months

2.3  Factor 3: AI Answer Quality (Weight: 25%)
Definition
A measure of how well the LLM-generated PA answers hold up to semantic coherence checks, internal consistency checks, and payer-specific logic validation.
Sub-components
Sub-component
What it checks
Weight within this factor
LLM self-confidence
The LLM's own probability distribution over its generated answer tokens. High entropy = lower confidence.
30%
Step therapy logic check
Deterministic check: does the generated answer correctly reflect the step therapy sequence required by this payer? (E.g., if the payer requires metformin before GLP-1, does the answer document metformin failure?)
40%
Internal consistency check
Does the generated answer contain contradictions? (E.g., claims patient failed Drug A, but Drug A is not in patient's medication history)
20%
Answer completeness
Did the LLM leave any required form fields blank or with placeholder text?
10%


Implementation note
The step therapy logic check and internal consistency check should be deterministic rule systems, not LLM evaluations. Using an LLM to evaluate LLM output creates a correlated failure mode , if the LLM is wrong about step therapy, it is likely to also be wrong in its self-evaluation. Rule-based checks are more reliable for payer logic validation.
The PM and ML team must decide on the right split between LLM-based and rule-based quality checks. The general principle: use LLM-based evaluation for fluency and coherence (subjective, hard to rule-encode); use rule-based checks for clinical logic and payer compliance (deterministic, documentable, auditable).
2.4  Factor 4: Payer Criteria Freshness (Weight: 10%)
Definition
How recently were the payer's step therapy criteria verified, and has any signal of a criteria change been detected since the last verification?
Computation
If payer criteria was verified within the last 30 days: 100%
If verified 31–60 days ago: 75%
If verified 61–90 days ago: 50%
If verified >90 days ago or criteria change detected: 0% + mandatory flag
Payer criteria change detection
Develop Health should implement a lightweight payer monitoring system: weekly automated checks against known payer portals and formulary documents (where machine-readable), plus manual monitoring by clinical ops. When a criteria change is detected: immediately set all affected drug/payer combinations' Payer Criteria Freshness score to 0, elevate all queued PAs for that combination to Yellow or Red, and notify the clinical ops team to update the payer criteria library.

