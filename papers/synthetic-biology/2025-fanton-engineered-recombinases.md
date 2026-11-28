---
title: "Site-specific DNA insertion into the human genome with engineered recombinases"
authors:
  - Alison Fanton
  - Liam J. Bartie
  - Juliana Q. Martins
  - Vincent Q. Tran
  - Laine Goudy
  - Courtney Kernick
  - Matthew G. Durrant
  - Jingyi Wei
  - Zev Armour-Garb
  - April Pawluk
  - Silvana Konermann
  - Alexander Marson
  - Luke A. Gilbert
  - Theodore L. Roth
  - Patrick D. Hsu
year: 2025
journal: "Nature Biotechnology"
doi: "10.1038/s41587-025-02895-3"
paper_url: "https://doi.org/10.1038/s41587-025-02895-3"
date_read: "2026-11-28"
category: "synthetic-biology"
tags:
  - Synthetic Biology
  - Recombinase
  - Protein Engineering
  - Genome Editing
  - Machine Learning
difficulty: "Intermediate"
reading_status: "Completed"
---

# Site-specific DNA insertion into the human genome with engineered recombinases

## 1. Paper Information

| Field | Details |
| :--- | :--- |
| Title | Site-specific DNA insertion into the human genome with engineered recombinases |
| Authors | Alison Fanton, Liam J. Bartie, Juliana Q. Martins, Vincent Q. Tran, Laine Goudy, Courtney Kernick, Matthew G. Durrant, Jingyi Wei, Zev Armour-Garb, April Pawluk, Silvana Konermann, Alexander Marson, Luke A. Gilbert, Theodore L. Roth, Patrick D. Hsu |
| Year | 2025 |
| Journal | Nature Biotechnology |
| DOI | [10.1038/s41587-025-02895-3](https://doi.org/10.1038/s41587-025-02895-3) |
| Link | [https://doi.org/10.1038/s41587-025-02895-3](https://doi.org/10.1038/s41587-025-02895-3) |
| Category | [Synthetic Biology](README.md) |
| Reading status | `Completed` |
| Difficulty | Intermediate |
| Date read | 2026-11-28 |

Citation: Alison Fanton, Liam J. Bartie, Juliana Q. Martins, Vincent Q. Tran, Laine Goudy, Courtney Kernick, Matthew G. Durrant, Jingyi Wei, Zev Armour-Garb, April Pawluk, Silvana Konermann, Alexander Marson, Luke A. Gilbert, Theodore L. Roth, Patrick D. Hsu (2025). Site-specific DNA insertion into the human genome with engineered recombinases. *Nature Biotechnology*, 44(11):1880–1893. https://doi.org/10.1038/s41587-025-02895-3

## 2. Research Question

This study investigates how large serine recombinases (LSRs) can be engineered to improve efficiency and specificity of large DNA insertions into endogenous human genomic sites. The authors address three questions:

1. Can recombinases be engineered to improve both DNA integration efficiency and genome-wide specificity?
2. Can machine learning models predict the activities of recombinase variants carrying combinations of beneficial amino acid mutations?
3. Can dCas9 fusion and donor DNA optimisation further improve genome integration?

## 3. Background

Several concepts form the basis of this study:

- Large serine recombinases (LSRs), enzymes that catalyse site-specific DNA recombination between compatible attachment sites.
- Directed evolution, an experimental cycle of generating, selecting, and refining protein variants with desired properties.
- Integration efficiency, the proportion of target genomic sites that successfully receive a DNA insertion.
- Genome-wide specificity, the proportion of integration events occurring at the intended target site instead of off-target genomic locations.
- dCas9, a catalytically inactive Cas9 protein that retains RNA-guided DNA binding and can recruit fused proteins to chosen genomic regions.

## 4. Hypothesis and Objectives

### Objectives

- Start from the natural LSR Dn29 and engineer variants with higher integration efficiency and specificity at endogenous human sites.
- Combine directed evolution, computational modelling, dCas9-mediated recruitment, and donor attP sequence optimisation.
- Evaluate engineered variants across human cell systems using integration assays and genome-wide specificity measurements.

### Inferred Hypotheses

- Combining beneficial single mutations identified by directed evolution can predictably improve recombinase activity and specificity.
- Tethering engineered recombinases with dCas9 and tuning donor attP sequences will raise recombination efficiency beyond protein engineering alone.

## 5. Methodology

Using Dn29 as the starting recombinase, the researchers combined four strategies:

1. Directed evolution to generate and select Dn29 variants with improved integration efficiency or specificity.
2. Computational modelling using regression and gradient boosting models to predict the activity of higher-order recombinase mutants containing multiple mutations.
3. dCas9 fusion to improve recruitment of the recombinase to endogenous genomic targets and donor DNA.
4. Donor DNA optimisation by modifying attP sequences to improve recombination efficiency.

The engineered systems were benchmarked using experimental integration assays and genome-wide specificity profiling.

## 6. Results and Figures

Note: Detailed per-figure quantitative breakdowns can be added later after reviewing each figure panel individually. The main findings recorded in my notes are summarised below.

### Finding 1: Recombinase engineering improves integration performance

Combining beneficial mutations produced Dn29 variants with much higher integration efficiency and specificity than wild-type Dn29.

### Finding 2: Simple linear models predict combinatorial mutants well

Ridge regression performed strongly when predicting the activities of higher-order recombinase mutants, indicating that many beneficial mutations have roughly additive effects.

### Finding 3: dCas9-mediated recruitment increases genome integration

Fusing engineered recombinases to dCas9 improved recruitment to DNA targets and increased overall integration efficiency.

### Finding 4: Combining engineering strategies produces large gains

Together, these strategies reached up to 53% integration efficiency and 97% genome-wide specificity in the reported experimental settings, inserting DNA cargoes up to 12 kb.

## 7. Discussion and Interpretation

The results answer all three research questions: directed evolution paired with regularised linear modelling identifies high-performing mutation combinations. Adding dCas9 recruitment plus donor attP optimisation pushes integration efficiency and specificity much higher than wild-type Dn29. Combining protein engineering with targeting and donor design is more effective than relying on any single optimisation step alone.

## 8. Strengths and Limitations

### Strengths

1. Pairs wet-lab directed evolution with computational mutation prediction.
2. Measures both integration efficiency and genome-wide specificity rather than optimising one metric in isolation.
3. Uses interpretable machine learning models alongside structural context.
4. Demonstrates activity across multiple human cell systems.

### Limitations

1. Engineered systems still generate some unintended editing outcomes.
2. Higher integration efficiency can increase multiple-insertion events.
3. Adding a dCas9 fusion increases construct size and delivery complexity.
4. Most engineering experiments centred on a specific endogenous genomic target, so performance and safety across additional loci need further testing.

## 9. My Understanding

### 9.1. Why can improving recombinase efficiency reduce specificity?

Increasing enzyme activity often creates a trade-off with target specificity. Mutations that make a recombinase cut and recombine DNA more actively or strengthen electrostatic binding to the DNA backbone lower the barrier for recombination wherever the protein binds. That helps integration at the intended endogenous site (attH1) but can also push imperfect genomic pseudosites across the threshold needed for recombination. Improving efficiency alone can raise off-target insertions unless selection also filters for specificity.

### 9.2. How does directed evolution identify beneficial mutations?

Directed evolution tests many protein variants experimentally instead of guessing every useful change from first principles. Starting from wild-type Dn29, researchers introduce amino acid mutations to build a diverse variant library, then run a cellular selection or screening assay where active variants produce a measurable integration readout. Comparing variant frequencies before and after selection via sequencing shows which mutations are enriched, giving candidates that can be combined in later rounds.

### 9.3. Why did ridge regression perform so well compared with more complex models?

Two factors explain why ridge regression worked well here. First, experimental protein-engineering datasets are sparse compared with the huge number of possible multi-mutant combinations. Flexible nonlinear models can overfit noise and extrapolate poorly to higher-order mutants never tested during training, whereas ridge regression applies L2 regularisation to shrink noisy weights and stay stable. Second, many beneficial single mutations sit in separate protein regions and contribute roughly additively to activity. When the fitness landscape is mostly additive, a regularised linear model captures most of the signal without complex nonlinear architectures. This contrasts with DeepCpf1 (Paper 001), where a large dataset of about 15,000 short DNA sequences gave a convolutional neural network enough data to learn local sequence motifs.

### 9.4. How does dCas9 improve recombinase recruitment?

A freely diffusing recombinase must locate a single genomic attachment site across billions of base pairs while also bringing donor DNA into the same complex. Fusing Dn29 to catalytically inactive Cas9 (dCas9) uses guide RNAs to tether the recombinase beside the genomic target site and can help co-localise donor DNA. This raises the effective local concentration of the enzyme where recombination needs to happen without introducing double-strand breaks.

### 9.5. Why is the ability to insert large DNA cargoes important?

Standard CRISPR-Cas9 homology-directed repair relies on double-strand breaks, works poorly in non-dividing cells, and loses efficiency quickly as insert size grows past a few kilobases. Base editing and prime editing handle small edits well but cannot install whole genes. Inserting multi-kilobase cargoes (up to 12 kb in this study) without double-strand breaks makes it practical to deliver full-length therapeutic genes with native regulatory elements, engineered receptor constructs, or multi-gene synthetic circuits in a single integration step, including in non-dividing cell types.

## 10. Questions and Future Directions

### Investigating epistasis and model residuals in engineered recombinases

One question following Fanton et al. (2025) is where the additive assumption behind ridge regression breaks down. If a linear model predicts most higher-order Dn29 variants accurately, cases where ridge regression makes large errors likely involve two or more mutations interacting non-additively (epistasis), either reinforcing or cancelling each other.

A follow-up computational project using the published Dn29 mutant datasets could test four questions:

1. Which higher-order recombinase variants produce the largest residuals under ridge regression, and do nonlinear models (such as gradient boosted trees or a shallow neural network) predict those cases more accurately?
2. Can explainable machine learning tools, such as SHAP interaction values, pinpoint specific pairs of amino acid mutations that drive non-additive jumps or drops in integration efficiency and specificity?
3. When those interacting residue pairs are mapped onto 3D structures of Dn29 (from experimental structures or AlphaFold predictions), do epistatic pairs cluster close together in 3D space, such as within the catalytic domain or the DNA-binding interface?
4. Do mutations that improve efficiency while hurting specificity occupy distinct structural regions from mutations that improve both traits together?

Answering these questions could clarify when simple linear models suffice for recombinase engineering and when structural or nonlinear interaction terms are necessary. These are proposed follow-up directions, not findings demonstrated in Fanton et al. (2025).

## 11. Related Papers

- [Deep learning improves prediction of CRISPR–Cpf1 guide RNA activity](../bioinformatics/2018-kim-deep-learning-crispr-cpf1.md) (Kim et al., 2018): contrasts deep CNN prediction on large DNA sequence libraries with regularised linear modelling on combinatorial protein mutants.

## 12. Code and Reproduction

No companion scripts or notebooks linked yet.

[Back to Synthetic Biology](README.md) · [Papers archive](../README.md)
