# SBSeg2026

**Supplementary Materials**

This repository contains the supplementary materials, datasets, source code, and experimental results associated with the paper:

**Network Flow Integration to Improve Generalization of Machine Learning-Based IDS.**

---

## Authors

* author1
* author2

---

## Abstract

The growth of cyber threats and the evolution of attacks highlight the need for more robust machine learning-based IDS capable of operating in heterogeneous, dynamic network environments. Although some approaches presented in the literature improve the performance of these systems, their generalization capability remains limited in multi-domain data scenarios. This paper proposes a network flow integration method across multiple datasets to increase the diversity of training instances and improve model generalization capability. The results indicate better adaptation of intrusion detection models across different data domains and reduced performance degradation, despite trade-offs between attack detection and false alarms.

## Repository Structure

```text
.
├── datasets/
│   ├── GenIDS-CIC17/
│                   └── GenIDS-CIC17.csv
│                   └── GenIDS-CIC17_description.txt
│   ├── GenIDS-CIC18/
│                   └── GenIDS-CIC18.csv
│                   └── GenIDS-CIC18_description.txt
│   ├── GenIDS-UNSW15/
│                   └── GenIDS-UNSW15.csv
│                   └── GenIDS-UNSW15_description.txt
├── tables/
│   └── features.pdf
├── notebooks/
│   └── notebook_1.ipynb
│   └── notebook_2.ipynb
│   └── notebook_3.ipynb
│   └── notebook_4.ipynb
│   └── notebook_5.ipynb
│   └── notebook_6.ipynb
│   └── notebook_7.ipynb
│   └── notebook_8.ipynb
│   └── notebook_9.ipynb
└── README.md
```
---

## Datasets

The experiments were conducted using the following public datasets:

* [GenIDS-UNSW15](https://drive.google.com/drive/folders/1ASpkvg6UUJ2HWq2Xn5goJPXmVEWBHIeR?usp=sharing)
* [GenIDS-CIC17](https://drive.google.com/drive/folders/1iWY9djW9Y5KBROlafgLgUx05cKipzW8e?usp=drive_link)
* [GenIDS-CIC18](https://drive.google.com/drive/folders/1uuHYlvi0TUSjUEHK67NKnX00eA166D7J?usp=sharing)

Due to licensing and distribution restrictions, the original datasets are not redistributed in this repository and should be obtained from their respective official sources.

To support reproducibility and facilitate IDS generalization research, this repository provides the processed versions of these datasets. The datasets were generated from the original network traffic captures and standardized using the NFStream tool, resulting in a common feature space that enables cross-dataset generalization experiments and comparative evaluations.

The features extracted by NFStream were organized according to the categories originally defined by the framework, as presented in Table [Features Extracted with NFStream from the PCAP Files of the Datasets](tables/features.pdf). These categories group features that describe different characteristics of network flows, including basic identification and traffic volume information (Core Features), statistical metrics derived from packets observed throughout the flow (Post-Mortem Statistics), and application identification features (Ground Truth).

## Notebooks (Code)

The experiments were conducted by integrating network flows from the source dataset into the destination dataset before model training. To prevent data leakage, all integrated flows were removed from the source dataset prior to testing. Additionally, an equivalent number of flows were removed from the destination dataset to maintain a consistent dataset size and preserve the original class proportions.

Flow integration was evaluated using different integration rates (20%, 40%, 60%, and 80%) and three integration strategies:

* **Benign Flow Integration:** Only benign flows were integrated.
* **(D)DoS Flow Integration:** Only malicious flows of the (D)DoS class were integrated, across DoS and DDoS types.
* **Mixed Flow Integration:** Both benign and (D)DoS flows were integrated.

The following notebooks are available:

**Baseline Flow Integration**

* [Notebook 1](notebooks/notebook_1.ipynb): Integration of benign flows.
* [Notebook 2](notebooks/notebook_2.ipynb): Integration of malicious (D)DoS flows.
* [Notebook 3](notebooks/notebook_3.ipynb): Integration of both benign and malicious (D)DoS flows.

**Flow Integration with PCA**

Principal Component Analysis (PCA) is applied before the flow integration process.

* [Notebook 4](notebooks/notebook_4.ipynb): PCA + benign flow integration.
* [Notebook 5](notebooks/notebook_5.ipynb): PCA + malicious (D)DoS flow integration.
* [Notebook 6](notebooks/notebook_6.ipynb): PCA + mixed flow integration.

**Flow Integration with Chi-Square Feature Selection**

Chi-Square feature selection is applied before the flow integration process.

* [Notebook 7](notebooks/notebook_7.ipynb): Chi-Square + benign flow integration.
* [Notebook 8](notebooks/notebook_8.ipynb): Chi-Square + malicious (D)DoS flow integration.
* [Notebook 9](notebooks/notebook_9.ipynb): Chi-Square + mixed flow integration.

These notebooks support the experiments reported in the paper and enable reproduction of the proposed flow integration methodology across different preprocessing and feature-engineering scenarios.
