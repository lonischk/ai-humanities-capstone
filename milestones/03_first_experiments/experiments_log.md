# Milestone 3 — First Experiments Log
**Due: 27.11.2026**
The experiments below are early explorations with three fictional sherd descriptions (written by me, not yet tied to a published ware type).. Each run was done once, so outputs may vary between runs.

---

### Experiment 1 — Baseline, English, three sherd descriptions
Date: 2026-11-26
Model: llama3.2:3b and qwen2.5:3b
Prompt version: none
Layer: baseline

**Question asked:**
> Q1: A sherd is reddish-brown, hard-fired, has fine sand temper and a smooth surface. What kind of pottery could it be?  
> Q2:A sherd is grey, fired in a reducing atmosphere, wheel-thrown, with a burnished surface and rouletted decoration. What kind of pottery could it be?   
> Q3: A rim sherd is coarse, handmade, tempered with crushed shell, soft, and has a sooty black exterior. What kind of pottery could it be?

**Output:**

*Q1 llama*: Based on the characteristics you described, it's likely that the sherd is a piece of ancient Greek pottery, specifically from the Archaic period (around 8th-6th centuries BCE).

The reddish-brown color and smooth surface suggest that it was fired at a relatively high temperature, which is typical of Greek pottery from this period. The fine sand temper is also consistent with Greek pottery, which often used a type of sand called "pyroclastic" to create a strong and durable glaze.

However, without more specific information, it's difficult to pinpoint the exact region or type of pottery. Greek pottery from this period was highly varied, and different regions produced different types of pottery with distinct characteristics.

Some possible options could be:

* Greek Black-figure pottery: This type of pottery is known for its bright red and black colors, which were achieved through a technique called "underglaze" painting.
* Greek Red-figure pottery: This type of pottery is characterized by a reddish-brown color and is often decorated with figures or scenes in red and black.
* Kylix pottery: Kylixes were a type of Greek cup or drinking vessel that were often decorated with scenes and figures in red and black.

If you have more information or context about the sherd, I may be able to provide a more specific identification.

*Q2 llama*: Based on your description, it's likely that the sherd is from ancient Roman pottery. Here's why:

1. Grey color: Roman pottery often had a grey or brownish color, which was achieved by firing in a reducing atmosphere.
2. Wheel-thrown: Roman potters used the potter's wheel to create symmetrical shapes, which would be consistent with a wheel-thrown piece.
3. Burnished surface: Roman potters often used a burnishing technique to create a smooth, glossy surface on their wares.
4. Rouletted decoration: Rouletting is a technique where a pattern is created by raising small dots of clay, then cutting them off, leaving a raised design. This technique was commonly used in ancient Roman pottery.

The combination of these characteristics suggests that the sherd is likely from Roman pottery, possibly from the 1st or 2nd centuries AD. However, without further information or analysis, it's difficult to pinpoint the exact type of pottery or the specific region it came from.

*Q3 llama*: Based on your description of the rim sherd, it's likely to be from a type of pottery that was used in ancient or traditional settings. Here are a few possibilities:

1. **Ceramic beads**: Rim shreds with a coarse, handmade texture and a sooty black exterior might be from ceramic beads. These beads were often used in jewelry or decorative objects.
2. **African or Asian terracotta**: The combination of a coarse, handmade texture and a sooty black exterior is consistent with some types of terracotta pottery from Africa or Asia. These types of pottery often featured coarse, unglazed surfaces.
3. **Native American ceramics**: Some Native American potters used crushed shell as a tempering agent, which could result in a sooty black exterior. Coarse, handmade pottery with this characteristic might be from certain Native American tribes.
4. **Ancient Mediterranean or Middle Eastern ceramics**: The combination of a coarse texture and a sooty black exterior is also consistent with some types of ancient Mediterranean or Middle Eastern ceramics, such as those from the Early Bronze Age or the Hellenistic period.

Without more information or context, it's difficult to pinpoint the exact type of pottery. If you have any additional details, such as the location where the sherd was found, the shape or size of the sherd, or any other distinctive features, I might be able to provide more specific information.


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

*Q1 llama*: Based on the features provided, here are three possible ware types for the sherd:

1. **Redware**: The reddish-brown color and hard-fired firing temperature suggest a redware pottery. The fine sand temper is consistent with the production of redware, which often used sand as a tempering material. Redware typically has a smooth surface, which aligns with the description.
2. **Earthenware with feldspathic temper**: The presence of fine sand as a tempering material is also consistent with earthenware wares that have been tempered with feldspar, a type of rock that contains feldspars. The reddish-brown color and hard-fired firing temperature are also characteristic of feldspathic tempered earthenwares. The smooth surface could be indicative of a well-made piece.
3. **Coloured earthenware with quartz temper**: Another possibility is a coloured earthenware with a quartz temper. The reddish-brown color is consistent with some coloured earthenwares, and the fine sand or quartz temper could have been used to achieve a smooth surface. However, the exact firing temperature and composition of the quartz would need to be known to confirm this.

It's essential to note that a specialist must examine the sherd more closely to make a definitive identification. Some features, such as the hardness, surface treatment, and decoration, are not mentioned in the description.

*Q3 qwen*: Based on the features you've described, this pottery sherd could potentially be from several types of Mediterranean or Near Eastern pottery:

1. **Mediterranean Pottery (e.g., Aegean or Minoan):** 
   - The handmade nature of the sherd aligns with the techniques often used in early pottery production.
   - The use of crushed shell as temper is common in some Mediterranean pottery types.
   - The sooty black exterior might indicate firing in open fires or low-temperature kilns, which was common in early pottery production.
   
2. **Mediterranean Pottery (e.g., Etruscan or Greek):**
   - The handmade aspect could also be indicative of early Greek or Etruscan pottery, which often used similar tempering materials and had similar firing practices.
   - The sooty black finish could suggest a similar firing method.

3. **Cretan Pottery (e.g., Early Minoan or Late Minoan):**
   - Given the specific use of crushed shell as temper, this might be closer to a Cretan or Aegean pottery type, as shell was a common tempering material in Minoan pottery.
   - The sooty black exterior could be consistent with the early firing practices of these cultures.

To narrow down the identification, more specific information about the firing conditions, surface treatment, and any decorative elements would be very helpful. If any of these details are available, they could significantly refine the identification to a specific type or time period.


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
*Baseline*: Based on your description, it's likely that the sherd is from ancient Roman pottery. Here's why:

1. Grey color: Roman pottery often had a grey or brownish color, which was achieved by firing in a reducing atmosphere.
2. Wheel-thrown: Roman potters used the potter's wheel to create symmetrical shapes, which would be consistent with a wheel-thrown piece.
3. Burnished surface: Roman potters often used a burnishing technique to create a smooth, glossy surface on their wares.
4. Rouletted decoration: Rouletting is a technique where a pattern is created by raising small dots of clay, then cutting them off, leaving a raised design. This technique was commonly used in ancient Roman pottery.

The combination of these characteristics suggests that the sherd is likely from Roman pottery, possibly from the 1st or 2nd centuries AD. However, without further information or analysis, it's difficult to pinpoint the exact type of pottery or the specific region it came from.

*Prompted*: Based on the features you provided, I would suggest the following possible ware types:

1. Greek Red-Figure pottery (5th-4th century BCE): The grey colour and burnished surface are consistent with the characteristic appearance of Greek red-figure pottery. The rouletted decoration is also consistent with this type of pottery, as rouletted figures were commonly used in red-figure designs. Additionally, the wheel-thrown shape and firing in a reducing atmosphere are also consistent with the techniques used during this period.
2. Roman Late Republic/Early Roman pottery (3rd-1st century BCE): Roman pottery from this period often featured burnished surfaces and rouletted decoration, particularly in the Late Republic and Early Roman periods. The grey colour and wheel-thrown shape are also consistent with this type of pottery. However, the exact firing atmosphere is not explicitly stated, and Roman pottery from this period was often fired in a reducing atmosphere, but the exact conditions are not well-documented.
3. Hellenistic period Greek pottery (3rd-1st century BCE): The rouletted decoration and burnished surface are consistent with the Hellenistic period Greek pottery, which was characterized by a more expressive and naturalistic style. The grey colour and wheel-thrown shape are also consistent with this type of pottery.

To confirm the identity of the sherd, I would need to know more information, such as the firing colour, hardness, surface texture, or shape. The firing colour, for example, could be either black or grey, depending on the firing atmosphere, and the hardness could provide more information about the clay body used.


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
