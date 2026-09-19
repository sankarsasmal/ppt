# Independent Evaluation: Run18 E-HAZID Assessment (ILS-10315, Heavy Naphtha Reforming)

**Evaluated document:** E-HAZID_Assessment_Run18_Heavy_Naphtha_Reforming1.md
**Evaluation basis:** The same evidence set cited in the assessment's Appendix A (INT-1 through INT-8, USR-1, WEB-1/WEB-2), the original agent prompt (new_prompt_for_copilot.txt), and the minimal-input form (E-HAZID_Minimal_User_Input_Filled.md)
**Purpose:** Score the assessment against its own governing framework, identify specific technical gaps, and demonstrate the first-principles screening that should have accompanied it.

---

## 1. Scorecard Against the Governing Framework

| Framework requirement | Rating | Basis |
|---|---|---|
| Intake gate completed before substantive assessment | **Strong** | All mandatory intake fields addressed; missing items (run plan, feed/catalyst SDS) correctly logged as gaps rather than assumed |
| Tier 1 evidence check, with status per item | **Strong** | Clean Found/Stale/Conflicting classification; correctly refuses to silently pick between the 550°C SOP, 540°C pre-MOC basis, and 680°C user claim |
| Four independent passes, no cross-suppression | **Strong** | Passes read as genuinely distinct lenses (documentation-trusting, skeptic, lifecycle, cross-discipline), not a repeated list |
| Reconciliation without erasing disagreement | **Strong** | S-03 explicitly carries the unresolved tube-rating conflict into a scenario rather than resolving it |
| First-principles hazard calculations | **Weak** | Only inventory-throughput arithmetic performed (Section 1.2). No LFL/UFL, no exposure-limit values, no bounding thermal estimate, no JT-direction analysis, despite these being available from public literature without site-specific data |
| Named-hazard-class handling (HTHA specifically) | **Weak** | User-flagged concern (HTHA) never invoked by name or screened against a standard method (API 941 Nelson curves) |
| Evidence-outage handling | **Adequate, under-weighted** | Internal search failure (email/chat/meetings) disclosed, but treated as a footnote rather than a blocking finding |
| Scenario development (cause → event → consequence → gap) | **Strong** | 20 scenarios, well-formed, correctly phase-tagged |
| Refusal to invent values / approve operation | **Strong** | Explicit "INSUFFICIENT BASIS" gate; no safeguard-adequacy or approval language anywhere |
| Deliverable format compliance | **Fail** | Word requested (intake form, Section G); Markdown delivered |
| Scope-traceability against the ~20 requested hazard categories | **Adequate, not verifiable** | Most categories addressed in Section 6, but no single matrix confirms full coverage |

**Overall:** A structurally sound, disciplined draft that correctly executes the hardest part of this method — surfacing and preserving genuine document conflict instead of resolving it prematurely. Its main weakness is being *too* conservative about calculation: it treats "don't invent site-specific values" as "don't calculate anything," when the framework asks for first-principles screening using cited public data, clearly separated from site-specific claims.

---

## 2. Corrected and Supplemented First-Principles Screens

These are additions to the existing report, not replacements. Each uses a public, static literature value (not a site-specific claim) and is labeled by evidence class per the assessment's own legend (Appendix B).

### 2.1 Flammability limits — missing from Section 6.4

| Species | LFL | UFL | Evidence class |
|---|---|---|---|
| Hydrogen | ~4.0 vol% | ~75 vol% | Inferred — standard published value, not site-verified for this stream composition |
| Benzene | ~1.2 vol% | ~7.8 vol% | Inferred — standard published value |

**Why it matters:** Hydrogen's flammable range is roughly nineteen times wider than most hydrocarbons. Any leak scenario involving the pure-H₂ feed line (WC-01, S-01) should be screened against this range specifically, not treated with the same dilution-to-safety assumptions that would apply to a narrower-range gas. This does not resolve WC-01 (leak size and ventilation rate are still genuinely missing) — it sharpens what the workshop is screening for once those inputs arrive.

### 2.2 Correction to the JT cooling discussion (Section 6.9)

The existing text states that "rapid H₂ depressurization creates cooling potential." This should be corrected:

- Hydrogen's Joule-Thomson inversion temperature is approximately **–71°C (≈202 K)** at low-to-moderate pressure.
- **Above** that temperature — which covers every condition in this experiment, including ambient startup — hydrogen has a **negative** JT coefficient: it **warms**, not cools, on isenthalpic expansion. This is the opposite of CO₂ and most hydrocarbons.
- The credible JT/condensation risk in this system is therefore on the **hydrocarbon/naphtha fraction of the effluent**, which does have a conventional positive JT coefficient, not on the hydrogen stream itself.

**Revised finding (replaces the generic statement in 6.9):** *"Depressurization of the hydrogen-rich stream is not expected to produce auto-refrigeration; hydrogen warms on throttling above –71°C. JT cooling and associated condensation/hydrate risk should instead be screened on the condensable hydrocarbon fraction of the effluent during blowdown, consistent with the carryover concern already raised in F-06/S-08."*
Evidence class: Inferred — general thermodynamic principle, not a site-specific measurement.

### 2.3 HTHA screening — absent from Section 6.7, despite being a named user concern

The intake form's "Known concerns" field explicitly names High-Temperature Hydrogen Attack. This should be a **named sub-finding**, not folded into general materials commentary:

**New finding F-11 (materials):** *At 650°C process temperature and up to 20 barg total pressure, the installed metallurgy should be screened against API RP 941 Nelson curves using the actual hydrogen partial pressure and the confirmed installed alloy (SS321H per INT-3's recommendation vs. SS316/carbon steel referenced elsewhere in the conflicting document set). This screen cannot be completed without the resolved material identity already required under D-01/F-02, but the method should be named explicitly so the mechanical/materials reviewer knows which standard governs the check.* Evidence class: Gap, with a named resolution method — stronger than a generic "assess degradation" statement.

### 2.4 Order-of-magnitude thermal screen for catalyst reduction (S-05) — not attempted in the original

Even without the exact catalyst formulation, a bounding estimate is possible and should be shown, not skipped:

- Total catalyst charge: 8 g (1 g × 8 reactors) — evidenced.
- Using a representative literature heat of reduction for a dilute (0.1–0.6 wt%) Pt-oxide-on-alumina system, on the order of 10–30 kJ per gram of catalyst is a reasonable **screening-level bound** for the reduction exotherm (this is a generic order-of-magnitude figure for this catalyst class, not the specific vendor value).
- For 8 g total catalyst, that bounds total heat release on the order of **80–240 kJ across the full charge** — small in absolute terms, but concentrated in a small catalyst bed with limited thermal mass, so **local, not average, temperature rise is the governing concern.**
- **What this screen does and doesn't do:** it tells the workshop the total energy release is not large in absolute terms, but it does *not* bound the local hot-spot temperature, because that depends on bed thermal mass, heat-loss rate, and reduction kinetics — none of which are available. This should be stated as the actual conclusion, replacing "no thermal-response data... was provided" with a bounded-but-incomplete screen.

Evidence class: Inferred — order-of-magnitude literature estimate for the catalyst class, explicitly not validated against the actual formulation.

### 2.5 Toxicity — quantify what's citable (Section 6.5)

| Substance | Typical occupational exposure limit (illustrative, not site-approved) |
|---|---|
| Benzene | OSHA PEL ~1 ppm TWA; ACGIH TLV lower still (sub-ppm) |
| H₂S (if generated via any sulfur impurity path) | OSHA PEL ceiling ~20 ppm; IDLH ~100 ppm |
| CO (if generated via any side reaction) | OSHA PEL ~50 ppm TWA |

These give the industrial hygiene reviewer (D-04, F-07) a concrete comparison basis the moment batch-specific concentration data arrives, rather than starting the exposure-limit lookup from zero at workshop time.

---

## 3. Findings I Would Add or Elevate

| ID | Finding | Why it needs its own line item |
|---|---|---|
| **F-11 (new)** | Internal email/meeting/chat search failed during this run (service error), not merely "no results." Any near-miss, prior-approval, or informal deviation discussion that exists only in those channels was invisible to this assessment. | This is a *retrieval failure*, materially different from genuine tacit-knowledge absence. It should block full confidence in the "Missing" classification for anything that plausibly lives in those channels, and should be re-run before the workshop, not just noted in passing. |
| **F-12 (new)** | No flammability (LFL/UFL) or exposure-limit (PEL/TLV) values are quoted anywhere in the report, despite both being static public data directly relevant to the two highest-priority hazard classes (H₂ leak, benzene exposure). | These don't require site data and should not have been left out under the "insufficient data" umbrella. |
| **F-13 (new)** | HTHA, named explicitly by the requester, is never invoked by name or method (API 941 Nelson curves) in the materials section. | A user-flagged concern deserves a named, traceable answer — even if that answer is "screening method identified, pending material confirmation" — not silence. |
| **F-14 (new)** | Deliverable was produced in Markdown; intake form Section G specified Word. | Direct instruction not followed; low technical risk, but affects downstream usability (redlining, signature workflow) and is easy to fix. |

---

## 4. Scope Traceability Matrix

A gap in the original report is that no single table confirms coverage against the full hazard-category list the requester specified. Reconstructed here from Sections 5–7 of the assessment:

| Requested category (from intake form / prompt) | Addressed? | Where |
|---|---|---|
| Chemical reactivity & incompatibility | Yes | 6.1 |
| Thermal instability & runaway | Partial — qualitative only, no bounding estimate | 6.2 (see 2.4 above for the missing screen) |
| Pressure / gas generation | Yes, bounded as a gap | 6.3, WC-03 |
| Flammability & explosion | Partial — no LFL/UFL quoted | 6.4 (see 2.1 above) |
| Toxicity (acute/chronic) | Partial — no exposure limits quoted | 6.5 (see 2.5 above) |
| Leak vs. ventilation/dispersion | Partial — framed as calculation request, no indoor O₂/toxic bounding attempt shown | WC-01, S-19 |
| Volatile metal carbonyl formation | Yes, correctly conditional | 6.8, S-18 |
| JT cooling / hydrates / CO₂ solids | Yes, but directionally incorrect for H₂ | 6.9 (see 2.2 above for correction) |
| Catalyst-state hazards / pyrophoricity | Yes | 6.8, S-13 |
| Corrosion / material degradation | Partial — HTHA not named | 6.7 (see 2.3 above) |
| Phase change / carryover / dead-leg accumulation | Yes, strong | 6.6, S-08, S-16 |
| Oxygen enrichment/deficiency | Partial — qualitative only | S-19 |
| Static/electrostatic ignition | Yes | S-11 |
| Off-normal ops (startup/shutdown/sampling/regen) | Yes, strong | Pass 3 (Section D), S-04, S-09 |
| Historical incidents & analogous chemistry | Partial — internal search outage limits confidence | Section 4A, Appendix A |
| Credible worst cases | Yes | Section 7 |
| Uncertainties / data gaps | Yes, strong | Throughout; Appendix B legend |

---

## 5. Summary — What I Would Have Done Differently

1. **Kept every "insufficient data" call that's genuinely about site-specific values** (leak size, ventilation rate, exact catalyst formulation, actual installed alloy) — these are correctly deferred and should stay deferred.
2. **Filled in the calculations that don't need site data** — LFL/UFL, exposure limits, JT-direction analysis, and an order-of-magnitude thermal bound — clearly tagged as literature-based screens, not site-verified conclusions. The framework's "don't invent values" rule protects against fabricating *site-specific* numbers; it doesn't require withholding *public, citable* ones.
3. **Named HTHA and its standard screening method explicitly**, because the requester flagged it by name — silence on a named concern reads as an oversight even when the underlying material question is correctly deferred elsewhere.
4. **Elevated the internal-search outage to a blocking finding**, since it's a fixable retrieval failure, not a genuine evidence gap, and conflating the two understates how much of "Missing" is actually "not yet found."
5. **Added a scope-traceability matrix** as a standing report section, so "evidence-traceable" extends to completeness against the original ask, not just traceability of the findings that were made.
6. **Matched the requested output format** (Word) or explicitly flagged the format substitution as a limitation if Word generation wasn't available in that run.

None of this changes the report's central, correct conclusion: **Run18 should not proceed at 650°C until the assembled system's pressure-temperature basis is resolved.** The additions sharpen the technical basis under that conclusion and close two categories (flammability limits, HTHA) that were in scope and citable but left blank.
