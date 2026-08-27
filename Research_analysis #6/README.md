# Research Paper Analysis #06 — Omics in Diabetes Epidemiology

**What a Review Article Taught Me About Study Design**

It's easy to think of an omics study as starting when someone opens a dataset and runs a model. This paper pushed that starting point much further back for me. By the time an analysis begins, decisions about who was recruited, what was collected, how it was stored, and which layers were measured may have already set limits on what that analysis can actually answer.

## The paper

Yu, G., Tam, H. C. H., Huang, C., Shi, M., Lim, C. K. P., Chan, J. C. N., & Ma, R. C. W. (2024). Lessons and applications of omics research in diabetes epidemiology. *Current Diabetes Reports*, 24, 27–44. https://doi.org/10.1007/s11892-024-01533-7

This is a review article, not original research. It walks through genetics and GWAS, polygenic risk scores, epigenetics, proteomics, metabolomics, and multi-omics integration, drawing heavily on the authors' own cohorts — the Hong Kong Diabetes Register and Hong Kong Diabetes Biobank — as working examples of what putting omics into an epidemiological study actually looks like.

## Why I picked this paper

Most of what I'd been thinking about before this was downstream — how data gets represented, modeled, clustered, interpreted. This paper is about the other end of the pipeline entirely. The question I kept asking myself while reading it was simpler than I expected: what has to be true about a dataset before any of that downstream work is even possible?

## The part I didn't expect to care about

Table 1 in the original review is not a results table. It's a planning table — sample type needed, rough sample size, and a column of "special considerations" for each kind of biomarker. Two examples stuck with me: methylation profiling needs blood cell-type composition accounted for, or the signal gets confounded, and miRNA profiling can be wrecked by haemolysis or by using the wrong collection tube (lithium heparin, specifically). Neither of those facts is exciting on its own. What got me was the implication — a sophisticated downstream analysis can be constrained or ruined by a decision made in a phlebotomy room, long before anyone opens a dataset. That's probably the most reusable part of the whole paper.

## What each omics layer is actually adding

| Layer | Example from the review | What it contributes |
|---|---|---|
| Genetics / GWAS | 611 loci, 1,289 signals from a 2.5-million-person multi-ancestry meta-analysis | Maps the common-variant landscape of T2D risk |
| Polygenic risk scores | Trans-ancestry T2D PRS showing a 2.5–4.5-fold risk gradient across populations | Compresses genetic signal into an individual-level number |
| Epigenetics | A methylation site in TXNIP flagged in one cohort, then independently reappearing in a T1D complications study | Links environmental exposure to gene regulation |
| Proteomics | Mendelian randomization identifying SIRPG, IL27-EBI3, and CTRB1 as candidate T1D drug targets | Separates causal proteins from ones that are just correlated |
| Metabolomics | 163 metabolites associated with T2D risk in the China Kadoorie Biobank | Captures dynamic, diet- and microbiome-linked signal |

Each row is really asking a different kind of question about the disease, not just measuring a different molecule.

## The result that changed one of my assumptions

I'd absorbed, without really examining it, the intuitive story that rare variants probably account for a lot of the "missing heritability" in complex diseases like T2D — it's the logical place to look once common variants have been mostly accounted for. The review cites an exome-sequencing study of over 20,000 T2D cases where the strongest rare-variant gene-level signals explained only about 25% of the heritability that the strongest common-variant signals already captured. That's not "rare variants don't matter." It's a reminder that a biologically intuitive explanation still has to be measured before I treat it as settled, and in this case the measurement came back lower than the intuition predicted.

## Why Mendelian randomization kept standing out

Across the proteomics, methylation, and metabolomics sections, the same pattern kept showing up: an omics assay generates an association, and Mendelian randomization is what the authors reach for to ask whether that association looks more like causation than coincidence. I didn't consciously notice this the first couple of times — it only became obvious once I saw it recur independently in three unrelated sections.

That said, MR isn't proof of causality by itself. It depends on assumptions — valid instruments, no problematic horizontal pleiotropy — that have to hold for the inference to be trustworthy. The review leans on MR-supported findings as stronger evidence pretty consistently, but it doesn't spend much time on those underlying assumptions. That's a real strength of the paper's approach sitting right next to a real gap in how it's discussed.

## PRS: useful, but not by itself

A PRS takes thousands of individually tiny genetic effects and compresses them into one number per person. What I hadn't thought about enough is that the review is fairly direct about PRS often not being clinically useful on its own — it becomes actionable when combined with things like BMI, autoantibody status (GADA), or fasting glucose. That reframes a PRS less as a standalone answer and more as one input feeding a larger risk model.

## One risk score, or several biological components?

A conventional PRS is a single weighted sum. A different approach — the "palette model" from Udler and colleagues, discussed in the review — instead partitions genetic effects into several clusters, each tied to a different metabolic or clinical pattern (beta-cell function, insulin resistance, and so on).

I find the idea genuinely appealing: it gives a single risk number some biological structure instead of collapsing everything into one undifferentiated score. But I'm skeptical of treating the resulting clusters as fixed biological subtypes just yet. The five-cluster version was later extended into a ten-cluster version, and the clusters weren't identical between them. That tells me the boundaries are, at least partly, a function of how the clustering was run — the discovery dataset, the trait set, the procedure — rather than a stable biological fact waiting to be found. That doesn't make the approach invalid. It means the clusters are a candidate structure whose stability still needs to be demonstrated, not an established typology.

## The test I'd want to see

Run the same clustering procedure independently on a non-European T2D GWAS and check whether roughly the same cluster structure falls out. If it does, that's a real argument the clusters reflect reproducible biology rather than an artifact of one dataset. If the structure changes substantially, that points toward ancestry, trait composition, or the clustering procedure itself shaping the boundaries. I haven't done this — it's the analysis I'd want to see someone run.

## Ancestry still matters

Most PRS development the review discusses is still weighted toward European-ancestry discovery data, and transferability across ancestry groups comes up repeatedly as an acknowledged limitation, though never quantified in one consolidated place. The clustering framework raises the same question in a slightly different form, since the discovery data behind the palette model were also largely European. This isn't a claim that the review ignores diversity — it draws substantially on Hong Kong cohorts throughout. It's specifically about how genetic prediction and clustering generalize once you move outside the population they were built on.

## Why measuring everything in the same people matters

Some of the review's examples come from separate cohorts measuring separate omics layers and comparing results afterward. Others come from measuring multiple layers — genome, epigenome, proteome, metabolome — in the same individuals, which allows direct cross-layer analyses like pQTL or meQTL relationships. That's a real advantage for biological interpretation. But it isn't free: integrated multi-omics needs far more storage, data linkage, computational infrastructure, and coordination across people with different kinds of expertise. Neither design is automatically the better choice; they trade off differently.

## Where I became more critical

The review draws heavily on the authors' own cohorts, HKDR and HKDB — genuinely useful for showing what running an omics-informed epidemiology study actually looks like in practice, but it does mean the illustrative examples skew toward one group's work rather than the field broadly. It also covers five distinct omics layers in one document, which is good for orientation but means no single layer gets a deep methodological treatment. It's not a systematic review either — there's no stated process for how the cited studies were selected, which matters if you're tempted to read it as a comprehensive map of the field rather than a curated tour. And MR assumptions, as above, get used consistently but discussed thinly relative to how much interpretive weight they're carrying.

## What I took away from it

- An intuitive biological explanation still needs to be measured, not assumed.
- A PRS is usually one input into a larger risk model, not a standalone answer.
- Association and causation need to stay separate, even when MR is doing good work to bridge them.
- Omics data quality is partly decided at the point of sample collection and biobanking, well before any model gets trained.
- A statistical cluster is not automatically a biological subtype until its stability has been shown across procedures and populations.

## Questions I'd follow up

These are open questions from my reading, not analyses I've run:

1. Would the five- or ten-cluster T2D genetic structure reappear if the clustering were rerun independently on an East Asian or African-ancestry GWAS?
2. As exome-sequencing studies scale toward the million-sample range the authors mention, will the ~25% rare-variant heritability figure move much, or does that number reflect something closer to a ceiling?
3. When multiple omics layers are measured in the same individuals rather than compiled across separate cohorts, how much does that actually change the biological conclusions, versus just making the analysis more convenient to run?

## What I'd actually like to try next

The direction I keep coming back to is picking one biomarker from the proteomics section and trying to reproduce the logic of its Mendelian randomization analysis using publicly available GWAS summary statistics — not to challenge the review's finding, just to get a concrete sense of how that kind of causal check actually works instead of only reading about it secondhand.

When I read computational papers, I naturally pay attention to what happens downstream — how data gets represented, clustered, modeled, validated. This paper made me look further upstream instead. By the time a dataset reaches the modeling stage, decisions about who was sampled, what was collected, how it was stored, and which measurements were taken may have already constrained the questions that data can answer. That's the part of this review I expect to keep thinking about.


The PDF contains the complete omics-layer analysis, methodological comparisons, critical evaluation, proposed research extensions, and full references.

## Reference

Yu, G., Tam, H. C. H., Huang, C., Shi, M., Lim, C. K. P., Chan, J. C. N., & Ma, R. C. W. (2024). Lessons and applications of omics research in diabetes epidemiology. *Current Diabetes Reports*, 24, 27–44. https://doi.org/10.1007/s11892-024-01533-7

---

This is part of my Research Portfolio Series and represents my independent critical reading of the review above. The original review and the studies it discusses belong to their respective authors; the interpretation, comparisons, and commentary here are my own.
