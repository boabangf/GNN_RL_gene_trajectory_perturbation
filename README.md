Dataset: https://gitlab.com/stemcellbioengineering/iqcell/-/tree/master/Mouse%20T-cell%20Supplementary%20dataset?ref_type=heads



Title of  Talk: **** Machine Learning Optimization Methods and Their Application to Predicting T-Cell Differentiation Using GNNs and Reinforcement Learning****

#adata = sc.datasets.paul15()


#adata = sc.datasets.moignard15()


#adata = sc.datasets.visium_sge()

****(cell, gene)****
**** cellular level, gene level and molecular level-multimodal approach


****Algorithm  1  (suitable for higher number of perturbation which creates highly sparse data)

**Tested Cases: MAX_PERTURB: Maximum perturbation 4,5,6,7,8,9,10**
**MultiStep Prediction predicts the cell fate per stage**

In those environments,

MAX_PERTURB = the maximum number of perturbations allowed per single cell (during training episodes).

If MAX_PERTURB = 1 : only single-gene perturbations.

If MAX_PERTURB = 2 : allows double perturbations (pairwise knockouts).

If MAX_PERTURB = N (where N = total number of genes) 

The proposed ASGDAdam/ASGDAmsgrad optimizers (nonconvex case) are particularly well-suited for training on single-cell gene expression datasets, which are characterized by high sparsity—that is, a large proportion of the data consists of zeros due to gene perturbation. In such sparse settings, gradient updates often fluctuate between informative signals (non-zero values) and noise (zeros). A fixed base learning rate may either be too aggressive, leading to instability when rare informative signals appear, or too conservative, slowing convergence when the model mostly encounters zeros. By dynamically switching between a cautious base learning rate (lr_min) and a more aggressive one (lr_max), the ASGD optimizers adapt more effectively to these shifts. This dual learning rate mechanism allows the optimizer to exploit informative non-zero updates when available while avoiding overshooting during the many zero-gradient steps, making the training process more stable and better aligned with the properties of gene expression data.







In reinforcement learning, you can force local optima by:

Using short horizon episodes, so the policy learns a “shortcut” behavior that is locally optimal but not globally optimum. We proposed three algorithms to achieve a global optimal solution.




RL algorithms = {


    "A2C": {"class": A2C, "kwargs": {}},

    
    "PPO": {"class": PPO, "kwargs": {}},

    
    "SAC": {

    
        "class": SAC,

        
        "kwargs": {

        
            "learning_rate": 3e-4,

            
            "buffer_size": 1000000,

            
            "batch_size": 256,

            
            "tau": 0.005,

            
            "train_freq": (1, "step"),

            
            "gradient_steps": 1,

            
            "ent_coef": "auto"
        }
        
    },
    "TRPO": {"class": TRPO, "kwargs": {}},

    
    "TRPO_to_PPO": {"class": PPO, "kwargs": {}}, ***First stage of the Proposed method ***

    
    "TRPO_from_PPO": {"class": TRPO, "kwargs": {}} ***Second  stage of the Proposed method***


    
}

By starting with a few steps of TRPO before switching to PPO, we help the model avoid local optima and guide it toward a better solution.


train_steps = {


    "A2C": 100000,

    
    "PPO": 100000,

    
    "SAC": 100000,

    
    "TRPO": 100000,

    
    "TRPO_to_PPO": 1000, ***First stage of the Proposed method ***

    
    "TRPO_from_PPO": 99000 ***Second  stage of the Proposed method***

    
}



   

Algorithm 3

           ┌───────────────────────────┐
           │      Pretrained Policy     │
           └───────────────────────────┘
                       │
                       ▼
             ┌───────────────────┐
             │  Convex LoRA      │
             │ (stable, sample-  │
             │ efficient warm-up)│
             └───────────────────┘
                       │
                       ▼
             ┌───────────────────┐
             │ Non-Convex LoRA   │
             │ (flexible, escape │
             │ local optima)     │
             └───────────────────┘
                       │
                       ▼
             ┌───────────────────┐
             │  Full Fine-Tuning │
             │ or Standard RL    │
             │ (optional, full  │
             │ policy express.) │
             └───────────────────┘


Lora- standard for low rank matrix factoriaztion

We introduce a multistage Low-Rank Adaptation (LoRA) approach for reinforcement learning. The method starts with convex LoRA updates to stabilize training and improve sample efficiency, then transitions to non-convex LoRA to increase expressiveness and allow the policy to escape local optima.






***CITATION**


Heydari, Tiam, et al. "IQCELL: A platform for predicting the effect of gene perturbations on developmental trajectories using single-cell RNA-seq data." PLoS Computational Biology 18.2 (2022): e1009907.


Fu, Zeyu, et al. "scRL: Utilizing Reinforcement Learning to Evaluate Fate Decisions in Single-Cell Data." Biology 14.6 (2025): 679.
