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
