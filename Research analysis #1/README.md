# Deep Learning for Predictive Medicine: A Critical Review

A critical analysis of Sharma et al. (2024), *"Advances in AI and Machine Learning for Predictive Medicine"* (Journal of Human Genetics), focused on the DeepInsight family of tabular-to-image deep learning methods.

---
## Table of Contents

- Overview
- Objectives
- Topics Covered
- Repository Structure
- Highlights
- Skills Demonstrated
- Key Takeaways
- Future Work
- References
- Acknowledgements
- License
## Overview

This repository contains a critical literature review of a 2024 review article from the *Journal of Human Genetics* that surveys DeepInsight and its derivatives — a set of methods that convert tabular omics data (gene expression, mutation, copy number) into image-like representations so that convolutional neural networks, originally designed for photographs, can be applied to genomic prediction problems.

I picked this paper because it sits at an intersection I find genuinely interesting: GWAS and multi-omics data keep accumulating faster than classical tools like random forests or SVMs can extract structure from them, and the DeepInsight approach offers a fairly unusual answer to that problem — not a new architecture, but a new way of representing the data so an existing, well-understood architecture (a CNN) becomes usable.

The review isn't a re-implementation or a new experiment. It's a written analysis: a summary of the paper's methodology and results, followed by my own assessment of where the approach holds up and where I think it's still shaky. Readers will get a breakdown of how the DeepInsight pipeline works, a summary of the reported results across drug-response prediction and cell-type annotation, a comparison against graph neural networks that the original paper doesn't make, and a list of open questions I was left with after reading it.

---

## Objectives

- Summarize the methodology behind DeepInsight, DeepFeature, DeepInsight-3D, and scDeepInsight
- Evaluate the strengths and weaknesses of tabular-to-image conversion for omics data
- Compare the CNN-based approach against graph neural networks as an alternative way of modeling gene relationships
- Identify open questions and possible follow-up experiments suggested by the paper

---

## Topics Covered

- DeepInsight tabular-to-image conversion (t-SNE / UMAP / kernel PCA + convex hull mapping)
- CNN-based classification of genomic and multi-omics data
- Transfer learning for small omics datasets
- Model interpretability via class activation maps (DeepFeature)
- Multi-omics integration (DeepInsight-3D) and single-cell RNA-seq annotation (scDeepInsight)
- Graph neural networks as a point of comparison
- Benchmarking inconsistencies across the reviewed methods

---

## Repository Structure

```
README.md
LICENSE
docs/
    revised_research_analysis.pdf
references/
    bibliography.md
```

---

## Highlights

The review includes a breakdown of the DeepInsight pipeline (dimensionality reduction → image construction → CNN classification → interpretability), a summary of the reported results for DeepInsight-3D (drug-response prediction) and scDeepInsight (cell-type annotation), and a discussion of strengths (reuse of mature CNN architectures, improved interpretability via CAMs) and weaknesses (limited validation across diverse datasets, computational cost, possible loss of biological information during image conversion).

It also includes a comparison between this CNN-based approach and graph neural networks — a comparison the original paper does not make but that I thought was worth drawing out, given how differently the two approaches handle gene-gene relationships. The review closes with the paper's stated future directions, a set of research extensions I'd consider pursuing myself, and a list of questions the paper left unanswered.

---

## Skills Demonstrated

- Literature Review
- Scientific Writing
- Critical Analysis
- Bioinformatics
- Machine Learning
- Computational Biology
- Research Communication

---

## Key Takeaways

- A CNN doesn't require pixels from a camera — DeepInsight's core contribution is a data representation trick, not a new model architecture, and that reframing is the most useful thing to take from this paper.
- Transfer learning from unrelated image datasets (ImageNet) meaningfully improves performance on small omics datasets, which matters a lot for rare-disease genomics where large datasets are rarely available.
- Interpretability (via DeepFeature's class activation maps) isn't a side feature here — it's what would let a clinician act on a prediction rather than just trust a black box.
- The biggest open weakness is that gene placement in the generated image comes from t-SNE/UMAP proximity, which reflects statistical similarity in the data, not a known biological relationship. That's a real gap next to methods, like GNNs, that encode gene interactions explicitly as edges.
- The paper's own benchmarking is somewhat inconsistent across methods and datasets, which makes it hard to say with confidence how this approach stacks up against alternatives like graph neural networks or transformers.

---

## Future Work

Based on the directions the authors themselves lay out, future work in this space is expected to involve:

- Integrating more omics layers simultaneously within the tabular-to-image framework
- Incorporating more domain-specific biological knowledge into training
- Moving toward real-time clinical applications where genomic data could inform treatment decisions
- Continued development of interpretability tools, which the authors flag as essential for clinical adoption

---

## References

Sharma, A., Lysenko, A., Jia, S., Boroevich, K. A., & Tsunoda, T. (2024). Advances in AI and machine learning for predictive medicine. *Journal of Human Genetics*. https://doi.org/10.1038/s10038-024-01231-y



---

## Acknowledgements

This is an independent educational analysis written for a personal research portfolio. All scientific credit for the work discussed belongs to the original authors of the reviewed paper and the methods it surveys.

---

## License

This repository is licensed under **CC BY 4.0** (Creative Commons Attribution 4.0 International).

A written review like this is closer to a piece of scholarship than to software — CC BY allows others to share, adapt, and build on the analysis as long as they give appropriate credit, which fits an educational document better than a code-oriented license like MIT or Apache 2.0.

---

**Repository description (GitHub, max 350 characters):**
A critical review of Sharma et al. (2024)'s survey on DeepInsight and related tabular-to-image deep learning methods for genomic and multi-omics prediction, including a comparison against graph neural networks and a set of open research questions.

This repository is part of an ongoing effort to strengthen my understanding of computational biology and machine learning through structured literature reviews.

**Recommended GitHub topics/tags:**
`bioinformatics` `computational-biology` `deep-learning` `machine-learning` `genomics` `literature-review` `cnn` `multi-omics` `graph-neural-networks`


