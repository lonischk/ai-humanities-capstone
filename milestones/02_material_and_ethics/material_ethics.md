# Milestone 2 — Material and Ethics Note
**Due: 13.11.2026**

---

## Your collection

**What is it?**
<!-- Describe the body of material your system will draw on -->
A small, curated collection of open-access texts describing ceramic ware types of [period/region, e.g. Roman provincial pottery or medieval pottery in eastern Austria]. It covers roughly 5 to 10 ware types. For each ware, the system needs descriptions of its distinguishing features: firing (oxidising/reducing), colour, temper, hardness, fracture, surface treatment, manufacturing technique, typical forms, decoration, and dating. The system will use this material to ask a user targeted questions and to suggest plausible ware types with source references.

**Where does it come from?**
<!-- Source(s), institution(s), creator(s), date range -->
Open-access typologies, ware catalogues, and excavation publications from [e.g. open-access repositories such as Zenodo or Propylaeum-DOK, the Archaeology Data Service, and publications of institutions working on the chosen region]. Creators are professional archaeologists and research institutions. The publication dates will be recorded per document ([date range, e.g. 1990 to 2024]). Every document is logged in a source table (title, author, institution, year, URL/DOI, licence).

**How will you prepare it?**
<!-- Cleaning, chunking, OCR, transcription, format — describe your pipeline -->
1. Select relevant passages from each source (ware descriptions, not the whole report).
2. Convert them into plain text or Markdown; where a PDF has no usable text layer, run OCR and check it manually.
3. Rewrite nothing: keep original wording, but add a short header per document with ware name, source, page, and licence.
4. Structure each ware as one document with the same feature fields, so the retrieval step can match user answers to comparable fields.
5. Split into chunks by feature section, keeping source metadata attached to each chunk.
6. Load into a local setup (Ollama with a local retrieval front end) and test whether retrieved chunks match the question asked.

**Size and scope**
<!-- Approximate number of documents / images / recordings, word count, etc. -->
About [15 to 30] source documents, condensed into 5 to 10 ware documents of roughly 300 to 800 words each, so about 3,000 to 8,000 words in total. Text only; no images in the first version. The scope is deliberately narrow (one period/region) to keep the material checkable by hand.

---

## Ethical considerations

**Copyright and licensing**
<!-- Is the material in the public domain? Under a Creative Commons licence? Used with permission? -->
Only material that is public domain or openly licensed (e.g. CC BY, CC BY-SA, CC0) is used. The licence of each document is checked and recorded in the source table, and documents with unclear or restrictive licences are excluded. Because the system runs locally, no material is uploaded to external services. The system always shows the source of the passage it relies on, and the project documentation credits all authors and licences.

**Consent**
<!-- If the material involves living people or community archives: how was consent obtained? -->
The collection contains no personal data or community archives, so no consent is needed for the material itself. If I use photos or descriptions of real sherds from a museum or private collection, I will only do so with permission and note it here. People who test the prototype will be told that their inputs are used for evaluation, and no personal data is stored.

**Whose voices are present?**
<!-- Who created this material, and whose perspectives does it centre? -->
Professional archaeologists, ceramic specialists, and academic institutions, mostly writing in [German/English]. The material centres a scientific, typological view of pottery: classification by technical and formal criteria.

**Whose voices are absent or marginalised?**
<!-- Who is missing, and does that matter for your question? -->
Missing are regions and periods that are poorly published or not open access, and non-academic knowledge such as that of excavation workers, finds processors, and local communities, as well as the potters' perspective (craft knowledge). It matters for my question because the system will favour well-published wares and may wrongly suggest them for finds that belong to less documented traditions. I will document this gap and test for it.

**Limits you will communicate to users**
<!-- What should users know before trusting the system's outputs? -->
- The system gives hints, not identifications; a specialist must examine the sherd.
- It only knows the wares in its collection; a find outside them can still be matched wrongly.
- Text descriptions cannot capture everything that is visible or tangible on a sherd.
- Small local models can misread or mix sources, so users should check the cited passage.
- Dates and ware names reflect the sources used and may differ in other regional typologies.
