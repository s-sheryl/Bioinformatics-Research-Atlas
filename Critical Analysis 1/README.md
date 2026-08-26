# Eight Clusters, One Discrete Assignment

### A critical analysis of the genetic architecture of type 2 diabetes across global populations

## Overview

This repository contains my independent critical analysis of Suzuki et al.'s large multi-ancestry study of the genetic architecture of type 2 diabetes (T2D).

The original study brings together genome-wide association data across multiple ancestry groups to investigate the genetic heterogeneity of T2D. Among its major analyses, T2D-associated variants were grouped according to their cardiometabolic association profiles, producing eight clusters that were subsequently examined using regulatory annotations, ancestry-related heterogeneity, and cluster-partitioned polygenic scores.

My analysis focuses less on whether these clusters are biologically plausible and more on a methodological question: **how much biological interpretation should be placed on a discrete clustering solution when the underlying genetic architecture may be overlapping, pleiotropic, or continuous?**

Rather than attempting to reproduce the original study, I examine the assumptions connecting statistical clustering to biological interpretation and identify analyses that could further test the stability of those conclusions.

## Original Study

Suzuki et al. conducted a large multi-ancestry genetic analysis of T2D using data from several global ancestry groups.

One component of the study examined the cardiometabolic association profiles of T2D index variants. Missing phenotype associations were handled using ClustImpute, and the variants were assigned to clusters using k-means clustering. The selected number of clusters was determined using a majority rule across 27 cluster-performance indices implemented through NbClust.

The resulting clusters were investigated further through analyses including cell-type-specific open-chromatin enrichment, ancestry-correlated heterogeneity, and cluster-specific components of partitioned polygenic scores.

These analyses provide evidence that T2D genetic risk is heterogeneous and that different groups of risk variants are associated with different biological and phenotypic patterns.

## Focus of the Critical Analysis

The central issue I examine is the use of **hard clustering**, where each index variant is assigned to exactly one cluster.

This produces an interpretable representation of genetic heterogeneity, but the discreteness of the resulting clusters should not automatically be interpreted as evidence that the underlying biology is equally discrete.

This matters because genetic variants can influence multiple traits and biological pathways. A variant with an intermediate association profile may resemble more than one cluster even though the clustering algorithm ultimately assigns it to only one.

The original study acknowledges this limitation of hard clustering and evaluates cluster disparity. My analysis asks a narrower question: **how much uncertainty exists at the level of individual variant assignments?**

A cluster can be coherent overall while still containing variants whose membership is ambiguous.

I therefore distinguish between two related but different forms of evidence:

- evidence that the resulting clusters have biological coherence; and
- evidence that individual variants are stably assigned to those particular clusters.

The downstream regulatory and phenotypic analyses provide meaningful evidence for the first. They do not necessarily quantify the second.

## Missing Data and ClustImpute

A related issue concerns missing cardiometabolic phenotype associations.

The study uses ClustImpute, which iteratively combines missing-value imputation with clustering. Missing values are initially sampled from phenotype distributions and are subsequently updated in relation to the developing cluster structure.

This is a reasonable approach to a difficult missing-data problem, but it also creates an interaction between imputation and cluster assignment.

My analysis does not claim that this procedure biased the resulting clusters. Instead, I treat it as a testable methodological question: **are cluster assignments equally stable for variants with relatively complete phenotype profiles and variants whose profiles depend more heavily on imputation?**

Sensitivity analyses across different imputation realizations could help answer that question.

## From Regulatory Enrichment to Mechanism

The original study integrates the genetic clusters with cell-type-specific open-chromatin data, providing evidence that different clusters are enriched in regulatory regions active in different cell types.

I regard this as important biological support for the clustering framework.

At the same time, regulatory enrichment and demonstrated molecular mechanism are not equivalent.

Open-chromatin enrichment can strengthen the biological plausibility of a cluster and suggest relevant cell types, but it does not by itself establish the effector gene, direction of regulation, causal molecular pathway, or downstream phenotypic consequence.

This distinction is important when moving from statistical association to mechanistic interpretation.

## Partitioned Polygenic Scores

The study also examines cluster-specific components of partitioned polygenic scores and their associations with T2D-related outcomes.

An important distinction in my analysis is between **detecting additional association structure** and **demonstrating improved clinical prediction**.

A cluster-specific score can show a significant association with an outcome after adjustment for an overall T2D polygenic score without necessarily being a better clinical predictor.

Demonstrating predictive improvement would require direct evaluation using appropriate measures of discrimination, calibration, reclassification, or other predictive-performance metrics.

The partitioned-score findings are therefore informative about genetic and phenotypic heterogeneity, but they should not automatically be interpreted as evidence of superior clinical prediction.

## Ancestry and Generalizability

One of the major strengths of the original study is its multi-ancestry design. It substantially expands the ancestral diversity represented in T2D genetic research and allows the authors to investigate ancestry-correlated heterogeneity in genetic effects.

However, multi-ancestry does not mean equally representative.

The contribution of different ancestry groups remains uneven, which affects how confidently particular findings can be generalized across populations. My analysis therefore treats ancestry diversity as both an important strength of the study and an area where continued expansion of genetic datasets remains necessary.

## Questions Raised

The analysis ultimately leaves me with several questions that could be tested computationally:

1. How stable are individual variant-to-cluster assignments under resampling?
2. How often would the same number of clusters be recovered across alternative samples or imputation realizations?
3. How large is the difference between a variant's distance to its assigned centroid and its second-closest centroid?
4. Are variants with more missing phenotype information less stable in their cluster assignments?
5. Would soft or probabilistic clustering reveal variants with substantial membership in more than one biological profile?
6. Would the interpretation of downstream regulatory or phenotypic analyses change under alternative plausible cluster assignments?
7. Do cluster-partitioned polygenic scores improve predictive performance when evaluated directly against the overall score?

These are not demonstrated weaknesses of the original study. They are sensitivity analyses that could help determine how strongly the biological interpretation depends on the chosen statistical representation.

## Proposed Extensions

A useful extension of this work would be to quantify uncertainty in the clustering solution rather than treating cluster membership as entirely categorical.

Possible approaches discussed in the critical analysis include:

- bootstrap or resampling-based cluster stability analysis;
- comparison of first- and second-nearest cluster centroids;
- soft or probabilistic clustering;
- sensitivity analysis across alternative missing-data treatments;
- examination of assignment stability as a function of phenotype missingness; and
- direct comparison of predictive performance between overall and partitioned polygenic scores.

These analyses were **proposed as extensions and were not performed as part of this critical analysis**.

## What I Took From This Paper

The main lesson I took from this study is that biological interpretation depends not only on the data being analysed, but also on the statistical representation imposed on those data.

A clustering algorithm can provide a useful model of biological heterogeneity without establishing that biology itself is divided into the same discrete categories. Likewise, regulatory enrichment can support biological plausibility without proving mechanism, and statistically significant polygenic-score associations do not by themselves establish clinical predictive value.

For me, critically reading a computational genetics study therefore means asking not only whether a result is statistically convincing, but also **what level of biological inference the analysis actually supports**.

## Repository Contents

| File | Description |
| --- | --- |
| `critical-analysis.pdf` | Independent critical analysis of the Suzuki et al. study |
| `README.md` | Overview of the analysis, central critique, and proposed extensions |


## Scope

This document is an independent undergraduate critical analysis prepared as part of my development in genetics, genomics, and bioinformatics.

It is not a reproduction of the original GWAS, an original experimental study, or a peer-reviewed publication. The proposed sensitivity analyses discussed above are suggestions for further investigation rather than analyses performed in this work.

## Original Publication

Suzuki, K. et al. *Genetic drivers of heterogeneity in type 2 diabetes pathophysiology.* **Nature** (2024).


## Disclaimer

This analysis is independent of the original authors and their institutions and is not affiliated with or endorsed by the journal in which the original study was published.
