# MedEval-ES Pilot

**Pilot benchmark: systematic error analysis of LLMs on Spanish-language general medicine clinical cases.**

A methodology-focused study (n=30) comparing Claude, GPT-4, and Gemini on diagnostic reasoning in Mexican Spanish, with a structured taxonomy of clinical error types.

---

## Why this project

LLMs are increasingly deployed in clinical settings. Most public benchmarks (MedQA, MedMCQA, USMLE-style) are in English and emphasize accuracy as a single metric. This study takes a different approach: **understanding *how* models fail**, not just whether they fail, in Spanish-language general medicine reasoning relevant to Mexican clinical practice.

The goal is not to rank models. It is to characterize their distinct failure modes — the kind of analysis a clinical team would need before deploying one of these tools in production.

## Research question

How do GPT-4, Claude, and Gemini differ in the *types* of errors they make when reasoning about general medicine clinical cases in Mexican Spanish, and what are the implications for clinical implementation?

## Hypotheses (pre-registered)

1. Models will exhibit different proportions of error types — not just different accuracy.
2. All models will show at least one systematic error pattern in Spanish-language clinical reasoning.
3. Models will perform worse on atypical presentations and culturally-contextualized cases than on classical textbook cases.

## Methodology

### Case design (n=30)

- 10 **classical cases**: textbook-style presentations
- 10 **atypical cases**: non-canonical presentations, easy-to-miss diagnoses
- 10 **culturally-contextualized cases**: Mexican epidemiology, occupational exposure, traditional medicine, regional disease patterns

Each case includes a clinical vignette (80–150 words), a single focused question, a gold-standard answer, and clinical reasoning.

### Gold standard

Established by combining:
- Mexican Clinical Practice Guidelines (CENETEC GPC)
- Author's clinical judgment (general practitioner, social service stage)
- Peer review for borderline cases

### Models evaluated

- Anthropic Claude (latest available)
- OpenAI GPT-4 (latest available)
- Google Gemini 2.5 Pro

All three models are evaluated using an identical standardized prompt, a single response per case, with default temperature.

### Error taxonomy

1. **Factual hallucination** — fabricated clinical facts
2. **Clinical reasoning error** — incorrect integration of correct facts
3. **Red flag failure** — missed urgent warning signs
4. **Cultural/contextual bias** — non-Mexican defaults applied
5. **Unjustified overconfidence** — categorical answers from insufficient data
6. **Excessive hedging** — refusal to commit when commitment is appropriate

### Evaluation rubric (per case × model)

- Correct / Partially correct / Incorrect
- If error: assigned to one or more of the 6 categories
- Qualitative observation (1–2 lines)

## Limitations (declared up front)

- Sample size (n=30) is exploratory, not statistically powered.
- Single response per case (no temperature variability analysis).
- Single evaluator (author) with peer review for ambiguous cases — not multi-rater.
- Mexican Spanish only; results may not generalize to other Spanish variants.
- Snapshot in time; model versions evolve.

This is a **pilot study**. Its purpose is to demonstrate a methodology and surface preliminary patterns — not to provide definitive comparative benchmarks.

## Repository structure

```
medeval-es-pilot/
├── README.md                       (this file)
├── methodology.md                  (extended methodology)
├── error_taxonomy.md               (detailed error definitions with examples)
├── limitations.md                  (extended limitations discussion)
├── data/
│   ├── cases/                      (30 clinical cases as JSON)
│   └── responses/                  (raw model outputs)
├── analysis/                       (Python notebooks for analysis)
├── figures/                        (output visualizations)
└── prompts/                        (standardized prompts used)
```

## Status

🚧 In progress — pilot study underway. Expected completion: [TWO WEEKS FROM TODAY].

## Author

Yves Silva — General practitioner (social service, Zimapán, Hidalgo, México), independently trained in machine learning and clinical AI.

[LinkedIn] · [Twitter/X]

## License

MIT for code. Cases and analyses released under CC BY 4.0.

## How to cite (once complete)

Silva, Y. (2026). *MedEval-ES Pilot: Error analysis of LLMs on Spanish-language general medicine reasoning*. GitHub repository.