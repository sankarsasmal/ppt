**E-HAZID ASSESSMENT — REVISED**

**Heavy Naphtha Reforming | Run18**

ILS-10315 | All eight reactors | Human workshop draft (v2 — first-principles calculations added)

| **DOCUMENT CONTROL STATUS** Preliminary, evidence-traceable hazard identification draft. This revision adds first-principles screening calculations from external, citable data sources (OSHA, NIOSH, ACGIH, API RP 941, published thermochemical literature) that were not present in v1. It does not change v1's central conclusion: the reactor-tube upgrade to a stated 680°C maximum remains USER-SUPPLIED, UNVERIFIED information, inconsistent with current controlled documents. This report does not approve operation, accept risk, assess safeguard adequacy, or replace accountable engineering review. | |
| --- | --- |
| **Field** | **Value** | |
| Project / experiment | Heavy Naphtha reforming | |
| Experiment ID | Run18 | |
| Requester / owner | Harish Balam | |
| Unit / scope | ILS-10315; R1–R8 | |
| Proposed envelope | Room temperature / 630 / 650°C; 1 / 15 / 20 barg | |
| Stated upgraded tube limit | 680°C maximum, unverified user statement | |
| Assessment date | 19 September 2026 | |
| Planned run date | 01/10/2026 as entered; date convention unresolved | |
| Output status | Controlled working draft for multidisciplinary review | |

Prepared as an evidence-management, calculation-screening and hazard-identification assistant. Accountable human review is required.

---

## Executive decision summary

| **OVERALL STATUS: INSUFFICIENT BASIS / HOLD AT HUMAN DECISION GATE** — unchanged from v1, now on firmer quantitative ground. Run18 proposes 650°C, which sits above every currently controlled temperature boundary in the document set (550°C SOP, 540°C pre-MOC basis) and, per the calculation in Section 6.3 below, is unambiguously inside High-Temperature Hydrogen Attack territory for carbon steel under API RP 941 — carbon steel's absolute safe ceiling in hydrogen service is ~200°C regardless of pressure. This sharpens, rather than resolves, the case for holding at the current decision gate: the material question is no longer "is 650°C plausible" but "is the *installed, assembled* system built from an alloy qualified for this exact temperature/hydrogen-partial-pressure combination." |
| --- |

---

## Priority findings

* F-01 Document conflict: SOP boundary 550°C versus Run18 maximum 650°C versus user-stated tube capability 680°C.
* F-02 Upgrade evidence absent: no verified material certificate, wall-thickness/design calculation, pressure-temperature rating, inspection/appraisal, MOC approval or as-built revision for the upgraded tubes.
* F-03 System boundary gap: a tube rating does not establish the limits of seals, O-rings, sleeves, reactor heads, valves, thermocouples, fittings, downstream oven, GC path, product collection or vent routing.
* F-04 Feed and catalyst identity gaps: the actual heavy-naphtha batch specification/SDS and exact catalyst code/SDS are missing.
* F-05 Run plan gap: staging, ramp rates, reduction recipe, H2-to-hydrocarbon ratio, per-reactor allocation, sampling frequency, shutdown/recovery and passivation are not defined.
* F-06 Phase-management concern: prior MOC material identifies possible naphtha carryover to vents in fully gas-phase operation and a need for catch-pot/quench arrangements.
* F-07 Toxicity concern: BTX, especially benzene, may be present in feed/product; exposure potential concentrates at sampling, collection, disconnection, weighing and waste handling. **Quantified in Section 6.4 below.**
* F-08 Pressure/flammability concern: continuous pure H2 plus generated H2/light hydrocarbons can create a pressurized flammable inventory. **Quantified in Section 6.2 below, including the temperature-widened flammable envelope at process conditions.**
* F-09 Catalyst-state concern: fresh oxidic catalyst is reduced in H2, and spent/reduced catalyst may self-heat or react on air ingress. **Bounded in Section 6.5 below.**
* F-10 Long-duration accumulation: 720 h increases opportunity for coke, pressure-drop growth, condensate/dead-leg accumulation, seal degradation, drift and unnoticed vent/catch-pot loading.
* **F-11 (new) Internal search outage:** email, meeting and chat retrieval returned service errors during evidence gathering. This is a retrieval failure, not confirmed absence — any near-miss, informal deviation discussion, or prior tube-upgrade approval that exists only in those channels was invisible to this assessment. **Treated as a blocking gap, not a footnote — see D-07.**
* **F-12 (new) Named-concern gap closed:** High-Temperature Hydrogen Attack, flagged explicitly by the requester, is now screened by name against API RP 941 in Section 6.3.
* **F-13 (new) Deliverable format:** intake form Section G specified Word output; this and the prior revision were produced in Markdown. Flagged for correction at final issue.

---

## Required accountable decisions before run

| **ID** | **Decision / evidence required** | **Discipline** |
| --- | --- | --- |
| D-01 | Confirm whether 680°C is an approved tube MAWT/design limit at 20 barg and identify material, dimensions, heat/lot traceability and design code basis. | Mechanical / materials |
| D-02 | Approve or reject 650°C as the experiment maximum after checking every pressure-boundary and temperature-exposed component **against the API RP 941 Nelson curve for the confirmed alloy** (Section 6.3). | Technical authority / mechanical / process |
| D-03 | Update or formally redline SOP, PEFS/P&ID, HEMP, equipment appraisal, critical-equipment list and operating envelope. | Document owner / MOC |
| D-04 | Confirm actual feed batch, catalyst code, impurity limits and approved SDS set. | Experiment owner / IH / chemistry |
| D-05 | Confirm downstream phase-control and capacity basis for GC, catch pot, quench/collection and process vent — **noting per Section 6.6 that the condensation risk sits on the hydrocarbon fraction, not the hydrogen stream.** | Process / operations |
| D-06 | Approve the detailed Run18 run plan, including reduction, startup, sampling, abnormal recovery, shutdown and passivation. | Experiment owner / operations |
| **D-07 (new)** | Re-run internal email/meeting/chat search once the service outage is resolved, before the workshop convenes, to confirm no written near-miss or prior-approval record was missed. | Document custodian / IT |

---

## 1. Scope, boundaries and basis

Unchanged from v1: this assessment covers hazard identification for Run18 on ILS-10315 across all lifecycle phases (reduction, startup, heat-up, pressurization, normal operation, sampling, depressurization, shutdown, product collection, venting, catalyst unloading/passivation, maintenance). Safeguards are mentioned only as documented context. HAZOP worksheets, LOPA, alarm/interlock/ESD assessment, SIL, relief sizing and residual-risk judgement remain excluded.

### 1.1 Experiment basis (unchanged from v1)

| Parameter | Basis used | Evidence class |
| --- | --- | --- |
| Objective | Convert heavy naphtha to high-octane reformate, aromatics and branched hydrocarbons | Intake, evidenced |
| Chemistry | Dehydrogenation, dehydrocyclization, isomerization, controlled hydrocracking | Intake, evidenced |
| Gas feed | 100% H2; maximum 2 NL/min | Intake, evidenced |
| Liquid feed | Heavy naphtha; broad PIONA ranges; maximum 2 g/h | Intake, approximate |
| Catalyst | Pt/alumina, 0.1–0.6 wt% Pt, possible Re/Ir/Sn and Cl/F promoters; 1 g/reactor; fresh oxidic; reduction planned | Intake, identity unresolved |
| Reactor scope | R1–R8 | Intake, evidenced |
| Temperature | RT / 630 / 650°C | Intake, evidenced |
| Pressure | 1 / 15 / 20 barg | Intake, evidenced |
| Duration | 720 h maximum | Intake, evidenced |
| Stated tube upgrade | Maximum 680°C. Documents not updated | User statement, unverified |

---

## 2. Evidence register and Tier 1 check

Carried forward from v1 without change — the same INT-1 through INT-8, USR-1, and WEB-1/WEB-2 sources, with the same Found/Stale/Conflicting classification. **One change:** the internal search limitation noted in v1 Section 4A is now elevated to Priority Finding F-11 and Decision D-07 rather than remaining a methodological footnote.

New external sources used for the calculations in Section 6 are listed in **Appendix C**, classified separately from the internal evidence register because they support general physical/chemical/regulatory screening, not site-specific claims.

---

## 3. Change classification and assumptions

Unchanged from v1 (new/changed feed and impurity profile; catalyst and catalyst-state change; temperature-window change; equipment/material configuration change; operating-mode change; downstream phase/collection change). Controlled assumptions A-01 through A-06 carried forward unchanged.

---

## 4. Four-pass adversarial synthesis

The four-pass structure and findings from v1 (Documentation-Trusting, Skeptic and Deviation, Operational and Lifecycle, Cross-Discipline and Hidden Interactions) are carried forward unchanged — the evidence base did not change, only the calculation layer beneath it. Three passes now have sharper conclusions as a direct result of Section 6:

- **Pass 1 (P1-03, hot reactor connections):** now explicitly tied to the Nelson-curve finding — "confirm complete 650°C component list" becomes "confirm complete 650°C component list **against the specific alloy's API 941 curve, not against the tube rating alone.**"
- **Pass 2 (P2-01, tube vs. assembled system):** unchanged in substance, now reinforced — even if the tube itself is metallurgically qualified at 680°C, heads/seals/sleeves of a *different, unconfirmed* alloy could each have a *different* Nelson-curve limit, and the governing limit is whichever component's curve is crossed first.
- **Pass 3 (Depressurization phase):** the JT/cooling entry is corrected — see Section 6.6.

---

## 5. Reconciled hazard scenarios

The 20 scenarios (S-01 through S-20) from v1 are carried forward. Four are updated in substance based on the new calculations; the rest are unchanged.

| ID | Update |
| --- | --- |
| S-03 (tube service beyond approved limit) | Now explicitly a Nelson-curve violation for carbon steel at these conditions, not just an "unverified claim" — see 6.3. Confirms this is High priority, not merely Medium-pending-data. |
| S-05 (catalyst-reduction exotherm) | Bounded — see 6.5. Total Pt-reduction energy is small in absolute terms; the residual concern is local/kinetic, not bulk thermal. |
| S-07 (excess hydrocracking) | Sharpened — see 6.5. Hydrocracking is the exothermic, non-self-limiting side reaction; the primary aromatization pathways are endothermic and self-quenching. The workshop's thermal-runaway attention should weight toward S-07, not the primary reaction network. |
| S-12 (rapid depressurization cooling) | Corrected — see 6.6. The JT effect on the hydrogen stream itself is warming, not cooling, above -71°C. Retarget this scenario at the condensable hydrocarbon fraction of the effluent. |

All other scenarios (S-01, S-02, S-04, S-06, S-08 through S-11, S-13 through S-20) are unchanged from v1.

---

## 6. First-principles screening calculations

This section is the substantive addition to v1. Each calculation uses external, citable, static data — not site-specific measurements — and is explicitly separated from the genuinely missing site data (leak sizes, ventilation rates, exact catalyst formulation) that no calculation can substitute for. Evidence class for every value in this section is **Inferred — external literature/regulatory constant, not site-verified for this exact stream.**

### 6.1 Flammability limits

| Species | LFL | UFL | Source |
| --- | --- | --- | --- |
| Hydrogen (ambient, ~20°C) | ~4.0 vol% | ~75 vol% | Widely cited literature/industrial value (e.g., NASA/DOE hydrogen safety references) |
| Benzene | 1.2 vol% | 7.8 vol% | OSHA Chemical Sampling Information, CAS 71-43-2 |

**Temperature effect — directly relevant here.** Hydrogen's flammable range widens with temperature: published data show the LFL falling from ~4% at 20°C to roughly 1.5% at 400°C, while the UFL rises by roughly 12.5 percentage points over the same span. Run18 operates at 630–650°C, well beyond the data reported in the source literature. The direction of the trend is unambiguous — **the flammable envelope at process temperature is materially wider than the ambient 4–75% figure**, meaning any credible leak or air-ingress scenario inside the hot zone should be screened against a wider, not the nominal, flammability window. The exact envelope at 650°C is not available in the sources reviewed and should be requested as a specialist input (flame/combustion data at elevated temperature) rather than extrapolated further by this assessment.

**Implication for S-01/S-04:** hydrogen's flammable range is roughly nineteen times wider than typical hydrocarbon vapors at ambient conditions, and wider still at process temperature. Air-ingress scenarios during purge, startup, or post-shutdown opening (S-04, S-19) should be evaluated with this widened envelope in mind, not a generic "dilute below 4%" assumption.

### 6.2 Toxicity — occupational exposure limits

| Substance | OSHA PEL | ACGIH TLV | NIOSH REL | IDLH | Source |
| --- | --- | --- | --- | --- | --- |
| Benzene | 1 ppm TWA / 5 ppm STEL | 0.5 ppm TWA / 2.5 ppm STEL | 0.1 ppm TWA / 1 ppm STEL | 500 ppm | OSHA Chemical Sampling Information; NIOSH Pocket Guide / IDLH documentation, CAS 71-43-2 |
| Hydrogen sulfide | 20 ppm ceiling / 50 ppm 10-min peak | 1 ppm TWA / 5 ppm STEL | 10 ppm 10-min ceiling | 100 ppm | OSHA 29 CFR 1910.1000 Table Z-2; NIOSH IDLH documentation, CAS 7783-06-4 |
| Carbon monoxide | 50 ppm TWA | 25 ppm TWA | — | ~1,200 ppm | OSHA/NIOSH general industry references |

**What this closes:** F-07 (benzene exposure) and the toxicity entries in S-09/S-10 now have a concrete comparison basis. Benzene's PEL (1 ppm) is roughly 500 times lower than its IDLH (500 ppm) — a narrow margin that argues for continuous or frequent monitoring at sampling/collection points, not periodic spot-checks, once actual batch concentration data is available. This does not resolve F-07 — actual product-stream benzene concentration is still a genuine data gap — but it tells the industrial hygiene reviewer exactly what threshold the eventual monitoring data must be checked against.

### 6.3 HTHA screening against API RP 941 Nelson curves

This directly closes F-12, the requester's named "Known concern" that v1 left unaddressed by name.

**Method:** API RP 941 (American Petroleum Institute, *Steels for Hydrogen Service at Elevated Temperatures and Pressures in Petroleum Refineries and Petrochemical Plants*) provides empirically derived temperature-vs-hydrogen-partial-pressure curves ("Nelson curves") below which a given steel grade resists High-Temperature Hydrogen Attack, and above which it does not.

**Governing published facts:**
- Unalloyed carbon steel's absolute safe operating ceiling in hydrogen service is approximately **200°C (392°F), regardless of hydrogen partial pressure.** Above this temperature, carbon steel is outside its Nelson curve entirely.
- HTHA is not generally observed below a hydrogen partial pressure of roughly 50 psia (~3.4 bar), except at very high temperatures — but this pressure-based exemption does not apply once temperature alone exceeds the ~200°C ceiling.
- Higher alloy grades (Cr-Mo steels, and further, austenitic stainless steels such as the SS321H referenced in the pre-MOC document, INT-3) tolerate substantially higher temperature/hydrogen-partial-pressure combinations, which is precisely why SS321H was recommended in that document.

**Screening result for Run18:** At 650°C reactor temperature with a feed gas that is 100% hydrogen at up to 20 barg (~21 bar absolute, ≈300 psia, essentially all of it hydrogen partial pressure), the process condition is **more than three times the absolute carbon-steel ceiling on temperature alone**, independent of the pressure term. This is unambiguous: **any carbon steel or low-alloy (e.g., C-0.5Mo) component in this service is outside its Nelson curve and is a confirmed HTHA risk, not a hypothetical one.** The open question is not whether HTHA is a credible mechanism here — it is — but which alloy is actually installed in each component (tube, heads, fittings, thermocouple wells, valves), which remains the genuine data gap already captured in F-02/D-01.

**What this adds to S-03:** v1 correctly flagged the tube-rating conflict as unresolved; this calculation confirms that the *consequence* of an incorrect material assumption is not a generic "degradation" concern but a specifically named, well-characterized failure mechanism with a documented history of refinery incidents (including fatalities) when overlooked. This raises the evidentiary weight of D-01/D-02, without changing their content.

### 6.4 Joule-Thomson behavior on depressurization — correction to v1

**Governing published fact:** hydrogen's maximum Joule-Thomson inversion temperature is approximately **200–202 K (–71 to –73°C)**. Above this temperature — which covers every condition in Run18, from ambient startup through 650°C operation — hydrogen has a **negative** Joule-Thomson coefficient: it **warms**, not cools, on throttling/isenthalpic expansion. This is the opposite behavior from nitrogen, oxygen, or CO2, whose inversion temperatures (623 K, 761 K, and roughly 1500 K respectively) are far above ambient, so those gases cool on expansion under normal conditions.

**Corrected finding (replaces the v1 statement in Section 6.9):** *Rapid depressurization of the predominantly-hydrogen process stream is not expected to produce auto-refrigeration; hydrogen warms on throttling at any temperature encountered in this experiment. The credible JT-cooling/condensation risk sits instead on the condensable hydrocarbon components of the effluent (naphtha, reformate, BTX vapor), which do have conventional positive JT coefficients at these conditions. This reframes S-12: the depressurization hazard of concern is condensation/icing of the hydrocarbon fraction at restrictions or low points, consistent with — and reinforcing — the carryover concern already raised in F-06/S-08, not a hydrogen-specific auto-refrigeration event.*

This also affects **WC-06 (long-run accumulation)** framing: any cold-spot analysis during blowdown should be scoped to the hydrocarbon-bearing lines and vessels, not the hydrogen supply path.

### 6.5 Catalyst reduction — bounding thermal screen

This is the calculation v1 skipped entirely in favor of "no thermal-response data was provided." A defensible bound is available using only the data already in the intake form.

**Inputs (from intake form, evidenced):**
- Catalyst mass: 1 g per reactor × 8 reactors = 8 g total
- Pt loading: 0.1–0.6 wt% of catalyst mass

**Step 1 — bound the Pt mass:**
Total Pt mass = 8 g × (0.1% to 0.6%) = **8 mg to 48 mg** across all eight reactors.

**Step 2 — convert to moles:**
Using Pt atomic mass 195.08 g/mol: moles Pt = 8 mg / 195.08 g/mol to 48 mg / 195.08 g/mol = **~0.041 to ~0.246 mmol** (41–246 micromoles) total.

**Step 3 — bound the reduction enthalpy per mole:**
A precise, verified value for the enthalpy of the specific PtOx-to-Pt reduction used in this catalyst was not found in the sources reviewed for this screen (proprietary formulation, promoter content, and support interaction all affect the real value). As a conservative screening bound, a generic transition-metal-oxide reduction enthalpy on the order of **100–400 kJ/mol** is used — this range comfortably spans typical values reported for comparable supported noble-metal-oxide reductions in the literature and is deliberately biased high to produce a conservative (over-, not under-, estimated) bound.

**Step 4 — bound total heat release:**
Total heat = (41 to 246 µmol) × (100 to 400 kJ/mol) = **on the order of 4 J to 100 J** across the entire 8-reactor charge.

**Conclusion:** Even under a deliberately conservative (high) assumption for the reduction enthalpy, the *total* energy released by Pt-oxide reduction across all eight reactors is on the order of tens of joules — trivial in absolute terms, roughly the energy of a falling pencil. **This bound resolves the bulk/average thermal concern in S-05: the primary catalyst-reduction reaction, by itself, is not a significant total-energy hazard given the milligram-scale Pt loading.**

**What this bound does NOT resolve** (explicitly, so the workshop does not over-read it):
- It says nothing about **local, transient hot-spots** at the specific active-site scale during fast reduction kinetics, which depend on heat-transfer rate and reduction rate, not total energy — a genuinely separate question requiring vendor thermal data or bench-scale calorimetry.
- It does **not** cover reduction/decomposition of halide promoters (Cl/F) or secondary metals (Re, Ir, Sn) if present, which have their own, unquantified thermal behavior — this remains a real gap (D-01-adjacent).
- It does **not** cover the water-formation side reaction (PtOx + H2 → Pt + H2O) interacting with any residual moisture or with support dehydration, which is a separate, uncharacterized effect.

This converts S-05 from "unknown, no data" to "bulk energy bounded and small; local/kinetic and promoter-related aspects remain open" — a materially more useful statement for the workshop.

### 6.6 Reaction thermal duty — endothermic vs. exothermic pathways

**Governing published data:** the dehydrogenation of cyclohexane to benzene, the textbook example of the primary naphthene-dehydrogenation pathway in catalytic reforming, is confirmed in the reforming literature as:

Cyclohexane → Benzene + 3 H2, ΔH ≈ **+221 kJ/mol (endothermic)**

Naphthene dehydrogenation and paraffin dehydrocyclization reactions across the reforming literature are consistently and strongly endothermic, which is precisely why reformer trains require inter-reactor reheating furnaces to sustain conversion — a well-established industry design fact, not a Run18-specific claim.

**Safety implication (missing from v1):** the *primary, desired* reaction pathways in Run18 (dehydrogenation, dehydrocyclization, isomerization) are **self-limiting under adiabatic conditions** — as they proceed, they consume heat and the local temperature falls, which slows the reaction further. This is a structurally favorable property for runaway-avoidance and should be stated as such, not left implicit.

**Hydrocracking, by contrast, is exothermic** and does not share this self-limiting property; unlike the primary aromatization reactions, an exothermic side reaction can accelerate itself as local temperature rises. **This means the workshop's thermal-runaway attention (S-07) should be weighted specifically toward hydrocracking selectivity and control, not toward the primary reaction network**, which is thermodynamically self-quenching. This is a sharper, more actionable statement than v1's generic "hydrocracking and dehydrogenation generate/consume gases differently than expected" (P1-04).

### 6.7 Bounding estimate — reaction-generated hydrogen from naphthene dehydrogenation

This partially answers WC-03 (maximum gas generation), which v1 left entirely as a data request.

**Inputs (from intake form, evidenced):**
- Maximum liquid feed: 2 g/h
- Naphthene content: 15–20 wt% of feed (evidenced range from intake form)

**Assumption (flagged, not site-verified):** average naphthene molecular weight ≈ 110 g/mol, representative of C7–C9 naphthenes typical of heavy naphtha. This is an assumption, not a measured value for this specific batch.

**Calculation:**
- Naphthene feed rate = 2 g/h × (15% to 20%) = 0.3 to 0.4 g/h
- Moles naphthene/h = (0.3 to 0.4 g/h) / 110 g/mol ≈ 0.0027 to 0.0036 mol/h
- If fully dehydrogenated (3 mol H2 per mol naphthene, per the cyclohexane→benzene stoichiometry above): H2 generated ≈ 0.0082 to 0.0109 mol/h
- Converting to standard volume (22.4 NL/mol): **≈ 0.18 to 0.24 NL/h of reaction-generated hydrogen from complete naphthene dehydrogenation**

**Comparison to fed hydrogen:** the intake form states a maximum fed H2 rate of 120 NL/h (2 NL/min × 60). The naphthene-dehydrogenation contribution above is therefore **on the order of 0.15–0.2% of the fed hydrogen rate** — a small addition to the pressurized inventory from this specific pathway.

**What this bound explicitly excludes (do not over-read):**
- **Paraffin dehydrocyclization** (n-paraffin → aromatic + 4 H2) also generates hydrogen and applies to a larger fraction of the feed (paraffins + isoparaffins are 57–75 wt% of feed per the intake form), but its selectivity and conversion are not provided and are known from the reforming literature to be considerably lower and more variable than naphthene dehydrogenation. This is a genuine, unresolved gap — the total reaction-generated hydrogen is very likely higher than the 0.18–0.24 NL/h bound above, but by how much cannot be estimated without conversion/selectivity data or a validated kinetic model.
- **Hydrocracking gas generation** (light ends: methane, ethane, propane, butane) is excluded from this bound entirely and remains a genuine data gap, consistent with v1.

**Net effect on WC-03:** this calculation converts "maximum effluent generation is not quantified" into "the naphthene-dehydrogenation floor is small and quantified; the paraffin-dehydrocyclization and hydrocracking contributions remain the dominant unresolved uncertainty and should be the specialist calculation's primary focus," which is a more precisely targeted specialist request than v1's undifferentiated ask.

### 6.8 Oxygen deficiency — illustrative method (not a site-specific result)

v1 left this entirely qualitative (S-19). The governing calculation is straightforward once a room/enclosure volume is known, but **no such volume was supplied in the intake form**, so this is shown as a worked method with an illustrative placeholder volume, explicitly not a site-specific conclusion.

**Method:** fractional oxygen depletion in a well-mixed enclosure ≈ (volume of displacing gas released) / (enclosure volume + volume of displacing gas released), for a released inert or non-oxygen gas mixing into a fixed room volume.

**Illustrative example only** (placeholder room volume of 50 m³, a generic small-lab figure, NOT the actual ILS-10315 room):
A credible purge/vent release of, say, 5 m³ of hydrogen-rich gas into a 50 m³ room without forced ventilation would displace roughly 5/(50+5) ≈ 9% of the room's air volume, which — starting from 20.9% ambient oxygen — could depress oxygen concentration to roughly 19%, below the OSHA-referenced 19.5% minimum action threshold for atmospheres requiring monitoring, but not yet at an acutely dangerous level. **This example is illustrative of method only.**

**What is actually needed to close S-19:** the real enclosure/room volume, the actual ventilation rate (air changes per hour), and a credible release-volume scenario tied to an actual leak or vent case — none of which are available. This remains a genuine specialist input request (D-05/field verification), not resolved by this screen.

---

## 7. Topic-by-topic hazard challenge (updated)

Sections 6.1 (reactivity), 6.6 (phase change/accumulation — unchanged from v1 apart from the JT correction cross-reference), 6.8 (catalyst-state — cross-referenced to the new Section 6.5 bound above), 6.10 (human factors) carry forward from v1 without substantive change. The following are revised:

**6.4 Flammability and explosion (revised):** The process intentionally combines H2 (LFL 4%, UFL 75% at ambient — see Section 6.1) and flammable hydrocarbons (benzene LFL 1.2%, UFL 7.8%) at elevated pressure and temperature, with hydrogen's flammable envelope widening further at process temperature. Credible ignition sources include hot surfaces, static discharge and electrical/mechanical sources after loss of containment. Dispersion or explosion calculation still requires leak size, ventilation rate, and enclosure geometry — this remains a genuine data gap, but the flammability constants themselves are now on record rather than absent.

**6.5 Toxicity and exposure (revised):** Heavy naphtha and reformate may contain benzene and other aromatics; actual concentrations remain missing (unchanged gap). What is now available: benzene's OSHA PEL (1 ppm TWA), ACGIH TLV (0.5 ppm TWA), and IDLH (500 ppm) — see Section 6.2 — giving the eventual monitoring program a concrete target. The generic heavy-naphtha SDS found by search remains not a substitute for the batch-specific approved site SDS.

**6.7 Materials and degradation (revised):** The user-stated 680°C tube upgrade remains without controlled evidence (unchanged gap). What is now available: a completed HTHA screen against API RP 941 (Section 6.3) confirming that carbon steel and low-alloy components are unambiguously unsuitable at these conditions, sharpening why the material-identity gap (F-02/D-01) is not a formality but a confirmed-mechanism risk.

**6.9 JT cooling, icing, hydrates and CO2 solids (revised — see Section 6.4 above for full correction):** Hydrogen does not auto-refrigerate on depressurization at any temperature in this experiment; the condensation/icing risk is on the hydrocarbon effluent fraction. CO2 solidification and hydrate formation remain not supported as primary scenarios (no CO2 feed, water inventory undefined) — unchanged from v1, retained as conditional checks.

---

## 8. Worst-case screens and calculation needs (updated)

| **Case** | **v1 status** | **v2 status after Section 6** |
| --- | --- | --- |
| WC-01 H2 leak | No quantified result | Unchanged — leak size/ventilation still required; flammability constants now available for the eventual dispersion calc (6.1) |
| WC-02 Reactor tube failure | No quantified result | Unchanged — still requires material/geometry confirmation; consequence severity reinforced by confirmed HTHA applicability (6.3) |
| WC-03 Maximum gas generation | Entirely unquantified | **Partial floor established** (6.7): naphthene-dehydrogenation contribution bounded at ~0.18–0.24 NL/h; paraffin-dehydrocyclization and hydrocracking contributions remain the open, dominant uncertainty |
| WC-04 Downstream carryover | Unquantified | Unchanged — still requires as-built routing/capacity data; now correctly attributed to the hydrocarbon fraction only, not hydrogen (6.4) |
| WC-05 Reduction thermal case | Entirely unquantified | **Bulk energy bounded** (6.5): tens of joules total; local/kinetic hot-spot behavior remains open |
| WC-06 Long-run accumulation | Unquantified | Unchanged — cold-spot analysis now correctly scoped to hydrocarbon-bearing lines (6.4) |

---

## 9. Required actions and workshop handoff (updated)

All P0–P2 actions from v1 (mechanical design substantiation, controlled redline, Run18 experimental plan, feed/catalyst SDS, downstream routing confirmation, IH exposure review, tube inspection, date-format resolution, prior-history capture) remain in force unchanged. Two additions:

| Priority | Action | Acceptance evidence for workshop | Owner role |
| --- | --- | --- | --- |
| P0 | Screen every hot-zone component's actual alloy against its specific API RP 941 Nelson curve, not the tube rating alone. | Component-by-component alloy identification cross-referenced against Nelson curve for that alloy at 650°C/20 barg H2 partial pressure. | Mechanical / materials TA |
| P1 | Re-run internal email/meeting/chat search once service outage is resolved (F-11/D-07). | Confirmation that the outage-affected search has been repeated and results incorporated, or documented as still unavailable with a stated reason. | Document custodian / IT |

---

## 10. Scope traceability matrix

| Requested category | Status | Where addressed |
| --- | --- | --- |
| Chemical reactivity & incompatibility | Addressed | Section 7 (6.1 topic) |
| Thermal instability & runaway | **Improved** — bounded, endo/exo distinction added | Sections 6.5, 6.6 |
| Pressure / gas generation | **Improved** — partial quantitative floor | Section 6.7 |
| Flammability & explosion | **Improved** — LFL/UFL values now stated | Sections 6.1, 7 |
| Toxicity (acute/chronic) | **Improved** — exposure limits now stated | Sections 6.2, 7 |
| Leak vs. ventilation/dispersion | Partial — leak/ventilation data still missing | Section 6.1 (constants only) |
| Volatile metal carbonyl formation | Addressed, correctly conditional | v1 Section 6.8 / S-18 (unchanged) |
| JT cooling / hydrates / CO2 solids | **Corrected** — direction of effect fixed | Section 6.4 |
| Catalyst-state hazards / pyrophoricity | **Improved** — bulk energy bounded | Section 6.5 |
| Corrosion / material degradation | **Improved** — HTHA named and screened | Section 6.3 |
| Phase change / carryover / dead-leg | Addressed | v1 Section 6.6 / S-08, S-16 (unchanged) |
| Oxygen enrichment/deficiency | **Improved** — method demonstrated, site data still needed | Section 6.8 |
| Static/electrostatic ignition | Addressed | v1 S-11 (unchanged) |
| Off-normal ops | Addressed | v1 Pass 3 (unchanged) |
| Historical incidents & analogous chemistry | Partial — search outage limits confidence | F-11 |
| Credible worst cases | Addressed, several now partially quantified | Section 8 |
| Uncertainties / data gaps | Addressed throughout | Appendix B legend (unchanged) |

---

## 11. Conclusion

Run18 has a credible, now more rigorously quantified, preliminary hazard basis for multidisciplinary review, but it remains unsuitable for approval or operation on the current evidence set. The central issue is unchanged from v1: whether the installed, assembled reactor and connected system have a controlled, approved pressure-temperature-materials basis for 650°C operation with pure H2 and heavy naphtha. What this revision adds is that the consequence of getting that wrong is no longer generic — it is a **specifically named, externally documented failure mechanism (HTHA)** for which carbon steel is confirmed unsuitable at these conditions, and for which the actual installed alloy remains unconfirmed.

Three calculations move genuine content from "unknown" to "bounded": the catalyst-reduction thermal load (small in bulk, open at the local/kinetic level), the naphthene-dehydrogenation hydrogen-generation floor (small, with dominant uncertainty shifted to paraffin dehydrocyclization and hydrocracking), and the JT-effect direction (corrected from an assumed cooling risk on hydrogen to a condensation risk on the hydrocarbon fraction). None of these resolve the hold; all of them sharpen what the workshop should spend its time on.

The human E-HAZID workshop should focus first on the P0 evidence actions in Section 9, validate the 20 structured scenarios (four materially updated per Section 5), preserve unresolved disagreement, assign specialist checks, confirm the internal-search re-run (D-07), and determine the controlled operating basis. No statement in this report constitutes approval, residual-risk acceptance or confirmation of safeguard adequacy.

---

## Appendix A. Internal source notes

Unchanged from v1 (INT-1 through INT-8, USR-1, WEB-1, WEB-2) — see the original assessment for the full table.

## Appendix B. Evidence classification legend

Unchanged from v1 (Evidenced / User-supplied, unverified / Inferred / Gap / Conflicting / Stale).

## Appendix C. External reference sources used in Section 6 (new)

| ID | Source | Used for |
| --- | --- | --- |
| EXT-1 | OSHA Chemical Sampling Information — Benzene (CAS 71-43-2) and Hydrogen Sulfide (CAS 7783-06-4), osha.gov | LFL/UFL and OSHA PEL values, Section 6.1–6.2 |
| EXT-2 | NIOSH Pocket Guide to Chemical Hazards / IDLH documentation — Benzene, Hydrogen Sulfide | IDLH and REL values, Section 6.2 |
| EXT-3 | ACGIH Threshold Limit Values (referenced via OSHA/NIOSH compilations) | TLV values, Section 6.2 |
| EXT-4 | American Petroleum Institute, RP 941 — *Steels for Hydrogen Service at Elevated Temperatures and Pressures in Petroleum Refineries and Petrochemical Plants* (Nelson curves), and secondary engineering summaries (AIChE/CEP, AFPM) | HTHA screening method and carbon-steel temperature ceiling, Section 6.3 |
| EXT-5 | Published thermodynamics references on the Joule-Thomson effect and inversion temperatures of hydrogen, nitrogen, oxygen (e.g., standard thermodynamics texts and lecture references) | JT inversion temperature and sign correction, Section 6.4 |
| EXT-6 | Published catalytic-reforming reaction engineering literature — cyclohexane dehydrogenation enthalpy and general reforming reaction thermodynamics | Reaction enthalpy and endo/exo classification, Section 6.6 |

**Applicability note:** all EXT sources support general physical, chemical, or regulatory constants (flammability limits, exposure limits, alloy behavior, thermodynamic properties) that are not specific to ILS-10315 or to Run18's actual batch chemistry. They do not, and cannot, substitute for the site-specific evidence still required under F-02, F-04, F-05, and D-01 through D-07. Where a calculation in Section 6 combines an EXT source with an intake-form value (e.g., Section 6.5, 6.7), the intake-form value is cited as "evidenced" per Appendix B and the external constant is cited separately, so the workshop can see exactly which part of each conclusion is site-specific and which is a general screening assumption.
