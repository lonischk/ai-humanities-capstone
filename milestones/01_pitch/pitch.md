# Milestone 1 — Pitch
**Due: 30.10.2026**

Fill in each section below. A page is enough; these are prompts, not a form.

---

## Working title
<!-- A short name for your project -->
Sherds in Conversation: A Local Dialogue Assistant for Pottery Identification

## The theme and question
<!-- What are you exploring, and why does it matter to you? -->
Archaeological pottery is identified through features such as firing, temper, hardness, surface treatment, and manufacturing technique. This knowledge is scattered across typologies and excavation reports and is hard for beginners to access. My question: can an AI assistant guide a user through targeted questions about a sherd's characteristics and, drawing on open-access literature, suggest plausible ware types? And where does text-based identification reach its limits? The topic matters to me because I studied archaeology, and pottery identification is a classic case where expert knowledge is well documented but hard to query.

## The material
<!-- What will your system draw on? Who created it, and whose voices might be missing? -->
Open-access typologies, ware descriptions, and excavation publications on [period/region, e.g. Roman provincial pottery or medieval pottery in eastern Austria], covering roughly 5 to 10 ware types. Each ware is prepared as a short, consistently structured document with source and license information. The material was created by professional archaeologists and institutions, so it reflects the perspective of published research. Likely gaps: poorly published regions and periods, literature behind paywalls, and the practical knowledge of excavation workers and finds processors that rarely appears in print.

## Why AI?
<!-- What could an AI system help you see or do here, and where might it mislead? -->
A language model can hold a dialogue, accept feature descriptions in everyday language, and match them against ware descriptions via retrieval (RAG). Without AI, a beginner has to work through identification keys by hand. The risks: the model may confuse similar wares, invent features, or sound more certain than the evidence allows. To counter this, the system will show its source with every answer, offer several candidates instead of one "solution," and refer to experts for final identification.

## Who is it for?
<!-- Who might use what you build? -->
Archaeology students, volunteers at museums and excavations, and interested members of the public who want first orientation on a find.

## Your team
<!-- Who is involved, and what does each person bring? -->
Individual project. I bring a BA in Archaeology and Sociology as well as practical skills in Python and data preparation. I will implement the system with local tools (Ollama).

## Concerns
<!-- The biggest technical or ethical uncertainty you can foresee -->
Text descriptions cannot replace handling and seeing a sherd, so some distinguishing features may not be expressible in words. Technically, small local models sometimes follow sources poorly, which I will test and document. Ethically, results must stay clearly labeled as suggestions so that nobody misclassifies finds or adopts wrong dates.
