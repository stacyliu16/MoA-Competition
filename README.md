# MoA-Competition
## Introduction
**What is the Mechanism of Action (MoA) of a drug? And why is it important?**

In the past, scientists derived drugs from natural products or were inspired by traditional remedies. Very common drugs, such as paracetamol, known in the US as acetaminophen, were put into clinical use decades before the biological mechanisms driving their pharmacological activities were understood. Today, with the advent of more powerful technologies, drug discovery has changed from the serendipitous approaches of the past to a more targeted model based on an understanding of the underlying biological mechanism of a disease. In this new framework, scientists seek to identify a protein target associated with a disease and develop a molecule that can modulate that protein target. As a shorthand to describe the biological activity of a given molecule, scientists assign a label referred to as mechanism-of-action or MoA for short.

**We have been challenged to predict which receptors a drug will bind to**. 

**The goal of EDA Notebook**: This notebook will be used to visualize the training data and gain some insights from it.

**The data**: In this competition, we will have access to a unique dataset that combines gene expression and cell viability data. The data is based on a new technology that measures simultaneously (within the same samples) human cells’ responses to drugs in a pool of 100 different cell types (thus solving the problem of identifying ex-ante, which cell types are better suited for a given drug). In addition, we will have access to MoA annotations for more than 5,000 drugs in this dataset.


The data comes in the shape of 3 separate files:

- train_features: 
    - sig_id: ID of each sample
    - columns starts with "g-": gene expression
    - columns starts with "c-": cell viability
    - cp_type: samples treated with compound (cp_vehicle) or with a control perturbation (ctrl_vehicle); control perturbations have no MoAs
    - cp_time: treatment duration (24, 48, 72 hrs)
    - dose: either high or low
- train_targets_scored: 
    - sig_id: ID of each sample
    - 206 receptors and enzyme which drug might bind with
- train_targets_nonscored.csv 
    - Additional (optional) binary MoA responses for the training data. These are not predicted nor scored.
- test_features: same format as train_features

**The metrics:**
The accuracy of solutions will be evaluated on the average value of the **logarithmic loss function** applied to each drug-MoA annotation pair.
