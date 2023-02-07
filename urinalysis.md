Data-driven valuation on urinalysis data
================

This is an example of [the second layer of
DARTA](https://github.com/HsinYaoWang/DARTA#layer-of-data-driven-valuation-on-data),
**Layer of data-driven valuation on data**, with Urinalysis data.

## Data format

### HL7 FHIR

Laboratory data in [HL7 FHIR](https://hl7.org/fhir/) format, an
international standard for EHR, with [observation
resource](https://hl7.org/fhir/observation.html) can be used as an input
for DARTA.

### Basic lab data format

Basic lab data format with individual ID, laboratory test ID (or unique
name), date, test results.

### Analysis-ready data format

Analysis-ready data is composed of rows representing records, each with
a unique ID and all variables arranged in columns.

| Record ID | SEX | Age | Leu | Nitrite | Protein |  OB | RBC | WBC | EpCell | Trichomonas |
|----------:|:----|----:|----:|--------:|--------:|----:|----:|----:|-------:|:------------|
|         1 | F   |  85 |   2 |       1 |       2 |   2 |   2 | 154 |      1 | 1           |
|         2 | M   |  49 |   0 |       0 |       0 |   0 |   4 |   2 |      0 | 1           |
|         3 | F   |  31 |   0 |       0 |       0 |   0 |   0 |   2 |      6 | 0           |
|         4 | M   |  71 |   0 |       0 |       0 |   0 |   3 |   1 |      1 | 0           |
|         5 | F   |  46 |   1 |       0 |       0 |   0 |   4 |  26 |     28 | 0           |
|         6 | M   |  59 |   3 |       0 |       0 |   5 | 420 |  54 |      6 | 0           |
|         7 | F   |  34 |   1 |       0 |       0 |   0 |   1 |   5 |      6 | 0           |
|         8 | F   |  70 |   1 |       0 |       4 |   3 |   2 |   4 |      8 | 0           |
|         9 | M   |  11 |   0 |       0 |       0 |   0 |   0 |   0 |      0 | 0           |
|        10 | F   |  84 |   0 |       0 |       0 |   0 |   0 |   1 |      3 | 0           |

## Data metrics for valuation on IPFS/FVM

### Degree of rarity, exclusive/non-exclusive licensing

1.  Is there any publicly available dataset similar with the submitted
    data? (Yes/No)
    - No. There is no publicly available urinalysis data
2.  Licensing option. (exclusive/non-exclusive)
    - Non-exclusive

### Data usability and sharing options

1.  Can data be shared directly? (Yes/No)
    - Yes
2.  If data cannot be shared directly, provide the federated learning
    frameworks. (TensorFlow Federated/NVIDIA CLARA/OpenFL/Flower/etc.)
    - Not applicable (data can be shared directly)

### Amount of data

1.  Number of records
    - 839,164
2.  Number of variables
    - 10

### Characteristics

1.  Demographic stats
    - Age ![](urinalysis_files/figure-gfm/age-1.png)<!-- -->
    - Sex ![](urinalysis_files/figure-gfm/sex-1.png)<!-- -->
2.  Feature skewness / kurtosis

|                                                  |                       |
|:-------------------------------------------------|:----------------------|
| Name                                             | Trichomonas\[, 5:11\] |
| Number of rows                                   | 839155                |
| Number of columns                                | 7                     |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_   |                       |
| Column type frequency:                           |                       |
| numeric                                          | 7                     |
| \_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_ |                       |
| Group variables                                  | None                  |

Data summary

**Variable type: numeric**

| skim_variable | n_missing | complete_rate |  mean |     sd |  p0 | p25 | p50 | p75 | p100 | hist  |
|:--------------|----------:|--------------:|------:|-------:|----:|----:|----:|----:|-----:|:------|
| Leu           |         0 |             1 |  0.72 |   1.21 |   0 |   0 |   0 |   1 |    4 | ▇▂▁▁▁ |
| Nitrite       |         0 |             1 |  0.07 |   0.25 |   0 |   0 |   0 |   0 |    1 | ▇▁▁▁▁ |
| Protein       |         0 |             1 |  0.79 |   1.29 |   0 |   0 |   0 |   1 |    5 | ▇▁▁▁▁ |
| OB            |         0 |             1 |  1.09 |   1.49 |   0 |   0 |   0 |   2 |    5 | ▇▁▁▁▁ |
| RBC           |         0 |             1 | 36.04 | 107.67 |   0 |   0 |   2 |  10 |  501 | ▇▁▁▁▁ |
| WBC           |         0 |             1 | 36.94 | 103.49 |   0 |   0 |   3 |  13 |  501 | ▇▁▁▁▁ |
| EpCell        |         0 |             1 |  5.69 |  13.16 |   0 |   0 |   1 |   5 |  418 | ▇▁▁▁▁ |

Skewness & Kurtosis

|         | Skewness |  Kurtosis |
|:--------|---------:|----------:|
| Leu     | 1.578591 |  1.229976 |
| Nitrite | 3.504771 | 10.283433 |
| Protein | 1.487146 |  1.061333 |
| OB      | 1.040052 | -0.370144 |
| RBC     | 3.693680 | 12.554593 |
| WBC     | 3.702861 | 13.005261 |
| EpCell  | 4.484608 | 25.021743 |

### Data characteristics change over time

No time information in the dataset.

### Data heterogeneity checking

1.  Data characteristics in different folds
    - Randomly split the dataset into 10 folds

    - Check the differences between these 10 folds

|                     | 1              | 2              | 3              | 4              | 5              | 6              | 7              | 8              | 9              | 10             | p     | test |
|:--------------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:---------------|:------|:-----|
| n                   | 83916          | 83916          | 83916          | 83916          | 83915          | 83915          | 83915          | 83915          | 83915          | 83916          |       |      |
| SEX = M (%)         | 41087 (49.0)   | 41191 (49.1)   | 41213 (49.1)   | 40944 (48.8)   | 41042 (48.9)   | 41188 (49.1)   | 40909 (48.8)   | 41304 (49.2)   | 41137 (49.0)   | 40937 (48.8)   | 0.559 |      |
| Age (mean (SD))     | 48.20 (23.64)  | 48.21 (23.61)  | 48.24 (23.67)  | 48.20 (23.59)  | 48.39 (23.52)  | 48.15 (23.70)  | 48.17 (23.69)  | 48.26 (23.61)  | 48.22 (23.67)  | 48.23 (23.62)  | 0.774 |      |
| Leu (mean (SD))     | 0.73 (1.22)    | 0.72 (1.21)    | 0.71 (1.21)    | 0.72 (1.21)    | 0.72 (1.21)    | 0.72 (1.21)    | 0.72 (1.21)    | 0.72 (1.21)    | 0.72 (1.21)    | 0.72 (1.21)    | 0.122 |      |
| Nitrite (mean (SD)) | 0.07 (0.25)    | 0.06 (0.25)    | 0.06 (0.25)    | 0.07 (0.25)    | 0.07 (0.25)    | 0.06 (0.25)    | 0.07 (0.25)    | 0.07 (0.25)    | 0.07 (0.25)    | 0.07 (0.25)    | 0.091 |      |
| Protein (mean (SD)) | 0.80 (1.30)    | 0.78 (1.29)    | 0.79 (1.29)    | 0.78 (1.29)    | 0.78 (1.29)    | 0.79 (1.30)    | 0.79 (1.29)    | 0.79 (1.29)    | 0.78 (1.29)    | 0.79 (1.30)    | 0.345 |      |
| OB (mean (SD))      | 1.10 (1.50)    | 1.08 (1.49)    | 1.09 (1.49)    | 1.09 (1.50)    | 1.08 (1.49)    | 1.09 (1.49)    | 1.09 (1.49)    | 1.09 (1.49)    | 1.10 (1.50)    | 1.08 (1.49)    | 0.534 |      |
| RBC (mean (SD))     | 36.17 (107.86) | 36.05 (107.90) | 36.07 (107.85) | 36.04 (107.82) | 36.14 (107.89) | 35.86 (106.93) | 36.05 (107.64) | 35.81 (107.27) | 35.80 (107.13) | 36.38 (108.42) | 0.990 |      |
| WBC (mean (SD))     | 37.84 (104.92) | 36.67 (102.89) | 36.04 (101.99) | 37.04 (103.44) | 36.29 (102.47) | 37.27 (104.50) | 37.16 (103.73) | 36.65 (102.71) | 37.22 (104.04) | 37.22 (104.21) | 0.020 |      |
| EpCell (mean (SD))  | 5.75 (13.33)   | 5.70 (13.13)   | 5.71 (13.26)   | 5.69 (13.16)   | 5.69 (13.10)   | 5.65 (13.06)   | 5.77 (13.37)   | 5.72 (13.38)   | 5.62 (12.95)   | 5.61 (12.88)   | 0.241 |      |

2.  Models performances in different folds

| nth fold |     AUROC |
|---------:|----------:|
|        1 | 0.8872967 |
|        2 | 0.8800124 |
|        3 | 0.8314029 |
|        4 | 0.8256404 |
|        5 | 0.8105885 |
|        6 | 0.9101767 |
|        7 | 0.8795242 |
|        8 | 0.9071507 |
|        9 | 0.9421823 |
|       10 | 0.8802907 |

3.  Cluster analysis for outliers detection
   
   ![](urinalysis_files/figure-gfm/PCA-1.png)<!-- -->

### Duplication checking

1.  Training data size impact on model performance

- Sequentially add data (add 1/10 data per round) to the model
  development process and check the performance changes

| Number of records |     AUROC |
|------------------:|----------:|
|             83916 | 0.8658557 |
|            167832 | 0.8692465 |
|            251748 | 0.8867390 |
|            335664 | 0.8810154 |
|            419579 | 0.9148585 |
|            503494 | 0.9146025 |
|            587409 | 0.9099209 |
|            671324 | 0.9054694 |
|            755239 | 0.8815326 |
|            839155 | 0.9101476 |
