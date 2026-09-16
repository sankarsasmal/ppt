# E-HAZID Copilot Agent — Two-Stage Procedure
### AI-Assisted Synthesis → Human HAZID Workshop

---

## Stage 0: Minimum User Inputs to Start the Assessment

Before the agent runs, the user must provide a **minimal input form**. This is the trigger package — without these, the agent should refuse to proceed or should flag the run as "low-confidence, insufficient basis."

### 0.1 Mandatory inputs

| Field | Why it's required |
|---|---|
| **Skid/unit name & tag number** | Anchors retrieval to the correct document set |
| **New chemistry / experiment description** (reactants, catalysts, target reaction, phase) | This is the actual trigger — the agent needs to know what's changing |
| **Operating envelope** (T, P, flow range, composition range — including any proposed *new* range vs. current design basis) | Core input for first-principles calcs (JT cooling, gas generation, runaway potential) |
| **Point of deviation from prior baseline** — is this a new molecule, new catalyst, new operating window on existing chemistry, or a new mode of operation (e.g., regen) on an existing system? | Determines how much of the historical HAZID/HAZOP is still valid vs. needs fresh analysis |
| **Duration/scale of experiment** (bench trial, pilot run, continuous campaign) | Changes exposure time and worst-case consequence framing |
| **List of uploaded documents** (see 0.2) with revision/date stamps | Needed for the version-control and staleness checks in Stage 1 |
| **Named technical owner / requester** | Accountability — who is asking for this and who will receive the draft |

### 0.2 Documents to feed the agent

**Tier 1 — must have (block the run if missing):**
- Current P&ID(s) for the skid, with revision number/date
- Current PFD / mass-energy balance for the proposed experiment
- Latest SOP(s) covering startup, normal run, shutdown, sampling, and any regeneration/decoking steps
- Design data package: MOC (materials of construction), MAWP/MAOP, relief device basis, instrument ranges
- Safety Data Sheets for all chemicals involved, **including the new chemistry**

**Tier 2 — strongly recommended (agent should flag gaps if absent):**
- Prior HAZOP/HAZID/RHA reports for this skid or the closest analogous unit
- Incident/near-miss reports (site-specific and, if available, corporate database)
- Relief valve / PSV sizing calculations
- Catalyst technical data sheet (composition, known hazards, vendor safety bulletins)
- Any prior lab notebook / experimental data on this or a closely related chemistry

**Tier 3 — supplementary (agent pulls if available, doesn't block):**
- Corrosion monitoring / inspection history
- Maintenance/work order history flagging repeat issues
- Any MOC (management-of-change) records for modifications made after the original design
- Open literature: NIOSH/OSHA data, CCPS process safety references, relevant peer-reviewed studies on the chemistry class, DIPPR/NIST thermophysical data

> **Design note:** Tier 1 absence should hard-stop or heavily caveat the run. Tier 2/3 absence should populate the "Evidence Gaps" section of the report (see Stage 1 template) rather than silently being skipped.

---

## Stage 1: AI-Assisted Synthesis

### 1.1 Procedure steps

**Step 1 — Intake & validation**
Agent confirms all Tier 1 documents are present and checks revision dates against each other (e.g., does the P&ID revision post-date the last MOC?). Any mismatch or missing Tier 1 doc is logged as a **blocking gap**.

**Step 2 — Scoping pass**
Agent reads the experiment description and operating envelope, and classifies the change type:
- New molecule/chemistry on existing hardware
- Existing chemistry, new operating window (T/P/conc.)
- New operating mode on existing chemistry (e.g., first-time regen cycle)
- Combination of the above

This classification determines which historical HAZID/HAZOP sections are still "inherited valid" vs. which need full fresh analysis.

**Step 3 — Four-pass adversarial synthesis**
Run the same document set through four distinct analytical lenses (see prior discussion):
1. **Documentation-Trusting pass** — hazard picture built straight from SOPs/P&IDs/design data as written.
2. **Skeptic/Deviation pass** — explicitly assumes as-built may differ from as-documented; asks what undocumented changes would break the Pass 1 conclusions.
3. **Operator's-Eye pass** — reasons from a field/operations perspective: sampling habits, manual interventions, nuisance conditions.
4. **Cross-Discipline Interaction pass** — hunts for hazards at discipline boundaries (metallurgy × instrumentation, process change × mechanical design assumption, etc.).

Agent reconciles the four passes explicitly — conflicts are preserved and shown, not averaged away.

**Step 4 — First-principles hazard calculations (tool-verified, not free-text)**
For every quantitative claim, agent must route through actual calculation/data tools rather than reasoning from memory:
- Reactivity/incompatibility screening (e.g., NOAA/EPA CRW-type logic)
- Thermal stability/runaway indicators (adiabatic temperature rise, onset temperature vs. operating temperature margin)
- Gas generation / pressure rise estimates
- JT cooling temperature drop, hydrate formation envelope, CO₂ freeze-out check
- Metal carbonyl formation feasibility (T/P/CO partial pressure vs. known formation regimes for the specific metallurgy)
- Flammability envelope (LFL/UFL, LOC) at process and off-normal conditions
- Toxicity exposure modeling (leak-rate vs. ventilation dispersion, IDLH/PEL comparison)

Every number must carry its source (tool, database, literature citation) and its assumptions.

**Step 5 — Literature & incident search**
Agent searches:
- Site-specific and corporate incident/near-miss databases
- Open literature for the specific chemistry/catalyst class
- **Analogous-unit incidents** — same reaction class or phase behavior at other facilities, explicitly tagged as "analogous, not site-specific"

**Step 6 — Gap and silence detection**
For each of the 13 in-scope hazard categories, agent explicitly states whether documentation exists, is silent, or is contradictory — "document silence" is logged as a finding, not treated as "no hazard."

**Step 7 — Draft report assembly**
Agent compiles the report using the template in 1.3, including the mandatory "Unresolved / Requires Human Judgment" section.

**Step 8 — Confidence tagging**
Every finding gets one of three tags:
- 🟢 **Evidenced** — directly supported by cited document/calculation
- 🟡 **Inferred** — derived from general literature/engineering judgment, not site-specific data
- 🔴 **Gap** — no data found; flagged for SME input, not assumed safe

### 1.2 What to ask the agent (prompt structure)

> *"Using the attached Tier 1–3 documents for [skid tag], perform an E-HAZID for the following experiment: [chemistry/experiment description, operating envelope, duration/scale]. Run the four-pass adversarial synthesis. For every hazard category in scope, state evidence quality (Evidenced/Inferred/Gap). Route all quantitative claims through verified calculation tools and cite sources. Explicitly flag document silence as a finding. Do not resolve ambiguous or judgment-dependent findings — present them as open forks for human decision. Output using the E-HAZID report template."*

### 1.3 Report template

```
E-HAZID DRAFT REPORT
Skid/Unit: [tag] | Experiment: [description] | Date: [ ] | Prepared by: Agent v[ ] | Reviewed by: [pending]

1. SCOPE & CHANGE CLASSIFICATION
   - Change type (new chemistry / new window / new mode / combination)
   - Document set used (with revision dates) — Tier 1/2/3 completeness status
   - Blocking gaps (if any) — items that limited analysis confidence

2. OPERATING BASIS SUMMARY
   - Proposed envelope vs. current design basis (deltas highlighted)

3. HAZARD FINDINGS (repeat per category — 13 categories in scope)
   For each category:
   - Finding statement
   - Evidence tag: 🟢 Evidenced / 🟡 Inferred / 🔴 Gap
   - Supporting citations (document, section; calculation, tool, dataset; literature reference)
   - Worst-case scenario description
   - Four-pass reconciliation notes (where passes disagreed)
   - Open challenge questions for the human review team

4. CALCULATIONS APPENDIX
   - All quantitative work, tool/source used, assumptions, margins of error

5. HISTORICAL INCIDENTS & ANALOGOUS EVENTS
   - Site-specific incidents (if any)
   - Analogous incidents from literature/other facilities (tagged as such)

6. EVIDENCE GAPS REGISTER
   - Every 🔴 finding listed in one place, with what document/data/SME input would close it

7. UNRESOLVED / REQUIRES HUMAN JUDGMENT
   - Ambiguous SOP interpretations, conflicting document findings, credibility-of-deviation calls
   - Presented as explicit forks, not agent-resolved

8. HANDOFF NOTES
   - Items requiring downstream HAZOP/LOPA/SIS review
   - Items requiring MOC before experiment proceeds
```

---

## Stage 2: Human HAZID Workshop

### 2.1 Pre-workshop prep
- Distribute the draft report (with confidence tags) to all participants at least 2–3 days ahead
- Participants read and pre-mark: (a) findings they disagree with, (b) 🔴 gaps they can personally close, (c) new hazards not on the list
- Facilitator pre-screens the "Unresolved / Requires Human Judgment" section — this becomes the workshop's core agenda, not an afterthought

### 2.2 Recommended attendees
- Process/chemical engineer (owns the chemistry)
- Operations representative (someone who runs the actual skid)
- Metallurgy/materials engineer (if MOC-relevant hazards are flagged)
- Instrumentation/controls engineer (if cross-discipline findings involve I&C)
- EHS/process safety representative
- Named technical owner from Stage 0 (accountable sign-off role)

### 2.3 Workshop procedure
1. **Calibration** (10–15 min): Walk through how the agent generated the report — evidence tiers, four-pass method — so the team knows how to weight each finding.
2. **Category-by-category review**: For each hazard category, confirm 🟢 findings quickly, **spend the majority of time on 🟡 and 🔴 items**, and specifically interrogate points where the four passes disagreed.
3. **Tacit knowledge capture**: For every category, explicitly ask operations: *"Has anything like this happened that was never logged?"* This is the step that recovers what retrieval structurally cannot.
4. **Gap closure**: Work through the Evidence Gaps Register — close what can be closed in the room, assign owners/deadlines for what can't.
5. **New hazard capture**: Open floor for hazards the agent didn't surface at all.
6. **Disposition of each finding**: Accept / Modify / Reject / Escalate to HAZOP-LOPA, with a named owner and date for each open item.
7. **Sign-off**: Qualified process safety owner signs the finalized E-HAZID; document is version-locked against the source documents used.

### 2.4 Output of Stage 2
- Finalized, human-approved E-HAZID report
- Updated Evidence Gaps Register (closed items marked, open items assigned)
- Formal handoff package to downstream HAZOP/LOPA/MOC processes
- Lessons file: any tacit-knowledge findings from this workshop should be considered for formal documentation, so future agent runs have better source material (this is how the system improves over time)

---

## Design Principle Underlying Both Stages

The agent's job is to **synthesize, calculate, cite, and flag** — never to declare completeness or resolve ambiguity on its own. The workshop's job is to **supply what isn't written down and make the accountable call**. The report template enforces this split structurally: the "Unresolved" and "Evidence Gaps" sections are not appendices — they are what the workshop agenda is built from.
