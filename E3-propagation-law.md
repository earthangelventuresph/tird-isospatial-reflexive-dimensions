# E3. Medium, Obstruction, Position, and Information-Dependent Propagation

**Project:** EAV-TIRD-001
**Tests:** P6 Generalized Propagation Law
**Hypothesis H3:** Effective signal velocity depends not only on refractive index, but also on obstruction geometry, spatial position, and information content of the transmitted stream.
**Status:** Protocol Only. No data collected.
**Preregistration Required:** Yes.

---

## 1. CLAIM IN PLAIN LANGUAGE

Standard physics says velocity depends on the medium: `v = c / n`.

TIRD asserts that is incomplete. Velocity also depends on three additional, independently measurable corrections:

`v_eff = c / (n + eta_obstruction + eta_position + eta_information)`

Where eta_information is a function of the Shannon entropy of the transmitted stream.

If TIRD is correct, two signals through the identical medium, with identical obstruction and position, but with different information content, will have measurably different time-of-flight.

This is the most feasible experiment in the program. It is recommended first.

## 2. FORMAL PREDICTION

`v_eff = c / (n + eta_O + eta_X + eta_I)`

`eta_I = k_I * H`, where H is Shannon entropy (bits/symbol) of the stream.

Null model: `eta_O = eta_X = eta_I = 0`.

TIRD predicts `eta_I != 0` and scales linearly with H.

## 3. FALSIFICATION THRESHOLD

**FALSIFIED IF:** The 95% CI for `eta_I` lies entirely within `+/- 1e-6`.

That is the equivalence bound. An effect smaller than this is declared null for practical purposes.

**SUPPORTED IF:** CI excludes zero, excludes the equivalence bound, and replicates across two independent media.

## 4. DESIGN

**Design:** Factorial time-of-flight experiment. Within-lab replication.

**Factors:**
- **Medium:** 2 levels (e.g., optical fiber vs. free-space, or two controlled refractive indices)
- **Obstruction:** 2 levels (clear path vs. standardized obstruction geometry)
- **Position:** 3 positions along path (near, mid, far transmitter position)
- **Information Content:** 3 levels of entropy (low: highly repetitive stream, medium: natural text, high: encrypted / random stream) - matched on total bits and duration.

All combinations tested. Order randomized.

## 5. APPARATUS

1. Stable pulsed laser / RF source with picosecond timing
2. Time-of-flight measurement system, resolution < 10 ps
3. Controlled path: fixed length, temperature-stabilized, length measured by interferometry to < 0.1 mm
4. Standardized obstruction: calibrated aperture / scatterer, geometry fixed
5. Signal generator that can produce streams of controlled entropy, verified by entropy calculation before each block
6. Environmental logging: temperature, pressure, humidity

## 6. PROCEDURE

1. Calibrate path length. Record baseline time-of-flight with empty medium, no obstruction, low-entropy stream. Repeat 20 times.
2. For each condition in randomized order:
   a. Set medium, obstruction, position.
   b. Generate stream with target entropy H. Verify H via calculation, log it.
   c. Transmit 1,000 pulses. Record time-of-flight for each pulse.
   d. Repeat block 3 times.
3. Interleave calibration blocks every 10 blocks.
4. No analysis of eta_I until all collection is complete.

## 7. SAMPLE SIZE

**Primary unit:** Block mean time-of-flight.

**Planned:** 3 (entropy) x 2 (medium) x 2 (obstruction) x 3 (position) = 36 conditions. 10 blocks per condition = 360 blocks total.

**Power:** To detect eta_I = 2e-6 with measurement SD = 3e-6, alpha = 0.05, power = 0.80, need minimum 200 blocks. Planned 360 provides margin for drift and exclusions.

## 8. BLINDING

- Operator sets entropy level from coded list (A/B/C) without knowing which is high vs. low until after primary analysis.
- Analyst receives data coded by condition until analysis is locked.

## 9. ANALYSIS PLAN - FROZEN

1. Compute mean time-of-flight per block.
2. Fit model: `TOF ~ medium + obstruction + position + H + (1|day)`
3. Primary test: coefficient of H, converted to eta_I.
4. Sensitivity: Fit separately by medium. If effect appears in only one medium, declare medium-specific, not general.
5. Report eta_I with 95% CI, and eta_O, eta_X estimates.

## 10. CONFOUNDS

- **Heating from signal generator:** Monitor temperature per block. Include as covariate. If temperature correlates with H, experiment is invalid.
- **Timing drift:** Calibration blocks correct for drift. Drift > 50 ps per hour triggers repeat of day.
- **Path length change:** Interferometric check before and after each day.

## 11. RELATION TO VACUUM c

Vacuum c remains constant in TIRD. This experiment does NOT claim to change c in vacuum. It claims effective velocity in a medium has additional corrections. A positive result requires reconciliation with standard dispersion theory, not a claim of superluminal vacuum propagation.

## 12. DATA AVAILABILITY

Raw time-of-flight traces, entropy calculations, environmental logs, and frozen script will be deposited in `data/E3/` upon collection. No data exist yet.

## 13. ETHICS / SAFETY

No human participants. Laser safety review required.
