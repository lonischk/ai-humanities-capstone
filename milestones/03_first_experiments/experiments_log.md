# Milestone 3 — First Experiments Log
**Due: 27.11.2026**

See `src/evaluation/questions.md` for the test questions. The experiments below are early explorations with a small set of fictional sherd descriptions; the final test set (with known ware types from published sources) follows once the material is fixed.

---

### Experiment 1 — Baseline, German question
Date: 2026-11-[TT]
Model: llama3.2:3b and qwen2.5:3b (via Ollama, local)
Prompt version: none
Layer: baseline

**Question asked:**
> Eine Scherbe ist rotbraun, hart gebrannt, hat feine Sandmagerung und eine glatte Oberfläche. Um welche Keramik könnte es sich handeln?

**Output:**
> [paste both outputs from the terminal]

**What I noticed:**
- Both models answered in German and gave rather short answers.
- llama3.2:3b looks more detailed, but the content stays superficial.
- qwen2.5:3b is shorter and gives more information about the pottery itself, but does not mention that its answer is only a suggestion.
- Both models invent pottery type names, so the output is questionable and not usable for beginners who cannot check it.

**What I will change next:**
- Switch the whole system to English, because small local models tend to perform better in English and most open-access pottery literature is English.
- Add a prompt with rules (several candidates, no invented names, mention that a specialist must check).

---

### Experiment 2 — Baseline, English question
Date: 2026-11-26
Model: llama3.2:3b and qwen2.5:3b
Prompt version: none
Layer: baseline

**Question asked:**
> A sherd is reddish-brown, hard-fired, has fine sand temper and a smooth surface. What kind of pottery could it be?

**Output:**
> [paste from docs/m3_outputs.md, Q1 baseline]

**What I noticed:**
- [Is the answer longer/shorter/better than in German?]
- [Which ware names appear? Are they real?]

**What I will change next:**
- [...]

---

### Experiment 3 — Prompted (v001), English question
Date: 2026-11-26
Model: llama3.2:3b and qwen2.5:3b
Prompt version: v001 (rules: 1 to 3 candidates, justify with features, ask for missing features, no invented sites or dates, refer to a specialist)
Layer: prompted

**Question asked:**
> A sherd is reddish-brown, hard-fired, has fine sand temper and a smooth surface. What kind of pottery could it be?

**Output:**
> [paste from docs/m3_outputs.md, Q1 prompted]

**What I noticed:**
- [Does it now name several candidates? Does it ask for missing features? Does it still invent names?]
- [Does it remind the user to consult a specialist?]

**What I will change next:**
- [e.g. add retrieval from open-access ware descriptions so names and features come from real sources]

---

### Experiment 4 — Other question types (grey burnished ware, coarse shell-tempered ware)
Date: 2026-11-26
Model: llama3.2:3b and qwen2.5:3b
Prompt version: none vs. v001
Layer: baseline vs. prompted

**Questions asked:**
> Q2: A sherd is grey, fired in a reducing atmosphere, wheel-thrown, with a burnished surface and rouletted decoration. What kind of pottery could it be?
> Q3: A rim sherd is coarse, handmade, tempered with crushed shell, soft, and has a sooty black exterior. What kind of pottery could it be?

**Output:**
> [paste the most interesting examples from docs/m3_outputs.md]

**What I noticed:**
- [Do the models handle clearly different fabrics differently? Where do they guess?]

**What I will change next:**
- Fix period and region, collect open-access ware descriptions, and build the RAG layer so that suggestions can be traced to a source.

---

## Model comparison notes

| Model | Strength observed | Weakness observed |
|-------|-------------------|-------------------|
| llama3.2:3b | [e.g. longer, more structured answers] | Superficial content; invents pottery names |
| qwen2.5:3b | [e.g. shorter, more focused on the pottery itself] | Invents pottery names; in the baseline no hint that its answer is only a suggestion |

**Overall:** Without a prompt and without sources, both small local models invent ware names. [Add what the prompt changed.] This motivates the next layers: a stricter prompt and retrieval from a curated open-access collection.
| TODO  | TODO              | TODO              |
