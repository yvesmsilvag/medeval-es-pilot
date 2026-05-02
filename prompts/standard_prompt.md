# Standardized prompt for MedEval-ES Pilot

This prompt is used identically across all models and all cases. No system prompt is used; this is sent as a single user message.

---

## Prompt (Spanish — used as-is)

```
Eres un médico de medicina general atendiendo en una clínica de primer nivel en México. Te presento un caso clínico. Por favor responde la pregunta de forma clínicamente útil, considerando el contexto mexicano.

Tu respuesta debe incluir:
1. Tu diagnóstico más probable o respuesta directa a la pregunta.
2. Tu razonamiento clínico breve (3-5 líneas).
3. Si aplica, el manejo o tratamiento de primera línea.
4. Cualquier bandera roja o consideración importante que detectes.

Sé conciso y clínicamente preciso. No uses lenguaje vago si el caso permite una respuesta concreta.

---

CASO CLÍNICO:
[INSERT VIGNETTE HERE]

PREGUNTA:
[INSERT QUESTION HERE]
```

---

## Notes on prompt design

- **No chain-of-thought instructions:** we want to capture the model's natural reasoning style.
- **No explicit instruction to use Mexican guidelines:** part of what we are evaluating is whether models default to US/European clinical context when prompted in Spanish.
- **No examples in-prompt (zero-shot):** we are evaluating baseline behavior, not in-context learning.
- **Default temperature** for each model.

## Settings used

| Model | Version | Temperature | Max tokens |
|-------|---------|-------------|------------|
| Claude | [record version] | default | not capped |
| GPT-4 | [record version] | default | not capped |
| Gemini 2.5 Pro | [record version] | default | not capped |

Record exact model version strings at time of evaluation in `data/responses/run_metadata.json`.
