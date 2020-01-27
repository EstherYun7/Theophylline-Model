# Building and Evaluation of a PBPK Model for Theophylline in Adults



| Version     | 0.1       |
| ----------- | --------- |
| OSP Version | 8.0       |
| Author      | flyhighyj |


# Table of Contents
  * [1 Introduction](#1-introduction)
  * [2 Methods](#2-methods)
    * [2.1 Modeling Strategy](#21-modeling-strategy)
    * [2.2 Data](#22-data)
    * [2.3 Model Parameters and Assumptions](#23-model-parameters-and-assumptions)
  * [3 Results and Discussion](#3-results-and-discussion)
    * [3.1 Final input parameters](#31-final-input-parameters)
    * [3.2 Diagnostics Plots](#32-diagnostics-plots)
    * [3.3: Concentration-Time Profiles](#33-concentration-time-profiles)
      * [3.3.1 Model Building](#331-model-building)
      * [3.3.2 Model Verification](#332-model-verification)
  * [4 Conclusion](#4-conclusion)
  * [5 References](#5-references)
# 1 Introduction
Theophylline is used for therapy for respiratory diseases. It is metabolized by both CYP1A2 and CYP2E1. The fraction excreted unchanged in urine is 25%. 


# 2 Methods


## 2.1 Modeling Strategy
The general concept of building a PBPK model has previously been described by Kuepfer et al. ([Kuepfer 2016](# 5 References)) Regarding the relevant anthropometric (height, weight) and physiological parameters (e.g. blood flows, organ volumes, binding protein concentrations, hematocrit, cardiac output) in adults was gathered from the literature and has been previously published ([PK-Sim Ontogeny Database Version 7.3](# References)). The information was incorporated into PK-Sim® and was used as default values for the simulations in adults.

The  applied activity and variability of plasma proteins and active processes that are integrated into PK-Sim® are described in the publicly available PK-Sim® Ontogeny Database Version 7.3 ([Schlender 2016](# 5 References)) or otherwise referenced for the specific process.

First, a base mean model was built using literature data including selected intravenous single dose studies with Ondansetron to find an appropriate structure to describe the pharmacokinetics in plasma. The mean PBPK model was developed using a typical European individual.



For clearance, first order process was assumed. Specific clearance and lipophilicity were optimized based on the observed plasma concentration vs. time coefficients using the Parameter Identification module provided in PK-Sim®. 

The model was then verified by simulating:

- plasma concentration vs. time profile 

Details about input data (physicochemical, *in vitro* and clinical) can be found in  [Section 2.2](#2.2	Data).

Details about the structural model and its parameters can be found in  [Section 2.3](#2.3 Model Parameters and Assumptions).

Details about model development was described in Yun and Edginton (2019). 




## 2.2 Data
### 2.2.1	In vitro / physico-chemical Data

A literature search was performed to collect available information on physiochemical properties of dapagliflozin. The obtained information from literature is summarized in the table below. 

| **Parameter**   | **Unit**    | **Value** | Source             | **Description**                                 |
| :-------------- | ----------- | --------- | ------------------ | ----------------------------------------------- |
| MW              | g/mol       | 293.37    | Drugbank [DB00227] | Molecular weight                                |
| pK<sub>a</sub>  |             | 8.81      | Drugbank [DB00227] | Acid dissociation constant                      |
| Solubility (pH) | mg/L (pH 7) | 7360      | Drugbank [DB00227] | Aqueous Solubility, FaSSIF, ...                 |
| logP            |             | 1.23      | Optimized          | Partition coefficient between octanol and water |
| fup             | %           | 40        | (Simons 1979)      | Fraction unbound in plasma                      |
|                 |             |           |                    |                                                 |
| ...             |             |           |                    | ....                                            |

### 2.2.2	Clinical Data

A literature search was performed to collect available clinical data on dapagliflozin in healthy adults.

#### 2.2.2.1	Model Building

The following studies were used for model building (training data):

| Publication     | Arm / Treatment / Information used for model building        |
| :-------------- | :----------------------------------------------------------- |
| Steinijans 1987 | Healthy Subjects with a single intravenous dose of 506 mg infused for 8 hours |
| Gisclon 1997    | Healthy Subjects with a single intravenous dose of 4.5 mg/kg infused for 30 minutes |

#### 2.2.2.2	Model Verification

The following studies were used for model verification:

| Publication | Arm / Treatment / Information used for model building |
| :---------- | :---------------------------------------------------- |
| ...         | ...                                                   |
| ...         | ...                                                   |


## 2.3 Model Parameters and Assumptions
### 2.3.1	Absorption

Not applicable as an intravenous route was used.

### 2.3.2	Distribution

...

After testing the available organ-plasma partition coefficient and cell permeability calculation methods built in PK-Sim, observed clinical data was best described by choosing the partition coefficient calculation by `Rodgers and Rowland` and cellular permeability calculation by `PK-Sim Standard`. 

...

### 2.3.3	Metabolism and Elimination

Ondansetron undergoes primarily hepatic metabolism specifically CYP 3A4 and CYP 1A2. The fraction excreted unchanged in urine is 5%. 

### 2.3.4	Automated Parameter Identification


# 3 Results and Discussion
The PBPK model for Theophylline was developed with clinical pharmacokinetic data.

The next sections show:

1. the final model parameters for the building blocks: [Section 3.1](#3.1 Final Input Parameters).
2. the overall goodness of fit: [Section 3.2](#3.2 3.2 Diagnostics Plots).
3. simulated vs. observed concentration-time profiles for the clinical studies used for model building: [Section 3.3](#3.3 Concentration-Time Profiles).


## 3.1 Final input parameters
The compound parameter values of the final PBPK model are illustrated below.




# Compound: Theophylline

## Parameters

Name                                       | Value          | Value Origin | Alternative | Default |
------------------------------------------ | -------------- | ------------:| ----------- | ------- |
Solubility at reference pH                 | 7360 mg/l      |              | Measurement | True    |
Reference pH                               | 7              |              | Measurement | True    |
Lipophilicity                              | 1.23 Log Units |              | Measurement | True    |
Fraction unbound (plasma, reference value) | 0.4            |              | Measurement | True    |
Is small molecule                          | Yes            |              |             |         |
Molecular weight                           | 180.16 g/mol   |              |             |         |
Plasma protein binding partner             | Albumin        |              |             |         |
## Calculation methods

Name                    | Value           |
----------------------- | --------------- |
Partition coefficients  | PK-Sim Standard |
Cellular permeabilities | PK-Sim Standard |
## Processes

### Systemic Process: Glomerular Filtration-GFR

Species: Human
#### Parameters

Name         | Value | Value Origin |
------------ | -----:| ------------: |
GFR fraction |  0.15 |              |
### Metabolizing Enzyme: CYP1A2-CYP1A2

Species: Human
Molecule: CYP1A2
#### Parameters

Name                | Value       | Value Origin |
------------------- | ----------- | ------------ |
Intrinsic clearance | 0 l/min     |              |
Specific clearance  | 0.028 1/min | Unknown      |
### Metabolizing Enzyme: CYP2E1-CYP2E1

Species: Human
Molecule: CYP2E1
#### Parameters

Name                | Value       | Value Origin |
------------------- | ----------- | ------------ |
Intrinsic clearance | 0 l/min     |              |
Specific clearance  | 0.002 1/min | Unknown      |

## 3.2 Diagnostics Plots
Below you find the goodness-of-fit visual diagnostic plots for the PBPK model performance of all data used presented in [Section 2.2.2](#2.2 2	Clinical Data).

The first plot shows observed versus simulated plasma concentration, the second weighted residuals versus time. 


![001_plotGOFMergedPredictedVsObserved.png](images\003_3_Results_and_Discussion\002_3_2_Diagnostics_Plots\001_plotGOFMergedPredictedVsObserved.png)

![002_plotGOFMergedResidualsOverTime.png](images\003_3_Results_and_Discussion\002_3_2_Diagnostics_Plots\002_plotGOFMergedResidualsOverTime.png)

GMFE = 1.236970 

## 3.3: Concentration-Time Profiles
Simulated versus observed concentration-time profiles of all data listed in [Section 2.2.2](#2.2.2	Clinical Data) are presented below.


![003_plotTimeProfile.png](images\003_3_Results_and_Discussion\003_3_3__Concentration-Time_Profiles\003_plotTimeProfile.png)

![004_plotTimeProfile.png](images\003_3_Results_and_Discussion\003_3_3__Concentration-Time_Profiles\004_plotTimeProfile.png)

### 3.3.1 Model Building





### 3.3.2 Model Verification





# 4 Conclusion
The herein presented PBPK model adequately describes the pharmacokinetics of Theophylline in adults. Details of model development can be found in Yun and Edginton (2019).




# 5 References
**Kuepfer 2016** Kuepfer L, Niederalt C, Wendl T, Schlender JF, Willmann S, Lippert J, Block M, Eissing T, Teutonico D. Applied Concepts in PBPK Modeling: How to Build a PBPK/PD Model.CPT Pharmacometrics Syst Pharmacol. 2016 Oct;5(10):516-531. doi: 10.1002/psp4.12134. Epub 2016 Oct 19. 

**Drugbank DB00277** Drugbank DB00277 https://www.drugbank.ca/drugs/DB00277

PK-Sim Ontogeny Database Version 7.3 (https://github.com/Open-Systems-Pharmacology/OSPSuite.Documentation/blob/38cf71b384cfc25cfa0ce4d2f3addfd32757e13b/PK-Sim%20Ontogeny%20Database%20Version%207.3.pdf) 

**Yun 2019** Yun, Y.E. and A.N. Edginton, Model qualification of the PK-Sim® pediatric module for pediatric exposure assessment of CYP450 metabolized compounds. Journal of Toxicology and Environmental Health, Part A, 2019: p. 1-26.

**Steinijans 1987** Steinijans, V.W., et al., Absolute bioavailability of theophylline from a sustained-release formulation using different intravenous reference infusions. Eur J Clin Pharmacol, 1987. 33(5): p. 523-6.

**Gisclon 1997** Gisclon, L.G., et al., Absence of a pharmacokinetic interaction between intravenous theophylline and orally administered levofloxacin. The Journal of Clinical Pharmacology, 1997. 37(8): p. 744-750.

**Simons 1979** Simons, K.J., et al., Theophylline protein binding in humans. J Pharm Sci, 1979. 68(2): p. 252-3.
