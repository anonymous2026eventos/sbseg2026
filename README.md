# SBSeg2026

**Supplementary Materials**

This repository contains the supplementary materials, datasets, source code, and experimental results associated with the paper:

**Network Flow Integration to Improve Generalization of Machine Learning-Based IDS.**

---

## Authors

* Kelson Carvalho Santos
* Rodrigo Sanches Miani

---

## Abstract

The growth of cyber threats and the evolution of attacks highlight the need for more robust machine learning-based IDS capable of operating in heterogeneous, dynamic network environments. Although some approaches presented in the literature improve the performance of these systems, their generalization capability remains limited in multi-domain data scenarios. This paper proposes a network flow integration method across multiple datasets to increase the diversity of training instances and improve model generalization capability. The results indicate better adaptation of intrusion detection models across different data domains and reduced performance degradation, despite trade-offs between attack detection and false alarms.

## Repository Structure

```text
.
├── datasets/
│   ├── unsw-nb15/
│   ├── cic-ids2017/
│   └── cic-ids2018/
│
├── results/
│   ├── figures/
│   ├── tables/
│
├── notebooks/
│
└── README.md


```

## Datasets

The experiments were conducted using the following public datasets:

* [GenIDS-UNSW15](https://drive.google.com/drive/folders/1ASpkvg6UUJ2HWq2Xn5goJPXmVEWBHIeR?usp=sharing)
* [GenIDS-CIC17](https://drive.google.com/drive/folders/1iWY9djW9Y5KBROlafgLgUx05cKipzW8e?usp=drive_link)
* [GenIDS-CIC18](https://drive.google.com/drive/folders/1uuHYlvi0TUSjUEHK67NKnX00eA166D7J?usp=sharing)

Due to licensing and distribution restrictions, the original datasets are not redistributed in this repository and should be obtained from their respective official sources.

To support reproducibility and facilitate IDS generalization research, this repository provides the processed versions of these datasets. The datasets were generated from the original network traffic captures and standardized using the NFStream tool, resulting in a common feature space that enables cross-dataset generalization experiments and comparative evaluations.

The features extracted by NFStream were organized according to the categories originally defined by the framework, as presented in Table [Features Extracted with NFStream from the PCAP Files of the Datasets](tables/features.pdf). These categories group features that describe different characteristics of network flows, including basic identification and traffic volume information (Core Features), statistical metrics derived from packets observed throughout the flow (Post-Mortem Statistics), and application identification features (Ground Truth).
