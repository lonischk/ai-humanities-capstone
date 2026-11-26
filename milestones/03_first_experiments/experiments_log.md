# Milestone 3 — First Experiments Log
**Due: 27.11.2026**

See `src/evaluation/questions.md` for the test questions. The experiments below are early explorations with three fictional sherd descriptions (written by me, not yet tied to a published ware type). Raw outputs of Experiments 2–4 are in `docs/m3_outputs.md`; they were produced with `src/m3_experiments.py`. Each run was done once, so outputs may vary between runs.

---

### Experiment 1 — Baseline, English, three sherd descriptions
Date: 2026-11-26
Model: llama3.2:3b and qwen2.5:3b
Prompt version: none
Layer: baseline

**Question asked:**
> Q1: A sherd is reddish-brown, hard-fired, has fine sand temper and a smooth surface. What kind of pottery could it be?
> Q2: A sherd is grey, fired in a reducing atmosphere, wheel-thrown, with a burnished surface and rouletted decoration. ...
> Q3: A rim sherd is coarse, handmade, tempered with crushed shell, soft, and has a sooty black exterior. ...

**Output:**
> Key excerpts (full texts in `docs/m3_outputs.md`):
> - Q1 llama: "...ancient Greek pottery, specifically from the Archaic period"; Q1 qwen: "...Chinese porcelain... Yue ware... Zhejiang province".
> - Q2 llama: "...ancient Roman pottery... 1st or 2nd centuries AD"; Q2 qwen: "...a 'Celadon'".
> - Q3 llama: lists "ceramic beads", African/Asian terracotta, Native American ceramics, Mediterranean/Middle Eastern; Q3 qwen: "Black Slip Ware", linked to Tang dynasty Chinese pottery.

**What I noticed:**
- Without a prompt, each model jumps to one confident guess and names a culture or region from very little information. llama3.2:3b leans towards Greek/Roman pottery, qwen2.5:3b towards East Asian ceramics (porcelain, celadon, Tang) in all three questions. This may reflect training data; I can only call it a hypothesis for now.
- Several suggestions contradict the description: reddish-brown, sand-tempered ware does not fit porcelain (Q1 qwen), and a burnished, rouletted grey ware does not fit celadon, which is a glazed ware (Q2 qwen).
- Terminology is confused. llama describes rouletting as raising small dots of clay and cutting them off (Q2), which is not how rouletting works (a toothed wheel is rolled over the surface). It also mixes decoration techniques, vessel shapes and ware types: "black-figure", "red-figure" and "kylix" appear as if they were fabrics (Q1). It also claims a glaze made with "pyroclastic" sand (Q1), which I could not verify.
- Some partial hits: for Q2 the Roman direction from llama is plausible, and for Q3 both Native American shell-tempered pottery (llama) and a link between shell temper and sooty black exteriors are at least thematically relevant. However, the soot is presented as a result of the shell temper, which is a wrong causal link (soot comes from use over a fire).
- No answer names a source, and no baseline answer tells the user that a specialist must check it.

**What I will change next:**
- Prompt v002 with stricter rules (see Experiment 3).
- Collect open-access ware descriptions for one period/region and build the RAG layer, so that suggestions can be traced to a source.

---

### Experiment 2 — Prompted (v001), English, three sherd descriptions
Date: 2026-11-26
Model: llama3.2:3b and qwen2.5:3b
Prompt version: v001 (rules: always name 1 to 3 ware types, justify with the given features, say which features are missing, do not invent sites, dates or references, remind the user that a specialist must examine the sherd; always answer in English)
Layer: prompted

**Question asked:**
> Same Q1–Q3 as in Experiment 1.

**Output:**
> Key excerpts (full texts in `docs/m3_outputs.md`):
> - Q1 llama: "Redware", "Earthenware with feldspathic temper", "Coloured earthenware with quartz temper"; Q1 qwen: "Ceramic Ware", "Terracotta", "Stoneware".
> - Q3 qwen: three candidates, all Mediterranean (Aegean/Minoan, Etruscan/Greek, Cretan).

**What I noticed:**
- The prompt works on format: both models always give three candidates with a justification, and the Greek/Chinese guesses of the baseline disappear in Q1.
- The "1 to 3 candidates" rule makes the models fill up with weak candidates. Q1 qwen offers "Ceramic Ware" as a ware type, which is a category so broad that it says nothing. Q3 qwen's three candidates are practically the same region.
- Rules are followed inconsistently. The specialist reminder appears in 2 of 3 answers for llama (Q1, Q3, not Q2) and in 1 of 3 for qwen (Q2 only). Both models still give date ranges in Q2 even though the prompt says not to invent dates.
- "Ask for missing features" fails in a revealing way: llama (Q3) asks for hardness and shape although the description already says "soft" and "rim sherd", and in Q1 it says hardness is not mentioned although "hard-fired" is in the question. qwen asks for the firing temperature in Q1. So the models do not reliably check what is already given.
- Some candidate names look doubtful, e.g. "Roman Grey Ware (Graeca Vulgaris)" and "Iron Age Grey Ware... often lead-glazed" in Q2 qwen. I could not match "Graeca Vulgaris" to a known ware name and need to check it in the literature before calling it invented.

**What I will change next:**
- Prompt v002: allow "up to 3, fewer if unsure", allow "no good match", forbid dates unless they come from provided sources, and add "only ask for features that are not already in the description".
- Run the same questions at a fixed temperature to make runs comparable.

---

### Experiment 3 — Q2 in detail: prompt made one model worse
Date: 2026-11-26
Model: llama3.2:3b
Prompt version: none vs. v001
Layer: baseline vs. prompted

**Question asked:**
> Q2: A sherd is grey, fired in a reducing atmosphere, wheel-thrown, with a burnished surface and rouletted decoration. What kind of pottery could it be?

**Output:**
> Baseline: "...likely... ancient Roman pottery... 1st or 2nd centuries AD".
> Prompted: first candidate "Greek Red-Figure pottery (5th-4th century BCE)", followed by Roman Late Republic/Early Roman and Hellenistic Greek pottery.

**What I noticed:**
- The prompted answer is worse than the baseline here. Red-figure pottery is characterised by a red and black painted decoration and does not fit a grey, reduced, burnished ware with rouletting. The model still says the grey colour and burnished surface are "consistent" with it.
- The model also claims that rouletted figures were commonly used in red-figure designs, which looks wrong to me.
- Forcing several candidates and a justification produces confident-sounding but unsupported reasoning. This is a useful failure case for the later failure analysis.

**What I will change next:**
- Add Q2-type cases (reduced grey ware) to the final test set with a known answer from a published source.
- Check whether retrieval from real ware descriptions removes this error.

---

## Model comparison notes

| Model | Strength observed | Weakness observed |
|-------|-------------------|-------------------|
| llama3.2:3b | Follows the prompt format well (three candidates with a justification, usually a specialist reminder). Sometimes points in a plausible direction (Roman for Q2 baseline, shell temper in Q3). | Confident technical mistakes (rouletting, "pyroclastic" glaze, feldspathic temper). Mixes up decoration technique, vessel shape and ware. The prompt made Q2 worse. Gives dates despite the rule. |
| qwen2.5:3b | Short, clear answers; the prompted version gives a readable justification per candidate. | Baseline drifts to East Asian porcelain/celadon in all three questions. Uses overly broad categories ("Ceramic Ware", "Terracotta", "Stoneware"). Forgets the specialist reminder in 2 of 3 answers. Some ware names unclear (e.g. "Graeca Vulgaris", "Black Slip Ware"). |

**Overall:** Without sources, both small local models produce plausible-sounding but often wrong suggestions and never cite anything. A prompt improves the format and removes the most obvious wrong regions, but also creates new problems (forced weak candidates, inconsistent rule-following). This motivates the next layers: a stricter prompt (v002) and retrieval from a curated open-access collection, evaluated on a fixed question set with known answers.

**Overall:** Without a prompt and without sources, both small local models invent ware names. [Add what the prompt changed.] This motivates the next layers: a stricter prompt and retrieval from a curated open-access collection.
| TODO  | TODO              | TODO              |
