# DARTA - A Permissionless Biomarker Data Marketplace

**DARTA** is a web3 project that aims to build a marketplace for data related to biomarkers, laboratory test result. It is designed to be trustless and permissionless, allowing anyone to contribute data and organizations to access it for research or AI model training.

**DARTA** has a two-layer mechanism for ensuring the quality and value of the data on the platform. The first layer is a social credit system, which records the credentials of data providers and helps to establish their trustworthiness. The second layer is a data appraisal system, which uses various statistical metrics to provide insights on the value of the data.

# TODO
- data format 
    - HL7 compatible? based R library "lab" developed by Prof. Tseng
    - model format compatible?
- data metrics for valuation on IPFS/FVM
    - degree of rarity, suggesting exclusive/non-exclusive licensing
    - demographic stats
    - feature skewness / kurtosis
    - data change over time
    - data drift theory
    - data heterogeneity checking: models performances in different folds 
    - duplication checking: training data size impact on model performance (R caret, Python ScikitLearn/Pytorch, TensorFlow, etc.)
- mechanism on marketplace on Ethereum/Scroll


# Layer of trust on social credit
- building the marketplace system 
    - record the transaction on chain
    - the value of data also related to the credential of providers
    - pricing mechanism 

# Layer of data-driven valuation on data
- building the metrics and tools to value the data about
    - for requester
        - what's the quantity and quality need for certain model application
        - how to price the data by its valuation from model training perspective
    - for data contributer
        - what's the data value for individual model
        - what's the new information contributing from the data
        - what's the quality of data in term of model training



By contributing data to DARTA, you can earn economic incentives and contribute to research progress. Organizations can use the platform to access high-quality data and advance their research efforts.

We welcome contributions and feedback from the community. If you are interested in collaborating or have ideas for improving DARTA, please don't hesitate to reach out.
