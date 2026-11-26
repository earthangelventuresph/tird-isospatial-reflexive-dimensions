# E2. Palindromic Structure and Memory Integration

**Project:** EAV-TIRD-001
**Tests:** P4 Reflexive Palindromic Symmetry, P9 Memory Integration
**Hypothesis H2:** Palindromic encodings produce higher memory integration than non-palindromic encodings because integration is maximal under the reflexive mirror operator.
**Status:** Protocol Only. No data collected.
**Preregistration Required:** Yes.

---

## 1. CLAIM IN PLAIN LANGUAGE

TIRD asserts memory integration is not just repetition. It is mirroring.

A sequence that reads the same forward and backward - 1-2-3-3-2-1 - aligns with the reflexive operator R. That alignment produces maximal integration.

Therefore, people who learn palindromic sequences will remember them better after 24 hours than people who learn ascending or shuffled sequences of equal length and difficulty.

## 2. FORMAL PREDICTION

Memory integration:
`M = sum_i w_i * <x_i, R(x_i)>`

M is maximal when sequence is palindromic.

Predicted ordering of 24-hour delayed recall:
`Palindromic > Ascending > Shuffled`
Primary contrast: Palindromic vs. Shuffled.

## 3. FALSIFICATION THRESHOLD

**FALSIFIED IF:** The 95% CI for the Palindromic vs. Shuffled contrast lies entirely inside `|d| < 0.2` (Cohen's d).

Small effect = no support for P9 as stated.

**SUPPORTED IF:** Contrast d > 0.2, CI excludes 0, and effect holds after controlling for immediate recall.

## 4. DESIGN

**Design:** Three-arm, parallel-group, randomized controlled trial. Single-blind.

**Arms:**
- **Arm A - Palindromic:** Sequences structured as 1-2-3-3-2-1
- **Arm B - Ascending:** Sequences structured as 1-2-3-4-5-6
- **Arm C - Shuffled:** Same elements, randomized order, no palindromic structure

All arms matched on: total items, presentation time, number of repetitions, item difficulty.

## 5. PARTICIPANTS

**Inclusion:** Adults 18-65, normal or corrected vision/hearing, fluent in task language.
**Exclusion:** Diagnosed memory disorder, neurological condition, current use of memory-affecting medication, prior participation in similar study.

**Target N:** 180 total (60 per arm).

**Power:** To detect d = 0.45 between Palindromic and Shuffled, alpha = 0.05, power = 0.80, need 64 per arm. Planned 60 per arm + 10% attrition buffer = 66 per arm recruited, target 180 completers.

## 6. MATERIALS

- 12 sequences per participant, each 6 items long
- Items: neutral words, numbers, or shapes - one stimulus type only per study to avoid mixing
- Presentation: Computer screen, fixed timing, 2 seconds per item, 1 second inter-item interval
- 3 encoding repetitions per sequence

## 7. PROCEDURE

**Session 1 - Encoding (Day 0):**
1. Consent, demographics, baseline working memory screen.
2. Random assignment via computer-generated list, concealed from experimenter.
3. Encoding phase: Participant views 12 sequences in assigned structure.
4. Immediate recall test: Free recall immediately after encoding. This is a covariate, not the primary outcome.
5. Participant leaves. No rehearsal instructions given.

**Session 2 - Delayed Recall (Day 1, 24h +/- 2h):**
1. Free recall of all sequences, no cues.
2. Recognition test: 24 items, old/new judgment.
3. Subjective confidence rating 1-7.
4. Debrief.

## 8. OUTCOMES

**Primary Outcome:** Proportion correctly recalled at 24 hours (free recall, strict scoring - item + position correct).

**Secondary Outcomes:**
- Recognition accuracy (d-prime)
- Order accuracy
- Confidence calibration

## 9. BLINDING

- Participant is blind to hypothesis. Told study is about "sequence learning."
- Scorer of recall is blind to arm assignment.
- Analyst is blind to arm labels until primary analysis is locked.

## 10. ANALYSIS PLAN - FROZEN

1. Primary: ANCOVA, delayed recall ~ arm + immediate recall + age + baseline working memory.
2. Planned contrast: Palindromic vs. Shuffled.
3. Secondary contrast: Palindromic vs. Ascending.
4. No subgroup analysis unless pre-specified. No removal of outliers unless pre-defined rule ( >3 SD).
5. Report means, SDs, effect sizes, and 95% CIs for all arms.

## 11. CONFOUNDS

- **Difficulty difference:** All items piloted for equal difficulty across arms before main study. Pilot data reported separately.
- **Rehearsal:** Participants asked at Session 2 if they rehearsed. Rehearsers flagged in sensitivity analysis.
- **Expectation:** No mention of palindrome or mirror in instructions.

## 12. ETHICS

Ethics approval required before recruitment. Informed consent required. Voluntary withdrawal at any time. Data pseudonymized. No deception beyond withholding hypothesis, which is disclosed at debrief.

## 13. DATA AVAILABILITY

Anonymized trial data, randomization list, and frozen analysis script will be deposited in `data/E2/` upon collection. No data exist yet.
