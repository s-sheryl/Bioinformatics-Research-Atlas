# Detecting Resistance, Demonstrating Utility

Critical Analysis #05 in my bioinformatics research-reading portfolio.

**Author:** Sheryl S.

A critical analysis of Sauerborn et al. (2024), *“Detection of hidden antibiotic resistance through real-time genomics,”* published in *Nature Communications*.

---

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Topics Covered](#topics-covered)
- [Repository Structure](#repository-structure)
- [Highlights](#highlights)
- [Skills Demonstrated](#skills-demonstrated)
- [Key Takeaways](#key-takeaways)
- [Future Work](#future-work)
- [References](#references)
- [Acknowledgements](#acknowledgements)
- [License](#license)

---

## Overview

This repository contains my critical analysis of a study that used nanopore sequencing to investigate antibiotic resistance in two *Klebsiella pneumoniae* isolates from one patient.

I chose this paper because I wanted to understand how a resistance-gene detection becomes evidence that could help guide treatment. The study gave me a specific case to work through, including differences between routine susceptibility testing, carbapenemase detection, and sequencing.

The analysis looks at what the sequencing results support, how the samples were processed, and what would still need to be tested before making broader claims about clinical benefit. The sequencing was performed retrospectively and was not reported as guiding the patient’s treatment.

I did not run the authors’ code or reanalyse their sequencing data. This is a written critical analysis of the published study.

[Read the full analysis](CriticalAnalysis05_DetectingResistanceDemonstratingUtility.pdf)

---

## Objectives

- Explain the study’s design and sequencing workflow.
- Compare what the routine diagnostic tests and genomic methods measured.
- Examine the evidence for low-abundance resistance-gene detection.
- Separate the reported findings from claims that require further validation.
- Identify possible follow-up analyses and experiments.

---

## Topics Covered

- Nanopore sequencing and read-level resistance-gene detection
- The EPI2ME antimicrobial resistance workflow and CARD
- Genome assembly and plasmid analysis
- Phenotypic susceptibility testing and carbapenemase assays
- The distinction between blaKPC-14-labelled detections and KPC-159 identification
- Detection counts, plasmid copy-number estimates, and normalised gene abundance
- Colony sampling and sequencing turnaround time
- Reproducibility and access to data and code
- Limits of a retrospective, single-patient study

---

## Repository Structure

```text
.
├── README.md
└── CriticalAnalysis05_DetectingResistanceDemonstratingUtility.pdf
```

---

## Highlights

The analysis includes diagrams separating the clinical timeline from the retrospective sequencing work, along with tables comparing the diagnostic methods and explaining the reported measurements.

One point I focus on is the difference between the two isolates. Sequencing detected a low-abundance blaKPC-14-labelled signal in the pre-treatment isolate despite its reported ceftazidime–avibactam susceptibility. In the post-treatment isolate, routine testing detected resistance to this drug combination, but the carbapenemase assay returned a negative result.

I also discuss why the separate 8-hour sequencing run provided additional support without establishing a validated clinical reporting threshold.

---

## Skills Demonstrated

- Critical reading of research papers
- Interpretation of bioinformatics methods
- Evaluation of study design and diagnostic comparisons
- Scientific writing
- Communication through diagrams and tables
- Planning follow-up research

These reflect literature-analysis skills practised in this write-up, rather than hands-on implementation of the sequencing pipeline.

---

## Key Takeaways

- Detecting a resistance-associated gene and showing that its detection improves treatment are separate steps.
- A susceptibility test, a carbapenemase assay, and a sequencing workflow answer different questions.
- The initial workflow labelled the signal as blaKPC-14. Identification of KPC-159 required separate reference-laboratory sequencing of the post-treatment isolate.
- Read-level detections, plasmid copy-number estimates, and normalised gene abundance should not be treated as interchangeable measurements.
- The study supports further investigation of genomic resistance detection, but one retrospective case cannot establish general diagnostic superiority or improved patient outcomes.

---

## Future Work

Possible extensions discussed in the analysis include:

- Reanalysing reads over time to examine how support for a resistance-gene detection accumulates.
- Checking sequence positions that distinguish KPC-2, KPC-14, and KPC-159.
- Testing low-abundance detection using controlled mixtures while accounting for gene copy number.
- Comparing sequencing and routine diagnostics prospectively, with suitable reference tests and clearly defined reporting criteria.

These are proposed directions. I have not carried out these analyses or experiments.

---

## References

Sauerborn, E., et al. (2024). Detection of hidden antibiotic resistance through real-time genomics. *Nature Communications*, **15**, 5494.

https://doi.org/10.1038/s41467-024-49851-4

Additional references are included in the analysis PDF.

---

## Acknowledgements

This is an independent student critical analysis written for my research-reading portfolio. Credit for the original study, data, and methods belongs to Sauerborn and colleagues.

This analysis is not affiliated with or endorsed by the original authors or the journal.

---

## License

My writing and original diagrams are shared under **CC BY 4.0**. This does not cover the original article or other third-party material.
