# DARTA - A Permissionless Biomarker Data Marketplace

**DARTA**  is a web3 project that aims to build an accurate, valuation-based marketplace for biometric/clinical laboratory test data. It is designed to be a blockchain-based trusted and permissionless marketplace. Data with DARTA's precise valuation and robust transaction mechanism can be better transferred and used from data providers to requesters in developing useful AI models.

**DARTA** has a three-layer mechanism for ensuring the quality and value of the data on the platform. 
The 1st layer is a social credit system that records the credentials of data providers and helps establish their trustworthiness. 
The 2nd layer is a data valuation system that uses various statistical metrics to provide insight into the value of the data.
The 3rd layer focuses on creating various mechanisms to better match data providers and requesters.

# Layer of Trust on Social Credit
- building the marketplace system 
    - record the transaction on chain
    - the value of data also related to the credential of providers
    - pricing mechanism 

# Data Health Check-up
- data format 
    - [HL7 FHIR](https://hl7.org/fhir/) standard
    - basic lab data format that fit the input for R library [lab](https://github.com/DHLab-TSENG/lab) developed by Prof. Tseng
    - analysis-ready data format
- data metrics for valuation on IPFS/FVM
    - degree of rarity, suggesting exclusive/non-exclusive licensing
    - data usability, sharing data directly or contribution model development be federated learning
    - amount of data, missing percentage
    - characteristics
        - demographic stats
        - feature skewness / kurtosis
    - data characteristics change over time
    - data compatibility for sepcific models identified by data drift theory
    - data heterogeneity checking
        - data characteristics in different folds
        - models performances in different folds
        - cluster analysis for outliers detection
    - duplication checking: training data size impact on model performance (R caret, Python ScikitLearn/Pytorch, TensorFlow, etc.)

# Layer of Data-driven Appraisal on Data
- building the metrics and tools to value the data about
    - for requesters
        - what's the quantity and quality need for certain model application?
        - how to price the data by its value from model training perspective?
    - for data providers
        - what's the data value for individual model?
        - what's the new information contributing from the data?
        - what's the quality of data in term of model training?
    - mechanism on marketplace on Ethereum/Scroll
        - Whole dataset with appraisal report, and models, are licensed to the requesters
        - Whole dataset with appraisal report is licensed to the requesters
        - Model licensed to the requesters
        - Semi-contributor: the requsters upload their data to integrate into exisiting providers' data to have fine-tuned federated learning models
 
By contributing data to DARTA, you can earn economic incentives and contribute to research progress. Organizations can use the platform to access high-quality data and advance their research efforts.

We welcome contributions and feedback from the community. If you are interested in collaborating or have ideas for improving DARTA, please don't hesitate to reach out.
