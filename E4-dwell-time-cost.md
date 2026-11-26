# E4. Dwell-Time Cost

**Project:** EAV-TIRD-001
**Tests:** P3 Dwell-Time Cost of Presence
**Hypothesis H4:** Cost of sustained presence in a non-native layer / sustained non-native coupling grows nonlinearly (exponentially), not linearly, with dwell time.
**Status:** Protocol Only. No data collected.
**Preregistration Required:** Yes.

---

## 1. CLAIM IN PLAIN LANGUAGE

TIRD asserts presence has a cost, and the cost accelerates.

If you stay briefly in a non-native frequency band, disturbance is small. If you stay longer, disturbance does not just add up - it compounds.

The model predicts:
`C(tau) = C_0 * (e^(tau / tau_c) - 1)`

The competing null model is linear:
`C(tau) = k * tau`

This experiment compares the two models directly. It does not prove other layers exist by itself. It tests the cost function of P3.

## 2. OPERATIONALIZATION

Because direct inter-layer travel is not established, this protocol uses the closest operational proxy defined in TIRD:

**Sustained coupling task:** Participant maintains sustained attention / coupling to a non-native stimulus band for a graded duration. The stimulus band is defined in the lab as a frequency / task condition outside the participant's baseline preferred band, measured at baseline.

**Cost proxies (all pre-registered, one primary):**
- **Primary:** Performance degradation slope + physiological fatigue index (composite of heart-rate variability change + subjective fatigue)
- **Secondary:** Error rate, reaction time variability, subjective disturbance rating

No claim is made that this proxy IS inter-layer travel. It is a test of the cost function shape.

## 3. FALSIFICATION THRESHOLD

**FALSIFIED IF:** Linear model is preferred over exponential model by `Delta AIC > 10`.

Delta AIC > 10 is strong evidence for linear. If that happens, P3 as stated is rejected.

**SUPPORTED IF:** Exponential model is preferred by `Delta AIC > 10`, and tau_c estimate has 95% CI that excludes zero and is stable across two duration ranges.

If `|Delta AIC| <= 10`, result is INCONCLUSIVE.

## 4. DESIGN

**Design:** Within-subjects, graded duration, counterbalanced order.

**Independent Variable:** Dwell duration: 15, 30, 60, 90, 120 minutes. 5 levels.

**Dependent Variable:** Cost C(tau) at end of each duration block, measured as composite fatigue / performance degradation.

**Washout:** Minimum 48 hours between sessions. Order randomized.

## 5. PARTICIPANTS

**Inclusion:** Adults 18-50, normal sleep in prior 48h, no sleep disorder.
**Exclusion:** Cardiovascular condition affecting HRV, current fatigue-related illness, use of stimulants within 12h.

**Target N:** 40 completers.

**Power:** To distinguish exponential vs. linear with expected tau_c = 60 min, SD = 15%, alpha = 0.05, power = 0.80, need 36 completers. Planned 40 + 10% attrition = 44 recruited.

## 6. PROCEDURE

**Baseline Session:**
1. Consent, sleep diary, baseline HRV (5 min resting), baseline task performance.
2. Determine participant's native band / baseline task condition.

**Experimental Sessions (5 sessions, one duration each):**
1. Resting HRV 5 min.
2. Begin sustained coupling task at assigned duration.
3. Every 15 min: brief performance probe (2 min) + subjective fatigue rating 1-10. Probe does not break coupling.
4. At end of duration: full performance battery + HRV + subjective disturbance.
5. Recovery period 30 min. HRV re-measured.

**No session exceeds 120 min of sustained task.**

## 7. OUTCOMES

**Primary:** Composite Cost Index at end of block, standardized within participant.

**Secondary:**
- Error rate change from baseline
- Reaction time variability
- HRV change (RMSSD)
- Subjective fatigue

## 8. BLINDING

- Participant is told durations vary but not the hypothesis about exponential vs. linear.
- Analyst is blind to duration labels until primary model comparison is locked.

## 9. ANALYSIS PLAN - FROZEN

1. Compute Cost Index per block.
2. Fit two models to group mean Cost vs. tau:
   - Linear: `C = a + b*tau`
   - Exponential: `C = C_0 * (exp(tau / tau_c) - 1)`
3. Compare by AIC. Report Delta AIC (AIC_linear - AIC_exponential).
4. Fit mixed model with participant random effect as sensitivity check.
5. Report tau_c with 95% CI.
6. No post-hoc selection of different cost proxy if primary fails.

## 10. CONFOUNDS

- **General fatigue vs. dwell cost:** Control condition - same duration but native-band task - run on separate day. If control shows same exponential shape, effect is general fatigue, not dwell cost.
- **Sleep:** Sleep diary + actigraphy if available. Exclude sessions after poor sleep.
- **Time of day:** All sessions for a participant at same time of day +/- 1 hour.

## 11. SAFETY / STOPPING RULES

Participant may stop at any time. Session stops if: HR exceeds safety threshold, participant reports distress > 8/10, or experimenter observes adverse signs. No penalty for withdrawal.

## 12. ETHICS

Ethics approval required. Informed consent required. Voluntary withdrawal. Data pseudonymized.

## 13. DATA AVAILABILITY

Anonymized session data and frozen analysis script will be deposited in `data/E4/` upon collection. No data exist yet.
