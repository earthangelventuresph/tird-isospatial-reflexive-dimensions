# E1. Entanglement versus Environmental Frequency

**Project:** EAV-TIRD-001
**Tests:** P1 Isospatial Layered Coexistence, P7 Entanglement as Inter-Layer Coupling
**Hypothesis H1:** The CHSH parameter S varies systematically with environmental electromagnetic frequency because inter-layer coupling J_ab depends on the perception kernel G.
**Status:** Protocol Only. No data collected. No results claimed.
**Preregistration Required:** Yes. Analysis script must be frozen before data collection.

---

## 1. CLAIM IN PLAIN LANGUAGE

TIRD asserts that entanglement is not just correlation between two particles. It is coupling between layers that share the same spacetime coordinate.

If layers are isospatial and frequency-stratified, then changing the environmental frequency should change how strongly layers couple. That change must show up as a change in measured entanglement strength.

Standard branching models predict NO frequency dependence. TIRD predicts a measurable slope.

This experiment discriminates between them.

## 2. FORMAL PREDICTION

Cross-layer coupling:
`J_ab = J_0 * G(omega_k, omega_O) * exp(-D / D_crit)`

Where G is the Gaussian perception kernel.

Predicted outcome:
`S(f) = S_0 + beta * f + error`

TIRD predicts `beta != 0` and systematically structured, not random drift.

Null model predicts `beta = 0`.

## 3. FALSIFICATION THRESHOLD - DECIDED IN ADVANCE

**FALSIFIED IF:** The 95% Confidence Interval of the slope `beta` lies entirely inside `|dS/df| < 0.02 per frequency step`.

If that happens, P7 as stated is rejected. P1 is weakened but not automatically rejected, because other couplings may exist.

**SUPPORTED IF:** 95% CI excludes zero AND lies outside the equivalence bound, AND the effect replicates in an independent run with pre-registered analysis.

## 4. DESIGN

**Design:** Within-subjects repeated measures, frequency-blocked, counterbalanced order.

**Independent Variable:** Programmable EM drive frequency. Minimum 6 frequency levels, equally spaced, covering a range chosen to avoid known resonance artifacts of the apparatus.

**Dependent Variable:** CHSH parameter S, calculated from coincidence counts in the standard 4-setting Bell test.

**Controls:**
- Shielded enclosure, Faraday + mu-metal
- Temperature stabilized to +/- 0.5 C
- Vibration isolation
- Laser power monitored continuously
- Detector efficiency logged per block

## 5. APPARATUS

1. Polarization-entangled photon pair source (SPDC)
2. Two polarization analyzers with motorized waveplates
3. Single-photon detectors with time-tagging
4. Programmable EM drive inside enclosure, frequency logged independently
5. Environmental sensors: temperature, humidity, EM background, vibration

## 6. PROCEDURE - STEP BY STEP

1. Calibrate source. Verify S > 2.0 at baseline frequency with no drive. Record baseline.
2. Randomize order of frequency levels using pre-generated randomization list. Experimenter running the session is blind to order.
3. For each frequency block:
   a. Set EM drive to target frequency. Wait 10 minutes for stabilization.
   b. Collect minimum 10,000 coincidence events per analyzer setting.
   c. Log all environmental sensors.
   d. Repeat block twice, back-to-back, to check short-term drift.
4. Repeat full frequency sequence on a second day with reversed order.
5. No analysis of S by frequency until all data collection is complete.

## 7. SAMPLE SIZE

**Power calculation:** To detect a slope of 0.05 per step with SD = 0.08, alpha = 0.05, power = 0.80, minimum N = 48 blocks total (8 blocks per frequency level).

**Planned:** 72 blocks total (12 per frequency level) to allow for 20% data loss and drift correction.

**Stopping rule:** Data collection stops at 72 blocks. No optional stopping. No peeking at slope during collection.

## 8. BLINDING

- Data collector is blind to frequency order.
- Analyst receives data with frequency labels coded as A-F until primary analysis is complete.
- Unblinding only after primary slope estimate is locked.

## 9. ANALYSIS PLAN - FROZEN

1. Compute S per block using standard CHSH formula.
2. Fit linear mixed model: `S ~ frequency + (1|day) + (1|block_order) + temperature + laser_power`
3. Primary test: slope of frequency.
4. Sensitivity: Re-fit excluding first block of each day. Re-fit with drift term (time).
5. If drift explains the effect, result is declared INCONCLUSIVE, not supportive.
6. Report full 95% CI, not just p-value.

## 10. CONFOUNDS AND HOW THEY ARE RULED OUT

- **Thermal drift:** Temperature is a covariate. If temperature correlates with frequency, experiment is invalid and must be repeated.
- **Stray coupling:** Run sham blocks with drive powered but antenna disconnected. If sham shows same slope, effect is artifact.
- **Detector drift:** Interleave calibration blocks every 6 blocks.

## 11. DATA AVAILABILITY

Raw time-tags, coincidence counts, environmental logs, and frozen analysis script will be deposited in `data/E1/` upon collection. No data exist yet.

## 12. ETHICS / SAFETY

No human participants. Laser safety review required. EM exposure within institutional limits.
