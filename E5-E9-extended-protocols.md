# E5-E9. Extended Protocols

**Project:** EAV-TIRD-001
**Tests:** P11 Push-Pull Polarity, P12 On-Off Gate, P13 Curvature, P14 Frame Recurrence, P15 Intuition Accuracy, P16 Projection and Alignment
**Status:** Protocol Summaries Only. Full protocols to be expanded before preregistration.
**No data collected for any protocol.**

These five protocols are separable. Failure of one does not reject the others. Each has its own falsification threshold, decided in advance.

---

## E5. Hysteresis Width - Tests P12 On-Off Gate

**Claim:** Coupling is active only above a threshold. When coupling is turned on and then off, the on-threshold and off-threshold differ. That difference is hysteresis width.

**Design:** Within-subjects threshold titration. Stimulus intensity is increased stepwise until coupling is detected (on-threshold), then decreased stepwise until coupling is lost (off-threshold). Repeat 3 cycles per participant.

**Primary Outcome:** Hysteresis width = on-threshold minus off-threshold.

**Falsification:** If 95% CI for mean hysteresis width lies entirely inside `|width| < 0.05` standardized units, P12 as stated is rejected.

**Controls:** Order counterbalanced, sham trials with no stimulus, experimenter blind to threshold.

**N:** 40 participants. Power to detect width = 0.15, SD = 0.20, alpha = 0.05, power = 0.80.

**Analysis:** Paired t-test on on- vs. off-threshold. Report mean width, 95% CI, effect size.

---

## E6. Curvature Residual Delay - Tests P13 Curvature

**Claim:** Concave and convex local geometry are distinct dimensional aspects of the same spacetime support. After correcting for medium, residual group delay depends on controlled local curvature.

**Design:** Time-of-flight experiment, same apparatus as E3, with added curvature factor. Two curvature conditions: concave vs. convex, matched on path length, medium, and obstruction.

**Primary Outcome:** Residual group delay after medium correction.

**Falsification:** If 95% CI for concave-minus-convex residual delay lies entirely inside `+/- 20 ps`, P13 as stated is rejected.

**Controls:** Path length verified by interferometry per condition. Temperature covariate. Calibration blocks every 10 blocks.

**N:** 120 blocks per curvature condition (240 total). Power to detect 30 ps difference with SD = 60 ps.

**Analysis:** Linear model: residual delay ~ curvature + medium + temperature + (1|day). Primary test is curvature coefficient.

---

## E7. Frame Recurrence - Tests P14 Frame Recurrence

**Claim:** The reflexive sequence implies periodic return of frames. Palindromic stimuli produce higher rates of subjective recurrence reports and EEG recognition markers than non-palindromic stimuli.

**Design:** Within-subjects EEG study. Participants view sequences of visual frames: palindromic vs. ascending vs. shuffled, matched on content. Continuous EEG recorded.

**Primary Outcomes:**
1. Subjective recurrence report rate ("I have seen this frame before" - yes/no)
2. EEG recognition marker: P300 amplitude / old-new effect in pre-registered time window 300-500 ms

**Falsification:** If 95% CI for palindromic vs. shuffled difference in recurrence rate lies inside `|d| < 0.2` AND EEG marker CI lies inside `|d| < 0.2`, P14 as stated is rejected.

**Controls:** Stimuli piloted for equal familiarity. Presentation order randomized. Participant blind to hypothesis.

**N:** 48 participants. Power to detect d = 0.45, alpha = 0.05, power = 0.80.

**Analysis:** Mixed model for recurrence rate. Pre-registered EEG window, no post-hoc window selection. Report both outcomes.

**Ethics:** Ethics approval required. EEG is non-invasive. Voluntary withdrawal.

---

## E8. Intuition Accuracy Under Time Pressure - Tests P15 Intuition

**Claim:** Intuitive judgment is a rapid low-bandwidth readout from a broader perception window. Accuracy under time pressure correlates with Phi and sigma_O.

**Design:** Within-subjects, time-pressure manipulation. Participants make intuitive judgments on novel stimuli (e.g., which of two patterns is coherent) under 3 conditions: no time pressure (10s), moderate (3s), high (1s).

**Primary Outcome:** Accuracy under high time pressure.

**Predictors:** Phi proxy (integrated information measure from task / questionnaire) and sigma_O proxy (perception-window width measure from baseline task).

**Falsification:** If 95% CI for correlation between accuracy and Phi lies inside `|r| < 0.15` AND correlation with sigma_O lies inside `|r| < 0.15`, P15 as stated is rejected.

**Controls:** Stimulus difficulty matched across conditions. Order counterbalanced. Baseline accuracy measured without time pressure.

**N:** 100 participants. Power to detect r = 0.30, alpha = 0.05, power = 0.80.

**Analysis:** Correlation + regression: accuracy ~ Phi + sigma_O + baseline accuracy + age. Report r, beta, 95% CIs.

**Ethics:** Ethics approval required. No deception beyond withholding hypothesis.

---

## E9. Projection-Alignment Synchrony - Tests P16 Projection and Alignment

**Claim:** Projection maps internal state onto external layer. Alignment is match under the reflexive operator. Synchrony improves when stimuli respect palindromic structure.

**Design:** Dyadic synchrony task. Pairs of participants perform a joint rhythmic / tapping / movement task. Two stimulus conditions: palindromic-structured cues vs. non-palindromic cues, matched on tempo and complexity.

**Primary Outcome:** Synchrony index: phase-locking value between partners, averaged over trial.

**Falsification:** If 95% CI for palindromic-minus-non-palindromic synchrony difference lies entirely inside `|d| < 0.2`, P16 as stated is rejected.

**Controls:** Pairs matched on prior familiarity (strangers only). Order counterbalanced. Experimenter blind to condition.

**N:** 40 pairs (80 participants). Power to detect d = 0.50, alpha = 0.05, power = 0.80.

**Analysis:** Paired t-test on synchrony index by condition. Report mean difference, 95% CI, effect size.

**Ethics:** Ethics approval required. Informed consent for dyadic recording. Data pseudonymized.

---

## GENERAL RULES FOR E5-E9

1. Each protocol must be expanded to a full standalone file before preregistration.
2. Each protocol must have a frozen analysis script before data collection.
3. Each protocol must state its falsification threshold in advance. No threshold may be changed after data collection.
4. No data exist for any of these protocols.
5. All human-participant protocols require ethics approval and informed consent before recruitment.
