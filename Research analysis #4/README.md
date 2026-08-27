# Research Paper Analysis #04 — Cancer Biomarker Science

**Evidentiary Architecture in Cancer Biomarker Science**

A biomarker that's already changing what oncologists do and a biomarker that's still just a correlation in a discovery cohort can end up described in almost the same tone on the page. This analysis is about that gap, and what it takes to see it.

## The paper

Liu, H., Karsidag, I., Golin, R., & Wu, G. (2025). "Bridging Discovery and Treatment: Cancer Biomarker." *Cancers*, 17(22), 3720. https://doi.org/10.3390/cancers17223720

It's a narrative review — not new experimental data, a synthesis of existing literature — covering cancer biomarkers across sample types (tissue, blood, imaging), detection strategies, molecular modalities (DNA, RNA, epigenetic, protein, metabolite, microbial), clinical applications, translational barriers, and personalized-medicine approaches.

## Why I picked this paper

Most biomarker reviews I'd read before this one organize themselves by molecular category — here's what DNA-based markers can do, here's what liquid biopsy can do, and so on. That's a reasonable way to organize a paper. But it left me with a question the category structure doesn't really answer: how much evidence actually separates a biomarker that's promising from one that's ready to be part of a treatment decision? This review covers both kinds side by side, which made it a useful place to try to answer that.

## The question I kept coming back to

Does surveying a biomarker landscape this wide give a coherent account of what's actually ready for clinical use, or does it flatten biomarkers sitting at very different evidence levels into the same category of "promising"? I didn't have a firm answer going in. I'm still not sure I have a clean one now, but working through the paper's own examples got me a lot closer.

## The evidence pipeline

One thing that helped me was reconstructing where the paper's examples sit along something like this:
The review itself isn't organized this way — it's organized by biomarker type. So this placement is my own reconstruction for the purposes of this analysis, not a classification the authors published.

| Example | Where I placed it | Why |
|---|---|---|
| MGMT promoter methylation (glioblastoma) | Routine implementation | Cited as directly informing treatment selection (temozolomide) in current practice |
| ctDNA fragmentomics (MRD detection) | Clinical validation, approaching utility | Detects relapse ahead of imaging in the cited cohorts, but the ESMO guideline reflects that utility isn't fully established for cfDNA alone |
| Microbiome composition (checkpoint-inhibitor response) | Discovery / early clinical validation | Correlative association only — the authors themselves flag contamination and batch-effect problems as unresolved |
| AI-driven multimodal phenotyping | Discovery | Presented as an emerging direction; no clinical validation evidence is cited for the integration claim itself |

## What I think the review does well

The multi-axis classification — sample type, detection dimension, molecular modality — actually does useful work. It makes clear that two biomarkers in the "same" molecular class can behave very differently depending on how they're detected, which stops you from treating biomarker discovery as one flat activity. The translational-barriers section is similarly specific: it names six distinct failure points instead of gesturing at "translation is hard" as a single vague problem. And section 5.6, on machine-learning reproducibility, is genuinely careful — it names leakage via premature feature selection, temporal leakage, and test-set-informed hyperparameter tuning as specific, distinguishable failure modes, not just "AI models can overfit."

## Where I became more critical

A few things stood out once I started checking claims against evidence stage rather than just reading for content:

- There's no consistent evidence-level tagging. A biomarker at routine clinical use and one still at the discovery stage get described in structurally similar declarative sentences, so tone alone doesn't tell you which is which.
- Some limitations are proportionally under-discussed relative to the claims they qualify. The metabolomics section is the clearest case — pre-analytical variability and rapid degradation of metabolites, which is a real reason metabolomic biomarkers struggle to replicate across cohorts, gets six words at the end of an otherwise promise-focused sentence.
- The methodological rigor the paper applies to ML reproducibility in section 5.6 doesn't carry over to its earlier discussion of AI-driven multimodal phenotyping. Same kind of claim — a model's reported performance — evaluated with very different levels of scrutiny depending on where it shows up in the paper.

## Clinical validity ≠ clinical utility

This was the distinction that actually reshaped how I read the rest of the paper. A biomarker can be genuinely clinically valid — reliably associated with a meaningful outcome — without there being evidence that acting on it changes what happens to the patient. MGMT methylation gets much closer to that bar: the review describes it as informing temozolomide treatment decisions, so it contributes to management rather than serving only as a prognostic association. ctDNA fragmentomics detects relapse earlier than imaging in the cited cohorts, which is a real clinical-validity claim — but earlier detection isn't the same as demonstrating that acting on it earlier improves survival. No interventional trial testing that specific question is cited.

## The computational side

Section 5.6 raises a question worth sitting with beyond this paper: can a reported model performance number — accuracy, AUC, whatever it is — be trusted as evidence of generalizable value, or does it partly reflect an artifact of how the model was validated? Leakage from the test set into training, whether through premature feature selection or hyperparameter tuning informed by test-set results, inflates reported performance in ways that don't show up unless someone checks for them specifically. I didn't run any of these analyses myself. What the review's own inconsistency showed me is that this kind of scrutiny has to be applied deliberately, every time a model's performance is cited — it doesn't automatically transfer from one section of a paper to another just because the authors clearly know how to do it.

  Discovery → Analytical Validation → Clinical Validation → Clinical Utility → Regulatory Adoption → Routine Implementation
## What I took away from it

- Discovery and validation aren't stages of the same activity — they require different study designs and different standards of evidence entirely.
- Biological plausibility doesn't establish clinical usefulness on its own.
- A biomarker being reported in the literature is not the same as a biomarker being validated.
- Reproducibility failures show up in different forms across modalities — inter-lab discordance, batch effects, ML leakage — but they're often the same underlying problem: an evaluation that had access to information it shouldn't have had.
- How much a limitation should weigh on a claim depends on how directly it constrains that claim, not on how much space the authors gave it.

## Questions I'd follow up

These are proposed extensions from my analysis, not studies I ran:

1. Does acting on earlier ctDNA-based MRD detection — treatment escalation, specifically — actually improve recurrence-free or overall survival compared with standard surveillance, or does earlier detection alone not translate into better outcomes?
2. How consistent are analytical performance metrics for ctDNA fragmentomic assays across independent labs and platforms? The review doesn't report this at the platform level.
3. Would applying a leakage-audit framework, similar to the one proposed in section 5.6, to published AI-driven multimodal phenotyping studies change what their reported performance actually looks like?

Working through this changed something in how I want to read biomarker papers going forward — not just asking what a paper reports, but asking where a given claim actually sits between discovery and implementation, and what evidence would still need to exist to move it further along.


The PDF contains the complete critical analysis, the evidence-stage reconstruction, the methodological scrutiny, the proposed research extensions, and full references.

## Reference

Liu, H., Karsidag, I., Golin, R., & Wu, G. (2025). Bridging Discovery and Treatment: Cancer Biomarker. *Cancers*, 17(22), 3720. https://doi.org/10.3390/cancers17223720

---

This is part of my Research Portfolio Series and reflects my independent critical reading of the published paper above. The original review belongs to its authors and to *Cancers*; the interpretation, the evidence-stage reconstruction, and the commentary here are my own.
