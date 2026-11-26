---
title: "Deep learning improves prediction of CRISPR–Cpf1 guide RNA activity"
authors:
  - Hui Kwon Kim
  - Seonwoo Min
  - Myungjae Song
  - Soobin Jung
  - Jae Woo Choi
  - Younggwang Kim
  - Sangeun Lee
  - Sungroh Yoon
  - Hyongbum (Henry) Kim
year: 2018
journal: "Nature Biotechnology"
doi: "10.1038/nbt.4061"
paper_url: "https://doi.org/10.1038/nbt.4061"
date_read: "2026-11-27"
category: "bioinformatics"
tags:
  - CRISPR
  - Cas12a
  - Cpf1
  - Deep Learning
  - Genome Editing
difficulty: "Intermediate"
reading_status: "Completed"
---

# Deep learning improves prediction of CRISPR–Cpf1 guide RNA activity

## 1. Paper Information

| Field | Details |
| :--- | :--- |
| Title | Deep learning improves prediction of CRISPR–Cpf1 guide RNA activity |
| Authors | Hui Kwon Kim, Seonwoo Min, Myungjae Song, Soobin Jung, Jae Woo Choi, Younggwang Kim, Sangeun Lee, Sungroh Yoon, Hyongbum (Henry) Kim |
| Year | 2018 |
| Journal | Nature Biotechnology |
| DOI | [10.1038/nbt.4061](https://doi.org/10.1038/nbt.4061) |
| Link | [https://doi.org/10.1038/nbt.4061](https://doi.org/10.1038/nbt.4061) |
| Category | [Bioinformatics](README.md) |
| Reading status | `Completed` |
| Difficulty | Intermediate |
| Date read | 2026-11-27 |

Citation: Hui Kwon Kim, Seonwoo Min, Myungjae Song, Soobin Jung, Jae Woo Choi, Younggwang Kim, Sangeun Lee, Sungroh Yoon, Hyongbum (Henry) Kim (2018). Deep learning improves prediction of CRISPR–Cpf1 guide RNA activity. *Nature Biotechnology*, 36(3):239–241. https://doi.org/10.1038/nbt.4061

## 2. Research Question

This study investigates how deep learning can improve the prediction of CRISPR-Cas12a (previously known as Cpf1) guide RNA activity. Although Cas12a can be directed to specific DNA targets, different guide RNAs produce very different editing efficiencies, making candidate selection difficult before experiments begin.

To address this problem, the researchers built two prediction models, Seq-deepCpf1 and DeepCpf1, to answer two questions:

1. Can deep learning predict Cas12a guide RNA activity more accurately than conventional machine learning methods?
2. Does adding chromatin accessibility information improve predictions at endogenous genomic target sites?

## 3. Background

CRISPR-Cas12a is an RNA-guided endonuclease used for genome editing. It recognises specific DNA target sequences using CRISPR RNA (crRNA) together with a compatible protospacer adjacent motif (PAM). Successful target recognition does not guarantee high editing efficiency because factors such as target sequence composition and chromatin accessibility also affect Cas12a activity.

Key concepts used in the study include:

- Guide RNA activity, meaning how effectively a guide RNA directs Cas12a-mediated DNA cleavage and editing at a target site.
- Indel frequency, meaning the proportion of DNA sequences carrying insertions or deletions at a target site, used here to measure genome-editing activity.
- Chromatin accessibility, meaning how open a genomic region is to DNA-binding proteins and genome-editing complexes.
- Convolutional neural networks (CNNs), a deep learning architecture used here to learn sequence patterns associated with Cas12a editing activity.

## 4. Hypothesis and Objectives

### Objectives

- Generate large experimental indel-frequency datasets across thousands of AsCpf1 target sequences.
- Train and evaluate a sequence-only convolutional neural network (`Seq-deepCpf1`) and an extended model incorporating chromatin accessibility (`DeepCpf1`).
- Compare both deep learning models against conventional machine learning approaches.

### Inferred Hypotheses

- Sequence patterns learned directly by a CNN capture determinants of AsCpf1 cleavage activity better than hand-engineered features in conventional models.
- Chromatin accessibility provides additional biological context that improves prediction at endogenous genomic sites beyond DNA sequence alone.

## 5. Methodology

The researchers generated large experimental datasets covering thousands of Cas12a target sequences and measured their indel frequencies. About 15,000 target sequences were used to train a convolutional neural network to predict AsCpf1 activity. Two prediction models were built and compared against conventional machine learning baselines:

### Seq-deepCpf1

`Seq-deepCpf1` is a sequence-only model that takes target DNA sequence information as input and uses a convolutional neural network to identify sequence patterns linked to editing activity. It predicts Cas12a activity without requiring chromatin accessibility data.

### DeepCpf1

`DeepCpf1` extends the sequence-based CNN by adding chromatin accessibility information. This lets the model account for differences in local target-site accessibility when predicting editing efficiency at endogenous genomic loci.

## 6. Results and Figures

Note: Detailed per-figure quantitative readouts (such as exact correlation metrics per panel) are still to be added from the figures. The main findings reported in my notes are summarized below.

### Finding 1: Deep learning improves guide RNA activity prediction

`Seq-deepCpf1` outperformed the conventional machine learning methods tested in the study, indicating that convolutional neural networks can learn useful sequence-dependent patterns associated with Cas12a activity.

### Finding 2: Chromatin accessibility improves prediction accuracy

`DeepCpf1` achieved higher predictive accuracy when chromatin accessibility information was included, showing that genomic context matters alongside DNA sequence composition.

### Finding 3: Computational models support candidate prioritisation

Both models help researchers rank guide RNA candidates by predicted activity, reducing the number of guides that require experimental screening before wet-lab validation.

## 7. Discussion and Interpretation

These results address both research questions: a CNN trained on a large experimental dataset outperforms conventional machine learning models using sequence alone, and adding chromatin accessibility data further improves accuracy at endogenous sites. In practice, computational ranking helps prioritise promising guide RNAs, though predicted scores still need experimental validation rather than replacing bench testing.

## 8. Strengths and Limitations

### Strengths

1. The researchers generated measured editing activities from about 15,000 target sequences, giving the neural networks enough training data to generalize better than small-scale datasets.
2. Both deep learning models were benchmarked directly against conventional machine learning methods.
3. By incorporating chromatin accessibility, `DeepCpf1` accounts for chromatin state alongside DNA sequence composition.
4. Supplementary data and source code availability allow independent inspection and reuse of the models.

### Limitations

1. Both models were trained on AsCpf1; generalization to other Cas12a orthologs requires further validation.
2. Predictive performance can vary across species and cell types because underlying biological context differs.
3. `DeepCpf1` depends on chromatin accessibility data, which may be unavailable for some cell types or experimental systems.
4. Indel frequency captures on-target cleavage outcomes well, but does not measure off-target effects or precise editing efficiency.

## 9. My Understanding

### 9.1. Why can different guide RNAs have different editing efficiencies?

Different guide RNA sequences likely affect editing efficiency through several interacting mechanisms. One factor is crRNA stability, which influences how well the guide functions inside the Cas12a complex. Another is the stability of the RNA-DNA hybrid formed during target recognition. For instance, GC base pairs generally form stronger interactions than AT or AU base pairs, so GC content can influence interaction strength between the guide RNA and target DNA. Even so, higher GC content does not automatically improve editing, because excessive binding stability or unfavorable sequence motifs can interfere with guide folding, target recognition, or later cleavage steps.

### 9.2. What does the CNN learn from DNA sequences?

Rather than computing a single property like GC percentage, the CNN scans the target DNA sequence and learns combinations of nucleotide motifs associated with measured indel frequencies. Those learned patterns likely reflect physical properties relevant to Cas12a activity, even if the model itself does not explain the underlying biochemistry. Its main practical benefit is learning sequence-activity relationships directly from data without requiring manual feature engineering for every motif.

### 9.3. Why does chromatin accessibility improve prediction?

Cas12a must physically access target DNA inside the nucleus to cleave it. Even when a guide has a favourable sequence, editing efficiency can drop if the target lies inside closed, inaccessible chromatin. Open chromatin allows the Cas12a-crRNA complex to reach target DNA more easily, adding biological context that sequence alone cannot represent. At the same time, extra features only help predictions when the measurements are relevant and reliable for the target cell type.

### 9.4. How would I use these models in a genome-editing experiment?

If I designed a Cas12a experiment, I would start by scanning for candidate target sites next to a compatible PAM sequence. Next, I would run `Seq-deepCpf1` to score candidates from sequence alone, and switch to `DeepCpf1` if matched chromatin accessibility data were available for that cell type. I would prioritise top-scoring candidates instead of picking targets randomly, check off-target risk and experimental constraints, and validate the shortlisted guides in the lab.

## 10. Questions and Future Directions

### Understanding DeepCpf1 predictions using Explainable AI (XAI)

One open question is why deep learning models like `DeepCpf1` beat conventional machine learning models at predicting Cas12a guide RNA activity, and which biological features drive that gain. A follow-up bioinformatics project could apply Explainable AI (XAI) methods such as SHAP or Integrated Gradients to test five questions:

1. Which DNA sequence features contribute most strongly to `DeepCpf1` predictions?
2. How much do GC content, nucleotide positions, sequence motifs, and chromatin accessibility each contribute?
3. Does XAI uncover feature interactions that conventional machine learning models miss?
4. What accounts for the performance gap between deep learning and conventional approaches?
5. Do the features highlighted by XAI match known biochemical mechanisms of Cas12a activity?

Exploring these questions could make model predictions easier to interpret biologically and suggest mechanistic hypotheses around Cas12a targeting. These ideas are proposed follow-up directions rather than findings shown in Kim et al. (2018).

## 11. Related Papers

No related paper notes linked yet.

## 12. Code and Reproduction

No companion scripts or notebooks linked yet.

[Back to Bioinformatics](README.md) · [Papers archive](../README.md)
